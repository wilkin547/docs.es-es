---
description: 'Más información acerca de: Protocolo de mensajería de confianza versión 1,0'
title: Protocolo de mensajería de confianza versión 1.0
ms.date: 03/30/2017
ms.assetid: a5509a5c-de24-4bc2-9a48-19138055dcce
ms.openlocfilehash: dbd0184fd6ea9f92c96639d71088ac61bec20f3e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793602"
---
# <a name="reliable-messaging-protocol-version-10"></a>Protocolo de mensajería de confianza versión 1.0

En este tema se tratan los detalles de implementación de Windows Communication Foundation (WCF) para el protocolo WS-Reliable Messaging 2005 de febrero (versión 1,0) necesario para la interoperación mediante el transporte HTTP. WCF sigue el WS-Reliable especificación de mensajería con las restricciones y aclaraciones explicadas en este tema. Tenga en cuenta que el protocolo WS-ReliableMessaging versión 1,0 se implementa a partir de WinFX.

El protocolo WS-Reliable Messaging 2005 de febrero se implementa en WCF <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> .

Para su comodidad, el tema utiliza las siguientes funciones:

- Iniciador: el cliente que inicia la creación de la secuencia de mensajes WS-Reliable

- Respondedor: el servicio que recibe las solicitudes del iniciador

En este documento, se utilizan los prefijos y espacios de nombres de la tabla siguiente.

|Prefijo|Espacio de nombres|
|------------|---------------|
|wsrm|`http://schemas.xmlsoap.org/ws/2005/02/rm`|
|netrm|`http://schemas.microsoft.com/ws/2006/05/rm`|
|s|`http://www.w3.org/2003/05/soap-envelope`|
|wsa|`http://schemas.xmlsoap.org/ws/2005/08/addressing`|
|wsse|`http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd`|

## <a name="messaging"></a>Mensajería

### <a name="sequence-establishment-messages"></a>Mensajes de establecimiento de secuencia

WCF implementa `CreateSequence` mensajes y `CreateSequenceResponse` para establecer una secuencia de mensajes confiable. Se aplican las siguientes restricciones:

- B1101: el iniciador de WCF no genera el elemento Expires opcional en el `CreateSequence` mensaje o, en los casos en los que el `CreateSequence` mensaje contiene un `Offer` elemento, el `Expires` elemento opcional en el `Offer` elemento.

- B1102: al obtener acceso al `CreateSequence` mensaje, WCF `Responder` envía y recibe ambos `Expires` elementos si existen, pero no usa sus valores.

WS-Reliable Messaging incluye el mecanismo `Offer` para establecer las dos secuencias correlacionadas inversas que forman una sesión.

- R1103: si `CreateSequence` contiene un elemento `Offer`, el respondedor de la mensajería de confianza debe aceptar la secuencia y responder con `CreateSequenceResponse`, que contiene un elemento `wsrm:Accept`, formando dos secuencias correlacionadas inversas, o rechazar la solicitud `CreateSequence`.

- R1104: `SequenceAcknowledgement` y los mensajes de la aplicación que fluyen en una secuencia inversa se deben enviar a la referencia de punto de conexión `ReplyTo` de `CreateSequence`.

- R1105: las referencias de punto de conexión `AcksTo` y `ReplyTo` en `CreateSequence` deben tener valores de dirección que coincidan byte a byte.

  El respondedor de WCF comprueba que la parte del URI de `AcksTo` los `ReplyTo` EPRs y son idénticas antes de crear una secuencia.

- R1106: las referencias de punto de conexión `AcksTo` y `ReplyTo` del mensaje `CreateSequence` deberían tener el mismo conjunto de parámetros de referencia.

  WCF no aplica pero supone que los [parámetros de referencia] de `AcksTo` y `ReplyTo` en `CreateSequence` son idénticos y utiliza [parámetros de referencia] de `ReplyTo` referencia de extremo para las confirmaciones y los mensajes de secuencia inversa.

- R1107: cuando dos secuencias inversas se establecen por medio del mecanismo `Offer`, los mensajes de aplicación y `SequenceAcknowledgement` que fluyen en secuencias inversas se deben enviar a la referencia de punto de conexión `ReplyTo` de `CreateSequence`.

