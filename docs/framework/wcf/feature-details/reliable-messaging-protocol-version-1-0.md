---
title: Protocolo de mensajería de confianza versión 1.0
ms.date: 03/30/2017
ms.assetid: a5509a5c-de24-4bc2-9a48-19138055dcce
ms.openlocfilehash: 857bbbf9ffa1311c38cfc007e0cdc6bde06d6284
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64617576"
---
# <a name="reliable-messaging-protocol-version-10"></a><span data-ttu-id="ad496-102">Protocolo de mensajería de confianza versión 1.0</span><span class="sxs-lookup"><span data-stu-id="ad496-102">Reliable Messaging Protocol version 1.0</span></span>
<span data-ttu-id="ad496-103">En este tema cubre los detalles de implementación de Windows Communication Foundation (WCF) para WS-Reliable Messaging protocol de febrero de 2005 (versión 1.0) necesario para la interoperación mediante el transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="ad496-103">This topic covers Windows Communication Foundation (WCF) implementation details for the WS-Reliable Messaging February 2005 (version 1.0) protocol necessary for interoperation using the HTTP transport.</span></span> <span data-ttu-id="ad496-104">WCF sigue la especificación WS-Reliable Messaging con las restricciones y clarificaciones explicadas en este tema.</span><span class="sxs-lookup"><span data-stu-id="ad496-104">WCF follows the WS-Reliable Messaging specification with the constraints and clarifications explained in this topic.</span></span> <span data-ttu-id="ad496-105">Tenga en cuenta que la versión 1.0 del protocolo WS-ReliableMessaging se implementa a partir de [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad496-105">Note that the WS-ReliableMessaging version 1.0 protocol is implemented starting with the [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)].</span></span>  
  
 <span data-ttu-id="ad496-106">El WS-Reliable Messaging de febrero de 2005 protocolo se implementa en WCF mediante el <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="ad496-106">The WS-Reliable Messaging February 2005 protocol is implemented in WCF by the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span></span>  
  
 <span data-ttu-id="ad496-107">Para su comodidad, el tema utiliza las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="ad496-107">For convenience, the topic uses the following roles:</span></span>  
  
- <span data-ttu-id="ad496-108">Iniciador: el cliente que inicia la creación de la secuencia de mensajes WS-Reliable</span><span class="sxs-lookup"><span data-stu-id="ad496-108">Initiator: the client that initiates WS-Reliable Message sequence creation</span></span>  
  
- <span data-ttu-id="ad496-109">Respondedor: el servicio que recibe las solicitudes del iniciador</span><span class="sxs-lookup"><span data-stu-id="ad496-109">Responder: the service that receives the initiator's requests</span></span>  
  
 <span data-ttu-id="ad496-110">En este documento, se utilizan los prefijos y espacios de nombres de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="ad496-110">This document uses the prefixes and namespaces in the following table.</span></span>  
  
|<span data-ttu-id="ad496-111">Prefijo</span><span class="sxs-lookup"><span data-stu-id="ad496-111">Prefix</span></span>|<span data-ttu-id="ad496-112">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="ad496-112">Namespace</span></span>|  
|------------|---------------|  
|<span data-ttu-id="ad496-113">wsrm</span><span class="sxs-lookup"><span data-stu-id="ad496-113">wsrm</span></span>|http://schemas.xmlsoap.org/ws/2005/02/rm|  
|<span data-ttu-id="ad496-114">netrm</span><span class="sxs-lookup"><span data-stu-id="ad496-114">netrm</span></span>|http://schemas.microsoft.com/ws/2006/05/rm|  
|<span data-ttu-id="ad496-115">s</span><span class="sxs-lookup"><span data-stu-id="ad496-115">s</span></span>|http://www.w3.org/2003/05/soap-envelope|  
|<span data-ttu-id="ad496-116">wsa</span><span class="sxs-lookup"><span data-stu-id="ad496-116">wsa</span></span>|http://schemas.xmlsoap.org/ws/2005/08/addressing|  
|<span data-ttu-id="ad496-117">wsse</span><span class="sxs-lookup"><span data-stu-id="ad496-117">wsse</span></span>|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd|  
  
## <a name="messaging"></a><span data-ttu-id="ad496-118">Mensajería</span><span class="sxs-lookup"><span data-stu-id="ad496-118">Messaging</span></span>  
  
### <a name="sequence-establishment-messages"></a><span data-ttu-id="ad496-119">Mensajes de establecimiento de secuencia</span><span class="sxs-lookup"><span data-stu-id="ad496-119">Sequence Establishment Messages</span></span>  
 <span data-ttu-id="ad496-120">WCF implementa `CreateSequence` y `CreateSequenceResponse` mensajes para establecer una secuencia de mensajes confiable.</span><span class="sxs-lookup"><span data-stu-id="ad496-120">WCF implements `CreateSequence` and `CreateSequenceResponse` messages to establish a reliable message sequence.</span></span> <span data-ttu-id="ad496-121">Las siguientes restricciones son aplicables:</span><span class="sxs-lookup"><span data-stu-id="ad496-121">The following constraints apply:</span></span>  
  
- <span data-ttu-id="ad496-122">B1101: El iniciador de WCF no genera el elemento Expires opcional en el `CreateSequence` mensaje o, en los casos cuando el `CreateSequence` mensaje contiene un `Offer` elemento, el elemento opcional `Expires` elemento en el `Offer` elemento.</span><span class="sxs-lookup"><span data-stu-id="ad496-122">B1101: The WCF Initiator does not generate the optional Expires element in the `CreateSequence` message or, in the cases when the `CreateSequence` message contains an `Offer` element, the optional `Expires` element in the `Offer` element.</span></span>  
  
- <span data-ttu-id="ad496-123">B1102: Al obtener acceso a la `CreateSequence` mensaje WCF`Responder` envía y recibe ambos `Expires` elementos si existen, pero no usa sus valores.</span><span class="sxs-lookup"><span data-stu-id="ad496-123">B1102: When accessing the `CreateSequence` message, the WCF`Responder` sends and receives both `Expires` elements if they exist, but does not use their values.</span></span>  
  
 <span data-ttu-id="ad496-124">WS-Reliable Messaging incluye el mecanismo `Offer` para establecer las dos secuencias correlacionadas inversas que forman una sesión.</span><span class="sxs-lookup"><span data-stu-id="ad496-124">WS-Reliable Messaging introduces the `Offer` mechanism to establish the two converse correlated sequences that form a session.</span></span>  
  
- <span data-ttu-id="ad496-125">R1103: Si `CreateSequence` contiene un `Offer` elemento, el Respondedor de mensajería de confianza debe aceptar la secuencia y responder con `CreateSequenceResponse` que contiene un `wsrm:Accept` elemento, formando dos correlacionado secuencias inversas o rechazar la `CreateSequence`solicitud.</span><span class="sxs-lookup"><span data-stu-id="ad496-125">R1103: If `CreateSequence` contains an `Offer` element, the Reliable Messaging Responder must either accept the sequence and respond with `CreateSequenceResponse` that contains a `wsrm:Accept` element, forming two correlated converse sequences or reject the `CreateSequence` request.</span></span>  
  
- <span data-ttu-id="ad496-126">R1104: `SequenceAcknowledgement` y los mensajes de la aplicación que fluyen en una secuencia inversa se deben enviar a la referencia de punto de conexión `ReplyTo` de `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="ad496-126">R1104: `SequenceAcknowledgement` and application messages flowing on converse sequence must be sent to the `ReplyTo` endpoint reference of the `CreateSequence`.</span></span>  
  
- <span data-ttu-id="ad496-127">R1105: las referencias de punto de conexión `AcksTo` y `ReplyTo` en `CreateSequence` deben tener valores de dirección que coincidan byte a byte.</span><span class="sxs-lookup"><span data-stu-id="ad496-127">R1105: `AcksTo` and `ReplyTo` endpoint references in the `CreateSequence` must have address values that match the octet-wise.</span></span>  
  
     <span data-ttu-id="ad496-128">El servicio de respuesta WCF comprueba que la parte del URI del `AcksTo` y `ReplyTo` EPR es idénticos antes de crear una secuencia.</span><span class="sxs-lookup"><span data-stu-id="ad496-128">The WCF Responder verifies that the URI portion of the `AcksTo` and `ReplyTo` EPRs are identical before creating a sequence.</span></span>  
  
- <span data-ttu-id="ad496-129">R1106: las referencias de punto de conexión `AcksTo` y `ReplyTo` del mensaje `CreateSequence` deberían tener el mismo conjunto de parámetros de referencia.</span><span class="sxs-lookup"><span data-stu-id="ad496-129">R1106: `AcksTo` and `ReplyTo` Endpoint References in the `CreateSequence` should have the same set of reference parameters.</span></span>  
  
     <span data-ttu-id="ad496-130">WCF no exige, pero supone que [parámetros de referencia] de `AcksTo` y `ReplyTo` en `CreateSequence` son idénticas y utiliza [parámetros de referencia] de `ReplyTo` referencia de punto de conexión para las confirmaciones y los mensajes de secuencia inversa.</span><span class="sxs-lookup"><span data-stu-id="ad496-130">WCF does not enforce but assumes that [reference parameters] of `AcksTo` and `ReplyTo` on `CreateSequence` are identical and uses [reference parameters] from `ReplyTo` endpoint reference for acknowledgements and converse sequence messages.</span></span>  
  
- <span data-ttu-id="ad496-131">R1107: Cuando dos secuencias inversas se establecen utilizando el `Offer` mecanismo, `SequenceAcknowledgement` y mensajes de la aplicación que fluyen en secuencias inversas se deben enviar a la `ReplyTo` referencia del extremo de la `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="ad496-131">R1107: When two converse sequences are established using the `Offer` mechanism, `SequenceAcknowledgement` and application messages flowing on converse sequences must be sent to the `ReplyTo` endpoint reference of the `CreateSequence`.</span></span>  
  
- <span data-ttu-id="ad496-132">R1108: Cuando dos secuencias inversas se establecen mediante el mecanismo Offer, la `[address]` propiedad de la `wsrm:AcksTo` elemento secundario de referencia del extremo de la `wsrm:Accept` elemento de la `CreateSequenceResponse` debe coincidir byte a byte para el URI de destino de la `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="ad496-132">R1108: When two converse sequences are established using the Offer mechanism, the `[address]` property of the `wsrm:AcksTo` Endpoint Reference child element of the `wsrm:Accept` element of the `CreateSequenceResponse` must match byte-wise the destination URI of the `CreateSequence`.</span></span>  
  
- <span data-ttu-id="ad496-133">R1109: Cuando dos secuencias inversas se establecen utilizando el `Offer` mecanismo, los mensajes enviados por el iniciador y las confirmaciones de mensajes por parte del Respondedor se deben enviar a la misma referencia de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="ad496-133">R1109: When two converse sequences are established using the `Offer` mechanism, messages sent by initiator and acknowledgements to messages by responder must be sent to the same Endpoint Reference.</span></span>  
  
     <span data-ttu-id="ad496-134">WCF usa WS-Reliable Messaging para establecer sesiones confiables entre el iniciador y Respondedor.</span><span class="sxs-lookup"><span data-stu-id="ad496-134">WCF uses WS-Reliable Messaging to establish reliable sessions between the Initiator and Responder.</span></span> <span data-ttu-id="ad496-135">Implementación de WS-Reliable Messaging de WCF proporciona una sesión confiable para completa y de solicitud-respuesta unidireccional, patrones de mensajería dúplex.</span><span class="sxs-lookup"><span data-stu-id="ad496-135">WCF's WS-Reliable Messaging implementation provides reliable session for one-way, request-reply and full duplex messaging patterns.</span></span> <span data-ttu-id="ad496-136">El WS-Reliable Messaging `Offer` mecanismo en `CreateSequence` / `CreateSequenceResponse` le permite establecer dos secuencias inversas correlacionadas y proporciona un protocolo de sesión que es apto para todos los puntos de conexión del mensaje.</span><span class="sxs-lookup"><span data-stu-id="ad496-136">The WS-Reliable Messaging `Offer` mechanism on `CreateSequence`/`CreateSequenceResponse` lets you establish two correlated converse sequences, and provides a session protocol that is suitable for all message endpoints.</span></span> <span data-ttu-id="ad496-137">Dado que WCF proporciona una garantía de seguridad para este tipo de sesión incluida la protección de extremo a otro para la integridad de la sesión, es práctico asegurar que llegan los mensajes dirigidos a la misma entidad al mismo destino.</span><span class="sxs-lookup"><span data-stu-id="ad496-137">Because WCF provides a security guarantee for such a session including end-to-end protection for session integrity, it is practical to ensure messages intended to the same party are arriving at the same destination.</span></span> <span data-ttu-id="ad496-138">Esto también permite el “apoyo a caballo” de confirmaciones de secuencias en mensajes de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="ad496-138">This also allows piggy-backing of sequence acknowledgements on application messages.</span></span> <span data-ttu-id="ad496-139">Por lo tanto, las restricciones R1104, R1105 y R1108 se aplican a WCF.</span><span class="sxs-lookup"><span data-stu-id="ad496-139">Therefore, constraints R1104, R1105, and R1108 apply to WCF.</span></span>  
  
 <span data-ttu-id="ad496-140">Ejemplo de mensaje `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="ad496-140">An example of a `CreateSequence` message.</span></span>  
  
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
  
 <span data-ttu-id="ad496-141">Ejemplo de mensaje `CreateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="ad496-141">An example of a `CreateSequenceResponse` message.</span></span>  
  
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
  
### <a name="sequence"></a><span data-ttu-id="ad496-142">Secuencia</span><span class="sxs-lookup"><span data-stu-id="ad496-142">Sequence</span></span>  
 <span data-ttu-id="ad496-143">A continuación, se muestra una lista de restricciones que se aplican a las secuencias:</span><span class="sxs-lookup"><span data-stu-id="ad496-143">The following is a list of constraints that apply to sequences:</span></span>  
  
- <span data-ttu-id="ad496-144">Genera B1201:WCF y no mayores que los números de secuencia de accesos `xs:long`del valor inclusivo máximo, 9223372036854775807.</span><span class="sxs-lookup"><span data-stu-id="ad496-144">B1201:WCF generates and accesses sequence numbers no higher than `xs:long`’s maximum inclusive value, 9223372036854775807.</span></span>  
  
- <span data-ttu-id="ad496-145">B1202:WCF siempre genera un mensaje de último cuerpo vacío con el URI de acción de `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`.</span><span class="sxs-lookup"><span data-stu-id="ad496-145">B1202:WCF always generates an empty-bodied last message with the action URI of `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`.</span></span>  
  
- <span data-ttu-id="ad496-146">B1203: WCF recibe y entrega un mensaje con un encabezado de secuencia que contiene un `LastMessage` elemento siempre y cuando el URI de acción no es `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`.</span><span class="sxs-lookup"><span data-stu-id="ad496-146">B1203: WCF receives and delivers a message with a Sequence header that contains a `LastMessage` element as long as the action URI is not `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`.</span></span>  
  
 <span data-ttu-id="ad496-147">Ejemplo de encabezado de secuencia.</span><span class="sxs-lookup"><span data-stu-id="ad496-147">An example of a Sequence Header.</span></span>  
  
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
  
### <a name="ackrequested-header"></a><span data-ttu-id="ad496-148">Encabezado AckRequested</span><span class="sxs-lookup"><span data-stu-id="ad496-148">AckRequested Header</span></span>  
 <span data-ttu-id="ad496-149">WCF usa `AckRequested` encabezado como un mecanismo keep-alive.</span><span class="sxs-lookup"><span data-stu-id="ad496-149">WCF uses `AckRequested` Header as a keep-alive mechanism.</span></span> <span data-ttu-id="ad496-150">WCF no genera opcional `MessageNumber` elemento.</span><span class="sxs-lookup"><span data-stu-id="ad496-150">WCF does not generate the optional `MessageNumber` element.</span></span> <span data-ttu-id="ad496-151">Al recibir un mensaje con un `AckRequested` encabezado que contiene el `MessageNumber` elemento, WCF omite el `MessageNumber` valor del elemento, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ad496-151">Upon receiving a message with an `AckRequested` header that contains the `MessageNumber` element, WCF ignores the `MessageNumber` element’s value, as shown in the following example.</span></span>  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>  
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
  </wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement-header"></a><span data-ttu-id="ad496-152">Encabezado SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="ad496-152">SequenceAcknowledgement Header</span></span>  
 <span data-ttu-id="ad496-153">WCF usa un mecanismo para confirmaciones de secuencias proporcionadas en WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="ad496-153">WCF uses piggy-back mechanism for sequence acknowledgements provided in WS-Reliable Messaging.</span></span>  
  
- <span data-ttu-id="ad496-154">R1401: Cuando dos secuencias inversas se establecen utilizando el `Offer` mecanismo, el `SequenceAcknowledgement` encabezado puede incluirse en cualquier mensaje de aplicación transmitido al destinatario deseado.</span><span class="sxs-lookup"><span data-stu-id="ad496-154">R1401: When two converse sequences are established using the `Offer` mechanism, the `SequenceAcknowledgement` header may be included in any application message transmitted to the intended recipient.</span></span>  
  
- <span data-ttu-id="ad496-155">B1402: Cuando WCF debe generar una confirmación antes de recibir ningún mensaje de secuencia (por ejemplo, para satisfacer un `AckRequested` mensaje), WCF genera un `SequenceAcknowledgement` encabezado que contiene el intervalo 0-0, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ad496-155">B1402: When WCF must generate an acknowledgement prior to receiving any sequence messages (for example, to satisfy an `AckRequested` message), WCF generates a `SequenceAcknowledgement` header that contains the range 0-0, as shown in the following example.</span></span>  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>  
        urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
      </wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="0" Lower="0"/>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
- <span data-ttu-id="ad496-156">B1403: WCF no genera `SequenceAcknowledgement` los encabezados que contienen un `Nack` elemento, pero admite `Nack` elementos.</span><span class="sxs-lookup"><span data-stu-id="ad496-156">B1403: WCF does not generate `SequenceAcknowledgement` headers that contain a `Nack` element but supports `Nack` elements.</span></span>  
  
### <a name="ws-reliablemessaging-faults"></a><span data-ttu-id="ad496-157">Errores de WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="ad496-157">WS-ReliableMessaging Faults</span></span>  
 <span data-ttu-id="ad496-158">La siguiente es una lista de restricciones que se aplican a la implementación de WCF de errores de WS-Reliable Messaging:</span><span class="sxs-lookup"><span data-stu-id="ad496-158">The following is a list of constraints that apply to the WCF implementation of WS-Reliable Messaging faults:</span></span>  
  
- <span data-ttu-id="ad496-159">B1501: WCF no genera `MessageNumberRollover` errores.</span><span class="sxs-lookup"><span data-stu-id="ad496-159">B1501: WCF does not generate `MessageNumberRollover` faults.</span></span>  
  
- <span data-ttu-id="ad496-160">Puede generar el punto de conexión B1502:WCF `CreateSequenceRefused` produce un error como se describe en la especificación.</span><span class="sxs-lookup"><span data-stu-id="ad496-160">B1502:WCF endpoint may generate `CreateSequenceRefused` faults as described in the specification.</span></span>  
  
- <span data-ttu-id="ad496-161">B1503:when el punto de conexión de servicio alcanza su límite de conexión y no se puede procesar nuevas conexiones, WCF genera adicional `CreateSequenceRefused` subcódigo, de error `netrm:ConnectionLimitReached`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ad496-161">B1503:When the service endpoint reaches its connection limit and cannot process new connections, WCF generates an additional `CreateSequenceRefused` fault subcode, `netrm:ConnectionLimitReached`, as shown in the following example.</span></span>  
  
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
  
### <a name="ws-addressing-faults"></a><span data-ttu-id="ad496-162">Errores WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="ad496-162">WS-Addressing Faults</span></span>  
 <span data-ttu-id="ad496-163">Dado que WS-Reliable Messaging utiliza WS-Addressing, WS-Reliable Messaging WCF implementación puede generar errores de WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="ad496-163">Because WS-Reliable Messaging uses WS-Addressing, WCF WS-Reliable Messaging implementation may generate WS-Addressing faults.</span></span> <span data-ttu-id="ad496-164">En esta sección se trata los errores de WS-Addressing que WCF genera explícitamente en la capa de WS-Reliable Messaging:</span><span class="sxs-lookup"><span data-stu-id="ad496-164">This section covers the WS-Addressing faults that WCF explicitly generates at the WS-Reliable Messaging layer:</span></span>  
  
- <span data-ttu-id="ad496-165">B1601:WCF genera el error requiere un encabezado Addressing mensaje cuando se cumple una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="ad496-165">B1601:WCF generates the fault Message Addressing Header Required when one of the following is true:</span></span>  
  
    - <span data-ttu-id="ad496-166">Falta un encabezado `Sequence` y un encabezado `Action` en un mensaje.</span><span class="sxs-lookup"><span data-stu-id="ad496-166">A message is missing a `Sequence` header and an `Action` header.</span></span>  
  
    - <span data-ttu-id="ad496-167">Falta un encabezado `CreateSequence` en un mensaje `MessageId`.</span><span class="sxs-lookup"><span data-stu-id="ad496-167">A `CreateSequence` message is missing a `MessageId` header.</span></span>  
  
    - <span data-ttu-id="ad496-168">Falta un encabezado `CreateSequence` en un mensaje `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="ad496-168">A `CreateSequence` message is missing a `ReplyTo` header.</span></span>  
  
- <span data-ttu-id="ad496-169">B1602:WCF genera el error no admite la acción como respuesta a un mensaje que falta un `Sequence` encabezado y tiene un `Action` encabezado que no es reconocido en la especificación WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="ad496-169">B1602:WCF generates the fault Action Not Supported in reply to a message that is missing a `Sequence` header and has an `Action` header that is not a recognized in the WS-Reliable Messaging specification.</span></span>  
  
- <span data-ttu-id="ad496-170">B1603:WCF genera el error extremo no disponible para indicar que el punto de conexión no procesa la secuencia tras el examen de la `CreateSequence` encabezados de direccionamiento del mensaje.</span><span class="sxs-lookup"><span data-stu-id="ad496-170">B1603:WCF generates the fault Endpoint Unavailable to indicate that the endpoint does not process the sequence based upon examination of the `CreateSequence` message’s addressing headers.</span></span>  
  
## <a name="protocol-composition"></a><span data-ttu-id="ad496-171">Composición de protocolos</span><span class="sxs-lookup"><span data-stu-id="ad496-171">Protocol Composition</span></span>  
  
### <a name="composition-with-ws-addressing"></a><span data-ttu-id="ad496-172">Composición con WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="ad496-172">Composition with WS-Addressing</span></span>  
 <span data-ttu-id="ad496-173">WCF admite dos versiones de WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] y W3C WS-Addressing 1.0 recomendaciones [WS-ADDR-CORE] y [WS-ADDR-SOAP].</span><span class="sxs-lookup"><span data-stu-id="ad496-173">WCF supports two versions of WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] and W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] and [WS-ADDR-SOAP].</span></span>  
  
 <span data-ttu-id="ad496-174">Aunque la especificación de WS-Reliable Messaging solo menciona a WS-Addressing 2004/08, no limita la versión de WS-Addressing que se ha de utilizar.</span><span class="sxs-lookup"><span data-stu-id="ad496-174">While the WS-Reliable Messaging specification mentions only WS-Addressing 2004/08, it does not restrict the WS-Addressing version to be used.</span></span> <span data-ttu-id="ad496-175">La siguiente es una lista de restricciones que se aplican a WCF:</span><span class="sxs-lookup"><span data-stu-id="ad496-175">The following is a list of constraints that apply to WCF:</span></span>  
  
