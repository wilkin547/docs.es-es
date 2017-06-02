---
title: "C&#243;mo: Configurar los servicios WCF para interoperar con clientes de WSE 3.0 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0f38c4a0-49a6-437c-bdde-ad1d138d3c4a
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# C&#243;mo: Configurar los servicios WCF para interoperar con clientes de WSE 3.0
Los servicios de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] son compatibles en el nivel de conexión con Web Services Enhancements 3.0 para clientes de Microsoft .NET \(WSE\) cuando los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se configuran para utilizar la versión de agosto de 2004 de la especificación WS\-Addressing.  
  
### Para permitir a un servicio de WCF interoperar con clientes de WSE 3.0  
  
1.  Defina un enlace personalizado para el servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
     Para especificar que la versión de agosto de 2004 de la especificación WS\-Addressing se utiliza para la codificación de mensajes, se deberá crear un enlace personalizado.  
  
    1.  Agregue un [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) secundario a [\<enlaces\>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) del archivo de configuración del servicio.  
  
    2.  Especifique un nombre para el enlace, agregando [\<enlace\>](../../../../docs/framework/misc/binding.md) a [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) y estableciendo el atributo `name`.  
  
    3.  Especifique un modo de autenticación y la versión de las especificaciones de WS\-Security que se utilizan para proteger mensajes que son compatibles con WSE 3.0, agregando un [\<seguridad\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) secundario a [\<enlace\>](../../../../docs/framework/misc/binding.md).  
  
         Para establecer el modo de autenticación, establezca el atributo `authenicationMode` de [\<seguridad\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).Un modo de autenticación es aproximadamente el equivalente a una aserción de seguridad lista para ser usada en WSE 3.0.La tabla siguiente asigna los modos de autenticación en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] a las aserciones de seguridad listas para ser usadas en WSE 3.0.  
  
        |Modo de autenticación WCF|Aserción de seguridad lista para ser usada de WSE 3.0|  
        |-------------------------------|-----------------------------------------------------------|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode>|`anonymousForCertificateSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode>|`kerberosSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode>|`mutualCertificate10Security`\*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode>|`mutualCertificate11Security`\*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode>|`usernameOverTransportSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode>|`usernameForCertificateSecurity`|  
  
         \* Una de las diferencias principales entre las aserciones de seguridad listas para ser usadas `mutualCertificate10Security` y `mutualCertificate11Security` es la versión de la especificación WS\-Security que WSE utiliza para proteger los mensajes SOAP.Para `mutualCertificate10Security`, se utiliza WS\-Security 1.0, mientras que WS\-Security 1.1 se usa para `mutualCertificate11Security`.Para [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], la versión de la especificación WS\-Security se especifica en el atributo `messageSecurityVersion` de [\<seguridad\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).  
  
         Para establecer la versión de la especificación WS\-Security que se utiliza para proteger los mensajes SOAP, establezca el atributo `messageSecurityVersion` de [\<seguridad\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).Para interoperar con WSE 3.0, defina el valor del atributo `messageSecurityVersion` en <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>.  
  
    4.  Especifique que la versión de agosto de 2004 de la especificación WS\-Addressing se utiliza por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] agregando [\<textMessageEncoding\>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md) y defina `messageVersion` en su valor de <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>.  
  
        > [!NOTE]
        >  Cuando utilice SOAP 1.2, establezca el atributo `messageVersion` en <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>.  
  
2.  Especifique que el servicio utiliza el enlace personalizado.  
  
    1.  Establezca el atributo `binding` del elemento [\<extremo\>](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) en `customBinding`:  
  
    2.  Defina el atributo `bindingConfiguration` del elemento [\<extremo\>](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) en el valor especificado en al atributo `name` de [\<enlace\>](../../../../docs/framework/misc/binding.md) para el enlace personalizado.  
  
## Ejemplo  
 El ejemplo de código siguiente especifica que `Service.HelloWorldService` utiliza un enlace personalizado para interoperar con clientes de WSE 3.0.El enlace personalizado especifica que se utiliza la versión de agosto de 2004 del conjunto de especificaciones WS\-Addressing y WS\-Security 1.1 para codificar los mensajes intercambiados.Los mensajes se protegen utilizando el modo de autenticación <xref:System.ServiceModel.Configuration.AuthenticationMode>.  
  
```  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service   
        behaviorConfiguration="ServiceBehavior"   
        name="Service.HelloWorldService">  
        <endpoint binding="customBinding" address=""  
          bindingConfiguration="ServiceBinding"  
          contract="Service.IHelloWorld"></endpoint>  
      </service>  
    </services>  
  
    <bindings>  
      <customBinding>  
        <binding name="ServiceBinding">  
          <security authenticationMode="AnonymousForCertificate"  
                  messageProtectionOrder="SignBeforeEncrypt"  
                  messageSecurityVersion="WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10"  
                  requireDerivedKeys="false">  
          </security>  
          <textMessageEncoding messageVersion ="Soap11WSAddressingAugust2004"></textMessageEncoding>  
          <httpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
    <behaviors>  
      <behavior name="ServiceBehavior" returnUnknownExceptionsAsFaults="true">  
        <serviceCredentials>  
          <serviceCertificate findValue="CN=WCFQuickstartServer" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectDistinguishedName"/>  
        </serviceCredentials>  
      </behavior>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## Vea también  
 [Personalización de un enlace proporcionado por el sistema](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)