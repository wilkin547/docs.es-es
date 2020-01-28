---
title: Protocolos de transacción
ms.date: 03/30/2017
ms.assetid: 2820b0ec-2f32-430c-b299-1f0e95e1f2dc
ms.openlocfilehash: 32c5da24eb7b23145d79c33a9ca1f5e5bcc22c06
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742731"
---
# <a name="transaction-protocols"></a>Protocolos de transacción
Windows Communication Foundation (WCF) implementa los protocolos WS-Atomic Transaction y WS-Coordination.  
  
|Especificación/documento|Version|Link|  
|-----------------------------|-------------|----------|  
|WS-Coordination|1.0<br /><br /> 1.1|<http://schemas.xmlsoap.org/ws/2004/10/wscoor/><br /><br /> <https://docs.oasis-open.org/ws-tx/wscoor/2006/06>|  
|Transacción WS-Atomic|1.0<br /><br /> 1.1|<http://schemas.xmlsoap.org/ws/2004/10/wsat/><br /><br /> <https://docs.oasis-open.org/ws-tx/wsat/2006/06>|  
  
 La interoperabilidad en estas especificaciones de protocolo se requiere en dos niveles: entre las aplicaciones y entre los administradores de transacciones (véase la siguiente figura). Las especificaciones describen en gran detalle los formatos de mensajes y el intercambio de mensajes para ambos niveles de interoperabilidad. Cierta seguridad, fiabilidad y codificaciones para el intercambio de aplicación a aplicación se aplican tal y como lo hacen para el intercambio normal de aplicaciones. Sin embargo, para una interoperabilidad correcta entre los administradores de transacciones es necesario el acuerdo en el enlace determinado, porque el usuario no lo configura por regla general.  
  
 Este tema describe una composición de la especificación de transacción WS-Atomic (WS-AT) con seguridad y describe el enlace seguro utilizado para la comunicación entre administradores de transacciones. El enfoque descrito en este documento se ha probado correctamente con otras implementaciones de WS-AT y WS-Coordination incluidos IBM, IONA, Sun Microsystems y otros.  
  
 En la ilustración siguiente se muestra la interoperabilidad entre dos administradores de transacciones, Transaction Manager 1 y Transaction Manager 2, y dos aplicaciones, Application 1 y Application 2:  
  
 ![Captura de pantalla que muestra la interacción entre los administradores de transacciones.](./media/transaction-protocols/transaction-managers-flow.gif)  
  
 Considere un escenario típico WS-Coordination/transacciones WS-Atomic con un Iniciador (I) y un Participante (P). Iniciador y Participante tienen administradores de transacciones (ITM y PTM, respectivamente). La confirmación en dos fases se conoce como 2PC en este tema.  
  
|||  
|-|-|  
|1. CreateCoordinationContext|12. respuesta del mensaje de aplicación|  
|2. CreateCoordinationContextResponse|13. confirmación (finalización)|  
|3. registro (finalización)|14. preparar (2PC)|  
|4. RegisterResponse|15. preparar (2PC)|  
|5. mensaje de la aplicación|16. preparado (2PC)|  
|6. CreateCoordinationContext con contexto|17. preparado (2PC)|  
|7. registro (duradero)|18. confirmado (finalización)|  
|8. RegisterResponse|19. Commit (2PC)|  
|9. CreateCoordinationContextResponse|20. Commit (2PC)|  
|10. registro (duradero)|21. confirmado (2PC)|  
|11. RegisterResponse|22. confirmado (2PC)|  
  
 Este documento describe una composición de la especificación de transacción WS-Atomic con seguridad y describe el enlace seguro utilizado para la comunicación entre administradores de transacciones. El enfoque descrito en este documento se ha probado correctamente con otras implementaciones de WS-AT y Coordinación del WS.  
  
 La figura y la tabla muestran cuatro clases de mensajes desde el punto de vista de la seguridad:  
  
- Mensajes de activación (CreateCoordinationContext y CreateCoordinationContextResponse).  
  
- Mensajes del registro (Register y RegisterResponse)  
  
