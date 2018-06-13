---
title: Protocolo de mensajería de confianza versión 1,1
ms.date: 03/30/2017
ms.assetid: 0da47b82-f8eb-42da-8bfe-e56ce7ba6f59
ms.openlocfilehash: 8ff02bc6953ec1e5030dd0b592a352b7e23ab0d6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33496963"
---
# <a name="reliable-messaging-protocol-version-11"></a><span data-ttu-id="724a6-102">Protocolo de mensajería de confianza versión 1,1</span><span class="sxs-lookup"><span data-stu-id="724a6-102">Reliable Messaging Protocol version 1.1</span></span>
<span data-ttu-id="724a6-103">Este tema cubre los detalles de implementación de Windows Communication Foundation (WCF) de WS-ReliableMessaging protocolo de febrero de 2007 (versión 1.1) necesario para la interoperación mediante el transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="724a6-103">This topic covers Windows Communication Foundation (WCF) implementation details for the WS-ReliableMessaging February 2007 (version 1.1) protocol necessary for interoperation using the HTTP transport.</span></span> <span data-ttu-id="724a6-104">WCF sigue la especificación de WS-ReliableMessaging con las restricciones y clarificaciones explicadas en este tema.</span><span class="sxs-lookup"><span data-stu-id="724a6-104">WCF follows the WS-ReliableMessaging specification with the constraints and clarifications explained in this topic.</span></span> <span data-ttu-id="724a6-105">Tenga en cuenta que la versión 1.1 del protocolo WS-ReliableMessaging se implementa a partir de la [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="724a6-105">Note that the WS-ReliableMessaging version 1.1 protocol is implemented starting with the [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)].</span></span>  
  
 <span data-ttu-id="724a6-106">WS-ReliableMessaging de febrero de 2007 protocolo se implementa en WCF mediante el <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="724a6-106">The WS-ReliableMessaging February 2007 protocol is implemented in WCF by the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span></span>  
  
 <span data-ttu-id="724a6-107">Para su comodidad, el tema utiliza las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="724a6-107">For convenience, the topic uses the following roles:</span></span>  
  
-   <span data-ttu-id="724a6-108">Iniciador: el cliente que inicia la creación de la secuencia de mensajes WS-Reliable.</span><span class="sxs-lookup"><span data-stu-id="724a6-108">Initiator: The client that initiates WS-Reliable Message sequence creation.</span></span>  
  
-   <span data-ttu-id="724a6-109">Respondedor: el servicio que recibe las solicitudes del iniciador.</span><span class="sxs-lookup"><span data-stu-id="724a6-109">Responder: The service that receives the initiator's requests.</span></span>  
  
 <span data-ttu-id="724a6-110">En este documento, se utilizan los prefijos y espacios de nombres de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="724a6-110">This document uses the prefixes and namespaces in the following table.</span></span>  
  
|<span data-ttu-id="724a6-111">Prefijo</span><span class="sxs-lookup"><span data-stu-id="724a6-111">Prefix</span></span>|<span data-ttu-id="724a6-112">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="724a6-112">Namespace</span></span>|  
|-|-|  
|<span data-ttu-id="724a6-113">wsrm</span><span class="sxs-lookup"><span data-stu-id="724a6-113">wsrm</span></span>|http://docs.oasis-open.org/ws-rx/wsrm/200702|  
|<span data-ttu-id="724a6-114">netrm</span><span class="sxs-lookup"><span data-stu-id="724a6-114">netrm</span></span>|http://schemas.microsoft.com/ws/2006/05/rm|  
|<span data-ttu-id="724a6-115">s</span><span class="sxs-lookup"><span data-stu-id="724a6-115">s</span></span>|http://www.w3.org/2003/05/soap-envelope|  
|<span data-ttu-id="724a6-116">wsa</span><span class="sxs-lookup"><span data-stu-id="724a6-116">wsa</span></span>|http://schemas.xmlsoap.org/ws/2005/08/addressing|  
|<span data-ttu-id="724a6-117">wsse</span><span class="sxs-lookup"><span data-stu-id="724a6-117">wsse</span></span>|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd|  
|<span data-ttu-id="724a6-118">wsrmp</span><span class="sxs-lookup"><span data-stu-id="724a6-118">wsrmp</span></span>|http://docs.oasis-open.org/ws-rx/wsrmp/200702|  
|<span data-ttu-id="724a6-119">netrmp</span><span class="sxs-lookup"><span data-stu-id="724a6-119">netrmp</span></span>|http://schemas.microsoft.com/ws-rx/wsrmp/200702|  
|<span data-ttu-id="724a6-120">wsp</span><span class="sxs-lookup"><span data-stu-id="724a6-120">wsp</span></span>|<span data-ttu-id="724a6-121">(Directiva WS-Policy 1.2 o WS-Policy 1.5)</span><span class="sxs-lookup"><span data-stu-id="724a6-121">(Either WS-Policy 1.2 or WS-Policy 1.5)</span></span>|  
  
## <a name="messaging"></a><span data-ttu-id="724a6-122">Mensajería</span><span class="sxs-lookup"><span data-stu-id="724a6-122">Messaging</span></span>  
  
### <a name="sequence-creation"></a><span data-ttu-id="724a6-123">Creación de secuencias</span><span class="sxs-lookup"><span data-stu-id="724a6-123">Sequence Creation</span></span>  
 <span data-ttu-id="724a6-124">WCF implementa `CreateSequence` y `CreateSequenceResponse` de secuencia de mensajes para establecer una mensajería de confianza.</span><span class="sxs-lookup"><span data-stu-id="724a6-124">WCF implements `CreateSequence` and `CreateSequenceResponse` messages to establish a reliable messaging sequence.</span></span> <span data-ttu-id="724a6-125">Las siguientes restricciones son aplicables:</span><span class="sxs-lookup"><span data-stu-id="724a6-125">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="724a6-126">B1101: El iniciador de WCF usa la misma referencia de punto de conexión que el `CreateSequence` del mensaje `ReplyTo`, `AcksTo` y `Offer/Endpoint`.</span><span class="sxs-lookup"><span data-stu-id="724a6-126">B1101: The WCF Initiator uses the same endpoint reference as the `CreateSequence` message’s `ReplyTo`, `AcksTo` and `Offer/Endpoint`.</span></span>  
  
-   <span data-ttu-id="724a6-127">R1102: las referencias de extremo `AcksTo`, `ReplyTo` y `Offer/Endpoint` en el mensaje `CreateSequence` deben tener valores de dirección con representaciones de cadena idénticas, de tal modo que coincidan por octetos.</span><span class="sxs-lookup"><span data-stu-id="724a6-127">R1102: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message must have address values with identical string representations such that they match the octet-wise.</span></span>  
  
    -   <span data-ttu-id="724a6-128">El servicio de respuesta WCF comprueba que la parte del URI del `AcksTo`, `ReplyTo` y `Endpoint` referencias de extremo sean idénticas antes de crear una secuencia.</span><span class="sxs-lookup"><span data-stu-id="724a6-128">The WCF Responder verifies that the URI portion of the `AcksTo`, `ReplyTo` and `Endpoint` endpoint references are identical before creating a sequence.</span></span>  
  
