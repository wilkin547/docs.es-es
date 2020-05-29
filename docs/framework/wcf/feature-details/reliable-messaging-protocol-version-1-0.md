---
title: Protocolo de mensajería de confianza versión 1.0
ms.date: 03/30/2017
ms.assetid: a5509a5c-de24-4bc2-9a48-19138055dcce
ms.openlocfilehash: 8d192afcffca52136d6d71de49770c5a5ad13895
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202301"
---
# <a name="reliable-messaging-protocol-version-10"></a><span data-ttu-id="13ae6-102">Protocolo de mensajería de confianza versión 1.0</span><span class="sxs-lookup"><span data-stu-id="13ae6-102">Reliable Messaging Protocol version 1.0</span></span>

<span data-ttu-id="13ae6-103">En este tema se tratan los detalles de implementación de Windows Communication Foundation (WCF) para el protocolo WS-Reliable Messaging de febrero de 2005 (versión 1,0) necesario para la interoperación mediante el transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="13ae6-103">This topic covers Windows Communication Foundation (WCF) implementation details for the WS-Reliable Messaging February 2005 (version 1.0) protocol necessary for interoperation using the HTTP transport.</span></span> <span data-ttu-id="13ae6-104">WCF sigue la especificación WS-Reliable Messaging con las restricciones y aclaraciones explicadas en este tema.</span><span class="sxs-lookup"><span data-stu-id="13ae6-104">WCF follows the WS-Reliable Messaging specification with the constraints and clarifications explained in this topic.</span></span> <span data-ttu-id="13ae6-105">Tenga en cuenta que el protocolo WS-ReliableMessaging versión 1,0 se implementa a partir de WinFX.</span><span class="sxs-lookup"><span data-stu-id="13ae6-105">Note that the WS-ReliableMessaging version 1.0 protocol is implemented starting with the WinFX.</span></span>

<span data-ttu-id="13ae6-106">Implementa el protocolo WS-Reliable Messaging de febrero de 2005 en WCF <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> .</span><span class="sxs-lookup"><span data-stu-id="13ae6-106">The WS-Reliable Messaging February 2005 protocol is implemented in WCF by the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span></span>

<span data-ttu-id="13ae6-107">Para su comodidad, el tema utiliza las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="13ae6-107">For convenience, the topic uses the following roles:</span></span>

- <span data-ttu-id="13ae6-108">Iniciador: el cliente que inicia la creación de la secuencia de mensajes WS-Reliable</span><span class="sxs-lookup"><span data-stu-id="13ae6-108">Initiator: the client that initiates WS-Reliable Message sequence creation</span></span>

- <span data-ttu-id="13ae6-109">Respondedor: el servicio que recibe las solicitudes del iniciador</span><span class="sxs-lookup"><span data-stu-id="13ae6-109">Responder: the service that receives the initiator's requests</span></span>

<span data-ttu-id="13ae6-110">En este documento, se utilizan los prefijos y espacios de nombres de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="13ae6-110">This document uses the prefixes and namespaces in the following table.</span></span>

|<span data-ttu-id="13ae6-111">Prefijo</span><span class="sxs-lookup"><span data-stu-id="13ae6-111">Prefix</span></span>|<span data-ttu-id="13ae6-112">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="13ae6-112">Namespace</span></span>|
|------------|---------------|
|<span data-ttu-id="13ae6-113">wsrm</span><span class="sxs-lookup"><span data-stu-id="13ae6-113">wsrm</span></span>|`http://schemas.xmlsoap.org/ws/2005/02/rm`|
|<span data-ttu-id="13ae6-114">netrm</span><span class="sxs-lookup"><span data-stu-id="13ae6-114">netrm</span></span>|`http://schemas.microsoft.com/ws/2006/05/rm`|
|<span data-ttu-id="13ae6-115">s</span><span class="sxs-lookup"><span data-stu-id="13ae6-115">s</span></span>|`http://www.w3.org/2003/05/soap-envelope`|
|<span data-ttu-id="13ae6-116">wsa</span><span class="sxs-lookup"><span data-stu-id="13ae6-116">wsa</span></span>|`http://schemas.xmlsoap.org/ws/2005/08/addressing`|
|<span data-ttu-id="13ae6-117">wsse</span><span class="sxs-lookup"><span data-stu-id="13ae6-117">wsse</span></span>|`http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd`|

## <a name="messaging"></a><span data-ttu-id="13ae6-118">Mensajería</span><span class="sxs-lookup"><span data-stu-id="13ae6-118">Messaging</span></span>

### <a name="sequence-establishment-messages"></a><span data-ttu-id="13ae6-119">Mensajes de establecimiento de secuencia</span><span class="sxs-lookup"><span data-stu-id="13ae6-119">Sequence Establishment Messages</span></span>

<span data-ttu-id="13ae6-120">WCF implementa `CreateSequence` mensajes y `CreateSequenceResponse` para establecer una secuencia de mensajes confiable.</span><span class="sxs-lookup"><span data-stu-id="13ae6-120">WCF implements `CreateSequence` and `CreateSequenceResponse` messages to establish a reliable message sequence.</span></span> <span data-ttu-id="13ae6-121">Las siguientes restricciones son aplicables:</span><span class="sxs-lookup"><span data-stu-id="13ae6-121">The following constraints apply:</span></span>

- <span data-ttu-id="13ae6-122">B1101: el iniciador de WCF no genera el elemento Expires opcional en el `CreateSequence` mensaje o, en los casos en los que el `CreateSequence` mensaje contiene un `Offer` elemento, el `Expires` elemento opcional en el `Offer` elemento.</span><span class="sxs-lookup"><span data-stu-id="13ae6-122">B1101: The WCF Initiator does not generate the optional Expires element in the `CreateSequence` message or, in the cases when the `CreateSequence` message contains an `Offer` element, the optional `Expires` element in the `Offer` element.</span></span>

- <span data-ttu-id="13ae6-123">B1102: al obtener acceso al `CreateSequence` mensaje, WCF `Responder` envía y recibe ambos `Expires` elementos si existen, pero no usa sus valores.</span><span class="sxs-lookup"><span data-stu-id="13ae6-123">B1102: When accessing the `CreateSequence` message, the WCF`Responder` sends and receives both `Expires` elements if they exist, but does not use their values.</span></span>

<span data-ttu-id="13ae6-124">WS-Reliable Messaging incluye el mecanismo `Offer` para establecer las dos secuencias correlacionadas inversas que forman una sesión.</span><span class="sxs-lookup"><span data-stu-id="13ae6-124">WS-Reliable Messaging introduces the `Offer` mechanism to establish the two converse correlated sequences that form a session.</span></span>

- <span data-ttu-id="13ae6-125">R1103: si `CreateSequence` contiene un elemento `Offer`, el respondedor de la mensajería de confianza debe aceptar la secuencia y responder con `CreateSequenceResponse`, que contiene un elemento `wsrm:Accept`, formando dos secuencias correlacionadas inversas, o rechazar la solicitud `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="13ae6-125">R1103: If `CreateSequence` contains an `Offer` element, the Reliable Messaging Responder must either accept the sequence and respond with `CreateSequenceResponse` that contains a `wsrm:Accept` element, forming two correlated converse sequences or reject the `CreateSequence` request.</span></span>

- <span data-ttu-id="13ae6-126">R1104: `SequenceAcknowledgement` y los mensajes de la aplicación que fluyen en una secuencia inversa se deben enviar a la referencia de punto de conexión `ReplyTo` de `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="13ae6-126">R1104: `SequenceAcknowledgement` and application messages flowing on converse sequence must be sent to the `ReplyTo` endpoint reference of the `CreateSequence`.</span></span>

