---
title: "Protocolo de mensajería de confianza versión 1.0"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a5509a5c-de24-4bc2-9a48-19138055dcce
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5657b48a648603f24e89c0eebd1285ed9a505e54
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="reliable-messaging-protocol-version-10"></a>Protocolo de mensajería de confianza versión 1.0
Este tema cubre los detalles de implementación de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] para el protocolo de febrero de 2005 WS-ReliableMessaging (versión 1.0) necesario para la interoperación mediante el transporte HTTP. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sigue la especificación WS-ReliableMessaging con las restricciones y clarificaciones explicadas en este tema. Tenga en cuenta que la versión 1.0 del protocolo WS-ReliableMessaging se implementa a partir de [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)].  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementa el protocolo WS-Reliable Messaging de febrero de 2005 en <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.  
  
 Para su comodidad, el tema utiliza las siguientes funciones:  
  
-   Iniciador: el cliente que inicia la creación de la secuencia de mensajes WS-Reliable  
  
-   Respondedor: el servicio que recibe las solicitudes del iniciador  
  
 En este documento, se utilizan los prefijos y espacios de nombres de la tabla siguiente.  
  
|Prefijo|Espacio de nombres|  
|------------|---------------|  
|wsrm|http://schemas.xmlsoap.org/ws/2005/02/rm|  
|netrm|http://schemas.microsoft.com/ws/2006/05/rm|  
|s|http://www.w3.org/2003/05/soap-envelope|  
|wsa|http://schemas.xmlsoap.org/ws/2005/08/addressing|  
|wsse|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd|  
  
## <a name="messaging"></a>Mensajería  
  
### <a name="sequence-establishment-messages"></a>Mensajes de establecimiento de secuencia  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementa mensajes `CreateSequence` y `CreateSequenceResponse` para establecer una secuencia de mensajes de confianza. Las siguientes restricciones son aplicables:  
  
-   B1101: el iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no genera el elemento Expires opcional en el mensaje `CreateSequence` o, en los casos en los que el mensaje `CreateSequence` contiene un elemento `Offer`, el elemento opcional `Expires` en el elemento `Offer`.  
  
-   B1102: al tener acceso al mensaje `CreateSequence`, el [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] de `Responder` envía y recibe ambos elementos `Expires` si existen, pero no usa sus valores.  
  
 WS-Reliable Messaging incluye el mecanismo `Offer` para establecer las dos secuencias correlacionadas inversas que forman una sesión.  
  
-   R1103: si `CreateSequence` contiene un elemento `Offer`, el respondedor de la mensajería de confianza debe aceptar la secuencia y responder con `CreateSequenceResponse`, que contiene un elemento `wsrm:Accept`, formando dos secuencias correlacionadas inversas, o rechazar la solicitud `CreateSequence`.  
  
-   R1104: `SequenceAcknowledgement` y los mensajes de la aplicación que fluyen en una secuencia inversa se deben enviar a la referencia de extremo `ReplyTo` de `CreateSequence`.  
  
-   R1105: las referencias de extremo `AcksTo` y `ReplyTo` en `CreateSequence` deben tener valores de dirección que coincidan byte a byte.  
  
     El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] comprueba que la parte del URI de las EPR `AcksTo` y `ReplyTo` sean idénticas antes de crear una secuencia.  
  
