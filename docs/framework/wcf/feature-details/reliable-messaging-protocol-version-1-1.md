---
description: 'Más información acerca de: Protocolo de mensajería de confianza versión 1,1'
title: Protocolo de mensajería de confianza versión 1,1
ms.date: 03/30/2017
ms.assetid: 0da47b82-f8eb-42da-8bfe-e56ce7ba6f59
ms.openlocfilehash: 07d1ffb4347c7481944bc5d1c2ccef0940f18071
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99632911"
---
# <a name="reliable-messaging-protocol-version-11"></a>Protocolo de mensajería de confianza versión 1,1

En este tema se tratan los detalles de implementación de Windows Communication Foundation (WCF) para el protocolo WS-ReliableMessaging 2007 de febrero (versión 1,1) necesario para la interoperación mediante el transporte HTTP. WCF sigue la especificación de WS-ReliableMessaging con las restricciones y aclaraciones explicadas en este tema. Tenga en cuenta que el protocolo WS-ReliableMessaging versión 1,1 se implementa a partir de .NET Framework 3,5.

El WS-ReliableMessaging el protocolo 2007 de febrero se implementa en WCF <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> .

Para su comodidad, el tema utiliza las siguientes funciones:

- Iniciador: el cliente que inicia la creación de la secuencia de mensajes WS-Reliable.

- Respondedor: el servicio que recibe las solicitudes del iniciador.

 En este documento, se utilizan los prefijos y espacios de nombres de la tabla siguiente.

|Prefijo|Espacio de nombres|
|-|-|
|wsrm|`http://docs.oasis-open.org/ws-rx/wsrm/200702`|
|netrm|`http://schemas.microsoft.com/ws/2006/05/rm`|
|s|`http://www.w3.org/2003/05/soap-envelope`|
|wsa|`http://schemas.xmlsoap.org/ws/2005/08/addressing`|
|wsse|`http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd`|
|wsrmp|`http://docs.oasis-open.org/ws-rx/wsrmp/200702`|
|netrmp|`http://schemas.microsoft.com/ws-rx/wsrmp/200702`|
|wsp|(Directiva WS-Policy 1.2 o WS-Policy 1.5)|

## <a name="messaging"></a>Mensajería

### <a name="sequence-creation"></a>Creación de secuencias

WCF implementa `CreateSequence` mensajes y `CreateSequenceResponse` para establecer una secuencia de mensajería confiable. Se aplican las siguientes restricciones:

- B1101: el iniciador de WCF usa la misma referencia de extremo que el `CreateSequence` del mensaje `ReplyTo` , `AcksTo` y `Offer/Endpoint` .

- R1102: las referencias de punto de conexión `AcksTo`, `ReplyTo` y `Offer/Endpoint` en el mensaje `CreateSequence` deben tener valores de dirección con representaciones de cadena idénticas, de tal modo que coincidan por octetos.

  - El respondedor de WCF comprueba que la parte del URI de `AcksTo` las `ReplyTo` `Endpoint` referencias de extremo y son idénticas antes de crear una secuencia.

- R1103: las referencias de punto de conexión `AcksTo`, `ReplyTo` y `Offer/Endpoint` en el mensaje `CreateSequence` deberían tener el mismo conjunto de parámetros de referencia.

  - WCF no exige, pero supone que los parámetros de referencia de `AcksTo` `ReplyTo` y `Offer/Endpoint` las referencias de extremo en `CreateSequence` son idénticos y usa parámetros de referencia de la `ReplyTo` referencia de extremo para las confirmaciones y los mensajes de secuencia inversa.

- B1104: el iniciador de WCF no genera el `Expires` elemento opcional o `Offer/Expires` en el `CreateSequence` mensaje.

- B1105: al obtener acceso al `CreateSequence` mensaje, el respondedor de WCF usa el `Expires` valor del `CreateSequence` elemento como el `Expires` valor del `CreateSequenceResponse` elemento. De lo contrario, el respondedor de WCF Lee y omite los `Expires` `Offer/Expires` valores y.

- B1106: al obtener acceso al `CreateSequenceResponse` mensaje, el iniciador de WCF lee el valor opcional, `Expires` pero no lo usa.

- B1107: el iniciador y respondedor de WCF siempre genera el `IncompleteSequenceBehavior` elemento opcional en los `CreateSequence/Offer` `CreateSequenceResponse` elementos y.

- B1108: WCF solo usa los `DiscardFollowingFirstGap` valores y del `NoDiscard` `IncompleteSequenceBehavior` elemento.

  - WS-ReliableMessaging utiliza el mecanismo `Offer` para establecer las dos secuencias correlacionadas inversas que forman una sesión.

- B1109: Si `CreateSequence` contiene un `Offer` elemento, el respondedor de WCF unidireccional rechaza la secuencia proporcionada respondiendo con una `CreateSequenceResponse` sin un `Accept` elemento.