-   <span data-ttu-id="724a6-129">R1103: las referencias de extremo `AcksTo`, `ReplyTo` y `Offer/Endpoint` en el mensaje `CreateSequence` deberían tener el mismo conjunto de parámetros de referencia.</span><span class="sxs-lookup"><span data-stu-id="724a6-129">R1103: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message should have the same set of reference parameters.</span></span>  
  
    -   <span data-ttu-id="724a6-130">WCF no exige, pero se da por supuesto que hacen referencia a parámetros de la `AcksTo`, `ReplyTo` y `Offer/Endpoint` referencias de extremo en `CreateSequence` son idénticas y utiliza los parámetros de referencia de la `ReplyTo` referencia de extremo para confirmaciones y los mensajes de secuencia inversa.</span><span class="sxs-lookup"><span data-stu-id="724a6-130">WCF does not enforce, but assumes that reference parameters of the `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references on `CreateSequence` are identical and uses reference parameters from the `ReplyTo` endpoint reference for acknowledgements and converse sequence messages.</span></span>  
  
-   <span data-ttu-id="724a6-131">B1104: El iniciador de WCF no genera opcional `Expires` o `Offer/Expires` elemento en el `CreateSequence` mensaje.</span><span class="sxs-lookup"><span data-stu-id="724a6-131">B1104: The WCF Initiator does not generate the optional `Expires` or `Offer/Expires` element in the `CreateSequence` message.</span></span>  
  
-   <span data-ttu-id="724a6-132">B1105: Al tener acceso a la `CreateSequence` mensaje, el servicio de respuesta WCF utiliza el `Expires` valor en el `CreateSequence` elemento como el `Expires` valor en el `CreateSequenceResponse` elemento.</span><span class="sxs-lookup"><span data-stu-id="724a6-132">B1105: When accessing the `CreateSequence` message, the WCF Responder uses the `Expires` value in the `CreateSequence` element as the `Expires` value in the `CreateSequenceResponse` element.</span></span> <span data-ttu-id="724a6-133">En caso contrario, el servicio de respuesta WCF lee y pasa por alto el `Expires` y `Offer/Expires` valores.</span><span class="sxs-lookup"><span data-stu-id="724a6-133">Otherwise, the WCF Responder reads and ignores the `Expires` and `Offer/Expires` values.</span></span>  
  
-   <span data-ttu-id="724a6-134">B1106: Al tener acceso a la `CreateSequenceResponse` mensaje, el iniciador de WCF lee opcional `Expires` valor pero no la usa.</span><span class="sxs-lookup"><span data-stu-id="724a6-134">B1106: When accessing the `CreateSequenceResponse` message, the WCF Initiator reads the optional `Expires` value but does not use it.</span></span>  
  
-   <span data-ttu-id="724a6-135">B1107: El iniciador de WCF y el contestador siempre generan opcional `IncompleteSequenceBehavior` elemento en el `CreateSequence/Offer` y `CreateSequenceResponse` elementos.</span><span class="sxs-lookup"><span data-stu-id="724a6-135">B1107: The WCF Initiator and Responder always generate the optional `IncompleteSequenceBehavior` element in the `CreateSequence/Offer` and `CreateSequenceResponse` elements.</span></span>  
  
-   <span data-ttu-id="724a6-136">B1108: WCF usa solo la `DiscardFollowingFirstGap` y `NoDiscard` valores en el `IncompleteSequenceBehavior` elemento.</span><span class="sxs-lookup"><span data-stu-id="724a6-136">B1108: WCF uses only the `DiscardFollowingFirstGap` and `NoDiscard` values in the `IncompleteSequenceBehavior` element.</span></span>  
  
    -   <span data-ttu-id="724a6-137">WS-ReliableMessaging utiliza el mecanismo `Offer` para establecer las dos secuencias correlacionadas inversas que forman una sesión.</span><span class="sxs-lookup"><span data-stu-id="724a6-137">WS-ReliableMessaging utilizes the `Offer` mechanism to establish the two converse correlated sequences that form a session.</span></span>  
  
-   <span data-ttu-id="724a6-138">B1109: Si `CreateSequence` contiene un `Offer` elemento, el servicio de respuesta WCF unidireccional rechaza la secuencia proporcionada respondiendo con un `CreateSequenceResponse` sin un `Accept` elemento.</span><span class="sxs-lookup"><span data-stu-id="724a6-138">B1109: If `CreateSequence` contains an `Offer` element, the one way WCF Responder rejects the offered sequence by responding with a `CreateSequenceResponse` without an `Accept` element.</span></span>  
  
-   <span data-ttu-id="724a6-139">B1110: Si un Respondedor de mensajería de confianza rechaza la secuencia proporcionada, el iniciador de WCF produce un error en la secuencia recientemente establecida.</span><span class="sxs-lookup"><span data-stu-id="724a6-139">B1110: If a Reliable Messaging Responder rejects the offered sequence, the WCF Initiator faults the newly established sequence.</span></span>  
  
-   <span data-ttu-id="724a6-140">B1111: Si `CreateSequence` no contiene una `Offer` elemento, el servicio de respuesta WCF bidireccional rechaza la secuencia proporcionada respondiendo con un `CreateSequenceRefused` error.</span><span class="sxs-lookup"><span data-stu-id="724a6-140">B1111: If `CreateSequence` does not contain an `Offer` element, the two-way WCF Responder rejects the offered sequence by responding with a `CreateSequenceRefused` fault.</span></span>  
  
-   <span data-ttu-id="724a6-141">R1112: cuando dos secuencias inversas se establecen utilizando el mecanismo `Offer`, la propiedad `[address]` de la referencia de extremo `CreateSequenceResponse/Accept/AcksTo` debe coincidir con el URI de destino del mensaje `CreateSequence` byte a byte.</span><span class="sxs-lookup"><span data-stu-id="724a6-141">R1112: When two converse sequences are established using the `Offer` mechanism, the `[address]` property of the `CreateSequenceResponse/Accept/AcksTo` endpoint reference must match the destination URI of the `CreateSequence` message byte for byte.</span></span>  
  
-   <span data-ttu-id="724a6-142">R1113: cuando dos secuencias inversas se establecen utilizando el mecanismo `Offer`, todos los mensajes en ambas secuencias que fluyen desde el iniciador hasta el respondedor se deben enviar a la misma referencia de extremo.</span><span class="sxs-lookup"><span data-stu-id="724a6-142">R1113: When two converse sequences are established using the `Offer` mechanism, all messages on both sequences flowing from the Initiator to the Responder must be sent to the same endpoint reference.</span></span>  
  
 <span data-ttu-id="724a6-143">WCF usa WS-ReliableMessaging para establecer sesiones confiables entre el iniciador y el Respondedor.</span><span class="sxs-lookup"><span data-stu-id="724a6-143">WCF uses WS-ReliableMessaging to establish reliable sessions between the Initiator and the Responder.</span></span> <span data-ttu-id="724a6-144">La implementación de WS-ReliableMessaging de WCF proporciona una sesión confiable para completa y de solicitud-respuesta unidireccional, patrones de mensajería dúplex.</span><span class="sxs-lookup"><span data-stu-id="724a6-144">The WCF WS-ReliableMessaging implementation provides a reliable session for one-way, request-reply and full duplex messaging patterns.</span></span> <span data-ttu-id="724a6-145">El mecanismo `Offer` de WS-ReliableMessaging en `CreateSequence` y `CreateSequenceResponse` le permite establecer dos secuencias inversas correlacionadas y proporciona un protocolo de sesión que es apto para todos los extremos de mensajes.</span><span class="sxs-lookup"><span data-stu-id="724a6-145">The WS-ReliableMessaging `Offer` mechanism on `CreateSequence` and `CreateSequenceResponse` lets you establish two correlated converse sequences and provides a session protocol that is suitable for all message endpoints.</span></span> <span data-ttu-id="724a6-146">Dado que WCF proporciona una garantía de seguridad para este tipo de sesión incluida la protección de extremo a extremo para la integridad de la sesión, es práctico para asegurarse de que los mensajes dirigidos a la misma parte lleguen al mismo destino.</span><span class="sxs-lookup"><span data-stu-id="724a6-146">Because WCF provides a security guarantee for such a session including end-to-end protection for session integrity, it is practical to ensure that messages intended for the same party arrive at the same destination.</span></span> <span data-ttu-id="724a6-147">Esto también permite el “apoyo a caballo” de confirmaciones de secuencias en mensajes de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="724a6-147">This also allows "piggy-backing" of sequence acknowledgements on application messages.</span></span> <span data-ttu-id="724a6-148">Por lo tanto, se aplican restricciones R1102, R1112 y R1113 a WCF.</span><span class="sxs-lookup"><span data-stu-id="724a6-148">Therefore, constraints R1102, R1112, and R1113 apply to WCF.</span></span>  
  
 <span data-ttu-id="724a6-149">Ejemplo de mensaje `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="724a6-149">An example of a `CreateSequence` message.</span></span>  
  
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
  
 <span data-ttu-id="724a6-150">Ejemplo de mensaje `CreateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="724a6-150">An example of a `CreateSequenceResponse` message.</span></span>  
  
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
  
### <a name="closing-a-sequence"></a><span data-ttu-id="724a6-151">Cierre de una secuencia</span><span class="sxs-lookup"><span data-stu-id="724a6-151">Closing a Sequence</span></span>  
 <span data-ttu-id="724a6-152">WCF usa la `CloseSequence` y `CloseSequenceResponse` mensajes para un cierre iniciado por el origen de mensajería confiable.</span><span class="sxs-lookup"><span data-stu-id="724a6-152">WCF uses the `CloseSequence` and `CloseSequenceResponse` messages for a Reliable Messaging source-initiated shutdown.</span></span> <span data-ttu-id="724a6-153">El destino de mensajería confiable de WCF no inicia el cierre y el origen de mensajería confiable de WCF no admite un cierre iniciado por el destino de la mensajería de confianza.</span><span class="sxs-lookup"><span data-stu-id="724a6-153">The WCF Reliable Messaging destination does not initiate shutdown and the WCF Reliable Messaging source does not support a Reliable Messaging destination-initiated shutdown.</span></span> <span data-ttu-id="724a6-154">Las siguientes restricciones son aplicables:</span><span class="sxs-lookup"><span data-stu-id="724a6-154">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="724a6-155">B1201: El origen de mensajería confiable de WCF siempre envía un `CloseSequence` mensaje para cerrar la secuencia.</span><span class="sxs-lookup"><span data-stu-id="724a6-155">B1201: The WCF Reliable Messaging source always sends a `CloseSequence` message to shut down the sequence.</span></span>  
  
-   <span data-ttu-id="724a6-156">B1202: el origen de la mensajería de confianza espera la confirmación del intervalo completo de mensajes de secuencia antes de enviar el mensaje `CloseSequence`.</span><span class="sxs-lookup"><span data-stu-id="724a6-156">B1202: The Reliable Messaging source waits for acknowledgement of the full range of sequence messages before sending the `CloseSequence` message.</span></span>  
  
-   <span data-ttu-id="724a6-157">B1203: el origen de la mensajería de confianza siempre incluye el elemento opcional `LastMsgNumber`, a menos que la secuencia no contenga mensajes.</span><span class="sxs-lookup"><span data-stu-id="724a6-157">B1203: The Reliable Messaging source always includes the optional `LastMsgNumber` element unless the sequence does not contain messages.</span></span>  
  
-   <span data-ttu-id="724a6-158">R1204: el destino de la mensajería de confianza no debe iniciar el cierre mediante el envío de un mensaje `CloseSequence`.</span><span class="sxs-lookup"><span data-stu-id="724a6-158">R1204: The Reliable Messaging destination must not initiate shutdown by sending a `CloseSequence` message.</span></span>  
  
-   <span data-ttu-id="724a6-159">B1205: tras recibir un `CloseSequence` mensaje, el origen de mensajería confiable de WCF considera la secuencia incompleta y envía un error.</span><span class="sxs-lookup"><span data-stu-id="724a6-159">B1205: Upon receiving a `CloseSequence` message, the WCF Reliable Messaging source considers the sequence incomplete and sends a fault.</span></span>  
  
 <span data-ttu-id="724a6-160">Ejemplo de mensaje `CloseSequence`.</span><span class="sxs-lookup"><span data-stu-id="724a6-160">An example of a `CloseSequence` message.</span></span>  
  
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
  
### <a name="sequence-termination"></a><span data-ttu-id="724a6-161">Finalización de secuencia</span><span class="sxs-lookup"><span data-stu-id="724a6-161">Sequence Termination</span></span>  
 <span data-ttu-id="724a6-162">WCF se usa principalmente el `TerminateSequence/TerminateSequenceResponse` protocolo de enlace después de completar la `CloseSequence/CloseSequenceResponse` protocolo de enlace.</span><span class="sxs-lookup"><span data-stu-id="724a6-162">WCF primarily uses the `TerminateSequence/TerminateSequenceResponse` handshake after completing the `CloseSequence/CloseSequenceResponse` handshake.</span></span> <span data-ttu-id="724a6-163">El destino de mensajería confiable de WCF no inicia la finalización y el origen de la mensajería de confianza no admite una terminación iniciada por el destino de la mensajería de confianza.</span><span class="sxs-lookup"><span data-stu-id="724a6-163">The WCF Reliable Messaging destination does not initiate termination and the Reliable Messaging source does not support a Reliable Messaging destination-initiated termination.</span></span> <span data-ttu-id="724a6-164">Las siguientes restricciones son aplicables:</span><span class="sxs-lookup"><span data-stu-id="724a6-164">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="724a6-165">B1301: El iniciador de WCF solo envía el `TerminateSequence` mensaje después de la finalización correcta de la `CloseSequence/CloseSequenceResponse` protocolo de enlace.</span><span class="sxs-lookup"><span data-stu-id="724a6-165">B1301: The WCF Initiator only sends the `TerminateSequence` message after the successful completion of the `CloseSequence/CloseSequenceResponse` handshake.</span></span>  
  
-   <span data-ttu-id="724a6-166">R1302: WCF valida que el `LastMsgNumber` elemento sea coherente en todos los `CloseSequence` y `TerminateSequence` mensajes para una secuencia determinada.</span><span class="sxs-lookup"><span data-stu-id="724a6-166">R1302: WCF validates that the `LastMsgNumber` element is consistent across all `CloseSequence` and `TerminateSequence` messages for a given sequence.</span></span> <span data-ttu-id="724a6-167">Esto significa que `LastMsgNumber` no está presente en todos los mensajes `CloseSequence` y `TerminateSequence`, o está presente y es idéntico en todos los mensajes `CloseSequence` y `TerminateSequence`.</span><span class="sxs-lookup"><span data-stu-id="724a6-167">This means that `LastMsgNumber` is either not present on all `CloseSequence` and `TerminateSequence` messages, or it is present and identical on all `CloseSequence` and `TerminateSequence` messages.</span></span>  
  
-   <span data-ttu-id="724a6-168">B1303: al recibir un mensaje `TerminateSequence` después del protocolo de enlace `CloseSequence/CloseSequenceResponse`, el destino de la mensajería de confianza responde con un mensaje `TerminateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="724a6-168">B1303: When receiving a `TerminateSequence` message after the `CloseSequence/CloseSequenceResponse` handshake, the Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="724a6-169">Puesto que el origen de la mensajería de confianza recibe la confirmación definitiva antes de enviar el mensaje `TerminateSequence`, el destino de la mensajería de confianza sabe sin duda que finaliza la secuencia y reclama recursos inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="724a6-169">Because the Reliable Messaging source has the final acknowledgement before sending the `TerminateSequence` message, the Reliable Messaging destination knows without doubt that the sequence ends, and reclaims resources immediately.</span></span>  
  
