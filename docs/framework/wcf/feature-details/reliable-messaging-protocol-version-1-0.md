---
title: Protocolo de mensajería de confianza versión 1.0
ms.date: 03/30/2017
ms.assetid: a5509a5c-de24-4bc2-9a48-19138055dcce
ms.openlocfilehash: cff07ae23e83a68c4cafa1ca122d84db98163d0d
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "48583968"
---
# <a name="reliable-messaging-protocol-version-10"></a>Protocolo de mensajería de confianza versión 1.0
En este tema cubre los detalles de implementación de Windows Communication Foundation (WCF) para WS-Reliable Messaging protocol de febrero de 2005 (versión 1.0) necesario para la interoperación mediante el transporte HTTP. WCF sigue la especificación WS-Reliable Messaging con las restricciones y clarificaciones explicadas en este tema. Tenga en cuenta que la versión 1.0 del protocolo WS-ReliableMessaging se implementa a partir de [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)].  
  
 El WS-Reliable Messaging de febrero de 2005 protocolo se implementa en WCF mediante el <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.  
  
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
 WCF implementa `CreateSequence` y `CreateSequenceResponse` mensajes para establecer una secuencia de mensajes confiable. Las siguientes restricciones son aplicables:  
  
-   B1101: El iniciador de WCF no genera el elemento Expires opcional en el `CreateSequence` mensaje o, en los casos cuando el `CreateSequence` mensaje contiene un `Offer` elemento, el elemento opcional `Expires` elemento en el `Offer` elemento.  
  
-   B1102: Al tener acceso a la `CreateSequence` mensaje WCF`Responder` envía y recibe ambos `Expires` elementos si existen, pero no usa sus valores.  
  
 WS-Reliable Messaging incluye el mecanismo `Offer` para establecer las dos secuencias correlacionadas inversas que forman una sesión.  
  
-   R1103: si `CreateSequence` contiene un elemento `Offer`, el respondedor de la mensajería de confianza debe aceptar la secuencia y responder con `CreateSequenceResponse`, que contiene un elemento `wsrm:Accept`, formando dos secuencias correlacionadas inversas, o rechazar la solicitud `CreateSequence`.  
  
-   R1104: `SequenceAcknowledgement` y los mensajes de la aplicación que fluyen en una secuencia inversa se deben enviar a la referencia de extremo `ReplyTo` de `CreateSequence`.  
  
-   R1105: las referencias de extremo `AcksTo` y `ReplyTo` en `CreateSequence` deben tener valores de dirección que coincidan byte a byte.  
  
     El servicio de respuesta WCF comprueba que la parte del URI del `AcksTo` y `ReplyTo` EPR es idénticos antes de crear una secuencia.  
  
-   R1106: las referencias de extremo `AcksTo` y `ReplyTo` del mensaje `CreateSequence` deberían tener el mismo conjunto de parámetros de referencia.  
  
     WCF no exige, pero supone que [parámetros de referencia] de `AcksTo` y `ReplyTo` en `CreateSequence` son idénticas y utiliza [parámetros de referencia] de `ReplyTo` referencia de punto de conexión para las confirmaciones y los mensajes de secuencia inversa.  
  
-   R1107: cuando dos secuencias inversas se establecen por medio del mecanismo `Offer`, los mensajes de aplicación y `SequenceAcknowledgement` que fluyen en secuencias inversas se deben enviar a la referencia de extremo `ReplyTo` de `CreateSequence`.  
  
-   R1108: cuando dos secuencias inversas se establecen mediante el mecanismo Offer, la propiedad `[address]` del elemento secundario de referencia de extremo `wsrm:AcksTo` del elemento `wsrm:Accept` de `CreateSequenceResponse` debe coincidir byte a byte con el URI de destino de `CreateSequence`.  
  