- B1110: Si un respondedor de mensajería de confianza rechaza la secuencia ofrecida, el iniciador de WCF genera un error en la secuencia recién establecida.

- B1111: Si `CreateSequence` no contiene un `Offer` elemento, el respondedor de WCF bidireccional rechaza la secuencia proporcionada respondiendo con un `CreateSequenceRefused` error.

- R1112: cuando dos secuencias inversas se establecen utilizando el mecanismo `Offer`, la propiedad `[address]` de la referencia de punto de conexión `CreateSequenceResponse/Accept/AcksTo` debe coincidir con el URI de destino del mensaje `CreateSequence` byte a byte.

- R1113: cuando dos secuencias inversas se establecen utilizando el mecanismo `Offer`, todos los mensajes en ambas secuencias que fluyen desde el iniciador hasta el respondedor se deben enviar a la misma referencia de punto de conexión.

WCF usa WS-ReliableMessaging para establecer sesiones confiables entre el iniciador y el respondedor. La implementación de WS-ReliableMessaging de WCF proporciona una sesión confiable para patrones de mensajería dúplex completa y de solicitud-respuesta unidireccionales. El mecanismo `Offer` de WS-ReliableMessaging en `CreateSequence` y `CreateSequenceResponse` le permite establecer dos secuencias inversas correlacionadas y proporciona un protocolo de sesión que es apto para todos los puntos de conexión de mensajes. Dado que WCF proporciona una garantía de seguridad para este tipo de sesión, incluida la protección de un extremo a otro para la integridad de la sesión, es práctico asegurarse de que los mensajes destinados a la misma parte lleguen al mismo destino. Esto también permite el “apoyo a caballo” de confirmaciones de secuencias en mensajes de aplicaciones. Por lo tanto, las restricciones R1102, R1112 y R1113 se aplican a WCF.

Ejemplo de mensaje `CreateSequence`.

```xml
<s:Envelope>
  <s:Header>
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/CreateSequence</wsa:Action>
    <wsa:MessageID>urn:uuid:949cca61-8813-42ff-ab33-18d9e3fa82fa</wsa:MessageID>
    <wsa:ReplyTo>
        <wsa:Address>http://Business456.com/clientA</wsa:Address>
    </wsa:ReplyTo>
    <wsa:To s:mustUnderstand="1">http://BusinessABC.com/serviceA</wsa:To>
  </s:Header>
  <s:Body>
    <wsrm:CreateSequence>
      <wsrm:AcksTo>
        <wsa:Address>http://Business456.com/clientA</wsa:Address>
      </wsrm:AcksTo>
      <wsrm:Offer>
        <wsrm:Identifier>urn:uuid:066b4730-fc82-458a-a5c1-210be4fb4e4e</wsrm:Identifier>
        <wsrm:Endpoint>
          <wsa:Address>http://Business456.com/clientA</wsa:Address>
        </wsrm:Endpoint>
        <wsrm:IncompleteSequenceBehavior>DiscardFollowingFirstGap</wsrm:IncompleteSequenceBehavior>
      </wsrm:Offer>
    </wsrm:CreateSequence>
  </s:Body>
</s:Envelope>
```

Ejemplo de mensaje `CreateSequenceResponse`.

```xml
<s:Envelope>
  <s:Header>
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/CreateSequenceResponse</wsa:Action>
    <wsa:RelatesTo>urn:uuid:949cca61-8813-42ff-ab33-18d9e3fa82fa</wsa:RelatesTo>
    <wsa:To s:mustUnderstand="1">http://Business456.com/clientA</wsa:To>
  </s:Header>
  <s:Body>
    <wsrm:CreateSequenceResponse>
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
      <wsrm:IncompleteSequenceBehavior>DiscardFollowingFirstGap</wsrm:IncompleteSequenceBehavior>
      <wsrm:Accept>
        <wsrm:AcksTo>
          <wsa:Address>http://BusinessABC.com/serviceA</wsa:Address>
        </wsrm:AcksTo>
      </wsrm:Accept>
    </wsrm:CreateSequenceResponse>
  </s:Body>
</s:Envelope>
```

### <a name="closing-a-sequence"></a>Cierre de una secuencia

WCF usa los `CloseSequence` `CloseSequenceResponse` mensajes y para un cierre Iniciado por el origen de mensajería de confianza. El destino de la mensajería de confianza de WCF no inicia el cierre y el origen de la mensajería de confianza de WCF no admite el apagado Iniciado por el destino de la mensajería de confianza. Se aplican las siguientes restricciones:

- B1201: el origen de la mensajería de confianza de WCF siempre envía un `CloseSequence` mensaje para cerrar la secuencia.

- B1202: el origen de la mensajería de confianza espera la confirmación del intervalo completo de mensajes de secuencia antes de enviar el mensaje `CloseSequence`.

