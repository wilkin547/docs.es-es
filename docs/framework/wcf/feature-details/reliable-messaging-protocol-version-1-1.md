---
title: "Protocolo de mensajer&#237;a confiable versi&#243;n 1.1 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0da47b82-f8eb-42da-8bfe-e56ce7ba6f59
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# Protocolo de mensajer&#237;a confiable versi&#243;n 1.1
Este tema cubre los detalles de implementación de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] para el protocolo de febrero de 2007 WS\-ReliableMessaging \(versión 1.1\) necesario para la interoperación mediante el transporte HTTP.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sigue la especificación WS\-ReliableMessaging con las restricciones y clarificaciones explicadas en este tema.Tenga en cuenta que la versión 1.1 del protocolo WS\-ReliableMessaging se implementa a partir de [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)].  
  
 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> implementa el protocolo WS\-ReliableMessaging de febrero de 2007 en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 Para su comodidad, el tema utiliza las siguientes funciones:  
  
-   Iniciador: el cliente que inicia la creación de la secuencia de mensajes WS\-Reliable.  
  
-   Respondedor: el servicio que recibe las solicitudes del iniciador.  
  
 En este documento, se utilizan los prefijos y espacios de nombres de la tabla siguiente.  
  
|||  
|-|-|  
|Prefijo|Espacio de nombres|  
|wsrm|http:\/\/docs.oasis\-open.org\/ws\-rx\/wsrm\/200702|  
|netrm|http:\/\/schemas.microsoft.com\/ws\/2006\/05\/rm|  
|s|http:\/\/www.w3.org\/2003\/05\/soap\-envelope|  
|wsa|http:\/\/schemas.xmlsoap.org\/ws\/2005\/08\/addressing|  
|wsse|http:\/\/docs.oasis\-open.org\/wss\/2004\/01\/oasis\-200401\-wssecurity\-secext\-1.0.xsd|  
|wsrmp|http:\/\/docs.oasis\-open.org\/ws\-rx\/wsrmp\/200702|  
|netrmp|http:\/\/schemas.microsoft.com\/ws\-rx\/wsrmp\/200702|  
|wsp|\(Directiva WS\-Policy 1.2 o WS\-Policy 1.5\)|  
  
## Mensajería  
  
### Creación de secuencias  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementa mensajes `CreateSequence` y `CreateSequenceResponse` para establecer una secuencia de mensajería de confianza.Las siguientes restricciones son aplicables:  
  
-   B1101: el iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza la misma referencia de extremo que `ReplyTo`, `AcksTo` y `Offer/Endpoint` del mensaje `CreateSequence`.  
  
-   R1102: las referencias de extremo `AcksTo`, `ReplyTo` y `Offer/Endpoint` en el mensaje `CreateSequence` deben tener valores de dirección con representaciones de cadena idénticas, de tal modo que coincidan por octetos.  
  
    -   El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] comprueba que la parte del URI de las referencias de extremo `AcksTo`, `ReplyTo` y `Endpoint` sean idénticas antes de crear una secuencia.  
  
-   R1103: las referencias de extremo `AcksTo`, `ReplyTo` y `Offer/Endpoint` en el mensaje `CreateSequence` deberían tener el mismo conjunto de parámetros de referencia.  
  
    -   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no exige, pero supone que los parámetros de las referencias de extremo `AcksTo`, `ReplyTo` y `Offer/Endpoint` en `CreateSequence` son idénticas y utiliza los parámetros de referencia de la referencia de extremo `ReplyTo` para las confirmaciones y los mensajes de secuencia inversa.  
  
-   B1104: el iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no genera el elemento opcional `Expires` o `Offer/Expires` en el mensaje `CreateSequence`.  
  
-   B1105: al tener acceso al mensaje `CreateSequence`, el respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza el valor `Expires` del elemento `CreateSequence` como el valor `Expires` del elemento `CreateSequenceResponse`.De lo contrario, el respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] lee y pasa por alto los valores `Expires` y `Offer/Expires`.  
  
-   B1106: al tener acceso al mensaje `CreateSequenceResponse`, el iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] lee el valor opcional `Expires`, pero no lo utiliza.  
  
-   B1107: el iniciador y respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] siempre generan el elemento opcional `IncompleteSequenceBehavior` en los elementos `CreateSequence/Offer` y `CreateSequenceResponse`.  
  