-   <span data-ttu-id="724a6-170">B1304: Al recibir un `TerminateSequence` mensajes anteriores a la `CloseSequence/CloseSequenceResponse` protocolo de enlace, el destino de mensajería confiable de WCF responde con un `TerminateSequenceResponse` mensaje.</span><span class="sxs-lookup"><span data-stu-id="724a6-170">B1304: When receiving a `TerminateSequence` message prior to the `CloseSequence/CloseSequenceResponse` handshake, the WCF Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="724a6-171">Si el destino de la mensajería de confianza determina que no hay incoherencias en la secuencia, el destino de la mensajería de confianza espera durante un tiempo especificado por el destino de la aplicación antes de reclamar recursos, para permitir al cliente que reciba la confirmación final.</span><span class="sxs-lookup"><span data-stu-id="724a6-171">If the Reliable Messaging destination determines that there are no inconsistencies in the sequence, the Reliable Messaging destination waits for an application destination-specified time before reclaiming resources, to allow the client the chance to receive the final acknowledgement.</span></span> <span data-ttu-id="724a6-172">De lo contrario, el destino de la mensajería de confianza reclama recursos inmediatamente e indica al destino de la aplicación que la secuencia finaliza de manera dudosa iniciando el evento `Faulted`.</span><span class="sxs-lookup"><span data-stu-id="724a6-172">Otherwise, the Reliable Messaging destination reclaims resources immediately and indicates to the application destination that the sequence ends with doubt by raising the `Faulted` event.</span></span>  
  
 <span data-ttu-id="724a6-173">Ejemplo de mensaje `TerminateSequence`.</span><span class="sxs-lookup"><span data-stu-id="724a6-173">An example of a `TerminateSequence` message.</span></span>  
  
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
  
### <a name="sequences"></a><span data-ttu-id="724a6-174">Secuencias</span><span class="sxs-lookup"><span data-stu-id="724a6-174">Sequences</span></span>  
 <span data-ttu-id="724a6-175">A continuación, se muestra una lista de restricciones que se aplican a las secuencias:</span><span class="sxs-lookup"><span data-stu-id="724a6-175">The following is a list of constraints that apply to sequences:</span></span>  
  
-   <span data-ttu-id="724a6-176">Genera B1401:WCF y no mayor de números de secuencia de accesos `xs:long`del valor inclusivo máximo, 9223372036854775807.</span><span class="sxs-lookup"><span data-stu-id="724a6-176">B1401:WCF generates and accesses sequence numbers no higher than `xs:long`’s maximum inclusive value, 9223372036854775807.</span></span>  
  
 <span data-ttu-id="724a6-177">Ejemplo de encabezado `Sequence`.</span><span class="sxs-lookup"><span data-stu-id="724a6-177">An example of a `Sequence` header.</span></span>  
  
```xml  
<wsrm:Sequence s:mustUnderstand="1">  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:MessageNumber>1</wsrm:MessageNumber>  
</wsrm:Sequence>  
```  
  
### <a name="request-acknowledgement"></a><span data-ttu-id="724a6-178">Solicitar confirmación</span><span class="sxs-lookup"><span data-stu-id="724a6-178">Request Acknowledgement</span></span>  
 <span data-ttu-id="724a6-179">WCF usa la `AckRequested` encabezado como un mecanismo keep-alive.</span><span class="sxs-lookup"><span data-stu-id="724a6-179">WCF uses the `AckRequested` header as a keep-alive mechanism.</span></span>  
  
 <span data-ttu-id="724a6-180">Ejemplo de encabezado `AckRequested`.</span><span class="sxs-lookup"><span data-stu-id="724a6-180">An example of an `AckRequested` header.</span></span>  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement"></a><span data-ttu-id="724a6-181">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="724a6-181">SequenceAcknowledgement</span></span>  
 <span data-ttu-id="724a6-182">WCF usa un mecanismo de "apoyo a caballo" de confirmaciones de secuencias proporcionadas en WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="724a6-182">WCF uses a "piggy-back" mechanism for sequence acknowledgements provided in WS-Reliable Messaging.</span></span> <span data-ttu-id="724a6-183">Las siguientes restricciones son aplicables:</span><span class="sxs-lookup"><span data-stu-id="724a6-183">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="724a6-184">R1601: Cuando dos secuencias inversas se establecen utilizando el `Offer` mecanismo, el `SequenceAcknowledgement` encabezado puede incluirse en cualquier mensaje de aplicación transmitido al destinatario previsto.</span><span class="sxs-lookup"><span data-stu-id="724a6-184">R1601: When two converse sequences are established using the `Offer` mechanism, the `SequenceAcknowledgement` header may be included in any application message transmitted to the intended recipient.</span></span> <span data-ttu-id="724a6-185">El extremo remoto debe poder tener acceso a un encabezado `SequenceAcknowledgement` superpuesto.</span><span class="sxs-lookup"><span data-stu-id="724a6-185">The remote endpoint must be able to access a piggybacked `SequenceAcknowledgement` header.</span></span>  
  
