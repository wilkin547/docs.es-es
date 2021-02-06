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
# <a name="reliable-messaging-protocol-version-11"></a><span data-ttu-id="e433f-103">Protocolo de mensajería de confianza versión 1,1</span><span class="sxs-lookup"><span data-stu-id="e433f-103">Reliable Messaging Protocol version 1.1</span></span>

<span data-ttu-id="e433f-104">En este tema se tratan los detalles de implementación de Windows Communication Foundation (WCF) para el protocolo WS-ReliableMessaging 2007 de febrero (versión 1,1) necesario para la interoperación mediante el transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="e433f-104">This topic covers Windows Communication Foundation (WCF) implementation details for the WS-ReliableMessaging February 2007 (version 1.1) protocol necessary for interoperation using the HTTP transport.</span></span> <span data-ttu-id="e433f-105">WCF sigue la especificación de WS-ReliableMessaging con las restricciones y aclaraciones explicadas en este tema.</span><span class="sxs-lookup"><span data-stu-id="e433f-105">WCF follows the WS-ReliableMessaging specification with the constraints and clarifications explained in this topic.</span></span> <span data-ttu-id="e433f-106">Tenga en cuenta que el protocolo WS-ReliableMessaging versión 1,1 se implementa a partir de .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="e433f-106">Note that the WS-ReliableMessaging version 1.1 protocol is implemented starting with .NET Framework 3.5.</span></span>

<span data-ttu-id="e433f-107">El WS-ReliableMessaging el protocolo 2007 de febrero se implementa en WCF <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> .</span><span class="sxs-lookup"><span data-stu-id="e433f-107">The WS-ReliableMessaging February 2007 protocol is implemented in WCF by the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span></span>

<span data-ttu-id="e433f-108">Para su comodidad, el tema utiliza las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="e433f-108">For convenience, the topic uses the following roles:</span></span>

- <span data-ttu-id="e433f-109">Iniciador: el cliente que inicia la creación de la secuencia de mensajes WS-Reliable.</span><span class="sxs-lookup"><span data-stu-id="e433f-109">Initiator: The client that initiates WS-Reliable Message sequence creation.</span></span>

- <span data-ttu-id="e433f-110">Respondedor: el servicio que recibe las solicitudes del iniciador.</span><span class="sxs-lookup"><span data-stu-id="e433f-110">Responder: The service that receives the initiator's requests.</span></span>

 <span data-ttu-id="e433f-111">En este documento, se utilizan los prefijos y espacios de nombres de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e433f-111">This document uses the prefixes and namespaces in the following table.</span></span>

|<span data-ttu-id="e433f-112">Prefijo</span><span class="sxs-lookup"><span data-stu-id="e433f-112">Prefix</span></span>|<span data-ttu-id="e433f-113">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="e433f-113">Namespace</span></span>|
|-|-|
|<span data-ttu-id="e433f-114">wsrm</span><span class="sxs-lookup"><span data-stu-id="e433f-114">wsrm</span></span>|`http://docs.oasis-open.org/ws-rx/wsrm/200702`|
|<span data-ttu-id="e433f-115">netrm</span><span class="sxs-lookup"><span data-stu-id="e433f-115">netrm</span></span>|`http://schemas.microsoft.com/ws/2006/05/rm`|
|<span data-ttu-id="e433f-116">s</span><span class="sxs-lookup"><span data-stu-id="e433f-116">s</span></span>|`http://www.w3.org/2003/05/soap-envelope`|
|<span data-ttu-id="e433f-117">wsa</span><span class="sxs-lookup"><span data-stu-id="e433f-117">wsa</span></span>|`http://schemas.xmlsoap.org/ws/2005/08/addressing`|
|<span data-ttu-id="e433f-118">wsse</span><span class="sxs-lookup"><span data-stu-id="e433f-118">wsse</span></span>|`http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd`|
|<span data-ttu-id="e433f-119">wsrmp</span><span class="sxs-lookup"><span data-stu-id="e433f-119">wsrmp</span></span>|`http://docs.oasis-open.org/ws-rx/wsrmp/200702`|
|<span data-ttu-id="e433f-120">netrmp</span><span class="sxs-lookup"><span data-stu-id="e433f-120">netrmp</span></span>|`http://schemas.microsoft.com/ws-rx/wsrmp/200702`|
|<span data-ttu-id="e433f-121">wsp</span><span class="sxs-lookup"><span data-stu-id="e433f-121">wsp</span></span>|<span data-ttu-id="e433f-122">(Directiva WS-Policy 1.2 o WS-Policy 1.5)</span><span class="sxs-lookup"><span data-stu-id="e433f-122">(Either WS-Policy 1.2 or WS-Policy 1.5)</span></span>|

## <a name="messaging"></a><span data-ttu-id="e433f-123">Mensajería</span><span class="sxs-lookup"><span data-stu-id="e433f-123">Messaging</span></span>

### <a name="sequence-creation"></a><span data-ttu-id="e433f-124">Creación de secuencias</span><span class="sxs-lookup"><span data-stu-id="e433f-124">Sequence Creation</span></span>

<span data-ttu-id="e433f-125">WCF implementa `CreateSequence` mensajes y `CreateSequenceResponse` para establecer una secuencia de mensajería confiable.</span><span class="sxs-lookup"><span data-stu-id="e433f-125">WCF implements `CreateSequence` and `CreateSequenceResponse` messages to establish a reliable messaging sequence.</span></span> <span data-ttu-id="e433f-126">Se aplican las siguientes restricciones:</span><span class="sxs-lookup"><span data-stu-id="e433f-126">The following constraints apply:</span></span>

- <span data-ttu-id="e433f-127">B1101: el iniciador de WCF usa la misma referencia de extremo que el `CreateSequence` del mensaje `ReplyTo` , `AcksTo` y `Offer/Endpoint` .</span><span class="sxs-lookup"><span data-stu-id="e433f-127">B1101: The WCF Initiator uses the same endpoint reference as the `CreateSequence` message’s `ReplyTo`, `AcksTo` and `Offer/Endpoint`.</span></span>

- <span data-ttu-id="e433f-128">R1102: las referencias de punto de conexión `AcksTo`, `ReplyTo` y `Offer/Endpoint` en el mensaje `CreateSequence` deben tener valores de dirección con representaciones de cadena idénticas, de tal modo que coincidan por octetos.</span><span class="sxs-lookup"><span data-stu-id="e433f-128">R1102: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message must have address values with identical string representations such that they match the octet-wise.</span></span>

  - <span data-ttu-id="e433f-129">El respondedor de WCF comprueba que la parte del URI de `AcksTo` las `ReplyTo` `Endpoint` referencias de extremo y son idénticas antes de crear una secuencia.</span><span class="sxs-lookup"><span data-stu-id="e433f-129">The WCF Responder verifies that the URI portion of the `AcksTo`, `ReplyTo` and `Endpoint` endpoint references are identical before creating a sequence.</span></span>

