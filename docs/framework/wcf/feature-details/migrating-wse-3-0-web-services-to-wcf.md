---
title: Migración de los servicios web WSE 3.0 a WCF
ms.date: 03/30/2017
ms.assetid: 7bc5fff7-a2b2-4dbc-86cc-ecf73653dcdc
ms.openlocfilehash: 8f79674350109d111fe263704dee6c40c1a12451
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184578"
---
# <a name="migrating-wse-30-web-services-to-wcf"></a>Migración de los servicios web WSE 3.0 a WCF
Las ventajas de migrar los servicios web de WSE 3.0 a Windows Communication Foundation (WCF) incluyen un rendimiento mejorado y la compatibilidad de transportes adicionales, escenarios de seguridad adicionales y especificaciones WS-*. Un servicio web que se migra de WSE 3.0 a WCF puede experimentar una mejora de rendimiento de hasta un 200 % a un 400 %. Para obtener más información acerca de los transportes admitidos por WCF, vea [elegir un transporte](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md). Para obtener una lista de los escenarios admitidos por WCF, vea [escenarios](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)de seguridad comunes . Para obtener una lista de las especificaciones admitidas por WCF, vea Guía de interoperabilidad de [protocolos](../../../../docs/framework/wcf/feature-details/web-services-protocols-interoperability-guide.md)de servicios web .  
  
 En las secciones siguientes se proporcionan instrucciones sobre cómo migrar una característica específica de un servicio web WSE 3.0 a WCF.  
  
## <a name="general"></a>General  
 Las aplicaciones WSE 3.0 y WCF incluyen interoperabilidad a nivel de cable y un conjunto común de terminología. Las aplicaciones WSE 3.0 y WCF son interoperables a nivel de cable en función del conjunto de especificaciones WS-* que admiten ambas. Cuando se desarrolla una aplicación WSE 3.0 o WCF hay un conjunto común de terminología, como los nombres de las aserciones de seguridad llave en mano en WSE y los modos de autenticación.  
  
 Aunque hay muchos aspectos similares entre los modelos de programación WCF y ASP.NET o WSE 3.0, son diferentes. Para obtener más información sobre el modelo de programación WCF, vea Ciclo de vida de [programación básica](../../../../docs/framework/wcf/basic-programming-lifecycle.md).  
  