-   <span data-ttu-id="724a6-186">B1602: WCF no genera `SequenceAcknowledgement` encabezados que contengan `Nack` elementos.</span><span class="sxs-lookup"><span data-stu-id="724a6-186">B1602: WCF does not generate `SequenceAcknowledgement` headers that contain `Nack` elements.</span></span> <span data-ttu-id="724a6-187">WCF valida que cada `Nack` elemento contiene un número de secuencia, pero omite de otra forma el `Nack` elemento y valor.</span><span class="sxs-lookup"><span data-stu-id="724a6-187">WCF validates that each `Nack` element contains a sequence number, but otherwise ignores the `Nack` element and value.</span></span>  
  
 <span data-ttu-id="724a6-188">Ejemplo de encabezado `SequenceAcknowledgement`.</span><span class="sxs-lookup"><span data-stu-id="724a6-188">An example of a `SequenceAcknowledgement` header.</span></span>  
  
```xml  
<wsrm:SequenceAcknowledgement>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:AcknowledgementRange Lower="1" Upper="1"></wsrm:AcknowledgementRange>  
</wsrm:SequenceAcknowledgement>  
```  
  
### <a name="ws-reliablemessaging-faults"></a><span data-ttu-id="724a6-189">Errores de WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="724a6-189">WS-ReliableMessaging Faults</span></span>  
 <span data-ttu-id="724a6-190">La siguiente es una lista de restricciones que se aplican a la implementación de WCF de errores de WS-ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="724a6-190">The following is a list of constraints that apply to the WCF implementation of WS-ReliableMessaging faults.</span></span> <span data-ttu-id="724a6-191">Las siguientes restricciones son aplicables:</span><span class="sxs-lookup"><span data-stu-id="724a6-191">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="724a6-192">B1701: WCF no genera `MessageNumberRollover` errores.</span><span class="sxs-lookup"><span data-stu-id="724a6-192">B1701: WCF does not generate `MessageNumberRollover` faults.</span></span>  
  
-   <span data-ttu-id="724a6-193">B1702: Sobre SOAP 1.2, cuando el punto de conexión de servicio alcanza su límite de conexión y no puede procesar nuevas conexiones, WCF genera anidada `CreateSequenceRefused` subcódigo, de error `netrm:ConnectionLimitReached`, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="724a6-193">B1702: Over SOAP 1.2, when the service endpoint reaches its connection limit and cannot process new connections, WCF generates a nested `CreateSequenceRefused` fault subcode, `netrm:ConnectionLimitReached`, as shown in the following example.</span></span>  
  
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
  
### <a name="ws-addressing-faults"></a><span data-ttu-id="724a6-194">Errores WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="724a6-194">WS-Addressing Faults</span></span>  
 <span data-ttu-id="724a6-195">Dado que WS-ReliableMessaging utiliza WS-Addressing, la implementación de WS-ReliableMessaging de WCF puede generar y transmitir errores de WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="724a6-195">Because WS-ReliableMessaging uses WS-Addressing, the WCF WS-ReliableMessaging implementation may generate and transmit WS-Addressing faults.</span></span> <span data-ttu-id="724a6-196">En esta sección se trata los errores de WS-Addressing que WCF explícitamente genera y transmite en la capa de WS-ReliableMessaging:</span><span class="sxs-lookup"><span data-stu-id="724a6-196">This section covers the WS-Addressing faults that WCF explicitly generates and transmits at the WS-ReliableMessaging layer:</span></span>  
  