- R1108: cuando dos secuencias inversas se establecen mediante el mecanismo Offer, la propiedad `[address]` del elemento secundario de referencia de extremo `wsrm:AcksTo` del elemento `wsrm:Accept` de `CreateSequenceResponse` debe coincidir byte a byte con el URI de destino de `CreateSequence`.

- R1109: cuando se establecen dos secuencias inversas por medio del mecanismo `Offer`, los mensajes enviados por el iniciador y las confirmaciones de los mensajes por parte del respondedor se deben enviar a la misma referencia de punto de conexión.

  WCF usa mensajería WS-Reliable para establecer sesiones confiables entre el iniciador y el respondedor. La implementación de mensajería de WS-Reliable de WCF proporciona una sesión confiable para patrones de mensajería dúplex completa, de solicitud-respuesta y unidireccionales. El `Offer` mecanismo de mensajería WS-Reliable de `CreateSequence` / `CreateSequenceResponse` permite establecer dos secuencias inversas correlacionadas y proporciona un protocolo de sesión que es adecuado para todos los extremos de mensajes. Dado que WCF proporciona una garantía de seguridad para este tipo de sesión, incluida la protección de un extremo a otro para la integridad de la sesión, es práctico asegurarse de que los mensajes destinados a la misma entidad lleguen al mismo destino. Esto también permite el “apoyo a caballo” de confirmaciones de secuencias en mensajes de aplicaciones. Por lo tanto, las restricciones R1104, R1105 y R1108 se aplican a WCF.

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

- B1201: WCF genera y obtiene acceso a los números de secuencia que no son mayores que el `xs:long` valor inclusivo máximo de 9223372036854775807.

- B1202: WCF siempre genera un último mensaje de cuerpo vacío con el URI de la acción de `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage` .

- B1203: WCF recibe y entrega un mensaje con un encabezado de secuencia que contiene un `LastMessage` elemento, siempre y cuando el URI de la acción no sea `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage` .

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

WCF usa `AckRequested` el encabezado como un mecanismo Keep-Alive. WCF no genera el elemento opcional `MessageNumber` . Al recibir un mensaje con un `AckRequested` encabezado que contiene el `MessageNumber` elemento, WCF omite el `MessageNumber` valor del elemento, como se muestra en el ejemplo siguiente.

```xml
<wsrm:AckRequested>
  <wsrm:Identifier>
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36
  </wsrm:Identifier>
</wsrm:AckRequested>
```

### <a name="sequenceacknowledgement-header"></a>Encabezado SequenceAcknowledgement

WCF usa el mecanismo de reutilización para las confirmaciones de secuencias proporcionadas en WS-Reliable mensajería.

- R1401: cuando dos secuencias inversas se establecen utilizando el mecanismo `Offer`, el encabezado `SequenceAcknowledgement` puede estar incluido en cualquier mensaje de aplicación transmitido al destinatario previsto.

- B1402: cuando WCF debe generar una confirmación antes de recibir mensajes de secuencia (por ejemplo, para satisfacer un `AckRequested` mensaje), WCF genera un `SequenceAcknowledgement` encabezado que contiene el intervalo 0-0, como se muestra en el ejemplo siguiente.

  ```xml
  <wsrm:SequenceAcknowledgement>
    <wsrm:Identifier>
      urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36
    </wsrm:Identifier>
    <wsrm:AcknowledgementRange Upper="0" Lower="0"/>
  </wsrm:SequenceAcknowledgement>
  ```

- B1403: WCF no genera `SequenceAcknowledgement` encabezados que contengan un `Nack` elemento pero admita `Nack` elementos.

### <a name="ws-reliablemessaging-faults"></a>Errores de WS-ReliableMessaging

A continuación se muestra una lista de restricciones que se aplican a la implementación de WCF de errores de mensajería de WS-Reliable:

- B1501: WCF no genera `MessageNumberRollover` errores.

- B1502: el punto de conexión de WCF puede generar `CreateSequenceRefused` errores como se describe en la especificación.