- B1203: el origen de la mensajería de confianza siempre incluye el elemento opcional `LastMsgNumber`, a menos que la secuencia no contenga mensajes.

- R1204: el destino de la mensajería de confianza no debe iniciar el cierre mediante el envío de un mensaje `CloseSequence`.

- B1205: al recibir un `CloseSequence` mensaje, el origen de mensajería confiable de WCF considera que la secuencia está incompleta y envía un error.

 Ejemplo de mensaje `CloseSequence`.

```xml
<s:Envelope>
  <s:Header>
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/CloseSequence</wsa:Action>
    <wsa:MessageID>urn:uuid:6ce1d4c3-e1c1-474f-a8c9-4210e37f7877</wsa:MessageID>
    <wsa:ReplyTo>
      <wsa:Address>http://Business456.com/clientA</wsa:Address>
    </wsa:ReplyTo>
    <wsa:To s:mustUnderstand="1">http://BusinessABC.com/serviceA</wsa:To>
  </s:Header>
  <s:Body>
    <wsrm:CloseSequence>
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
      <wsrm:LastMsgNumber>30</wsrm:LastMsgNumber>
    </wsrm:CloseSequence>
  </s:Body>
</s:Envelope>
```

Mensaje de ejemplo `CloseSequenceResponse` :

```xml
<s:Envelope>
  <s:Header>
    <wsrm:SequenceAcknowledgement>
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
      <wsrm:AcknowledgementRange Lower="1" Upper="30"></wsrm:AcknowledgementRange>
      <wsrm:Final></wsrm:Final>
      <netrm:BufferRemaining>8</netrm:BufferRemaining>
    </wsrm:SequenceAcknowledgement>
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/CloseSequenceResponse</wsa:Action>
    <wsa:RelatesTo>urn:uuid:6ce1d4c3-e1c1-474f-a8c9-4210e37f7877</wsa:RelatesTo>
    <wsa:To s:mustUnderstand="1">http://Business456.com/clientA</wsa:To>
  </s:Header>
  <s:Body>
    <wsrm:CloseSequenceResponse>
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
    </wsrm:CloseSequenceResponse>
  </s:Body>
</s:Envelope>
```

### <a name="sequence-termination"></a>Finalización de secuencia

WCF usa principalmente el `TerminateSequence/TerminateSequenceResponse` Protocolo de enlace después de completar el `CloseSequence/CloseSequenceResponse` Protocolo de enlace. El destino de la mensajería de confianza de WCF no inicia la terminación y el origen de la mensajería de confianza no admite una terminación iniciada por el destino de la mensajería de confianza. Se aplican las siguientes restricciones:

- B1301: el iniciador de WCF solo envía el `TerminateSequence` mensaje después de la finalización correcta del `CloseSequence/CloseSequenceResponse` Protocolo de enlace.

- R1302: WCF valida que el `LastMsgNumber` elemento es coherente en todos los `CloseSequence` `TerminateSequence` mensajes y para una secuencia determinada. Esto significa que `LastMsgNumber` no está presente en todos los mensajes `CloseSequence` y `TerminateSequence`, o está presente y es idéntico en todos los mensajes `CloseSequence` y `TerminateSequence`.

- B1303: al recibir un mensaje `TerminateSequence` después del protocolo de enlace `CloseSequence/CloseSequenceResponse`, el destino de la mensajería de confianza responde con un mensaje `TerminateSequenceResponse`. Puesto que el origen de la mensajería de confianza recibe la confirmación definitiva antes de enviar el mensaje `TerminateSequence`, el destino de la mensajería de confianza sabe sin duda que finaliza la secuencia y reclama recursos inmediatamente.

- B1304: al recibir un `TerminateSequence` mensaje antes del `CloseSequence/CloseSequenceResponse` Protocolo de enlace, el destino de la mensajería de confianza de WCF responde con un `TerminateSequenceResponse` mensaje. Si el destino de la mensajería de confianza determina que no hay incoherencias en la secuencia, el destino de la mensajería de confianza espera durante un tiempo especificado por el destino de la aplicación antes de reclamar recursos, para permitir al cliente que reciba la confirmación final. De lo contrario, el destino de la mensajería de confianza reclama recursos inmediatamente e indica al destino de la aplicación que la secuencia finaliza de manera dudosa iniciando el evento `Faulted`.

Ejemplo de mensaje `TerminateSequence`.

```xml
<s:Envelope>
  <s:Header>
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/TerminateSequence</wsa:Action>
    <wsa:MessageID>urn:uuid:3597a398-4f3c-40f4-9335-8f1515572fdf</wsa:MessageID>
    <wsa:ReplyTo>
      <wsa:Address>http://Business456.com/clientA</wsa:Address>
    </wsa:ReplyTo>
    <wsa:To s:mustUnderstand="1">http://BusinessABC.com/serviceA</wsa:To>
  </s:Header>
  <s:Body>
    <wsrm:TerminateSequence>
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
      <wsrm:LastMsgNumber>30</wsrm:LastMsgNumber>
      </wsrm:TerminateSequence>
  </s:Body>
</s:Envelope>
```