- <span data-ttu-id="ad496-176">R2101: ambos WS-Addressing 2004/08 y WS-Addressing 1.0 se pueden usar con WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="ad496-176">R2101:Both WS-Addressing 2004/08 and WS-Addressing 1.0 can be used with WS-Reliable Messaging.</span></span>  
  
- <span data-ttu-id="ad496-177">Se debe usar R2102:A única versión de WS-Addressing a lo largo de una secuencia de WS-Reliable Messaging determinada o un par de secuencias inversas correlacionadas mediante el `wsrm:Offer` mecanismo.</span><span class="sxs-lookup"><span data-stu-id="ad496-177">R2102:A single version of WS-Addressing must be used throughout a given WS-Reliable Messaging sequence or a pair of converse sequences correlated by using the `wsrm:Offer` mechanism.</span></span>  
  
### <a name="composition-with-soap"></a><span data-ttu-id="ad496-178">Composición con SOAP</span><span class="sxs-lookup"><span data-stu-id="ad496-178">Composition with SOAP</span></span>  
 <span data-ttu-id="ad496-179">WCF admite el uso de SOAP 1.1 y SOAP 1.2 con WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="ad496-179">WCF supports use of both SOAP 1.1 and SOAP 1.2 with WS-Reliable Messaging.</span></span>  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a><span data-ttu-id="ad496-180">Composición con WS-Security y WS-SecureConversation</span><span class="sxs-lookup"><span data-stu-id="ad496-180">Composition with WS-Security and WS-SecureConversation</span></span>  
 <span data-ttu-id="ad496-181">WCF proporciona protección para secuencias de WS-Reliable Messaging mediante el uso de transporte (HTTPS) segura, la composición con WS-Security y composición con WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="ad496-181">WCF provides protection for WS-Reliable Messaging sequences by using secure Transport (HTTPS), composition with WS-Security, and composition with WS-Secure Conversation.</span></span> <span data-ttu-id="ad496-182">La siguiente es una lista de restricciones que se aplican a WCF:</span><span class="sxs-lookup"><span data-stu-id="ad496-182">The following is a list of constraints that apply to WCF:</span></span>  
  