- B1503: cuando el extremo de servicio alcanza su límite de conexiones y no puede procesar nuevas conexiones, WCF genera un `CreateSequenceRefused` subcódigo de error adicional, `netrm:ConnectionLimitReached` , tal y como se muestra en el ejemplo siguiente.

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

Dado que WS-Reliable mensajería usa WS-Addressing, WCF WS-Reliable la implementación de mensajería puede generar errores de WS-Addressing. En esta sección se tratan los errores de WS-Addressing que WCF genera explícitamente en el nivel de mensajería WS-Reliable:

- B1601: WCF genera el encabezado de direccionamiento del mensaje de error necesario cuando se cumple una de las siguientes condiciones:

  - Falta un encabezado `Sequence` y un encabezado `Action` en un mensaje.

  - Falta un encabezado `CreateSequence` en un mensaje `MessageId`.

  - Falta un encabezado `CreateSequence` en un mensaje `ReplyTo`.

- B1602: WCF genera la acción de error no admitida en la respuesta a un mensaje que no tiene un `Sequence` encabezado y tiene un `Action` encabezado que no es reconocido en la especificación de mensajería de WS-Reliable.

- B1603: WCF genera el extremo de error no disponible para indicar que el extremo no procesa la secuencia en función del examen de los `CreateSequence` encabezados de direccionamiento del mensaje.

## <a name="protocol-composition"></a>Composición de protocolos

### <a name="composition-with-ws-addressing"></a>Composición con WS-Addressing

WCF admite dos versiones de WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] y las recomendaciones de W3C WS-Addressing 1,0 [WS-ADDR-CORE] y [WS-ADDR-SOAP].

Aunque la especificación de WS-Reliable Messaging solo menciona a WS-Addressing 2004/08, no limita la versión de WS-Addressing que se ha de utilizar. A continuación se muestra una lista de restricciones que se aplican a WCF:

- R2101:WS-Addressing 2004/08 y WS-Addressing 1.0 se pueden utilizar con WS-Reliable Messaging.

- R2102: se debe utilizar una única versión de WS-Addressing en una secuencia de mensajería WS-Reliable determinada o un par de secuencias inversas correlacionadas mediante el `wsrm:Offer` mecanismo.

### <a name="composition-with-soap"></a>Composición con SOAP

WCF admite el uso de SOAP 1,1 y SOAP 1,2 con WS-Reliable mensajería.

### <a name="composition-with-ws-security-and-ws-secureconversation"></a>Composición con WS-Security y WS-SecureConversation

WCF proporciona protección para WS-Reliable secuencias de mensajería mediante el transporte seguro (HTTPS), la composición con WS-Security y la composición con WS-Secure Conversation. A continuación se muestra una lista de restricciones que se aplican a WCF:

- R2301: para proteger la integridad de una secuencia de mensajería WS-Reliable además de la integridad y confidencialidad de los mensajes individuales, WCF requiere que se use WS-Secure conversación.

- R2302:una sesión de WS-Secure Conversation se debe establecer antes de establecer las secuencias de WS-Reliable Messaging.

- R2303: si la duración de la secuencia de WS-Reliable Messaging supera la duración de la sesión de WS-Secure Conversation, el `SecurityContextToken` establecido mediante WS-Secure Conversation se debe renovar utilizando el enlace de renovación de WS-Secure Conversation correspondiente.

- B2304:la secuencia de WS-Reliable Messaging o un par de secuencias inversas correlacionadas siempre se enlazan a una única sesión de WS-SecureConversation.

  El origen de WCF genera el `wsse:SecurityTokenReference` elemento en la sección de extensibilidad de elementos del `CreateSequence` mensaje.

- R2305: cuando se crea con WS-Secure Conversation, un `CreateSequence` mensaje debe contener el `wsse:SecurityTokenReference` elemento.

## <a name="ws-reliable-messaging-ws-policy-assertion"></a>Aserción de WS-Policy de WS-Reliable Messaging 

WCF usa WS-Reliable la aserción WS-Policy `wsrm:RMAssertion` de mensajería para describir las capacidades de los extremos. A continuación se muestra una lista de restricciones que se aplican a WCF:

- B3001: WCF asocia `wsrm:RMAssertion` WS-Policy aserción a `wsdl:binding` los elementos. WCF admite datos adjuntos `wsdl:binding` a `wsdl:port` elementos y.

- B3002: WCF admite las siguientes propiedades opcionales de WS-Reliable aserción de mensajería y proporciona control sobre ellas en WCF `ReliableMessagingBindingElement` :

  - `wsrm:InactivityTimeout`

  - `wsrm:AcknowledgementInterval`

  A continuación se muestra un ejemplo.

  ```xml
  <wsrm:RMAssertion>
    <wsrm:InactivityTimeout Milliseconds="600000" />
    <wsrm:AcknowledgementInterval Milliseconds="200" />
  </wsrm:RMAssertion>
  ```

## <a name="flow-control-ws-reliable-messaging-extension"></a>Extensión de WS-Reliable Messaging de control de flujo

WCF usa la extensibilidad de mensajería de WS-Reliable para proporcionar un control adicional más estrecho y opcional sobre el flujo de mensajes de secuencia.

El control de flujo se habilita estableciendo la <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> propiedad en `true` . A continuación se muestra una lista de restricciones que se aplican a WCF:

- B4001: cuando está habilitado el control de flujo de mensajería de confianza, WCF genera un `netrm:BufferRemaining` elemento en la extensibilidad de elementos del `SequenceAcknowledgement` encabezado.

- B4002: cuando está habilitado el control de flujo de la mensajería de confianza, WCF no requiere que `netrm:BufferRemaining` haya un elemento en `SequenceAcknowledgement` el encabezado, tal y como se muestra en el ejemplo siguiente.

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

- B4003: WCF usa `netrm:BufferRemaining` para indicar cuántos mensajes nuevos puede almacenar en búfer el destino de la mensajería de confianza.

- B4004: el servicio de mensajería confiable de WCF limita el número de mensajes que se transmiten cuando la aplicación de destino de la mensajería de confianza no puede recibir mensajes rápidamente. El destino de la mensajería de confianza almacena en búfer los mensajes y el valor del elemento cae a 0.

- B4005: WCF genera `netrm:BufferRemaining` valores enteros entre 0 y 4096, ambos inclusive, y Lee valores enteros entre 0 y `xs:int` el `maxInclusive` valor 214748364, ambos inclusive.

## <a name="message-exchange-patterns"></a>Modelos de intercambio de mensajes

En esta sección se describe el comportamiento de WCF cuando WS-Reliable mensajería se usa para diferentes patrones de intercambio de mensajes. Para cada patrón de intercambio de mensajes, se consideran los dos escenarios de implementación siguientes:

- Iniciador no direccionable: el iniciador está tras un firewall; el respondedor solo puede entregar mensajes al iniciador mediante respuestas HTTP.

- Iniciador direccionable: el iniciador y el respondedor pueden enviar solicitudes HTTP; en otras palabras, se pueden establecer dos conexiones HTTP inversas.

### <a name="one-way-non-addressable-initiator"></a>Iniciador unidireccional no direccionable

#### <a name="binding"></a>Enlace

WCF proporciona un patrón de intercambio de mensajes unidireccional utilizando una secuencia sobre un canal HTTP. WCF usa las solicitudes HTTP para transmitir todos los mensajes del RMS al RMD y la respuesta HTTP para transmitir todos los mensajes del RMD al RMS.

#### <a name="createsequence-exchange"></a>Intercambio de CreateSequence

El iniciador de WCF genera un `CreateSequence` mensaje sin ninguna oferta. El respondedor de WCF garantiza que `CreateSequence` no tenga ninguna oferta antes de crear una secuencia. El respondedor de WCF responde a la `CreateSequence` solicitud con un `CreateSequenceResponse` mensaje.

#### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement

El iniciador de WCF procesa las confirmaciones en la respuesta de todos los mensajes excepto el `CreateSequence` mensaje y los mensajes de error. El respondedor de WCF siempre genera una confirmación independiente en la respuesta a la secuencia y a `AckRequested` los mensajes.

#### <a name="terminatesequence-message"></a>Mensaje TerminateSequence

