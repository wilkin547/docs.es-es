---
title: Migración de los servicios web WSE 3.0 a WCF
ms.date: 03/30/2017
ms.assetid: 7bc5fff7-a2b2-4dbc-86cc-ecf73653dcdc
ms.openlocfilehash: fea56d5737b47dabd5632477b7daed23fcfaf249
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="migrating-wse-30-web-services-to-wcf"></a>Migración de los servicios web WSE 3.0 a WCF
Entre las ventajas de migrar los servicios Web WSE 3.0 para Windows Communication Foundation (WCF) incluyen un mejor rendimiento y la compatibilidad con transportes adicionales, escenarios de seguridad adicional y WS-* especificaciones. Puede experimentar un servicio Web que se migra desde WSE 3.0 a WCF hasta una mejora del rendimiento del 200% al 400%. Para obtener más información acerca de los transportes admitidos por WCF, vea [elegir un transporte](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md). Para obtener una lista de los escenarios admitidos por WCF, vea [escenarios comunes de seguridad](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md). Para obtener una lista de las especificaciones que son compatibles con WCF, vea [Guía de interoperabilidad de protocolos de servicios Web](../../../../docs/framework/wcf/feature-details/web-services-protocols-interoperability-guide.md).  
  
 En las siguientes secciones se proporcionan instrucciones sobre cómo migrar una característica específica de un servicio Web de WSE 3.0 a WCF.  
  
## <a name="general"></a>General  
 Aplicaciones WSE 3.0 y WCF incluyen interoperabilidad de nivel de conexión y un conjunto común de terminología. Aplicaciones WSE 3.0 y WCF están nivel de conexión interoperable basado en el conjunto de WS-* las especificaciones que ambos admitan. Cuando se desarrolla una aplicación WSE 3.0 o WCF, hay un conjunto común de terminología, como los nombres de las aserciones de seguridad inmediata en WSE y los modos de autenticación.  
  
 Aunque hay muchos aspectos similares entre WCF y ASP.NET o modelos de programación de WSE 3.0, son diferentes. Para obtener más información sobre el modelo de programación de WCF, vea [ciclo de vida básico de programación](../../../../docs/framework/wcf/basic-programming-lifecycle.md).  
  
> [!NOTE]
>  Para migrar un servicio Web de WSE a WCF la [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) herramienta puede usarse para generar un cliente. No obstante, ese cliente contiene interfaces y clases que también pueden usarse como punto inicial para un servicio WCF. Las interfaces que se generan tienen el atributo <xref:System.ServiceModel.OperationContractAttribute> aplicado a los miembros del contrato con la propiedad <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> establecida en `*` Cuando un cliente WSE llama a un servicio Web con esta configuración, se produce la siguiente excepción: **Web.Services3.ResponseProcessingException: WSE910: se produjo un error durante el procesamiento de un mensaje de respuesta, y puede encontrar el error en el interior excepción**. Para mitigar esto, establezca la propiedad <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> del atributo <xref:System.ServiceModel.OperationContractAttribute> en un valor que no sea `null`, como `http://Microsoft.WCF.Documentation/ResponseToOCAMethod`.  
  
## <a name="security"></a>Seguridad  
  