- <span data-ttu-id="ad496-183">R2301: para proteger la integridad de una secuencia de WS-Reliable Messaging además de la integridad y confidencialidad de los mensajes individuales, WCF requiere que se deben utilizar WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="ad496-183">R2301:To protect the integrity of a WS-Reliable Messaging sequence in addition to the integrity and confidentiality of individual messages, WCF requires that WS-Secure Conversation must be used.</span></span>  
  
- <span data-ttu-id="ad496-184">R2302:AWS-Secure Conversation debe establecerse antes de establecer las secuencias de WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="ad496-184">R2302:AWS-Secure Conversation session must be established prior to establishing WS-Reliable Messaging sequence(s).</span></span>  
  
- <span data-ttu-id="ad496-185">R2303: Si la duración de secuencia de WS-Reliable Messaging supera WS-Secure Conversation, la duración de la sesión, el `SecurityContextToken` establecido mediante WS-Secure Conversation se debe renovar utilizando el enlace de renovación WS-Secure Conversation correspondiente.</span><span class="sxs-lookup"><span data-stu-id="ad496-185">R2303: If the WS-Reliable Messaging sequence lifetime exceeds the WS-Secure Conversation session’s lifetime, the `SecurityContextToken` established by using WS-Secure Conversation must be renewed by using the corresponding WS-Secure Conversation Renewal binding.</span></span>  
  
