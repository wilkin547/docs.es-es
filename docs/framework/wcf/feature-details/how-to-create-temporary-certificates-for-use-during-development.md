---
title: 'Cómo: Crear certificados temporales que puedan utilizarse durante las operaciones de desarrollo'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], creating temporary certificates
- temporary certificates [WCF]
ms.assetid: bc5f6637-5513-4d27-99bb-51aad7741e4a
ms.openlocfilehash: ca495c23b30144013b8efe22b7bf6f3cf38b16cd
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "45969842"
---
# <a name="how-to-create-temporary-certificates-for-use-during-development"></a>Cómo: Crear certificados temporales que puedan utilizarse durante las operaciones de desarrollo
Al desarrollar un servicio seguro o cliente mediante Windows Communication Foundation (WCF), a menudo es necesario proporcionar un certificado X.509 que se usará como una credencial. El certificado forma normalmente parte de una cadena de certificados con una entidad emisora raíz situada en el almacén de las Entidades emisoras de certificados raíz de confianza del equipo. Tener una cadena de certificados le permite establecer un conjunto de certificados donde normalmente la entidad emisora raíz pertenece a su organización o unidad del negocio. Para emularlo en el momento de desarrollo, puede crear dos certificados para satisfacer los requisitos de seguridad. El primero es un certificado con firma automática que se coloca en el almacén de las Entidades emisoras de certificados raíz de confianza y el segundo certificado se crea a partir del primero y se coloca en el almacén personal de la ubicación del equipo local o en el almacén personal de la ubicación del usuario actual. En este tema se describe los pasos para crear estos dos certificados mediante el Powershell [New-SelfSignedCertificate)](https://docs.microsoft.com/en-us/powershell/module/pkiclient/new-selfsignedcertificate?view=win10-ps) cmdlet.  
  
> [!IMPORTANT]
>  Los certificados que genera el cmdlet New-SelfSignedCertificate se proporcionan únicamente con fines de prueba. Al implementar un servicio o cliente, asegúrese de usar un certificado adecuado proporcionado por una entidad de certificación. Esto podría ser de un servidor de certificados de Windows Server en su organización o un tercero.  
>   
>  De forma predeterminada, el [New-SelfSignedCertificate](https://docs.microsoft.com/en-us/powershell/module/pkiclient/new-selfsignedcertificate?view=win10-ps) cmdlet crea certificados autofirmados y estos certificados no son seguros. Almacén de colocación de los certificados autofirmados en las entidades de certificación raíz de confianza permite crear un entorno de desarrollo que simula el entorno de implementación.  
  
 Para obtener más información sobre la creación y uso de certificados, consulte [trabajar con certificados](../../../../docs/framework/wcf/feature-details/working-with-certificates.md). Para obtener más información sobre el uso de un certificado como credencial, vea [proteger servicios y clientes](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md). Para ver un tutorial sobre el uso de la tecnología Microsoft Authenticode, consulte [información general de Authenticode y tutoriales](https://go.microsoft.com/fwlink/?LinkId=88919).  
  
### <a name="to-create-a-self-signed-root-authority-certificate-and-export-the-private-key"></a>Para crear un certificado de la entidad de certificación raíz firmado automáticamente y exportar la clave privada  
  
El siguiente comando crea un certificado autofirmado con un nombre de sujeto de "RootCA" en el almacén Personal de usuario actual. 
```
PS $rootCert = New-SelfSignedCertificate -CertStoreLocation cert:\CurrentUser\My -DnsName "RootCA" -TextExtension @("1.3.6.1.4.1.311.21.10={text}1.3.6.1.5.5.7.3.1,1.3.6.1.5.5.7.3.2")
```
Es necesario exportar el certificado a un archivo PFX, por lo que puede importarse a cuando sea necesario en un paso posterior. Al exportar un certificado con la clave privada, se necesita una contraseña para protegerla. Se guarda la contraseña en un `SecureString` y usar el [Export-PfxCertificate](https://docs.microsoft.com/en-us/powershell/module/pkiclient/export-pfxcertificate?view=win10-ps) cmdlet para exportar el certificado con la clave privada asociada a un archivo PFX. También guardamos simplemente el certificado público en un archivo de CRT mediante el [Exportar certificado](https://docs.microsoft.com/en-us/powershell/module/pkiclient/export-certificate?view=win10-ps) cmdlet.
```
PS [System.Security.SecureString]$rootcertPassword = ConvertTo-SecureString -String "password" -Force -AsPlainText
PS [String]$rootCertPath = Join-Path -Path 'cert:\CurrentUser\My\' -ChildPath "$($rootcert.Thumbprint)"
PS Export-PfxCertificate -Cert $rootCertPath -FilePath 'RootCA.pfx' -Password $rootcertPassword
PS Export-Certificate -Cert $rootCertPath -FilePath 'RootCA.crt'
```

### <a name="to-create-a-new-certificate-signed-by-a-root-authority-certificate"></a>Crear un nuevo certificado firmado por un certificado de la entidad emisora raíz  
  
El siguiente comando crea un certificado firmado por la `RootCA` con un nombre de sujeto de "SignedByRootCA" mediante la clave privada del emisor.
```
PS $testCert = New-SelfSignedCertificate -CertStoreLocation Cert:\LocalMachine\My -DnsName "SignedByRootCA" -KeyExportPolicy Exportable -KeyLength 2048 -KeyUsage DigitalSignature,KeyEncipherment -Signer $rootCert 
```
De forma similar, guardamos el certificado de firma con la clave privada en un archivo PFX y solo la clave pública en un archivo de CRT.
```
PS [String]$testCertPath = Join-Path -Path 'cert:\LocalMachine\My\' -ChildPath "$($testCert.Thumbprint)"
PS Export-PfxCertificate -Cert $testCertPath -FilePath testcert.pfx -Password $rootcertPassword 
PS Export-Certificate -Cert $testCertPath -FilePath testcert.crt        
```
  
## <a name="installing-a-certificate-in-the-trusted-root-certification-authorities-store"></a>Instalar un certificado en el almacén de entidades de certificación raíz de confianza  
 Una vez creado un certificado firmado automáticamente, puede instalarlo en el almacén Entidades emisoras de certificados raíz de confianza. El equipo confía en todos los certificados firmados con el certificado en este punto. Por esta razón, elimine el certificado del almacén en cuanto ya no lo necesite. Cuando elimine este certificado de entidad emisora raíz, se desautorizan el resto de certificados que firmó con él. Los certificados de entidad emisora raíz simplemente son un mecanismo con el que se pueden incluir un grupo de certificados, cuando sea necesario. Por ejemplo, en aplicaciones punto a punto, normalmente no es necesario una entidad emisora raíz porque usted simplemente confía en la identidad de un individuo mediante el certificado proporcionado por él.  
  
#### <a name="to-install-a-self-signed-certificate-in-the-trusted-root-certification-authorities"></a>Instalar un certificado firmado automáticamente en las entidades emisoras de certificados raíz de confianza  
  
1.  Abra el complemento del certificado. Para obtener más información, vea [Cómo: Ver certificados con el complemento de MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).  
  
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
  
 En el archivo de configuración para un cliente, use el siguiente código XML para especificar que el certificado es se encuentre en el almacén del usuario y puede encontrarlo buscando el campo SubjectName para el valor "CohoWinery".  
  
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