- <span data-ttu-id="13ae6-127">R1105: las referencias de punto de conexión `AcksTo` y `ReplyTo` en `CreateSequence` deben tener valores de dirección que coincidan byte a byte.</span><span class="sxs-lookup"><span data-stu-id="13ae6-127">R1105: `AcksTo` and `ReplyTo` endpoint references in the `CreateSequence` must have address values that match the octet-wise.</span></span>

  <span data-ttu-id="13ae6-128">El respondedor de WCF comprueba que la parte del URI de `AcksTo` los `ReplyTo` EPRs y son idénticas antes de crear una secuencia.</span><span class="sxs-lookup"><span data-stu-id="13ae6-128">The WCF Responder verifies that the URI portion of the `AcksTo` and `ReplyTo` EPRs are identical before creating a sequence.</span></span>

- <span data-ttu-id="13ae6-129">R1106: las referencias de punto de conexión `AcksTo` y `ReplyTo` del mensaje `CreateSequence` deberían tener el mismo conjunto de parámetros de referencia.</span><span class="sxs-lookup"><span data-stu-id="13ae6-129">R1106: `AcksTo` and `ReplyTo` Endpoint References in the `CreateSequence` should have the same set of reference parameters.</span></span>

  <span data-ttu-id="13ae6-130">WCF no aplica pero supone que los [parámetros de referencia] de `AcksTo` y `ReplyTo` en `CreateSequence` son idénticos y utiliza [parámetros de referencia] de `ReplyTo` referencia de extremo para las confirmaciones y los mensajes de secuencia inversa.</span><span class="sxs-lookup"><span data-stu-id="13ae6-130">WCF does not enforce but assumes that [reference parameters] of `AcksTo` and `ReplyTo` on `CreateSequence` are identical and uses [reference parameters] from `ReplyTo` endpoint reference for acknowledgements and converse sequence messages.</span></span>

- <span data-ttu-id="13ae6-131">R1107: cuando dos secuencias inversas se establecen por medio del mecanismo `Offer`, los mensajes de aplicación y `SequenceAcknowledgement` que fluyen en secuencias inversas se deben enviar a la referencia de punto de conexión `ReplyTo` de `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="13ae6-131">R1107: When two converse sequences are established using the `Offer` mechanism, `SequenceAcknowledgement` and application messages flowing on converse sequences must be sent to the `ReplyTo` endpoint reference of the `CreateSequence`.</span></span>

- <span data-ttu-id="13ae6-132">R1108: cuando dos secuencias inversas se establecen mediante el mecanismo Offer, la propiedad `[address]` del elemento secundario de referencia de extremo `wsrm:AcksTo` del elemento `wsrm:Accept` de `CreateSequenceResponse` debe coincidir byte a byte con el URI de destino de `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="13ae6-132">R1108: When two converse sequences are established using the Offer mechanism, the `[address]` property of the `wsrm:AcksTo` Endpoint Reference child element of the `wsrm:Accept` element of the `CreateSequenceResponse` must match byte-wise the destination URI of the `CreateSequence`.</span></span>

- <span data-ttu-id="13ae6-133">R1109: cuando se establecen dos secuencias inversas por medio del mecanismo `Offer`, los mensajes enviados por el iniciador y las confirmaciones de los mensajes por parte del respondedor se deben enviar a la misma referencia de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="13ae6-133">R1109: When two converse sequences are established using the `Offer` mechanism, messages sent by initiator and acknowledgements to messages by responder must be sent to the same Endpoint Reference.</span></span>

  <span data-ttu-id="13ae6-134">WCF usa WS-Reliable Messaging para establecer sesiones confiables entre el iniciador y el respondedor.</span><span class="sxs-lookup"><span data-stu-id="13ae6-134">WCF uses WS-Reliable Messaging to establish reliable sessions between the Initiator and Responder.</span></span> <span data-ttu-id="13ae6-135">La implementación de WS-Reliable Messaging de WCF proporciona una sesión confiable para patrones de mensajería dúplex completa y de solicitud-respuesta unidireccionales.</span><span class="sxs-lookup"><span data-stu-id="13ae6-135">WCF's WS-Reliable Messaging implementation provides reliable session for one-way, request-reply and full duplex messaging patterns.</span></span> <span data-ttu-id="13ae6-136">El mecanismo de WS-Reliable Messaging `Offer` en `CreateSequence` / `CreateSequenceResponse` le permite establecer dos secuencias inversas correlacionadas y proporciona un protocolo de sesión que es adecuado para todos los extremos de mensajes.</span><span class="sxs-lookup"><span data-stu-id="13ae6-136">The WS-Reliable Messaging `Offer` mechanism on `CreateSequence`/`CreateSequenceResponse` lets you establish two correlated converse sequences, and provides a session protocol that is suitable for all message endpoints.</span></span> <span data-ttu-id="13ae6-137">Dado que WCF proporciona una garantía de seguridad para este tipo de sesión, incluida la protección de un extremo a otro para la integridad de la sesión, es práctico asegurarse de que los mensajes destinados a la misma entidad lleguen al mismo destino.</span><span class="sxs-lookup"><span data-stu-id="13ae6-137">Because WCF provides a security guarantee for such a session including end-to-end protection for session integrity, it is practical to ensure messages intended to the same party are arriving at the same destination.</span></span> <span data-ttu-id="13ae6-138">Esto también permite el “apoyo a caballo” de confirmaciones de secuencias en mensajes de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="13ae6-138">This also allows piggy-backing of sequence acknowledgements on application messages.</span></span> <span data-ttu-id="13ae6-139">Por lo tanto, las restricciones R1104, R1105 y R1108 se aplican a WCF.</span><span class="sxs-lookup"><span data-stu-id="13ae6-139">Therefore, constraints R1104, R1105, and R1108 apply to WCF.</span></span>

<span data-ttu-id="13ae6-140">Ejemplo de mensaje `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="13ae6-140">An example of a `CreateSequence` message.</span></span>

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

 <span data-ttu-id="13ae6-141">Ejemplo de mensaje `CreateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="13ae6-141">An example of a `CreateSequenceResponse` message.</span></span>

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

### <a name="sequence"></a><span data-ttu-id="13ae6-142">Secuencia</span><span class="sxs-lookup"><span data-stu-id="13ae6-142">Sequence</span></span>

<span data-ttu-id="13ae6-143">A continuación, se muestra una lista de restricciones que se aplican a las secuencias:</span><span class="sxs-lookup"><span data-stu-id="13ae6-143">The following is a list of constraints that apply to sequences:</span></span>

- <span data-ttu-id="13ae6-144">B1201: WCF genera y obtiene acceso a los números de secuencia que no son mayores que el `xs:long` valor inclusivo máximo de 9223372036854775807.</span><span class="sxs-lookup"><span data-stu-id="13ae6-144">B1201:WCF generates and accesses sequence numbers no higher than `xs:long`’s maximum inclusive value, 9223372036854775807.</span></span>

- <span data-ttu-id="13ae6-145">B1202: WCF siempre genera un último mensaje de cuerpo vacío con el URI de la acción de `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage` .</span><span class="sxs-lookup"><span data-stu-id="13ae6-145">B1202:WCF always generates an empty-bodied last message with the action URI of `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`.</span></span>

- <span data-ttu-id="13ae6-146">B1203: WCF recibe y entrega un mensaje con un encabezado de secuencia que contiene un `LastMessage` elemento, siempre y cuando el URI de la acción no sea `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage` .</span><span class="sxs-lookup"><span data-stu-id="13ae6-146">B1203: WCF receives and delivers a message with a Sequence header that contains a `LastMessage` element as long as the action URI is not `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`.</span></span>

