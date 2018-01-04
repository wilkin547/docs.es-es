---
title: "Cómo: Especificar los valores de credenciales de cliente"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 82293d7f-471a-4549-8f19-0be890e7b074
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cd818a2342ff5b44e4e8ab1b237f7c657d3bf438
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-client-credential-values"></a>Cómo: Especificar los valores de credenciales de cliente
Con [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], el servicio puede especificar cómo se debe autenticar un cliente con él. Por ejemplo, un servicio puede estipular que el cliente se autentique mediante un certificado.  
  
### <a name="to-determine-the-client-credential-type"></a>Para determinar el tipo de credencial de cliente  
  
1.  Recupere los metadatos del extremo de metadatos del servicio. Normalmente, los metadatos constan de dos archivos: el código de cliente en el lenguaje de programación elegido (el predeterminado es Visual C#), y un archivo de configuración XML. Una manera de recuperar los metadatos consiste en usar la herramienta Svcutil.exe para devolver el código y la configuración de cliente. Para obtener más información, consulte [recuperación de metadatos](../../../docs/framework/wcf/feature-details/retrieving-metadata.md) y [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
2.  Abra el archivo de configuración XML. Si usa la herramienta Svcutil.exe, el nombre predeterminado del archivo es Output.config.  
  
3.  Buscar el  **\<seguridad >** elemento con la **modo** atributo (**< SecurityMode =** `MessageOrTransport`  **>**  donde `MessageOrTransport` se establece en uno de los modos de seguridad.  
  
4.  Busque el elemento secundario que coincida con el valor del modo. Por ejemplo, si el modo está establecido en **mensaje**, buscar el  **\<mensaje >** los elementos en el  **\<seguridad >** elemento.  
  
5.  Tenga en cuenta el valor asignado a la **clientCredentialType** atributo. El valor real dependerá del modo que se use, de transporte o de mensaje.  
  
 El código XML siguiente muestra la configuración de un cliente usando la seguridad de mensajes y solicitando un certificado para autenticar al cliente.  
  
```xml  
<security mode="Message">  
    <transport clientCredentialType="Windows" proxyCredentialType="None"  
        realm="" />  
     <message clientCredentialType="Certificate" negotiateServiceCredential="true"  
    algorithmSuite="Default" establishSecurityContext="true" />  
</security>  
```  
  
## <a name="example-tcp-transport-mode-with-certificate-as-client-credential"></a>Ejemplo: modo de transporte TCP con certificado como credencial de cliente  
 Este ejemplo establece el modo de seguridad en transporte y establece el valor de credencial de cliente en un certificado X.509. Los procedimientos siguientes muestran cómo establecer el valor de credencial de cliente en el cliente en código y configuración. Se supone que ha usado el [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para devolver los metadatos (código y configuración) desde el servicio. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Cómo: crear un cliente](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).  
  
#### <a name="to-specify-the-client-credential-value-on-the-client-in-code"></a>Para especificar el valor de credencial de cliente en el cliente en código  
  
1.  Use la [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para generar código y la configuración del servicio.  
  
2.  Cree una instancia del cliente [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] utilizando el código generado.  
  
3.  En la clase de cliente, establezca la propiedad <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> de la clase <xref:System.ServiceModel.ClientBase%601> en un valor adecuado. Este ejemplo establece la propiedad en un certificado X.509 utilizando el método <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> de la clase <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>.  
  
     [!code-csharp[c_TcpService#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpservice/cs/source.cs#4)]
     [!code-vb[c_TcpService#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpservice/vb/source.vb#4)]  
  
     Puede utilizar cualquiera de las enumeraciones de la clase <xref:System.Security.Cryptography.X509Certificates.X509FindType>. El nombre de sujeto se utiliza aquí en caso de que se cambie el certificado (debido a una fecha de caducidad). Utilizar el nombre de sujeto permite a la infraestructura encontrar de nuevo el certificado.  
  
#### <a name="to-specify-the-client-credential-value-on-the-client-in-configuration"></a>Para especificar el valor de credencial de cliente en el cliente en configuración  
  
1.  Agregar un [ \<comportamiento >](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) elemento a la [ \<comportamientos >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento.  
  
2.  Agregar un [ \<clientCredentials >](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elemento a la [ \<comportamientos >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento. Asegúrese de establecer el atributo `name` necesario en un valor adecuado.  
  
3.  Agregar un [ \<clientCertificate >](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) elemento a la [ \<clientCredentials >](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elemento.  
  
4.  Establezca los atributos siguientes en los valores adecuados: `storeLocation`, `storeName`, `x509FindType` y `findValue`, como se muestra en el código siguiente. [!INCLUDE[crabout](../../../includes/crabout-md.md)]certificados, consulte [trabajar con certificados](../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
    ```xml  
    <behaviors>  
       <endpointBehaviors>  
          <behavior name="endpointCredentialBehavior">  
            <clientCredentials>  
              <clientCertificate findValue="Contoso.com"   
                                 storeLocation="LocalMachine"  
                                 storeName="TrustedPeople"  
                                 x509FindType="FindBySubjectName" />  
            </clientCredentials>  
          </behavior>  
       </endpointBehaviors>  
    </behaviors>  
    ```  
  
5.  Al configurar el cliente, especifique el comportamiento estableciendo el atributo `behaviorConfiguration` del elemento `<endpoint>`, como se muestra en el código siguiente. El punto de conexión es un elemento secundario de la [ \<cliente >](../../../docs/framework/configure-apps/file-schema/wcf/client.md) elemento. Especifique también el nombre de la configuración de enlace estableciendo el atributo `bindingConfiguration` en el enlace para el cliente. Si está utilizando un archivo de configuración generado, se genera automáticamente el nombre del enlace. En este ejemplo, el nombre es `"tcpBindingWithCredential"`.  
  
    ```xml  
    <client>  
      <endpoint name =""  
                address="net.tcp://contoso.com:8036/aloha"  
                binding="netTcpBinding"  
                bindingConfiguration="tcpBindingWithCredential"  
                behaviorConfiguration="endpointCredentialBehavior" />  
    </client>  
    ```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.NetTcpBinding>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>  
 <xref:System.ServiceModel.ClientBase%601>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>  
 [Programación de la seguridad de WCF](../../../docs/framework/wcf/feature-details/programming-wcf-security.md)  
 [Selección de tipos de credenciales](../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [Trabajo con certificados](../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [Cómo crear un cliente](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [\<netTcpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)  
 [\<seguridad >](../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)  
 [\<mensaje >](../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-nettcpbinding.md)  
 [\<comportamiento >](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)  
 [\<comportamientos >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)  
 [\<clientCertificate >](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)  
 [\<clientCredentials >](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)