- Mensajes de protocolos (Preparar, Reversión, Confirmar, Anulado, etc.).  
  
- Mensajes de aplicaciones  
  
 Las primeras tres clases de mensajes están consideradas mensajes de Administrador de transacciones y su configuración de enlaces se describe en el "Intercambio de mensajes de aplicaciones" más adelante en este tema. La cuarta clase del mensaje son mensajes de aplicación a aplicación y se describe en la sección “Ejemplos de mensajes” más adelante en este tema. En esta sección se describen los enlaces de protocolo usados por WCF para cada una de estas clases.  
  
 Los siguientes espacios de nombres XML y prefijos asociados se utilizan a lo largo de este documento.  
  
|Prefijo|Version|Espacio de nombres URI|  
|------------|-------------|-------------------|  
|s11||<https://schemas.xmlsoap.org/soap/envelope/>|  
|wsa|Anterior a 1,0<br /><br /> 1.0|`http://www.w3.org/2004/08/addressing`<br /><br /> <https://www.w3.org/2005/08/addressing/>|  
|wscoor|1.0<br /><br /> 1.1|<http://schemas.xmlsoap.org/ws/2004/10/wscoor/><br /><br /> <https://docs.oasis-open.org/ws-tx/wscoor/2006/06>|  
|wsat|1.0<br /><br /> 1.1|<http://schemas.xmlsoap.org/ws/2004/10/wsat/><br /><br /> <https://docs.oasis-open.org/ws-tx/wsat/2006/06>|  
|m|Pre-1.3<br /><br /> 1.3|<http://schemas.xmlsoap.org/ws/2005/02/trust/><br /><br /> <https://docs.oasis-open.org/ws-sx/ws-trust/200512>|  
|o||<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd>|  
|xsd||<https://www.w3.org/2001/XMLSchema>|  
  
## <a name="transaction-manager-bindings"></a>Enlaces del administrador de transacciones  
 R1001: los administradores de transacciones que participan en una transacción WS-AT 1,0 deben usar SOAP 1,1 y WS-Addressing 2004/08 para los intercambios de mensajes WS-Atomic Transaction y WS-Coordination.  
  
 R1002: los administradores de transacciones que participan en una transacción WS-AT 1.1 deben utilizar SOAP 1.1 y WS-Addressing 2005/08 para intercambios de mensajes de transacciones WS-Atomic y WS-Coordination.  
  
 Los mensajes de la aplicación no se restringen a estos enlaces y se describen más adelante.  
  
### <a name="transaction-manager-https-binding"></a>Enlace HTTPS de administrador de transacciones  
 El enlace HTTPS del administrador de transacciones confía solamente en la seguridad de transporte para lograr la seguridad y establecer confianza entre cada par de remitente-receptor en el árbol de transacciones.  
  
#### <a name="https-transport-configuration"></a>Configuración de transporte HTTPS  
 Los certificados X.509 se utilizan para establecer la identidad del administrador de transacciones. Se requiere la autenticación cliente/servidor, y la autorización cliente/servidor queda como un detalle de implementación:  
  
- R1111: los certificados X.509 presentados a través de la conexión deben tener un nombre de sujeto que coincida con el nombre de dominio completo (FQDN) del equipo de origen.  
  
- B1112: DNS debe ser funcional entre cada par remitente-receptor del sistema para que las comprobaciones de nombre de sujeto X.509 se realicen correctamente.  
  
#### <a name="activation-and-registration-binding-configuration"></a>Activación y configuración de enlace de registro  
 WCF requiere un enlace dúplex de solicitud/respuesta con correlación sobre HTTPS. (Para obtener más información sobre la correlación y descripciones de los patrones de intercambio de mensajes de solicitud/respuesta, vea Transacción WS-Atomic, sección 8.)  
  
#### <a name="2pc-protocol-binding-configuration"></a>Configuración de enlace de protocolo 2PC  
 WCF admite mensajes unidireccionales (datagrama) a través de HTTPS. La correlación entre los mensajes queda como un detalle de implementación.  
  
 B1131: las implementaciones deben admitir `wsa:ReferenceParameters` tal y como se describe en WS-Addressing para lograr la correlación de los mensajes 2PC de WCF.  
  
