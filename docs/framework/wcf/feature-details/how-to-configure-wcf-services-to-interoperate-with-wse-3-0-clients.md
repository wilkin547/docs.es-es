---
title: 'Cómo: Configurar los servicios WCF para interoperar con clientes de WSE 3.0'
ms.date: 03/30/2017
ms.assetid: 0f38c4a0-49a6-437c-bdde-ad1d138d3c4a
ms.openlocfilehash: bd9f2bec94ca45f76590f64366428a00edd5d6ea
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141743"
---
# <a name="how-to-configure-wcf-services-to-interoperate-with-wse-30-clients"></a>Cómo: Configurar los servicios WCF para interoperar con clientes de WSE 3.0

Los servicios de Windows Communication Foundation (WCF) son compatibles en el nivel de conexión con las mejoras de servicios web 3,0 para los clientes de Microsoft .NET (WSE) cuando los servicios WCF están configurados para usar la versión de agosto de 2004 de la especificación WS-Addressing.

### <a name="to-enable-a-wcf-service-to-interoperate-with-wse-30-clients"></a>Para permitir a un servicio de WCF interoperar con clientes de WSE 3.0

1. Defina un enlace personalizado para el servicio WCF.

    Para especificar que la versión de agosto de 2004 de la especificación WS-Addressing se utiliza para la codificación de mensajes, se deberá crear un enlace personalizado.

    1. Agregue un elemento secundario [\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) a los [enlaces de\<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) del archivo de configuración del servicio.

    2. Especifique un nombre para el enlace agregando un [> de enlace de\<](../../configure-apps/file-schema/wcf/bindings.md) a la [\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) y estableciendo el atributo `name`.

    3. Especifique un modo de autenticación y la versión de las especificaciones de WS-Security que se usan para proteger los mensajes compatibles con WSE 3,0 agregando un [> de seguridad de\<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) secundario al > de enlace de [\<](../../configure-apps/file-schema/wcf/bindings.md).

        Para establecer el modo de autenticación, establezca el atributo `authenticationMode` del [> de seguridad\<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md). Un modo de autenticación es aproximadamente el equivalente a una aserción de seguridad lista para ser usada en WSE 3.0. En la tabla siguiente se asignan modos de autenticación en WCF a las aserciones de seguridad llave en mano en WSE 3,0.

        |Modo de autenticación WCF|Aserción de seguridad lista para ser usada de WSE 3.0|
        |-----------------------------|----------------------------------------|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>|`anonymousForCertificateSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.Kerberos>|`kerberosSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate10Security`*|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate11Security`*|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameOverTransport>|`usernameOverTransportSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameForCertificate>|`usernameForCertificateSecurity`|

        \* una de las principales diferencias entre el `mutualCertificate10Security` y `mutualCertificate11Security` las aserciones de seguridad llave en mano es la versión de la especificación WS-Security que WSE utiliza para proteger los mensajes SOAP. Para `mutualCertificate10Security`, se utiliza WS-Security 1.0, mientras que WS-Security 1.1 se usa para `mutualCertificate11Security`. Para WCF, la versión de la especificación de WS-Security se especifica en el atributo `messageSecurityVersion` del [> de seguridad\<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).

        Para establecer la versión de la especificación de WS-Security que se usa para proteger los mensajes SOAP, establezca el atributo `messageSecurityVersion` del [> de seguridad\<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md). Para interoperar con WSE 3.0, defina el valor del atributo `messageSecurityVersion` en <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>.

    4. Especifique que WCF use la versión de agosto de 2004 de la especificación WS-Addressing agregando un [\<textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md) y establezca el `messageVersion` en su valor en <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>.

        > [!NOTE]
        > Cuando utilice SOAP 1.2, establezca el atributo `messageVersion` en <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>.

2. Especifique que el servicio utiliza el enlace personalizado.

    1. Establezca el atributo `binding` del elemento [> del punto de conexión de\<](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) en `customBinding`.

    2. Establezca el atributo `bindingConfiguration` del elemento [> del punto de conexión de\<](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) en el valor especificado en el atributo `name` del\<de [enlace >](../../configure-apps/file-schema/wcf/bindings.md) para el enlace personalizado.

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

- [Personalización de un enlace proporcionado por el sistema](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)