### <a name="wse-30-web-services-that-are-secured-using-a-policy-file"></a>Los servicios web WSE 3.0 que se protegen mediante un archivo de directivas  
 Servicios WCF pueden utilizar un archivo de configuración para proteger un servicio y ese mecanismo es similar a un archivo de directivas de WSE 3.0. En WSE 3.0, al proteger un servicio web mediante un archivo de directivas, utiliza una aserción de seguridad inmediata o una aserción de directiva personalizada. Las aserciones de seguridad inmediata se asignan estrechamente al modo de autenticación de un elemento de enlace de seguridad WCF. No solo son los modos de autenticación de WCF y las aserciones de seguridad de llave en mano de WSE 3.0 con el mismo nombre o del mismo modo, protegen los mensajes utilizando los mismos tipos de credencial. Por ejemplo, el `usernameForCertificate` aserción de seguridad inmediata en WSE 3.0 se asigna a la `UsernameForCertificate` modo de autenticación en WCF. Los ejemplos de código siguientes muestran cómo una directiva mínima que utiliza el `usernameForCertificate` aserción de seguridad inmediata en WSE 3.0 se asigna a un `UsernameForCertificate` modo de autenticación de WCF en un enlace personalizado.  
  
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
  
 Para migrar la configuración de seguridad de un servicio Web de WSE 3.0 que se especifica en un archivo de directiva a WCF, un enlace personalizado debe crearse en un archivo de configuración y la aserción de seguridad inmediata debe establecerse en su modo de autenticación equivalente. Además, el enlace personalizado debe configurarse para que utilice la especificación WS-Addressing de agosto de 2004 cuando los clientes WSE 3.0 se comunican con el servicio. Cuando el servicio WCF migrado no requiere la comunicación con clientes WSE 3.0 y solo debe mantener la paridad de seguridad, considere la posibilidad de usar los enlaces de WCF definido por el sistema con la configuración de seguridad adecuada en lugar de crear un enlace personalizado.  
  
 En la siguiente tabla enumera la asignación entre un archivo de directivas de WSE 3.0 y el enlace personalizado equivalente en WCF.  
  
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
 Si se usa WSE 3.0 o WCF, los requisitos de seguridad se pueden especificar en código de aplicación en lugar de en la configuración. En WSE 3.0, esto se logra creando una clase que derive de la clase `Policy` y, a continuación, agregando los requisitos llamando al método `Add`. Para obtener más información acerca de cómo especificar los requisitos de seguridad en el código, vea [Cómo: proteger un servicio Web sin utilizar un archivo de directiva](http://go.microsoft.com/fwlink/?LinkId=73747). En WCF, para especificar los requisitos de seguridad en el código, cree una instancia de la <xref:System.ServiceModel.Channels.BindingElementCollection> clase y agregue una instancia de un <xref:System.ServiceModel.Channels.SecurityBindingElement> a la <xref:System.ServiceModel.Channels.BindingElementCollection>. Los requisitos de aserción de seguridad se establecen mediante los métodos de ayuda del modo de autenticación estático de la clase <xref:System.ServiceModel.Channels.SecurityBindingElement>. Para obtener más información acerca de cómo especificar requisitos de seguridad en el código mediante WCF, consulte [Cómo: crear un personalizado de enlace con SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md) y [Cómo: crear un SecurityBindingElement para un especificada Modo de autenticación](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md).  
  
### <a name="wse-30-custom-policy-assertion"></a>Aserción de directivas personalizadas WSE 3.0  
 En WSE 3.0 hay dos tipos de aserciones de directivas personalizadas: las que protegen un mensaje SOAP y las que no protegen un mensaje SOAP. Aserciones de directiva que protegen los mensajes SOAP se derivan de WSE 3.0 `SecurityPolicyAssertion` clase y el equivalente conceptual en WCF es el <xref:System.ServiceModel.Channels.SecurityBindingElement> clase.  
  
 Un punto importante a tener en cuenta es que las aserciones de seguridad inmediata de WSE 3.0 son un subconjunto de los modos de autenticación de WCF. Si ha creado una aserción de directiva personalizada en WSE 3.0, puede haber un modo de autenticación de WCF equivalente. Por ejemplo, WSE 3.0 no proporciona ninguna aserción de seguridad de CertificateOverTransport que sea el equivalente a la aserción de seguridad inmediata `UsernameOverTransport`, pero utiliza un certificado X.509 para la autenticación del cliente. Si ha definido su propia aserción de directiva personalizada para este escenario, WCF simplifica la migración. WCF define un modo de autenticación para este escenario, por lo que puede beneficiarse de la autenticación estática métodos auxiliares del modo para configurar un WCF<xref:System.ServiceModel.Channels.SecurityBindingElement>.  
  
 Cuando no hay un modo de autenticación de WCF que es equivalente a una aserción de directiva personalizada que proteja los mensajes SOAP, derive una clase de <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>, <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> o <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>WCF clases y especifique el elemento de enlace equivalente. Para obtener más información, consulte [Cómo: crear un personalizado de enlace con SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
 Para convertir una aserción de directiva personalizada que no se protegen un mensaje SOAP, consulte [Filtering](../../../../docs/framework/wcf/feature-details/filtering.md) y el ejemplo [Interceptor de mensajes personalizado](../../../../docs/framework/wcf/samples/custom-message-interceptor.md).  
  
### <a name="wse-30-custom-security-token"></a>Token de seguridad personalizado de WSE 3.0  
 El modelo de programación de WCF para crear un token personalizado es diferente de WSE 3.0. Para obtener más información acerca de cómo crear un token personalizado de WSE, consulte [crear Tokens de seguridad personalizados](http://go.microsoft.com/fwlink/?LinkID=73750). Para obtener más información acerca de cómo crear un token personalizado de WCF, vea [Cómo: crear un Token personalizado](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).  
  
### <a name="wse-30-custom-token-manager"></a>Administrador de tokens personalizados de WSE 3.0  
 El modelo de programación para crear un administrador de tokens personalizado es diferente en WCF que WSE 3.0. Para obtener más información sobre cómo crear un administrador de tokens personalizado y los demás componentes que son necesarios para un token de seguridad personalizado, vea [Cómo: crear un Token personalizado](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).  
  
> [!NOTE]
>  Si ha creado un personalizado `UsernameToken` Administrador de tokens de seguridad, WCF proporciona un mecanismo más sencillo para especificar la lógica de autenticación de la creación de administrador de tokens de seguridad personalizado. Para obtener más información, consulte [Cómo: utilizar un nombre de usuario personalizado y validador de contraseña](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md).  
  
### <a name="wse-30-web-services-that-use-mtom-encoded-soap-messages"></a>Servicio web de WSE 3.0 que usan mensajes SOAP codificados mediante MTOM  
 Al igual que una aplicación WSE 3, una aplicación de WCF puede especificar la codificación en la configuración de mensajes MTOM. Para migrar esta configuración, agregue el [ \<mtomMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/mtommessageencoding.md) para el enlace con el servicio. En el ejemplo de código siguiente se muestra cómo la codificación de MTOM se especifica en WSE 3.0 para un servicio que es equivalente en WCF.  
  
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
 De forma predeterminada, los clientes de WSE 3.0 y los servicios Web que envían mensajes SOAP mediante el transporte TCP no interoperan con clientes de WCF y los servicios Web. Esta incompatibilidad se debe a diferencias en el marco utilizado en el protocolo TCP y por cuestiones de rendimiento. Sin embargo, un ejemplo de WCF detalles sobre cómo implementar una sesión TCP personalizada que interopera con WSE 3.0. Para obtener más información acerca de este ejemplo, vea [transporte: interoperabilidad de WSE 3.0 TCP](../../../../docs/framework/wcf/samples/transport-wse-3-0-tcp-interoperability.md).  
  
 Para especificar que una aplicación de WCF usa el transporte TCP, use la [ \<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).  
  
### <a name="custom-transport"></a>Transporte personalizado  
 El equivalente de un transporte personalizado WSE 3.0 en WCF es una extensión de canal. Para obtener más información acerca de cómo crear una extensión de canal, vea [extender la capa del canal](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md).  
  
## <a name="see-also"></a>Vea también  
 [Ciclo de vida de programación básica](../../../../docs/framework/wcf/basic-programming-lifecycle.md)  
 [Enlaces personalizados](../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [Creación de un enlace personalizado mediante SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [Creación de un SecurityBindingElement para un modo de autenticación especificado](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