- <span data-ttu-id="e433f-130">R1103: las referencias de punto de conexión `AcksTo`, `ReplyTo` y `Offer/Endpoint` en el mensaje `CreateSequence` deberían tener el mismo conjunto de parámetros de referencia.</span><span class="sxs-lookup"><span data-stu-id="e433f-130">R1103: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message should have the same set of reference parameters.</span></span>

  - <span data-ttu-id="e433f-131">WCF no exige, pero supone que los parámetros de referencia de `AcksTo` `ReplyTo` y `Offer/Endpoint` las referencias de extremo en `CreateSequence` son idénticos y usa parámetros de referencia de la `ReplyTo` referencia de extremo para las confirmaciones y los mensajes de secuencia inversa.</span><span class="sxs-lookup"><span data-stu-id="e433f-131">WCF does not enforce, but assumes that reference parameters of the `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references on `CreateSequence` are identical and uses reference parameters from the `ReplyTo` endpoint reference for acknowledgements and converse sequence messages.</span></span>

- <span data-ttu-id="e433f-132">B1104: el iniciador de WCF no genera el `Expires` elemento opcional o `Offer/Expires` en el `CreateSequence` mensaje.</span><span class="sxs-lookup"><span data-stu-id="e433f-132">B1104: The WCF Initiator does not generate the optional `Expires` or `Offer/Expires` element in the `CreateSequence` message.</span></span>

- <span data-ttu-id="e433f-133">B1105: al obtener acceso al `CreateSequence` mensaje, el respondedor de WCF usa el `Expires` valor del `CreateSequence` elemento como el `Expires` valor del `CreateSequenceResponse` elemento.</span><span class="sxs-lookup"><span data-stu-id="e433f-133">B1105: When accessing the `CreateSequence` message, the WCF Responder uses the `Expires` value in the `CreateSequence` element as the `Expires` value in the `CreateSequenceResponse` element.</span></span> <span data-ttu-id="e433f-134">De lo contrario, el respondedor de WCF Lee y omite los `Expires` `Offer/Expires` valores y.</span><span class="sxs-lookup"><span data-stu-id="e433f-134">Otherwise, the WCF Responder reads and ignores the `Expires` and `Offer/Expires` values.</span></span>

- <span data-ttu-id="e433f-135">B1106: al obtener acceso al `CreateSequenceResponse` mensaje, el iniciador de WCF lee el valor opcional, `Expires` pero no lo usa.</span><span class="sxs-lookup"><span data-stu-id="e433f-135">B1106: When accessing the `CreateSequenceResponse` message, the WCF Initiator reads the optional `Expires` value but does not use it.</span></span>

- <span data-ttu-id="e433f-136">B1107: el iniciador y respondedor de WCF siempre genera el `IncompleteSequenceBehavior` elemento opcional en los `CreateSequence/Offer` `CreateSequenceResponse` elementos y.</span><span class="sxs-lookup"><span data-stu-id="e433f-136">B1107: The WCF Initiator and Responder always generate the optional `IncompleteSequenceBehavior` element in the `CreateSequence/Offer` and `CreateSequenceResponse` elements.</span></span>

- <span data-ttu-id="e433f-137">B1108: WCF solo usa los `DiscardFollowingFirstGap` valores y del `NoDiscard` `IncompleteSequenceBehavior` elemento.</span><span class="sxs-lookup"><span data-stu-id="e433f-137">B1108: WCF uses only the `DiscardFollowingFirstGap` and `NoDiscard` values in the `IncompleteSequenceBehavior` element.</span></span>

  - <span data-ttu-id="e433f-138">WS-ReliableMessaging utiliza el mecanismo `Offer` para establecer las dos secuencias correlacionadas inversas que forman una sesión.</span><span class="sxs-lookup"><span data-stu-id="e433f-138">WS-ReliableMessaging utilizes the `Offer` mechanism to establish the two converse correlated sequences that form a session.</span></span>

- <span data-ttu-id="e433f-139">B1109: Si `CreateSequence` contiene un `Offer` elemento, el respondedor de WCF unidireccional rechaza la secuencia proporcionada respondiendo con una `CreateSequenceResponse` sin un `Accept` elemento.</span><span class="sxs-lookup"><span data-stu-id="e433f-139">B1109: If `CreateSequence` contains an `Offer` element, the one way WCF Responder rejects the offered sequence by responding with a `CreateSequenceResponse` without an `Accept` element.</span></span>

- <span data-ttu-id="e433f-140">B1110: Si un respondedor de mensajería de confianza rechaza la secuencia ofrecida, el iniciador de WCF genera un error en la secuencia recién establecida.</span><span class="sxs-lookup"><span data-stu-id="e433f-140">B1110: If a Reliable Messaging Responder rejects the offered sequence, the WCF Initiator faults the newly established sequence.</span></span>

- <span data-ttu-id="e433f-141">B1111: Si `CreateSequence` no contiene un `Offer` elemento, el respondedor de WCF bidireccional rechaza la secuencia proporcionada respondiendo con un `CreateSequenceRefused` error.</span><span class="sxs-lookup"><span data-stu-id="e433f-141">B1111: If `CreateSequence` does not contain an `Offer` element, the two-way WCF Responder rejects the offered sequence by responding with a `CreateSequenceRefused` fault.</span></span>

- <span data-ttu-id="e433f-142">R1112: cuando dos secuencias inversas se establecen utilizando el mecanismo `Offer`, la propiedad `[address]` de la referencia de punto de conexión `CreateSequenceResponse/Accept/AcksTo` debe coincidir con el URI de destino del mensaje `CreateSequence` byte a byte.</span><span class="sxs-lookup"><span data-stu-id="e433f-142">R1112: When two converse sequences are established using the `Offer` mechanism, the `[address]` property of the `CreateSequenceResponse/Accept/AcksTo` endpoint reference must match the destination URI of the `CreateSequence` message byte for byte.</span></span>

- <span data-ttu-id="e433f-143">R1113: cuando dos secuencias inversas se establecen utilizando el mecanismo `Offer`, todos los mensajes en ambas secuencias que fluyen desde el iniciador hasta el respondedor se deben enviar a la misma referencia de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="e433f-143">R1113: When two converse sequences are established using the `Offer` mechanism, all messages on both sequences flowing from the Initiator to the Responder must be sent to the same endpoint reference.</span></span>

<span data-ttu-id="e433f-144">WCF usa WS-ReliableMessaging para establecer sesiones confiables entre el iniciador y el respondedor.</span><span class="sxs-lookup"><span data-stu-id="e433f-144">WCF uses WS-ReliableMessaging to establish reliable sessions between the Initiator and the Responder.</span></span> <span data-ttu-id="e433f-145">La implementación de WS-ReliableMessaging de WCF proporciona una sesión confiable para patrones de mensajería dúplex completa y de solicitud-respuesta unidireccionales.</span><span class="sxs-lookup"><span data-stu-id="e433f-145">The WCF WS-ReliableMessaging implementation provides a reliable session for one-way, request-reply and full duplex messaging patterns.</span></span> <span data-ttu-id="e433f-146">El mecanismo `Offer` de WS-ReliableMessaging en `CreateSequence` y `CreateSequenceResponse` le permite establecer dos secuencias inversas correlacionadas y proporciona un protocolo de sesión que es apto para todos los puntos de conexión de mensajes.</span><span class="sxs-lookup"><span data-stu-id="e433f-146">The WS-ReliableMessaging `Offer` mechanism on `CreateSequence` and `CreateSequenceResponse` lets you establish two correlated converse sequences and provides a session protocol that is suitable for all message endpoints.</span></span> <span data-ttu-id="e433f-147">Dado que WCF proporciona una garantía de seguridad para este tipo de sesión, incluida la protección de un extremo a otro para la integridad de la sesión, es práctico asegurarse de que los mensajes destinados a la misma parte lleguen al mismo destino.</span><span class="sxs-lookup"><span data-stu-id="e433f-147">Because WCF provides a security guarantee for such a session including end-to-end protection for session integrity, it is practical to ensure that messages intended for the same party arrive at the same destination.</span></span> <span data-ttu-id="e433f-148">Esto también permite el “apoyo a caballo” de confirmaciones de secuencias en mensajes de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e433f-148">This also allows "piggy-backing" of sequence acknowledgements on application messages.</span></span> <span data-ttu-id="e433f-149">Por lo tanto, las restricciones R1102, R1112 y R1113 se aplican a WCF.</span><span class="sxs-lookup"><span data-stu-id="e433f-149">Therefore, constraints R1102, R1112, and R1113 apply to WCF.</span></span>

<span data-ttu-id="e433f-150">Ejemplo de mensaje `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="e433f-150">An example of a `CreateSequence` message.</span></span>

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

