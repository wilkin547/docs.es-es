---
title: Seguridad de mensajes con un cliente de certificado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 99770573-c815-4428-a38c-e4335c8bd7ce
ms.openlocfilehash: 2b2717bc68da9f07cd38e10a5d75b2a7df9add45
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602640"
---
# <a name="message-security-with-a-certificate-client"></a>Seguridad de mensajes con un cliente de certificado
El siguiente escenario muestra un cliente y un servicio de Windows Communication Foundation (WCF) protegidos mediante el modo de seguridad de mensajes. Tanto el cliente como el servicio se autentican con certificados. Para obtener más información, vea [seguridad de aplicaciones distribuidas](distributed-application-security.md).

 ![Captura de pantalla que muestra un cliente con certificado.](./media/message-security-with-a-certificate-client/client-with-certificate.gif)  
  
 Para obtener una aplicación de ejemplo, vea [certificado de seguridad de mensajes](../samples/message-security-certificate.md).  

|Característica|Descripción|  
|--------------------|-----------------|  
|Modo de seguridad|Message|  
|Interoperabilidad|Solo WCF|  
|Autenticación (servidor)|Con el certificado del servicio|  
|Autenticación (cliente)|Con el certificado del cliente|  
|Integridad|Sí|  
|Confidencialidad|Sí|  
|Transporte|HTTP|  
|Enlace|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a>web de Office  
 El código y la configuración siguientes están diseñados para ejecutarse de forma independiente. Lleve a cabo una de las siguientes acciones:  
  
- Cree un servicio independiente mediante el código sin configuración.  
  
- Cree un servicio mediante la configuración proporcionada, pero sin definir ningún punto de conexión.  
  
### <a name="code"></a>Código  
 El código siguiente muestra cómo crear un punto de conexión de servicio que utilice la seguridad del mensaje para establecer un contexto seguro.  
  
 [!code-csharp[C_SecurityScenarios#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#10)]
 [!code-vb[C_SecurityScenarios#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#10)]  
  
### <a name="configuration"></a>Configuración  
 En lugar del código, se puede utilizar la siguiente configuración.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ServiceCredentialsBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"  
                                x509FindType="FindBySubjectName" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service behaviorConfiguration="ServiceCredentialsBehavior"
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"
                  binding="wsHttpBinding"  
                  bindingConfiguration="MessageAndCertificateClient"
                  name="SecuredByClientCertificate"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator">  
          <security mode="Message">  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a>Cliente  
 El código y la configuración siguientes están diseñados para ejecutarse de forma independiente. Lleve a cabo una de las siguientes acciones:  
  
- Cree un cliente independiente mediante el código (y el código de cliente).  
  
- Cree un cliente que no defina direcciones de punto de conexión. En su lugar, utilice el constructor de cliente que adopta el nombre de configuración como un argumento. Por ejemplo:  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a>Código  
 El siguiente código crea el cliente. El enlace es para la seguridad del modo de mensaje y el tipo de credencial de cliente está establecido en `Certificate`.  
  
 [!code-csharp[C_SecurityScenarios#17](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#17)]
 [!code-vb[C_SecurityScenarios#17](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#17)]  
  
### <a name="configuration"></a>Configuración  
 La configuración siguiente especifica el certificado de cliente mediante un comportamiento del punto de conexión. Para más información, consulte [Trabajar con certificados](working-with-certificates.md). El código también usa un `identity` elemento <> para especificar un sistema de nombres de dominio (DNS) de la identidad de servidor esperada. Para obtener más información acerca de la identidad, consulte [identidad de servicio y autenticación](service-identity-and-authentication.md).  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="endpointCredentialsBehavior">  
          <clientCredentials>  
            <clientCertificate findValue="Cohowinery.com"
               storeLocation="LocalMachine"  
              x509FindType="FindBySubjectName" />  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"
                behaviorConfiguration="endpointCredentialsBehavior"  
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"  
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <dns value="Contoso.com" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- [Información general sobre seguridad](security-overview.md)
- [Identidad del servicio y autenticación](service-identity-and-authentication.md)
- [Trabajar con certificados](working-with-certificates.md)
- [Modelo de seguridad para Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