-   R1109: cuando se establecen dos secuencias inversas por medio del mecanismo `Offer`, los mensajes enviados por el iniciador y las confirmaciones de los mensajes por parte del respondedor se deben enviar a la misma referencia de extremo.  
  
     WCF usa WS-Reliable Messaging para establecer sesiones confiables entre el iniciador y Respondedor. Implementación de WS-Reliable Messaging de WCF proporciona una sesión confiable para completa y de solicitud-respuesta unidireccional, patrones de mensajería dúplex. El WS-Reliable Messaging `Offer` mecanismo en `CreateSequence` / `CreateSequenceResponse` le permite establecer dos secuencias inversas correlacionadas y proporciona un protocolo de sesión que es apto para todos los puntos de conexión del mensaje. Dado que WCF proporciona una garantía de seguridad para este tipo de sesión incluida la protección de extremo a otro para la integridad de la sesión, es práctico asegurar que llegan los mensajes dirigidos a la misma entidad al mismo destino. Esto también permite el “apoyo a caballo” de confirmaciones de secuencias en mensajes de aplicaciones. Por lo tanto, las restricciones R1104, R1105 y R1108 se aplican a WCF.  
  
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
  
-   Genera B1201:WCF y no mayores que los números de secuencia de accesos `xs:long`del valor inclusivo máximo, 9223372036854775807.  
  
-   B1202:WCF siempre genera un mensaje de último cuerpo vacío con el URI de acción de `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`.  
  
-   B1203: WCF recibe y entrega un mensaje con un encabezado de secuencia que contiene un `LastMessage` elemento siempre y cuando el URI de acción no es `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`.  
  
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
 WCF usa `AckRequested` encabezado como un mecanismo keep-alive. WCF no genera opcional `MessageNumber` elemento. Al recibir un mensaje con un `AckRequested` encabezado que contiene el `MessageNumber` elemento, WCF omite el `MessageNumber` valor del elemento, tal como se muestra en el ejemplo siguiente.  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>  
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
  </wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement-header"></a>Encabezado SequenceAcknowledgement  
 WCF usa un mecanismo para confirmaciones de secuencias proporcionadas en WS-Reliable Messaging.  
  
-   R1401: cuando dos secuencias inversas se establecen utilizando el mecanismo `Offer`, el encabezado `SequenceAcknowledgement` puede estar incluido en cualquier mensaje de aplicación transmitido al destinatario previsto.  
  
-   B1402: Cuando WCF debe generar una confirmación antes de recibir ningún mensaje de secuencia (por ejemplo, para satisfacer un `AckRequested` mensaje), WCF genera un `SequenceAcknowledgement` encabezado que contiene el intervalo 0-0, tal como se muestra en el ejemplo siguiente.  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>  
        urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
      </wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="0" Lower="0"/>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   B1403: WCF no genera `SequenceAcknowledgement` los encabezados que contienen un `Nack` elemento, pero admite `Nack` elementos.  
  
### <a name="ws-reliablemessaging-faults"></a>Errores de WS-ReliableMessaging  
 La siguiente es una lista de restricciones que se aplican a la implementación de WCF de errores de WS-Reliable Messaging:  
  
-   B1501: WCF no genera `MessageNumberRollover` errores.  
  
-   Puede generar el punto de conexión B1502:WCF `CreateSequenceRefused` produce un error como se describe en la especificación.  
  
-   B1503:when el punto de conexión de servicio alcanza su límite de conexión y no se puede procesar nuevas conexiones, WCF genera adicional `CreateSequenceRefused` subcódigo, de error `netrm:ConnectionLimitReached`, como se muestra en el ejemplo siguiente.  
  
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
 Dado que WS-Reliable Messaging utiliza WS-Addressing, WS-Reliable Messaging WCF implementación puede generar errores de WS-Addressing. En esta sección se trata los errores de WS-Addressing que WCF genera explícitamente en la capa de WS-Reliable Messaging:  
  
-   B1601:WCF genera el error requiere un encabezado Addressing mensaje cuando se cumple una de las siguientes acciones:  
  
    -   Falta un encabezado `Sequence` y un encabezado `Action` en un mensaje.  
  
    -   Falta un encabezado `CreateSequence` en un mensaje `MessageId`.  
  
    -   Falta un encabezado `CreateSequence` en un mensaje `ReplyTo`.  
  