<span data-ttu-id="e433f-151">Ejemplo de mensaje `CreateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="e433f-151">An example of a `CreateSequenceResponse` message.</span></span>

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

### <a name="closing-a-sequence"></a><span data-ttu-id="e433f-152">Cierre de una secuencia</span><span class="sxs-lookup"><span data-stu-id="e433f-152">Closing a Sequence</span></span>

<span data-ttu-id="e433f-153">WCF usa los `CloseSequence` `CloseSequenceResponse` mensajes y para un cierre Iniciado por el origen de mensajería de confianza.</span><span class="sxs-lookup"><span data-stu-id="e433f-153">WCF uses the `CloseSequence` and `CloseSequenceResponse` messages for a Reliable Messaging source-initiated shutdown.</span></span> <span data-ttu-id="e433f-154">El destino de la mensajería de confianza de WCF no inicia el cierre y el origen de la mensajería de confianza de WCF no admite el apagado Iniciado por el destino de la mensajería de confianza.</span><span class="sxs-lookup"><span data-stu-id="e433f-154">The WCF Reliable Messaging destination does not initiate shutdown and the WCF Reliable Messaging source does not support a Reliable Messaging destination-initiated shutdown.</span></span> <span data-ttu-id="e433f-155">Se aplican las siguientes restricciones:</span><span class="sxs-lookup"><span data-stu-id="e433f-155">The following constraints apply:</span></span>

- <span data-ttu-id="e433f-156">B1201: el origen de la mensajería de confianza de WCF siempre envía un `CloseSequence` mensaje para cerrar la secuencia.</span><span class="sxs-lookup"><span data-stu-id="e433f-156">B1201: The WCF Reliable Messaging source always sends a `CloseSequence` message to shut down the sequence.</span></span>

- <span data-ttu-id="e433f-157">B1202: el origen de la mensajería de confianza espera la confirmación del intervalo completo de mensajes de secuencia antes de enviar el mensaje `CloseSequence`.</span><span class="sxs-lookup"><span data-stu-id="e433f-157">B1202: The Reliable Messaging source waits for acknowledgement of the full range of sequence messages before sending the `CloseSequence` message.</span></span>

- <span data-ttu-id="e433f-158">B1203: el origen de la mensajería de confianza siempre incluye el elemento opcional `LastMsgNumber`, a menos que la secuencia no contenga mensajes.</span><span class="sxs-lookup"><span data-stu-id="e433f-158">B1203: The Reliable Messaging source always includes the optional `LastMsgNumber` element unless the sequence does not contain messages.</span></span>

- <span data-ttu-id="e433f-159">R1204: el destino de la mensajería de confianza no debe iniciar el cierre mediante el envío de un mensaje `CloseSequence`.</span><span class="sxs-lookup"><span data-stu-id="e433f-159">R1204: The Reliable Messaging destination must not initiate shutdown by sending a `CloseSequence` message.</span></span>

- <span data-ttu-id="e433f-160">B1205: al recibir un `CloseSequence` mensaje, el origen de mensajería confiable de WCF considera que la secuencia está incompleta y envía un error.</span><span class="sxs-lookup"><span data-stu-id="e433f-160">B1205: Upon receiving a `CloseSequence` message, the WCF Reliable Messaging source considers the sequence incomplete and sends a fault.</span></span>

 <span data-ttu-id="e433f-161">Ejemplo de mensaje `CloseSequence`.</span><span class="sxs-lookup"><span data-stu-id="e433f-161">An example of a `CloseSequence` message.</span></span>

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

<span data-ttu-id="e433f-162">Mensaje de ejemplo `CloseSequenceResponse` :</span><span class="sxs-lookup"><span data-stu-id="e433f-162">Example `CloseSequenceResponse` message:</span></span>

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

### <a name="sequence-termination"></a><span data-ttu-id="e433f-163">Finalización de secuencia</span><span class="sxs-lookup"><span data-stu-id="e433f-163">Sequence Termination</span></span>

<span data-ttu-id="e433f-164">WCF usa principalmente el `TerminateSequence/TerminateSequenceResponse` Protocolo de enlace después de completar el `CloseSequence/CloseSequenceResponse` Protocolo de enlace.</span><span class="sxs-lookup"><span data-stu-id="e433f-164">WCF primarily uses the `TerminateSequence/TerminateSequenceResponse` handshake after completing the `CloseSequence/CloseSequenceResponse` handshake.</span></span> <span data-ttu-id="e433f-165">El destino de la mensajería de confianza de WCF no inicia la terminación y el origen de la mensajería de confianza no admite una terminación iniciada por el destino de la mensajería de confianza.</span><span class="sxs-lookup"><span data-stu-id="e433f-165">The WCF Reliable Messaging destination does not initiate termination and the Reliable Messaging source does not support a Reliable Messaging destination-initiated termination.</span></span> <span data-ttu-id="e433f-166">Se aplican las siguientes restricciones:</span><span class="sxs-lookup"><span data-stu-id="e433f-166">The following constraints apply:</span></span>

- <span data-ttu-id="e433f-167">B1301: el iniciador de WCF solo envía el `TerminateSequence` mensaje después de la finalización correcta del `CloseSequence/CloseSequenceResponse` Protocolo de enlace.</span><span class="sxs-lookup"><span data-stu-id="e433f-167">B1301: The WCF Initiator only sends the `TerminateSequence` message after the successful completion of the `CloseSequence/CloseSequenceResponse` handshake.</span></span>

- <span data-ttu-id="e433f-168">R1302: WCF valida que el `LastMsgNumber` elemento es coherente en todos los `CloseSequence` `TerminateSequence` mensajes y para una secuencia determinada.</span><span class="sxs-lookup"><span data-stu-id="e433f-168">R1302: WCF validates that the `LastMsgNumber` element is consistent across all `CloseSequence` and `TerminateSequence` messages for a given sequence.</span></span> <span data-ttu-id="e433f-169">Esto significa que `LastMsgNumber` no está presente en todos los mensajes `CloseSequence` y `TerminateSequence`, o está presente y es idéntico en todos los mensajes `CloseSequence` y `TerminateSequence`.</span><span class="sxs-lookup"><span data-stu-id="e433f-169">This means that `LastMsgNumber` is either not present on all `CloseSequence` and `TerminateSequence` messages, or it is present and identical on all `CloseSequence` and `TerminateSequence` messages.</span></span>

- <span data-ttu-id="e433f-170">B1303: al recibir un mensaje `TerminateSequence` después del protocolo de enlace `CloseSequence/CloseSequenceResponse`, el destino de la mensajería de confianza responde con un mensaje `TerminateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="e433f-170">B1303: When receiving a `TerminateSequence` message after the `CloseSequence/CloseSequenceResponse` handshake, the Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="e433f-171">Puesto que el origen de la mensajería de confianza recibe la confirmación definitiva antes de enviar el mensaje `TerminateSequence`, el destino de la mensajería de confianza sabe sin duda que finaliza la secuencia y reclama recursos inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="e433f-171">Because the Reliable Messaging source has the final acknowledgement before sending the `TerminateSequence` message, the Reliable Messaging destination knows without doubt that the sequence ends, and reclaims resources immediately.</span></span>

- <span data-ttu-id="e433f-172">B1304: al recibir un `TerminateSequence` mensaje antes del `CloseSequence/CloseSequenceResponse` Protocolo de enlace, el destino de la mensajería de confianza de WCF responde con un `TerminateSequenceResponse` mensaje.</span><span class="sxs-lookup"><span data-stu-id="e433f-172">B1304: When receiving a `TerminateSequence` message prior to the `CloseSequence/CloseSequenceResponse` handshake, the WCF Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="e433f-173">Si el destino de la mensajería de confianza determina que no hay incoherencias en la secuencia, el destino de la mensajería de confianza espera durante un tiempo especificado por el destino de la aplicación antes de reclamar recursos, para permitir al cliente que reciba la confirmación final.</span><span class="sxs-lookup"><span data-stu-id="e433f-173">If the Reliable Messaging destination determines that there are no inconsistencies in the sequence, the Reliable Messaging destination waits for an application destination-specified time before reclaiming resources, to allow the client the chance to receive the final acknowledgement.</span></span> <span data-ttu-id="e433f-174">De lo contrario, el destino de la mensajería de confianza reclama recursos inmediatamente e indica al destino de la aplicación que la secuencia finaliza de manera dudosa iniciando el evento `Faulted`.</span><span class="sxs-lookup"><span data-stu-id="e433f-174">Otherwise, the Reliable Messaging destination reclaims resources immediately and indicates to the application destination that the sequence ends with doubt by raising the `Faulted` event.</span></span>

<span data-ttu-id="e433f-175">Ejemplo de mensaje `TerminateSequence`.</span><span class="sxs-lookup"><span data-stu-id="e433f-175">An example of a `TerminateSequence` message.</span></span>

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

<span data-ttu-id="e433f-176">Mensaje de ejemplo `TerminateSequenceResponse` :</span><span class="sxs-lookup"><span data-stu-id="e433f-176">Example `TerminateSequenceResponse` message:</span></span>

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

### <a name="sequences"></a><span data-ttu-id="e433f-177">Secuencias</span><span class="sxs-lookup"><span data-stu-id="e433f-177">Sequences</span></span>

<span data-ttu-id="e433f-178">A continuación, se muestra una lista de restricciones que se aplican a las secuencias:</span><span class="sxs-lookup"><span data-stu-id="e433f-178">The following is a list of constraints that apply to sequences:</span></span>

- <span data-ttu-id="e433f-179">B1401: WCF genera y obtiene acceso a los números de secuencia que no son mayores que el `xs:long` valor inclusivo máximo de 9223372036854775807.</span><span class="sxs-lookup"><span data-stu-id="e433f-179">B1401:WCF generates and accesses sequence numbers no higher than `xs:long`’s maximum inclusive value, 9223372036854775807.</span></span>

<span data-ttu-id="e433f-180">Ejemplo de encabezado `Sequence`.</span><span class="sxs-lookup"><span data-stu-id="e433f-180">An example of a `Sequence` header.</span></span>

```xml
<wsrm:Sequence s:mustUnderstand="1">
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
  <wsrm:MessageNumber>1</wsrm:MessageNumber>
</wsrm:Sequence>
```

### <a name="request-acknowledgement"></a><span data-ttu-id="e433f-181">Solicitar confirmación</span><span class="sxs-lookup"><span data-stu-id="e433f-181">Request Acknowledgement</span></span>

<span data-ttu-id="e433f-182">WCF usa el `AckRequested` encabezado como un mecanismo Keep-Alive.</span><span class="sxs-lookup"><span data-stu-id="e433f-182">WCF uses the `AckRequested` header as a keep-alive mechanism.</span></span>

<span data-ttu-id="e433f-183">Ejemplo de encabezado `AckRequested`.</span><span class="sxs-lookup"><span data-stu-id="e433f-183">An example of an `AckRequested` header.</span></span>

```xml
<wsrm:AckRequested>
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
</wsrm:AckRequested>
```

### <a name="sequenceacknowledgement"></a><span data-ttu-id="e433f-184">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="e433f-184">SequenceAcknowledgement</span></span>

<span data-ttu-id="e433f-185">WCF usa un mecanismo de "reutilizable" para las confirmaciones de secuencias proporcionadas en WS-Reliable mensajería.</span><span class="sxs-lookup"><span data-stu-id="e433f-185">WCF uses a "piggy-back" mechanism for sequence acknowledgements provided in WS-Reliable Messaging.</span></span> <span data-ttu-id="e433f-186">Se aplican las siguientes restricciones:</span><span class="sxs-lookup"><span data-stu-id="e433f-186">The following constraints apply:</span></span>

- <span data-ttu-id="e433f-187">R1601: cuando dos secuencias inversas se establecen utilizando el `Offer` mecanismo, el `SequenceAcknowledgement` encabezado puede estar incluido en cualquier mensaje de aplicación transmitido al destinatario previsto.</span><span class="sxs-lookup"><span data-stu-id="e433f-187">R1601: When two converse sequences are established using the `Offer` mechanism, the `SequenceAcknowledgement` header may be included in any application message transmitted to the intended recipient.</span></span> <span data-ttu-id="e433f-188">El extremo remoto debe poder tener acceso a un encabezado `SequenceAcknowledgement` superpuesto.</span><span class="sxs-lookup"><span data-stu-id="e433f-188">The remote endpoint must be able to access a piggybacked `SequenceAcknowledgement` header.</span></span>