-   <span data-ttu-id="724a6-197">B1801:WCF genera y transmite el `Message Addressing Header Required` de error cuando se cumple alguna de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="724a6-197">B1801:WCF generates and transmits the `Message Addressing Header Required` fault when one of the following is true:</span></span>  
  
    -   <span data-ttu-id="724a6-198">A un mensaje `CreateSequence`, `CloseSequence`, o `TerminateSequence` le falta un encabezado `MessageId`.</span><span class="sxs-lookup"><span data-stu-id="724a6-198">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `MessageId` header.</span></span>  
  
    -   <span data-ttu-id="724a6-199">A un mensaje `CreateSequence`, `CloseSequence`, o `TerminateSequence` le falta un encabezado `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="724a6-199">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `ReplyTo` header.</span></span>  
  
    -   <span data-ttu-id="724a6-200">A un mensaje `CreateSequenceResponse`, `CloseSequenceResponse`, o `TerminateSequenceResponse` le falta un encabezado `RelatesTo`.</span><span class="sxs-lookup"><span data-stu-id="724a6-200">A `CreateSequenceResponse`, `CloseSequenceResponse`, or `TerminateSequenceResponse` message is missing a `RelatesTo` header.</span></span>  
  
-   <span data-ttu-id="724a6-201">B1802:WCF genera y transmite el `Endpoint Unavailable` error para indicar que no hay ningún extremo escuchando que puede procesar la secuencia en función de examen de los encabezados de direccionamiento en el `CreateSequence` mensaje.</span><span class="sxs-lookup"><span data-stu-id="724a6-201">B1802:WCF generates and transmits the `Endpoint Unavailable` fault to indicate there is no endpoint listening that can process the sequence based on examination of the addressing headers in the `CreateSequence` message.</span></span>  
  
## <a name="protocol-composition"></a><span data-ttu-id="724a6-202">Composición de protocolos</span><span class="sxs-lookup"><span data-stu-id="724a6-202">Protocol Composition</span></span>  
  
### <a name="composition-with-ws-addressing"></a><span data-ttu-id="724a6-203">Composición con WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="724a6-203">Composition with WS-Addressing</span></span>  
 <span data-ttu-id="724a6-204">WCF admite dos versiones de WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] y W3C WS-Addressing 1.0 recomendaciones [WS-ADDR-CORE] y [WS-ADDR-SOAP].</span><span class="sxs-lookup"><span data-stu-id="724a6-204">WCF supports two versions of WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] and W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] and [WS-ADDR-SOAP].</span></span>  
  
 <span data-ttu-id="724a6-205">Aunque la especificación de WS-ReliableMessaging solo menciona WS-Addressing 2004/08, no restringe la versión de WS-Addressing que se ha de utilizar.</span><span class="sxs-lookup"><span data-stu-id="724a6-205">While the WS-ReliableMessaging specification mentions only WS-Addressing 2004/08, it does not restrict the WS-Addressing version to be used.</span></span> <span data-ttu-id="724a6-206">La siguiente es una lista de restricciones que se aplican a WCF:</span><span class="sxs-lookup"><span data-stu-id="724a6-206">The following is a list of constraints that apply to WCF:</span></span>  
  
-   <span data-ttu-id="724a6-207">R2101: WS-Addressing 2004/08 y WS-Addressing 1.0 se pueden utilizar con la mensajería de confianza de WS.</span><span class="sxs-lookup"><span data-stu-id="724a6-207">R2101: Both WS-Addressing 2004/08 and WS-Addressing 1.0 can be used with WS-Reliable Messaging.</span></span>  
  
-   <span data-ttu-id="724a6-208">R2102: se debe utilizar una única versión de WS-Addressing a lo largo de una secuencia de WS-ReliableMessaging determinada o un par de secuencias inversas correlacionadas mediante el mecanismo `Offer`.</span><span class="sxs-lookup"><span data-stu-id="724a6-208">R2102: A single version of WS-Addressing must be used throughout a given WS-ReliableMessaging sequence or a pair of converse sequences correlated by using the `Offer` mechanism.</span></span>  
  
### <a name="composition-with-soap"></a><span data-ttu-id="724a6-209">Composición con SOAP</span><span class="sxs-lookup"><span data-stu-id="724a6-209">Composition with SOAP</span></span>  
 <span data-ttu-id="724a6-210">WCF admite el uso de SOAP 1.1 y SOAP 1.2 con WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="724a6-210">WCF supports the use of both SOAP 1.1 and SOAP 1.2 with WS-Reliable Messaging.</span></span>  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a><span data-ttu-id="724a6-211">Composición con WS-Security y WS-SecureConversation</span><span class="sxs-lookup"><span data-stu-id="724a6-211">Composition with WS-Security and WS-SecureConversation</span></span>  
 <span data-ttu-id="724a6-212">WCF proporciona protección para secuencias de WS-ReliableMessaging mediante el uso de transporte (HTTPS) segura, composición con WS-Security y composición con WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="724a6-212">WCF provides protection for WS-ReliableMessaging sequences by using secure Transport (HTTPS), composition with WS-Security, and composition with WS-Secure Conversation.</span></span> <span data-ttu-id="724a6-213">Los protocolos WS-ReliableMessaging 1.1, WS-Security 1.1 y WS-Secure Conversation 1.3 deberían utilizarse conjuntamente.</span><span class="sxs-lookup"><span data-stu-id="724a6-213">The WS-ReliableMessaging 1.1 protocol, WS-Security 1.1 and WS-Secure Conversation 1.3 protocol should be used together.</span></span> <span data-ttu-id="724a6-214">La siguiente es una lista de restricciones que se aplican a WCF:</span><span class="sxs-lookup"><span data-stu-id="724a6-214">The following is a list of constraints that apply to WCF:</span></span>  
  
-   <span data-ttu-id="724a6-215">R2301: Para proteger la integridad de una secuencia de WS-ReliableMessaging además de la integridad y confidencialidad de los mensajes individuales, WCF requiere que se deben utilizar WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="724a6-215">R2301: To protect the integrity of a WS-ReliableMessaging sequence in addition to the integrity and confidentiality of individual messages, WCF requires that WS-Secure Conversation must be used.</span></span>  
  
-   <span data-ttu-id="724a6-216">R2302:AWS-Secure Conversation debe establecerse antes de establecer secuencias de WS-ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="724a6-216">R2302:AWS-Secure Conversation session must be established prior to establishing WS-ReliableMessaging sequence(s).</span></span>  
  
-   <span data-ttu-id="724a6-217">R2303: si la duración de la secuencia de WS-ReliableMessaging supera la duración de la sesión de WS-Secure Conversation, el `SecurityContextToken` establecido mediante WS-Secure Conversation se debe renovar utilizando el enlace de renovación de WS-Secure Conversation correspondiente.</span><span class="sxs-lookup"><span data-stu-id="724a6-217">R2303: If the WS-ReliableMessaging sequence lifetime exceeds the WS-Secure Conversation session’s lifetime, the `SecurityContextToken` established by using WS-Secure Conversation must be renewed by using the corresponding WS-Secure Conversation Renewal binding.</span></span>  
  
-   <span data-ttu-id="724a6-218">B2304:WS-ReliableMessaging secuencia o un par de secuencias inversas correlacionadas siempre están enlazados a una sola sesión de WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="724a6-218">B2304:WS-ReliableMessaging sequence or a pair of correlated converse sequences are always bound to a single WS-SecureConversation session.</span></span>  
  
-   <span data-ttu-id="724a6-219">R2305: Cuando se compone con WS-Secure Conversation, el servicio de respuesta WCF requiere que la `CreateSequence` mensaje contienen el `wsse:SecurityTokenReference` elemento y el `wsrm:UsesSequenceSTR` encabezado.</span><span class="sxs-lookup"><span data-stu-id="724a6-219">R2305: When composed with WS-Secure Conversation, the WCF responder requires that the `CreateSequence` message contain the `wsse:SecurityTokenReference` element and the `wsrm:UsesSequenceSTR` header.</span></span>  
  
 <span data-ttu-id="724a6-220">Ejemplo de encabezado `UsesSequenceSTR`.</span><span class="sxs-lookup"><span data-stu-id="724a6-220">An example of a `UsesSequenceSTR` header.</span></span>  
  
```xml  
<wsrm:UsesSequenceSTR></wsrm:UsesSequenceSTR>  
```  
  
### <a name="composition-with-ssltls-sessions"></a><span data-ttu-id="724a6-221">Composición con sesiones de SSL/TLS</span><span class="sxs-lookup"><span data-stu-id="724a6-221">Composition with SSL/TLS sessions</span></span>  
 <span data-ttu-id="724a6-222">WCF no admite la composición con sesiones de SSL/TLS:</span><span class="sxs-lookup"><span data-stu-id="724a6-222">WCF does not support composition with SSL/TLS sessions:</span></span>  
  
-   <span data-ttu-id="724a6-223">B2401: WCF no genera el `wsrm:UsesSequenceSSL` encabezado.</span><span class="sxs-lookup"><span data-stu-id="724a6-223">B2401: WCF does not generate the `wsrm:UsesSequenceSSL` header.</span></span>  
  
-   <span data-ttu-id="724a6-224">R2402: Un iniciador de la mensajería confiable no debe enviar un `CreateSequence` de mensajes con un `wsrm:UsesSequenceSSL` encabezado a un servicio de respuesta WCF.</span><span class="sxs-lookup"><span data-stu-id="724a6-224">R2402: A Reliable Messaging Initiator must not send a `CreateSequence` message with a `wsrm:UsesSequenceSSL` header to a WCF Responder.</span></span>  
  
### <a name="composition-with-ws-policy"></a><span data-ttu-id="724a6-225">Composición con WS-Policy</span><span class="sxs-lookup"><span data-stu-id="724a6-225">Composition with WS-Policy</span></span>  
 <span data-ttu-id="724a6-226">WCF admite dos versiones de WS-Policy: WS-Policy 1.2 y 1.5 de WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="724a6-226">WCF supports two versions of WS-Policy: WS-Policy 1.2 and WS-Policy 1.5.</span></span>  
  
## <a name="ws-reliablemessaging-ws-policy-assertion"></a><span data-ttu-id="724a6-227">Aserción de WS-Policy de WS-ReliableMessaging </span><span class="sxs-lookup"><span data-stu-id="724a6-227">WS-ReliableMessaging WS-Policy Assertion</span></span>  
 <span data-ttu-id="724a6-228">WCF usa la aserción de WS-Policy de WS-ReliableMessaging `wsrm:RMAssertion` para describir funciones de extremos.</span><span class="sxs-lookup"><span data-stu-id="724a6-228">WCF uses WS-ReliableMessaging WS-Policy Assertion `wsrm:RMAssertion` to describe endpoints capabilities.</span></span> <span data-ttu-id="724a6-229">La siguiente es una lista de restricciones que se aplican a WCF:</span><span class="sxs-lookup"><span data-stu-id="724a6-229">The following is a list of constraints that apply to WCF:</span></span>  
  
-   <span data-ttu-id="724a6-230">B3001: WCF adjunta `wsrmn:RMAssertion` WS-Policy Assertion a `wsdl:binding` elementos.</span><span class="sxs-lookup"><span data-stu-id="724a6-230">B3001: WCF attaches `wsrmn:RMAssertion` WS-Policy Assertion to `wsdl:binding` elements.</span></span> <span data-ttu-id="724a6-231">WCF admite datos adjuntos a `wsdl:binding` y `wsdl:port` elementos.</span><span class="sxs-lookup"><span data-stu-id="724a6-231">WCF supports both attachments to `wsdl:binding` and `wsdl:port` elements.</span></span>  
  
-   <span data-ttu-id="724a6-232">B3002: WCF nunca genera la `wsp:Optional` etiqueta.</span><span class="sxs-lookup"><span data-stu-id="724a6-232">B3002: WCF never generates the `wsp:Optional` tag.</span></span>  
  
-   <span data-ttu-id="724a6-233">B3003: Al tener acceso a la `wsrmp:RMAssertion` aserción de WS-Policy, WCF omite la `wsp:Optional` etiqueta y trata la directiva WS-RM como obligatoria.</span><span class="sxs-lookup"><span data-stu-id="724a6-233">B3003: When accessing the `wsrmp:RMAssertion` WS-Policy Assertion, WCF ignores the `wsp:Optional` tag and treats the WS-RM policy as mandatory.</span></span>  
  
-   <span data-ttu-id="724a6-234">R3004: Dado que WCF no compone con sesiones de SSL/TLS, WCF no acepta directiva que especifica `wsrmp:SequenceTransportSecurity`.</span><span class="sxs-lookup"><span data-stu-id="724a6-234">R3004: Because WCF does not compose with SSL/TLS sessions, WCF does not accept policy that specifies `wsrmp:SequenceTransportSecurity`.</span></span>  
  
-   <span data-ttu-id="724a6-235">B3005: WCF siempre genera el `wsrmp:DeliveryAssurance` elemento.</span><span class="sxs-lookup"><span data-stu-id="724a6-235">B3005: WCF always generates the `wsrmp:DeliveryAssurance` element.</span></span>  
  
-   <span data-ttu-id="724a6-236">B3006: WCF siempre especifica la `wsrmp:ExactlyOnce` garantía de entrega.</span><span class="sxs-lookup"><span data-stu-id="724a6-236">B3006: WCF always specifies the `wsrmp:ExactlyOnce` delivery assurance.</span></span>  
  
-   <span data-ttu-id="724a6-237">B3007: WCF genera y lee las siguientes propiedades de la aserción de WS-ReliableMessaging y proporciona control sobre ellas en WCF`ReliableSessionBindingElement`:</span><span class="sxs-lookup"><span data-stu-id="724a6-237">B3007: WCF generates and reads the following properties of the WS-ReliableMessaging assertion and provides control over them on the WCF`ReliableSessionBindingElement`:</span></span>  
  
    -   `netrmp:InactivityTimeout`  
  
    -   `netrmp:AcknowledgementInterval`  
  
     <span data-ttu-id="724a6-238">Ejemplo de `RMAssertion`.</span><span class="sxs-lookup"><span data-stu-id="724a6-238">An example of a `RMAssertion`.</span></span>  
  
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
  
## <a name="flow-control-ws-reliablemessaging-extension"></a><span data-ttu-id="724a6-239">Extensión de WS-ReliableMessaging de control de flujo</span><span class="sxs-lookup"><span data-stu-id="724a6-239">Flow Control WS-ReliableMessaging Extension</span></span>  
 <span data-ttu-id="724a6-240">WCF usa extensibilidad de WS-ReliableMessaging para proporcionar opcional adicional y un mayor control sobre el flujo de mensajes de secuencias.</span><span class="sxs-lookup"><span data-stu-id="724a6-240">WCF uses WS-ReliableMessaging extensibility to provide optional additional tighter control over sequence message flow.</span></span>  
  
 <span data-ttu-id="724a6-241">Control de flujo se habilita estableciendo el `ReliableSessionBindingElement`del `FlowControlEnabled``boolean` propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="724a6-241">Flow control is enabled by setting the `ReliableSessionBindingElement`’s `FlowControlEnabled``boolean` property to `true`.</span></span> <span data-ttu-id="724a6-242">La siguiente es una lista de restricciones que se aplican a WCF:</span><span class="sxs-lookup"><span data-stu-id="724a6-242">The following is a list of constraints that apply to WCF:</span></span>  
  
-   <span data-ttu-id="724a6-243">B4001: Cuando está habilitado el Control de flujo de mensajería confiable, WCF genera un `netrm:BufferRemaining` elemento de la extensibilidad de elementos de la `SequenceAcknowledgement` encabezado, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="724a6-243">B4001: When Reliable Messaging Flow Control is enabled, WCF generates a `netrm:BufferRemaining` element in the element extensibility of the `SequenceAcknowledgement` header, as shown in the following example.</span></span>  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="1" Lower="1"/>             
      <netrm:BufferRemaining>8</netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   <span data-ttu-id="724a6-244">B4002: Incluso cuando está habilitado el Control de flujo de mensajería confiable, WCF no requiere un `netrm:BufferRemaining` elemento en el `SequenceAcknowledgement` encabezado.</span><span class="sxs-lookup"><span data-stu-id="724a6-244">B4002: Even when Reliable Messaging Flow Control is enabled, WCF does not require a `netrm:BufferRemaining` element in the `SequenceAcknowledgement` header.</span></span>  
  
-   <span data-ttu-id="724a6-245">B4003: El destino de mensajería confiable de WCF usa `netrm:BufferRemaining` indicar cuántos mensajes nuevos puede almacenar en búfer.</span><span class="sxs-lookup"><span data-stu-id="724a6-245">B4003: WCF Reliable Messaging Destination uses `netrm:BufferRemaining` to indicate how many new messages it can buffer.</span></span>  
  
-   <span data-ttu-id="724a6-246">B4004:when confiable de mensajería de flujo de Control está habilitado, el origen de mensajería confiable de WCF usa el valor de `netrm:BufferRemaining` para la transmisión de mensajes del acelerador.</span><span class="sxs-lookup"><span data-stu-id="724a6-246">B4004:When Reliable Messaging Flow Control is enabled, the WCF Reliable Messaging Source uses the value of `netrm:BufferRemaining` to throttle message transmission.</span></span>  
  
-   <span data-ttu-id="724a6-247">B4005: WCF genera `netrm:BufferRemaining` entero los valores comprendidos entre 0 y 4.096, ambos incluidos y lee valores enteros entre 0 y `xs:int`del `maxInclusive` valor 214748364 inclusive.</span><span class="sxs-lookup"><span data-stu-id="724a6-247">B4005: WCF generates `netrm:BufferRemaining` integer values between 0 and 4096 inclusive, and reads integer values between 0 and `xs:int`’s `maxInclusive` value 214748364 inclusive.</span></span>  
  
## <a name="message-exchange-patterns"></a><span data-ttu-id="724a6-248">Modelos de intercambio de mensajes</span><span class="sxs-lookup"><span data-stu-id="724a6-248">Message Exchange Patterns</span></span>  
 <span data-ttu-id="724a6-249">Esta sección describe el comportamiento de WCF cuando se utiliza WS-ReliableMessaging para patrones de intercambio de mensajes diferentes.</span><span class="sxs-lookup"><span data-stu-id="724a6-249">This section describes WCF's behavior when WS-ReliableMessaging is used for different Message Exchange Patterns.</span></span> <span data-ttu-id="724a6-250">Para cada patrón de intercambio de mensajes, se consideran los dos escenarios de implementación siguientes:</span><span class="sxs-lookup"><span data-stu-id="724a6-250">For each Message Exchange Pattern the following two deployments scenarios are considered:</span></span>  
  
-   <span data-ttu-id="724a6-251">Iniciador no direccionable: el iniciador está tras un firewall; el respondedor solo puede entregar mensajes al iniciador mediante respuestas HTTP.</span><span class="sxs-lookup"><span data-stu-id="724a6-251">Non-Addressable Initiator: Initiator is behind a firewall; Responder can deliver messages to the Initiator only on HTTP responses.</span></span>  
  
-   <span data-ttu-id="724a6-252">Iniciador direccionable: el iniciador y el respondedor pueden enviar solicitudes HTTP; en otras palabras, se pueden establecer dos conexiones HTTP inversas.</span><span class="sxs-lookup"><span data-stu-id="724a6-252">Addressable Initiator: Initiator and Responder both can be sent HTTP requests; in other words, two converse HTTP connections can be established.</span></span>  
  
### <a name="one-way-non-addressable-initiator"></a><span data-ttu-id="724a6-253">Iniciador unidireccional no direccionable</span><span class="sxs-lookup"><span data-stu-id="724a6-253">One-way, Non-addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="724a6-254">Enlaces</span><span class="sxs-lookup"><span data-stu-id="724a6-254">Binding</span></span>  
 <span data-ttu-id="724a6-255">WCF proporciona un patrón de intercambio de mensajes unidireccional usando una secuencia sobre un canal HTTP.</span><span class="sxs-lookup"><span data-stu-id="724a6-255">WCF provides a one-way message exchange pattern using one sequence over one HTTP channel.</span></span> <span data-ttu-id="724a6-256">WCF usa solicitudes HTTP para transmitir todos los mensajes del iniciador para el Respondedor y respuestas HTTP para transmitir todos los mensajes del Respondedor al iniciador.</span><span class="sxs-lookup"><span data-stu-id="724a6-256">WCF uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="724a6-257">Intercambio de CreateSequence</span><span class="sxs-lookup"><span data-stu-id="724a6-257">CreateSequence Exchange</span></span>  
 <span data-ttu-id="724a6-258">El iniciador de WCF transmite una `CreateSequence` mensaje y no tienen ninguna `Offer` elemento en una solicitud HTTP y espera el `CreateSequenceResponse` mensaje en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="724a6-258">The WCF Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="724a6-259">El servicio de respuesta WCF crea una secuencia y transmite el `CreateSequenceResponse` mensaje sin ningún `Accept` elemento en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="724a6-259">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on the HTTP response.</span></span>  
  
#### <a name="sequenceacknowledgement"></a><span data-ttu-id="724a6-260">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="724a6-260">SequenceAcknowledgement</span></span>  
 <span data-ttu-id="724a6-261">El iniciador de WCF procesa las confirmaciones en la respuesta de todos los mensajes excepto el `CreateSequence` mensajes y mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="724a6-261">The WCF Initiator processes acknowledgements on the reply of all messages except the `CreateSequence` message and fault messages.</span></span> <span data-ttu-id="724a6-262">El servicio de respuesta WCF siempre transmite una confirmación independiente en la respuesta HTTP a todas las secuencia y `AckRequested` mensajes.</span><span class="sxs-lookup"><span data-stu-id="724a6-262">The WCF Responder always transmits a stand-alone acknowledgement on the HTTP response to all sequence and `AckRequested` messages.</span></span>  
  
#### <a name="closesequence-exchange"></a><span data-ttu-id="724a6-263">Intercambio de CloseSequence</span><span class="sxs-lookup"><span data-stu-id="724a6-263">CloseSequence Exchange</span></span>  
 <span data-ttu-id="724a6-264">El iniciador de WCF transmite una `CloseSequence` el mensaje en una solicitud HTTP y espera el `CreateSequenceResponse` mensaje en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="724a6-264">The WCF Initiator transmits a `CloseSequence` message on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="724a6-265">El servicio de respuesta WCF transmite el `CloseSequenceResponse` mensaje en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="724a6-265">The WCF Responder transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>  
  
#### <a name="terminatesequence-exchange"></a><span data-ttu-id="724a6-266">Intercambio de TerminateSequence</span><span class="sxs-lookup"><span data-stu-id="724a6-266">TerminateSequence Exchange</span></span>  
 <span data-ttu-id="724a6-267">El iniciador de WCF transmite una `TerminateSequence` el mensaje en una solicitud HTTP y espera el `TerminateSequenceResponse` mensaje en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="724a6-267">The WCF Initiator transmits a `TerminateSequence` message on an HTTP request and expects the `TerminateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="724a6-268">El servicio de respuesta WCF transmite el `TerminateSequenceResponse` mensaje en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="724a6-268">The WCF Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>  
  