- <span data-ttu-id="ad496-186">B2304:ws-secuencia de mensajería de confianza o un par de secuencias inversas correlacionadas siempre se enlazan a una sola sesión de WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="ad496-186">B2304:WS-Reliable Messaging sequence or a pair of correlated converse sequences are always bound to a single WS-SecureConversation session.</span></span>  
  
     <span data-ttu-id="ad496-187">El origen WCF genera el `wsse:SecurityTokenReference` elemento en la sección de extensibilidad de elemento de la `CreateSequence` mensaje.</span><span class="sxs-lookup"><span data-stu-id="ad496-187">The WCF source generates the `wsse:SecurityTokenReference` element in the element extensibility section of the `CreateSequence` message.</span></span>  
  
- <span data-ttu-id="ad496-188">R2305:when compuesta con WS-Secure Conversation, un `CreateSequence` mensaje debe contener el `wsse:SecurityTokenReference` elemento.</span><span class="sxs-lookup"><span data-stu-id="ad496-188">R2305:When composed with WS-Secure Conversation, a `CreateSequence` message must contain the `wsse:SecurityTokenReference` element.</span></span>  
  
## <a name="ws-reliable-messaging-ws-policy-assertion"></a><span data-ttu-id="ad496-189">Aserción de WS-Policy de WS-Reliable Messaging </span><span class="sxs-lookup"><span data-stu-id="ad496-189">WS-Reliable Messaging WS-Policy Assertion</span></span>  
 <span data-ttu-id="ad496-190">WCF usa WS-Reliable Messaging de aserción de WS-Policy `wsrm:RMAssertion` para describir funciones de extremos.</span><span class="sxs-lookup"><span data-stu-id="ad496-190">WCF uses WS-Reliable Messaging WS-Policy Assertion `wsrm:RMAssertion` to describe endpoints capabilities.</span></span> <span data-ttu-id="ad496-191">La siguiente es una lista de restricciones que se aplican a WCF:</span><span class="sxs-lookup"><span data-stu-id="ad496-191">The following is a list of constraints that apply to WCF:</span></span>  
  