### <a name="transaction-manager-mixed-security-binding"></a>Enlace de seguridad mixta del administrador de transacciones  
 Éste es un enlace alternativo (modo mixto) que utiliza seguridad de transporte combinada con el modelo de token emitido de WS-Coordination para el establecimiento de la identidad. La activación y el registro son los únicos elementos que difieren entre los dos enlaces.  
  
#### <a name="https-transport-configuration"></a>Configuración de transporte HTTPS  
 Los certificados X.509 se utilizan para establecer la identidad del administrador de transacciones. Se requiere la autenticación cliente/servidor, y la autorización cliente/servidor queda como un detalle de implementación.  
  
#### <a name="activation-message-binding-configuration"></a>Configuración del enlace de mensajes de activación  
 Los mensajes de activación normalmente no participan en la interoperabilidad porque, por lo general, se producen entre una aplicación y su administrador de transacción local.  
  
 B1221: WCF usa el enlace HTTPS dúplex (descrito en [protocolos de mensajería](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)) para los mensajes de activación. Los mensajes de solicitud y respuesta se ponen en correlación utilizando WS-Addressing 2004/08 para WS-AT 1.0 y WS-Addressing 2005/08 para WS-AT 1.1.  
  
 La especificación de transacción WS-Atomic, sección 8, describe detalles adicionales sobre la correlación y los patrones de intercambio de mensajes.  
  
- R1222: tras recibir `CreateCoordinationContext`, el coordinador debe emitir un `SecurityContextToken` con `STx`secreto asociado. Este token se devuelve dentro de un encabezado `t:IssuedTokens` que sigue la especificación de WS-Trust.  
  
- R1223: si la activación se produce dentro de un contexto de coordinación existente, el encabezado `t:IssuedTokens` con el `SecurityContextToken` asociado al contexto existente debe fluir en el mensaje `CreateCoordinationContext`.  
  
 Se debe generar un nuevo encabezado de `t:IssuedTokens` para adjuntar al mensaje de `wscoor:CreateCoordinationContextResponse` saliente.  
  
#### <a name="registration-message-binding-configuration"></a>Configuración del enlace de mensajes de registro  
 B1231: WCF usa el enlace HTTPS dúplex (descrito en [protocolos de mensajería](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)). Los mensajes de solicitud y respuesta se ponen en correlación utilizando WS-Addressing 2004/08 para WS-AT 1.0 y WS-Addressing 2005/08 para WS-AT 1.1.  
  
 La transacción WS-Atomic, sección 8, describe detalles adicionales sobre la correlación y las descripciones del patrón de intercambio de mensajes.  
  
 R1232: los mensajes de `wscoor:Register` salientes deben usar el modo de autenticación `IssuedTokenOverTransport` descrito en [protocolos de seguridad](../../../../docs/framework/wcf/feature-details/security-protocols.md).  
  
 El elemento `wsse:Timestamp` se debe firmar utilizando el `SecurityContextToken STx` emitido. Esta firma es una prueba de posesión del token asociado a la transacción determinada y se utiliza para autenticar a un participante enumerado en la transacción. El mensaje RegistrationResponse se devuelve sobre HTTPS.  
  
#### <a name="2pc-protocol-binding-configuration"></a>Configuración de enlace de protocolo 2PC  
 WCF admite mensajes unidireccionales (datagrama) a través de HTTPS. La correlación entre los mensajes queda como un detalle de implementación.  
  
 B1241: las implementaciones deben admitir `wsa:ReferenceParameters` tal y como se describe en WS-Addressing para lograr la correlación de los mensajes 2PC de WCF.  
  
## <a name="application-message-exchange"></a>Intercambio de mensajes de aplicaciones  
 Las aplicaciones pueden utilizar cualquier enlace determinado para los mensajes de aplicación a aplicación, con tal de que el enlace cumpla los siguientes requisitos de seguridad:  
  