-   B1108: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] solo utiliza los valores `DiscardFollowingFirstGap` y `NoDiscard` en el elemento `IncompleteSequenceBehavior`.  
  
    -   WS\-ReliableMessaging utiliza el mecanismo `Offer` para establecer las dos secuencias correlacionadas inversas que forman una sesión.  
  
-   B1109: si `CreateSequence` contiene un elemento `Offer`, el respondedor unidireccional de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] rechaza la secuencia proporcionada respondiendo con una `CreateSequenceResponse` sin un elemento `Accept`.  
  
-   B1110: si un respondedor de mensajería de confianza rechaza la secuencia proporcionada, el iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] produce un error en la secuencia recientemente establecida.  
  
-   B1111: si `CreateSequence` no contiene un elemento `Offer`, el respondedor bidireccional de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] rechaza la secuencia proporcionada respondiendo con un error de `CreateSequenceRefused`.  
  
-   R1112: cuando dos secuencias inversas se establecen utilizando el mecanismo `Offer`, la propiedad `[address]` de la referencia de extremo `CreateSequenceResponse/Accept/AcksTo` debe coincidir con el URI de destino del mensaje `CreateSequence` byte a byte.  
  
-   R1113: cuando dos secuencias inversas se establecen utilizando el mecanismo `Offer`, todos los mensajes en ambas secuencias que fluyen desde el iniciador hasta el respondedor se deben enviar a la misma referencia de extremo.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza WS\-ReliableMessaging para establecer sesiones confiables entre el iniciador y el respondedor.La implementación de WS\-ReliableMessaging de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona una sesión confiable para modelos de mensajería dúplex completa y de solicitud\-respuesta unidireccional.El mecanismo `Offer` de WS\-ReliableMessaging en `CreateSequence` y `CreateSequenceResponse` le permite establecer dos secuencias inversas correlacionadas y proporciona un protocolo de sesión que es apto para todos los extremos de mensajes.Dado que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona una garantía de seguridad para este tipo de sesiones, incluyendo protección de un extremo a otro para la integridad de la sesión, es práctico asegurar que los mensajes dirigidos a la misma parte lleguen al mismo destino.Esto también permite el “apoyo a caballo” de confirmaciones de secuencias en mensajes de aplicaciones.Por consiguiente, las restricciones R1102, R1112 y R1113 se aplican a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 Ejemplo de mensaje `CreateSequence`.  
  
```  
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
  
```  
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
  
### Cierre de una secuencia  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza los mensajes `CloseSequenceResponse` y `CloseSequence` para llevar a cabo un cierre iniciado por el origen de la mensajería de confianza.El destino de la mensajería de confianza de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no inicia el cierre y el origen de la mensajería de confianza de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no admite un cierre iniciado por el destino de la mensajería de confianza.Las siguientes restricciones son aplicables:  
  
-   B1201: el origen de la mensajería de confianza de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] siempre envía un mensaje `CloseSequence` para cerrar la secuencia.  
  
-   B1202: el origen de la mensajería de confianza espera la confirmación del intervalo completo de mensajes de secuencia antes de enviar el mensaje `CloseSequence`.  
  
-   B1203: el origen de la mensajería de confianza siempre incluye el elemento opcional `LastMsgNumber`, a menos que la secuencia no contenga mensajes.  
  
-   R1204: el destino de la mensajería de confianza no debe iniciar el cierre mediante el envío de un mensaje `CloseSequence`.  
  
-   B1205: tras recibir un mensaje `CloseSequence`, el origen de la mensajería de confianza de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] considera la secuencia incompleta y envía un error.  
  
 Ejemplo de mensaje `CloseSequence`.  
  