- <span data-ttu-id="ad496-192">B3001: WCF adjunta `wsrm:RMAssertion` WS-Policy Assertion a `wsdl:binding` elementos.</span><span class="sxs-lookup"><span data-stu-id="ad496-192">B3001: WCF attaches `wsrm:RMAssertion` WS-Policy Assertion to `wsdl:binding` elements.</span></span> <span data-ttu-id="ad496-193">WCF admite datos adjuntos a `wsdl:binding` y `wsdl:port` elementos.</span><span class="sxs-lookup"><span data-stu-id="ad496-193">WCF supports both attachments to `wsdl:binding` and `wsdl:port` elements.</span></span>  
  
- <span data-ttu-id="ad496-194">B3002: WCF admite las siguientes propiedades opcionales de aserción de WS-Reliable Messaging y proporciona control sobre ellas en WCF`ReliableMessagingBindingElement`:</span><span class="sxs-lookup"><span data-stu-id="ad496-194">B3002: WCF supports the following optional properties of WS-Reliable Messaging assertion and provides control over them on the WCF`ReliableMessagingBindingElement`:</span></span>  
  
    - `wsrm:InactivityTimeout`  
  
    - `wsrm:AcknowledgementInterval`  
  
     <span data-ttu-id="ad496-195">A continuación se muestra un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ad496-195">The following is an example.</span></span>  
  
    ```xml  
    <wsrm:RMAssertion>  
      <wsrm:InactivityTimeout Milliseconds="600000" />  
      <wsrm:AcknowledgementInterval Milliseconds="200" />  
    </wsrm:RMAssertion>  
    ```  
  
## <a name="flow-control-ws-reliable-messaging-extension"></a><span data-ttu-id="ad496-196">Extensión de WS-Reliable Messaging de control de flujo</span><span class="sxs-lookup"><span data-stu-id="ad496-196">Flow Control WS-Reliable Messaging Extension</span></span>  
 <span data-ttu-id="ad496-197">WCF usa la extensibilidad de WS-Reliable Messaging para proporcionar un control más estricto adicional opcional sobre el flujo de mensajes de secuencias.</span><span class="sxs-lookup"><span data-stu-id="ad496-197">WCF uses WS-Reliable Messaging extensibility to provide optional additional tighter control over sequence message flow.</span></span>  
  
 <span data-ttu-id="ad496-198">Control de flujo se habilita estableciendo el <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="ad496-198">Flow control is enabled by setting the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="ad496-199">La siguiente es una lista de restricciones que se aplican a WCF:</span><span class="sxs-lookup"><span data-stu-id="ad496-199">The following is a list of constraints that apply to WCF:</span></span>  
  
- <span data-ttu-id="ad496-200">B4001: Cuando está habilitado el Control de flujo de mensajería confiable, WCF genera un `netrm:BufferRemaining` elemento en la extensibilidad de elementos de la `SequenceAcknowledgement` encabezado.</span><span class="sxs-lookup"><span data-stu-id="ad496-200">B4001: When Reliable Messaging Flow Control is enabled, WCF generates a `netrm:BufferRemaining` element in the element extensibility of the `SequenceAcknowledgement` header.</span></span>  
  
- <span data-ttu-id="ad496-201">B4002: Cuando se habilita el Control de flujo de mensajería confiable, WCF no requiere un `netrm:BufferRemaining` elemento esté presente en `SequenceAcknowledgement` encabezado, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ad496-201">B4002: When Reliable Messaging Flow Control is enabled, WCF does not require a `netrm:BufferRemaining` element to be present in `SequenceAcknowledgement` header, as shown in the following example.</span></span>  
  
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
  
- <span data-ttu-id="ad496-202">B4003: WCF usa `netrm:BufferRemaining` indicar cuántos mensajes nuevos el destino de la mensajería confiable puede almacenar en búfer.</span><span class="sxs-lookup"><span data-stu-id="ad496-202">B4003: WCF uses `netrm:BufferRemaining` to indicate how many new messages the Reliable Messaging Destination can buffer.</span></span>  
  
- <span data-ttu-id="ad496-203">B4004: el servicio de mensajería confiable de WCF limita el número de mensajes transmitidos cuando la aplicación de mensajería de confianza de destino no puede recibir mensajes rápidamente.</span><span class="sxs-lookup"><span data-stu-id="ad496-203">B4004:The WCF Reliable Messaging Service throttles the number of messages transmitted when the Reliable Messaging destination application cannot receive messages quickly.</span></span> <span data-ttu-id="ad496-204">El destino de la mensajería de confianza almacena en búfer los mensajes y el valor del elemento cae a 0.</span><span class="sxs-lookup"><span data-stu-id="ad496-204">The Reliable Messaging destination buffers messages and the element’s value drops to 0.</span></span>  
  
- <span data-ttu-id="ad496-205">B4005: WCF genera `netrm:BufferRemaining` entero valores entre 0 y 4.096, ambos incluidos y lee valores enteros entre 0 y `xs:int`del `maxInclusive` valor 214748364 inclusive.</span><span class="sxs-lookup"><span data-stu-id="ad496-205">B4005: WCF generates `netrm:BufferRemaining` integer values between 0 and 4096 inclusive, and reads integer values between 0 and `xs:int`’s `maxInclusive` value 214748364 inclusive.</span></span>  
  
## <a name="message-exchange-patterns"></a><span data-ttu-id="ad496-206">Modelos de intercambio de mensajes</span><span class="sxs-lookup"><span data-stu-id="ad496-206">Message Exchange Patterns</span></span>  
 <span data-ttu-id="ad496-207">Esta sección describe el comportamiento de WCF cuando se usa la WS-Reliable Messaging para patrones de intercambio de mensajes diferentes.</span><span class="sxs-lookup"><span data-stu-id="ad496-207">This section describes WCF's behavior when WS-Reliable Messaging is used for different Message Exchange Patterns.</span></span> <span data-ttu-id="ad496-208">Para cada patrón de intercambio de mensajes, se consideran los dos escenarios de implementación siguientes:</span><span class="sxs-lookup"><span data-stu-id="ad496-208">For each Message Exchange Pattern the following two deployments scenarios are considered:</span></span>  
  
- <span data-ttu-id="ad496-209">Iniciador no direccionable: Iniciador está tras el firewall; Servicio de respuesta puede entregar mensajes al iniciador sólo en las respuestas HTTP.</span><span class="sxs-lookup"><span data-stu-id="ad496-209">Non-Addressable Initiator: Initiator is behind firewall; Responder can deliver messages to Initiator only on HTTP responses.</span></span>  
  
- <span data-ttu-id="ad496-210">Iniciador direccionable: Iniciador y Respondedor se pueden enviar solicitudes HTTP; en otras palabras, se pueden establecer dos conexiones HTTP inversas.</span><span class="sxs-lookup"><span data-stu-id="ad496-210">Addressable Initiator: Initiator and Responder both can be sent HTTP requests; in other words, two converse HTTP connections can be established.</span></span>  
  