> [!NOTE]
> Para migrar un servicio web WSE a WCF, se puede usar la herramienta de utilidad de metadatos de [ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para generar un cliente. No obstante, ese cliente contiene interfaces y clases que también pueden usarse como punto inicial para un servicio WCF. Las interfaces que se generan tienen el atributo <xref:System.ServiceModel.OperationContractAttribute> aplicado a los miembros del contrato con la propiedad <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> establecida en `*` Cuando un cliente WSE llama a un servicio web con esta configuración, se produce la siguiente excepción: **Web.Services3.ResponseProcessingException: WSE910: Se ha producido un error durante el procesamiento de un mensaje de respuesta y puede encontrar el error en la excepción interna**. Para mitigar esto, establezca la propiedad <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> del atributo <xref:System.ServiceModel.OperationContractAttribute> en un valor que no sea `null`, como `http://Microsoft.WCF.Documentation/ResponseToOCAMethod`.  
  
## <a name="security"></a>Seguridad  
  
### <a name="wse-30-web-services-that-are-secured-using-a-policy-file"></a>Los servicios web WSE 3.0 que se protegen mediante un archivo de directivas  
 Los servicios WCF pueden usar un archivo de configuración para proteger un servicio y ese mecanismo es similar a un archivo de directiva WSE 3.0. En WSE 3.0, al proteger un servicio web mediante un archivo de directivas, utiliza una aserción de seguridad inmediata o una aserción de directiva personalizada. Las aserciones de seguridad llave en mano se asignan estrechamente al modo de autenticación de un elemento de enlace de seguridad WCF. No solo los modos de autenticación WCF y las aserciones de seguridad llave en mano de WSE 3.0 no solo tienen el mismo nombre o de forma similar, sino que protegen los mensajes con los mismos tipos de credenciales. Por ejemplo, `usernameForCertificate` la aserción de seguridad llave `UsernameForCertificate` en mano en WSE 3.0 se asigna al modo de autenticación en WCF. En los ejemplos de código siguientes `usernameForCertificate` se muestra cómo una directiva mínima que `UsernameForCertificate` usa la aserción de seguridad llave en mano en WSE 3.0 se asigna a un modo de autenticación en WCF en un enlace personalizado.  
  
 **WSE 3.0**  
  
```xml  
<policies>  
  <policy name="MyPolicy">  
    <usernameForCertificate messageProtectionOrder="SignBeforeEncrypt"  
                            requireDeriveKeys="true"/>  
  </policy>  
</policies>  
```  
  
 **WCF**  
  
```xml  
<customBinding>  
  <binding name="MyBinding">  
    <security authenticationMode="UserNameForCertificate"
              messageProtectionOrder="SignBeforeEncrypt"  
              requireDerivedKeys="true"/>  
  </binding>  
</customBinding>  
```  
  
 Para migrar la configuración de seguridad de un servicio web WSE 3.0 que se especifica en un archivo de directiva a WCF, se debe crear un enlace personalizado en un archivo de configuración y la aserción de seguridad llave en mano debe establecerse en su modo de autenticación equivalente. Además, el enlace personalizado debe configurarse para que utilice la especificación WS-Addressing de agosto de 2004 cuando los clientes WSE 3.0 se comunican con el servicio. Cuando el servicio WCF migrado no requiere comunicación con los clientes de WSE 3.0 y solo debe mantener la paridad de seguridad, considere la posibilidad de usar los enlaces definidos por el sistema WCF con la configuración de seguridad adecuada en lugar de crear un enlace personalizado.  
  
 En la tabla siguiente se muestra la asignación entre un archivo de directiva WSE 3.0 y el enlace personalizado equivalente en WCF.  
  
|Aserción de seguridad inmediata de WSE 3.0|Configuración de enlace personalizado de WCF|  
|----------------------------------------|--------------------------------------|  
|\<usernameOverTransportSecurity />|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="UserNameOverTransport" />     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<mutualCertificate10Security />|`<customBinding>   <binding name="MyBinding">     <security messageSecurityVersion="WSSecurity10WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10" authenticationMode="MutualCertificate" />     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<usernameForCertificateSecurity />|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="UsernameForCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<anonymousForCertificateSecurity />|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="AnonymousForCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<kerberosSecurity />|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="Kerberos"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<mutualCertificate11Security />|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="MutualCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
  
 Para obtener más información acerca de cómo crear enlaces personalizados en WCF, vea [enlaces personalizados](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
### <a name="wse-30-web-services-that-are-secured-using-application-code"></a>Servicios web WSE 3.0 que se protegen mediante código de aplicaciones  
 Si se usa WSE 3.0 o WCF, los requisitos de seguridad se pueden especificar en el código de aplicación en lugar de en la configuración. En WSE 3.0, esto se logra creando una clase que derive de la clase `Policy` y, a continuación, agregando los requisitos llamando al método `Add`. Para obtener más información acerca de cómo especificar los requisitos de seguridad en el código, vea [Cómo: proteger un servicio web sin usar un archivo](https://docs.microsoft.com/previous-versions/dotnet/netframework-2.0/aa528763(v=msdn.10))de directiva . En WCF, para especificar los requisitos de <xref:System.ServiceModel.Channels.BindingElementCollection> seguridad en el <xref:System.ServiceModel.Channels.SecurityBindingElement> código, <xref:System.ServiceModel.Channels.BindingElementCollection>cree una instancia de la clase y agregue una instancia de un archivo . Los requisitos de aserción de seguridad se establecen mediante los métodos de ayuda del modo de autenticación estático de la clase <xref:System.ServiceModel.Channels.SecurityBindingElement>. Para obtener más información acerca de cómo especificar los requisitos de seguridad en el código mediante WCF, vea [Cómo: crear un enlace personalizado mediante el SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md) y [Cómo: crear un SecurityBindingElement para un modo](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)de autenticación especificado .  
  
### <a name="wse-30-custom-policy-assertion"></a>Aserción de directivas personalizadas WSE 3.0  
 En WSE 3.0 hay dos tipos de aserciones de directivas personalizadas: las que protegen un mensaje SOAP y las que no protegen un mensaje SOAP. Aserciones de directiva que los mensajes `SecurityPolicyAssertion` SOAP seguros derivan de WSE 3.0 clase y el equivalente conceptual en WCF es la <xref:System.ServiceModel.Channels.SecurityBindingElement> clase.  
  
 Un punto importante a tener en cuenta es que las aserciones de seguridad llave en mano de WSE 3.0 son un subconjunto de los modos de autenticación WCF. Si ha creado una aserción de directiva personalizada en WSE 3.0, puede haber un modo de autenticación WCF equivalente. Por ejemplo, WSE 3.0 no proporciona ninguna aserción de seguridad de CertificateOverTransport que sea el equivalente a la aserción de seguridad inmediata `UsernameOverTransport`, pero utiliza un certificado X.509 para la autenticación del cliente. Si ha definido su propia aserción de directiva personalizada para este escenario, WCF simplifica la migración. WCF define un modo de autenticación para este escenario, por lo que<xref:System.ServiceModel.Channels.SecurityBindingElement>puede aprovechar los métodos auxiliares de modo de autenticación estática para configurar un WCF .  
  
 Cuando no hay un modo de autenticación WCF que sea equivalente a una <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>aserción de directiva personalizada que protege los mensajes SOAP, derive una clase de , <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> o <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>clases WCF y especifique el elemento de enlace equivalente. Para obtener más información, vea [Cómo: crear un enlace personalizado mediante SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
 Para convertir una aserción de directiva personalizada que no protege un mensaje SOAP, consulte [Filtrado](../../../../docs/framework/wcf/feature-details/filtering.md) y el interceptor de mensajes [personalizados](../../../../docs/framework/wcf/samples/custom-message-interceptor.md)de ejemplo.  
  
### <a name="wse-30-custom-security-token"></a>Token de seguridad personalizado de WSE 3.0  
 El modelo de programación WCF para crear un token personalizado es diferente de WSE 3.0. Para obtener más información sobre cómo crear un token personalizado en WSE, consulte Creación de tokens de [seguridad personalizados](https://docs.microsoft.com/previous-versions/dotnet/netframework-2.0/aa529304(v=msdn.10)). Para obtener información detallada acerca de cómo crear un token personalizado en WCF, vea [Cómo: crear un token personalizado](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).  
  
### <a name="wse-30-custom-token-manager"></a>Administrador de tokens personalizados de WSE 3.0  
 El modelo de programación para crear un administrador de tokens personalizado es diferente en WCF que WSE 3.0. Para obtener más información sobre cómo crear un administrador de tokens personalizado y los demás componentes necesarios para un token de seguridad personalizado, consulte [Cómo: crear un token personalizado](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).  
  
> [!NOTE]
> Si ha creado `UsernameToken` un administrador de tokens de seguridad personalizado, WCF proporciona un mecanismo más fácil para especificar la lógica de autenticación que crear un administrador de tokens de seguridad personalizado. Para obtener más información, consulte [Cómo: Usar un validador](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md)de nombre de usuario y contraseña personalizado .  
  
### <a name="wse-30-web-services-that-use-mtom-encoded-soap-messages"></a>Servicio web de WSE 3.0 que usan mensajes SOAP codificados mediante MTOM  
 Al igual que una aplicación WSE 3, una aplicación WCF puede especificar la codificación de mensajes MTOM en la configuración. Para migrar esta configuración, agregue el [ \<>mtomMessageEncoding](../../../../docs/framework/configure-apps/file-schema/wcf/mtommessageencoding.md) al enlace del servicio. En el ejemplo de código siguiente se muestra cómo se especifica la codificación MTOM en WSE 3.0 para un servicio que es equivalente en WCF.  
  
 **WSE 3.0**  
  
```xml  
<messaging>  
    <mtom clientMode="On"/>  
</messaging>  
```  
  
 **WCF**  
  
```xml  
<customBinding>  
  <binding name="MyBinding">  
    <mtomMessageEncoding/>  
  </binding>  
</customBinding>  
```  
  
## <a name="messaging"></a>Mensajería  
  
### <a name="wse-30-applications-that-use-the-wse-messaging-api"></a>Aplicaciones WSE 3.0 que utilizan la API de mensajería WSE  

 Cuando la API de mensajería WSE se utiliza para obtener acceso directo al XML que se comunica entre el cliente y el servicio web, la aplicación puede convertirse para utilizar XML simple convencional (POX). Para obtener más información acerca de POX, consulte [Interoperabilidad con aplicaciones POX](interoperability-with-pox-applications.md). Para obtener más información acerca de la API de mensajería de WSE, consulte Envío y recepción de mensajes SOAP mediante la [API de mensajería](https://docs.microsoft.com/previous-versions/dotnet/netframework-2.0/aa529293(v=msdn.10))de WSE .  
  
## <a name="transports"></a>Transportes  
  
### <a name="tcp"></a>TCP  
 De forma predeterminada, los clientes WSE 3.0 y los servicios web que envían mensajes SOAP mediante el transporte TCP no interoperan con los clientes WCF y los servicios web. Esta incompatibilidad se debe a diferencias en el marco utilizado en el protocolo TCP y por cuestiones de rendimiento. Sin embargo, un ejemplo de WCF detalla cómo implementar una sesión TCP personalizada que interopera con WSE 3.0. Para obtener más información sobre este ejemplo, consulte [Transporte: Interoperabilidad TCP de WSE 3.0](../../../../docs/framework/wcf/samples/transport-wse-3-0-tcp-interoperability.md).  
  
 Para especificar que una aplicación WCF usa el transporte TCP, use [ \<el>netTcpBinding ](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).  
  
### <a name="custom-transport"></a>Transporte personalizado  
 El equivalente de un transporte personalizado de WSE 3.0 en WCF es una extensión de canal. Para obtener más información sobre cómo crear una extensión de canal, consulte [Ampliación de la capa](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md)de canal .  
  
## <a name="see-also"></a>Consulte también

- [Ciclo de vida de programación básica](../../../../docs/framework/wcf/basic-programming-lifecycle.md)
- [Enlaces personalizados](../../../../docs/framework/wcf/extending/custom-bindings.md)
- [Cómo: Crear un enlace personalizado mediante SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [Cómo: Crear un SecurityBindingElement para un modo de autenticación especificado](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