- R2001: los mensajes de aplicación a aplicación deben fluir el encabezado `t:IssuedTokens` junto con `CoordinationContext` en el encabezado del mensaje.  
  
- R2002: se debe proporcionar la integridad y confidencialidad de `t:IssuedToken`.  
  
 El encabezado `CoordinationContext` contiene `wscoor:Identifier`. Aunque la definición de `xsd:AnyURI` permite el uso de URI absolutos y relativos, WCF solo admite `wscoor:Identifiers`, que son URI absolutos.  
  
 B2003: Si el `wscoor:Identifier` de la `wscoor:CoordinationContext` es un URI relativo, los errores se devolverán desde los servicios de WCF transaccionales.  
  
## <a name="message-examples"></a>Ejemplos de mensajes  
  
### <a name="createcoordinationcontext-requestresponse-messages"></a>Mensajes de solicitud/respuesta CreateCoordinationContext  
 Los siguientes mensajes siguen un patrón de solicitud/respuesta.  
  
#### <a name="createcoordinationcontext-with-wscoor-10"></a>CreateCoordinationContext con WSCoor 1,0  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://.../ws/2004/10/wscoor/CreateCoordinationContext</Action>  
    <a:MessageID>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</MessageID>  
    <a:ReplyTo>  
      <Address>https://...</a:Address>  
    </a:ReplyTo>  
    <a:To>https://...</a:To>  
    <wsse:Security>  
      <u:Timestamp>  
        <wsu:Created>2005-12-15T23:36:09.921Z</u:Created>  
        <wsu:Expires>2005-12-15T23:41:09.921Z</u:Expires>  
      </u:Timestamp>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:CreateCoordinationContext>  
      <wscoor:CoordinationType>...</wscoor:CoordinationType>  
    </wscoor:CreateCoordinationContext>  
  </s:Body>  
</s11:Envelope>  
```  
  
#### <a name="createcoordinationcontext-with-wscoor-11"></a>CreateCoordinationContext con WSCoor 1.1  
  
```xml  
<s:Envelope>   
<s:Header>  
<a:Action>http://docs.oasis-open.org/ws-tx/wscoor/2006/06/CreateCoordinationContext</Action>  
<a:MessageID>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</MessageID>  
<a:ReplyTo>   
<Address>https://...</a:Address>   
</a:ReplyTo>   
<a:To>https://...</a:To>   
<wsse:Security>  
 <u:Timestamp>  
<wsu:Created>2005-12-15T23:36:09.921Z</u:Created>  
<wsu:Expires>2005-12-15T23:41:09.921Z</u:Expires>  
</u:Timestamp>   
</wsse:Security>   
</s:Header>   
<s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
<wscoor:CreateCoordinationContext>  
<wscoor:CoordinationType>...</wscoor:CoordinationType>  
</wscoor:CreateCoordinationContext>  
 </s:Body>  