-   B1602:WCF genera el error no admite la acción como respuesta a un mensaje que falta un `Sequence` encabezado y tiene un `Action` encabezado que no es reconocido en la especificación WS-Reliable Messaging.  
  
-   B1603:WCF genera el error extremo no disponible para indicar que el punto de conexión no procesa la secuencia tras el examen de la `CreateSequence` encabezados de direccionamiento del mensaje.  
  
## <a name="protocol-composition"></a>Composición de protocolos  
  
### <a name="composition-with-ws-addressing"></a>Composición con WS-Addressing  
 WCF admite dos versiones de WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] y W3C WS-Addressing 1.0 recomendaciones [WS-ADDR-CORE] y [WS-ADDR-SOAP].  
  
 Aunque la especificación de WS-Reliable Messaging solo menciona a WS-Addressing 2004/08, no limita la versión de WS-Addressing que se ha de utilizar. La siguiente es una lista de restricciones que se aplican a WCF:  
  
-   R2101: ambos WS-Addressing 2004/08 y WS-Addressing 1.0 se pueden usar con WS-Reliable Messaging.  
  
-   Se debe usar R2102:A única versión de WS-Addressing a lo largo de una secuencia de WS-Reliable Messaging determinada o un par de secuencias inversas correlacionadas mediante el `wsrm:Offer` mecanismo.  
  
### <a name="composition-with-soap"></a>Composición con SOAP  
 WCF admite el uso de SOAP 1.1 y SOAP 1.2 con WS-Reliable Messaging.  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a>Composición con WS-Security y WS-SecureConversation  
 WCF proporciona protección para secuencias de WS-Reliable Messaging mediante el uso de transporte (HTTPS) segura, la composición con WS-Security y composición con WS-Secure Conversation. La siguiente es una lista de restricciones que se aplican a WCF:  
  
-   R2301: para proteger la integridad de una secuencia de WS-Reliable Messaging además de la integridad y confidencialidad de los mensajes individuales, WCF requiere que se deben utilizar WS-Secure Conversation.  
  
-   R2302:AWS-Secure Conversation debe establecerse antes de establecer las secuencias de WS-Reliable Messaging.  
  
-   R2303: si la duración de la secuencia de WS-Reliable Messaging supera la duración de la sesión de WS-Secure Conversation, el `SecurityContextToken` establecido mediante WS-Secure Conversation se debe renovar utilizando el enlace de renovación de WS-Secure Conversation correspondiente.  
  
-   B2304:ws-secuencia de mensajería de confianza o un par de secuencias inversas correlacionadas siempre se enlazan a una sola sesión de WS-SecureConversation.  
  
     El origen WCF genera el `wsse:SecurityTokenReference` elemento en la sección de extensibilidad de elemento de la `CreateSequence` mensaje.  
  
-   R2305:when compuesta con WS-Secure Conversation, un `CreateSequence` mensaje debe contener el `wsse:SecurityTokenReference` elemento.  
  
## <a name="ws-reliable-messaging-ws-policy-assertion"></a>Aserción de WS-Policy de WS-Reliable Messaging   
 WCF usa WS-Reliable Messaging de aserción de WS-Policy `wsrm:RMAssertion` para describir funciones de extremos. La siguiente es una lista de restricciones que se aplican a WCF:  
  
-   B3001: WCF adjunta `wsrm:RMAssertion` WS-Policy Assertion a `wsdl:binding` elementos. WCF admite datos adjuntos a `wsdl:binding` y `wsdl:port` elementos.  
  
-   B3002: WCF admite las siguientes propiedades opcionales de aserción de WS-Reliable Messaging y proporciona control sobre ellas en WCF`ReliableMessagingBindingElement`:  
  
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
 WCF usa la extensibilidad de WS-Reliable Messaging para proporcionar un control más estricto adicional opcional sobre el flujo de mensajes de secuencias.  
  
 Control de flujo se habilita estableciendo el `ReliableSessionBindingElement`del `FlowControlEnabled``bool` propiedad `true`. La siguiente es una lista de restricciones que se aplican a WCF:  
  