### <a name="one-way-addressable-initiator"></a><span data-ttu-id="724a6-269">Iniciador unidireccional y direccionable</span><span class="sxs-lookup"><span data-stu-id="724a6-269">One Way, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="724a6-270">Enlaces</span><span class="sxs-lookup"><span data-stu-id="724a6-270">Binding</span></span>  
 <span data-ttu-id="724a6-271">WCF proporciona un patrón de intercambio de mensajes unidireccional usando una secuencia sobre una entrada y un canal HTTP saliente.</span><span class="sxs-lookup"><span data-stu-id="724a6-271">WCF provides a one-way message exchange pattern using one sequence over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="724a6-272">WCF usa las solicitudes HTTP para transmitir todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="724a6-272">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="724a6-273">Todas las respuestas HTTP tienen un cuerpo vacío y código de estado HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="724a6-273">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="724a6-274">Intercambio de CreateSequence</span><span class="sxs-lookup"><span data-stu-id="724a6-274">CreateSequence Exchange</span></span>  
 <span data-ttu-id="724a6-275">El iniciador de WCF transmite una `CreateSequence` mensaje sin ningún `Offer` elemento en una solicitud HTTP.</span><span class="sxs-lookup"><span data-stu-id="724a6-275">The WCF Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request.</span></span> <span data-ttu-id="724a6-276">El servicio de respuesta WCF crea una secuencia y transmite el `CreateSequenceResponse` mensaje sin ningún `Accept` elemento en una solicitud HTTP.</span><span class="sxs-lookup"><span data-stu-id="724a6-276">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on an HTTP request.</span></span>  
  