</s11:Envelope>  
```  
  
#### <a name="createcoordinationcontextresponse-with-trust-pre-13-and-wscoor-10"></a>CreateCoordinationContextResponse con Trust Pre-1.3 y WSCoor 1.0  
  
```xml  
<s:Envelope>  
  <!-- Data below is shown in the clear for  
       illustration purposes only. -->  
  <s:Header>  
    <a:Action>./ws/2004/10/wscoor/CreateCoordinationContextResponse </a:Action>  
    <a:RelatesTo>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</a:RelatesTo>  
    <a:To s:mustUnderstand="1">https://... </a:To>  
    <t:IssuedTokens>  
 <wst:RequestSecurityTokenResponse     
    xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
    xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd"   
    xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust"  
    xmlns:wsc="http://schemas.xmlsoap.org/ws/2005/02/sc"  
    xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy">  
    <wst:TokenType>http://schemas.xmlsoap.org/ws/2005/02/sc/sct</wst:TokenType>  
    <wst:RequestedSecurityToken>  
      <wsc:SecurityContextToken>  
        <wssu:Identifier>  
          http://fabrikam123.com/SCTi  
        </wssu:Identifier>  
      </wsc:SecurityContextToken>   
    </wst:RequestedSecurityToken>  
    <wsp:AppliesTo>  
        http://fabrikam123.com/CCi  
    </wsp:AppliesTo>    
    <wst:RequestedAttachedReference>  
      <wsse:SecurityTokenReference >  
        <wsse:Reference   
           ValueType="http://schemas.xmlsoap.org/ws/2005/02/sc/sct"  
           URI="http://fabrikam123.com/SCTi"/>  
      </wsse:SecurityTokenReference>  
    </wst:RequestedAttachedReference>  
    <wst:RequestedUnattachedReference>  
      <wsse:SecurityTokenReference>  
        <wsse:Reference   
          ValueType="http://schemas.xmlsoap.org/ws/2005/02/sc/sct"  
          URI="http://fabrikam123.com/SCTi"/>  
      </wsse:SecurityTokenReference>  
    </wst:RequestedUnattachedReference>  
    <wst:RequestedProofToken>  
      <wst:BinarySecret   
        Type="http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey">  
        <!-- base64 encoded value -->  
      </wst:BinarySecret>  
    </wst:RequestedProofToken>  
    <wst:Lifetime>  
      <wssu:Created>2005-10-24T20:19:26.526Z</wssu:Created>  
      <wssu:Expires>2005-10-25T06:24:26.526Z</wssu:Expires>  
    </wst:Lifetime>  
    <wst:KeySize>256</wst:KeySize>  
</wst:RequestSecurityTokenResponse>  
    </t:IssuedTokens>  
    <o:Security xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
      <u:Timestamp u:Id="_0">  
        <u:Created>2005-12-15T23:36:12.015Z</u:Created>  
        <u:Expires>2005-12-15T23:41:12.015Z</u:Expires>  
      </u:Timestamp>  
    </o:Security>  
  </s:Header>  
  <s:Body>  
    <wscoor:CreateCoordinationContextResponse>  
      <wscoor:CoordinationContext>  
        <wscoor:Identifier>  
     http://fabrikam123.com/CCi  
      </wscoor:Identifier>  
        <wscoor:Expires>...</wscoor:Expires>  
        <wscoor:CoordinationType>...</wscoor:CoordinationType>  
        <wscoor:RegistrationService>  
          <a:Address>https://...</a:Address>  
          <a:ReferenceParameters>  
             ...  
          </a:ReferenceParameters>  
        </wscoor:RegistrationService>  
      </wscoor:CoordinationContext>  
    </wscoor:CreateCoordinationContextResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
#### <a name="createcoordinationcontextresponse-with-trust-13-and-wscoor-11"></a>CreateCoordinationContextResponse con Trust 1.3 y WSCoor 1.1  
  