- <span data-ttu-id="e433f-189">B1602: WCF no genera `SequenceAcknowledgement` encabezados que contengan `Nack` elementos.</span><span class="sxs-lookup"><span data-stu-id="e433f-189">B1602: WCF does not generate `SequenceAcknowledgement` headers that contain `Nack` elements.</span></span> <span data-ttu-id="e433f-190">WCF valida que cada `Nack` elemento contiene un número de secuencia, pero de lo contrario omite el `Nack` elemento y el valor.</span><span class="sxs-lookup"><span data-stu-id="e433f-190">WCF validates that each `Nack` element contains a sequence number, but otherwise ignores the `Nack` element and value.</span></span>

 <span data-ttu-id="e433f-191">Ejemplo de encabezado `SequenceAcknowledgement`.</span><span class="sxs-lookup"><span data-stu-id="e433f-191">An example of a `SequenceAcknowledgement` header.</span></span>

```xml
<wsrm:SequenceAcknowledgement>
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
  <wsrm:AcknowledgementRange Lower="1" Upper="1"></wsrm:AcknowledgementRange>
</wsrm:SequenceAcknowledgement>
```

### <a name="ws-reliablemessaging-faults"></a><span data-ttu-id="e433f-192">Errores de WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="e433f-192">WS-ReliableMessaging Faults</span></span>

<span data-ttu-id="e433f-193">A continuación se muestra una lista de restricciones que se aplican a la implementación de WCF de WS-ReliableMessaging errores.</span><span class="sxs-lookup"><span data-stu-id="e433f-193">The following is a list of constraints that apply to the WCF implementation of WS-ReliableMessaging faults.</span></span> <span data-ttu-id="e433f-194">Se aplican las siguientes restricciones:</span><span class="sxs-lookup"><span data-stu-id="e433f-194">The following constraints apply:</span></span>

- <span data-ttu-id="e433f-195">B1701: WCF no genera `MessageNumberRollover` errores.</span><span class="sxs-lookup"><span data-stu-id="e433f-195">B1701: WCF does not generate `MessageNumberRollover` faults.</span></span>

- <span data-ttu-id="e433f-196">B1702: sobre SOAP 1,2, cuando el extremo de servicio alcanza su límite de conexiones y no puede procesar nuevas conexiones, WCF genera un `CreateSequenceRefused` subcódigo de error anidado, `netrm:ConnectionLimitReached` , como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="e433f-196">B1702: Over SOAP 1.2, when the service endpoint reaches its connection limit and cannot process new connections, WCF generates a nested `CreateSequenceRefused` fault subcode, `netrm:ConnectionLimitReached`, as shown in the following example.</span></span>

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

### <a name="ws-addressing-faults"></a><span data-ttu-id="e433f-197">Errores WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="e433f-197">WS-Addressing Faults</span></span>

<span data-ttu-id="e433f-198">Dado que WS-ReliableMessaging usa WS-Addressing, la implementación de WS-ReliableMessaging de WCF puede generar y transmitir errores de WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="e433f-198">Because WS-ReliableMessaging uses WS-Addressing, the WCF WS-ReliableMessaging implementation may generate and transmit WS-Addressing faults.</span></span> <span data-ttu-id="e433f-199">En esta sección se tratan los errores de WS-Addressing que WCF genera y transmite explícitamente en el nivel de WS-ReliableMessaging:</span><span class="sxs-lookup"><span data-stu-id="e433f-199">This section covers the WS-Addressing faults that WCF explicitly generates and transmits at the WS-ReliableMessaging layer:</span></span>