### <a name="duplex-addressable-initiator"></a><span data-ttu-id="724a6-277">Iniciador dúplex y direccionable</span><span class="sxs-lookup"><span data-stu-id="724a6-277">Duplex, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="724a6-278">Enlaces</span><span class="sxs-lookup"><span data-stu-id="724a6-278">Binding</span></span>  
 <span data-ttu-id="724a6-279">WCF proporciona un patrón de intercambio de mensajes totalmente asincrónico y bidireccional utilizando dos secuencias sobre un entrante y un canal HTTP saliente.</span><span class="sxs-lookup"><span data-stu-id="724a6-279">WCF provides a fully-asynchronous, two-way message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="724a6-280">Este patrón de intercambio de mensajes se puede mezclar con el patrón de intercambio de mensajes del iniciador de `Request/Reply`, `Addressable` de una manera limitada.</span><span class="sxs-lookup"><span data-stu-id="724a6-280">This message exchange pattern can be mixed with the `Request/Reply`, `Addressable` Initiator message exchange pattern in a limited way.</span></span> <span data-ttu-id="724a6-281">WCF usa solicitudes HTTP para transmitir todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="724a6-281">WCF uses HTTP requests to transmit all messages.</span></span> <span data-ttu-id="724a6-282">Todas las respuestas HTTP tienen un cuerpo vacío y código de estado HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="724a6-282">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="724a6-283">Intercambio de CreateSequence</span><span class="sxs-lookup"><span data-stu-id="724a6-283">CreateSequence Exchange</span></span>  
 <span data-ttu-id="724a6-284">El iniciador de WCF transmite una `CreateSequence` de mensajes con un `Offer` elemento en una solicitud HTTP.</span><span class="sxs-lookup"><span data-stu-id="724a6-284">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="724a6-285">El servicio de respuesta WCF garantiza que la `CreateSequence` tiene un `Offer` elemento, a continuación, crea una secuencia y transmite el `CreateSequenceResponse` de mensajes con un `Accept` elemento.</span><span class="sxs-lookup"><span data-stu-id="724a6-285">The WCF Responder ensures that the `CreateSequence` has an `Offer` element, then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>  
  
#### <a name="sequence-lifetime"></a><span data-ttu-id="724a6-286">Duración de la secuencia</span><span class="sxs-lookup"><span data-stu-id="724a6-286">Sequence Lifetime</span></span>  
 <span data-ttu-id="724a6-287">WCF trata las dos secuencias como una sesión totalmente dúplex.</span><span class="sxs-lookup"><span data-stu-id="724a6-287">WCF treats the two sequences as one fully-duplex session.</span></span>  
  
 <span data-ttu-id="724a6-288">Tras generar un error que se produce un error en una secuencia, WCF espera que el extremo remoto al error en ambas secuencias.</span><span class="sxs-lookup"><span data-stu-id="724a6-288">Upon generating a fault that faults one sequence, WCF expects the remote endpoint to fault both sequences.</span></span> <span data-ttu-id="724a6-289">Tras leer un error que se produce un error en una secuencia, WCF produce un error en ambas secuencias.</span><span class="sxs-lookup"><span data-stu-id="724a6-289">Upon reading a fault that faults one sequence, WCF faults both sequences.</span></span>  
  
 <span data-ttu-id="724a6-290">WCF puede cerrar su secuencia saliente y continuar procesando mensajes en su secuencia de entrada.</span><span class="sxs-lookup"><span data-stu-id="724a6-290">WCF can close its outbound sequence and continue to process messages on its inbound sequence.</span></span> <span data-ttu-id="724a6-291">Por el contrario, WCF puede procesar el cierre de la secuencia entrante y continuar enviando mensajes en su secuencia saliente.</span><span class="sxs-lookup"><span data-stu-id="724a6-291">Conversely, WCF can process the close of the inbound sequence and continue to send messages on its outbound sequence.</span></span>  
  
### <a name="request-reply-and-one-way-non-addressable-initiator"></a><span data-ttu-id="724a6-292">Iniciador de solicitud-respuesta unidireccional y no direccionable</span><span class="sxs-lookup"><span data-stu-id="724a6-292">Request-Reply and One-Way, Non-Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="724a6-293">Enlaces</span><span class="sxs-lookup"><span data-stu-id="724a6-293">Binding</span></span>  
 <span data-ttu-id="724a6-294">WCF proporciona un unidireccional y patrón de intercambio de mensajes de solicitud-respuesta usando dos secuencias sobre un canal HTTP.</span><span class="sxs-lookup"><span data-stu-id="724a6-294">WCF provides a one-way and request-reply message exchange pattern using two sequences over one HTTP channel.</span></span> <span data-ttu-id="724a6-295">WCF usa solicitudes HTTP para transmitir todos los mensajes del iniciador para el Respondedor y respuestas HTTP para transmitir todos los mensajes del Respondedor al iniciador.</span><span class="sxs-lookup"><span data-stu-id="724a6-295">WCF uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="724a6-296">Intercambio de CreateSequence</span><span class="sxs-lookup"><span data-stu-id="724a6-296">CreateSequence Exchange</span></span>  
 <span data-ttu-id="724a6-297">El iniciador de WCF transmite una `CreateSequence` de mensajes con un `Offer` elemento en una solicitud HTTP y espera el `CreateSequenceResponse` mensaje en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="724a6-297">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="724a6-298">El servicio de respuesta WCF crea una secuencia y transmite el `CreateSequenceResponse` de mensajes con un `Accept` elemento en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="724a6-298">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element on the HTTP response.</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="724a6-299">Mensaje unidireccional</span><span class="sxs-lookup"><span data-stu-id="724a6-299">One-way Message</span></span>  
 <span data-ttu-id="724a6-300">Para completar correctamente un intercambio de mensajes unidireccional, el iniciador de WCF transmite un mensaje de secuencia de solicitud en la solicitud HTTP y recibe una independiente `SequenceAcknowledgement` mensaje en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="724a6-300">To complete a one-way message exchange successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a standalone `SequenceAcknowledgement` message on the HTTP response.</span></span> <span data-ttu-id="724a6-301">La `SequenceAcknowledgement` debe confirmar el mensaje transmitido.</span><span class="sxs-lookup"><span data-stu-id="724a6-301">The `SequenceAcknowledgement` must acknowledge the message transmitted.</span></span>  
  
 <span data-ttu-id="724a6-302">El servicio de respuesta WCF puede responder a la solicitud con una confirmación, un error o una respuesta con un cuerpo vacío y código de estado HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="724a6-302">The WCF Responder may reply to the request with an acknowledgement, a fault, or a response with an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="two-way-messages"></a><span data-ttu-id="724a6-303">Mensajes bidireccionales</span><span class="sxs-lookup"><span data-stu-id="724a6-303">Two Way Messages</span></span>  
 <span data-ttu-id="724a6-304">Para completar correctamente un protocolo de intercambio de mensajes bidireccional, el iniciador de WCF transmite un mensaje de secuencia de solicitud en la solicitud HTTP y recibe un mensaje de secuencia de respuesta en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="724a6-304">To complete a two way message exchange protocol successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a reply sequence message on the HTTP response.</span></span> <span data-ttu-id="724a6-305">La respuesta debe llevar una `SequenceAcknowledgement` que confirme que se ha transmitido el mensaje de secuencia de solicitud.</span><span class="sxs-lookup"><span data-stu-id="724a6-305">The response must carry a `SequenceAcknowledgement` acknowledging the request sequence message transmitted.</span></span>  
  
 <span data-ttu-id="724a6-306">El servicio de respuesta WCF puede responder a la solicitud con una respuesta de la aplicación, un error o una respuesta con un cuerpo vacío y código de estado HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="724a6-306">The WCF Responder may reply to the request with an application reply, a fault or a response with an empty body and HTTP 202 status code.</span></span>  
  
 <span data-ttu-id="724a6-307">Debido a la presencia de mensajes unidireccionales y al control de tiempo de las respuestas de la aplicación, el número de secuencia del mensaje de secuencia de solicitud y el número de secuencia del mensaje de respuesta no tienen ninguna correlación.</span><span class="sxs-lookup"><span data-stu-id="724a6-307">Because of the presence of one-way messages and the timing of application replies, the request sequence message’s sequence number and the response message’s sequence number have no correlation.</span></span>  
  