-   B4001: Cuando está habilitado el Control de flujo de mensajería confiable, WCF genera un `netrm:BufferRemaining` elemento en la extensibilidad de elementos de la `SequenceAcknowledgement` encabezado.  
  
-   B4002: Cuando está habilitado el Control de flujo de mensajería confiable, WCF no requiere un `netrm:BufferRemaining` elemento esté presente en `SequenceAcknowledgement` encabezado, tal como se muestra en el ejemplo siguiente.  
  
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
  
-   B4003: WCF usa `netrm:BufferRemaining` indicar cuántos mensajes nuevos el destino de la mensajería confiable puede almacenar en búfer.  
  
-   B4004: el servicio de mensajería confiable de WCF limita el número de mensajes transmitidos cuando la aplicación de mensajería de confianza de destino no puede recibir mensajes rápidamente. El destino de la mensajería de confianza almacena en búfer los mensajes y el valor del elemento cae a 0.  
  
-   B4005: WCF genera `netrm:BufferRemaining` entero valores entre 0 y 4.096, ambos incluidos y lee valores enteros entre 0 y `xs:int`del `maxInclusive` valor 214748364 inclusive.  
  
## <a name="message-exchange-patterns"></a>Modelos de intercambio de mensajes  
 Esta sección describe el comportamiento de WCF cuando se usa la WS-Reliable Messaging para patrones de intercambio de mensajes diferentes. Para cada patrón de intercambio de mensajes, se consideran los dos escenarios de implementación siguientes:  
  
-   Iniciador no direccionable: el iniciador está tras un firewall; el respondedor solo puede entregar mensajes al iniciador mediante respuestas HTTP.  
  
-   Iniciador direccionable: el iniciador y el respondedor pueden enviar solicitudes HTTP; en otras palabras, se pueden establecer dos conexiones HTTP inversas.  
  
### <a name="one-way-non-addressable-initiator"></a>Iniciador unidireccional no direccionable  
  
#### <a name="binding"></a>Enlaces  
 WCF proporciona un patrón de intercambio de mensajes unidireccional utilizando una secuencia sobre un canal HTTP. WCF usa las solicitudes HTTP para transmitir todos los mensajes del RMS al RMD y la respuesta HTTP para transmitir todos los mensajes del RMD al RMS.  
  
#### <a name="createsequence-exchange"></a>Intercambio de CreateSequence  
 El iniciador de WCF genera un `CreateSequence` mensaje sin oferta. El servicio de respuesta WCF asegura la `CreateSequence` no tenga ninguna oferta antes de crear una secuencia. El servicio de respuesta WCF responde a la `CreateSequence` solicitud con un `CreateSequenceResponse` mensaje.  
  
#### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement  
 El iniciador de WCF procesa las confirmaciones en la respuesta de todos los mensajes excepto el `CreateSequence` mensajes y mensajes de error. El servicio de respuesta WCF siempre genera una confirmación independiente en la respuesta a la secuencia y `AckRequested` mensajes.  
  
#### <a name="terminatesequence-message"></a>Mensaje TerminateSequence  
 WCF trata `TerminateSequence` como una operación unidireccional, lo que significa que la respuesta HTTP tiene un cuerpo vacío y el código de estado HTTP 202.  
  
### <a name="one-way-addressable-initiator"></a>Iniciador unidireccional y direccionable  
  
#### <a name="binding"></a>Enlaces  
 WCF proporciona un patrón de intercambio de mensajes unidireccional utilizando una secuencia sobre una entrada y un canal de salida Http. WCF usa las solicitudes HTTP para transmitir todos los mensajes. Todas las respuestas HTTP tienen un cuerpo vacío y código de estado HTTP 202.  
  