Mensaje de ejemplo `TerminateSequenceResponse` :

```xml
<s:Envelope>
  <s:Header>
    <wsrm:SequenceAcknowledgement>
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
      <wsrm:AcknowledgementRange Lower="1" Upper="30"></wsrm:AcknowledgementRange>
      <wsrm:Final></wsrm:Final>
      <netrm:BufferRemaining>8</netrm:BufferRemaining>
    </wsrm:SequenceAcknowledgement>
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/TerminateSequenceResponse</wsa:Action>
    <wsa:RelatesTo>urn:uuid:3597a398-4f3c-40f4-9335-8f1515572fdf</wsa:RelatesTo>
    <wsa:To s:mustUnderstand="1">://Business456.com/clientA</wsa:To>
  </s:Header>
  <s:Body>
    <wsrm:TerminateSequenceResponse>
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
    </wsrm:TerminateSequenceResponse>
  </s:Body>
</s:Envelope>
```

### <a name="sequences"></a>Secuencias

A continuación, se muestra una lista de restricciones que se aplican a las secuencias:

- B1401: WCF genera y obtiene acceso a los números de secuencia que no son mayores que el `xs:long` valor inclusivo máximo de 9223372036854775807.

Ejemplo de encabezado `Sequence`.

```xml
<wsrm:Sequence s:mustUnderstand="1">
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
  <wsrm:MessageNumber>1</wsrm:MessageNumber>
</wsrm:Sequence>
```

### <a name="request-acknowledgement"></a>Solicitar confirmación

WCF usa el `AckRequested` encabezado como un mecanismo Keep-Alive.

Ejemplo de encabezado `AckRequested`.

```xml
<wsrm:AckRequested>
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
</wsrm:AckRequested>
```

### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement

WCF usa un mecanismo de "reutilizable" para las confirmaciones de secuencias proporcionadas en WS-Reliable mensajería. Se aplican las siguientes restricciones:

- R1601: cuando dos secuencias inversas se establecen utilizando el `Offer` mecanismo, el `SequenceAcknowledgement` encabezado puede estar incluido en cualquier mensaje de aplicación transmitido al destinatario previsto. El extremo remoto debe poder tener acceso a un encabezado `SequenceAcknowledgement` superpuesto.

- B1602: WCF no genera `SequenceAcknowledgement` encabezados que contengan `Nack` elementos. WCF valida que cada `Nack` elemento contiene un número de secuencia, pero de lo contrario omite el `Nack` elemento y el valor.

 Ejemplo de encabezado `SequenceAcknowledgement`.

```xml
<wsrm:SequenceAcknowledgement>
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
  <wsrm:AcknowledgementRange Lower="1" Upper="1"></wsrm:AcknowledgementRange>
</wsrm:SequenceAcknowledgement>
```

### <a name="ws-reliablemessaging-faults"></a>Errores de WS-ReliableMessaging

A continuación se muestra una lista de restricciones que se aplican a la implementación de WCF de WS-ReliableMessaging errores. Se aplican las siguientes restricciones:

- B1701: WCF no genera `MessageNumberRollover` errores.

- B1702: sobre SOAP 1,2, cuando el extremo de servicio alcanza su límite de conexiones y no puede procesar nuevas conexiones, WCF genera un `CreateSequenceRefused` subcódigo de error anidado, `netrm:ConnectionLimitReached` , como se muestra en el ejemplo siguiente.

```xml
<s:Envelope>
  <s:Header>
    <wsa:Action>http://docs.oasis-open.org/ws-rx/wsrm/200702/fault</wsa:Action>
  </s:Header>
  <s:Body>
    <s:Fault>
      <s:Code>
        <s:Value>s:Receiver</s:Value>
        <s:Subcode>
          <s:Value>wsrm:CreateSequenceRefused</s:Value>
          <s:Subcode>
            <s:Value>netrm:ConnectionLimitReached</s:Value>
          </s:Subcode>
        </s:Subcode>
      </s:Code>
      <s:Reason>
        <s:Text xml:lang="en">Server 'http://BusinessABC.com/serviceA' is too busy to process this request. Try again later.</s:Text>
      </s:Reason>
    </s:Fault>
  </s:Body>
</s:Envelope>
```

### <a name="ws-addressing-faults"></a>Errores WS-Addressing

Dado que WS-ReliableMessaging usa WS-Addressing, la implementación de WS-ReliableMessaging de WCF puede generar y transmitir errores de WS-Addressing. En esta sección se tratan los errores de WS-Addressing que WCF genera y transmite explícitamente en el nivel de WS-ReliableMessaging:

- B1801: WCF genera y transmite el `Message Addressing Header Required` error cuando se cumple una de las siguientes condiciones:

  - A un mensaje `CreateSequence`, `CloseSequence`, o `TerminateSequence` le falta un encabezado `MessageId`.

  - A un mensaje `CreateSequence`, `CloseSequence`, o `TerminateSequence` le falta un encabezado `ReplyTo`.

  - A un mensaje `CreateSequenceResponse`, `CloseSequenceResponse`, o `TerminateSequenceResponse` le falta un encabezado `RelatesTo`.

- B1802: WCF genera y transmite el `Endpoint Unavailable` error para indicar que no hay ningún extremo escuchando que pueda procesar la secuencia en función del examen de los encabezados de direccionamiento en el `CreateSequence` mensaje.

## <a name="protocol-composition"></a>Composición de protocolos

### <a name="composition-with-ws-addressing"></a>Composición con WS-Addressing

WCF admite dos versiones de WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] y las recomendaciones de W3C WS-Addressing 1,0 [WS-ADDR-CORE] y [WS-ADDR-SOAP].

Aunque la especificación de WS-ReliableMessaging solo menciona WS-Addressing 2004/08, no restringe la versión de WS-Addressing que se ha de utilizar. A continuación se muestra una lista de restricciones que se aplican a WCF:

- R2101: WS-Addressing 2004/08 y WS-Addressing 1.0 se pueden utilizar con la mensajería de confianza de WS.

- R2102: se debe utilizar una única versión de WS-Addressing a lo largo de una secuencia de WS-ReliableMessaging determinada o un par de secuencias inversas correlacionadas mediante el mecanismo `Offer`.

### <a name="composition-with-soap"></a>Composición con SOAP

WCF admite el uso de SOAP 1,1 y SOAP 1,2 con WS-Reliable mensajería.

### <a name="composition-with-ws-security-and-ws-secureconversation"></a>Composición con WS-Security y WS-SecureConversation

WCF proporciona protección para WS-ReliableMessaging secuencias mediante el transporte seguro (HTTPS), la composición con WS-Security y la composición con WS-Secure Conversation. Los protocolos WS-ReliableMessaging 1.1, WS-Security 1.1 y WS-Secure Conversation 1.3 deberían utilizarse conjuntamente. A continuación se muestra una lista de restricciones que se aplican a WCF:

- R2301: para proteger la integridad de una secuencia de WS-ReliableMessaging además de la integridad y confidencialidad de los mensajes individuales, WCF requiere que se use WS-Secure conversación.

- R2302:una sesión de WS-Secure Conversation se debe establecer antes de establecer las secuencias de WS-ReliableMessaging.

- R2303: si la duración de la secuencia de WS-ReliableMessaging supera la duración de la sesión de WS-Secure Conversation, el `SecurityContextToken` establecido mediante WS-Secure Conversation se debe renovar utilizando el enlace de renovación de WS-Secure Conversation correspondiente.

- B2304:La secuencia de WS-ReliableMessaging o un par de secuencias inversas correlacionadas siempre se enlazan a una única sesión de WS-SecureConversation.

- R2305: cuando se crea con WS-Secure Conversation, el respondedor de WCF requiere que el `CreateSequence` mensaje contenga el `wsse:SecurityTokenReference` elemento y el `wsrm:UsesSequenceSTR` encabezado.

 Ejemplo de encabezado `UsesSequenceSTR`.

```xml
<wsrm:UsesSequenceSTR></wsrm:UsesSequenceSTR>
```

### <a name="composition-with-ssltls-sessions"></a>Composición con sesiones de SSL/TLS

WCF no admite la composición con sesiones SSL/TLS:

- B2401: WCF no genera el `wsrm:UsesSequenceSSL` encabezado.

- R2402: un iniciador de mensajería de confianza no debe enviar un `CreateSequence` mensaje con un `wsrm:UsesSequenceSSL` encabezado a un respondedor de WCF.

### <a name="composition-with-ws-policy"></a>Composición con WS-Policy

WCF admite dos versiones de WS-Policy: WS-Policy 1,2 y WS-Policy 1,5.

## <a name="ws-reliablemessaging-ws-policy-assertion"></a>Aserción de WS-Policy de WS-ReliableMessaging 

WCF usa WS-ReliableMessaging WS-Policy aserción `wsrm:RMAssertion` para describir las capacidades de los extremos. A continuación se muestra una lista de restricciones que se aplican a WCF:

- B3001: WCF asocia `wsrmn:RMAssertion` WS-Policy aserción a `wsdl:binding` los elementos. WCF admite datos adjuntos `wsdl:binding` a `wsdl:port` elementos y.

- B3002: WCF nunca genera la `wsp:Optional` etiqueta.