-   R1106: las referencias de extremo `AcksTo` y `ReplyTo` del mensaje `CreateSequence` deberían tener el mismo conjunto de parámetros de referencia.  
  
     [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no exige, pero supone que los parámetros de referencia de extremo `AcksTo` y `ReplyTo` en `CreateSequence` son idénticas y utiliza los parámetros de referencia de la referencia de extremo `ReplyTo` para las confirmaciones y los mensajes de secuencia inversa.  
  
-   R1107: cuando dos secuencias inversas se establecen por medio del mecanismo `Offer`, los mensajes de aplicación y `SequenceAcknowledgement` que fluyen en secuencias inversas se deben enviar a la referencia de extremo `ReplyTo` de `CreateSequence`.  
  
-   R1108: cuando dos secuencias inversas se establecen mediante el mecanismo Offer, la propiedad `[address]` del elemento secundario de referencia de extremo `wsrm:AcksTo` del elemento `wsrm:Accept` de `CreateSequenceResponse` debe coincidir byte a byte con el URI de destino de `CreateSequence`.  
  
-   R1109: cuando se establecen dos secuencias inversas por medio del mecanismo `Offer`, los mensajes enviados por el iniciador y las confirmaciones de los mensajes por parte del respondedor se deben enviar a la misma referencia de extremo.  
  
     [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza WS-Reliable Messaging para establecer sesiones confiables entre el iniciador y el respondedor. La implementación de WS-Reliable Messaging de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona una sesión confiable para patrones de mensajería dúplex completa y de solicitud-respuesta unidireccional. WS-Reliable Messaging `Offer` mecanismo en `CreateSequence` / `CreateSequenceResponse` le permite establecer dos secuencias inversas correlacionadas y proporciona un protocolo de sesión que es apto para todos los puntos de conexión de mensajes. Dado que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona una garantía de seguridad para este tipo de sesiones, incluyendo la protección de un extremo a otro para la integridad de la sesión, es práctico asegurar que los mensajes dirigidos a la misma parte lleguen al mismo destino. Esto también permite el “apoyo a caballo” de confirmaciones de secuencias en mensajes de aplicaciones. Por consiguiente, las restricciones R1104, R1105, y R1108 se aplican a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 Ejemplo de mensaje `CreateSequence`.  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action s:mustUnderstand="1">  
      http://schemas.xmlsoap.org/ws/2005/02/rm/CreateSequence  
    </a:Action>  
    <a:ReplyTo>  
      <a:Address>          
         http://Business456.com/clientA        
      </a:Address>  
    </a:ReplyTo>  
    <a:MessageID>  
      urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
    </a:MessageID>  
    <a:To s:mustUnderstand="1">  
      http://Business456.com/clientA  
    </a:To>  
  </s:Header>  
  <s:Body>  
    <wsrm:CreateSequence>  
      <wsrm:AcksTo>  
       <wsa:Address>  
         http://Business456.com/clientA  
       </wsa:Address>  
     </wsrm:AcksTo>  
     <wsrm:Offer>  
      <wsrm:Identifier>  
        urn:uuid:0afb8d36-bf26-4776-b8cf-8c91fddb5496  
      </wsrm:Identifier>  
     </wsrm:Offer>  
   </wsrm:CreateSequence>  
  </s:Body>  
</s:Envelope>  
```  
  
 Ejemplo de mensaje `CreateSequenceResponse`.  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action s:mustUnderstand="1">  
      http://schemas.xmlsoap.org/ws/2005/02/rm/CreateSequenceResponse  
    </a:Action>  
    <a:RelatesTo>  
      urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
    </a:RelatesTo>  
    <a:To s:mustUnderstand="1">  
      http://Business456.com/clientA  
    </a:To>  
  </s:Header>  
  <s:Body>  
   <wsrm:CreateSequenceResponse>  
    <Identifier>  
     urn:uuid:eea0a36c-b38a-43e8-8c76-2fabe2d76386  
    </Identifier>  
    <Accept>  
    <AcksTo>  
      <a:Address>  
        http://BusinessABC.com/serviceA  
      </a:Address>  
    </AcksTo>  
    </Accept>  
   </wsrm:CreateSequenceResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="sequence"></a>Secuencia  
 A continuación, se muestra una lista de restricciones que se aplican a las secuencias:  
  
-   B1201:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera y obtiene acceso a los números de secuencia no superiores a `xs:long`del valor inclusivo máximo, 9223372036854775807.  
  
-   B1202:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] siempre genera un mensaje último cuerpo vacío con el URI de acción de http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage.  
  
-   B1203: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] recibe y entrega un mensaje con un encabezado de secuencia que contiene un elemento `LastMessage`, siempre que el URI de acción no sea http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage.  
  
 Ejemplo de encabezado de secuencia.  
  
```xml  
<wsrm:Sequence>  
  <wsrm:Identifier>  
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
  </wsrm:Identifier>  
  <wsrm:MessageNumber>  
    10  
  </wsrm:MessageNumber>  
  <wsrm:LastMessage/>  
 </wsrm:Sequence>  
```  
  
### <a name="ackrequested-header"></a>Encabezado AckRequested  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usa el encabezado `AckRequested` como mecanismo de supervivencia. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no genera el elemento `MessageNumber` opcional. Al recibir un mensaje con un encabezado `AckRequested` que contiene el elemento `MessageNumber`, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] pasa por alto el valor del elemento `MessageNumber`, tal y como se muestra en el siguiente ejemplo.  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>  
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
  </wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement-header"></a>Encabezado SequenceAcknowledgement  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usa un mecanismo de superposición para las confirmaciones de secuencias proporcionadas en WS-Reliable Messaging.  
  
-   R1401: cuando dos secuencias inversas se establecen utilizando el mecanismo `Offer`, el encabezado `SequenceAcknowledgement` puede estar incluido en cualquier mensaje de aplicación transmitido al destinatario previsto.  
  
-   B1402: cuando [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] debe generar una confirmación antes de recibir ningún mensaje de secuencia (por ejemplo, para satisfacer un mensaje `AckRequested`), [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera un encabezado `SequenceAcknowledgement` que contiene el intervalo 0-0, tal y como se muestra en el siguiente ejemplo.  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>  
        urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
      </wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="0" Lower="0"/>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   B1403: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no genera encabezados `SequenceAcknowledgement` que contengan un elemento `Nack`, pero admite elementos `Nack`.  
  
### <a name="ws-reliablemessaging-faults"></a>Errores de WS-ReliableMessaging  
 A continuación, se muestra una lista de las restricciones que se aplican a la implementación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] de errores de WS-Reliable Messaging:  
  
-   B1501: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no genera errores `MessageNumberRollover`.  
  
-   B1502:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] punto de conexión puede generar `CreateSequenceRefused` produce un error como se describe en la especificación.  
  
-   B1503:when el extremo de servicio alcanza su límite de conexión y no se puede procesar nuevas conexiones, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera más `CreateSequenceRefused` subcódigo, de error `netrm:ConnectionLimitReached`, tal y como se muestra en el ejemplo siguiente.  
  
    ```xml  
    <s:Envelope>  
      <s:Header>  
        <wsa:Action>  
          http://schemas.xmlsoap.org/ws/2005/08/addressing/fault  
        </wsa:Action>  
      </s:Header>  
      <s:Body>  
        <s:Fault>  
          <s:Code>  
            <s:Value>  
              s:Receiver  
            </s:Value>  
            <s:Subcode>  
              <s:Value>  
                wsrm:CreateSequenceRefused  
              </s:Value>  
              <s:Subcode>  
                <s:Value>  
                  netrm:ConnectionLimitReached  
                </s:Value>  
              </s:Subcode>  
            </s:Subcode>  
          </s:Code>  
          <s:Reason>  
            <s:Text xml:lang="en">  
              [Reason]  
            </s:Text>  
          </s:Reason>  
        </s:Fault>  
      </s:Body>  
    </s:Envelope>  
    ```  
  
### <a name="ws-addressing-faults"></a>Errores WS-Addressing  
 Dado que WS-Reliable Messaging utiliza WS-Addressing, la implementación de WS-Reliable Messaging de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] puede generar errores de WS-Addressing. Esta sección cubre los errores de WS-Addressing que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera explícitamente en la capa de WS-Reliable Messaging:  
  
-   B1601:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera el error necesario de encabezado de direccionamiento de mensajes cuando se cumple alguna de las siguientes acciones:  
  
    -   Falta un encabezado `Sequence` y un encabezado `Action` en un mensaje.  
  
    -   Falta un encabezado `CreateSequence` en un mensaje `MessageId`.  
  
    -   Falta un encabezado `CreateSequence` en un mensaje `ReplyTo`.  
  
-   B1602:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera el error no admite la acción como respuesta a un mensaje que falta un `Sequence` encabezado y tiene un `Action` encabezado no reconocido en la especificación WS-Reliable Messaging.  
  
-   B1603:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera el error de punto de conexión disponible para indicar que el punto de conexión no procesa la secuencia basándose en el examen de la `CreateSequence` encabezados de direccionamiento del mensaje.  
  
## <a name="protocol-composition"></a>Composición de protocolos  
  
### <a name="composition-with-ws-addressing"></a>Composición con WS-Addressing  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite dos versiones de WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] y las recomendaciones de WS-Addressing 1.0 de W3C [WS-ADDR-CORE] y [WS-ADDR-SOAP].  
  
 Aunque la especificación de WS-Reliable Messaging solo menciona a WS-Addressing 2004/08, no limita la versión de WS-Addressing que se ha de utilizar. A continuación, se muestra una lista de restricciones que se aplican a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:  
  
-   R2101: ambos WS-Addressing 2004/08 y WS-Addressing 1.0 pueden utilizarse con WS-Reliable Messaging.  
  
-   Debe utilizarse R2102:A única versión de WS-Addressing a lo largo de una secuencia de WS-ReliableMessaging determinada o un par de secuencias inversas correlacionadas mediante el `wsrm:Offer` mecanismo.  
  
### <a name="composition-with-soap"></a>Composición con SOAP  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite el uso de SOAP 1.1 y SOAP 1.2 con WS-Reliable Messaging.  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a>Composición con WS-Security y WS-SecureConversation  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona protección para secuencias de WS-Reliable Messaging mediante el transporte seguro (HTTPS), la composición con WS-Security y la composición con WS-Secure Conversation. A continuación, se muestra una lista de restricciones que se aplican a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:  
  
-   R2301: para proteger la integridad de una secuencia de WS-ReliableMessaging además de la integridad y confidencialidad de los mensajes individuales, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requiere que se deben utilizar WS-Secure Conversation.  
  
-   R2302:AWS-Secure Conversation debe establecerse antes de establecer secuencias de WS-Reliable Messaging.  
  
-   R2303: si la duración de la secuencia de WS-Reliable Messaging supera la duración de la sesión de WS-Secure Conversation, el `SecurityContextToken` establecido mediante WS-Secure Conversation se debe renovar utilizando el enlace de renovación de WS-Secure Conversation correspondiente.  
  
-   B2304:ws-secuencia de mensajería de confianza o un par de secuencias inversas correlacionadas siempre están enlazados a una sola sesión de WS-SecureConversation.  
  
     El origen de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera el elemento `wsse:SecurityTokenReference` en la sección de extensibilidad de elementos del mensaje `CreateSequence`.  
  
-   R2305:when compuesta con WS-Secure Conversation, un `CreateSequence` mensaje debe contener el `wsse:SecurityTokenReference` elemento.  
  
## <a name="ws-reliable-messaging-ws-policy-assertion"></a>Aserción de WS-Policy de WS-Reliable Messaging   
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza la aserción de WS-Policy de WS-Reliable Messaging `wsrm:RMAssertion` para describir funciones de extremos. A continuación, se muestra una lista de restricciones que se aplican a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:  
  
-   B3001: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] adjunta la aserción `wsrm:RMAssertion` de WS-Policy Assertion a elementos `wsdl:binding`. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite datos adjuntos para los elementos `wsdl:binding` y `wsdl:port`.  
  
-   B3002: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite las siguientes propiedades opcionales de aserción de WS-Reliable Messaging y proporciona control sobre ellas en el [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] de `ReliableMessagingBindingElement`:  
  
    -   `wsrm:InactivityTimeout`  
  
    -   `wsrm:AcknowledgementInterval`  
  
     A continuación se muestra un ejemplo.  
  
    ```xml  
    <wsrm:RMAssertion>  
      <wsrm:InactivityTimeout Milliseconds="600000" />  
      <wsrm:AcknowledgementInterval Milliseconds="200" />  
    </wsrm:RMAssertion>  
    ```  
  
## <a name="flow-control-ws-reliable-messaging-extension"></a>Extensión de WS-Reliable Messaging de control de flujo  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usa la extensibilidad de WS-Reliable Messaging para proporcionar un control opcional adicional más estricto sobre el flujo de mensajes de secuencias.  
  
 Control de flujo se habilita estableciendo el `ReliableSessionBindingElement`del `FlowControlEnabled``bool` propiedad `true`. A continuación, se muestra una lista de restricciones que se aplican a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:  
  
-   B4001: cuando se habilitada el control de flujo de la mensajería de confianza, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera un elemento `netrm:BufferRemaining` en la extensibilidad de elementos del encabezado `SequenceAcknowledgement`.  
  
-   B4002: cuando está habilitado el control de flujo de la mensajería de confianza, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no requiere que haya un elemento `netrm:BufferRemaining` en el encabezado `SequenceAcknowledgement`, tal y como se muestra en el ejemplo siguiente.  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>  
        http://fabrikam123.com/abc  
      </wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="1" Lower="1"/>             
      <netrm:BufferRemaining>  
        8  
      </netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   B4003: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza `netrm:BufferRemaining` para indicar cuántos mensajes nuevos puede almacenar en búfer el destino de la mensajería de confianza.  
  
-   B4004: el [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] el servicio de mensajería confiable limita el número de mensajes transmitidos cuando la aplicación de destino de la mensajería de confianza no puede recibir mensajes rápidamente. El destino de la mensajería de confianza almacena en búfer los mensajes y el valor del elemento cae a 0.  
  
-   B4005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera valores enteros de `netrm:BufferRemaining` entre 0 y 4.096, ambos incluidos, y lee valores enteros entre 0 y el valor `xs:int` 214748364 de `maxInclusive`, ambos incluidos.  
  
## <a name="message-exchange-patterns"></a>Modelos de intercambio de mensajes  
 En esta sección se describe el comportamiento de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cuando se utiliza WS-Reliable Messaging para patrones de intercambio de mensajes diferentes. Para cada patrón de intercambio de mensajes, se consideran los dos escenarios de implementación siguientes:  
  
-   Iniciador no direccionable: el iniciador está tras un firewall; el respondedor solo puede entregar mensajes al iniciador mediante respuestas HTTP.  
  
-   Iniciador direccionable: el iniciador y el respondedor pueden enviar solicitudes HTTP; en otras palabras, se pueden establecer dos conexiones HTTP inversas.  
  
### <a name="one-way-non-addressable-initiator"></a>Iniciador unidireccional no direccionable  
  
#### <a name="binding"></a>Enlaces  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona un patrón de intercambio de mensajes unidireccional usando una secuencia sobre un canal HTTP. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usa las solicitudes HTTP para transmitir todos los mensajes del RMS al RMD y la respuesta HTTP para transmitir todos los mensajes del RMD al RMS.  
  
#### <a name="createsequence-exchange"></a>Intercambio de CreateSequence  
 El iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera un mensaje `CreateSequence` sin oferta. El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] asegura que `CreateSequence` no tenga ninguna oferta antes de crear una secuencia. El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] responde a la solicitud de `CreateSequence` con un mensaje `CreateSequenceResponse`.  
  
#### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement  
 El iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] procesa las confirmaciones en la respuesta de todos los mensajes, salvo en los mensajes de error y el mensaje `CreateSequence`. El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] siempre genera una confirmación independiente en respuesta a la secuencia y los mensajes `AckRequested`.  
  
#### <a name="terminatesequence-message"></a>Mensaje TerminateSequence  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] trata a `TerminateSequence` como una operación unidireccional, lo que significa que la respuesta HTTP tiene un cuerpo vacío y un código de estado HTTP 202.  
  
### <a name="one-way-addressable-initiator"></a>Iniciador unidireccional y direccionable  
  
#### <a name="binding"></a>Enlaces  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona un patrón de intercambio de mensajes unidireccional usando una secuencia sobre un canal HTTP entrante y uno saliente. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usa las solicitudes HTTP para transmitir todos los mensajes. Todas las respuestas HTTP tienen un cuerpo vacío y código de estado HTTP 202.  
  
#### <a name="createsequence-exchange"></a>Intercambio de CreateSequence  
 El iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera un mensaje `CreateSequence` sin oferta. El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] asegura que `CreateSequence` no tenga ninguna oferta antes de crear una secuencia. El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transmite el mensaje `CreateSequenceResponse` en una solicitud HTTP direccionada con la referencia de extremo `ReplyTo`.  
  
### <a name="duplex-addressable-initiator"></a>Iniciador dúplex y direccionable  
  
#### <a name="binding"></a>Enlaces  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona un patrón de intercambio de mensajes totalmente asincrónico y bidireccional usando dos secuencias sobre un canal HTTP entrante y uno saliente. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usa las solicitudes HTTP para transmitir todos los mensajes. Todas las respuestas HTTP tienen un cuerpo vacío y código de estado HTTP 202.  
  
#### <a name="createsequence-exchange"></a>Intercambio de CreateSequence  
 El iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera un mensaje `CreateSequence` con una oferta. El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se asegura de que `CreateSequence` tenga una oferta antes de crear una secuencia. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] envía `CreateSequenceResponse` en la solicitud HTTP dirigida a la referencia de extremo `CreateSequence` de los `ReplyTo`.  
  
#### <a name="sequence-lifetime"></a>Duración de la secuencia  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] trata las dos secuencias como una sesión totalmente dúplex.  
  
 Tras generar un error que provoca un error en una secuencia, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] espera que el extremo remoto genere un error en ambas secuencias. Tras leer un error que provoca un error en una secuencia, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera un error en ambas secuencias.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] puede cerrar su secuencia saliente y continuar procesando mensajes en su secuencia entrante. De manera inversa, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] puede procesar el cierre de la secuencia entrante y continuar enviando mensajes en su secuencia saliente.  
  
### <a name="request-reply-non-addressable-initiator"></a>Iniciador no direccionable de solicitud-respuesta  
  
#### <a name="binding"></a>Enlaces  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona un patrón de intercambio unidireccional de mensajes de solicitud-respuesta usando dos secuencias sobre un canal HTTP. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usa las solicitudes HTTP para transmitir los mensajes de la secuencia de solicitud y usa las respuestas HTTP para transmitir los mensajes de la secuencia de respuesta.  
  
#### <a name="createsequence-exchange"></a>Intercambio de CreateSequence  
 El iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera un mensaje `CreateSequence` con una oferta. El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se asegura de que `CreateSequence` tenga una oferta antes de crear una secuencia. El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] responde a la solicitud de `CreateSequence` con un mensaje `CreateSequenceResponse`.  
  
#### <a name="one-way-message"></a>Mensaje unidireccional  
 Para completar correctamente un protocolo de intercambio de mensajes unidireccional, el iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transmite un mensaje de secuencia de solicitud en la solicitud HTTP y recibe un mensaje `SequenceAcknowledgement` independiente en la respuesta HTTP. La `SequenceAcknowledgement` debe confirmar el mensaje transmitido.  
  
 El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] puede responder a la solicitud con una confirmación, un error o una respuesta con un cuerpo vacío y un código de estado HTTP 202.  
  
#### <a name="two-way-messages"></a>Mensajes bidireccionales  
 Para completar correctamente un protocolo de intercambio de mensajes bidireccional, el iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transmite un mensaje de secuencia de solicitud en la solicitud HTTP y recibe un mensaje de secuencia de respuesta en la respuesta HTTP. La respuesta debe llevar una `SequenceAcknowledgement` que confirme que se ha transmitido el mensaje de secuencia de solicitud.  
  
 El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] puede responder a la solicitud con una respuesta de la aplicación, un error o una respuesta con un cuerpo vacío y un código de estado HTTP 202.  
  
 Debido a la presencia de mensajes unidireccionales y al control de tiempo de las respuestas de la aplicación, el número de secuencia del mensaje de secuencia de solicitud y el número de secuencia del mensaje de respuesta no tienen ninguna correlación.  
  
#### <a name="retrying-replies"></a>Reintento de respuestas  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] confía en la correlación de solicitud-respuesta HTTP para la correlación del protocolo de intercambio de mensajes bidireccional. Debido a esto, el iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no deja de reintentar un mensaje de secuencia de solicitud cuando éste se confirma, sino cuando la respuesta HTTP lleva una confirmación, un mensaje de usuario o un error. El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] reintenta las respuestas en la bifurcación de la solicitud HTTP de la solicitud con la que se correlaciona la respuesta.  
  
#### <a name="lastmessage-exchange"></a>Intercambio de LastMessage  
 El iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera y transmite un último mensaje con cuerpo vacío en la bifurcación de la solicitud HTTP. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] necesita una respuesta pero omite el mensaje de respuesta real. El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] responde al último mensaje de cuerpo vacío de la secuencia de solicitud con el último mensaje de cuerpo vacío de la secuencia de respuesta.  
  
 Si el respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] recibe un último mensaje en el que el URI de acción no es http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] responde con un último mensaje. En el caso de un protocolo de intercambio de mensajes bidireccional, el último mensaje lleva el mensaje de la aplicación; en el caso de un protocolo de intercambio de mensajes unidireccional, el último mensaje está vacío.  
  
 El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no requiere una confirmación para el último mensaje de cuerpo vacío de la secuencia de respuesta.  
  
#### <a name="terminatesequence-exchange"></a>Intercambio de TerminateSequence  
 Cuando todas las solicitudes han recibido una respuesta válida, el iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera y transmite el mensaje `TerminateSequence` de la secuencia de solicitud en la bifurcación de la solicitud HTTP. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] necesita una respuesta pero omite el mensaje de respuesta real. El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] responde al mensaje `TerminateSequence` de la secuencia de solicitud con el mensaje `TerminateSequence` de la secuencia de respuesta.  
  
 En una secuencia de apagado normal, ambos mensajes `TerminateSequence` llevan un `SequenceAcknowledgement` de intervalo completo.  
  
### <a name="requestreply-addressable-initiator"></a>Iniciador direccionable de solicitud-respuesta  
  
#### <a name="binding"></a>Enlaces  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona un patrón de intercambio de mensajes de solicitud-respuesta usando dos secuencias sobre un canal HTTP entrante y uno saliente. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usa las solicitudes HTTP para transmitir todos los mensajes. Todas las respuestas HTTP tienen un cuerpo vacío y código de estado HTTP 202.  
  
#### <a name="createsequence-exchange"></a>Intercambio de CreateSequence  
 El iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera un mensaje `CreateSequence` con una oferta. El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se asegura de que `CreateSequence` tenga una oferta antes de crear una secuencia. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] envía `CreateSequenceResponse` en la solicitud HTTP dirigida a la referencia de extremo `CreateSequence` de los `ReplyTo`.  
  
#### <a name="requestreply-correlation"></a>Correlación entre solicitud y respuesta  
 El iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se asegura de que todos los mensajes de solicitud de la aplicación lleven un`MessageId` y una referencia de extremo `ReplyTo`. El iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aplica la referencia de extremo `CreateSequence` del mensaje `ReplyTo` en cada mensaje de solicitud de la aplicación. El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requiere que los mensajes de solicitud entrantes lleven un `MessageId` y un `ReplyTo`. El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se asegura de que el URI de la referencia del extremo de `CreateSequence` y de todos los mensajes de solicitud de la aplicación sean idénticos.