### <a name="one-way-non-addressable-initiator"></a><span data-ttu-id="ad496-211">Iniciador unidireccional no direccionable</span><span class="sxs-lookup"><span data-stu-id="ad496-211">One-way, Non-addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="ad496-212">Enlaces</span><span class="sxs-lookup"><span data-stu-id="ad496-212">Binding</span></span>  
 <span data-ttu-id="ad496-213">WCF proporciona un patrón de intercambio de mensajes unidireccional utilizando una secuencia sobre un canal HTTP.</span><span class="sxs-lookup"><span data-stu-id="ad496-213">WCF provides a one-way message exchange pattern using one sequence over one HTTP channel.</span></span> <span data-ttu-id="ad496-214">WCF usa las solicitudes HTTP para transmitir todos los mensajes del RMS al RMD y la respuesta HTTP para transmitir todos los mensajes del RMD al RMS.</span><span class="sxs-lookup"><span data-stu-id="ad496-214">WCF uses the HTTP requests to transmit all messages from the RMS to the RMD and the HTTP response to transmit all messages from the RMD to the RMS.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="ad496-215">Intercambio de CreateSequence</span><span class="sxs-lookup"><span data-stu-id="ad496-215">CreateSequence Exchange</span></span>  
 <span data-ttu-id="ad496-216">El iniciador de WCF genera un `CreateSequence` mensaje sin oferta.</span><span class="sxs-lookup"><span data-stu-id="ad496-216">The WCF Initiator generates a `CreateSequence` message with no offer.</span></span> <span data-ttu-id="ad496-217">El servicio de respuesta WCF asegura la `CreateSequence` no tenga ninguna oferta antes de crear una secuencia.</span><span class="sxs-lookup"><span data-stu-id="ad496-217">The WCF Responder ensures the `CreateSequence` has no offer before creating a sequence.</span></span> <span data-ttu-id="ad496-218">El servicio de respuesta WCF responde a la `CreateSequence` solicitud con un `CreateSequenceResponse` mensaje.</span><span class="sxs-lookup"><span data-stu-id="ad496-218">The WCF Responder replies to the `CreateSequence` request with a `CreateSequenceResponse` message.</span></span>  
  
#### <a name="sequenceacknowledgement"></a><span data-ttu-id="ad496-219">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="ad496-219">SequenceAcknowledgement</span></span>  
 <span data-ttu-id="ad496-220">El iniciador de WCF procesa las confirmaciones en la respuesta de todos los mensajes excepto el `CreateSequence` mensajes y mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="ad496-220">The WCF Initiator processes acknowledgements on the reply of all messages except the `CreateSequence` message and fault messages.</span></span> <span data-ttu-id="ad496-221">El servicio de respuesta WCF siempre genera una confirmación independiente en la respuesta a la secuencia y `AckRequested` mensajes.</span><span class="sxs-lookup"><span data-stu-id="ad496-221">The WCF Responder always generates a stand-alone acknowledgement in the response to both sequence and `AckRequested` messages.</span></span>  
  
#### <a name="terminatesequence-message"></a><span data-ttu-id="ad496-222">Mensaje TerminateSequence</span><span class="sxs-lookup"><span data-stu-id="ad496-222">TerminateSequence message</span></span>  
 <span data-ttu-id="ad496-223">WCF trata `TerminateSequence` como una operación unidireccional, lo que significa que la respuesta HTTP tiene un cuerpo vacío y el código de estado HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="ad496-223">WCF treats `TerminateSequence` as a one-way operation, meaning the HTTP response has an empty body and HTTP 202 status code.</span></span>  
  
### <a name="one-way-addressable-initiator"></a><span data-ttu-id="ad496-224">Iniciador unidireccional y direccionable</span><span class="sxs-lookup"><span data-stu-id="ad496-224">One Way, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="ad496-225">Enlaces</span><span class="sxs-lookup"><span data-stu-id="ad496-225">Binding</span></span>  
 <span data-ttu-id="ad496-226">WCF proporciona un patrón de intercambio de mensajes unidireccional utilizando una secuencia sobre una entrada y un canal de salida Http.</span><span class="sxs-lookup"><span data-stu-id="ad496-226">WCF provides a one-way message exchange pattern using one sequence over an inbound and an outbound Http channel.</span></span> <span data-ttu-id="ad496-227">WCF usa las solicitudes HTTP para transmitir todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="ad496-227">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="ad496-228">Todas las respuestas HTTP tienen un cuerpo vacío y código de estado HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="ad496-228">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="ad496-229">Intercambio de CreateSequence</span><span class="sxs-lookup"><span data-stu-id="ad496-229">CreateSequence Exchange</span></span>  
 <span data-ttu-id="ad496-230">El iniciador de WCF genera un `CreateSequence` mensaje sin oferta.</span><span class="sxs-lookup"><span data-stu-id="ad496-230">The WCF Initiator generates a `CreateSequence` message with no offer.</span></span> <span data-ttu-id="ad496-231">El servicio de respuesta WCF garantiza que el `CreateSequence` no tenga ninguna oferta antes de crear una secuencia.</span><span class="sxs-lookup"><span data-stu-id="ad496-231">The WCF Responder ensures that the `CreateSequence` has no offer before creating a sequence.</span></span> <span data-ttu-id="ad496-232">El servicio de respuesta WCF transmite el `CreateSequenceResponse` envía el mensaje en una solicitud HTTP con el `ReplyTo` referencia del extremo.</span><span class="sxs-lookup"><span data-stu-id="ad496-232">The WCF Responder transmits the `CreateSequenceResponse` message on an HTTP request addressed with the `ReplyTo` endpoint reference.</span></span>  
  
### <a name="duplex-addressable-initiator"></a><span data-ttu-id="ad496-233">Iniciador dúplex y direccionable</span><span class="sxs-lookup"><span data-stu-id="ad496-233">Duplex, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="ad496-234">Enlaces</span><span class="sxs-lookup"><span data-stu-id="ad496-234">Binding</span></span>  
 <span data-ttu-id="ad496-235">WCF proporciona un patrón de intercambio de mensajes bidireccional totalmente asincrónico usando dos secuencias sobre una entrada y un canal de salida HTTP.</span><span class="sxs-lookup"><span data-stu-id="ad496-235">WCF provides a fully asynchronous two-way message exchange pattern using two sequences over an inbound and an outbound HTTP channel.</span></span> <span data-ttu-id="ad496-236">WCF usa las solicitudes HTTP para transmitir todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="ad496-236">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="ad496-237">Todas las respuestas HTTP tienen un cuerpo vacío y código de estado HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="ad496-237">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="ad496-238">Intercambio de CreateSequence</span><span class="sxs-lookup"><span data-stu-id="ad496-238">CreateSequence Exchange</span></span>  
 <span data-ttu-id="ad496-239">El iniciador de WCF genera un `CreateSequence` mensaje con una oferta.</span><span class="sxs-lookup"><span data-stu-id="ad496-239">The WCF Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="ad496-240">El servicio de respuesta WCF garantiza que la `CreateSequence` tenga una oferta antes de crear una secuencia.</span><span class="sxs-lookup"><span data-stu-id="ad496-240">The WCF Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> <span data-ttu-id="ad496-241">WCF envía el `CreateSequenceResponse` en la solicitud HTTP dirigida a la `CreateSequence`del `ReplyTo` referencia del extremo.</span><span class="sxs-lookup"><span data-stu-id="ad496-241">WCF sends the `CreateSequenceResponse` on the HTTP request addressed to the `CreateSequence`’s `ReplyTo` endpoint reference.</span></span>  
  
