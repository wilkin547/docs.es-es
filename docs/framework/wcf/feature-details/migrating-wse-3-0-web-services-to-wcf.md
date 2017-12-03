---
title: "Migración de los servicios web WSE 3.0 a WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7bc5fff7-a2b2-4dbc-86cc-ecf73653dcdc
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c97279b553a615feda1dd3a195ad033744d82983
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="migrating-wse-30-web-services-to-wcf"></a>Migración de los servicios web WSE 3.0 a WCF
Entre las ventajas de migrar los servicios web WSE 3.0 a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] se incluyen un mejor rendimiento y la compatibilidad con transportes adicionales, escenarios de seguridad adicionales y especificaciones WS - *. Un servicio web que se migra desde WSE 3.0 a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] puede experimentar una mejora de rendimiento de entre un 200% y un 400%. Para obtener más información acerca de los transportes admitidos por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], consulte [elegir un transporte](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md). Para obtener una lista de los escenarios compatibles con [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], consulte [escenarios comunes de seguridad](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md). Para obtener una lista de las especificaciones que son compatibles con [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], consulte [Guía de interoperabilidad de protocolos de servicios Web](../../../../docs/framework/wcf/feature-details/web-services-protocols-interoperability-guide.md).  
  
 Las siguientes secciones proporcionan una guía sobre cómo migrar una característica específica de un servicio web WSE 3.0 a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="general"></a>General  
 WSE 3.0 y las aplicaciones de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] incluyen interoperabilidad de nivel de conexión y un conjunto común de terminología. WSE 3.0 y las aplicaciones de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] son interoperables en cuanto a la conexión se refiere, en función del conjunto de especificaciones WS - * que ambos admitan. Cuando un WSE 3.0 o una aplicación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] es desarrollada, hay un conjunto común de terminología, como los nombres de las aserciones de seguridad inmediata en WSE y los  modos de autenticación.  
  
 Aunque hay muchos aspectos similares entre [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y ASP.NET o los modelos de programación de WSE 3.0, son diferentes. Para obtener más información sobre la [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] modelo de programación, vea [ciclo de vida básico de programación](../../../../docs/framework/wcf/basic-programming-lifecycle.md).  
  
> [!NOTE]
>  Para migrar un servicio Web de WSE a WCF la [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) herramienta puede usarse para generar un cliente. No obstante, ese cliente contiene interfaces y clases que también pueden usarse como punto inicial para un servicio WCF. Las interfaces que se generan tienen el atributo <xref:System.ServiceModel.OperationContractAttribute> aplicado a los miembros del contrato con la propiedad <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> establecida en `*` Cuando un cliente WSE llama a un servicio Web con esta configuración, se produce la siguiente excepción: **Web.Services3.ResponseProcessingException: WSE910: se produjo un error durante el procesamiento de un mensaje de respuesta, y puede encontrar el error en el interior excepción**. Para mitigar esto, establezca la propiedad <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> del atributo <xref:System.ServiceModel.OperationContractAttribute> en un valor que no sea `null`, como `http://Microsoft.WCF.Documentation/ResponseToOCAMethod`.  
  
## <a name="security"></a>Seguridad  
  
### <a name="wse-30-web-services-that-are-secured-using-a-policy-file"></a>Los servicios web WSE 3.0 que se protegen mediante un archivo de directivas  
 Los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] pueden utilizar un archivo de configuración para proteger un servicio y ese mecanismo es similar a un archivo de directivas de WSE 3.0. En WSE 3.0, al proteger un servicio web mediante un archivo de directivas, utiliza una aserción de seguridad inmediata o una aserción de directiva personalizada. Las aserciones de seguridad inmediata se asignan estrechamente al modo de autenticación de un elemento de enlace de seguridad de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. No solo son los modos de autenticación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y las aserciones de seguridad inmediata denominados igual o de forma similar, sino que protegen los mensajes utilizando los mismos tipos de credenciales. Por ejemplo, la aserción de seguridad inmediata `usernameForCertificate` en WSE 3.0 se asigna al modo de autenticación `UsernameForCertificate` en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Los siguientes ejemplos de código muestran cómo una directiva mínima que utiliza la aserción de seguridad inmediata `usernameForCertificate` en WSE 3.0 se asigna a un modo de autenticación `UsernameForCertificate` en un enlace personalizado de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
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
  
 Para migrar la configuración de seguridad de un servicio web WSE 3.0 que se especifica en un archivo de directiva para [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], un enlace personalizado debe crearse en un archivo de configuración y la aserción de seguridad inmediata debe establecerse en su modo de autenticación equivalente. Además, el enlace personalizado debe configurarse para que utilice la especificación WS-Addressing de agosto de 2004 cuando los clientes WSE 3.0 se comunican con el servicio. Cuando el servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] migrado no requiere la comunicación con clientes WSE 3.0 y solo debe mantener la paridad de seguridad, considere usar los enlaces definidos por el sistema de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con la configuración de seguridad adecuada en lugar de crear un enlace personalizado.  
  
 La siguiente tabla enumera la asignación entre un archivo de directivas WSE 3.0 y el enlace personalizado equivalente en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