- <span data-ttu-id="e433f-200">B1801: WCF genera y transmite el `Message Addressing Header Required` error cuando se cumple una de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="e433f-200">B1801:WCF generates and transmits the `Message Addressing Header Required` fault when one of the following is true:</span></span>

  - <span data-ttu-id="e433f-201">A un mensaje `CreateSequence`, `CloseSequence`, o `TerminateSequence` le falta un encabezado `MessageId`.</span><span class="sxs-lookup"><span data-stu-id="e433f-201">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `MessageId` header.</span></span>

  - <span data-ttu-id="e433f-202">A un mensaje `CreateSequence`, `CloseSequence`, o `TerminateSequence` le falta un encabezado `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="e433f-202">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `ReplyTo` header.</span></span>

  - <span data-ttu-id="e433f-203">A un mensaje `CreateSequenceResponse`, `CloseSequenceResponse`, o `TerminateSequenceResponse` le falta un encabezado `RelatesTo`.</span><span class="sxs-lookup"><span data-stu-id="e433f-203">A `CreateSequenceResponse`, `CloseSequenceResponse`, or `TerminateSequenceResponse` message is missing a `RelatesTo` header.</span></span>

- <span data-ttu-id="e433f-204">B1802: WCF genera y transmite el `Endpoint Unavailable` error para indicar que no hay ningún extremo escuchando que pueda procesar la secuencia en función del examen de los encabezados de direccionamiento en el `CreateSequence` mensaje.</span><span class="sxs-lookup"><span data-stu-id="e433f-204">B1802:WCF generates and transmits the `Endpoint Unavailable` fault to indicate there is no endpoint listening that can process the sequence based on examination of the addressing headers in the `CreateSequence` message.</span></span>

## <a name="protocol-composition"></a><span data-ttu-id="e433f-205">Composición de protocolos</span><span class="sxs-lookup"><span data-stu-id="e433f-205">Protocol Composition</span></span>

### <a name="composition-with-ws-addressing"></a><span data-ttu-id="e433f-206">Composición con WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="e433f-206">Composition with WS-Addressing</span></span>

<span data-ttu-id="e433f-207">WCF admite dos versiones de WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] y las recomendaciones de W3C WS-Addressing 1,0 [WS-ADDR-CORE] y [WS-ADDR-SOAP].</span><span class="sxs-lookup"><span data-stu-id="e433f-207">WCF supports two versions of WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] and W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] and [WS-ADDR-SOAP].</span></span>

<span data-ttu-id="e433f-208">Aunque la especificación de WS-ReliableMessaging solo menciona WS-Addressing 2004/08, no restringe la versión de WS-Addressing que se ha de utilizar.</span><span class="sxs-lookup"><span data-stu-id="e433f-208">While the WS-ReliableMessaging specification mentions only WS-Addressing 2004/08, it does not restrict the WS-Addressing version to be used.</span></span> <span data-ttu-id="e433f-209">A continuación se muestra una lista de restricciones que se aplican a WCF:</span><span class="sxs-lookup"><span data-stu-id="e433f-209">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="e433f-210">R2101: WS-Addressing 2004/08 y WS-Addressing 1.0 se pueden utilizar con la mensajería de confianza de WS.</span><span class="sxs-lookup"><span data-stu-id="e433f-210">R2101: Both WS-Addressing 2004/08 and WS-Addressing 1.0 can be used with WS-Reliable Messaging.</span></span>

- <span data-ttu-id="e433f-211">R2102: se debe utilizar una única versión de WS-Addressing a lo largo de una secuencia de WS-ReliableMessaging determinada o un par de secuencias inversas correlacionadas mediante el mecanismo `Offer`.</span><span class="sxs-lookup"><span data-stu-id="e433f-211">R2102: A single version of WS-Addressing must be used throughout a given WS-ReliableMessaging sequence or a pair of converse sequences correlated by using the `Offer` mechanism.</span></span>

### <a name="composition-with-soap"></a><span data-ttu-id="e433f-212">Composición con SOAP</span><span class="sxs-lookup"><span data-stu-id="e433f-212">Composition with SOAP</span></span>

<span data-ttu-id="e433f-213">WCF admite el uso de SOAP 1,1 y SOAP 1,2 con WS-Reliable mensajería.</span><span class="sxs-lookup"><span data-stu-id="e433f-213">WCF supports the use of both SOAP 1.1 and SOAP 1.2 with WS-Reliable Messaging.</span></span>

### <a name="composition-with-ws-security-and-ws-secureconversation"></a><span data-ttu-id="e433f-214">Composición con WS-Security y WS-SecureConversation</span><span class="sxs-lookup"><span data-stu-id="e433f-214">Composition with WS-Security and WS-SecureConversation</span></span>

<span data-ttu-id="e433f-215">WCF proporciona protección para WS-ReliableMessaging secuencias mediante el transporte seguro (HTTPS), la composición con WS-Security y la composición con WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="e433f-215">WCF provides protection for WS-ReliableMessaging sequences by using secure Transport (HTTPS), composition with WS-Security, and composition with WS-Secure Conversation.</span></span> <span data-ttu-id="e433f-216">Los protocolos WS-ReliableMessaging 1.1, WS-Security 1.1 y WS-Secure Conversation 1.3 deberían utilizarse conjuntamente.</span><span class="sxs-lookup"><span data-stu-id="e433f-216">The WS-ReliableMessaging 1.1 protocol, WS-Security 1.1 and WS-Secure Conversation 1.3 protocol should be used together.</span></span> <span data-ttu-id="e433f-217">A continuación se muestra una lista de restricciones que se aplican a WCF:</span><span class="sxs-lookup"><span data-stu-id="e433f-217">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="e433f-218">R2301: para proteger la integridad de una secuencia de WS-ReliableMessaging además de la integridad y confidencialidad de los mensajes individuales, WCF requiere que se use WS-Secure conversación.</span><span class="sxs-lookup"><span data-stu-id="e433f-218">R2301: To protect the integrity of a WS-ReliableMessaging sequence in addition to the integrity and confidentiality of individual messages, WCF requires that WS-Secure Conversation must be used.</span></span>

- <span data-ttu-id="e433f-219">R2302:una sesión de WS-Secure Conversation se debe establecer antes de establecer las secuencias de WS-ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="e433f-219">R2302:AWS-Secure Conversation session must be established prior to establishing WS-ReliableMessaging sequence(s).</span></span>

- <span data-ttu-id="e433f-220">R2303: si la duración de la secuencia de WS-ReliableMessaging supera la duración de la sesión de WS-Secure Conversation, el `SecurityContextToken` establecido mediante WS-Secure Conversation se debe renovar utilizando el enlace de renovación de WS-Secure Conversation correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e433f-220">R2303: If the WS-ReliableMessaging sequence lifetime exceeds the WS-Secure Conversation session’s lifetime, the `SecurityContextToken` established by using WS-Secure Conversation must be renewed by using the corresponding WS-Secure Conversation Renewal binding.</span></span>

- <span data-ttu-id="e433f-221">B2304:La secuencia de WS-ReliableMessaging o un par de secuencias inversas correlacionadas siempre se enlazan a una única sesión de WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="e433f-221">B2304:WS-ReliableMessaging sequence or a pair of correlated converse sequences are always bound to a single WS-SecureConversation session.</span></span>

- <span data-ttu-id="e433f-222">R2305: cuando se crea con WS-Secure Conversation, el respondedor de WCF requiere que el `CreateSequence` mensaje contenga el `wsse:SecurityTokenReference` elemento y el `wsrm:UsesSequenceSTR` encabezado.</span><span class="sxs-lookup"><span data-stu-id="e433f-222">R2305: When composed with WS-Secure Conversation, the WCF responder requires that the `CreateSequence` message contain the `wsse:SecurityTokenReference` element and the `wsrm:UsesSequenceSTR` header.</span></span>

 <span data-ttu-id="e433f-223">Ejemplo de encabezado `UsesSequenceSTR`.</span><span class="sxs-lookup"><span data-stu-id="e433f-223">An example of a `UsesSequenceSTR` header.</span></span>

```xml
<wsrm:UsesSequenceSTR></wsrm:UsesSequenceSTR>
```

### <a name="composition-with-ssltls-sessions"></a><span data-ttu-id="e433f-224">Composición con sesiones de SSL/TLS</span><span class="sxs-lookup"><span data-stu-id="e433f-224">Composition with SSL/TLS sessions</span></span>

<span data-ttu-id="e433f-225">WCF no admite la composición con sesiones SSL/TLS:</span><span class="sxs-lookup"><span data-stu-id="e433f-225">WCF does not support composition with SSL/TLS sessions:</span></span>

- <span data-ttu-id="e433f-226">B2401: WCF no genera el `wsrm:UsesSequenceSSL` encabezado.</span><span class="sxs-lookup"><span data-stu-id="e433f-226">B2401: WCF does not generate the `wsrm:UsesSequenceSSL` header.</span></span>

- <span data-ttu-id="e433f-227">R2402: un iniciador de mensajería de confianza no debe enviar un `CreateSequence` mensaje con un `wsrm:UsesSequenceSSL` encabezado a un respondedor de WCF.</span><span class="sxs-lookup"><span data-stu-id="e433f-227">R2402: A Reliable Messaging Initiator must not send a `CreateSequence` message with a `wsrm:UsesSequenceSSL` header to a WCF Responder.</span></span>

### <a name="composition-with-ws-policy"></a><span data-ttu-id="e433f-228">Composición con WS-Policy</span><span class="sxs-lookup"><span data-stu-id="e433f-228">Composition with WS-Policy</span></span>

<span data-ttu-id="e433f-229">WCF admite dos versiones de WS-Policy: WS-Policy 1,2 y WS-Policy 1,5.</span><span class="sxs-lookup"><span data-stu-id="e433f-229">WCF supports two versions of WS-Policy: WS-Policy 1.2 and WS-Policy 1.5.</span></span>

## <a name="ws-reliablemessaging-ws-policy-assertion"></a><span data-ttu-id="e433f-230">Aserción de WS-Policy de WS-ReliableMessaging </span><span class="sxs-lookup"><span data-stu-id="e433f-230">WS-ReliableMessaging WS-Policy Assertion</span></span>

<span data-ttu-id="e433f-231">WCF usa WS-ReliableMessaging WS-Policy aserción `wsrm:RMAssertion` para describir las capacidades de los extremos.</span><span class="sxs-lookup"><span data-stu-id="e433f-231">WCF uses WS-ReliableMessaging WS-Policy Assertion `wsrm:RMAssertion` to describe endpoints capabilities.</span></span> <span data-ttu-id="e433f-232">A continuación se muestra una lista de restricciones que se aplican a WCF:</span><span class="sxs-lookup"><span data-stu-id="e433f-232">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="e433f-233">B3001: WCF asocia `wsrmn:RMAssertion` WS-Policy aserción a `wsdl:binding` los elementos.</span><span class="sxs-lookup"><span data-stu-id="e433f-233">B3001: WCF attaches `wsrmn:RMAssertion` WS-Policy Assertion to `wsdl:binding` elements.</span></span> <span data-ttu-id="e433f-234">WCF admite datos adjuntos `wsdl:binding` a `wsdl:port` elementos y.</span><span class="sxs-lookup"><span data-stu-id="e433f-234">WCF supports both attachments to `wsdl:binding` and `wsdl:port` elements.</span></span>

- <span data-ttu-id="e433f-235">B3002: WCF nunca genera la `wsp:Optional` etiqueta.</span><span class="sxs-lookup"><span data-stu-id="e433f-235">B3002: WCF never generates the `wsp:Optional` tag.</span></span>

- <span data-ttu-id="e433f-236">B3003: al obtener acceso a la `wsrmp:RMAssertion` aserción de WS-Policy, WCF omite la `wsp:Optional` etiqueta y trata la Directiva de WS-RM como obligatoria.</span><span class="sxs-lookup"><span data-stu-id="e433f-236">B3003: When accessing the `wsrmp:RMAssertion` WS-Policy Assertion, WCF ignores the `wsp:Optional` tag and treats the WS-RM policy as mandatory.</span></span>

- <span data-ttu-id="e433f-237">R3004: dado que WCF no se compone con sesiones SSL/TLS, WCF no acepta la Directiva que especifica `wsrmp:SequenceTransportSecurity` .</span><span class="sxs-lookup"><span data-stu-id="e433f-237">R3004: Because WCF does not compose with SSL/TLS sessions, WCF does not accept policy that specifies `wsrmp:SequenceTransportSecurity`.</span></span>

- <span data-ttu-id="e433f-238">B3005: WCF siempre genera el `wsrmp:DeliveryAssurance` elemento.</span><span class="sxs-lookup"><span data-stu-id="e433f-238">B3005: WCF always generates the `wsrmp:DeliveryAssurance` element.</span></span>

- <span data-ttu-id="e433f-239">B3006: WCF siempre especifica la `wsrmp:ExactlyOnce` garantía de entrega.</span><span class="sxs-lookup"><span data-stu-id="e433f-239">B3006: WCF always specifies the `wsrmp:ExactlyOnce` delivery assurance.</span></span>

- <span data-ttu-id="e433f-240">B3007: WCF genera y Lee las siguientes propiedades de la aserción WS-ReliableMessaging y proporciona control sobre ellas en WCF `ReliableSessionBindingElement` :</span><span class="sxs-lookup"><span data-stu-id="e433f-240">B3007: WCF generates and reads the following properties of the WS-ReliableMessaging assertion and provides control over them on the WCF`ReliableSessionBindingElement`:</span></span>

  - `netrmp:InactivityTimeout`

  - `netrmp:AcknowledgementInterval`

  <span data-ttu-id="e433f-241">Ejemplo de `RMAssertion`.</span><span class="sxs-lookup"><span data-stu-id="e433f-241">An example of a `RMAssertion`.</span></span>

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

## <a name="flow-control-ws-reliablemessaging-extension"></a><span data-ttu-id="e433f-242">Extensión de WS-ReliableMessaging de control de flujo</span><span class="sxs-lookup"><span data-stu-id="e433f-242">Flow Control WS-ReliableMessaging Extension</span></span>

<span data-ttu-id="e433f-243">WCF usa la extensibilidad de WS-ReliableMessaging para proporcionar un control adicional más estrecho opcional sobre el flujo de mensajes de secuencia.</span><span class="sxs-lookup"><span data-stu-id="e433f-243">WCF uses WS-ReliableMessaging extensibility to provide optional additional tighter control over sequence message flow.</span></span>

<span data-ttu-id="e433f-244">El control de flujo se habilita estableciendo la <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> propiedad en `true` .</span><span class="sxs-lookup"><span data-stu-id="e433f-244">Flow control is enabled by setting the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="e433f-245">A continuación se muestra una lista de restricciones que se aplican a WCF:</span><span class="sxs-lookup"><span data-stu-id="e433f-245">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="e433f-246">B4001: cuando está habilitado el control de flujo de la mensajería de confianza, WCF genera un `netrm:BufferRemaining` elemento en la extensibilidad de elementos del `SequenceAcknowledgement` encabezado, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="e433f-246">B4001: When Reliable Messaging Flow Control is enabled, WCF generates a `netrm:BufferRemaining` element in the element extensibility of the `SequenceAcknowledgement` header, as shown in the following example.</span></span>

  ```xml
  <wsrm:SequenceAcknowledgement>
    <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
    <wsrm:AcknowledgementRange Upper="1" Lower="1"/>
    <netrm:BufferRemaining>8</netrm:BufferRemaining>
  </wsrm:SequenceAcknowledgement>
  ```

- <span data-ttu-id="e433f-247">B4002: incluso cuando está habilitado el control de flujo de mensajería de confianza, WCF no requiere un `netrm:BufferRemaining` elemento en el `SequenceAcknowledgement` encabezado.</span><span class="sxs-lookup"><span data-stu-id="e433f-247">B4002: Even when Reliable Messaging Flow Control is enabled, WCF does not require a `netrm:BufferRemaining` element in the `SequenceAcknowledgement` header.</span></span>

- <span data-ttu-id="e433f-248">B4003: el destino de la mensajería confiable de WCF usa `netrm:BufferRemaining` para indicar cuántos mensajes nuevos puede almacenar en búfer.</span><span class="sxs-lookup"><span data-stu-id="e433f-248">B4003: WCF Reliable Messaging Destination uses `netrm:BufferRemaining` to indicate how many new messages it can buffer.</span></span>

- <span data-ttu-id="e433f-249">B4004: cuando está habilitado el control de flujo de la mensajería de confianza, el origen de mensajería confiable de WCF usa el valor de `netrm:BufferRemaining` para limitar la transmisión de mensajes.</span><span class="sxs-lookup"><span data-stu-id="e433f-249">B4004:When Reliable Messaging Flow Control is enabled, the WCF Reliable Messaging Source uses the value of `netrm:BufferRemaining` to throttle message transmission.</span></span>

- <span data-ttu-id="e433f-250">B4005: WCF genera `netrm:BufferRemaining` valores enteros entre 0 y 4096, ambos inclusive, y Lee valores enteros entre 0 y `xs:int` el `maxInclusive` valor 214748364, ambos inclusive.</span><span class="sxs-lookup"><span data-stu-id="e433f-250">B4005: WCF generates `netrm:BufferRemaining` integer values between 0 and 4096 inclusive, and reads integer values between 0 and `xs:int`’s `maxInclusive` value 214748364 inclusive.</span></span>

## <a name="message-exchange-patterns"></a><span data-ttu-id="e433f-251">Modelos de intercambio de mensajes</span><span class="sxs-lookup"><span data-stu-id="e433f-251">Message Exchange Patterns</span></span>

<span data-ttu-id="e433f-252">En esta sección se describe el comportamiento de WCF cuando WS-ReliableMessaging se usa para diferentes patrones de intercambio de mensajes.</span><span class="sxs-lookup"><span data-stu-id="e433f-252">This section describes WCF's behavior when WS-ReliableMessaging is used for different Message Exchange Patterns.</span></span> <span data-ttu-id="e433f-253">Para cada patrón de intercambio de mensajes, se consideran los dos escenarios de implementación siguientes:</span><span class="sxs-lookup"><span data-stu-id="e433f-253">For each Message Exchange Pattern the following two deployments scenarios are considered:</span></span>

- <span data-ttu-id="e433f-254">Iniciador no direccionable: el iniciador está tras un firewall; el respondedor solo puede entregar mensajes al iniciador mediante respuestas HTTP.</span><span class="sxs-lookup"><span data-stu-id="e433f-254">Non-Addressable Initiator: Initiator is behind a firewall; Responder can deliver messages to the Initiator only on HTTP responses.</span></span>

- <span data-ttu-id="e433f-255">Iniciador direccionable: el iniciador y el respondedor pueden enviar solicitudes HTTP; en otras palabras, se pueden establecer dos conexiones HTTP inversas.</span><span class="sxs-lookup"><span data-stu-id="e433f-255">Addressable Initiator: Initiator and Responder both can be sent HTTP requests; in other words, two converse HTTP connections can be established.</span></span>

### <a name="one-way-non-addressable-initiator"></a><span data-ttu-id="e433f-256">Iniciador unidireccional no direccionable</span><span class="sxs-lookup"><span data-stu-id="e433f-256">One-way, Non-addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="e433f-257">Enlace</span><span class="sxs-lookup"><span data-stu-id="e433f-257">Binding</span></span>

<span data-ttu-id="e433f-258">WCF proporciona un patrón de intercambio de mensajes unidireccional utilizando una secuencia sobre un canal HTTP.</span><span class="sxs-lookup"><span data-stu-id="e433f-258">WCF provides a one-way message exchange pattern using one sequence over one HTTP channel.</span></span> <span data-ttu-id="e433f-259">WCF usa solicitudes HTTP para transmitir todos los mensajes desde el iniciador al respondedor y respuestas HTTP para transmitir todos los mensajes del respondedor al iniciador.</span><span class="sxs-lookup"><span data-stu-id="e433f-259">WCF uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="e433f-260">Intercambio de CreateSequence</span><span class="sxs-lookup"><span data-stu-id="e433f-260">CreateSequence Exchange</span></span>

<span data-ttu-id="e433f-261">El iniciador de WCF transmite un `CreateSequence` mensaje sin `Offer` elemento en una solicitud HTTP y espera el `CreateSequenceResponse` mensaje en la respuesta http.</span><span class="sxs-lookup"><span data-stu-id="e433f-261">The WCF Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="e433f-262">El respondedor de WCF crea una secuencia y transmite el `CreateSequenceResponse` mensaje sin ningún `Accept` elemento en la respuesta http.</span><span class="sxs-lookup"><span data-stu-id="e433f-262">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on the HTTP response.</span></span>

#### <a name="sequenceacknowledgement"></a><span data-ttu-id="e433f-263">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="e433f-263">SequenceAcknowledgement</span></span>

<span data-ttu-id="e433f-264">El iniciador de WCF procesa las confirmaciones en la respuesta de todos los mensajes excepto el `CreateSequence` mensaje y los mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="e433f-264">The WCF Initiator processes acknowledgements on the reply of all messages except the `CreateSequence` message and fault messages.</span></span> <span data-ttu-id="e433f-265">El respondedor de WCF siempre transmite una confirmación independiente en la respuesta HTTP a todas las secuencias y `AckRequested` mensajes.</span><span class="sxs-lookup"><span data-stu-id="e433f-265">The WCF Responder always transmits a stand-alone acknowledgement on the HTTP response to all sequence and `AckRequested` messages.</span></span>

#### <a name="closesequence-exchange"></a><span data-ttu-id="e433f-266">Intercambio de CloseSequence</span><span class="sxs-lookup"><span data-stu-id="e433f-266">CloseSequence Exchange</span></span>

<span data-ttu-id="e433f-267">El iniciador de WCF transmite un `CloseSequence` mensaje en una solicitud HTTP y espera el `CreateSequenceResponse` mensaje en la respuesta http.</span><span class="sxs-lookup"><span data-stu-id="e433f-267">The WCF Initiator transmits a `CloseSequence` message on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="e433f-268">El respondedor de WCF transmite el `CloseSequenceResponse` mensaje en la respuesta http.</span><span class="sxs-lookup"><span data-stu-id="e433f-268">The WCF Responder transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>

#### <a name="terminatesequence-exchange"></a><span data-ttu-id="e433f-269">Intercambio de TerminateSequence</span><span class="sxs-lookup"><span data-stu-id="e433f-269">TerminateSequence Exchange</span></span>

<span data-ttu-id="e433f-270">El iniciador de WCF transmite un `TerminateSequence` mensaje en una solicitud HTTP y espera el `TerminateSequenceResponse` mensaje en la respuesta http.</span><span class="sxs-lookup"><span data-stu-id="e433f-270">The WCF Initiator transmits a `TerminateSequence` message on an HTTP request and expects the `TerminateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="e433f-271">El respondedor de WCF transmite el `TerminateSequenceResponse` mensaje en la respuesta http.</span><span class="sxs-lookup"><span data-stu-id="e433f-271">The WCF Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>