```xml  
<s:Envelope>  
<!-- Data below is shown in the clear for illustration purposes only. -->   
<s:Header>   
<a:Action>http://docs.oasis-open.org/ws-tx/wscoor/2006/06/CreateCoordinationContextResponse </a:Action>  
<a:RelatesTo>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</a:RelatesTo>  
<a:To s:mustUnderstand="1">https://... </a:To>   
<t:IssuedTokens>   
<wst:RequestSecurityTokenResponse   
xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"   
xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd"   
xmlns:wst="http://docs.oasis-open.org/ws-sx/ws-trust/200512"  
xmlns:wsc="http://schemas.xmlsoap.org/ws/2005/02/sc"  
xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy">  
<wst:TokenType>http://schemas.xmlsoap.org/ws/2005/02/sc/sct</wst:TokenType>  
<wst:RequestedSecurityToken>   
<wsc:SecurityContextToken>   
<wssu:Identifier> http://fabrikam123.com/SCTi  
</wssu:Identifier>   
</wsc:SecurityContextToken>   
</wst:RequestedSecurityToken>   
<wsp:AppliesTo> http://fabrikam123.com/CCi </wsp:AppliesTo>  
<wst:RequestedAttachedReference>   
<wsse:SecurityTokenReference >   
<wsse:Reference  
  ValueType="http://schemas.xmlsoap.org/ws/2005/02/sc/sct"  
  URI="http://fabrikam123.com/SCTi"/>  
</wsse:SecurityTokenReference>   
</wst:RequestedAttachedReference>   
<wst:RequestedUnattachedReference>   
<wsse:SecurityTokenReference>   
<wsse:Reference  
 ValueType="http://schemas.xmlsoap.org/ws/2005/02/sc/sct"  
 URI="http://fabrikam123.com/SCTi"/>  
</wsse:SecurityTokenReference>   
</wst:RequestedUnattachedReference>   
<wst:RequestedProofToken>   
<wst:BinarySecret  
  Type="http://docs.oasis-open.org/ws-sx/ws-trust/200512/SymmetricKey">  
  <!-- base64 encoded value -->   
</wst:BinarySecret>   
</wst:RequestedProofToken>   
<wst:Lifetime>   
<wssu:Created>2005-10-24T20:19:26.526Z</wssu:Created>  
<wssu:Expires>2005-10-25T06:24:26.526Z</wssu:Expires>  
</wst:Lifetime>   
<wst:KeySize>256</wst:KeySize>   
</wst:RequestSecurityTokenResponse>   
</t:IssuedTokens>   
<o:Security xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">   
<u:Timestamp u:Id="_0">   
<u:Created>2005-12-15T23:36:12.015Z</u:Created>   
<u:Expires>2005-12-15T23:41:12.015Z</u:Expires>   
</u:Timestamp>   
</o:Security>   
</s:Header>   
<s:Body>   
<wscoor:CreateCoordinationContextResponse>   
<wscoor:CoordinationContext>   
<wscoor:Identifier> http://fabrikam123.com/CCi  
</wscoor:Identifier>   
<wscoor:Expires>...</wscoor:Expires>  
<wscoor:CoordinationType>...</wscoor:CoordinationType>  
<wscoor:RegistrationService>   
<a:Address>https://...</a:Address>  
<a:ReferenceParameters> ...  
</a:ReferenceParameters>  
</wscoor:RegistrationService>   
</wscoor:CoordinationContext>   
</wscoor:CreateCoordinationContextResponse>   
</s:Body>   
</s:Envelope>  
```  
  
### <a name="registration-messages"></a>Mensajes del registro  
 Los siguientes mensajes son mensajes del registro.  
  
#### <a name="register-with-wscoor-10"></a>Regístrese con WSCoor 1,0  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://schemas.xmlsoap.org/ws/2004/10/wscoor/Register</a:Action>  
    <a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e</a:MessageID>  
    <a:ReplyTo>  
      <a:Address>https://...</a:Address>        
    </a:ReplyTo>  
    <a:To>https://...</a:To>  
    <wsse:Security   
      s:mustUnderstand="1"   
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp wssu:Id="_0" >  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
      <wsc:SecurityContextToken>  
      <wssu:Identifier>  
          http://fabrikam123.com/SCTi  
      </wssu:Identifier>  
      </wsc:SecurityContextToken>  
      <!-- supporting signature over the timestamp -->  
      <wsse:Signature xmlns:ds="http://www.w3.org/2000/09/xmldsig#">  
        <ds:SignedInfo>  
          <ds:CanonicalizationMethod Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>  
          <ds:SignatureMethod Algorithm="http://www.w3.org/2000/09/xmldsig#hmac-sha1"/>  
          <ds:Reference URI="#_0">  
            <ds:Transforms>  
              <ds:Transform Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>  
            </ds:Transforms>  
            <ds:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1"/>  
            <ds:DigestValue>  
              alRzyhjLgoUOYoh8cx4n75eTcUk=  
            </ds:DigestValue>  
          </ds:Reference>  
        </ds:SignedInfo>  
        <ds:SignatureValue>YZYjnVvSOVasAQqQxaaviTSWtqI=</ds:SignatureValue>  
        <ds:KeyInfo>  
          <wsse:SecurityTokenReference  
            xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
            <wsse:Reference   
              URI="http://fabrikam123.com/SCTi"/>  
          </wsse:SecurityTokenReference>  
        </ds:KeyInfo>  
      </wsse:Signature>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:Register>  
      <wscoor:ProtocolIdentifier>...</wscoor:ProtocolIdentifier>  
      <wscoor:ParticipantProtocolService>  
        <a:Address>https://... </a:Address>  
      </wscoor:ParticipantProtocolService>  
    </wscoor:Register>  
  </s:Body>  