#### <a name="createsequence-exchange"></a>Intercambio de CreateSequence  
 El iniciador de WCF genera un `CreateSequence` mensaje sin oferta. El servicio de respuesta WCF garantiza que el `CreateSequence` no tenga ninguna oferta antes de crear una secuencia. El servicio de respuesta WCF transmite el `CreateSequenceResponse` envía el mensaje en una solicitud HTTP con el `ReplyTo` referencia del extremo.  
  
### <a name="duplex-addressable-initiator"></a>Iniciador dúplex y direccionable  
  
#### <a name="binding"></a>Enlaces  
 WCF proporciona un patrón de intercambio de mensajes bidireccional totalmente asincrónico usando dos secuencias sobre una entrada y un canal de salida HTTP. WCF usa las solicitudes HTTP para transmitir todos los mensajes. Todas las respuestas HTTP tienen un cuerpo vacío y código de estado HTTP 202.  
  
#### <a name="createsequence-exchange"></a>Intercambio de CreateSequence  
 El iniciador de WCF genera un `CreateSequence` mensaje con una oferta. El servicio de respuesta WCF garantiza que la `CreateSequence` tenga una oferta antes de crear una secuencia. WCF envía el `CreateSequenceResponse` en la solicitud HTTP dirigida a la `CreateSequence`del `ReplyTo` referencia del extremo.  
  
#### <a name="sequence-lifetime"></a>Duración de la secuencia  
 WCF trata las dos secuencias como una sesión totalmente dúplex.  
  
 Tras generar un error que se produce un error en una secuencia, WCF espera que el extremo remoto al error en ambas secuencias. Tras leer un error que se produce un error en una secuencia, WCF produce un error en ambas secuencias.  
  
 WCF puede cerrar su secuencia saliente y continuar procesando los mensajes en su secuencia entrante. Por el contrario, WCF puede procesar el cierre de la secuencia entrante y continuar enviando mensajes en su secuencia saliente.  
  
### <a name="request-reply-non-addressable-initiator"></a>Iniciador no direccionable de solicitud-respuesta  
  
#### <a name="binding"></a>Enlaces  
 WCF ofrece un sentido y patrón de intercambio de mensajes de solicitud-respuesta usando dos secuencias sobre un canal HTTP. WCF usa las solicitudes HTTP para transmitir los mensajes de la secuencia de solicitud y usa las respuestas HTTP para transmitir los mensajes de la secuencia de respuesta.  
  
#### <a name="createsequence-exchange"></a>Intercambio de CreateSequence  
 El iniciador de WCF genera un `CreateSequence` mensaje con una oferta. El servicio de respuesta WCF garantiza que la `CreateSequence` tenga una oferta antes de crear una secuencia. El servicio de respuesta WCF responde a la `CreateSequence` solicitud con un `CreateSequenceResponse` mensaje.  
  
#### <a name="one-way-message"></a>Mensaje unidireccional  
 Para completar correctamente un protocolo de intercambio de mensajes unidireccional, el iniciador de WCF transmite un mensaje de secuencia de solicitud en la solicitud HTTP y recibe una independiente `SequenceAcknowledgement` mensaje en la respuesta HTTP. La `SequenceAcknowledgement` debe confirmar el mensaje transmitido.  
  
 El servicio de respuesta WCF puede responder a la solicitud con una confirmación, un error o una respuesta con un cuerpo vacío y el código de estado HTTP 202.  
  
#### <a name="two-way-messages"></a>Mensajes bidireccionales  
 Para completar correctamente un protocolo de intercambio de mensajes bidireccional, el iniciador de WCF transmite un mensaje de secuencia de solicitud en la solicitud HTTP y recibe un mensaje de secuencia de respuesta en la respuesta HTTP. La respuesta debe llevar una `SequenceAcknowledgement` que confirme que se ha transmitido el mensaje de secuencia de solicitud.  
  
 El servicio de respuesta WCF puede responder a la solicitud con una respuesta de la aplicación, un error o una respuesta con un cuerpo vacío y el código de estado HTTP 202.  
  
 Debido a la presencia de mensajes unidireccionales y al control de tiempo de las respuestas de la aplicación, el número de secuencia del mensaje de secuencia de solicitud y el número de secuencia del mensaje de respuesta no tienen ninguna correlación.  
  