```  
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
Example CloseSequenceResponse message:  
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
  
### Finalización de secuencia  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza principalmente el protocolo de enlace `TerminateSequence/TerminateSequenceResponse` después de completar el protocolo de enlace `CloseSequence/CloseSequenceResponse`.El destino de la mensajería de confianza de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no inicia la finalización y el origen de la mensajería de confianza no admite una finalización de la mensajería de confianza iniciada por el destino.Las siguientes restricciones son aplicables:  
  
-   B1301: el iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] solo envía el mensaje `TerminateSequence` después de la finalización correcta del protocolo de enlace `CloseSequence/CloseSequenceResponse`.  
  
-   R1302: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] valida que el elemento `LastMsgNumber` sea coherente en todos los mensajes `TerminateSequence` y `CloseSequence` para una secuencia determinada.Esto significa que `LastMsgNumber` no está presente en todos los mensajes `TerminateSequence` y `CloseSequence`, o está presente y es idéntico en todos los mensajes `TerminateSequence` y `CloseSequence`.  
  
-   B1303: al recibir un mensaje `TerminateSequence` después del protocolo de enlace `CloseSequence/CloseSequenceResponse`, el destino de la mensajería de confianza responde con un mensaje `TerminateSequenceResponse`.Puesto que el origen de la mensajería de confianza recibe la confirmación definitiva antes de enviar el mensaje `TerminateSequence`, el destino de la mensajería de confianza sabe sin duda que finaliza la secuencia y reclama recursos inmediatamente.  
  
-   B1304: al recibir un mensaje `TerminateSequence` antes del protocolo de enlace `CloseSequence/CloseSequenceResponse`, el destino de la mensajería de confianza de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] responde con un mensaje `TerminateSequenceResponse`.Si el destino de la mensajería de confianza determina que no hay incoherencias en la secuencia, el destino de la mensajería de confianza espera durante un tiempo especificado por el destino de la aplicación antes de reclamar recursos, para permitir al cliente que reciba la confirmación final.De lo contrario, el destino de la mensajería de confianza reclama recursos inmediatamente e indica al destino de la aplicación que la secuencia finaliza de manera dudosa iniciando el evento `Faulted`.  
  
 Ejemplo de mensaje `TerminateSequence`.  
  
```  
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
Example TerminateSequenceResponse message:  
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
  
### Secuencias  
 A continuación, se muestra una lista de restricciones que se aplican a las secuencias:  
  
-   B1401:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera y tiene acceso a números de secuencia no superiores al valor máximo incluido de `xs:long`, 9223372036854775807.  
  
 Ejemplo de encabezado `Sequence`.  
  
```  
<wsrm:Sequence s:mustUnderstand="1">  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:MessageNumber>1</wsrm:MessageNumber>  
</wsrm:Sequence>  
```  
  
### Solicitar confirmación  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza el encabezado `AckRequested` como un mecanismo de supervivencia.  
  
 Ejemplo de encabezado `AckRequested`.  
  
```  
<wsrm:AckRequested>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### SequenceAcknowledgement  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza un mecanismo de "apoyo a caballo" para las confirmaciones de secuencias proporcionadas en la mensajería de confianza de WS.Las siguientes restricciones son aplicables:  
  
-   R1601: cuando dos secuencias inversas se establecen utilizando el mecanismo `Offer`, el encabezado `SequenceAcknowledgement` puede estar incluido en cualquier mensaje de aplicación transmitido al destinatario previsto.El extremo remoto debe poder tener acceso a un encabezado `SequenceAcknowledgement` superpuesto.  
  
-   B1602: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no genera encabezados `SequenceAcknowledgement` que contienen elementos `Nack`.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] valida que cada elemento `Nack` contiene un número de secuencia, pero omite de otra forma el elemento y el valor de `Nack`.  
  
 Ejemplo de encabezado `SequenceAcknowledgement`.  
  
```  
<wsrm:SequenceAcknowledgement>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:AcknowledgementRange Lower="1" Upper="1"></wsrm:AcknowledgementRange>  
</wsrm:SequenceAcknowledgement>  
```  
  
### Errores de WS\-ReliableMessaging  
 A continuación, se muestra una lista de restricciones que se aplican a la implementación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] de errores de WS\-ReliableMessaging.Las siguientes restricciones son aplicables:  
  
-   B1701: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no genera errores `MessageNumberRollover`.  
  
-   B1702: sobre SOAP 1.2, cuando el extremo de servicio alcanza su límite de conexiones y no puede procesar nuevas conexiones, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera un subcódigo de error `CreateSequenceRefused` anidado, `netrm:ConnectionLimitReached`, como se muestra en el siguiente ejemplo.  
  
```  
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
  
### Errores WS\-Addressing  
 Dado que WS\-ReliableMessaging utiliza WS\-Addressing, la implementación de WS\-ReliableMessaging de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] puede generar y transmitir errores de WS\-Addressing.Esta sección cubre los errores de WS\-Addressing que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera explícitamente y transmite en la capa de WS\-ReliableMessaging:  
  