</s:Envelope>  
```  
  
#### <a name="register-with-wscoor-11"></a>Registro con WSCoor 1.1  
  
```xml  
<s:Envelope>  
<s:Header>   
<a:Action>http://docs.oasis-open.org/ws-tx/wscoor/2006/06/Register</a:Action>   
<a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e</a:MessageID>  
<a:ReplyTo>   
<a:Address>https://...</a:Address>   
</a:ReplyTo>  
<a:To>https://...</a:To>   
<wsse:Security   
s:mustUnderstand="1"   
xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"   
xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
<wssu:Timestamp wssu:Id="_0" >   
<wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
<wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
</wssu:Timestamp>   
<wsc:SecurityContextToken>   
<wssu:Identifier> http://fabrikam123.com/SCTi  
</wssu:Identifier>   
</wsc:SecurityContextToken>   
<!-- supporting signature over the timestamp -->  
<wsse:Signature xmlns:ds="http://www.w3.org/2000/09/xmldsig#">  
<ds:SignedInfo>   
<ds:CanonicalizationMethod Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>   
<ds:SignatureMethod Algorithm="http://www.w3.org/2000/09/xmldsig#hmac-sha1"/>   
<ds:Reference URI="#_0">   
<ds:Transforms>   
<ds:Transform Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>   
</ds:Transforms>   
<ds:DigestMethod  
Algorithm="http://www.w3.org/2000/09/xmldsig#sha1"/>   
<ds:DigestValue> alRzyhjLgoUOYoh8cx4n75eTcUk=  
</ds:DigestValue>   
</ds:Reference>   
</ds:SignedInfo>  
<ds:SignatureValue>YZYjnVvSOVasAQqQxaaviTSWtqI=  
</ds:SignatureValue>  
<ds:KeyInfo>   
<wsse:SecurityTokenReference xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
  <wsse:Reference URI="http://fabrikam123.com/SCTi"/>  
</wsse:SecurityTokenReference>   
</ds:KeyInfo>   
</wsse:Signature>   
</wsse:Security>   
</s:Header>   
<s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">   
<wscoor:Register>   
<wscoor:ProtocolIdentifier>...</wscoor:ProtocolIdentifier>  
<wscoor:ParticipantProtocolService>   
<a:Address>https://... </a:Address>  
</wscoor:ParticipantProtocolService>   
</wscoor:Register>   
</s:Body>   
</s:Envelope>  
```  
  
#### <a name="register-response-with-wscoor-10"></a>Registrar respuesta con WSCoor 1,0  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>  
      http://schemas.xmlsoap.org/ws/2004/10/wscoor/RegisterResponse  
    </a:Action>  
    <a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088d</a:MessageID>  
    <a:RelatesTo>  
      urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e        
    </a:RelatesTo>  
    <a:To>https://...</a:To>  
    <wsse:Security   
      s:mustUnderstand="1"   
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp>  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:RegisterResponse>  
      <wscoor:CoordinatorProtocolService>  
        <a:Address>https://...</a:Address>  
        <a:ReferenceParameters>  
          ...  
        </a:ReferenceParameters>  
      </wscoor:CoordinatorProtocolService>  
    </wscoor:RegisterResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
#### <a name="register-response-with-wscoor-11"></a>Respuesta del registro con WSCoor 1.1  
  
```xml  
<s:Envelope>  
<s:Header>   
<a:Action> http://docs.oasis-open.org/ws-tx/wscoor/2006/06/RegisterResponse  
</a:Action>   
<a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088d</a:MessageID>  
<a:RelatesTo> urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e </a:RelatesTo>  
<a:To>https://...</a:To>   
<wsse:Security   
s:mustUnderstand="1"   
xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"   
xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">   
<wssu:Timestamp>   
<wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
<wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
</wssu:Timestamp>   
</wsse:Security>   
</s:Header>   
<s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">   
<wscoor:RegisterResponse>   
<wscoor:CoordinatorProtocolService>  
<a:Address>https://...</a:Address>  
<a:ReferenceParameters> ... </a:ReferenceParameters>  
</wscoor:CoordinatorProtocolService>   
</wscoor:RegisterResponse>   
</s:Body>   
</s:Envelope>  
```  
  
### <a name="two-phase-commit-protocol-messages"></a>Mensajes de protocolo de confirmación de dos fase  
 El siguiente mensaje se relaciona con el protocolo de confirmación en dos fases (2PC).  
  
#### <a name="commit-with-wsat-10"></a>Confirmación con WSAT 1,0  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://.../ws/2004/10/wsat/Commit</a:Action>  
    <a:To>https://...</a:To>  
    <wsse:Security   
      s:mustUnderstand="1"   
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp wssu:Id="_0" >  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
   </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wsat:Commit />  
  </s:Body>  
</s:Envelope>  
```  
  
