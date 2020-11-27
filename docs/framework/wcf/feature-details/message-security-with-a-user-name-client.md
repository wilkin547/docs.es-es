---
title: Seguridad de los mensajes con un cliente de nombres de usuario
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 36335cb9-76b8-4443-92c7-44f081eabb21
ms.openlocfilehash: 7168b393bde626c8c413cda3c7422e0eee4ce267
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96292875"
---
# <a name="message-security-with-a-user-name-client"></a>Seguridad de los mensajes con un cliente de nombres de usuario

En la ilustración siguiente se muestra un servicio y un cliente de Windows Communication Foundation (WCF) protegidos mediante la seguridad de nivel de mensaje. La autenticación del servicio se realiza mediante un certificado X.509. El cliente se autentica utilizando un nombre de usuario y contraseña.  
  
 Para obtener una aplicación de ejemplo, vea [nombre de usuario de seguridad de mensaje](../samples/message-security-user-name.md).  
  
 ![Seguridad de mensajes mediante la autenticación de nombre de usuario](media/1fb10a61-7e1d-42f5-b1af-195bfee5b3c6.gif "1fb10a61-7e1d-42f5-b1af-195bfee5b3c6")  
  
|Característica|Descripción|  
|--------------------|-----------------|  
|Modo de seguridad|Message|  
|Interoperabilidad|Solo Windows Communication Foundation (WCF)|  
|Autenticación (servidor)|La negociación inicial requiere autenticación de servidor|  
|Autenticación (cliente)|Nombre de usuario/contraseña|  
|Integridad|Sí, mediante el contexto de seguridad compartido|  
|Confidencialidad|Sí, mediante el contexto de seguridad compartido|  
|Transporte|HTTP|  
|Enlaces|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a>Servicio  

 El código y la configuración siguientes están diseñados para ejecutarse de forma independiente. Lleve a cabo una de las siguientes acciones:  
  
- Cree un servicio independiente mediante el código sin configuración.  
  
- Cree un servicio mediante la configuración proporcionada, pero sin definir ningún punto de conexión.  
  
### <a name="code"></a>Código  

 El código siguiente muestra cómo crear un extremo de servicio que utiliza la seguridad del mensaje.  
  
 [!code-csharp[C_SecurityScenarios#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#9)]
 [!code-vb[C_SecurityScenarios#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#9)]  
  
### <a name="configuration"></a>Configuración  

 La siguiente configuración se puede usar en lugar del código.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ServiceCredentialsBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"
                                storeLocation="LocalMachine"  
                                storeName="My"
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
                  bindingConfiguration="MessageAndUserName"  
                  name="SecuredByTransportEndpoint"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="MessageAndUserName">  
          <security mode="Message">
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a>Cliente  
  
### <a name="code"></a>Código  

 El siguiente código crea el cliente. El enlace es para la seguridad del modo de mensaje y el tipo de credencial de cliente está establecido en `UserName`. El nombre de usuario y la contraseña solo se pueden especificar mediante código (no es configurable). El código para devolver el nombre de usuario y la contraseña no se muestra aquí porque se debe hacer en el nivel de la aplicación. Por ejemplo, use un cuadro de diálogo de Windows Forms para solicitar los datos al usuario.  
  
 [!code-csharp[C_SecurityScenarios#16](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#16)]
 [!code-vb[C_SecurityScenarios#16](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#16)]  
  
### <a name="configuration"></a>Configuración  

 El siguiente código configura el cliente. El enlace es para la seguridad del modo de mensaje y el tipo de credencial de cliente está establecido en `UserName`. El nombre de usuario y la contraseña solo se pueden especificar mediante código (no es configurable).  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <dns value ="Contoso.com" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- [Información general sobre seguridad](security-overview.md)
- [Nombre de usuario de seguridad de mensaje](../samples/message-security-user-name.md)
- [Identidad del servicio y autenticación](service-identity-and-authentication.md)
- [\<identity>](../../configure-apps/file-schema/wcf/identity.md)
- [Modelo de seguridad para Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))