-   B1801: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera y transmite el error `Message Addressing Header Required` cuando una de las siguientes situaciones es verdadera:  
  
    -   A un mensaje `CreateSequence`, `CloseSequence`, o `TerminateSequence` le falta un encabezado `MessageId`.  
  
    -   A un mensaje `CreateSequence`, `CloseSequence`, o `TerminateSequence` le falta un encabezado `ReplyTo`.  
  
    -   A un mensaje `CreateSequenceResponse`, `CloseSequenceResponse`, o `TerminateSequenceResponse` le falta un encabezado `RelatesTo`.  
  
-   B1802::[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera y transmite el error `Endpoint Unavailable` para indicar que no hay ningún extremo a la escucha que pueda procesar la secuencia a partir del examen de los encabezados de direccionamiento del mensaje `CreateSequence`.  
  
## Composición de protocolos  
  
### Composición con WS\-Addressing  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite dos versiones de WS\-Addressing: WS\-Addressing 2004\/08 \[WS\-ADDR\] y las recomendaciones de WS\-Addressing 1.0 de W3C \[WS\-ADDR\-CORE\] y \[WS\-ADDR\-SOAP\].  
  
 Aunque la especificación de WS\-ReliableMessaging solo menciona WS\-Addressing 2004\/08, no restringe la versión de WS\-Addressing que se ha de utilizar.A continuación, se muestra una lista de restricciones que se aplican a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:  
  
-   R2101: WS\-Addressing 2004\/08 y WS\-Addressing 1.0 se pueden utilizar con la mensajería de confianza de WS.  
  
-   R2102: se debe utilizar una única versión de WS\-Addressing a lo largo de una secuencia de WS\-ReliableMessaging determinada o un par de secuencias inversas correlacionadas mediante el mecanismo `Offer`.  
  
### Composición con SOAP  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite el uso de SOAP 1.1 y SOAP 1.2 con la mensajería de confianza de WS.  
  
### Composición con WS\-Security y WS\-SecureConversation  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona protección para secuencias de WS\-ReliableMessaging mediante el transporte seguro \(HTTPS\), la composición con WS\-Security y la composición con WS\-Secure Conversation.Los protocolos WS\-ReliableMessaging 1.1, WS\-Security 1.1 y WS\-Secure Conversation 1.3 deberían utilizarse conjuntamente.A continuación se muestra una lista de restricciones que se aplican a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:  
  
-   R2301: para proteger la integridad de una secuencia de WS\-ReliableMessaging además de la integridad y confidencialidad de los mensajes individuales, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requiere que se utilice WS\-Secure Conversation.  
  
-   R2302:una sesión de WS\-Secure Conversation se debe establecer antes de establecer las secuencias de WS\-ReliableMessaging.  
  
-   R2303: si la duración de la secuencia de WS\-ReliableMessaging supera la duración de la sesión de WS\-Secure Conversation, el `SecurityContextToken` establecido mediante WS\-Secure Conversation se debe renovar utilizando el enlace de renovación de WS\-Secure Conversation correspondiente.  
  
-   B2304:La secuencia de WS\-ReliableMessaging o un par de secuencias inversas correlacionadas siempre se enlazan a una única sesión de WS\-SecureConversation.  
  
-   R2305: cuando se compone con WS\-Secure Conversation, el respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requiere que el mensaje `CreateSequence` contenga el elemento `wsse:SecurityTokenReference` y el encabezado `wsrm:UsesSequenceSTR`.  
  
 Ejemplo de encabezado `UsesSequenceSTR`.  
  
```  
<wsrm:UsesSequenceSTR></wsrm:UsesSequenceSTR>  
```  
  
### Composición con sesiones de SSL\/TLS  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no admite la composición con sesiones de SSL\/TLS:  
  
-   B2401: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no genera el encabezado `wsrm:UsesSequenceSSL`.  
  
-   R2402: un iniciador de la mensajería de confianza no debe enviar un mensaje `CreateSequence` con un encabezado `wsrm:UsesSequenceSSL` a un respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
### Composición con WS\-Policy  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite dos versiones de WS\-Policy: WS\-Policy 1.2 y WS\-Policy 1.5.  
  
## Aserción de WS\-Policy de WS\-ReliableMessaging  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza la aserción de WS\-Policy de WS\-ReliableMessaging `wsrm:RMAssertion` para describir funciones de extremos.A continuación se muestra una lista de restricciones que se aplican a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:  
  
-   B3001: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] adjunta la aserción `wsrmn:RMAssertion` de WS\-Policy Assertion a elementos `wsdl:binding`.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite datos adjuntos para los elementos `wsdl:binding` y `wsdl:port`.  
  