WCF trata `TerminateSequence` como una operación unidireccional, lo que significa que la respuesta http tiene un cuerpo vacío y un código de estado http 202.

### <a name="one-way-addressable-initiator"></a>Iniciador unidireccional y direccionable

#### <a name="binding"></a>Enlace

WCF proporciona un patrón de intercambio de mensajes unidireccional utilizando una secuencia sobre un canal http de entrada y de salida. WCF usa las solicitudes HTTP para transmitir todos los mensajes. Todas las respuestas HTTP tienen un cuerpo vacío y código de estado HTTP 202.

#### <a name="createsequence-exchange"></a>Intercambio de CreateSequence

El iniciador de WCF genera un `CreateSequence` mensaje sin ninguna oferta. El respondedor de WCF garantiza que `CreateSequence` no tiene ninguna oferta antes de crear una secuencia. El respondedor de WCF transmite el `CreateSequenceResponse` mensaje en una solicitud HTTP dirigida a la `ReplyTo` referencia de extremo.

### <a name="duplex-addressable-initiator"></a>Iniciador dúplex y direccionable

#### <a name="binding"></a>Enlace

WCF proporciona un modelo de intercambio de mensajes bidireccional totalmente asincrónico que usa dos secuencias sobre un canal HTTP de entrada y de salida. WCF usa las solicitudes HTTP para transmitir todos los mensajes. Todas las respuestas HTTP tienen un cuerpo vacío y código de estado HTTP 202.

#### <a name="createsequence-exchange"></a>Intercambio de CreateSequence

El iniciador de WCF genera un `CreateSequence` mensaje con una oferta. El respondedor de WCF garantiza que `CreateSequence` tenga una oferta antes de crear una secuencia. WCF envía el `CreateSequenceResponse` en la solicitud HTTP dirigida a la `CreateSequence` `ReplyTo` referencia de extremo de.

#### <a name="sequence-lifetime"></a>Duración de la secuencia

WCF trata las dos secuencias como una sesión totalmente dúplex.

Tras generar un error que genera un error en una secuencia, WCF espera que el punto de conexión remoto genere un error en ambas secuencias. Al leer un error que genera un error en una secuencia, WCF genera un error en ambas secuencias.

WCF puede cerrar su secuencia de salida y continuar procesando los mensajes en la secuencia de entrada. Por el contrario, WCF puede procesar el cierre de la secuencia de entrada y continuar enviando mensajes en su secuencia de salida.

### <a name="request-reply-non-addressable-initiator"></a>Iniciador no direccionable de solicitud-respuesta

#### <a name="binding"></a>Enlace

WCF proporciona un modelo de intercambio de mensajes de solicitud-respuesta unidireccional que usa dos secuencias sobre un canal HTTP. WCF usa las solicitudes HTTP para transmitir los mensajes de la secuencia de solicitud y usa las respuestas HTTP para transmitir los mensajes de la secuencia de respuesta.

#### <a name="createsequence-exchange"></a>Intercambio de CreateSequence

El iniciador de WCF genera un `CreateSequence` mensaje con una oferta. El respondedor de WCF garantiza que `CreateSequence` tenga una oferta antes de crear una secuencia. El respondedor de WCF responde a la `CreateSequence` solicitud con un `CreateSequenceResponse` mensaje.

#### <a name="one-way-message"></a>Mensaje unidireccional

Para completar correctamente un protocolo de intercambio de mensajes unidireccional, el iniciador de WCF transmite un mensaje de secuencia de solicitud en la solicitud HTTP y recibe un `SequenceAcknowledgement` mensaje independiente en la respuesta http. La `SequenceAcknowledgement` debe confirmar el mensaje transmitido.

El respondedor de WCF puede responder a la solicitud con una confirmación, un error o una respuesta con un cuerpo vacío y un código de Estado HTTP 202.

#### <a name="two-way-messages"></a>Mensajes bidireccionales

Para completar correctamente un protocolo de intercambio de mensajes bidireccional, el iniciador de WCF transmite un mensaje de secuencia de solicitud en la solicitud HTTP y recibe un mensaje de secuencia de respuesta en la respuesta HTTP. La respuesta debe llevar una `SequenceAcknowledgement` que confirme que se ha transmitido el mensaje de secuencia de solicitud.