### <a name="one-way-addressable-initiator"></a><span data-ttu-id="e433f-272">Iniciador unidireccional y direccionable</span><span class="sxs-lookup"><span data-stu-id="e433f-272">One Way, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="e433f-273">Enlace</span><span class="sxs-lookup"><span data-stu-id="e433f-273">Binding</span></span>

<span data-ttu-id="e433f-274">WCF proporciona un patrón de intercambio de mensajes unidireccional utilizando una secuencia sobre un canal HTTP entrante y otro saliente.</span><span class="sxs-lookup"><span data-stu-id="e433f-274">WCF provides a one-way message exchange pattern using one sequence over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="e433f-275">WCF usa las solicitudes HTTP para transmitir todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="e433f-275">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="e433f-276">Todas las respuestas HTTP tienen un cuerpo vacío y código de estado HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="e433f-276">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="e433f-277">Intercambio de CreateSequence</span><span class="sxs-lookup"><span data-stu-id="e433f-277">CreateSequence Exchange</span></span>

<span data-ttu-id="e433f-278">El iniciador de WCF transmite un `CreateSequence` mensaje sin `Offer` elemento en una solicitud HTTP.</span><span class="sxs-lookup"><span data-stu-id="e433f-278">The WCF Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request.</span></span> <span data-ttu-id="e433f-279">El respondedor de WCF crea una secuencia y transmite el `CreateSequenceResponse` mensaje sin ningún `Accept` elemento en una solicitud HTTP.</span><span class="sxs-lookup"><span data-stu-id="e433f-279">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on an HTTP request.</span></span>