#### <a name="sequence-lifetime"></a><span data-ttu-id="ad496-242">Duración de la secuencia</span><span class="sxs-lookup"><span data-stu-id="ad496-242">Sequence Lifetime</span></span>  
 <span data-ttu-id="ad496-243">WCF trata las dos secuencias como una sesión totalmente dúplex.</span><span class="sxs-lookup"><span data-stu-id="ad496-243">WCF treats the two sequences as one fully duplex session.</span></span>  
  
 <span data-ttu-id="ad496-244">Tras generar un error que se produce un error en una secuencia, WCF espera que el extremo remoto al error en ambas secuencias.</span><span class="sxs-lookup"><span data-stu-id="ad496-244">Upon generating a fault that faults one sequence, WCF expects the remote endpoint to fault both sequences.</span></span> <span data-ttu-id="ad496-245">Tras leer un error que se produce un error en una secuencia, WCF produce un error en ambas secuencias.</span><span class="sxs-lookup"><span data-stu-id="ad496-245">Upon reading a fault that faults one sequence, WCF faults both sequences.</span></span>  
  
 <span data-ttu-id="ad496-246">WCF puede cerrar su secuencia saliente y continuar procesando los mensajes en su secuencia entrante.</span><span class="sxs-lookup"><span data-stu-id="ad496-246">WCF can close its outbound sequence and continue to process messages on its inbound sequence.</span></span> <span data-ttu-id="ad496-247">Por el contrario, WCF puede procesar el cierre de la secuencia entrante y continuar enviando mensajes en su secuencia saliente.</span><span class="sxs-lookup"><span data-stu-id="ad496-247">Conversely, WCF can process the close of the inbound sequence and continue to send messages on its outbound sequence.</span></span>  
  
### <a name="request-reply-non-addressable-initiator"></a><span data-ttu-id="ad496-248">Iniciador no direccionable de solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="ad496-248">Request-Reply, Non-Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="ad496-249">Enlaces</span><span class="sxs-lookup"><span data-stu-id="ad496-249">Binding</span></span>  
 <span data-ttu-id="ad496-250">WCF ofrece un sentido y patrón de intercambio de mensajes de solicitud-respuesta usando dos secuencias sobre un canal HTTP.</span><span class="sxs-lookup"><span data-stu-id="ad496-250">WCF provides a one-way and request-reply message exchange pattern using two sequences over one HTTP channel.</span></span> <span data-ttu-id="ad496-251">WCF usa las solicitudes HTTP para transmitir los mensajes de la secuencia de solicitud y usa las respuestas HTTP para transmitir los mensajes de la secuencia de respuesta.</span><span class="sxs-lookup"><span data-stu-id="ad496-251">WCF uses the HTTP requests to transmit the request sequence’s messages and uses the HTTP responses to transmit the reply sequence’s messages.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="ad496-252">Intercambio de CreateSequence</span><span class="sxs-lookup"><span data-stu-id="ad496-252">CreateSequence Exchange</span></span>  
 <span data-ttu-id="ad496-253">El iniciador de WCF genera un `CreateSequence` mensaje con una oferta.</span><span class="sxs-lookup"><span data-stu-id="ad496-253">The WCF Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="ad496-254">El servicio de respuesta WCF garantiza que la `CreateSequence` tenga una oferta antes de crear una secuencia.</span><span class="sxs-lookup"><span data-stu-id="ad496-254">The WCF Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> <span data-ttu-id="ad496-255">El servicio de respuesta WCF responde a la `CreateSequence` solicitud con un `CreateSequenceResponse` mensaje.</span><span class="sxs-lookup"><span data-stu-id="ad496-255">The WCF Responder replies to the `CreateSequence` request with a `CreateSequenceResponse` message.</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="ad496-256">Mensaje unidireccional</span><span class="sxs-lookup"><span data-stu-id="ad496-256">One-way Message</span></span>  
 <span data-ttu-id="ad496-257">Para completar correctamente un protocolo de intercambio de mensajes unidireccional, el iniciador de WCF transmite un mensaje de secuencia de solicitud en la solicitud HTTP y recibe una independiente `SequenceAcknowledgement` mensaje en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="ad496-257">To complete a one-way message exchange protocol successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a standalone `SequenceAcknowledgement` message on the HTTP response.</span></span> <span data-ttu-id="ad496-258">La `SequenceAcknowledgement` debe confirmar el mensaje transmitido.</span><span class="sxs-lookup"><span data-stu-id="ad496-258">The `SequenceAcknowledgement` must acknowledge the message transmitted.</span></span>  
  
 <span data-ttu-id="ad496-259">El servicio de respuesta WCF puede responder a la solicitud con una confirmación, un error o una respuesta con un cuerpo vacío y el código de estado HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="ad496-259">The WCF Responder can reply to the request with an acknowledgement, a fault, or a response with an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="two-way-messages"></a><span data-ttu-id="ad496-260">Mensajes bidireccionales</span><span class="sxs-lookup"><span data-stu-id="ad496-260">Two Way Messages</span></span>  
 <span data-ttu-id="ad496-261">Para completar correctamente un protocolo de intercambio de mensajes bidireccional, el iniciador de WCF transmite un mensaje de secuencia de solicitud en la solicitud HTTP y recibe un mensaje de secuencia de respuesta en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="ad496-261">To complete a two way message exchange protocol successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a reply sequence message on the HTTP response.</span></span> <span data-ttu-id="ad496-262">La respuesta debe llevar una `SequenceAcknowledgement` que confirme que se ha transmitido el mensaje de secuencia de solicitud.</span><span class="sxs-lookup"><span data-stu-id="ad496-262">The response must carry a `SequenceAcknowledgement` acknowledging the request sequence message transmitted.</span></span>  
  
 <span data-ttu-id="ad496-263">El servicio de respuesta WCF puede responder a la solicitud con una respuesta de la aplicación, un error o una respuesta con un cuerpo vacío y el código de estado HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="ad496-263">The WCF Responder can reply to the request with an application reply, a fault or a response with an empty body and HTTP 202 status code.</span></span>  
  
 <span data-ttu-id="ad496-264">Debido a la presencia de mensajes unidireccionales y al control de tiempo de las respuestas de la aplicación, el número de secuencia del mensaje de secuencia de solicitud y el número de secuencia del mensaje de respuesta no tienen ninguna correlación.</span><span class="sxs-lookup"><span data-stu-id="ad496-264">Because of the presence of one-way messages and the timing of application replies, the request sequence message’s sequence number and the response message’s sequence number have no correlation.</span></span>  
  
#### <a name="retrying-replies"></a><span data-ttu-id="ad496-265">Reintento de respuestas</span><span class="sxs-lookup"><span data-stu-id="ad496-265">Retrying Replies</span></span>  
 <span data-ttu-id="ad496-266">WCF se basa en la correlación de solicitud-respuesta HTTP para la correlación de protocolo de intercambio de mensajes bidireccional.</span><span class="sxs-lookup"><span data-stu-id="ad496-266">WCF relies on HTTP request-reply correlation for two-way message exchange protocol correlation.</span></span> <span data-ttu-id="ad496-267">Por este motivo, el iniciador de WCF no deja de reintentar un mensaje de secuencia de solicitud cuando se confirma el mensaje de secuencia de solicitud, sino cuando la respuesta HTTP lleva una confirmación, el mensaje de usuario o el error.</span><span class="sxs-lookup"><span data-stu-id="ad496-267">Because of this, the WCF Initiator does not stop retrying a request sequence message when the request sequence message is acknowledged but rather when the HTTP response carries an acknowledgement, user message, or fault.</span></span> <span data-ttu-id="ad496-268">El servicio de respuesta WCF reintenta las respuestas en la bifurcación de la solicitud HTTP de la solicitud a la que se correlaciona la respuesta.</span><span class="sxs-lookup"><span data-stu-id="ad496-268">The WCF Responder retries replies on the HTTP request leg of the request to which the reply is correlated.</span></span>  
  