-   B3002: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] nunca genera la etiqueta `wsp:Optional`.  
  
-   B3003: al tener acceso la aserción de WS\-Policy `wsrmp:RMAssertion`, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] omite la etiqueta `wsp:Optional` y trata la directiva WS\-RM como obligatoria.  
  
-   R3004: puesto que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no compone con sesiones de SSL\/TLS, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no acepta ninguna directiva que especifique `wsrmp:SequenceTransportSecurity`.  
  
-   B3005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] siempre genera el elemento `wsrmp:DeliveryAssurance`.  
  
-   B3006: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] siempre especifica la garantía de entrega `wsrmp:ExactlyOnce`.  
  
-   B3007: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera y lee las siguientes propiedades de la aserción de WS\-ReliableMessaging y proporciona control sobre ellas en el elemento `ReliableSessionBindingElement` de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:  
  
    -   `netrmp:InactivityTimeout`  
  
    -   `netrmp:AcknowledgementInterval`  
  
     Ejemplo de `RMAssertion`.  
  
    ```  
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
  
## Extensión de WS\-ReliableMessaging de control de flujo  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza la extensibilidad de WS\-ReliableMessaging para proporcionar un mayor control adicional y opcional sobre el flujo de mensajes de secuencias.  
  
 El control de flujo se habilita estableciendo en `true` la propiedad `boolean``FlowControlEnabled` del `ReliableSessionBindingElement`.A continuación, se muestra una lista de restricciones que se aplican a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:  
  
-   B4001: cuando está habilitado el control de flujo de la mensajería de confianza, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera un elemento `netrm:BufferRemaining` en la extensibilidad de elementos del encabezado `SequenceAcknowledgement`, tal y como se muestra en el siguiente ejemplo.  
  
    ```  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="1" Lower="1"/>             
      <netrm:BufferRemaining>8</netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   B4002: incluso cuando está habilitado el control de flujo de la mensajería de confianza, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no requiere un elemento `netrm:BufferRemaining` en el encabezado `SequenceAcknowledgement`.  
  
-   B4003: el destino de la mensajería de confianza de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza `netrm:BufferRemaining` para indicar cuántos mensajes nuevos puede almacenar en búfer.  
  
-   B4004:cuando está habilitado el control de flujo de la mensajería de confianza, el origen de la mensajería de confianza de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza el valor de `netrm:BufferRemaining` para limitar la transmisión de mensajes.  
  
-   B4005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera valores enteros de `netrm:BufferRemaining` entre 0 y 4.096, ambos incluidos, y lee valores enteros entre 0 y el valor `maxInclusive` 214748364 de `xs:int`.  
  
## Modelos de intercambio de mensajes  
 En esta sección se describe el comportamiento de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cuando se utiliza WS\-ReliableMessaging para modelos de intercambio de mensajes diferentes.Para cada modelo de intercambio de mensajes, se consideran los dos escenarios de implementación siguientes:  
  
-   Iniciador no direccionable: el iniciador está tras un firewall; el respondedor solo puede entregar mensajes al iniciador mediante respuestas HTTP.  
  
-   Iniciador direccionable: el iniciador y el respondedor pueden enviar solicitudes HTTP; en otras palabras, se pueden establecer dos conexiones HTTP inversas.  
  
### Iniciador unidireccional no direccionable  
  
#### Enlace  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona un modelo de intercambio de mensajes unidireccional usando una secuencia sobre un canal HTTP.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usa solicitudes HTTP para transmitir todos los mensajes del iniciador al respondedor y respuestas HTTP para transmitir todos los mensajes del respondedor al iniciador.  
  
#### CreateSequence Exchange  
 El iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transmite un mensaje `CreateSequence` sin elemento `Offer` en una solicitud HTTP y espera el mensaje `CreateSequenceResponse` en la respuesta HTTP.El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] crea una secuencia y transmite el mensaje `CreateSequenceResponse` sin elemento `Accept` en la respuesta HTTP.  
  
#### SequenceAcknowledgement  
 El iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] procesa las confirmaciones en la respuesta de todos los mensajes, salvo en los mensajes de error y el mensaje `CreateSequence`.El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] siempre transmite una confirmación independiente en la respuesta HTTP a todos los mensajes de `AckRequested` y secuencias.  
  