<span data-ttu-id="13ae6-147">Ejemplo de encabezado de secuencia.</span><span class="sxs-lookup"><span data-stu-id="13ae6-147">An example of a Sequence Header.</span></span>

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

### <a name="ackrequested-header"></a><span data-ttu-id="13ae6-148">Encabezado AckRequested</span><span class="sxs-lookup"><span data-stu-id="13ae6-148">AckRequested Header</span></span>

<span data-ttu-id="13ae6-149">WCF usa `AckRequested` el encabezado como un mecanismo Keep-Alive.</span><span class="sxs-lookup"><span data-stu-id="13ae6-149">WCF uses `AckRequested` Header as a keep-alive mechanism.</span></span> <span data-ttu-id="13ae6-150">WCF no genera el elemento opcional `MessageNumber` .</span><span class="sxs-lookup"><span data-stu-id="13ae6-150">WCF does not generate the optional `MessageNumber` element.</span></span> <span data-ttu-id="13ae6-151">Al recibir un mensaje con un `AckRequested` encabezado que contiene el `MessageNumber` elemento, WCF omite el `MessageNumber` valor del elemento, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="13ae6-151">Upon receiving a message with an `AckRequested` header that contains the `MessageNumber` element, WCF ignores the `MessageNumber` element’s value, as shown in the following example.</span></span>

```xml
<wsrm:AckRequested>
  <wsrm:Identifier>
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36
  </wsrm:Identifier>
</wsrm:AckRequested>
```

### <a name="sequenceacknowledgement-header"></a><span data-ttu-id="13ae6-152">Encabezado SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="13ae6-152">SequenceAcknowledgement Header</span></span>

<span data-ttu-id="13ae6-153">WCF usa el mecanismo de reutilización para las confirmaciones de secuencias proporcionadas en la mensajería de confianza de WS.</span><span class="sxs-lookup"><span data-stu-id="13ae6-153">WCF uses piggy-back mechanism for sequence acknowledgements provided in WS-Reliable Messaging.</span></span>

- <span data-ttu-id="13ae6-154">R1401: cuando dos secuencias inversas se establecen utilizando el mecanismo `Offer`, el encabezado `SequenceAcknowledgement` puede estar incluido en cualquier mensaje de aplicación transmitido al destinatario previsto.</span><span class="sxs-lookup"><span data-stu-id="13ae6-154">R1401: When two converse sequences are established using the `Offer` mechanism, the `SequenceAcknowledgement` header may be included in any application message transmitted to the intended recipient.</span></span>

- <span data-ttu-id="13ae6-155">B1402: cuando WCF debe generar una confirmación antes de recibir mensajes de secuencia (por ejemplo, para satisfacer un `AckRequested` mensaje), WCF genera un `SequenceAcknowledgement` encabezado que contiene el intervalo 0-0, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="13ae6-155">B1402: When WCF must generate an acknowledgement prior to receiving any sequence messages (for example, to satisfy an `AckRequested` message), WCF generates a `SequenceAcknowledgement` header that contains the range 0-0, as shown in the following example.</span></span>

  ```xml
  <wsrm:SequenceAcknowledgement>
    <wsrm:Identifier>
      urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36
    </wsrm:Identifier>
    <wsrm:AcknowledgementRange Upper="0" Lower="0"/>
  </wsrm:SequenceAcknowledgement>
  ```

- <span data-ttu-id="13ae6-156">B1403: WCF no genera `SequenceAcknowledgement` encabezados que contengan un `Nack` elemento pero admita `Nack` elementos.</span><span class="sxs-lookup"><span data-stu-id="13ae6-156">B1403: WCF does not generate `SequenceAcknowledgement` headers that contain a `Nack` element but supports `Nack` elements.</span></span>

### <a name="ws-reliablemessaging-faults"></a><span data-ttu-id="13ae6-157">Errores de WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="13ae6-157">WS-ReliableMessaging Faults</span></span>

<span data-ttu-id="13ae6-158">A continuación se muestra una lista de restricciones que se aplican a la implementación de WCF de errores de mensajería de confianza WS:</span><span class="sxs-lookup"><span data-stu-id="13ae6-158">The following is a list of constraints that apply to the WCF implementation of WS-Reliable Messaging faults:</span></span>

- <span data-ttu-id="13ae6-159">B1501: WCF no genera `MessageNumberRollover` errores.</span><span class="sxs-lookup"><span data-stu-id="13ae6-159">B1501: WCF does not generate `MessageNumberRollover` faults.</span></span>

- <span data-ttu-id="13ae6-160">B1502: el punto de conexión de WCF puede generar `CreateSequenceRefused` errores como se describe en la especificación.</span><span class="sxs-lookup"><span data-stu-id="13ae6-160">B1502:WCF endpoint may generate `CreateSequenceRefused` faults as described in the specification.</span></span>

- <span data-ttu-id="13ae6-161">B1503: cuando el extremo de servicio alcanza su límite de conexiones y no puede procesar nuevas conexiones, WCF genera un `CreateSequenceRefused` subcódigo de error adicional, `netrm:ConnectionLimitReached` , tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="13ae6-161">B1503:When the service endpoint reaches its connection limit and cannot process new connections, WCF generates an additional `CreateSequenceRefused` fault subcode, `netrm:ConnectionLimitReached`, as shown in the following example.</span></span>

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

### <a name="ws-addressing-faults"></a><span data-ttu-id="13ae6-162">Errores WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="13ae6-162">WS-Addressing Faults</span></span>

<span data-ttu-id="13ae6-163">Dado que WS-Reliable Messaging usa WS-Addressing, la implementación de mensajería de confianza de WCF WS puede generar errores de WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="13ae6-163">Because WS-Reliable Messaging uses WS-Addressing, WCF WS-Reliable Messaging implementation may generate WS-Addressing faults.</span></span> <span data-ttu-id="13ae6-164">En esta sección se tratan los errores de WS-Addressing que WCF genera explícitamente en el nivel de mensajería WS-Reliable:</span><span class="sxs-lookup"><span data-stu-id="13ae6-164">This section covers the WS-Addressing faults that WCF explicitly generates at the WS-Reliable Messaging layer:</span></span>