El respondedor de WCF puede responder a la solicitud con una respuesta de la aplicación, un error o una respuesta con un cuerpo vacío y un código de Estado HTTP 202.

Debido a la presencia de mensajes unidireccionales y al control de tiempo de las respuestas de la aplicación, el número de secuencia del mensaje de secuencia de solicitud y el número de secuencia del mensaje de respuesta no tienen ninguna correlación.

#### <a name="retrying-replies"></a>Reintento de respuestas

WCF se basa en la correlación de solicitud-respuesta HTTP para la correlación del Protocolo de intercambio de mensajes bidireccional. Debido a esto, el iniciador de WCF no deja de reintentar un mensaje de secuencia de solicitud cuando se confirma el mensaje de secuencia de solicitud, sino cuando la respuesta HTTP lleva una confirmación, un mensaje de usuario o un error. El respondedor de WCF reintenta las respuestas en el segmento de la solicitud HTTP de la solicitud a la que se correlaciona la respuesta.

#### <a name="lastmessage-exchange"></a>Intercambio de LastMessage

El iniciador de WCF genera y transmite un último mensaje de cuerpo vacío en la pierna de la solicitud HTTP. WCF requiere una respuesta pero omite el mensaje de respuesta real. El respondedor de WCF responde al último mensaje de cuerpo vacío de la secuencia de la solicitud con el último mensaje de cuerpo vacío de la secuencia de respuesta.

Si el respondedor de WCF recibe un último mensaje en el que el URI de la acción no es `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage` , WCF responde con un último mensaje. En el caso de un protocolo de intercambio de mensajes bidireccional, el último mensaje lleva el mensaje de la aplicación; en el caso de un protocolo de intercambio de mensajes unidireccional, el último mensaje está vacío.

El respondedor de WCF no requiere una confirmación para el último mensaje de cuerpo vacío de la secuencia de respuesta.

#### <a name="terminatesequence-exchange"></a>Intercambio de TerminateSequence

Cuando todas las solicitudes han recibido una respuesta válida, el iniciador de WCF genera y transmite el mensaje de la secuencia de solicitud `TerminateSequence` en la pierna de la solicitud HTTP. WCF requiere una respuesta pero omite el mensaje de respuesta real. El respondedor de WCF responde al mensaje de la secuencia de solicitud `TerminateSequence` con el mensaje de la secuencia de respuesta `TerminateSequence` .

En una secuencia de apagado normal, ambos mensajes `TerminateSequence` llevan un `SequenceAcknowledgement` de intervalo completo.

### <a name="requestreply-addressable-initiator"></a>Iniciador direccionable de solicitud-respuesta

#### <a name="binding"></a>Enlace

WCF proporciona un patrón de intercambio de mensajes de solicitud-respuesta que usa dos secuencias sobre un canal HTTP de entrada y de salida. WCF usa las solicitudes HTTP para transmitir todos los mensajes. Todas las respuestas HTTP tienen un cuerpo vacío y código de estado HTTP 202.

#### <a name="createsequence-exchange"></a>Intercambio de CreateSequence

El iniciador de WCF genera un `CreateSequence` mensaje con una oferta. El respondedor de WCF garantiza que `CreateSequence` tenga una oferta antes de crear una secuencia. WCF envía el `CreateSequenceResponse` en la solicitud HTTP dirigida a la `CreateSequence` `ReplyTo` referencia de extremo de.

#### <a name="requestreply-correlation"></a>Correlación entre solicitud y respuesta

El iniciador de WCF garantiza que todos los mensajes de solicitud de aplicación llevan un `MessageId` y una `ReplyTo` referencia de extremo. El iniciador de WCF aplica la `CreateSequence` referencia de extremo del mensaje `ReplyTo` en cada mensaje de solicitud de aplicación. El respondedor de WCF requiere que los mensajes de solicitud entrantes lleven un `MessageId` y un `ReplyTo` . El respondedor de WCF garantiza que el URI de la referencia de extremo de los mensajes de solicitud de la `CreateSequence` aplicación y de todos son idénticos.