#### Intercambio de CloseSequence  
 El iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transmite un mensaje `CloseSequence` en una solicitud HTTP y espera el mensaje `CreateSequenceResponse` en la respuesta HTTP.El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transmite el mensaje `CloseSequenceResponse` en la respuesta HTTP.  
  
#### Intercambio de TerminateSequence  
 El iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transmite un mensaje `TerminateSequence` en una solicitud HTTP y espera el mensaje `TerminateSequenceResponse` en la respuesta HTTP.El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transmite el mensaje `TerminateSequenceResponse` en la respuesta HTTP.  
  
### Iniciador unidireccional y direccionable  
  
#### Enlace  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona un modelo de intercambio de mensajes unidireccional usando una secuencia sobre un canal HTTP entrante y uno saliente.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usa las solicitudes HTTP para transmitir todos los mensajes.Todas las respuestas HTTP tienen un cuerpo vacío y código de estado HTTP 202.  
  
#### CreateSequence Exchange  
 El iniciador [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transmite un mensaje `CreateSequence` sin elemento `Offer` en una solicitud HTTP.El respondedor [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] crea una secuencia y transmite el mensaje `CreateSequenceResponse` sin elemento `Accept` en una solicitud HTTP.  
  
### Iniciador dúplex y direccionable  
  
#### Enlace  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona un modelo de intercambio de mensajes totalmente asincrónico y bidireccional utilizando dos secuencias sobre un canal HTTP entrante y uno saliente.Este modelo de intercambio de mensajes se puede mezclar con el modelo de intercambio de mensajes del iniciador de `Request/Reply`, `Addressable` de una manera limitada.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usa solicitudes HTTP para transmitir todos los mensajes.Todas las respuestas HTTP tienen un cuerpo vacío y código de estado HTTP 202.  
  
#### CreateSequence Exchange  
 El iniciador [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transmite un mensaje `CreateSequence` con un elemento `Offer` en una solicitud HTTP.El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] asegura que la `CreateSequence` tiene un elemento `Offer`, a continuación, crea una secuencia y transmite el mensaje `CreateSequenceResponse` con un elemento `Accept`.  
  
#### Duración de la secuencia  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] trata las dos secuencias como una sesión totalmente dúplex.  
  
 Tras generar un error que provoca un error en una secuencia, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] espera que el extremo remoto genere un error en ambas secuencias.Tras leer un error que provoca un error en una secuencia, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera un error en ambas secuencias.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] puede cerrar su secuencia saliente y continuar procesando mensajes en su secuencia entrante.De manera inversa, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] puede procesar el cierre de la secuencia entrante y continuar enviando mensajes en su secuencia saliente.  
  
### Iniciador de solicitud\-respuesta unidireccional y no direccionable  
  
#### Enlace  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona un modelo de intercambio unidireccional de mensajes de solicitud\-respuesta usando dos secuencias sobre un canal HTTP.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usa solicitudes HTTP para transmitir todos los mensajes del iniciador al respondedor y respuestas HTTP para transmitir todos los mensajes del respondedor al iniciador.  
  
#### CreateSequence Exchange  
 El iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transmite un mensaje `CreateSequence` con un elemento `Offer` en una solicitud HTTP y espera el mensaje `CreateSequenceResponse` en la respuesta HTTP.El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] crea una secuencia y transmite el mensaje `CreateSequenceResponse` con un elemento `Accept` en la respuesta HTTP.  
  
#### Mensaje unidireccional  
 Para completar correctamente un intercambio de mensajes unidireccional, el iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transmite un mensaje de secuencia de solicitud en la solicitud HTTP y recibe un mensaje `SequenceAcknowledgement` independiente en la respuesta HTTP.La `SequenceAcknowledgement` debe confirmar el mensaje transmitido.  
  
 El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] puede responder a la solicitud con una confirmación, un error o una respuesta con un cuerpo vacío y un código de estado HTTP 202.  
  
#### Mensajes bidireccionales  
 Para completar correctamente un protocolo de intercambio de mensajes bidireccional, el iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transmite un mensaje de secuencia de solicitud en la solicitud HTTP y recibe un mensaje de secuencia de respuesta en la respuesta HTTP.La respuesta debe llevar una `SequenceAcknowledgement` que confirme que se ha transmitido el mensaje de secuencia de solicitud.  
  
 El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] puede responder a la solicitud con una respuesta de la aplicación, un error o una respuesta con un cuerpo vacío y un código de estado HTTP 202.  
  
 Debido a la presencia de mensajes unidireccionales y al control de tiempo de las respuestas de la aplicación, el número de secuencia del mensaje de secuencia de solicitud y el número de secuencia del mensaje de respuesta no tienen ninguna correlación.  
  