- B3003: al obtener acceso a la `wsrmp:RMAssertion` aserción de WS-Policy, WCF omite la `wsp:Optional` etiqueta y trata la Directiva de WS-RM como obligatoria.

- R3004: dado que WCF no se compone con sesiones SSL/TLS, WCF no acepta la Directiva que especifica `wsrmp:SequenceTransportSecurity` .

- B3005: WCF siempre genera el `wsrmp:DeliveryAssurance` elemento.

- B3006: WCF siempre especifica la `wsrmp:ExactlyOnce` garantía de entrega.

- B3007: WCF genera y Lee las siguientes propiedades de la aserción WS-ReliableMessaging y proporciona control sobre ellas en WCF `ReliableSessionBindingElement` :

  - `netrmp:InactivityTimeout`

  - `netrmp:AcknowledgementInterval`

  Ejemplo de `RMAssertion`.

  ```xml
  <wsrmp:RMAssertion>
    <wsp:Policy>
      <wsrmp:SequenceSTR/>
      <wsrmp:DeliveryAssurance>
        <wsp:Policy>
          <wsrmp:ExactlyOnce/>
          <wsrmp:InOrder/>
        </wsp:Policy>
      </wsrmp:DeliveryAssurance>
    </wsp:Policy>
    <netrmp:InactivityTimeout Milliseconds="600000"/>
    <netrmp:AcknowledgementInterval Milliseconds="200"/>
  </wsrmp:RMAssertion>
  ```

## <a name="flow-control-ws-reliablemessaging-extension"></a>Extensión de WS-ReliableMessaging de control de flujo

WCF usa la extensibilidad de WS-ReliableMessaging para proporcionar un control adicional más estrecho opcional sobre el flujo de mensajes de secuencia.

El control de flujo se habilita estableciendo la <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> propiedad en `true` . A continuación se muestra una lista de restricciones que se aplican a WCF:

- B4001: cuando está habilitado el control de flujo de la mensajería de confianza, WCF genera un `netrm:BufferRemaining` elemento en la extensibilidad de elementos del `SequenceAcknowledgement` encabezado, tal y como se muestra en el ejemplo siguiente.

  ```xml
  <wsrm:SequenceAcknowledgement>
    <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
    <wsrm:AcknowledgementRange Upper="1" Lower="1"/>
    <netrm:BufferRemaining>8</netrm:BufferRemaining>
  </wsrm:SequenceAcknowledgement>
  ```

- B4002: incluso cuando está habilitado el control de flujo de mensajería de confianza, WCF no requiere un `netrm:BufferRemaining` elemento en el `SequenceAcknowledgement` encabezado.

- B4003: el destino de la mensajería confiable de WCF usa `netrm:BufferRemaining` para indicar cuántos mensajes nuevos puede almacenar en búfer.

- B4004: cuando está habilitado el control de flujo de la mensajería de confianza, el origen de mensajería confiable de WCF usa el valor de `netrm:BufferRemaining` para limitar la transmisión de mensajes.

- B4005: WCF genera `netrm:BufferRemaining` valores enteros entre 0 y 4096, ambos inclusive, y Lee valores enteros entre 0 y `xs:int` el `maxInclusive` valor 214748364, ambos inclusive.

## <a name="message-exchange-patterns"></a>Modelos de intercambio de mensajes

En esta sección se describe el comportamiento de WCF cuando WS-ReliableMessaging se usa para diferentes patrones de intercambio de mensajes. Para cada patrón de intercambio de mensajes, se consideran los dos escenarios de implementación siguientes:

- Iniciador no direccionable: el iniciador está tras un firewall; el respondedor solo puede entregar mensajes al iniciador mediante respuestas HTTP.

- Iniciador direccionable: el iniciador y el respondedor pueden enviar solicitudes HTTP; en otras palabras, se pueden establecer dos conexiones HTTP inversas.

### <a name="one-way-non-addressable-initiator"></a>Iniciador unidireccional no direccionable

#### <a name="binding"></a>Enlace

WCF proporciona un patrón de intercambio de mensajes unidireccional utilizando una secuencia sobre un canal HTTP. WCF usa solicitudes HTTP para transmitir todos los mensajes desde el iniciador al respondedor y respuestas HTTP para transmitir todos los mensajes del respondedor al iniciador.

#### <a name="createsequence-exchange"></a>Intercambio de CreateSequence

El iniciador de WCF transmite un `CreateSequence` mensaje sin `Offer` elemento en una solicitud HTTP y espera el `CreateSequenceResponse` mensaje en la respuesta http. El respondedor de WCF crea una secuencia y transmite el `CreateSequenceResponse` mensaje sin ningún `Accept` elemento en la respuesta http.

#### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement

El iniciador de WCF procesa las confirmaciones en la respuesta de todos los mensajes excepto el `CreateSequence` mensaje y los mensajes de error. El respondedor de WCF siempre transmite una confirmación independiente en la respuesta HTTP a todas las secuencias y `AckRequested` mensajes.

