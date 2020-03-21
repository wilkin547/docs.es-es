---
title: Protocolos de servicios Web compatibles con los enlaces de interoperabilidad proporcionados por el sistema
ms.date: 03/30/2017
helpviewer_keywords:
- WS-protocols
- Web services protocols
- Windows Communication Foundation, Web service protocols
ms.assetid: 1f7fc4ff-30fe-4e46-adda-91caad3b06c6
ms.openlocfilehash: a1e67401a09370a46bc7a3e8546c95467bc18b67
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184148"
---
# <a name="web-services-protocols-supported-by-system-provided-interoperability-bindings"></a>Protocolos de servicios Web compatibles con los enlaces de interoperabilidad proporcionados por el sistema
Windows Communication Foundation (WCF) está diseñado para interoperar con servicios web que admiten un conjunto de especificaciones conocidas como especificaciones de servicios web. Para simplificar la configuración del servicio para las prácticas recomendadas de <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>interoperabilidad, WCF presenta tres enlaces interoperables proporcionados por el sistema: , <xref:System.ServiceModel.WSHttpBinding?displayProperty=nameWithType>, y <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>. Para la interoperabilidad con los estándares de la Organización para el Avance de <xref:System.ServiceModel.WS2007HttpBinding?displayProperty=nameWithType>los Estándares de Información Estructurada (OASIS), WCF incluye un enlace interoperable proporcionado por el sistema: . Para la publicación de metadatos, WCF incluye dos enlaces proporcionados por el sistema interoperables: [ \<mexHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md) y [ \<mexHttpsBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md). En este tema se enumeran las especificaciones que admiten los enlaces interoperables proporcionados por el sistema.  
  
## <a name="web-services-protocols-supported-by-basichttpbinding-wshttpbinding-ws2007httpbinding-and-wsdualhttpbinding-bindings"></a>Protocolos de servicios Web admitidos por basicHttpBinding, wsHttpBinding, ws2007HttpBinding y enlaces wsDualHttpBinding  
  
### <a name="all-bindings"></a>Todos los enlaces  
 Los [ \< ](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)enlaces basicHttpBinding>, [ \<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)y [ \<ws2007HttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) admiten los siguientes protocolos.  
  
> [!NOTE]
> Para obtener información sobre los enlaces usados para publicar metadatos, consulte la sección "Enlaces de metadatos proporcionados por el sistema" más adelante en este tema.  
  