#### <a name="retrying-replies"></a><span data-ttu-id="724a6-308">Reintento de respuestas</span><span class="sxs-lookup"><span data-stu-id="724a6-308">Retrying Replies</span></span>  
 <span data-ttu-id="724a6-309">WCF se basa en la correlación de solicitud y respuesta HTTP para la correlación de protocolo de intercambio de mensajes bidireccional.</span><span class="sxs-lookup"><span data-stu-id="724a6-309">WCF relies on HTTP request-reply correlation for two-way message exchange protocol correlation.</span></span> <span data-ttu-id="724a6-310">Por este motivo, el iniciador de WCF no deja de reintentar un mensaje de secuencia de solicitud cuando se confirma el mensaje de secuencia de solicitud, sino cuando la respuesta HTTP lleva una `SequenceAcknowledgement`, respuesta de la aplicación o error.</span><span class="sxs-lookup"><span data-stu-id="724a6-310">Because of this, the WCF Initiator does not stop retrying a request sequence message when the request sequence message is acknowledged but rather when the HTTP response carries a `SequenceAcknowledgement`, application reply, or fault.</span></span> <span data-ttu-id="724a6-311">El servicio de respuesta WCF reintenta las respuestas en la respuesta HTTP de la solicitud a la que se correlaciona la respuesta.</span><span class="sxs-lookup"><span data-stu-id="724a6-311">The WCF Responder retries replies on the HTTP response of the request to which the reply is correlated.</span></span>  
  
#### <a name="closesequence-exchange"></a><span data-ttu-id="724a6-312">Intercambio de CloseSequence</span><span class="sxs-lookup"><span data-stu-id="724a6-312">CloseSequence Exchange</span></span>  
 <span data-ttu-id="724a6-313">Después de recibir todos los mensajes de la secuencia de respuesta y confirmaciones para todos los mensajes de la secuencia de solicitud unidireccionales, el iniciador de WCF transmite una `CloseSequence` el mensaje para la secuencia de solicitud en una solicitud HTTP y espera el `CloseSequenceResponse` en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="724a6-313">After receiving all reply sequence messages and acknowledgements for all one way request sequence messages, the WCF Initiator transmits a `CloseSequence` message for the request sequence on an HTTP request and expects the `CloseSequenceResponse` on the HTTP response.</span></span>  
  
 <span data-ttu-id="724a6-314">Al cerrar implícitamente la secuencia de la solicitud, se cierra la secuencia de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="724a6-314">Closing the request sequence implicitly closes the reply sequence.</span></span> <span data-ttu-id="724a6-315">Esto significa que el iniciador de WCF incluye Final de la secuencia de respuesta `SequenceAcknowledgement` en el `CloseSequence` mensaje y la secuencia de respuesta no tiene un `CloseSequence` exchange.</span><span class="sxs-lookup"><span data-stu-id="724a6-315">This means the WCF Initiator includes the reply sequence’s Final `SequenceAcknowledgement` on the `CloseSequence` message and the reply sequence does not have a `CloseSequence` exchange.</span></span>  
  
 <span data-ttu-id="724a6-316">El servicio de respuesta WCF asegura todas las respuestas se confirmen y transmite el `CloseSequenceResponse` mensaje en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="724a6-316">The WCF Responder ensures all replies are acknowledged and transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>  
  
#### <a name="terminatesequence-exchange"></a><span data-ttu-id="724a6-317">Intercambio de TerminateSequence</span><span class="sxs-lookup"><span data-stu-id="724a6-317">TerminateSequence Exchange</span></span>  
 <span data-ttu-id="724a6-318">Después de recibir el `CloseSequenceResponse` mensaje, el iniciador de WCF transmite una `TerminateSequence` el mensaje para la secuencia de solicitud en una solicitud HTTP y espera el `TerminateSequenceResponse` en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="724a6-318">After receiving the `CloseSequenceResponse` message, the WCF Initiator transmits a `TerminateSequence` message for the request sequence on an HTTP request and expects the `TerminateSequenceResponse` on the HTTP response.</span></span>  
  
 <span data-ttu-id="724a6-319">Al igual que en el intercambio de `CloseSequence`, al finalizar la secuencia de solicitud, se finaliza la secuencia de respuesta.</span><span class="sxs-lookup"><span data-stu-id="724a6-319">Like the `CloseSequence` exchange, terminating the request sequence implicitly terminates the reply sequence.</span></span> <span data-ttu-id="724a6-320">Esto significa que el iniciador de WCF incluye final de la secuencia de respuesta `SequenceAcknowledgement` en el `TerminateSequence` mensaje y la secuencia de respuesta no tiene un `TerminateSequence` exchange.</span><span class="sxs-lookup"><span data-stu-id="724a6-320">This means the WCF Initiator includes the reply sequence’s final `SequenceAcknowledgement` on the `TerminateSequence` message and the reply sequence does not have a `TerminateSequence` exchange.</span></span>  
  
 <span data-ttu-id="724a6-321">El servicio de respuesta WCF transmite el `TerminateSequenceResponse` mensaje en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="724a6-321">The WCF Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>  
  
### <a name="requestreply-addressable-initiator"></a><span data-ttu-id="724a6-322">Iniciador direccionable de solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="724a6-322">Request/Reply, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="724a6-323">Enlaces</span><span class="sxs-lookup"><span data-stu-id="724a6-323">Binding</span></span>  
 <span data-ttu-id="724a6-324">WCF proporciona un patrón de intercambio de mensajes de solicitud-respuesta usando dos secuencias sobre un entrante y un canal HTTP saliente.</span><span class="sxs-lookup"><span data-stu-id="724a6-324">WCF provides a request-reply message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="724a6-325">Este patrón de intercambio de mensajes se puede mezclar con el patrón de intercambio de mensajes del iniciador de `Duplex, Addressable` de una manera limitada.</span><span class="sxs-lookup"><span data-stu-id="724a6-325">This message exchange pattern can be mixed with the `Duplex, Addressable` Initiator message exchange pattern in a limited way.</span></span> <span data-ttu-id="724a6-326">WCF usa las solicitudes HTTP para transmitir todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="724a6-326">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="724a6-327">Todas las respuestas HTTP tienen un cuerpo vacío y código de estado HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="724a6-327">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="724a6-328">Intercambio de CreateSequence</span><span class="sxs-lookup"><span data-stu-id="724a6-328">CreateSequence Exchange</span></span>  
 <span data-ttu-id="724a6-329">El iniciador de WCF transmite una `CreateSequence` de mensajes con un `Offer` elemento en una solicitud HTTP.</span><span class="sxs-lookup"><span data-stu-id="724a6-329">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="724a6-330">El servicio de respuesta WCF garantiza que la `CreateSequence` tiene un `Offer` elemento, a continuación, crea una secuencia y transmite el `CreateSequenceResponse` de mensajes con un `Accept` elemento.</span><span class="sxs-lookup"><span data-stu-id="724a6-330">The WCF Responder ensures that the `CreateSequence` has an `Offer` element then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>  
  
#### <a name="requestreply-correlation"></a><span data-ttu-id="724a6-331">Correlación entre solicitud y respuesta</span><span class="sxs-lookup"><span data-stu-id="724a6-331">Request/Reply Correlation</span></span>  
 <span data-ttu-id="724a6-332">Lo siguiente se aplica a todas las solicitudes y respuestas correlacionadas:</span><span class="sxs-lookup"><span data-stu-id="724a6-332">The following applies to all correlated requests and replies:</span></span>  
  
-   <span data-ttu-id="724a6-333">WCF asegura mensajes de solicitud de todas las aplicación lleven un `ReplyTo` referencia de extremo y un `MessageId`.</span><span class="sxs-lookup"><span data-stu-id="724a6-333">WCF ensures all application request messages bear a `ReplyTo` endpoint reference and a `MessageId`.</span></span>  
  
-   <span data-ttu-id="724a6-334">WCF aplica la referencia del extremo local como cada mensaje de solicitud de aplicación `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="724a6-334">WCF applies the local endpoint reference as each application request message’s `ReplyTo`.</span></span> <span data-ttu-id="724a6-335">La referencia del extremo local es la `CreateSequence` del mensaje `ReplyTo` para el iniciador y la `CreateSequence` del mensaje `To` para el respondedor.</span><span class="sxs-lookup"><span data-stu-id="724a6-335">The local endpoint reference is the `CreateSequence` message’s `ReplyTo` for the Initiator and the `CreateSequence` message’s `To` for the Responder.</span></span>  
  
-   <span data-ttu-id="724a6-336">WCF garantiza que los mensajes de solicitud entrante lleven un `MessageId` y `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="724a6-336">WCF ensures that incoming request messages bear a `MessageId` and a `ReplyTo`.</span></span>  
  
-   <span data-ttu-id="724a6-337">WCF garantiza la `ReplyTo` URI de la referencia de punto de conexión de todos los mensajes de solicitud de aplicación coincide con la referencia del extremo local tal y como se definió anteriormente.</span><span class="sxs-lookup"><span data-stu-id="724a6-337">WCF ensures the `ReplyTo` endpoint reference’s URI of all application request messages match the local endpoint reference as defined earlier.</span></span>  
  
-   <span data-ttu-id="724a6-338">WCF garantiza que todas las respuestas llevan correctos `RelatesTo` y `To` encabezados después `wsa` reglas de correlación de solicitud/respuesta.</span><span class="sxs-lookup"><span data-stu-id="724a6-338">WCF ensures that all replies bear the correct `RelatesTo` and `To` headers following `wsa` request/reply correlation rules.</span></span>