#### <a name="closesequence-exchange"></a>Intercambio de CloseSequence

El iniciador de WCF transmite un `CloseSequence` mensaje en una solicitud HTTP y espera el `CreateSequenceResponse` mensaje en la respuesta http. El respondedor de WCF transmite el `CloseSequenceResponse` mensaje en la respuesta http.

#### <a name="terminatesequence-exchange"></a>Intercambio de TerminateSequence

El iniciador de WCF transmite un `TerminateSequence` mensaje en una solicitud HTTP y espera el `TerminateSequenceResponse` mensaje en la respuesta http. El respondedor de WCF transmite el `TerminateSequenceResponse` mensaje en la respuesta http.

### <a name="one-way-addressable-initiator"></a>Iniciador unidireccional y direccionable

#### <a name="binding"></a>Enlace

WCF proporciona un patrón de intercambio de mensajes unidireccional utilizando una secuencia sobre un canal HTTP entrante y otro saliente. WCF usa las solicitudes HTTP para transmitir todos los mensajes. Todas las respuestas HTTP tienen un cuerpo vacío y código de estado HTTP 202.

#### <a name="createsequence-exchange"></a>Intercambio de CreateSequence

El iniciador de WCF transmite un `CreateSequence` mensaje sin `Offer` elemento en una solicitud HTTP. El respondedor de WCF crea una secuencia y transmite el `CreateSequenceResponse` mensaje sin ningún `Accept` elemento en una solicitud HTTP.

### <a name="duplex-addressable-initiator"></a>Iniciador dúplex y direccionable

#### <a name="binding"></a>Enlace

WCF proporciona un patrón de intercambio de mensajes bidireccional totalmente asincrónico que usa dos secuencias sobre un canal HTTP entrante y otro saliente. Este patrón de intercambio de mensajes se puede mezclar con el patrón de intercambio de mensajes del iniciador de `Request/Reply`, `Addressable` de una manera limitada. WCF usa solicitudes HTTP para transmitir todos los mensajes. Todas las respuestas HTTP tienen un cuerpo vacío y código de estado HTTP 202.

#### <a name="createsequence-exchange"></a>Intercambio de CreateSequence

El iniciador de WCF transmite un `CreateSequence` mensaje con un `Offer` elemento en una solicitud HTTP. El respondedor de WCF garantiza que `CreateSequence` tiene un `Offer` elemento y, a continuación, crea una secuencia y transmite el `CreateSequenceResponse` mensaje con un `Accept` elemento.

#### <a name="sequence-lifetime"></a>Duración de la secuencia

WCF trata las dos secuencias como una sesión totalmente dúplex.

Tras generar un error que genera un error en una secuencia, WCF espera que el punto de conexión remoto genere un error en ambas secuencias. Al leer un error que genera un error en una secuencia, WCF genera un error en ambas secuencias.

WCF puede cerrar su secuencia de salida y continuar procesando los mensajes en la secuencia de entrada. Por el contrario, WCF puede procesar el cierre de la secuencia de entrada y continuar enviando mensajes en su secuencia de salida.

### <a name="request-reply-and-one-way-non-addressable-initiator"></a>Iniciador de solicitud-respuesta unidireccional y no direccionable

#### <a name="binding"></a>Enlace

WCF proporciona un modelo de intercambio de mensajes de solicitud-respuesta unidireccional que usa dos secuencias sobre un canal HTTP. WCF usa solicitudes HTTP para transmitir todos los mensajes desde el iniciador al respondedor y respuestas HTTP para transmitir todos los mensajes del respondedor al iniciador.

#### <a name="createsequence-exchange"></a>Intercambio de CreateSequence

El iniciador de WCF transmite un `CreateSequence` mensaje con un `Offer` elemento en una solicitud HTTP y espera el `CreateSequenceResponse` mensaje en la respuesta http. El respondedor de WCF crea una secuencia y transmite el `CreateSequenceResponse` mensaje con un `Accept` elemento en la respuesta http.

#### <a name="one-way-message"></a>Mensaje unidireccional

Para completar correctamente un intercambio de mensajes unidireccional, el iniciador de WCF transmite un mensaje de secuencia de solicitud en la solicitud HTTP y recibe un `SequenceAcknowledgement` mensaje independiente en la respuesta http. La `SequenceAcknowledgement` debe confirmar el mensaje transmitido.

El respondedor de WCF puede responder a la solicitud con una confirmación, un error o una respuesta con un cuerpo vacío y un código de Estado HTTP 202.

#### <a name="two-way-messages"></a>Mensajes bidireccionales

Para completar correctamente un protocolo de intercambio de mensajes bidireccional, el iniciador de WCF transmite un mensaje de secuencia de solicitud en la solicitud HTTP y recibe un mensaje de secuencia de respuesta en la respuesta HTTP. La respuesta debe llevar una `SequenceAcknowledgement` que confirme que se ha transmitido el mensaje de secuencia de solicitud.