#### <a name="retrying-replies"></a>Reintento de respuestas  
 WCF se basa en la correlación de solicitud-respuesta HTTP para la correlación de protocolo de intercambio de mensajes bidireccional. Por este motivo, el iniciador de WCF no deja de reintentar un mensaje de secuencia de solicitud cuando se confirma el mensaje de secuencia de solicitud, sino cuando la respuesta HTTP lleva una confirmación, el mensaje de usuario o el error. El servicio de respuesta WCF reintenta las respuestas en la bifurcación de la solicitud HTTP de la solicitud a la que se correlaciona la respuesta.  
  
#### <a name="lastmessage-exchange"></a>Intercambio de LastMessage  
 El iniciador de WCF genera y transmite un último mensaje con cuerpo vacío en la bifurcación de la solicitud HTTP. WCF requiere una respuesta pero omite el mensaje de respuesta real. El servicio de respuesta WCF responde a último mensaje de cuerpo vacío con cuerpo vacío último mensaje de la secuencia de respuesta la secuencia de solicitud.  
  
 Si el servicio de respuesta WCF recibe un último mensaje en el que el URI de acción no es `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`, las respuestas con un último mensaje de WCF. En el caso de un protocolo de intercambio de mensajes bidireccional, el último mensaje lleva el mensaje de la aplicación; en el caso de un protocolo de intercambio de mensajes unidireccional, el último mensaje está vacío.  
  
 El servicio de respuesta WCF no requiere una confirmación para el último mensaje de la secuencia de respuesta cuerpo vacío.  
  
#### <a name="terminatesequence-exchange"></a>Intercambio de TerminateSequence  
 Cuando todas las solicitudes han recibido una respuesta válida, el iniciador de WCF genera y transmite la secuencia de solicitud `TerminateSequence` mensaje en la bifurcación de la solicitud HTTP. WCF requiere una respuesta pero omite el mensaje de respuesta real. El servicio de respuesta WCF responde a la secuencia de solicitud `TerminateSequence` mensaje con la secuencia de respuesta `TerminateSequence` mensaje.  
  
 En una secuencia de apagado normal, ambos mensajes `TerminateSequence` llevan un `SequenceAcknowledgement` de intervalo completo.  
  
### <a name="requestreply-addressable-initiator"></a>Iniciador direccionable de solicitud-respuesta  
  
#### <a name="binding"></a>Enlaces  
 WCF proporciona un patrón de intercambio de mensajes de solicitud-respuesta utilizando dos secuencias a través de una entrada y un canal de salida HTTP. WCF usa las solicitudes HTTP para transmitir todos los mensajes. Todas las respuestas HTTP tienen un cuerpo vacío y código de estado HTTP 202.  
  
#### <a name="createsequence-exchange"></a>Intercambio de CreateSequence  
 El iniciador de WCF genera un `CreateSequence` mensaje con una oferta. El servicio de respuesta WCF garantiza que la `CreateSequence` tenga una oferta antes de crear una secuencia. WCF envía el `CreateSequenceResponse` en la solicitud HTTP dirigida a la `CreateSequence`del `ReplyTo` referencia del extremo.  
  
#### <a name="requestreply-correlation"></a>Correlación entre solicitud y respuesta  
 El iniciador de WCF garantiza que todos los osito de mensajes de solicitud de aplicación una `MessageId` y un `ReplyTo` referencia del extremo. El iniciador de WCF se aplica el `CreateSequence` del mensaje `ReplyTo` referencia de punto de conexión en cada mensaje de solicitud de aplicación. El servicio de respuesta WCF requiere que los mensajes de solicitud entrante lleven un `MessageId` y un `ReplyTo`. El servicio de respuesta WCF garantiza que los URI de la referencia de extremo de la `CreateSequence` y todos los mensajes de solicitud de aplicación son idénticos.