#### <a name="lastmessage-exchange"></a><span data-ttu-id="ad496-269">Intercambio de LastMessage</span><span class="sxs-lookup"><span data-stu-id="ad496-269">LastMessage Exchange</span></span>  
 <span data-ttu-id="ad496-270">El iniciador de WCF genera y transmite un último mensaje con cuerpo vacío en la bifurcación de la solicitud HTTP.</span><span class="sxs-lookup"><span data-stu-id="ad496-270">The WCF Initiator generates and transmits an empty bodied last message on the HTTP request leg.</span></span> <span data-ttu-id="ad496-271">WCF requiere una respuesta pero omite el mensaje de respuesta real.</span><span class="sxs-lookup"><span data-stu-id="ad496-271">WCF requires a response but ignores the actual response message.</span></span> <span data-ttu-id="ad496-272">El servicio de respuesta WCF responde a último mensaje de cuerpo vacío con cuerpo vacío último mensaje de la secuencia de respuesta la secuencia de solicitud.</span><span class="sxs-lookup"><span data-stu-id="ad496-272">The WCF Responder replies to the request sequence’s empty-bodied last message with the reply sequence’s empty-bodied last message.</span></span>  
  
 <span data-ttu-id="ad496-273">Si el servicio de respuesta WCF recibe un último mensaje en el que el URI de acción no es `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`, las respuestas con un último mensaje de WCF.</span><span class="sxs-lookup"><span data-stu-id="ad496-273">If the WCF Responder receives a last message in which the action URI is not `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`, WCF replies with a last message.</span></span> <span data-ttu-id="ad496-274">En el caso de un protocolo de intercambio de mensajes bidireccional, el último mensaje lleva el mensaje de la aplicación; en el caso de un protocolo de intercambio de mensajes unidireccional, el último mensaje está vacío.</span><span class="sxs-lookup"><span data-stu-id="ad496-274">In the case of a two-way message exchange protocol, the last message carries the application message; in the case of a one-way message exchange protocol, the last message is empty.</span></span>  
  
 <span data-ttu-id="ad496-275">El servicio de respuesta WCF no requiere una confirmación para el último mensaje de la secuencia de respuesta cuerpo vacío.</span><span class="sxs-lookup"><span data-stu-id="ad496-275">The WCF Responder does not require an acknowledgement for the reply sequence’s empty-bodied last message.</span></span>  
  
#### <a name="terminatesequence-exchange"></a><span data-ttu-id="ad496-276">Intercambio de TerminateSequence</span><span class="sxs-lookup"><span data-stu-id="ad496-276">TerminateSequence Exchange</span></span>  
 <span data-ttu-id="ad496-277">Cuando todas las solicitudes han recibido una respuesta válida, el iniciador de WCF genera y transmite la secuencia de solicitud `TerminateSequence` mensaje en la bifurcación de la solicitud HTTP.</span><span class="sxs-lookup"><span data-stu-id="ad496-277">When all requests have received a valid reply, the WCF Initiator generates and transmits the request sequence’s `TerminateSequence` message on the HTTP request leg.</span></span> <span data-ttu-id="ad496-278">WCF requiere una respuesta pero omite el mensaje de respuesta real.</span><span class="sxs-lookup"><span data-stu-id="ad496-278">WCF requires a response but ignores the actual response message.</span></span> <span data-ttu-id="ad496-279">El servicio de respuesta WCF responde a la secuencia de solicitud `TerminateSequence` mensaje con la secuencia de respuesta `TerminateSequence` mensaje.</span><span class="sxs-lookup"><span data-stu-id="ad496-279">The WCF Responder replies to the request sequence’s `TerminateSequence` message with the reply sequence’s `TerminateSequence` message.</span></span>  
  
 <span data-ttu-id="ad496-280">En una secuencia de apagado normal, ambos mensajes `TerminateSequence` llevan un `SequenceAcknowledgement` de intervalo completo.</span><span class="sxs-lookup"><span data-stu-id="ad496-280">In a normal shutdown sequence, both `TerminateSequence` messages carry a full range `SequenceAcknowledgement`.</span></span>  
  
### <a name="requestreply-addressable-initiator"></a><span data-ttu-id="ad496-281">Iniciador direccionable de solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="ad496-281">Request/Reply, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="ad496-282">Enlaces</span><span class="sxs-lookup"><span data-stu-id="ad496-282">Binding</span></span>  
 <span data-ttu-id="ad496-283">WCF proporciona un patrón de intercambio de mensajes de solicitud-respuesta utilizando dos secuencias a través de una entrada y un canal de salida HTTP.</span><span class="sxs-lookup"><span data-stu-id="ad496-283">WCF provides a request-reply message exchange pattern using two sequences over an inbound and an outbound HTTP channel.</span></span> <span data-ttu-id="ad496-284">WCF usa las solicitudes HTTP para transmitir todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="ad496-284">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="ad496-285">Todas las respuestas HTTP tienen un cuerpo vacío y código de estado HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="ad496-285">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="ad496-286">Intercambio de CreateSequence</span><span class="sxs-lookup"><span data-stu-id="ad496-286">CreateSequence Exchange</span></span>  
 <span data-ttu-id="ad496-287">El iniciador de WCF genera un `CreateSequence` mensaje con una oferta.</span><span class="sxs-lookup"><span data-stu-id="ad496-287">The WCF Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="ad496-288">El servicio de respuesta WCF garantiza que la `CreateSequence` tenga una oferta antes de crear una secuencia.</span><span class="sxs-lookup"><span data-stu-id="ad496-288">The WCF Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> <span data-ttu-id="ad496-289">WCF envía el `CreateSequenceResponse` en la solicitud HTTP dirigida a la `CreateSequence`del `ReplyTo` referencia del extremo.</span><span class="sxs-lookup"><span data-stu-id="ad496-289">WCF sends the `CreateSequenceResponse` on the HTTP request addressed to the `CreateSequence`’s `ReplyTo` endpoint reference.</span></span>  
  
#### <a name="requestreply-correlation"></a><span data-ttu-id="ad496-290">Correlación entre solicitud y respuesta</span><span class="sxs-lookup"><span data-stu-id="ad496-290">Request/Reply Correlation</span></span>  
 <span data-ttu-id="ad496-291">El iniciador de WCF garantiza que todos los osito de mensajes de solicitud de aplicación una `MessageId` y un `ReplyTo` referencia del extremo.</span><span class="sxs-lookup"><span data-stu-id="ad496-291">The WCF Initiator ensures all application request messages bear a `MessageId` and a `ReplyTo` endpoint reference.</span></span> <span data-ttu-id="ad496-292">El iniciador de WCF se aplica el `CreateSequence` del mensaje `ReplyTo` referencia de punto de conexión en cada mensaje de solicitud de aplicación.</span><span class="sxs-lookup"><span data-stu-id="ad496-292">The WCF Initiator applies the `CreateSequence` message’s `ReplyTo` endpoint reference on each application request message.</span></span> <span data-ttu-id="ad496-293">El servicio de respuesta WCF requiere que los mensajes de solicitud entrante lleven un `MessageId` y un `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="ad496-293">The WCF Responder requires that incoming request messages bear a `MessageId` and a `ReplyTo`.</span></span> <span data-ttu-id="ad496-294">El servicio de respuesta WCF garantiza que los URI de la referencia de extremo de la `CreateSequence` y todos los mensajes de solicitud de aplicación son idénticos.</span><span class="sxs-lookup"><span data-stu-id="ad496-294">The WCF Responder ensures that the endpoint reference’s URI of both the `CreateSequence` and all application request messages are identical.</span></span>