#### Reintento de respuestas  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] confía en la correlación de solicitud\-respuesta HTTP para la correlación del protocolo de intercambio de mensajes bidireccional.Debido a esto, el iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no deja de reintentar un mensaje de secuencia de solicitud cuando se confirma el mensaje de secuencia de solicitud, sino cuando la respuesta HTTP lleva una `SequenceAcknowledgement`, una respuesta de la aplicación o error.El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] reintenta las respuestas en la respuesta HTTP de la solicitud con la que se correlaciona la respuesta.  
  
#### Intercambio de CloseSequence  
 Después de recibir todos los mensajes de secuencia de respuesta y confirmaciones para todos los mensajes de secuencia de solicitud unidireccionales, el iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transmite un mensaje `CloseSequence` para la secuencia de la solicitud en una solicitud HTTP y espera la `CloseSequenceResponse` en la respuesta HTTP.  
  
 Al cerrar implícitamente la secuencia de la solicitud, se cierra la secuencia de la respuesta.Esto significa que el iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] incluye la `SequenceAcknowledgement` final de la secuencia de respuesta en el mensaje `CloseSequence` y la secuencia de respuesta no tiene un intercambio de `CloseSequence`.  
  
 El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] garantiza que todas las respuestas se confirmen y transmite el mensaje `CloseSequenceResponse` en la respuesta HTTP.  
  
#### Intercambio de TerminateSequence  
 Después de recibir el mensaje `CloseSequenceResponse`, el iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transmite un mensaje `TerminateSequence` para la secuencia de la solicitud en una solicitud HTTP y espera la `TerminateSequenceResponse` en la respuesta HTTP.  
  
 Al igual que en el intercambio de `CloseSequence`, al finalizar la secuencia de solicitud, se finaliza la secuencia de respuesta.Esto significa que el iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] incluye la `SequenceAcknowledgement` final de la secuencia de respuesta en el mensaje `TerminateSequence` y la secuencia de respuesta no tiene un intercambio de `TerminateSequence`.  
  
 El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transmite el mensaje `TerminateSequenceResponse` en la respuesta HTTP.  
  
### Iniciador direccionable de solicitud\-respuesta  
  
#### Enlace  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona un modelo de intercambio de mensajes de solicitud\-respuesta utilizando dos secuencias sobre un canal HTTP entrante y uno saliente.Este modelo de intercambio de mensajes se puede mezclar con el modelo de intercambio de mensajes del iniciador de `Duplex, Addressable` de una manera limitada.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usa las solicitudes HTTP para transmitir todos los mensajes.Todas las respuestas HTTP tienen un cuerpo vacío y código de estado HTTP 202.  
  
#### CreateSequence Exchange  
 El iniciador [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transmite un mensaje `CreateSequence` con un elemento `Offer` en una solicitud HTTP.El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] asegura que la `CreateSequence` tiene un elemento `Offer`, a continuación, crea una secuencia y transmite el mensaje `CreateSequenceResponse` con un elemento `Accept`.  
  
#### Correlación entre solicitud y respuesta  
 Lo siguiente se aplica a todas las solicitudes y respuestas correlacionadas:  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] garantiza que todos los mensajes de solicitud de la aplicación llevan una referencia de extremo `ReplyTo` y un `MessageId`.  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aplica la referencia del extremo local como cada `ReplyTo` de mensaje de solicitud de la aplicación.La referencia del extremo local es la `ReplyTo` del mensaje `CreateSequence` para el iniciador y la `To` del mensaje `CreateSequence` para el respondedor.  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] garantiza que los mensajes de solicitud entrantes lleven un `MessageId` y una `ReplyTo`.  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] garantiza que el URI de la referencia de extremo `ReplyTo` de todos los mensajes de solicitud de aplicaciones coinciden con la referencia del extremo local tal y como se definió anteriormente.  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] garantiza que todas las respuestas llevan los encabezados `RelatesTo` y `To` correctos que siguen las reglas de correlación de solicitud\/respuesta de `wsa`.