### <a name="duplex-addressable-initiator"></a><span data-ttu-id="e433f-280">Iniciador dúplex y direccionable</span><span class="sxs-lookup"><span data-stu-id="e433f-280">Duplex, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="e433f-281">Enlace</span><span class="sxs-lookup"><span data-stu-id="e433f-281">Binding</span></span>

<span data-ttu-id="e433f-282">WCF proporciona un patrón de intercambio de mensajes bidireccional totalmente asincrónico que usa dos secuencias sobre un canal HTTP entrante y otro saliente.</span><span class="sxs-lookup"><span data-stu-id="e433f-282">WCF provides a fully-asynchronous, two-way message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="e433f-283">Este patrón de intercambio de mensajes se puede mezclar con el patrón de intercambio de mensajes del iniciador de `Request/Reply`, `Addressable` de una manera limitada.</span><span class="sxs-lookup"><span data-stu-id="e433f-283">This message exchange pattern can be mixed with the `Request/Reply`, `Addressable` Initiator message exchange pattern in a limited way.</span></span> <span data-ttu-id="e433f-284">WCF usa solicitudes HTTP para transmitir todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="e433f-284">WCF uses HTTP requests to transmit all messages.</span></span> <span data-ttu-id="e433f-285">Todas las respuestas HTTP tienen un cuerpo vacío y código de estado HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="e433f-285">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="e433f-286">Intercambio de CreateSequence</span><span class="sxs-lookup"><span data-stu-id="e433f-286">CreateSequence Exchange</span></span>

<span data-ttu-id="e433f-287">El iniciador de WCF transmite un `CreateSequence` mensaje con un `Offer` elemento en una solicitud HTTP.</span><span class="sxs-lookup"><span data-stu-id="e433f-287">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="e433f-288">El respondedor de WCF garantiza que `CreateSequence` tiene un `Offer` elemento y, a continuación, crea una secuencia y transmite el `CreateSequenceResponse` mensaje con un `Accept` elemento.</span><span class="sxs-lookup"><span data-stu-id="e433f-288">The WCF Responder ensures that the `CreateSequence` has an `Offer` element, then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>

#### <a name="sequence-lifetime"></a><span data-ttu-id="e433f-289">Duración de la secuencia</span><span class="sxs-lookup"><span data-stu-id="e433f-289">Sequence Lifetime</span></span>

<span data-ttu-id="e433f-290">WCF trata las dos secuencias como una sesión totalmente dúplex.</span><span class="sxs-lookup"><span data-stu-id="e433f-290">WCF treats the two sequences as one fully-duplex session.</span></span>

<span data-ttu-id="e433f-291">Tras generar un error que genera un error en una secuencia, WCF espera que el punto de conexión remoto genere un error en ambas secuencias.</span><span class="sxs-lookup"><span data-stu-id="e433f-291">Upon generating a fault that faults one sequence, WCF expects the remote endpoint to fault both sequences.</span></span> <span data-ttu-id="e433f-292">Al leer un error que genera un error en una secuencia, WCF genera un error en ambas secuencias.</span><span class="sxs-lookup"><span data-stu-id="e433f-292">Upon reading a fault that faults one sequence, WCF faults both sequences.</span></span>

<span data-ttu-id="e433f-293">WCF puede cerrar su secuencia de salida y continuar procesando los mensajes en la secuencia de entrada.</span><span class="sxs-lookup"><span data-stu-id="e433f-293">WCF can close its outbound sequence and continue to process messages on its inbound sequence.</span></span> <span data-ttu-id="e433f-294">Por el contrario, WCF puede procesar el cierre de la secuencia de entrada y continuar enviando mensajes en su secuencia de salida.</span><span class="sxs-lookup"><span data-stu-id="e433f-294">Conversely, WCF can process the close of the inbound sequence and continue to send messages on its outbound sequence.</span></span>

### <a name="request-reply-and-one-way-non-addressable-initiator"></a><span data-ttu-id="e433f-295">Iniciador de solicitud-respuesta unidireccional y no direccionable</span><span class="sxs-lookup"><span data-stu-id="e433f-295">Request-Reply and One-Way, Non-Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="e433f-296">Enlace</span><span class="sxs-lookup"><span data-stu-id="e433f-296">Binding</span></span>

<span data-ttu-id="e433f-297">WCF proporciona un modelo de intercambio de mensajes de solicitud-respuesta unidireccional que usa dos secuencias sobre un canal HTTP.</span><span class="sxs-lookup"><span data-stu-id="e433f-297">WCF provides a one-way and request-reply message exchange pattern using two sequences over one HTTP channel.</span></span> <span data-ttu-id="e433f-298">WCF usa solicitudes HTTP para transmitir todos los mensajes desde el iniciador al respondedor y respuestas HTTP para transmitir todos los mensajes del respondedor al iniciador.</span><span class="sxs-lookup"><span data-stu-id="e433f-298">WCF uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="e433f-299">Intercambio de CreateSequence</span><span class="sxs-lookup"><span data-stu-id="e433f-299">CreateSequence Exchange</span></span>

<span data-ttu-id="e433f-300">El iniciador de WCF transmite un `CreateSequence` mensaje con un `Offer` elemento en una solicitud HTTP y espera el `CreateSequenceResponse` mensaje en la respuesta http.</span><span class="sxs-lookup"><span data-stu-id="e433f-300">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="e433f-301">El respondedor de WCF crea una secuencia y transmite el `CreateSequenceResponse` mensaje con un `Accept` elemento en la respuesta http.</span><span class="sxs-lookup"><span data-stu-id="e433f-301">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element on the HTTP response.</span></span>

#### <a name="one-way-message"></a><span data-ttu-id="e433f-302">Mensaje unidireccional</span><span class="sxs-lookup"><span data-stu-id="e433f-302">One-way Message</span></span>

<span data-ttu-id="e433f-303">Para completar correctamente un intercambio de mensajes unidireccional, el iniciador de WCF transmite un mensaje de secuencia de solicitud en la solicitud HTTP y recibe un `SequenceAcknowledgement` mensaje independiente en la respuesta http.</span><span class="sxs-lookup"><span data-stu-id="e433f-303">To complete a one-way message exchange successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a standalone `SequenceAcknowledgement` message on the HTTP response.</span></span> <span data-ttu-id="e433f-304">La `SequenceAcknowledgement` debe confirmar el mensaje transmitido.</span><span class="sxs-lookup"><span data-stu-id="e433f-304">The `SequenceAcknowledgement` must acknowledge the message transmitted.</span></span>

<span data-ttu-id="e433f-305">El respondedor de WCF puede responder a la solicitud con una confirmación, un error o una respuesta con un cuerpo vacío y un código de Estado HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="e433f-305">The WCF Responder may reply to the request with an acknowledgement, a fault, or a response with an empty body and HTTP 202 status code.</span></span>

#### <a name="two-way-messages"></a><span data-ttu-id="e433f-306">Mensajes bidireccionales</span><span class="sxs-lookup"><span data-stu-id="e433f-306">Two Way Messages</span></span>

<span data-ttu-id="e433f-307">Para completar correctamente un protocolo de intercambio de mensajes bidireccional, el iniciador de WCF transmite un mensaje de secuencia de solicitud en la solicitud HTTP y recibe un mensaje de secuencia de respuesta en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="e433f-307">To complete a two way message exchange protocol successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a reply sequence message on the HTTP response.</span></span> <span data-ttu-id="e433f-308">La respuesta debe llevar una `SequenceAcknowledgement` que confirme que se ha transmitido el mensaje de secuencia de solicitud.</span><span class="sxs-lookup"><span data-stu-id="e433f-308">The response must carry a `SequenceAcknowledgement` acknowledging the request sequence message transmitted.</span></span>

<span data-ttu-id="e433f-309">El respondedor de WCF puede responder a la solicitud con una respuesta de la aplicación, un error o una respuesta con un cuerpo vacío y un código de Estado HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="e433f-309">The WCF Responder may reply to the request with an application reply, a fault or a response with an empty body and HTTP 202 status code.</span></span>

<span data-ttu-id="e433f-310">Debido a la presencia de mensajes unidireccionales y al control de tiempo de las respuestas de la aplicación, el número de secuencia del mensaje de secuencia de solicitud y el número de secuencia del mensaje de respuesta no tienen ninguna correlación.</span><span class="sxs-lookup"><span data-stu-id="e433f-310">Because of the presence of one-way messages and the timing of application replies, the request sequence message’s sequence number and the response message’s sequence number have no correlation.</span></span>

#### <a name="retrying-replies"></a><span data-ttu-id="e433f-311">Reintento de respuestas</span><span class="sxs-lookup"><span data-stu-id="e433f-311">Retrying Replies</span></span>

