---
title: 'Cómo: Configurar los servicios WCF para interoperar con clientes de WSE 3.0'
ms.date: 03/30/2017
ms.assetid: 0f38c4a0-49a6-437c-bdde-ad1d138d3c4a
ms.openlocfilehash: 174ecd279f9380136532ce0d5105b7a71b6d88da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-configure-wcf-services-to-interoperate-with-wse-30-clients"></a>Cómo: Configurar los servicios WCF para interoperar con clientes de WSE 3.0
Servicios de Windows Communication Foundation (WCF) son compatibles de nivel de conexión con Web Services Enhancements 3.0 para que los clientes de Microsoft .NET (WSE) cuando se configuran los servicios de WCF para usar la versión de agosto de 2004 de la especificación de WS-Addressing.  
  
### <a name="to-enable-a-wcf-service-to-interoperate-with-wse-30-clients"></a>Para permitir a un servicio de WCF interoperar con clientes de WSE 3.0  
  
1.  Definir un enlace personalizado para el servicio WCF.  
  
     Para especificar que la versión de agosto de 2004 de la especificación WS-Addressing se utiliza para la codificación de mensajes, se deberá crear un enlace personalizado.  
  
    1.  Agregar un elemento secundario [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) a la [ \<enlaces >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) del archivo de configuración del servicio.  
  
    2.  Especifique un nombre para el enlace agregando un [ \<enlace >](../../../../docs/framework/misc/binding.md) a la [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) y estableciendo el `name` atributo.  
  
    3.  Especifique un modo de autenticación y la versión de las especificaciones de WS-Security que se utilizan para proteger los mensajes que son compatibles con WSE 3.0, mediante la adición de un elemento secundario [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) a la [ \<enlace >](../../../../docs/framework/misc/binding.md).  
  
         Para establecer el modo de autenticación, establezca el `authenicationMode` atributo de la [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md). Un modo de autenticación es aproximadamente el equivalente a una aserción de seguridad lista para ser usada en WSE 3.0. La tabla siguiente asigna los modos de autenticación en WCF a las aserciones de seguridad inmediata en WSE 3.0.  
  
        |Modo de autenticación WCF|Aserción de seguridad lista para ser usada de WSE 3.0|  
        |-----------------------------|----------------------------------------|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>|`anonymousForCertificateSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.Kerberos>|`kerberosSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate10Security`*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate11Security`*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameOverTransport>|`usernameOverTransportSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameForCertificate>|`usernameForCertificateSecurity`|  
  
         \* Una de las diferencias principales entre el `mutualCertificate10Security` y `mutualCertificate11Security` aserciones de seguridad inmediata es la versión de la especificación de WS-Security que WSE utiliza para proteger los mensajes SOAP. Para `mutualCertificate10Security`, se utiliza WS-Security 1.0, mientras que WS-Security 1.1 se usa para `mutualCertificate11Security`. En WCF, se especifica la versión de la especificación WS-Security en el `messageSecurityVersion` atributo de la [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).  
  
         Para establecer la versión de la especificación de WS-Security que se usa para proteger los mensajes SOAP, establezca la `messageSecurityVersion` atributo de la [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md). Para interoperar con WSE 3.0, defina el valor del atributo `messageSecurityVersion` en <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>.  
  
    4.  Especificar que se usa la versión de agosto de 2004 de la especificación de WS-Addressing por WCF mediante la adición de un [ \<textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md) y establezca el `messageVersion` a su valor a <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>.  
  
        > [!NOTE]
        >  Cuando utilice SOAP 1.2, establezca el atributo `messageVersion` en <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>.  
  
2.  Especifique que el servicio utiliza el enlace personalizado.  
  
    1.  Establecer el `binding` atributo de la [ \<extremo >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) elemento `customBinding`.  
  
    2.  Establecer el `bindingConfiguration` atributo de la [ \<extremo >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) en el valor especificado en el `name` atributo de la [ \<enlace >](../../../../docs/framework/misc/binding.md) personalizada de enlace.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente especifica que `Service.HelloWorldService` utiliza un enlace personalizado para interoperar con clientes de WSE 3.0. El enlace personalizado especifica que se utiliza la versión de agosto de 2004 del conjunto de especificaciones WS-Addressing y WS-Security 1.1 para codificar los mensajes intercambiados. Los mensajes se protegen utilizando el modo de autenticación <xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>.  
  
```xml  
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
  
## <a name="see-also"></a>Vea también  
 [Personalización de un enlace proporcionado por el sistema](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)
