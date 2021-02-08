---
description: Más información acerca de cómo configurar servicios WCF para interoperar con clientes de WSE 3,0
title: Procedimiento para configurar los servicios WCF para interoperar con clientes de WSE 3.0
ms.date: 03/30/2017
ms.assetid: 0f38c4a0-49a6-437c-bdde-ad1d138d3c4a
ms.openlocfilehash: d48b24ac7787a9863744ee9b6a4a984cb6b371e4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99779938"
---
# <a name="how-to-configure-wcf-services-to-interoperate-with-wse-30-clients"></a>Procedimiento para configurar los servicios WCF para interoperar con clientes de WSE 3.0

Los servicios de Windows Communication Foundation (WCF) son compatibles en el nivel de conexión con las mejoras de servicios web 3,0 para los clientes de Microsoft .NET (WSE) cuando los servicios WCF están configurados para usar la versión 2004 de agosto de la especificación WS-Addressing.

### <a name="to-enable-a-wcf-service-to-interoperate-with-wse-30-clients"></a>Para permitir a un servicio de WCF interoperar con clientes de WSE 3.0

1. Defina un enlace personalizado para el servicio WCF.

    Para especificar que la versión de agosto de 2004 de la especificación WS-Addressing se utiliza para la codificación de mensajes, se deberá crear un enlace personalizado.

    1. Agregue un elemento secundario [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) al [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) del archivo de configuración del servicio.

    2. Especifique un nombre para el enlace agregando [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) y estableciendo el `name` atributo.

    3. Especifique un modo de autenticación y la versión de las especificaciones de WS-Security que se usan para proteger los mensajes que son compatibles con WSE 3,0, agregando un elemento secundario [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) al [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) .

        Para establecer el modo de autenticación, establezca el `authenticationMode` atributo de [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) . Un modo de autenticación es aproximadamente el equivalente a una aserción de seguridad lista para ser usada en WSE 3.0. En la tabla siguiente se asignan modos de autenticación en WCF a las aserciones de seguridad llave en mano en WSE 3,0.

        |Modo de autenticación WCF|Aserción de seguridad lista para ser usada de WSE 3.0|
        |-----------------------------|----------------------------------------|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>|`anonymousForCertificateSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.Kerberos>|`kerberosSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate10Security`*|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate11Security`*|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameOverTransport>|`usernameOverTransportSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameForCertificate>|`usernameForCertificateSecurity`|

        \* Una de las principales diferencias entre las `mutualCertificate10Security` `mutualCertificate11Security` aserciones de seguridad y llave en mano es la versión de la especificación WS-Security que WSE utiliza para proteger los mensajes SOAP. Para `mutualCertificate10Security`, se utiliza WS-Security 1.0, mientras que WS-Security 1.1 se usa para `mutualCertificate11Security`. Para WCF, la versión de la especificación WS-Security se especifica en el `messageSecurityVersion` atributo de [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) .

        Para establecer la versión de la especificación WS-Security que se usa para proteger los mensajes SOAP, establezca el `messageSecurityVersion` atributo de [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) . Para interoperar con WSE 3.0, defina el valor del atributo `messageSecurityVersion` en <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>.

    4. Especifique que WCF usa la versión de agosto de 2004 de la especificación WS-Addressing agregando [\<textMessageEncoding>](../../configure-apps/file-schema/wcf/textmessageencoding.md) y establezca `messageVersion` en su valor en <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A> .

        > [!NOTE]
        > Cuando utilice SOAP 1.2, establezca el atributo `messageVersion` en <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>.

2. Especifique que el servicio utiliza el enlace personalizado.

    1. Establezca el `binding` atributo del [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) elemento en `customBinding` .

    2. Establezca el `bindingConfiguration` atributo del [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) elemento en el valor especificado en el `name` atributo de [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) para el enlace personalizado.

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

- [Procedimiento para personalizar un enlace proporcionado por el sistema](../extending/how-to-customize-a-system-provided-binding.md)