<span data-ttu-id="e433f-312">WCF se basa en la correlación de solicitud-respuesta HTTP para la correlación del Protocolo de intercambio de mensajes bidireccional.</span><span class="sxs-lookup"><span data-stu-id="e433f-312">WCF relies on HTTP request-reply correlation for two-way message exchange protocol correlation.</span></span> <span data-ttu-id="e433f-313">Debido a esto, el iniciador de WCF no deja de reintentar un mensaje de secuencia de solicitud cuando se confirma el mensaje de secuencia de solicitud, sino cuando la respuesta HTTP lleva una, una respuesta de la `SequenceAcknowledgement` aplicación o un error.</span><span class="sxs-lookup"><span data-stu-id="e433f-313">Because of this, the WCF Initiator does not stop retrying a request sequence message when the request sequence message is acknowledged but rather when the HTTP response carries a `SequenceAcknowledgement`, application reply, or fault.</span></span> <span data-ttu-id="e433f-314">El respondedor de WCF reintenta las respuestas en la respuesta HTTP de la solicitud a la que se correlaciona la respuesta.</span><span class="sxs-lookup"><span data-stu-id="e433f-314">The WCF Responder retries replies on the HTTP response of the request to which the reply is correlated.</span></span>

#### <a name="closesequence-exchange"></a><span data-ttu-id="e433f-315">Intercambio de CloseSequence</span><span class="sxs-lookup"><span data-stu-id="e433f-315">CloseSequence Exchange</span></span>

<span data-ttu-id="e433f-316">Después de recibir todos los mensajes de secuencia de respuesta y las confirmaciones de todos los mensajes de secuencia de solicitud unidireccional, el iniciador de WCF transmite un `CloseSequence` mensaje para la secuencia de solicitud en una solicitud HTTP y espera la `CloseSequenceResponse` en la respuesta http.</span><span class="sxs-lookup"><span data-stu-id="e433f-316">After receiving all reply sequence messages and acknowledgements for all one way request sequence messages, the WCF Initiator transmits a `CloseSequence` message for the request sequence on an HTTP request and expects the `CloseSequenceResponse` on the HTTP response.</span></span>

<span data-ttu-id="e433f-317">Al cerrar implícitamente la secuencia de la solicitud, se cierra la secuencia de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="e433f-317">Closing the request sequence implicitly closes the reply sequence.</span></span> <span data-ttu-id="e433f-318">Esto significa que el iniciador de WCF incluye el final de la secuencia `SequenceAcknowledgement` de respuesta en el `CloseSequence` mensaje y la secuencia de respuesta no tiene un `CloseSequence` intercambio.</span><span class="sxs-lookup"><span data-stu-id="e433f-318">This means the WCF Initiator includes the reply sequence’s Final `SequenceAcknowledgement` on the `CloseSequence` message and the reply sequence does not have a `CloseSequence` exchange.</span></span>

<span data-ttu-id="e433f-319">El respondedor de WCF garantiza que todas las respuestas se reconocen y transmite el `CloseSequenceResponse` mensaje en la respuesta http.</span><span class="sxs-lookup"><span data-stu-id="e433f-319">The WCF Responder ensures all replies are acknowledged and transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>

#### <a name="terminatesequence-exchange"></a><span data-ttu-id="e433f-320">Intercambio de TerminateSequence</span><span class="sxs-lookup"><span data-stu-id="e433f-320">TerminateSequence Exchange</span></span>

<span data-ttu-id="e433f-321">Después de recibir el `CloseSequenceResponse` mensaje, el iniciador de WCF transmite un `TerminateSequence` mensaje para la secuencia de solicitud en una solicitud HTTP y espera la `TerminateSequenceResponse` en la respuesta http.</span><span class="sxs-lookup"><span data-stu-id="e433f-321">After receiving the `CloseSequenceResponse` message, the WCF Initiator transmits a `TerminateSequence` message for the request sequence on an HTTP request and expects the `TerminateSequenceResponse` on the HTTP response.</span></span>

<span data-ttu-id="e433f-322">Al igual que en el intercambio de `CloseSequence`, al finalizar la secuencia de solicitud, se finaliza la secuencia de respuesta.</span><span class="sxs-lookup"><span data-stu-id="e433f-322">Like the `CloseSequence` exchange, terminating the request sequence implicitly terminates the reply sequence.</span></span> <span data-ttu-id="e433f-323">Esto significa que el iniciador de WCF incluye el final de la secuencia `SequenceAcknowledgement` de respuesta en el `TerminateSequence` mensaje y la secuencia de respuesta no tiene un `TerminateSequence` intercambio.</span><span class="sxs-lookup"><span data-stu-id="e433f-323">This means the WCF Initiator includes the reply sequence’s final `SequenceAcknowledgement` on the `TerminateSequence` message and the reply sequence does not have a `TerminateSequence` exchange.</span></span>

<span data-ttu-id="e433f-324">El respondedor de WCF transmite el `TerminateSequenceResponse` mensaje en la respuesta http.</span><span class="sxs-lookup"><span data-stu-id="e433f-324">The WCF Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>

### <a name="requestreply-addressable-initiator"></a><span data-ttu-id="e433f-325">Iniciador direccionable de solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="e433f-325">Request/Reply, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="e433f-326">Enlace</span><span class="sxs-lookup"><span data-stu-id="e433f-326">Binding</span></span>

<span data-ttu-id="e433f-327">WCF proporciona un patrón de intercambio de mensajes de solicitud-respuesta con dos secuencias sobre un canal HTTP entrante y uno saliente.</span><span class="sxs-lookup"><span data-stu-id="e433f-327">WCF provides a request-reply message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="e433f-328">Este patrón de intercambio de mensajes se puede mezclar con el patrón de intercambio de mensajes del iniciador de `Duplex, Addressable` de una manera limitada.</span><span class="sxs-lookup"><span data-stu-id="e433f-328">This message exchange pattern can be mixed with the `Duplex, Addressable` Initiator message exchange pattern in a limited way.</span></span> <span data-ttu-id="e433f-329">WCF usa las solicitudes HTTP para transmitir todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="e433f-329">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="e433f-330">Todas las respuestas HTTP tienen un cuerpo vacío y código de estado HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="e433f-330">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="e433f-331">Intercambio de CreateSequence</span><span class="sxs-lookup"><span data-stu-id="e433f-331">CreateSequence Exchange</span></span>

<span data-ttu-id="e433f-332">El iniciador de WCF transmite un `CreateSequence` mensaje con un `Offer` elemento en una solicitud HTTP.</span><span class="sxs-lookup"><span data-stu-id="e433f-332">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="e433f-333">El respondedor de WCF garantiza que `CreateSequence` tiene un `Offer` elemento, a continuación, crea una secuencia y transmite el `CreateSequenceResponse` mensaje con un `Accept` elemento.</span><span class="sxs-lookup"><span data-stu-id="e433f-333">The WCF Responder ensures that the `CreateSequence` has an `Offer` element then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>

#### <a name="requestreply-correlation"></a><span data-ttu-id="e433f-334">Correlación entre solicitud y respuesta</span><span class="sxs-lookup"><span data-stu-id="e433f-334">Request/Reply Correlation</span></span>

<span data-ttu-id="e433f-335">Lo siguiente se aplica a todas las solicitudes y respuestas correlacionadas:</span><span class="sxs-lookup"><span data-stu-id="e433f-335">The following applies to all correlated requests and replies:</span></span>

- <span data-ttu-id="e433f-336">WCF garantiza que todos los mensajes de solicitud de aplicación llevan una `ReplyTo` referencia de extremo y un `MessageId` .</span><span class="sxs-lookup"><span data-stu-id="e433f-336">WCF ensures all application request messages bear a `ReplyTo` endpoint reference and a `MessageId`.</span></span>

- <span data-ttu-id="e433f-337">WCF aplica la referencia de punto de conexión local como cada mensaje de solicitud de aplicación `ReplyTo` .</span><span class="sxs-lookup"><span data-stu-id="e433f-337">WCF applies the local endpoint reference as each application request message’s `ReplyTo`.</span></span> <span data-ttu-id="e433f-338">La referencia del punto de conexión local es la `CreateSequence` del mensaje `ReplyTo` para el iniciador y la `CreateSequence` del mensaje `To` para el respondedor.</span><span class="sxs-lookup"><span data-stu-id="e433f-338">The local endpoint reference is the `CreateSequence` message’s `ReplyTo` for the Initiator and the `CreateSequence` message’s `To` for the Responder.</span></span>

- <span data-ttu-id="e433f-339">WCF garantiza que los mensajes de solicitud entrantes lleven un `MessageId` y un `ReplyTo` .</span><span class="sxs-lookup"><span data-stu-id="e433f-339">WCF ensures that incoming request messages bear a `MessageId` and a `ReplyTo`.</span></span>

- <span data-ttu-id="e433f-340">WCF garantiza que el `ReplyTo` URI de la referencia de extremo de todos los mensajes de solicitud de aplicación coincide con la referencia de punto de conexión local tal y como se definió anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e433f-340">WCF ensures the `ReplyTo` endpoint reference’s URI of all application request messages match the local endpoint reference as defined earlier.</span></span>

- <span data-ttu-id="e433f-341">WCF garantiza que todas las respuestas llevan los `RelatesTo` encabezados y correctos `To` después de `wsa` las reglas de correlación de solicitud/respuesta.</span><span class="sxs-lookup"><span data-stu-id="e433f-341">WCF ensures that all replies bear the correct `RelatesTo` and `To` headers following `wsa` request/reply correlation rules.</span></span>