- <span data-ttu-id="13ae6-165">B1601: WCF genera el encabezado de direccionamiento del mensaje de error necesario cuando se cumple una de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="13ae6-165">B1601:WCF generates the fault Message Addressing Header Required when one of the following is true:</span></span>

  - <span data-ttu-id="13ae6-166">Falta un encabezado `Sequence` y un encabezado `Action` en un mensaje.</span><span class="sxs-lookup"><span data-stu-id="13ae6-166">A message is missing a `Sequence` header and an `Action` header.</span></span>

  - <span data-ttu-id="13ae6-167">Falta un encabezado `CreateSequence` en un mensaje `MessageId`.</span><span class="sxs-lookup"><span data-stu-id="13ae6-167">A `CreateSequence` message is missing a `MessageId` header.</span></span>

  - <span data-ttu-id="13ae6-168">Falta un encabezado `CreateSequence` en un mensaje `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="13ae6-168">A `CreateSequence` message is missing a `ReplyTo` header.</span></span>

- <span data-ttu-id="13ae6-169">B1602: WCF genera la acción de error no admitida en la respuesta a un mensaje que no tiene un `Sequence` encabezado y tiene un `Action` encabezado que no es reconocido en la especificación WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="13ae6-169">B1602:WCF generates the fault Action Not Supported in reply to a message that is missing a `Sequence` header and has an `Action` header that is not a recognized in the WS-Reliable Messaging specification.</span></span>

- <span data-ttu-id="13ae6-170">B1603: WCF genera el extremo de error no disponible para indicar que el extremo no procesa la secuencia en función del examen de los `CreateSequence` encabezados de direccionamiento del mensaje.</span><span class="sxs-lookup"><span data-stu-id="13ae6-170">B1603:WCF generates the fault Endpoint Unavailable to indicate that the endpoint does not process the sequence based upon examination of the `CreateSequence` message’s addressing headers.</span></span>

## <a name="protocol-composition"></a><span data-ttu-id="13ae6-171">Composición de protocolos</span><span class="sxs-lookup"><span data-stu-id="13ae6-171">Protocol Composition</span></span>

### <a name="composition-with-ws-addressing"></a><span data-ttu-id="13ae6-172">Composición con WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="13ae6-172">Composition with WS-Addressing</span></span>

<span data-ttu-id="13ae6-173">WCF admite dos versiones de WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] y W3C WS-Addressing 1,0 Recommendations [WS-ADDR-CORE] y [WS-ADDR-SOAP].</span><span class="sxs-lookup"><span data-stu-id="13ae6-173">WCF supports two versions of WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] and W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] and [WS-ADDR-SOAP].</span></span>

<span data-ttu-id="13ae6-174">Aunque la especificación de WS-Reliable Messaging solo menciona a WS-Addressing 2004/08, no limita la versión de WS-Addressing que se ha de utilizar.</span><span class="sxs-lookup"><span data-stu-id="13ae6-174">While the WS-Reliable Messaging specification mentions only WS-Addressing 2004/08, it does not restrict the WS-Addressing version to be used.</span></span> <span data-ttu-id="13ae6-175">A continuación se muestra una lista de restricciones que se aplican a WCF:</span><span class="sxs-lookup"><span data-stu-id="13ae6-175">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="13ae6-176">R2101:WS-Addressing 2004/08 y WS-Addressing 1.0 se pueden utilizar con WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="13ae6-176">R2101:Both WS-Addressing 2004/08 and WS-Addressing 1.0 can be used with WS-Reliable Messaging.</span></span>

- <span data-ttu-id="13ae6-177">R2102: se debe utilizar una única versión de WS-Addressing en una secuencia de WS-Reliable Messaging determinada o un par de secuencias inversas correlacionadas mediante el `wsrm:Offer` mecanismo.</span><span class="sxs-lookup"><span data-stu-id="13ae6-177">R2102:A single version of WS-Addressing must be used throughout a given WS-Reliable Messaging sequence or a pair of converse sequences correlated by using the `wsrm:Offer` mechanism.</span></span>

### <a name="composition-with-soap"></a><span data-ttu-id="13ae6-178">Composición con SOAP</span><span class="sxs-lookup"><span data-stu-id="13ae6-178">Composition with SOAP</span></span>

<span data-ttu-id="13ae6-179">WCF admite el uso de SOAP 1,1 y SOAP 1,2 con la mensajería de confianza de WS.</span><span class="sxs-lookup"><span data-stu-id="13ae6-179">WCF supports use of both SOAP 1.1 and SOAP 1.2 with WS-Reliable Messaging.</span></span>

### <a name="composition-with-ws-security-and-ws-secureconversation"></a><span data-ttu-id="13ae6-180">Composición con WS-Security y WS-SecureConversation</span><span class="sxs-lookup"><span data-stu-id="13ae6-180">Composition with WS-Security and WS-SecureConversation</span></span>

<span data-ttu-id="13ae6-181">WCF proporciona protección para secuencias de WS-Reliable Messaging mediante el transporte seguro (HTTPS), la composición con WS-Security y la composición con WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="13ae6-181">WCF provides protection for WS-Reliable Messaging sequences by using secure Transport (HTTPS), composition with WS-Security, and composition with WS-Secure Conversation.</span></span> <span data-ttu-id="13ae6-182">A continuación se muestra una lista de restricciones que se aplican a WCF:</span><span class="sxs-lookup"><span data-stu-id="13ae6-182">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="13ae6-183">R2301: para proteger la integridad de una secuencia de mensajería de confianza WS, además de la integridad y confidencialidad de los mensajes individuales, WCF requiere que se utilice WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="13ae6-183">R2301:To protect the integrity of a WS-Reliable Messaging sequence in addition to the integrity and confidentiality of individual messages, WCF requires that WS-Secure Conversation must be used.</span></span>

- <span data-ttu-id="13ae6-184">R2302:una sesión de WS-Secure Conversation se debe establecer antes de establecer las secuencias de WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="13ae6-184">R2302:AWS-Secure Conversation session must be established prior to establishing WS-Reliable Messaging sequence(s).</span></span>

- <span data-ttu-id="13ae6-185">R2303: si la duración de la secuencia de WS-Reliable Messaging supera la duración de la sesión de WS-Secure Conversation, el `SecurityContextToken` establecido mediante WS-Secure Conversation se debe renovar utilizando el enlace de renovación de WS-Secure Conversation correspondiente.</span><span class="sxs-lookup"><span data-stu-id="13ae6-185">R2303: If the WS-Reliable Messaging sequence lifetime exceeds the WS-Secure Conversation session’s lifetime, the `SecurityContextToken` established by using WS-Secure Conversation must be renewed by using the corresponding WS-Secure Conversation Renewal binding.</span></span>

- <span data-ttu-id="13ae6-186">B2304:la secuencia de WS-Reliable Messaging o un par de secuencias inversas correlacionadas siempre se enlazan a una única sesión de WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="13ae6-186">B2304:WS-Reliable Messaging sequence or a pair of correlated converse sequences are always bound to a single WS-SecureConversation session.</span></span>

  <span data-ttu-id="13ae6-187">El origen de WCF genera el `wsse:SecurityTokenReference` elemento en la sección de extensibilidad de elementos del `CreateSequence` mensaje.</span><span class="sxs-lookup"><span data-stu-id="13ae6-187">The WCF source generates the `wsse:SecurityTokenReference` element in the element extensibility section of the `CreateSequence` message.</span></span>

- <span data-ttu-id="13ae6-188">R2305: cuando se crea con WS-Secure Conversation, un `CreateSequence` mensaje debe contener el `wsse:SecurityTokenReference` elemento.</span><span class="sxs-lookup"><span data-stu-id="13ae6-188">R2305:When composed with WS-Secure Conversation, a `CreateSequence` message must contain the `wsse:SecurityTokenReference` element.</span></span>

## <a name="ws-reliable-messaging-ws-policy-assertion"></a><span data-ttu-id="13ae6-189">Aserción de WS-Policy de WS-Reliable Messaging </span><span class="sxs-lookup"><span data-stu-id="13ae6-189">WS-Reliable Messaging WS-Policy Assertion</span></span>

<span data-ttu-id="13ae6-190">WCF usa la aserción WS-Policy de WS-Reliable Messaging `wsrm:RMAssertion` para describir las capacidades de los extremos.</span><span class="sxs-lookup"><span data-stu-id="13ae6-190">WCF uses WS-Reliable Messaging WS-Policy Assertion `wsrm:RMAssertion` to describe endpoints capabilities.</span></span> <span data-ttu-id="13ae6-191">A continuación se muestra una lista de restricciones que se aplican a WCF:</span><span class="sxs-lookup"><span data-stu-id="13ae6-191">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="13ae6-192">B3001: WCF adjunta `wsrm:RMAssertion` la aserción de WS-Policy a `wsdl:binding` los elementos.</span><span class="sxs-lookup"><span data-stu-id="13ae6-192">B3001: WCF attaches `wsrm:RMAssertion` WS-Policy Assertion to `wsdl:binding` elements.</span></span> <span data-ttu-id="13ae6-193">WCF admite datos adjuntos `wsdl:binding` a `wsdl:port` elementos y.</span><span class="sxs-lookup"><span data-stu-id="13ae6-193">WCF supports both attachments to `wsdl:binding` and `wsdl:port` elements.</span></span>

- <span data-ttu-id="13ae6-194">B3002: WCF admite las siguientes propiedades opcionales de la aserción de WS-Reliable Messaging y proporciona control sobre ellas en WCF `ReliableMessagingBindingElement` :</span><span class="sxs-lookup"><span data-stu-id="13ae6-194">B3002: WCF supports the following optional properties of WS-Reliable Messaging assertion and provides control over them on the WCF`ReliableMessagingBindingElement`:</span></span>

  - `wsrm:InactivityTimeout`

  - `wsrm:AcknowledgementInterval`

  <span data-ttu-id="13ae6-195">A continuación se muestra un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="13ae6-195">The following is an example.</span></span>

  ```xml
  <wsrm:RMAssertion>
    <wsrm:InactivityTimeout Milliseconds="600000" />
    <wsrm:AcknowledgementInterval Milliseconds="200" />
  </wsrm:RMAssertion>
  ```

## <a name="flow-control-ws-reliable-messaging-extension"></a><span data-ttu-id="13ae6-196">Extensión de WS-Reliable Messaging de control de flujo</span><span class="sxs-lookup"><span data-stu-id="13ae6-196">Flow Control WS-Reliable Messaging Extension</span></span>

<span data-ttu-id="13ae6-197">WCF usa la extensibilidad de WS-Reliable Messaging para proporcionar un control opcional adicional más estricto sobre el flujo de mensajes de secuencia.</span><span class="sxs-lookup"><span data-stu-id="13ae6-197">WCF uses WS-Reliable Messaging extensibility to provide optional additional tighter control over sequence message flow.</span></span>

<span data-ttu-id="13ae6-198">El control de flujo se habilita estableciendo la <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> propiedad en `true` .</span><span class="sxs-lookup"><span data-stu-id="13ae6-198">Flow control is enabled by setting the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="13ae6-199">A continuación se muestra una lista de restricciones que se aplican a WCF:</span><span class="sxs-lookup"><span data-stu-id="13ae6-199">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="13ae6-200">B4001: cuando está habilitado el control de flujo de mensajería de confianza, WCF genera un `netrm:BufferRemaining` elemento en la extensibilidad de elementos del `SequenceAcknowledgement` encabezado.</span><span class="sxs-lookup"><span data-stu-id="13ae6-200">B4001: When Reliable Messaging Flow Control is enabled, WCF generates a `netrm:BufferRemaining` element in the element extensibility of the `SequenceAcknowledgement` header.</span></span>

- <span data-ttu-id="13ae6-201">B4002: cuando está habilitado el control de flujo de la mensajería de confianza, WCF no requiere que `netrm:BufferRemaining` haya un elemento en `SequenceAcknowledgement` el encabezado, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="13ae6-201">B4002: When Reliable Messaging Flow Control is enabled, WCF does not require a `netrm:BufferRemaining` element to be present in `SequenceAcknowledgement` header, as shown in the following example.</span></span>

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

- <span data-ttu-id="13ae6-202">B4003: WCF usa `netrm:BufferRemaining` para indicar cuántos mensajes nuevos puede almacenar en búfer el destino de la mensajería de confianza.</span><span class="sxs-lookup"><span data-stu-id="13ae6-202">B4003: WCF uses `netrm:BufferRemaining` to indicate how many new messages the Reliable Messaging Destination can buffer.</span></span>

- <span data-ttu-id="13ae6-203">B4004: el servicio de mensajería confiable de WCF limita el número de mensajes que se transmiten cuando la aplicación de destino de la mensajería de confianza no puede recibir mensajes rápidamente.</span><span class="sxs-lookup"><span data-stu-id="13ae6-203">B4004:The WCF Reliable Messaging Service throttles the number of messages transmitted when the Reliable Messaging destination application cannot receive messages quickly.</span></span> <span data-ttu-id="13ae6-204">El destino de la mensajería de confianza almacena en búfer los mensajes y el valor del elemento cae a 0.</span><span class="sxs-lookup"><span data-stu-id="13ae6-204">The Reliable Messaging destination buffers messages and the element’s value drops to 0.</span></span>

- <span data-ttu-id="13ae6-205">B4005: WCF genera `netrm:BufferRemaining` valores enteros entre 0 y 4096, ambos inclusive, y Lee valores enteros entre 0 y `xs:int` el `maxInclusive` valor 214748364, ambos inclusive.</span><span class="sxs-lookup"><span data-stu-id="13ae6-205">B4005: WCF generates `netrm:BufferRemaining` integer values between 0 and 4096 inclusive, and reads integer values between 0 and `xs:int`’s `maxInclusive` value 214748364 inclusive.</span></span>

## <a name="message-exchange-patterns"></a><span data-ttu-id="13ae6-206">Modelos de intercambio de mensajes</span><span class="sxs-lookup"><span data-stu-id="13ae6-206">Message Exchange Patterns</span></span>

<span data-ttu-id="13ae6-207">En esta sección se describe el comportamiento de WCF cuando se usa WS-Reliable Messaging para diferentes patrones de intercambio de mensajes.</span><span class="sxs-lookup"><span data-stu-id="13ae6-207">This section describes WCF's behavior when WS-Reliable Messaging is used for different Message Exchange Patterns.</span></span> <span data-ttu-id="13ae6-208">Para cada patrón de intercambio de mensajes, se consideran los dos escenarios de implementación siguientes:</span><span class="sxs-lookup"><span data-stu-id="13ae6-208">For each Message Exchange Pattern the following two deployments scenarios are considered:</span></span>

- <span data-ttu-id="13ae6-209">Iniciador no direccionable: el iniciador está tras un firewall; el respondedor solo puede entregar mensajes al iniciador mediante respuestas HTTP.</span><span class="sxs-lookup"><span data-stu-id="13ae6-209">Non-Addressable Initiator: Initiator is behind firewall; Responder can deliver messages to Initiator only on HTTP responses.</span></span>

- <span data-ttu-id="13ae6-210">Iniciador direccionable: el iniciador y el respondedor pueden enviar solicitudes HTTP; en otras palabras, se pueden establecer dos conexiones HTTP inversas.</span><span class="sxs-lookup"><span data-stu-id="13ae6-210">Addressable Initiator: Initiator and Responder both can be sent HTTP requests; in other words, two converse HTTP connections can be established.</span></span>

### <a name="one-way-non-addressable-initiator"></a><span data-ttu-id="13ae6-211">Iniciador unidireccional no direccionable</span><span class="sxs-lookup"><span data-stu-id="13ae6-211">One-way, Non-addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="13ae6-212">Enlace</span><span class="sxs-lookup"><span data-stu-id="13ae6-212">Binding</span></span>

<span data-ttu-id="13ae6-213">WCF proporciona un patrón de intercambio de mensajes unidireccional utilizando una secuencia sobre un canal HTTP.</span><span class="sxs-lookup"><span data-stu-id="13ae6-213">WCF provides a one-way message exchange pattern using one sequence over one HTTP channel.</span></span> <span data-ttu-id="13ae6-214">WCF usa las solicitudes HTTP para transmitir todos los mensajes del RMS al RMD y la respuesta HTTP para transmitir todos los mensajes del RMD al RMS.</span><span class="sxs-lookup"><span data-stu-id="13ae6-214">WCF uses the HTTP requests to transmit all messages from the RMS to the RMD and the HTTP response to transmit all messages from the RMD to the RMS.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="13ae6-215">Intercambio de CreateSequence</span><span class="sxs-lookup"><span data-stu-id="13ae6-215">CreateSequence Exchange</span></span>

<span data-ttu-id="13ae6-216">El iniciador de WCF genera un `CreateSequence` mensaje sin ninguna oferta.</span><span class="sxs-lookup"><span data-stu-id="13ae6-216">The WCF Initiator generates a `CreateSequence` message with no offer.</span></span> <span data-ttu-id="13ae6-217">El respondedor de WCF garantiza que `CreateSequence` no tenga ninguna oferta antes de crear una secuencia.</span><span class="sxs-lookup"><span data-stu-id="13ae6-217">The WCF Responder ensures the `CreateSequence` has no offer before creating a sequence.</span></span> <span data-ttu-id="13ae6-218">El respondedor de WCF responde a la `CreateSequence` solicitud con un `CreateSequenceResponse` mensaje.</span><span class="sxs-lookup"><span data-stu-id="13ae6-218">The WCF Responder replies to the `CreateSequence` request with a `CreateSequenceResponse` message.</span></span>

#### <a name="sequenceacknowledgement"></a><span data-ttu-id="13ae6-219">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="13ae6-219">SequenceAcknowledgement</span></span>

<span data-ttu-id="13ae6-220">El iniciador de WCF procesa las confirmaciones en la respuesta de todos los mensajes excepto el `CreateSequence` mensaje y los mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="13ae6-220">The WCF Initiator processes acknowledgements on the reply of all messages except the `CreateSequence` message and fault messages.</span></span> <span data-ttu-id="13ae6-221">El respondedor de WCF siempre genera una confirmación independiente en la respuesta a la secuencia y a `AckRequested` los mensajes.</span><span class="sxs-lookup"><span data-stu-id="13ae6-221">The WCF Responder always generates a stand-alone acknowledgement in the response to both sequence and `AckRequested` messages.</span></span>

#### <a name="terminatesequence-message"></a><span data-ttu-id="13ae6-222">Mensaje TerminateSequence</span><span class="sxs-lookup"><span data-stu-id="13ae6-222">TerminateSequence message</span></span>

<span data-ttu-id="13ae6-223">WCF trata `TerminateSequence` como una operación unidireccional, lo que significa que la respuesta http tiene un cuerpo vacío y un código de estado http 202.</span><span class="sxs-lookup"><span data-stu-id="13ae6-223">WCF treats `TerminateSequence` as a one-way operation, meaning the HTTP response has an empty body and HTTP 202 status code.</span></span>

### <a name="one-way-addressable-initiator"></a><span data-ttu-id="13ae6-224">Iniciador unidireccional y direccionable</span><span class="sxs-lookup"><span data-stu-id="13ae6-224">One Way, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="13ae6-225">Enlace</span><span class="sxs-lookup"><span data-stu-id="13ae6-225">Binding</span></span>

<span data-ttu-id="13ae6-226">WCF proporciona un patrón de intercambio de mensajes unidireccional utilizando una secuencia sobre un canal http de entrada y de salida.</span><span class="sxs-lookup"><span data-stu-id="13ae6-226">WCF provides a one-way message exchange pattern using one sequence over an inbound and an outbound Http channel.</span></span> <span data-ttu-id="13ae6-227">WCF usa las solicitudes HTTP para transmitir todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="13ae6-227">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="13ae6-228">Todas las respuestas HTTP tienen un cuerpo vacío y código de estado HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="13ae6-228">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="13ae6-229">Intercambio de CreateSequence</span><span class="sxs-lookup"><span data-stu-id="13ae6-229">CreateSequence Exchange</span></span>

<span data-ttu-id="13ae6-230">El iniciador de WCF genera un `CreateSequence` mensaje sin ninguna oferta.</span><span class="sxs-lookup"><span data-stu-id="13ae6-230">The WCF Initiator generates a `CreateSequence` message with no offer.</span></span> <span data-ttu-id="13ae6-231">El respondedor de WCF garantiza que `CreateSequence` no tiene ninguna oferta antes de crear una secuencia.</span><span class="sxs-lookup"><span data-stu-id="13ae6-231">The WCF Responder ensures that the `CreateSequence` has no offer before creating a sequence.</span></span> <span data-ttu-id="13ae6-232">El respondedor de WCF transmite el `CreateSequenceResponse` mensaje en una solicitud HTTP dirigida a la `ReplyTo` referencia de extremo.</span><span class="sxs-lookup"><span data-stu-id="13ae6-232">The WCF Responder transmits the `CreateSequenceResponse` message on an HTTP request addressed with the `ReplyTo` endpoint reference.</span></span>

### <a name="duplex-addressable-initiator"></a><span data-ttu-id="13ae6-233">Iniciador dúplex y direccionable</span><span class="sxs-lookup"><span data-stu-id="13ae6-233">Duplex, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="13ae6-234">Enlace</span><span class="sxs-lookup"><span data-stu-id="13ae6-234">Binding</span></span>

<span data-ttu-id="13ae6-235">WCF proporciona un modelo de intercambio de mensajes bidireccional totalmente asincrónico que usa dos secuencias sobre un canal HTTP de entrada y de salida.</span><span class="sxs-lookup"><span data-stu-id="13ae6-235">WCF provides a fully asynchronous two-way message exchange pattern using two sequences over an inbound and an outbound HTTP channel.</span></span> <span data-ttu-id="13ae6-236">WCF usa las solicitudes HTTP para transmitir todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="13ae6-236">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="13ae6-237">Todas las respuestas HTTP tienen un cuerpo vacío y código de estado HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="13ae6-237">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="13ae6-238">Intercambio de CreateSequence</span><span class="sxs-lookup"><span data-stu-id="13ae6-238">CreateSequence Exchange</span></span>

<span data-ttu-id="13ae6-239">El iniciador de WCF genera un `CreateSequence` mensaje con una oferta.</span><span class="sxs-lookup"><span data-stu-id="13ae6-239">The WCF Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="13ae6-240">El respondedor de WCF garantiza que `CreateSequence` tenga una oferta antes de crear una secuencia.</span><span class="sxs-lookup"><span data-stu-id="13ae6-240">The WCF Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> <span data-ttu-id="13ae6-241">WCF envía el `CreateSequenceResponse` en la solicitud HTTP dirigida a la `CreateSequence` `ReplyTo` referencia de extremo de.</span><span class="sxs-lookup"><span data-stu-id="13ae6-241">WCF sends the `CreateSequenceResponse` on the HTTP request addressed to the `CreateSequence`’s `ReplyTo` endpoint reference.</span></span>

#### <a name="sequence-lifetime"></a><span data-ttu-id="13ae6-242">Duración de la secuencia</span><span class="sxs-lookup"><span data-stu-id="13ae6-242">Sequence Lifetime</span></span>

<span data-ttu-id="13ae6-243">WCF trata las dos secuencias como una sesión totalmente dúplex.</span><span class="sxs-lookup"><span data-stu-id="13ae6-243">WCF treats the two sequences as one fully duplex session.</span></span>

<span data-ttu-id="13ae6-244">Tras generar un error que genera un error en una secuencia, WCF espera que el punto de conexión remoto genere un error en ambas secuencias.</span><span class="sxs-lookup"><span data-stu-id="13ae6-244">Upon generating a fault that faults one sequence, WCF expects the remote endpoint to fault both sequences.</span></span> <span data-ttu-id="13ae6-245">Al leer un error que genera un error en una secuencia, WCF genera un error en ambas secuencias.</span><span class="sxs-lookup"><span data-stu-id="13ae6-245">Upon reading a fault that faults one sequence, WCF faults both sequences.</span></span>

<span data-ttu-id="13ae6-246">WCF puede cerrar su secuencia de salida y continuar procesando los mensajes en la secuencia de entrada.</span><span class="sxs-lookup"><span data-stu-id="13ae6-246">WCF can close its outbound sequence and continue to process messages on its inbound sequence.</span></span> <span data-ttu-id="13ae6-247">Por el contrario, WCF puede procesar el cierre de la secuencia de entrada y continuar enviando mensajes en su secuencia de salida.</span><span class="sxs-lookup"><span data-stu-id="13ae6-247">Conversely, WCF can process the close of the inbound sequence and continue to send messages on its outbound sequence.</span></span>

### <a name="request-reply-non-addressable-initiator"></a><span data-ttu-id="13ae6-248">Iniciador no direccionable de solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="13ae6-248">Request-Reply, Non-Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="13ae6-249">Enlace</span><span class="sxs-lookup"><span data-stu-id="13ae6-249">Binding</span></span>

<span data-ttu-id="13ae6-250">WCF proporciona un modelo de intercambio de mensajes de solicitud-respuesta unidireccional que usa dos secuencias sobre un canal HTTP.</span><span class="sxs-lookup"><span data-stu-id="13ae6-250">WCF provides a one-way and request-reply message exchange pattern using two sequences over one HTTP channel.</span></span> <span data-ttu-id="13ae6-251">WCF usa las solicitudes HTTP para transmitir los mensajes de la secuencia de solicitud y usa las respuestas HTTP para transmitir los mensajes de la secuencia de respuesta.</span><span class="sxs-lookup"><span data-stu-id="13ae6-251">WCF uses the HTTP requests to transmit the request sequence’s messages and uses the HTTP responses to transmit the reply sequence’s messages.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="13ae6-252">Intercambio de CreateSequence</span><span class="sxs-lookup"><span data-stu-id="13ae6-252">CreateSequence Exchange</span></span>

<span data-ttu-id="13ae6-253">El iniciador de WCF genera un `CreateSequence` mensaje con una oferta.</span><span class="sxs-lookup"><span data-stu-id="13ae6-253">The WCF Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="13ae6-254">El respondedor de WCF garantiza que `CreateSequence` tenga una oferta antes de crear una secuencia.</span><span class="sxs-lookup"><span data-stu-id="13ae6-254">The WCF Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> <span data-ttu-id="13ae6-255">El respondedor de WCF responde a la `CreateSequence` solicitud con un `CreateSequenceResponse` mensaje.</span><span class="sxs-lookup"><span data-stu-id="13ae6-255">The WCF Responder replies to the `CreateSequence` request with a `CreateSequenceResponse` message.</span></span>

#### <a name="one-way-message"></a><span data-ttu-id="13ae6-256">Mensaje unidireccional</span><span class="sxs-lookup"><span data-stu-id="13ae6-256">One-way Message</span></span>

<span data-ttu-id="13ae6-257">Para completar correctamente un protocolo de intercambio de mensajes unidireccional, el iniciador de WCF transmite un mensaje de secuencia de solicitud en la solicitud HTTP y recibe un `SequenceAcknowledgement` mensaje independiente en la respuesta http.</span><span class="sxs-lookup"><span data-stu-id="13ae6-257">To complete a one-way message exchange protocol successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a standalone `SequenceAcknowledgement` message on the HTTP response.</span></span> <span data-ttu-id="13ae6-258">La `SequenceAcknowledgement` debe confirmar el mensaje transmitido.</span><span class="sxs-lookup"><span data-stu-id="13ae6-258">The `SequenceAcknowledgement` must acknowledge the message transmitted.</span></span>

<span data-ttu-id="13ae6-259">El respondedor de WCF puede responder a la solicitud con una confirmación, un error o una respuesta con un cuerpo vacío y un código de Estado HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="13ae6-259">The WCF Responder can reply to the request with an acknowledgement, a fault, or a response with an empty body and HTTP 202 status code.</span></span>

#### <a name="two-way-messages"></a><span data-ttu-id="13ae6-260">Mensajes bidireccionales</span><span class="sxs-lookup"><span data-stu-id="13ae6-260">Two Way Messages</span></span>

<span data-ttu-id="13ae6-261">Para completar correctamente un protocolo de intercambio de mensajes bidireccional, el iniciador de WCF transmite un mensaje de secuencia de solicitud en la solicitud HTTP y recibe un mensaje de secuencia de respuesta en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="13ae6-261">To complete a two way message exchange protocol successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a reply sequence message on the HTTP response.</span></span> <span data-ttu-id="13ae6-262">La respuesta debe llevar una `SequenceAcknowledgement` que confirme que se ha transmitido el mensaje de secuencia de solicitud.</span><span class="sxs-lookup"><span data-stu-id="13ae6-262">The response must carry a `SequenceAcknowledgement` acknowledging the request sequence message transmitted.</span></span>

<span data-ttu-id="13ae6-263">El respondedor de WCF puede responder a la solicitud con una respuesta de la aplicación, un error o una respuesta con un cuerpo vacío y un código de Estado HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="13ae6-263">The WCF Responder can reply to the request with an application reply, a fault or a response with an empty body and HTTP 202 status code.</span></span>

<span data-ttu-id="13ae6-264">Debido a la presencia de mensajes unidireccionales y al control de tiempo de las respuestas de la aplicación, el número de secuencia del mensaje de secuencia de solicitud y el número de secuencia del mensaje de respuesta no tienen ninguna correlación.</span><span class="sxs-lookup"><span data-stu-id="13ae6-264">Because of the presence of one-way messages and the timing of application replies, the request sequence message’s sequence number and the response message’s sequence number have no correlation.</span></span>

#### <a name="retrying-replies"></a><span data-ttu-id="13ae6-265">Reintento de respuestas</span><span class="sxs-lookup"><span data-stu-id="13ae6-265">Retrying Replies</span></span>

<span data-ttu-id="13ae6-266">WCF se basa en la correlación de solicitud-respuesta HTTP para la correlación del Protocolo de intercambio de mensajes bidireccional.</span><span class="sxs-lookup"><span data-stu-id="13ae6-266">WCF relies on HTTP request-reply correlation for two-way message exchange protocol correlation.</span></span> <span data-ttu-id="13ae6-267">Debido a esto, el iniciador de WCF no deja de reintentar un mensaje de secuencia de solicitud cuando se confirma el mensaje de secuencia de solicitud, sino cuando la respuesta HTTP lleva una confirmación, un mensaje de usuario o un error.</span><span class="sxs-lookup"><span data-stu-id="13ae6-267">Because of this, the WCF Initiator does not stop retrying a request sequence message when the request sequence message is acknowledged but rather when the HTTP response carries an acknowledgement, user message, or fault.</span></span> <span data-ttu-id="13ae6-268">El respondedor de WCF reintenta las respuestas en el segmento de la solicitud HTTP de la solicitud a la que se correlaciona la respuesta.</span><span class="sxs-lookup"><span data-stu-id="13ae6-268">The WCF Responder retries replies on the HTTP request leg of the request to which the reply is correlated.</span></span>

#### <a name="lastmessage-exchange"></a><span data-ttu-id="13ae6-269">Intercambio de LastMessage</span><span class="sxs-lookup"><span data-stu-id="13ae6-269">LastMessage Exchange</span></span>

<span data-ttu-id="13ae6-270">El iniciador de WCF genera y transmite un último mensaje de cuerpo vacío en la pierna de la solicitud HTTP.</span><span class="sxs-lookup"><span data-stu-id="13ae6-270">The WCF Initiator generates and transmits an empty bodied last message on the HTTP request leg.</span></span> <span data-ttu-id="13ae6-271">WCF requiere una respuesta pero omite el mensaje de respuesta real.</span><span class="sxs-lookup"><span data-stu-id="13ae6-271">WCF requires a response but ignores the actual response message.</span></span> <span data-ttu-id="13ae6-272">El respondedor de WCF responde al último mensaje de cuerpo vacío de la secuencia de la solicitud con el último mensaje de cuerpo vacío de la secuencia de respuesta.</span><span class="sxs-lookup"><span data-stu-id="13ae6-272">The WCF Responder replies to the request sequence’s empty-bodied last message with the reply sequence’s empty-bodied last message.</span></span>

<span data-ttu-id="13ae6-273">Si el respondedor de WCF recibe un último mensaje en el que el URI de la acción no es `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage` , WCF responde con un último mensaje.</span><span class="sxs-lookup"><span data-stu-id="13ae6-273">If the WCF Responder receives a last message in which the action URI is not `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`, WCF replies with a last message.</span></span> <span data-ttu-id="13ae6-274">En el caso de un protocolo de intercambio de mensajes bidireccional, el último mensaje lleva el mensaje de la aplicación; en el caso de un protocolo de intercambio de mensajes unidireccional, el último mensaje está vacío.</span><span class="sxs-lookup"><span data-stu-id="13ae6-274">In the case of a two-way message exchange protocol, the last message carries the application message; in the case of a one-way message exchange protocol, the last message is empty.</span></span>

<span data-ttu-id="13ae6-275">El respondedor de WCF no requiere una confirmación para el último mensaje de cuerpo vacío de la secuencia de respuesta.</span><span class="sxs-lookup"><span data-stu-id="13ae6-275">The WCF Responder does not require an acknowledgement for the reply sequence’s empty-bodied last message.</span></span>

#### <a name="terminatesequence-exchange"></a><span data-ttu-id="13ae6-276">Intercambio de TerminateSequence</span><span class="sxs-lookup"><span data-stu-id="13ae6-276">TerminateSequence Exchange</span></span>

<span data-ttu-id="13ae6-277">Cuando todas las solicitudes han recibido una respuesta válida, el iniciador de WCF genera y transmite el mensaje de la secuencia de solicitud `TerminateSequence` en la pierna de la solicitud HTTP.</span><span class="sxs-lookup"><span data-stu-id="13ae6-277">When all requests have received a valid reply, the WCF Initiator generates and transmits the request sequence’s `TerminateSequence` message on the HTTP request leg.</span></span> <span data-ttu-id="13ae6-278">WCF requiere una respuesta pero omite el mensaje de respuesta real.</span><span class="sxs-lookup"><span data-stu-id="13ae6-278">WCF requires a response but ignores the actual response message.</span></span> <span data-ttu-id="13ae6-279">El respondedor de WCF responde al mensaje de la secuencia de solicitud `TerminateSequence` con el mensaje de la secuencia de respuesta `TerminateSequence` .</span><span class="sxs-lookup"><span data-stu-id="13ae6-279">The WCF Responder replies to the request sequence’s `TerminateSequence` message with the reply sequence’s `TerminateSequence` message.</span></span>

<span data-ttu-id="13ae6-280">En una secuencia de apagado normal, ambos mensajes `TerminateSequence` llevan un `SequenceAcknowledgement` de intervalo completo.</span><span class="sxs-lookup"><span data-stu-id="13ae6-280">In a normal shutdown sequence, both `TerminateSequence` messages carry a full range `SequenceAcknowledgement`.</span></span>

### <a name="requestreply-addressable-initiator"></a><span data-ttu-id="13ae6-281">Iniciador direccionable de solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="13ae6-281">Request/Reply, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="13ae6-282">Enlace</span><span class="sxs-lookup"><span data-stu-id="13ae6-282">Binding</span></span>

<span data-ttu-id="13ae6-283">WCF proporciona un patrón de intercambio de mensajes de solicitud-respuesta que usa dos secuencias sobre un canal HTTP de entrada y de salida.</span><span class="sxs-lookup"><span data-stu-id="13ae6-283">WCF provides a request-reply message exchange pattern using two sequences over an inbound and an outbound HTTP channel.</span></span> <span data-ttu-id="13ae6-284">WCF usa las solicitudes HTTP para transmitir todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="13ae6-284">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="13ae6-285">Todas las respuestas HTTP tienen un cuerpo vacío y código de estado HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="13ae6-285">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="13ae6-286">Intercambio de CreateSequence</span><span class="sxs-lookup"><span data-stu-id="13ae6-286">CreateSequence Exchange</span></span>

<span data-ttu-id="13ae6-287">El iniciador de WCF genera un `CreateSequence` mensaje con una oferta.</span><span class="sxs-lookup"><span data-stu-id="13ae6-287">The WCF Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="13ae6-288">El respondedor de WCF garantiza que `CreateSequence` tenga una oferta antes de crear una secuencia.</span><span class="sxs-lookup"><span data-stu-id="13ae6-288">The WCF Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> <span data-ttu-id="13ae6-289">WCF envía el `CreateSequenceResponse` en la solicitud HTTP dirigida a la `CreateSequence` `ReplyTo` referencia de extremo de.</span><span class="sxs-lookup"><span data-stu-id="13ae6-289">WCF sends the `CreateSequenceResponse` on the HTTP request addressed to the `CreateSequence`’s `ReplyTo` endpoint reference.</span></span>

#### <a name="requestreply-correlation"></a><span data-ttu-id="13ae6-290">Correlación entre solicitud y respuesta</span><span class="sxs-lookup"><span data-stu-id="13ae6-290">Request/Reply Correlation</span></span>

<span data-ttu-id="13ae6-291">El iniciador de WCF garantiza que todos los mensajes de solicitud de aplicación llevan un `MessageId` y una `ReplyTo` referencia de extremo.</span><span class="sxs-lookup"><span data-stu-id="13ae6-291">The WCF Initiator ensures all application request messages bear a `MessageId` and a `ReplyTo` endpoint reference.</span></span> <span data-ttu-id="13ae6-292">El iniciador de WCF aplica la `CreateSequence` referencia de extremo del mensaje `ReplyTo` en cada mensaje de solicitud de aplicación.</span><span class="sxs-lookup"><span data-stu-id="13ae6-292">The WCF Initiator applies the `CreateSequence` message’s `ReplyTo` endpoint reference on each application request message.</span></span> <span data-ttu-id="13ae6-293">El respondedor de WCF requiere que los mensajes de solicitud entrantes lleven un `MessageId` y un `ReplyTo` .</span><span class="sxs-lookup"><span data-stu-id="13ae6-293">The WCF Responder requires that incoming request messages bear a `MessageId` and a `ReplyTo`.</span></span> <span data-ttu-id="13ae6-294">El respondedor de WCF garantiza que el URI de la referencia de extremo de los mensajes de solicitud de la `CreateSequence` aplicación y de todos son idénticos.</span><span class="sxs-lookup"><span data-stu-id="13ae6-294">The WCF Responder ensures that the endpoint reference’s URI of both the `CreateSequence` and all application request messages are identical.</span></span>
