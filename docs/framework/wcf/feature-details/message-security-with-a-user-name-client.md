---
title: "Seguridad de los mensajes con un cliente de nombres de usuario | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 36335cb9-76b8-4443-92c7-44f081eabb21
caps.latest.revision: 15
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 15
---
# Seguridad de los mensajes con un cliente de nombres de usuario
La ilustración siguiente muestra un servicio y cliente de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] protegidos mediante seguridad del nivel de mensaje.La autenticación del servicio se realiza mediante un certificado X.509.El cliente se autentica utilizando un nombre de usuario y contraseña.  
  
 Para obtener una aplicación de ejemplo, vea [Nombre de usuario de seguridad de mensaje](../../../../docs/framework/wcf/samples/message-security-user-name.md).  
  
 ![Seguridad de mensajes mediante la autenticación de nombre de usuario](../../../../docs/framework/wcf/feature-details/media/1fb10a61-7e1d-42f5-b1af-195bfee5b3c6.gif "1fb10a61\-7e1d\-42f5\-b1af\-195bfee5b3c6")  
  
|Característica|Descripción|  
|--------------------|-----------------|  
|Modo de seguridad|Mensaje|  
|Interoperabilidad|Solo [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]|  
|Autenticación \(servidor\)|La negociación inicial requiere autenticación de servidor|  
|Autenticación \(cliente\)|Nombre de usuario\/contraseña|  
|Integridad|Sí, mediante el contexto de seguridad compartido|  
|Confidencialidad|Sí, mediante el contexto de seguridad compartido|  
|Transporte|HTTP|  
|Enlace|<xref:System.ServiceModel.WSHttpBinding>|  
  
## Servicio  
 El código y la configuración siguientes están diseñados para ejecutarse de forma independiente.Siga uno de los procedimientos siguientes:  
  
-   Cree un servicio independiente mediante el código sin configuración.  
  
-   Cree un servicio con la configuración proporcionada, pero sin definir ningún extremo.  
  
### Código  
 El código siguiente muestra cómo crear un extremo de servicio que utiliza la seguridad del mensaje.  
  
 [!code-csharp[C_SecurityScenarios#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#9)]
 [!code-vb[C_SecurityScenarios#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#9)]  
  
### Configuración  
 La siguiente configuración se puede usar en lugar del código.  
  
```  
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
  
## Client  
  
### Código  
 El siguiente código crea el cliente.El enlace es para la seguridad del modo de mensaje y el tipo de credencial de cliente está establecido en `UserName`.El nombre de usuario y la contraseña solo se pueden especificar mediante código \(no es configurable\).El código para devolver el nombre de usuario y la contraseña no se muestra aquí porque se debe hacer en el nivel de la aplicación.Por ejemplo, use un cuadro de diálogo de Window Forms para solicitar los datos al usuario.  
  
 [!code-csharp[C_SecurityScenarios#16](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#16)]
 [!code-vb[C_SecurityScenarios#16](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#16)]  
  
### Configuración  
 El siguiente código configura el cliente.El enlace es para la seguridad del modo de mensaje y el tipo de credencial de cliente está establecido en `UserName`.El nombre de usuario y la contraseña solo se pueden especificar mediante código \(no es configurable\).  
  
```  
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
  
## Vea también  
 [Información general sobre seguridad](../../../../docs/framework/wcf/feature-details/security-overview.md)   
 [Nombre de usuario de seguridad de mensaje](../../../../docs/framework/wcf/samples/message-security-user-name.md)   
 [Identidad del servicio y autenticación](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)   
 [\<identidad\>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)   
 [Modelo de seguridad para Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)