|Aserción de seguridad inmediata de WSE 3.0|Configuración de enlace personalizado de WCF|  
|----------------------------------------|--------------------------------------|  
|\<usernameOverTransportSecurity / >|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="UserNameOverTransport" />     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<mutualCertificate10Security / >|`<customBinding>   <binding name="MyBinding">     <security messageSecurityVersion="WSSecurity10WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10" authenticationMode="MutualCertificate" />     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<usernameForCertificateSecurity / >|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="UsernameForCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<anonymousForCertificateSecurity / >|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="AnonymousForCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<kerberosSecurity / >|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="Kerberos"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<mutualCertificate11Security / >|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="MutualCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
  
 Para obtener más información acerca de cómo crear enlaces personalizados en WCF, vea [enlaces personalizados](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
### <a name="wse-30-web-services-that-are-secured-using-application-code"></a>Servicios web WSE 3.0 que se protegen mediante código de aplicaciones  
 Si se usa WSE 3.0 o [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], los requisitos de seguridad se pueden especificar mediante código de aplicación en lugar de mediante configuración. En WSE 3.0, esto se logra creando una clase que derive de la clase `Policy` y, a continuación, agregando los requisitos llamando al método `Add`. Para obtener más información acerca de cómo especificar los requisitos de seguridad en el código, vea [Cómo: proteger un servicio Web sin utilizar un archivo de directiva](http://go.microsoft.com/fwlink/?LinkId=73747). En [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], para especificar los requisitos de seguridad mediante código, cree una instancia de la clase <xref:System.ServiceModel.Channels.BindingElementCollection> y agregue una instancia de <xref:System.ServiceModel.Channels.SecurityBindingElement> a <xref:System.ServiceModel.Channels.BindingElementCollection>. Los requisitos de aserción de seguridad se establecen mediante los métodos de ayuda del modo de autenticación estático de la clase <xref:System.ServiceModel.Channels.SecurityBindingElement>. Para obtener más información acerca de cómo especificar requisitos de seguridad en el código mediante [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], consulte [Cómo: crear un personalizado de enlace con SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md) y [Cómo: crear un SecurityBindingElement para un Especifica el modo de autenticación](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md).  
  
### <a name="wse-30-custom-policy-assertion"></a>Aserción de directivas personalizadas WSE 3.0  
 En WSE 3.0 hay dos tipos de aserciones de directivas personalizadas: las que protegen un mensaje SOAP y las que no protegen un mensaje SOAP. Las aserciones de directivas que protegen los mensajes SOAP se derivan de la clase `SecurityPolicyAssertion` de WSE 3.0 y el equivalente conceptual en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] es la clase <xref:System.ServiceModel.Channels.SecurityBindingElement>.  
  
 Un punto importante a tener en cuenta es que las aserciones de seguridad inmediata de WSE 3.0 son un subconjunto de los modos de autenticación [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Si ha creado una aserción de directiva personalizada en WSE 3.0, puede que haya un modo de autenticación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] equivalente. Por ejemplo, WSE 3.0 no proporciona ninguna aserción de seguridad de CertificateOverTransport que sea el equivalente a la aserción de seguridad inmediata `UsernameOverTransport`, pero utiliza un certificado X.509 para la autenticación del cliente. Si tiene definido su propia aserción de directiva personalizada para este escenario, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] simplifica la migración. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] define un modo de autenticación para este escenario, por lo que puede aprovechar los métodos auxiliares del modo de autenticación estático para configurar un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] de <xref:System.ServiceModel.Channels.SecurityBindingElement>.  
  
 Cuando no hay ningún modo de autenticación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que sea equivalente a una aserción de directiva personalizada que proteja los mensajes SOAP, derive una clase desde las clases <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>, <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> o <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y especifique el elemento de enlace equivalente. Para obtener más información, consulte [Cómo: crear un personalizado de enlace con SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
 Para convertir una aserción de directiva personalizada que no se protegen un mensaje SOAP, consulte [Filtering](../../../../docs/framework/wcf/feature-details/filtering.md) y el ejemplo [Interceptor de mensajes personalizado](../../../../docs/framework/wcf/samples/custom-message-interceptor.md).  
  
### <a name="wse-30-custom-security-token"></a>Token de seguridad personalizado de WSE 3.0  
 El modelo de programación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para la creación de un token personalizado es diferente del de WSE 3.0. Para obtener más información acerca de cómo crear un token personalizado de WSE, consulte [crear Tokens de seguridad personalizados](http://go.microsoft.com/fwlink/?LinkID=73750). Para obtener más información acerca de cómo crear un token personalizado en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], consulte [Cómo: crear un Token personalizado](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).  
  
### <a name="wse-30-custom-token-manager"></a>Administrador de tokens personalizados de WSE 3.0  
 El modelo de programación para la creación de un administrador de tokens personalizado es distinto en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y en WSE 3.0. Para obtener más información sobre cómo crear un administrador de tokens personalizado y los demás componentes que son necesarios para un token de seguridad personalizado, vea [Cómo: crear un Token personalizado](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).  
  
> [!NOTE]
>  Si ha creado un administrador de tokens de seguridad `UsernameToken` personalizado, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona un mecanismo para especificar la lógica de autenticación más fácil que crear un administrador de tokens de seguridad personalizado. Para obtener más información, consulte [Cómo: utilizar un nombre de usuario personalizado y validador de contraseña](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md).  
  
### <a name="wse-30-web-services-that-use-mtom-encoded-soap-messages"></a>Servicio web de WSE 3.0 que usan mensajes SOAP codificados mediante MTOM  
 Al igual que una aplicación WSE 3, una aplicación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] puede especificar la codificación de mensajes MTOM mediante configuración. Para migrar esta configuración, agregue el [ \<mtomMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/mtommessageencoding.md) para el enlace con el servicio. El ejemplo de código siguiente muestra cómo la codificación de MTOM se especifica en WSE 3.0 para un servicio que es equivalente en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
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
 Cuando la API de mensajería WSE se utiliza para obtener acceso directo al XML que se comunica entre el cliente y el servicio web, la aplicación puede convertirse para utilizar XML simple convencional (POX). Para obtener más detalles sobre POX, consulte [interoperabilidad con aplicaciones POX](../../../../docs/framework/wcf/feature-details/interoperability-with-pox-applications.md). Para obtener más información acerca de la API de mensajería de WSE, consulte [envío y recepción de SOAP mensajes usando API de mensajería WSE](http://go.microsoft.com/fwlink/?LinkID=73755).  
  
## <a name="transports"></a>Transportes  
  
### <a name="tcp"></a>TCP  
 De forma predeterminada, los clientes y servicios web WSE 3.0 que envían mensajes SOAP mediante transporte TCP no interoperan con clientes y servicios web de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Esta incompatibilidad se debe a diferencias en el marco utilizado en el protocolo TCP y por cuestiones de rendimiento. No obstante, hay un ejemplo de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] donde se ve al detalle cómo implementar una sesión TCP personalizada que interopera con WSE 3.0. Para obtener más información acerca de este ejemplo, vea [transporte: interoperabilidad de WSE 3.0 TCP](../../../../docs/framework/wcf/samples/transport-wse-3-0-tcp-interoperability.md).  
  
 Para especificar que un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aplicación usa el transporte TCP, use la [ \<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).  
  
### <a name="custom-transport"></a>Transporte personalizado  
 El equivalente de un transporte personalizado WSE 3.0 en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] es una extensión de canal. Para obtener más información acerca de cómo crear una extensión de canal, vea [extender la capa del canal](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md).  
  
## <a name="see-also"></a>Vea también  
 [Ciclo de vida de programación básica](../../../../docs/framework/wcf/basic-programming-lifecycle.md)  
 [Enlaces personalizados](../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [Cómo: crear un enlace personalizado mediante SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [Cómo: crear un SecurityBindingElement para un modo de autenticación especificado](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
