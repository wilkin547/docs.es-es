---
title: "Cómo: Crear certificados temporales que puedan utilizarse durante las operaciones de desarrollo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates [WCF], creating temporary certificates
- temporary certificates [WCF]
ms.assetid: bc5f6637-5513-4d27-99bb-51aad7741e4a
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4d6c955c3498c830403f628b4805611fadc44d68
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-temporary-certificates-for-use-during-development"></a>Cómo: Crear certificados temporales que puedan utilizarse durante las operaciones de desarrollo
Cuando se desarrolla un servicio seguro o cliente utilizando [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], a menudo es necesario proporcionar un certificado X.509 que se utilizará como una credencial. El certificado forma normalmente parte de una cadena de certificados con una entidad emisora raíz situada en el almacén de las Entidades emisoras de certificados raíz de confianza del equipo. Tener una cadena de certificados le permite establecer un conjunto de certificados donde normalmente la entidad emisora raíz pertenece a su organización o unidad del negocio. Para emularlo en el momento de desarrollo, puede crear dos certificados para satisfacer los requisitos de seguridad. El primero es un certificado con firma automática que se coloca en el almacén de las Entidades emisoras de certificados raíz de confianza y el segundo certificado se crea a partir del primero y se coloca en el almacén personal de la ubicación del equipo local o en el almacén personal de la ubicación del usuario actual. En este tema se describen los pasos para crear estos dos certificados con [Certificate Creation Tool (Herramienta de creación de certificados) (MakeCert.exe)](http://go.microsoft.com/fwlink/?LinkId=248185), proporcionada por el SDK de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] .  
  
> [!IMPORTANT]
>  Los certificados generados por la herramienta de creación de certificados sólo se proporcionan para pruebas. Al implementar un servicio o cliente, asegúrese de usar un certificado adecuado proporcionado por una entidad de certificación. Esto podría ser de un servidor de certificado [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] en su organización o de un tercero.  
>   
>  De forma predeterminada, el [Makecert.exe (herramienta de creación de certificados)](http://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d) crea certificados cuya entidad emisora raíz se denomina "Agencia raíz**."** Dado que la "Agencia raíz" no está en el almacén Entidades emisoras de certificados raíz de confianza, estos certificados no son seguros. Crear un certificado con firma automática que se coloca en el almacén Entidades emisoras de certificados raíz de confianza le permite crear un entorno de desarrollo que simula su entorno de distribución.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] cómo crear y usar certificados, consulte [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md). [!INCLUDE[crabout](../../../../includes/crabout-md.md)] cómo usar un certificado como credencial, consulte [Securing Services and Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md). Para obtener un tutorial sobre el uso de la tecnología Microsoft Authenticode, consulte [Authenticode Overviews and Tutorials (Información general y tutoriales de Authenticode)](http://go.microsoft.com/fwlink/?LinkId=88919).  
  
### <a name="to-create-a-self-signed-root-authority-certificate-and-export-the-private-key"></a>Para crear un certificado de la entidad de certificación raíz firmado automáticamente y exportar la clave privada  
  
1.  Utilice la herramienta MakeCert.exe con los modificadores siguientes:  
  
    1.  `-n` `subjectName`. Especifica el nombre del sujeto. La convención es prefijar el nombre sujeto con "CN = " para "Nombre Común."  
  
    2.  `-r`. Especifica que el certificado se firmará automáticamente.  
  
    3.  `-sv` `privateKeyFile`. Especifica el archivo que contiene el contenedor de clave privada.  
  
     Por ejemplo, el comando siguiente crea un certificado firmado automáticamente con un nombre sujeto de "CN=TempCA."  
  
    ```  
    makecert -n "CN=TempCA" -r -sv TempCA.pvk TempCA.cer  
    ```  
  
     Le solicitarán que proporcione una contraseña para proteger la clave privada. Esta contraseña es necesaria para crear un certificado firmado por este certificado raíz.  
  
### <a name="to-create-a-new-certificate-signed-by-a-root-authority-certificate"></a>Crear un nuevo certificado firmado por un certificado de la entidad emisora raíz  
  
1.  Utilice la herramienta MakeCert.exe con los modificadores siguientes:  
  
    1.  `-sk` `subjectKey`. La ubicación del contenedor de la clave del sujeto que contiene la clave privada. Si no existe un contenedor de claves, se creará uno. Si no se utiliza ninguna de las opciones - sk o - sv, se crea un contenedor de claves llamado JoeSoft de forma predeterminada.  
  
    2.  `-n` `subjectName`. Especifica el nombre del sujeto. La convención es prefijar el nombre sujeto con "CN = " para "Nombre Común."  
  
    3.  `-iv` `issuerKeyFile`. Especifica el archivo de clave privada .del emisor.  
  
    4.  `-ic` `issuerCertFile`. Especifica la ubicación del certificado del emisor.  
  
     Por ejemplo, el comando siguiente crea un certificado firmado por el certificado de entidad emisora raíz `TempCA` con un nombre sujeto de `"CN=SignedByCA"` utilizando la clave privada del emisor.  
  
    ```  
    makecert -sk SignedByCA -iv TempCA.pvk -n "CN=SignedByCA" -ic TempCA.cer SignedByCA.cer -sr currentuser -ss My  
    ```  
  
## <a name="installing-a-certificate-in-the-trusted-root-certification-authorities-store"></a>Instalar un certificado en el almacén de entidades de certificación raíz de confianza  
 Una vez creado un certificado firmado automáticamente, puede instalarlo en el almacén Entidades emisoras de certificados raíz de confianza. El equipo confía en todos los certificados firmados con el certificado en este punto. Por esta razón, elimine el certificado del almacén en cuanto ya no lo necesite. Cuando elimine este certificado de entidad emisora raíz, se desautorizan el resto de certificados que firmó con él. Los certificados de entidad emisora raíz simplemente son un mecanismo con el que se pueden incluir un grupo de certificados, cuando sea necesario. Por ejemplo, en aplicaciones punto a punto, normalmente no es necesario una entidad emisora raíz porque usted simplemente confía en la identidad de un individuo mediante el certificado proporcionado por él.  
  
#### <a name="to-install-a-self-signed-certificate-in-the-trusted-root-certification-authorities"></a>Instalar un certificado firmado automáticamente en las entidades emisoras de certificados raíz de confianza  
  
1.  Abra el complemento del certificado. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Cómo: ver certificados con el complemento de MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).  
  
2.  Abra la carpeta para almacenar el certificado, el **Equipo local** o el **Usuario actual**.  
  
3.  Abra la carpeta **Entidades emisoras de certificados raíz de confianza** .  
  
4.  Haga clic con el botón secundario en la carpeta **Certificados** y haga clic en **Todas las tareas**, a continuación, haga clic en **Importar**.  
  
5.  Siga las instrucciones del asistente en pantalla para importar TempCa.cer en el almacén.  
  
## <a name="using-certificates-with-wcf"></a>Uso de certificados con WCF  
 Una vez que se han preparado los certificados temporales, puede usarlos para desarrollar soluciones WCF que especifiquen los certificados como un tipo de credencial de cliente. Por ejemplo, en la siguiente configuración XML se especifica la seguridad de mensaje y un certificado como tipo de credencial de cliente.  
  
#### <a name="to-specify-a-certificate-as-the-client-credential-type"></a>Para especificar un certificado como tipo de credencial de cliente  
  
-   En el archivo de configuración de un servicio, use el código XML siguiente para establecer el modo de seguridad en mensaje y el tipo de credencial de cliente en certificado.  
  
    ```xml  
    <bindings>       
      <wsHttpBinding>  
        <binding name="CertificateForClient">  
          <security>  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    ```  
  
 En el archivo de configuración para un cliente, utilice el siguiente código XML para especificar que el certificado está en el almacén del usuario y puede encontrarse por campo SubjectName para el valor "CohoWinery".  
  
```xml  
<behaviors>  
  <endpointBehaviors>  
    <behavior name="CertForClient">  
      <clientCredentials>  
        <clientCertificate findValue="CohoWinery" x509FindType="FindBySubjectName" />  
       </clientCredentials>  
     </behavior>  
   </endpointBehaviors>  
</behaviors>  
```  
  
 Para obtener más información sobre el uso de certificados en WCF, consulte [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Asegúrese de eliminar cualquier los certificados temporales de entidad emisora raíz de las carpetas **Entidades emisoras de certificados raíz de confianza** y **Personal** haciendo clic con el botón secundario en el certificado y, a continuación, haciendo clic en **Eliminar**.  
  
## <a name="see-also"></a>Vea también  
 [Trabajo con certificados](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [Visualización de certificados con el complemento MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)  
 [Protección de servicios y clientes](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