|Category|Protocolo|Especificación y uso|  
|--------------|--------------|-----------------------------|  
|Transporte|HTTP 1.1|[HTTP 1.1](https://www.ietf.org/rfc/rfc2616.txt)<br /><br /> `BasicHttpBinding`, `WSHttpBinding`y `WS2007HttpBinding` utilizan los transportes HTTP y HTTPS.|  
|Mensajería|MTOM|[MTOM](https://www.w3.org/TR/soap12-mtom/)<br /><br /> `basicHttpBinding`, `wsHttpBinding`y `ws2007HttpBinding` admiten el Mecanismo de optimización de transmisión de mensajes (MTOM). No utilizado de manera predeterminada: Para utilizar MTOM, defina el atributo `messageEncoding` como `"Mtom"`.<br /><br /> Ejemplo:<br /><br /> `<wsHttpBinding> <binding messageEncoding="Mtom"/> </wsHttpBinding>`|  
|Metadatos|WSDL 1.1|[WSDL 1.1](https://www.w3.org/TR/wsdl/)<br /><br /> WCF usa el lenguaje de descripción de servicios Web (WSDL) para describir los servicios.|  
|Metadatos|WS-Policy|[WS-Policy](https://www.w3.org/Submission/WS-Policy/)<br /><br /> WCF usa la especificación WS-Policy junto con aserciones específicas del dominio para describir los requisitos y capacidades del servicio.|  
|Metadatos|WS-Policy 1.5|[WS-Policy 1.5](https://www.w3.org/TR/2007/CR-ws-policy-20070605/)<br /><br /> WCF usa la especificación WS-Policy junto con aserciones específicas del dominio para describir los requisitos y capacidades del servicio.|  
|Metadatos|WS-PolicyAttachment|[WS-PolicyAttachment](http://specs.xmlsoap.org/ws/2004/09/policy/ws-policyattachment.pdf)<br /><br /> WCF implementa WS-PolicyAttachment para adjuntar expresiones de directiva en varios ámbitos en lenguaje de descripción de servicios Web (WSDL).|  
|Metadatos|WS-MetadataExchange|[WS-MetadataExchange](http://specs.xmlsoap.org/ws/2004/09/mex/WS-MetadataExchange.pdf)<br /><br /> WCF implementa WS-MetadataExchange para recuperar el esquema XML, WSDL y WS-Policy.|  
  
### <a name="basichttpbinding"></a>basicHttpBinding  
  
|Category|Protocolo|Especificación y uso|  
|--------------|--------------|-----------------------------|  
|Mensajería|SOAP 1,1|[SOAP 1,1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/)<br /><br /> De acuerdo con Basic Profile 1.1, el elemento `basicHttpBinding` implementa el protocolo de mensajes SOAP 1.1.|  
|Seguridad|WSS SOAP Message Security 1.0|[WSS SOAP Message Security 1.0](http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf)<br /><br /> De acuerdo con el perfil de seguridad básico, el elemento `basicHttpBinding` implementa la especificación de seguridad de mensaje SOAP 1.0 de Seguridad de Servicios web (WSS) para el nombre de usuario/contraseña y la seguridad basada en X.509.<br /><br /> `<basicHttpBinding> <binding name="Binding1"> <security mode="TransportWithMessageCredential &#124;                     "Message" .../> </binding> </basicHttpBinding>`|  
|Seguridad|Perfil UsernameToken 1.0 de seguridad de mensaje WSS SOAP|[Perfil UsernameToken 1.0 de seguridad de mensaje WSS SOAP](http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf)<br /><br /> `<basicHttpBinding> <binding name="Binding1"> <security mode="TransportWithMessageCredential"> <transport clientCredentialType="Basic"/> </security> </basicHttpBinding>`|  
|Seguridad|Perfil de token de certificado X.509 de seguridad de mensaje WSS SOAP 1.1|[Perfil de token de certificado X.509 de seguridad de mensaje WSS SOAP 1.1](http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0.pdf)<br /><br /> `<basicHttpBinding>   <security mode="Message"> <message clientCredentialType="Certificate"/> </security> </basicHttpBinding>`|  
  
### <a name="wshttpbinding-ws2007httpbinding-and-wsdualhttpbinding"></a>wsHttpBinding, ws2007HttpBinding y wsDualHttpBinding  
  
|Category|Protocolo|Especificación y uso|  
|--------------|--------------|-----------------------------|  
|Mensajería|SOAP 1.2|[Primer](https://www.w3.org/TR/soap12-part0/)<br /><br /> [Marco de mensajería](https://www.w3.org/TR/2007/REC-soap12-part1-20070427/)<br /><br /> [Adjuntos (incluido el enlace HTTP)](https://www.w3.org/TR/soap12-part2/)|  
|Mensajería|WS-Addressing 2005/08|[Direccionamiento de servicios Web 1.0 - Núcleo](https://www.w3.org/TR/ws-addr-core/)<br /><br /> [Web Services Addressing 1.0 - SOAP](https://www.w3.org/TR/ws-addr-soap/)<br /><br /> `wsHttpBinding`, `ws2007HttpBinding`y `wsDualHttpBinding` implementan la recomendación WS-Addressing del World Wide Web Consortium (W3C) para habilitar la mensajería asincrónica, la correlación de mensajes y mecanismos de direccionamiento independiente del transporte.<br /><br /> WCF no admite el cifrado de encabezados de WS-Addressing aunque lo permiten las especificaciones de WS-*.|  
|Mensajería|WS-Addressing 1.0 - Metadatos|[Metadatos WS-Addressing 1.0](https://www.w3.org/2007/05/addressing/metadata/) La compatibilidad con este protocolo se habilita estableciendo la versión de directiva en el comportamiento ServiceMetadata: con policyversion establecido en 1.2 (valor predeterminado), la descripción wsdl es compatible con WS-Addressing wsdl, con policyversion establecido en 1.5, la descripción wsdl es compatible con los metadatos ws-addressing.<br /><br /> WCF no admite el cifrado de encabezados de WS-Addressing aunque lo permiten las especificaciones de WS-*.|  
|Seguridad|WSS SOAP Message Security 1.0|[WSS SOAP Message Security 1.0](http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf)<br /><br /> Utilícese cuando el atributo `securityMode` está definido como "wsSecurityOverHttp" (valor predeterminado) y los parámetros se configuran utilizando un elemento secundario `wsSecurity`.<br /><br /> `<wsHttpBinding>   <binding name="myBinding">      <security mode="Message" .../>   </binding> </wsHttpBinding>`|  
|Seguridad|WSS SOAP Message Security UsernameToken Profile 1.1|[Perfil UsernameToken 1.0 de seguridad de mensaje WSS SOAP](https://www.oasis-open.org/committees/download.php/16782/wss-v1.1-spec-os-UsernameTokenProfile.pdf)<br /><br /> Utilice cuando el atributo `wsSecurity` del elemento `authenticationMode` esté definido como "Nombre de usuario."<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="UserName        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security> </binding> </wsHttpBinding>`|  
|Seguridad|WSS SOAP Message Security X.509 Certificate Token Profile 1.1|[WSS SOAP Message Security X.509 Certificate Token Profile 1.1](https://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf)<br /><br /> Utilice para la protección del mensaje cuando el atributo `wsSecurity` del elemento `authenticationMode` está definido como "Nombre de usuario", "Certificado" o "Ninguno." Además, utilice esto para la autenticación del cliente cuando el atributo del `wsSecurity` de elemento `authenticationMode` se defina como "Certificado".<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="Certificate"        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security>   </binding> </wsHttpBinding>`|  
|Seguridad|WSS SOAP Message Security Kerberos Token Profile 1.1|[WSS SOAP Message Security Kerberos Token Profile 1.1](https://www.oasis-open.org/committees/download.php/16788/wss-v1.1-spec-os-KerberosTokenProfile.pdf)<br /><br /> Utilice para la autenticación y protección de mensajes cuando el atributo `wsSecurity` del elemento `authenticationMode` esté definido en "Windows".<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="Windows"        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security>   </binding> </wsHttpBinding>`|  
|Seguridad|WS-SecureConversation|[WS-SecureConversation](http://specs.xmlsoap.org/ws/2005/02/sc/ws-secureconversation.pdf)<br /><br /> Utilice para proporcionar una sesión segura cuando el atributo `security/@mode` esté establecido en "Mensaje" y el atributo `message/@establishSecurityContext` está establecido en "true" (valor predeterminado).|  
|Seguridad|WS-Trust|[WS-Trust](http://specs.xmlsoap.org/ws/2005/02/trust/ws-trust.pdf)<br /><br /> Utilizado por WS-SecureConversation (vea arriba).|  
|Mensajería de confianza|WS-ReliableMessaging|[WS-ReliableMessaging](http://specs.xmlsoap.org/ws/2005/02/rm/ws-reliablemessaging.pdf)<br /><br /> Utilícese cuando se configura el enlace para que use `reliableSession`.<br /><br /> `<wsHttpBinding>  <binding name="myBinding">    <reliableSession/>   </binding> </wsHttpBinding>`|  
|Transacciones|Transacción WS-Atomic|[Transacción WS-Atomic](http://specs.xmlsoap.org/ws/2004/10/wsat/wsat.pdf)<br /><br /> Se usa para la comunicación entre administradores de transacciones. Los clientes y servicios WCF siempre usan administradores de transacciones locales.|  
|Transacciones|WS-Coordination|[WS-Coordination](https://docs.microsoft.com/previous-versions/ms951231(v=msdn.10))<br /><br /> Utilícese para hacer fluir el contexto de transacción cuando el atributo `flowTransactions` se establece en "Allowed" (Permitido) o "Required" (Obligatorio).<br /><br /> `<wsHttpBinding>   <binding transactionFlow="true"/> </wsHttpBinding>`|  
  
## <a name="wsfederationhttpbinding-and-ws2007federationhttpbinding"></a>wsFederationHttpBinding y ws2007FederationHttpBinding  
 Los [ \<elementos wsFederationHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) y [ \<ws2007FederationHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) se introducen para proporcionar compatibilidad con escenarios federados, donde un tercero emite un token utilizado para autenticar un cliente. Además de los protocolos utilizados por `wsHttpBinding`, `wsFederationHttpBinding` utiliza:  
  
- `WS-Trust` para la emisión de tokens.  
  
- El Perfil 1.0 y 1.1 de tokens de lenguaje de marcado de aserciones de seguridad (SAML) WSS para el formato de tokens emitidos más comúnmente.  
  
 Ejemplo:  
  
```xml  
<wsFederationHttpBinding>  
  <binding name="myBinding">  
     <security mode="Message">  
       <message issuedKeyType="Symmetric"
                issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1">  
         <issuerMetadata address =
         'http://localhost/FederationSample/HomeRealmSTS/STS.svc/mex'>  
       </message>  
     </security>  
  </binding>  
</wsFederationHttpBinding>  
```  
  
 Para obtener más información, consulte [Federación](../../../../docs/framework/wcf/feature-details/federation.md) .  
  
## <a name="system-provided-metadata-bindings"></a>Enlaces de metadatos proporcionados por el sistema  
 Las tablas siguientes describen los protocolos admitidos por los enlaces de metadatos interoperables proporcionados por el sistema expuestos por la clase <xref:System.ServiceModel.Description.MetadataExchangeBindings?displayProperty=nameWithType>.  
  
### <a name="mexhttpbinding"></a>mexHttpBinding  
 El enlace [ \<de>mexHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md) admite los siguientes protocolos. Para obtener más información sobre el uso de este enlace, vea [Publicar metadatos](../../../../docs/framework/wcf/feature-details/publishing-metadata.md).  
  
|Category|Protocolo|Especificación y uso|  
|--------------|--------------|-----------------------------|  
|Transporte|HTTP 1.1|[HTTP 1.1](https://www.ietf.org/rfc/rfc2616.txt)|  
|Mensajería|SOAP 1.2|[Primer](https://www.w3.org/TR/soap12-part0/)<br /><br /> [Marco de mensajería](https://www.w3.org/TR/2007/REC-soap12-part1-20070427/)<br /><br /> [Adjuntos (incluido el enlace HTTP)](https://www.w3.org/TR/soap12-part2/)|  
|Mensajería|WS-Addressing 2005/08|[Direccionamiento de servicios Web 1.0 - Núcleo](https://www.w3.org/TR/ws-addr-core/)<br /><br /> [Web Services Addressing 1.0 - SOAP](https://www.w3.org/TR/ws-addr-soap/)|  
|Metadatos|WS-MetadataExchange|[WS-MetadataExchange](http://specs.xmlsoap.org/ws/2004/09/mex/WS-MetadataExchange.pdf)<br /><br /> WCF implementa WS-MetadataExchange para recuperar el esquema XML, WSDL y WS-Policy.|  
  
### <a name="mexhttpsbinding"></a>mexHttpsBinding  
 mexHttpsBinding>admite los siguientes protocolos. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md) Para obtener más información sobre el uso de este enlace, vea [Publicar metadatos](../../../../docs/framework/wcf/feature-details/publishing-metadata.md).  
  
|Category|Protocolo|Especificación y uso|  
|--------------|--------------|-----------------------------|  
|Transporte|HTTP 1.1|[HTTP 1.1](https://www.ietf.org/rfc/rfc2616.txt)<br /><br /> La seguridad de transporte está habilitada.|  
|Mensajería|SOAP 1.2|[Primer](https://www.w3.org/TR/soap12-part0/)<br /><br /> [Marco de mensajería](https://www.w3.org/TR/2007/REC-soap12-part1-20070427/)<br /><br /> [Adjuntos (incluido el enlace HTTP)](https://www.w3.org/TR/soap12-part2/)|  
|Mensajería|WS-Addressing 2005/08|[Direccionamiento de servicios Web 1.0 - Núcleo](https://www.w3.org/TR/ws-addr-core/)<br /><br /> [Web Services Addressing 1.0 - SOAP](https://www.w3.org/TR/ws-addr-soap/)|  
|Metadatos|WS-MetadataExchange|[WS-MetadataExchange](http://specs.xmlsoap.org/ws/2004/09/mex/WS-MetadataExchange.pdf)<br /><br /> WCF implementa WS-MetadataExchange para recuperar el esquema XML, WSDL y WS-Policy.|  
  
## <a name="see-also"></a>Consulte también

- [Enlaces proporcionados por el sistema](../../../../docs/framework/wcf/system-provided-bindings.md)
- [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)
- [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)
- [\<wsDualHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)
- [\<mexHttps>Binding](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md)
- [\<>mexHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md)