El respondedor de WCF puede responder a la solicitud con una respuesta de la aplicación, un error o una respuesta con un cuerpo vacío y un código de Estado HTTP 202.

Debido a la presencia de mensajes unidireccionales y al control de tiempo de las respuestas de la aplicación, el número de secuencia del mensaje de secuencia de solicitud y el número de secuencia del mensaje de respuesta no tienen ninguna correlación.

#### <a name="retrying-replies"></a>Reintento de respuestas

WCF se basa en la correlación de solicitud-respuesta HTTP para la correlación del Protocolo de intercambio de mensajes bidireccional. Debido a esto, el iniciador de WCF no deja de reintentar un mensaje de secuencia de solicitud cuando se confirma el mensaje de secuencia de solicitud, sino cuando la respuesta HTTP lleva una, una respuesta de la `SequenceAcknowledgement` aplicación o un error. El respondedor de WCF reintenta las respuestas en la respuesta HTTP de la solicitud a la que se correlaciona la respuesta.

#### <a name="closesequence-exchange"></a>Intercambio de CloseSequence

Después de recibir todos los mensajes de secuencia de respuesta y las confirmaciones de todos los mensajes de secuencia de solicitud unidireccional, el iniciador de WCF transmite un `CloseSequence` mensaje para la secuencia de solicitud en una solicitud HTTP y espera la `CloseSequenceResponse` en la respuesta http.

Al cerrar implícitamente la secuencia de la solicitud, se cierra la secuencia de la respuesta. Esto significa que el iniciador de WCF incluye el final de la secuencia `SequenceAcknowledgement` de respuesta en el `CloseSequence` mensaje y la secuencia de respuesta no tiene un `CloseSequence` intercambio.

El respondedor de WCF garantiza que todas las respuestas se reconocen y transmite el `CloseSequenceResponse` mensaje en la respuesta http.

#### <a name="terminatesequence-exchange"></a>Intercambio de TerminateSequence

Después de recibir el `CloseSequenceResponse` mensaje, el iniciador de WCF transmite un `TerminateSequence` mensaje para la secuencia de solicitud en una solicitud HTTP y espera la `TerminateSequenceResponse` en la respuesta http.

Al igual que en el intercambio de `CloseSequence`, al finalizar la secuencia de solicitud, se finaliza la secuencia de respuesta. Esto significa que el iniciador de WCF incluye el final de la secuencia `SequenceAcknowledgement` de respuesta en el `TerminateSequence` mensaje y la secuencia de respuesta no tiene un `TerminateSequence` intercambio.

El respondedor de WCF transmite el `TerminateSequenceResponse` mensaje en la respuesta http.

### <a name="requestreply-addressable-initiator"></a>Iniciador direccionable de solicitud-respuesta

#### <a name="binding"></a>Enlace

WCF proporciona un patrón de intercambio de mensajes de solicitud-respuesta con dos secuencias sobre un canal HTTP entrante y uno saliente. Este patrón de intercambio de mensajes se puede mezclar con el patrón de intercambio de mensajes del iniciador de `Duplex, Addressable` de una manera limitada. WCF usa las solicitudes HTTP para transmitir todos los mensajes. Todas las respuestas HTTP tienen un cuerpo vacío y código de estado HTTP 202.

#### <a name="createsequence-exchange"></a>Intercambio de CreateSequence

El iniciador de WCF transmite un `CreateSequence` mensaje con un `Offer` elemento en una solicitud HTTP. El respondedor de WCF garantiza que `CreateSequence` tiene un `Offer` elemento, a continuación, crea una secuencia y transmite el `CreateSequenceResponse` mensaje con un `Accept` elemento.

#### <a name="requestreply-correlation"></a>Correlación entre solicitud y respuesta

Lo siguiente se aplica a todas las solicitudes y respuestas correlacionadas:

- WCF garantiza que todos los mensajes de solicitud de aplicación llevan una `ReplyTo` referencia de extremo y un `MessageId` .

- WCF aplica la referencia de punto de conexión local como cada mensaje de solicitud de aplicación `ReplyTo` . La referencia del punto de conexión local es la `CreateSequence` del mensaje `ReplyTo` para el iniciador y la `CreateSequence` del mensaje `To` para el respondedor.

- WCF garantiza que los mensajes de solicitud entrantes lleven un `MessageId` y un `ReplyTo` .

- WCF garantiza que el `ReplyTo` URI de la referencia de extremo de todos los mensajes de solicitud de aplicación coincide con la referencia de punto de conexión local tal y como se definió anteriormente.

- WCF garantiza que todas las respuestas llevan los `RelatesTo` encabezados y correctos `To` después de `wsa` las reglas de correlación de solicitud/respuesta.