#### <a name="commit-with-wsat-11"></a>Confirmar con WSAT 1.1  
  
```xml  
<s:Envelope>  
<s:Header>   
<a:Action>http://docs.oasis-open.org/ws-tx/wsat/2006/06</a:Action>  
<a:To>https://...</a:To>   
<wsse:Security   
s:mustUnderstand="1"   
xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"   
xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">   
<wssu:Timestamp wssu:Id="_0" >   
<wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
<wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
</wssu:Timestamp>   
</wsse:Security>   
</s:Header>   
<s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">   
<wsat:Commit />   
</s:Body>   
</s:Envelope>  
```  
  
### <a name="application-messages"></a>Mensajes de aplicaciones  
 Los siguientes mensajes son mensajes de aplicaciones.  
  
#### <a name="application-message-request"></a>Solicitud de mensaje de aplicación  
  
```xml  
<s:Envelope>  
  <s:Header>  
<!-- Addressing headers, all signed-->  
    <wsse:Security s:mustUnderstand="1">  
      <wssu:Timestamp wssu:Id="timestamp">   
        <wssu:Created>2005-10-25T06:29:18.703Z</wssu:Created>  
        <wssu:Expires>2005-10-25T06:34:18.703Z</wssu:Expires>  
      </wssu:Timestamp>  
      <wsse:BinarySecurityToken   
          wssu:Id="IA_Certificate"   
          ValueType="...#X509v3"   
          EncodingType="...#Base64Binary">  
        <!-- IA certificate -->  
      </wsse:BinarySecurityToken>  
      <e:EncryptedKey Id="encrypted_key">  
            <!-- ephemeral key encrypted for PA certificate -->    
        <e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
          <e:DataReference URI="#encrypted_body"/>  
          <e:DataReference URI="#encrypted_CCi"/>  
          <e:DataReference URI="#encrypted_issuedtokens"/>  
        </e:ReferenceList>  
      </e:EncryptedKey>  
      <Signature xmlns="http://www.w3.org/2000/09/xmldsig#">  
        <!-- signature over Addressing headers, Timestamp, and Body -->  
      </Signature>  
    </wsse:Security>  
    <wsse11:EncryptedHeader >  
     <!-- encrypted wscoor:CoordinationContext header containing CCi -->  
    </wsse11:EncryptedHeader>  
    <wsse11:EncryptedHeader   
      <!-- encrypted wst:IssuedTokens header containing SCTi -->  
      <!-- wst:IssuedTokens header is taken verbatim from message #2 above, omitted for brevity -->  
    </wsse11:EncryptedHeader>  
  </s:Header>  
  <s:Body wssu:Id="body">  
    <!-- encrypted content of the Body element of the application message -->      
    <e:EncryptedData Id="encrypted_body"   
           Type="http://www.w3.org/2001/04/xmlenc#Content"   
           xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
...  
    </e:EncryptedData>  
  </s:Body>  
</s:Envelope>  
```
