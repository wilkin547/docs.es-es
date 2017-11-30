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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d204600682ec8acbc229240c4e1bc859d8ea4d21
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="reliable-messaging-protocol-version-10"></a><span data-ttu-id="15ac1-102">Protocolo de mensajería de confianza versión 1.0</span><span class="sxs-lookup"><span data-stu-id="15ac1-102">Reliable Messaging Protocol version 1.0</span></span>
<span data-ttu-id="15ac1-103">Este tema cubre los detalles de implementación de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] para el protocolo de febrero de 2005 WS-ReliableMessaging (versión 1.0) necesario para la interoperación mediante el transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="15ac1-103">This topic covers [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] implementation details for the WS-Reliable Messaging February 2005 (version 1.0) protocol necessary for interoperation using the HTTP transport.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="15ac1-104"> sigue la especificación WS-ReliableMessaging con las restricciones y clarificaciones explicadas en este tema.</span><span class="sxs-lookup"><span data-stu-id="15ac1-104"> follows the WS-Reliable Messaging specification with the constraints and clarifications explained in this topic.</span></span> <span data-ttu-id="15ac1-105">Tenga en cuenta que la versión 1.0 del protocolo WS-ReliableMessaging se implementa a partir de [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15ac1-105">Note that the WS-ReliableMessaging version 1.0 protocol is implemented starting with the [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)].</span></span>  
  
 <span data-ttu-id="15ac1-106">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementa el protocolo WS-Reliable Messaging de febrero de 2005 en <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="15ac1-106">The WS-Reliable Messaging February 2005 protocol is implemented in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] by the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span></span>  
  
 <span data-ttu-id="15ac1-107">Para su comodidad, el tema utiliza las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="15ac1-107">For convenience, the topic uses the following roles:</span></span>  
  
-   <span data-ttu-id="15ac1-108">Iniciador: el cliente que inicia la creación de la secuencia de mensajes WS-Reliable</span><span class="sxs-lookup"><span data-stu-id="15ac1-108">Initiator: the client that initiates WS-Reliable Message sequence creation</span></span>  
  
-   <span data-ttu-id="15ac1-109">Respondedor: el servicio que recibe las solicitudes del iniciador</span><span class="sxs-lookup"><span data-stu-id="15ac1-109">Responder: the service that receives the initiator's requests</span></span>  
  
 <span data-ttu-id="15ac1-110">En este documento, se utilizan los prefijos y espacios de nombres de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="15ac1-110">This document uses the prefixes and namespaces in the following table.</span></span>  
  
|<span data-ttu-id="15ac1-111">Prefijo</span><span class="sxs-lookup"><span data-stu-id="15ac1-111">Prefix</span></span>|<span data-ttu-id="15ac1-112">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="15ac1-112">Namespace</span></span>|  
|------------|---------------|  
|<span data-ttu-id="15ac1-113">wsrm</span><span class="sxs-lookup"><span data-stu-id="15ac1-113">wsrm</span></span>|<span data-ttu-id="15ac1-114">http://schemas.xmlsoap.org/ws/2005/02/rm</span><span class="sxs-lookup"><span data-stu-id="15ac1-114">http://schemas.xmlsoap.org/ws/2005/02/rm</span></span>|  
|<span data-ttu-id="15ac1-115">netrm</span><span class="sxs-lookup"><span data-stu-id="15ac1-115">netrm</span></span>|<span data-ttu-id="15ac1-116">http://schemas.microsoft.com/ws/2006/05/rm</span><span class="sxs-lookup"><span data-stu-id="15ac1-116">http://schemas.microsoft.com/ws/2006/05/rm</span></span>|  
|<span data-ttu-id="15ac1-117">s</span><span class="sxs-lookup"><span data-stu-id="15ac1-117">s</span></span>|<span data-ttu-id="15ac1-118">http://www.w3.org/2003/05/soap-envelope</span><span class="sxs-lookup"><span data-stu-id="15ac1-118">http://www.w3.org/2003/05/soap-envelope</span></span>|  
|<span data-ttu-id="15ac1-119">wsa</span><span class="sxs-lookup"><span data-stu-id="15ac1-119">wsa</span></span>|<span data-ttu-id="15ac1-120">http://schemas.xmlsoap.org/ws/2005/08/addressing</span><span class="sxs-lookup"><span data-stu-id="15ac1-120">http://schemas.xmlsoap.org/ws/2005/08/addressing</span></span>|  
|<span data-ttu-id="15ac1-121">wsse</span><span class="sxs-lookup"><span data-stu-id="15ac1-121">wsse</span></span>|<span data-ttu-id="15ac1-122">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd</span><span class="sxs-lookup"><span data-stu-id="15ac1-122">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd</span></span>|  
  
## <a name="messaging"></a><span data-ttu-id="15ac1-123">Mensajería</span><span class="sxs-lookup"><span data-stu-id="15ac1-123">Messaging</span></span>  
  
### <a name="sequence-establishment-messages"></a><span data-ttu-id="15ac1-124">Mensajes de establecimiento de secuencia</span><span class="sxs-lookup"><span data-stu-id="15ac1-124">Sequence Establishment Messages</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="15ac1-125"> implementa mensajes `CreateSequence` y `CreateSequenceResponse` para establecer una secuencia de mensajes de confianza.</span><span class="sxs-lookup"><span data-stu-id="15ac1-125"> implements `CreateSequence` and `CreateSequenceResponse` messages to establish a reliable message sequence.</span></span> <span data-ttu-id="15ac1-126">Las siguientes restricciones son aplicables:</span><span class="sxs-lookup"><span data-stu-id="15ac1-126">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="15ac1-127">B1101: el iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no genera el elemento Expires opcional en el mensaje `CreateSequence` o, en los casos en los que el mensaje `CreateSequence` contiene un elemento `Offer`, el elemento opcional `Expires` en el elemento `Offer`.</span><span class="sxs-lookup"><span data-stu-id="15ac1-127">B1101: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator does not generate the optional Expires element in the `CreateSequence` message or, in the cases when the `CreateSequence` message contains an `Offer` element, the optional `Expires` element in the `Offer` element.</span></span>  
  
-   <span data-ttu-id="15ac1-128">B1102: al tener acceso al mensaje `CreateSequence`, el [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] de `Responder` envía y recibe ambos elementos `Expires` si existen, pero no usa sus valores.</span><span class="sxs-lookup"><span data-stu-id="15ac1-128">B1102: When accessing the `CreateSequence` message, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]`Responder` sends and receives both `Expires` elements if they exist, but does not use their values.</span></span>  
  
 <span data-ttu-id="15ac1-129">WS-Reliable Messaging incluye el mecanismo `Offer` para establecer las dos secuencias correlacionadas inversas que forman una sesión.</span><span class="sxs-lookup"><span data-stu-id="15ac1-129">WS-Reliable Messaging introduces the `Offer` mechanism to establish the two converse correlated sequences that form a session.</span></span>  
  
-   <span data-ttu-id="15ac1-130">R1103: si `CreateSequence` contiene un elemento `Offer`, el respondedor de la mensajería de confianza debe aceptar la secuencia y responder con `CreateSequenceResponse`, que contiene un elemento `wsrm:Accept`, formando dos secuencias correlacionadas inversas, o rechazar la solicitud `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="15ac1-130">R1103: If `CreateSequence` contains an `Offer` element, the Reliable Messaging Responder must either accept the sequence and respond with `CreateSequenceResponse` that contains a `wsrm:Accept` element, forming two correlated converse sequences or reject the `CreateSequence` request.</span></span>  
  
-   <span data-ttu-id="15ac1-131">R1104: `SequenceAcknowledgement` y los mensajes de la aplicación que fluyen en una secuencia inversa se deben enviar a la referencia de extremo `ReplyTo` de `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="15ac1-131">R1104: `SequenceAcknowledgement` and application messages flowing on converse sequence must be sent to the `ReplyTo` endpoint reference of the `CreateSequence`.</span></span>  
  
-   <span data-ttu-id="15ac1-132">R1105: las referencias de extremo `AcksTo` y `ReplyTo` en `CreateSequence` deben tener valores de dirección que coincidan byte a byte.</span><span class="sxs-lookup"><span data-stu-id="15ac1-132">R1105: `AcksTo` and `ReplyTo` endpoint references in the `CreateSequence` must have address values that match the octet-wise.</span></span>  
  
     <span data-ttu-id="15ac1-133">El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] comprueba que la parte del URI de las EPR `AcksTo` y `ReplyTo` sean idénticas antes de crear una secuencia.</span><span class="sxs-lookup"><span data-stu-id="15ac1-133">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder verifies that the URI portion of the `AcksTo` and `ReplyTo` EPRs are identical before creating a sequence.</span></span>  
  
-   <span data-ttu-id="15ac1-134">R1106: las referencias de extremo `AcksTo` y `ReplyTo` del mensaje `CreateSequence` deberían tener el mismo conjunto de parámetros de referencia.</span><span class="sxs-lookup"><span data-stu-id="15ac1-134">R1106: `AcksTo` and `ReplyTo` Endpoint References in the `CreateSequence` should have the same set of reference parameters.</span></span>  
  
     [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="15ac1-135"> no exige, pero supone que los parámetros de referencia de extremo `AcksTo` y `ReplyTo` en `CreateSequence` son idénticas y utiliza los parámetros de referencia de la referencia de extremo `ReplyTo` para las confirmaciones y los mensajes de secuencia inversa.</span><span class="sxs-lookup"><span data-stu-id="15ac1-135"> does not enforce but assumes that [reference parameters] of `AcksTo` and `ReplyTo` on `CreateSequence` are identical and uses [reference parameters] from `ReplyTo` endpoint reference for acknowledgements and converse sequence messages.</span></span>  
  
-   <span data-ttu-id="15ac1-136">R1107: cuando dos secuencias inversas se establecen por medio del mecanismo `Offer`, los mensajes de aplicación y `SequenceAcknowledgement` que fluyen en secuencias inversas se deben enviar a la referencia de extremo `ReplyTo` de `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="15ac1-136">R1107: When two converse sequences are established using the `Offer` mechanism, `SequenceAcknowledgement` and application messages flowing on converse sequences must be sent to the `ReplyTo` endpoint reference of the `CreateSequence`.</span></span>  
  
-   <span data-ttu-id="15ac1-137">R1108: cuando dos secuencias inversas se establecen mediante el mecanismo Offer, la propiedad `[address]` del elemento secundario de referencia de extremo `wsrm:AcksTo` del elemento `wsrm:Accept` de `CreateSequenceResponse` debe coincidir byte a byte con el URI de destino de `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="15ac1-137">R1108: When two converse sequences are established using the Offer mechanism, the `[address]` property of the `wsrm:AcksTo` Endpoint Reference child element of the `wsrm:Accept` element of the `CreateSequenceResponse` must match byte-wise the destination URI of the `CreateSequence`.</span></span>  
  
-   <span data-ttu-id="15ac1-138">R1109: cuando se establecen dos secuencias inversas por medio del mecanismo `Offer`, los mensajes enviados por el iniciador y las confirmaciones de los mensajes por parte del respondedor se deben enviar a la misma referencia de extremo.</span><span class="sxs-lookup"><span data-stu-id="15ac1-138">R1109: When two converse sequences are established using the `Offer` mechanism, messages sent by initiator and acknowledgements to messages by responder must be sent to the same Endpoint Reference.</span></span>  
  
     [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="15ac1-139"> utiliza WS-Reliable Messaging para establecer sesiones confiables entre el iniciador y el respondedor.</span><span class="sxs-lookup"><span data-stu-id="15ac1-139"> uses WS-Reliable Messaging to establish reliable sessions between the Initiator and Responder.</span></span> <span data-ttu-id="15ac1-140">La implementación de WS-Reliable Messaging de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona una sesión confiable para patrones de mensajería dúplex completa y de solicitud-respuesta unidireccional.</span><span class="sxs-lookup"><span data-stu-id="15ac1-140">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]'s WS-Reliable Messaging implementation provides reliable session for one-way, request-reply and full duplex messaging patterns.</span></span> <span data-ttu-id="15ac1-141">WS-Reliable Messaging `Offer` mecanismo en `CreateSequence` / `CreateSequenceResponse` le permite establecer dos secuencias inversas correlacionadas y proporciona un protocolo de sesión que es apto para todos los puntos de conexión de mensajes.</span><span class="sxs-lookup"><span data-stu-id="15ac1-141">The WS-Reliable Messaging `Offer` mechanism on `CreateSequence`/`CreateSequenceResponse` lets you establish two correlated converse sequences, and provides a session protocol that is suitable for all message endpoints.</span></span> <span data-ttu-id="15ac1-142">Dado que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona una garantía de seguridad para este tipo de sesiones, incluyendo la protección de un extremo a otro para la integridad de la sesión, es práctico asegurar que los mensajes dirigidos a la misma parte lleguen al mismo destino.</span><span class="sxs-lookup"><span data-stu-id="15ac1-142">Because [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides a security guarantee for such a session including end-to-end protection for session integrity, it is practical to ensure messages intended to the same party are arriving at the same destination.</span></span> <span data-ttu-id="15ac1-143">Esto también permite el “apoyo a caballo” de confirmaciones de secuencias en mensajes de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="15ac1-143">This also allows piggy-backing of sequence acknowledgements on application messages.</span></span> <span data-ttu-id="15ac1-144">Por consiguiente, las restricciones R1104, R1105, y R1108 se aplican a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15ac1-144">Therefore, constraints R1104, R1105, and R1108 apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 <span data-ttu-id="15ac1-145">Ejemplo de mensaje `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="15ac1-145">An example of a `CreateSequence` message.</span></span>  
  
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
  
 <span data-ttu-id="15ac1-146">Ejemplo de mensaje `CreateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="15ac1-146">An example of a `CreateSequenceResponse` message.</span></span>  
  
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
  
### <a name="sequence"></a><span data-ttu-id="15ac1-147">Secuencia</span><span class="sxs-lookup"><span data-stu-id="15ac1-147">Sequence</span></span>  
 <span data-ttu-id="15ac1-148">A continuación, se muestra una lista de restricciones que se aplican a las secuencias:</span><span class="sxs-lookup"><span data-stu-id="15ac1-148">The following is a list of constraints that apply to sequences:</span></span>  
  
-   <span data-ttu-id="15ac1-149">B1201:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera y obtiene acceso a los números de secuencia no superiores a `xs:long`del valor inclusivo máximo, 9223372036854775807.</span><span class="sxs-lookup"><span data-stu-id="15ac1-149">B1201:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates and accesses sequence numbers no higher than `xs:long`’s maximum inclusive value, 9223372036854775807.</span></span>  
  
-   <span data-ttu-id="15ac1-150">B1202:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] siempre genera un mensaje último cuerpo vacío con el URI de acción de http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage.</span><span class="sxs-lookup"><span data-stu-id="15ac1-150">B1202:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] always generates an empty-bodied last message with the action URI of http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage.</span></span>  
  
-   <span data-ttu-id="15ac1-151">B1203: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] recibe y entrega un mensaje con un encabezado de secuencia que contiene un elemento `LastMessage`, siempre que el URI de acción no sea http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage.</span><span class="sxs-lookup"><span data-stu-id="15ac1-151">B1203: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] receives and delivers a message with a Sequence header that contains a `LastMessage` element as long as the action URI is not http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage.</span></span>  
  
 <span data-ttu-id="15ac1-152">Ejemplo de encabezado de secuencia.</span><span class="sxs-lookup"><span data-stu-id="15ac1-152">An example of a Sequence Header.</span></span>  
  
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
  
### <a name="ackrequested-header"></a><span data-ttu-id="15ac1-153">Encabezado AckRequested</span><span class="sxs-lookup"><span data-stu-id="15ac1-153">AckRequested Header</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="15ac1-154"> usa el encabezado `AckRequested` como mecanismo de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="15ac1-154"> uses `AckRequested` Header as a keep-alive mechanism.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="15ac1-155"> no genera el elemento `MessageNumber` opcional.</span><span class="sxs-lookup"><span data-stu-id="15ac1-155"> does not generate the optional `MessageNumber` element.</span></span> <span data-ttu-id="15ac1-156">Al recibir un mensaje con un encabezado `AckRequested` que contiene el elemento `MessageNumber`, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] pasa por alto el valor del elemento `MessageNumber`, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="15ac1-156">Upon receiving a message with an `AckRequested` header that contains the `MessageNumber` element, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ignores the `MessageNumber` element’s value, as shown in the following example.</span></span>  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>  
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
  </wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement-header"></a><span data-ttu-id="15ac1-157">Encabezado SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="15ac1-157">SequenceAcknowledgement Header</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="15ac1-158"> usa un mecanismo de superposición para las confirmaciones de secuencias proporcionadas en WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="15ac1-158"> uses piggy-back mechanism for sequence acknowledgements provided in WS-Reliable Messaging.</span></span>  
  
-   <span data-ttu-id="15ac1-159">R1401: cuando dos secuencias inversas se establecen utilizando el mecanismo `Offer`, el encabezado `SequenceAcknowledgement` puede estar incluido en cualquier mensaje de aplicación transmitido al destinatario previsto.</span><span class="sxs-lookup"><span data-stu-id="15ac1-159">R1401: When two converse sequences are established using the `Offer` mechanism, the `SequenceAcknowledgement` header may be included in any application message transmitted to the intended recipient.</span></span>  
  
-   <span data-ttu-id="15ac1-160">B1402: cuando [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] debe generar una confirmación antes de recibir ningún mensaje de secuencia (por ejemplo, para satisfacer un mensaje `AckRequested`), [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera un encabezado `SequenceAcknowledgement` que contiene el intervalo 0-0, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="15ac1-160">B1402: When [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] must generate an acknowledgement prior to receiving any sequence messages (for example, to satisfy an `AckRequested` message), [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates a `SequenceAcknowledgement` header that contains the range 0-0, as shown in the following example.</span></span>  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>  
        urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
      </wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="0" Lower="0"/>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   <span data-ttu-id="15ac1-161">B1403: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no genera encabezados `SequenceAcknowledgement` que contengan un elemento `Nack`, pero admite elementos `Nack`.</span><span class="sxs-lookup"><span data-stu-id="15ac1-161">B1403: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not generate `SequenceAcknowledgement` headers that contain a `Nack` element but supports `Nack` elements.</span></span>  
  
### <a name="ws-reliablemessaging-faults"></a><span data-ttu-id="15ac1-162">Errores de WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="15ac1-162">WS-ReliableMessaging Faults</span></span>  
 <span data-ttu-id="15ac1-163">A continuación, se muestra una lista de las restricciones que se aplican a la implementación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] de errores de WS-Reliable Messaging:</span><span class="sxs-lookup"><span data-stu-id="15ac1-163">The following is a list of constraints that apply to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementation of WS-Reliable Messaging faults:</span></span>  
  
-   <span data-ttu-id="15ac1-164">B1501: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no genera errores `MessageNumberRollover`.</span><span class="sxs-lookup"><span data-stu-id="15ac1-164">B1501: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not generate `MessageNumberRollover` faults.</span></span>  
  
-   <span data-ttu-id="15ac1-165">B1502:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] punto de conexión puede generar `CreateSequenceRefused` produce un error como se describe en la especificación.</span><span class="sxs-lookup"><span data-stu-id="15ac1-165">B1502:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint may generate `CreateSequenceRefused` faults as described in the specification.</span></span>  
  
-   <span data-ttu-id="15ac1-166">B1503:when el extremo de servicio alcanza su límite de conexión y no se puede procesar nuevas conexiones, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera más `CreateSequenceRefused` subcódigo, de error `netrm:ConnectionLimitReached`, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="15ac1-166">B1503:When the service endpoint reaches its connection limit and cannot process new connections, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates an additional `CreateSequenceRefused` fault subcode, `netrm:ConnectionLimitReached`, as shown in the following example.</span></span>  
  
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
  
### <a name="ws-addressing-faults"></a><span data-ttu-id="15ac1-167">Errores WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="15ac1-167">WS-Addressing Faults</span></span>  
 <span data-ttu-id="15ac1-168">Dado que WS-Reliable Messaging utiliza WS-Addressing, la implementación de WS-Reliable Messaging de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] puede generar errores de WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="15ac1-168">Because WS-Reliable Messaging uses WS-Addressing, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WS-Reliable Messaging implementation may generate WS-Addressing faults.</span></span> <span data-ttu-id="15ac1-169">Esta sección cubre los errores de WS-Addressing que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera explícitamente en la capa de WS-Reliable Messaging:</span><span class="sxs-lookup"><span data-stu-id="15ac1-169">This section covers the WS-Addressing faults that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] explicitly generates at the WS-Reliable Messaging layer:</span></span>  
  
-   <span data-ttu-id="15ac1-170">B1601:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera el error necesario de encabezado de direccionamiento de mensajes cuando se cumple alguna de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="15ac1-170">B1601:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates the fault Message Addressing Header Required when one of the following is true:</span></span>  
  
    -   <span data-ttu-id="15ac1-171">Falta un encabezado `Sequence` y un encabezado `Action` en un mensaje.</span><span class="sxs-lookup"><span data-stu-id="15ac1-171">A message is missing a `Sequence` header and an `Action` header.</span></span>  
  
    -   <span data-ttu-id="15ac1-172">Falta un encabezado `CreateSequence` en un mensaje `MessageId`.</span><span class="sxs-lookup"><span data-stu-id="15ac1-172">A `CreateSequence` message is missing a `MessageId` header.</span></span>  
  
    -   <span data-ttu-id="15ac1-173">Falta un encabezado `CreateSequence` en un mensaje `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="15ac1-173">A `CreateSequence` message is missing a `ReplyTo` header.</span></span>  
  
-   <span data-ttu-id="15ac1-174">B1602:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera el error no admite la acción como respuesta a un mensaje que falta un `Sequence` encabezado y tiene un `Action` encabezado no reconocido en la especificación WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="15ac1-174">B1602:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates the fault Action Not Supported in reply to a message that is missing a `Sequence` header and has an `Action` header that is not a recognized in the WS-Reliable Messaging specification.</span></span>  
  
-   <span data-ttu-id="15ac1-175">B1603:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera el error de punto de conexión disponible para indicar que el punto de conexión no procesa la secuencia basándose en el examen de la `CreateSequence` encabezados de direccionamiento del mensaje.</span><span class="sxs-lookup"><span data-stu-id="15ac1-175">B1603:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates the fault Endpoint Unavailable to indicate that the endpoint does not process the sequence based upon examination of the `CreateSequence` message’s addressing headers.</span></span>  
  
## <a name="protocol-composition"></a><span data-ttu-id="15ac1-176">Composición de protocolos</span><span class="sxs-lookup"><span data-stu-id="15ac1-176">Protocol Composition</span></span>  
  
### <a name="composition-with-ws-addressing"></a><span data-ttu-id="15ac1-177">Composición con WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="15ac1-177">Composition with WS-Addressing</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="15ac1-178"> admite dos versiones de WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] y las recomendaciones de WS-Addressing 1.0 de W3C [WS-ADDR-CORE] y [WS-ADDR-SOAP].</span><span class="sxs-lookup"><span data-stu-id="15ac1-178"> supports two versions of WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] and W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] and [WS-ADDR-SOAP].</span></span>  
  
 <span data-ttu-id="15ac1-179">Aunque la especificación de WS-Reliable Messaging solo menciona a WS-Addressing 2004/08, no limita la versión de WS-Addressing que se ha de utilizar.</span><span class="sxs-lookup"><span data-stu-id="15ac1-179">While the WS-Reliable Messaging specification mentions only WS-Addressing 2004/08, it does not restrict the WS-Addressing version to be used.</span></span> <span data-ttu-id="15ac1-180">A continuación, se muestra una lista de restricciones que se aplican a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="15ac1-180">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="15ac1-181">R2101: ambos WS-Addressing 2004/08 y WS-Addressing 1.0 pueden utilizarse con WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="15ac1-181">R2101:Both WS-Addressing 2004/08 and WS-Addressing 1.0 can be used with WS-Reliable Messaging.</span></span>  
  
-   <span data-ttu-id="15ac1-182">Debe utilizarse R2102:A única versión de WS-Addressing a lo largo de una secuencia de WS-ReliableMessaging determinada o un par de secuencias inversas correlacionadas mediante el `wsrm:Offer` mecanismo.</span><span class="sxs-lookup"><span data-stu-id="15ac1-182">R2102:A single version of WS-Addressing must be used throughout a given WS-Reliable Messaging sequence or a pair of converse sequences correlated by using the `wsrm:Offer` mechanism.</span></span>  
  
### <a name="composition-with-soap"></a><span data-ttu-id="15ac1-183">Composición con SOAP</span><span class="sxs-lookup"><span data-stu-id="15ac1-183">Composition with SOAP</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="15ac1-184"> admite el uso de SOAP 1.1 y SOAP 1.2 con WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="15ac1-184"> supports use of both SOAP 1.1 and SOAP 1.2 with WS-Reliable Messaging.</span></span>  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a><span data-ttu-id="15ac1-185">Composición con WS-Security y WS-SecureConversation</span><span class="sxs-lookup"><span data-stu-id="15ac1-185">Composition with WS-Security and WS-SecureConversation</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="15ac1-186"> proporciona protección para secuencias de WS-Reliable Messaging mediante el transporte seguro (HTTPS), la composición con WS-Security y la composición con WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="15ac1-186"> provides protection for WS-Reliable Messaging sequences by using secure Transport (HTTPS), composition with WS-Security, and composition with WS-Secure Conversation.</span></span> <span data-ttu-id="15ac1-187">A continuación, se muestra una lista de restricciones que se aplican a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="15ac1-187">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="15ac1-188">R2301: para proteger la integridad de una secuencia de WS-ReliableMessaging además de la integridad y confidencialidad de los mensajes individuales, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requiere que se deben utilizar WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="15ac1-188">R2301:To protect the integrity of a WS-Reliable Messaging sequence in addition to the integrity and confidentiality of individual messages, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requires that WS-Secure Conversation must be used.</span></span>  
  
-   <span data-ttu-id="15ac1-189">R2302:AWS-Secure Conversation debe establecerse antes de establecer secuencias de WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="15ac1-189">R2302:AWS-Secure Conversation session must be established prior to establishing WS-Reliable Messaging sequence(s).</span></span>  
  
-   <span data-ttu-id="15ac1-190">R2303: si la duración de la secuencia de WS-Reliable Messaging supera la duración de la sesión de WS-Secure Conversation, el `SecurityContextToken` establecido mediante WS-Secure Conversation se debe renovar utilizando el enlace de renovación de WS-Secure Conversation correspondiente.</span><span class="sxs-lookup"><span data-stu-id="15ac1-190">R2303: If the WS-Reliable Messaging sequence lifetime exceeds the WS-Secure Conversation session’s lifetime, the `SecurityContextToken` established by using WS-Secure Conversation must be renewed by using the corresponding WS-Secure Conversation Renewal binding.</span></span>  
  
-   <span data-ttu-id="15ac1-191">B2304:ws-secuencia de mensajería de confianza o un par de secuencias inversas correlacionadas siempre están enlazados a una sola sesión de WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="15ac1-191">B2304:WS-Reliable Messaging sequence or a pair of correlated converse sequences are always bound to a single WS-SecureConversation session.</span></span>  
  
     <span data-ttu-id="15ac1-192">El origen de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera el elemento `wsse:SecurityTokenReference` en la sección de extensibilidad de elementos del mensaje `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="15ac1-192">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] source generates the `wsse:SecurityTokenReference` element in the element extensibility section of the `CreateSequence` message.</span></span>  
  
-   <span data-ttu-id="15ac1-193">R2305:when compuesta con WS-Secure Conversation, un `CreateSequence` mensaje debe contener el `wsse:SecurityTokenReference` elemento.</span><span class="sxs-lookup"><span data-stu-id="15ac1-193">R2305:When composed with WS-Secure Conversation, a `CreateSequence` message must contain the `wsse:SecurityTokenReference` element.</span></span>  
  
## <a name="ws-reliable-messaging-ws-policy-assertion"></a><span data-ttu-id="15ac1-194">Aserción de WS-Policy de WS-Reliable Messaging </span><span class="sxs-lookup"><span data-stu-id="15ac1-194">WS-Reliable Messaging WS-Policy Assertion</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="15ac1-195"> utiliza la aserción de WS-Policy de WS-Reliable Messaging `wsrm:RMAssertion` para describir funciones de extremos.</span><span class="sxs-lookup"><span data-stu-id="15ac1-195"> uses WS-Reliable Messaging WS-Policy Assertion `wsrm:RMAssertion` to describe endpoints capabilities.</span></span> <span data-ttu-id="15ac1-196">A continuación, se muestra una lista de restricciones que se aplican a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="15ac1-196">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="15ac1-197">B3001: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] adjunta la aserción `wsrm:RMAssertion` de WS-Policy Assertion a elementos `wsdl:binding`.</span><span class="sxs-lookup"><span data-stu-id="15ac1-197">B3001: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] attaches `wsrm:RMAssertion` WS-Policy Assertion to `wsdl:binding` elements.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="15ac1-198"> admite datos adjuntos para los elementos `wsdl:binding` y `wsdl:port`.</span><span class="sxs-lookup"><span data-stu-id="15ac1-198"> supports both attachments to `wsdl:binding` and `wsdl:port` elements.</span></span>  
  
-   <span data-ttu-id="15ac1-199">B3002: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite las siguientes propiedades opcionales de aserción de WS-Reliable Messaging y proporciona control sobre ellas en el [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] de `ReliableMessagingBindingElement`:</span><span class="sxs-lookup"><span data-stu-id="15ac1-199">B3002: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] supports the following optional properties of WS-Reliable Messaging assertion and provides control over them on the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]`ReliableMessagingBindingElement`:</span></span>  
  
    -   `wsrm:InactivityTimeout`  
  
    -   `wsrm:AcknowledgementInterval`  
  
     <span data-ttu-id="15ac1-200">A continuación se muestra un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="15ac1-200">The following is an example.</span></span>  
  
    ```xml  
    <wsrm:RMAssertion>  
      <wsrm:InactivityTimeout Milliseconds="600000" />  
      <wsrm:AcknowledgementInterval Milliseconds="200" />  
    </wsrm:RMAssertion>  
    ```  
  
## <a name="flow-control-ws-reliable-messaging-extension"></a><span data-ttu-id="15ac1-201">Extensión de WS-Reliable Messaging de control de flujo</span><span class="sxs-lookup"><span data-stu-id="15ac1-201">Flow Control WS-Reliable Messaging Extension</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="15ac1-202"> usa la extensibilidad de WS-Reliable Messaging para proporcionar un control opcional adicional más estricto sobre el flujo de mensajes de secuencias.</span><span class="sxs-lookup"><span data-stu-id="15ac1-202"> uses WS-Reliable Messaging extensibility to provide optional additional tighter control over sequence message flow.</span></span>  
  
 <span data-ttu-id="15ac1-203">Control de flujo se habilita estableciendo el `ReliableSessionBindingElement`del `FlowControlEnabled``bool` propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="15ac1-203">Flow control is enabled by setting the `ReliableSessionBindingElement`’s `FlowControlEnabled``bool` property to `true`.</span></span> <span data-ttu-id="15ac1-204">A continuación, se muestra una lista de restricciones que se aplican a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="15ac1-204">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="15ac1-205">B4001: cuando se habilitada el control de flujo de la mensajería de confianza, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera un elemento `netrm:BufferRemaining` en la extensibilidad de elementos del encabezado `SequenceAcknowledgement`.</span><span class="sxs-lookup"><span data-stu-id="15ac1-205">B4001: When Reliable Messaging Flow Control is enabled, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates a `netrm:BufferRemaining` element in the element extensibility of the `SequenceAcknowledgement` header.</span></span>  
  
-   <span data-ttu-id="15ac1-206">B4002: cuando está habilitado el control de flujo de la mensajería de confianza, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no requiere que haya un elemento `netrm:BufferRemaining` en el encabezado `SequenceAcknowledgement`, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="15ac1-206">B4002: When Reliable Messaging Flow Control is enabled, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not require a `netrm:BufferRemaining` element to be present in `SequenceAcknowledgement` header, as shown in the following example.</span></span>  
  
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
  
-   <span data-ttu-id="15ac1-207">B4003: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza `netrm:BufferRemaining` para indicar cuántos mensajes nuevos puede almacenar en búfer el destino de la mensajería de confianza.</span><span class="sxs-lookup"><span data-stu-id="15ac1-207">B4003: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses `netrm:BufferRemaining` to indicate how many new messages the Reliable Messaging Destination can buffer.</span></span>  
  
-   <span data-ttu-id="15ac1-208">B4004: el [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] el servicio de mensajería confiable limita el número de mensajes transmitidos cuando la aplicación de destino de la mensajería de confianza no puede recibir mensajes rápidamente.</span><span class="sxs-lookup"><span data-stu-id="15ac1-208">B4004:The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging Service throttles the number of messages transmitted when the Reliable Messaging destination application cannot receive messages quickly.</span></span> <span data-ttu-id="15ac1-209">El destino de la mensajería de confianza almacena en búfer los mensajes y el valor del elemento cae a 0.</span><span class="sxs-lookup"><span data-stu-id="15ac1-209">The Reliable Messaging destination buffers messages and the element’s value drops to 0.</span></span>  
  
-   <span data-ttu-id="15ac1-210">B4005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera valores enteros de `netrm:BufferRemaining` entre 0 y 4.096, ambos incluidos, y lee valores enteros entre 0 y el valor `xs:int` 214748364 de `maxInclusive`, ambos incluidos.</span><span class="sxs-lookup"><span data-stu-id="15ac1-210">B4005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates `netrm:BufferRemaining` integer values between 0 and 4096 inclusive, and reads integer values between 0 and `xs:int`’s `maxInclusive` value 214748364 inclusive.</span></span>  
  
## <a name="message-exchange-patterns"></a><span data-ttu-id="15ac1-211">Modelos de intercambio de mensajes</span><span class="sxs-lookup"><span data-stu-id="15ac1-211">Message Exchange Patterns</span></span>  
 <span data-ttu-id="15ac1-212">En esta sección se describe el comportamiento de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cuando se utiliza WS-Reliable Messaging para patrones de intercambio de mensajes diferentes.</span><span class="sxs-lookup"><span data-stu-id="15ac1-212">This section describes [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]'s behavior when WS-Reliable Messaging is used for different Message Exchange Patterns.</span></span> <span data-ttu-id="15ac1-213">Para cada patrón de intercambio de mensajes, se consideran los dos escenarios de implementación siguientes:</span><span class="sxs-lookup"><span data-stu-id="15ac1-213">For each Message Exchange Pattern the following two deployments scenarios are considered:</span></span>  
  
-   <span data-ttu-id="15ac1-214">Iniciador no direccionable: el iniciador está tras un firewall; el respondedor solo puede entregar mensajes al iniciador mediante respuestas HTTP.</span><span class="sxs-lookup"><span data-stu-id="15ac1-214">Non-Addressable Initiator: Initiator is behind firewall; Responder can deliver messages to Initiator only on HTTP responses.</span></span>  
  
-   <span data-ttu-id="15ac1-215">Iniciador direccionable: el iniciador y el respondedor pueden enviar solicitudes HTTP; en otras palabras, se pueden establecer dos conexiones HTTP inversas.</span><span class="sxs-lookup"><span data-stu-id="15ac1-215">Addressable Initiator: Initiator and Responder both can be sent HTTP requests; in other words, two converse HTTP connections can be established.</span></span>  
  
### <a name="one-way-non-addressable-initiator"></a><span data-ttu-id="15ac1-216">Iniciador unidireccional no direccionable</span><span class="sxs-lookup"><span data-stu-id="15ac1-216">One-way, Non-addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="15ac1-217">Enlaces</span><span class="sxs-lookup"><span data-stu-id="15ac1-217">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="15ac1-218"> proporciona un patrón de intercambio de mensajes unidireccional usando una secuencia sobre un canal HTTP.</span><span class="sxs-lookup"><span data-stu-id="15ac1-218"> provides a one-way message exchange pattern using one sequence over one HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="15ac1-219"> usa las solicitudes HTTP para transmitir todos los mensajes del RMS al RMD y la respuesta HTTP para transmitir todos los mensajes del RMD al RMS.</span><span class="sxs-lookup"><span data-stu-id="15ac1-219"> uses the HTTP requests to transmit all messages from the RMS to the RMD and the HTTP response to transmit all messages from the RMD to the RMS.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="15ac1-220">Intercambio de CreateSequence</span><span class="sxs-lookup"><span data-stu-id="15ac1-220">CreateSequence Exchange</span></span>  
 <span data-ttu-id="15ac1-221">El iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera un mensaje `CreateSequence` sin oferta.</span><span class="sxs-lookup"><span data-stu-id="15ac1-221">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates a `CreateSequence` message with no offer.</span></span> <span data-ttu-id="15ac1-222">El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] asegura que `CreateSequence` no tenga ninguna oferta antes de crear una secuencia.</span><span class="sxs-lookup"><span data-stu-id="15ac1-222">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures the `CreateSequence` has no offer before creating a sequence.</span></span> <span data-ttu-id="15ac1-223">El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] responde a la solicitud de `CreateSequence` con un mensaje `CreateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="15ac1-223">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder replies to the `CreateSequence` request with a `CreateSequenceResponse` message.</span></span>  
  
#### <a name="sequenceacknowledgement"></a><span data-ttu-id="15ac1-224">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="15ac1-224">SequenceAcknowledgement</span></span>  
 <span data-ttu-id="15ac1-225">El iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] procesa las confirmaciones en la respuesta de todos los mensajes, salvo en los mensajes de error y el mensaje `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="15ac1-225">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator processes acknowledgements on the reply of all messages except the `CreateSequence` message and fault messages.</span></span> <span data-ttu-id="15ac1-226">El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] siempre genera una confirmación independiente en respuesta a la secuencia y los mensajes `AckRequested`.</span><span class="sxs-lookup"><span data-stu-id="15ac1-226">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder always generates a stand-alone acknowledgement in the response to both sequence and `AckRequested` messages.</span></span>  
  
#### <a name="terminatesequence-message"></a><span data-ttu-id="15ac1-227">Mensaje TerminateSequence</span><span class="sxs-lookup"><span data-stu-id="15ac1-227">TerminateSequence message</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="15ac1-228"> trata a `TerminateSequence` como una operación unidireccional, lo que significa que la respuesta HTTP tiene un cuerpo vacío y un código de estado HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="15ac1-228"> treats `TerminateSequence` as a one-way operation, meaning the HTTP response has an empty body and HTTP 202 status code.</span></span>  
  
### <a name="one-way-addressable-initiator"></a><span data-ttu-id="15ac1-229">Iniciador unidireccional y direccionable</span><span class="sxs-lookup"><span data-stu-id="15ac1-229">One Way, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="15ac1-230">Enlaces</span><span class="sxs-lookup"><span data-stu-id="15ac1-230">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="15ac1-231"> proporciona un patrón de intercambio de mensajes unidireccional usando una secuencia sobre un canal HTTP entrante y uno saliente.</span><span class="sxs-lookup"><span data-stu-id="15ac1-231"> provides a one-way message exchange pattern using one sequence over an inbound and an outbound Http channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="15ac1-232"> usa las solicitudes HTTP para transmitir todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="15ac1-232"> uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="15ac1-233">Todas las respuestas HTTP tienen un cuerpo vacío y código de estado HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="15ac1-233">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="15ac1-234">Intercambio de CreateSequence</span><span class="sxs-lookup"><span data-stu-id="15ac1-234">CreateSequence Exchange</span></span>  
 <span data-ttu-id="15ac1-235">El iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera un mensaje `CreateSequence` sin oferta.</span><span class="sxs-lookup"><span data-stu-id="15ac1-235">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates a `CreateSequence` message with no offer.</span></span> <span data-ttu-id="15ac1-236">El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] asegura que `CreateSequence` no tenga ninguna oferta antes de crear una secuencia.</span><span class="sxs-lookup"><span data-stu-id="15ac1-236">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has no offer before creating a sequence.</span></span> <span data-ttu-id="15ac1-237">El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transmite el mensaje `CreateSequenceResponse` en una solicitud HTTP direccionada con la referencia de extremo `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="15ac1-237">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder transmits the `CreateSequenceResponse` message on an HTTP request addressed with the `ReplyTo` endpoint reference.</span></span>  
  
### <a name="duplex-addressable-initiator"></a><span data-ttu-id="15ac1-238">Iniciador dúplex y direccionable</span><span class="sxs-lookup"><span data-stu-id="15ac1-238">Duplex, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="15ac1-239">Enlaces</span><span class="sxs-lookup"><span data-stu-id="15ac1-239">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="15ac1-240"> proporciona un patrón de intercambio de mensajes totalmente asincrónico y bidireccional usando dos secuencias sobre un canal HTTP entrante y uno saliente.</span><span class="sxs-lookup"><span data-stu-id="15ac1-240"> provides a fully asynchronous two-way message exchange pattern using two sequences over an inbound and an outbound HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="15ac1-241"> usa las solicitudes HTTP para transmitir todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="15ac1-241"> uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="15ac1-242">Todas las respuestas HTTP tienen un cuerpo vacío y código de estado HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="15ac1-242">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="15ac1-243">Intercambio de CreateSequence</span><span class="sxs-lookup"><span data-stu-id="15ac1-243">CreateSequence Exchange</span></span>  
 <span data-ttu-id="15ac1-244">El iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera un mensaje `CreateSequence` con una oferta.</span><span class="sxs-lookup"><span data-stu-id="15ac1-244">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="15ac1-245">El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se asegura de que `CreateSequence` tenga una oferta antes de crear una secuencia.</span><span class="sxs-lookup"><span data-stu-id="15ac1-245">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="15ac1-246"> envía `CreateSequenceResponse` en la solicitud HTTP dirigida a la referencia de extremo `CreateSequence` de los `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="15ac1-246"> sends the `CreateSequenceResponse` on the HTTP request addressed to the `CreateSequence`’s `ReplyTo` endpoint reference.</span></span>  
  
#### <a name="sequence-lifetime"></a><span data-ttu-id="15ac1-247">Duración de la secuencia</span><span class="sxs-lookup"><span data-stu-id="15ac1-247">Sequence Lifetime</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="15ac1-248"> trata las dos secuencias como una sesión totalmente dúplex.</span><span class="sxs-lookup"><span data-stu-id="15ac1-248"> treats the two sequences as one fully duplex session.</span></span>  
  
 <span data-ttu-id="15ac1-249">Tras generar un error que provoca un error en una secuencia, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] espera que el extremo remoto genere un error en ambas secuencias.</span><span class="sxs-lookup"><span data-stu-id="15ac1-249">Upon generating a fault that faults one sequence, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] expects the remote endpoint to fault both sequences.</span></span> <span data-ttu-id="15ac1-250">Tras leer un error que provoca un error en una secuencia, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera un error en ambas secuencias.</span><span class="sxs-lookup"><span data-stu-id="15ac1-250">Upon reading a fault that faults one sequence, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] faults both sequences.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="15ac1-251"> puede cerrar su secuencia saliente y continuar procesando mensajes en su secuencia entrante.</span><span class="sxs-lookup"><span data-stu-id="15ac1-251"> can close its outbound sequence and continue to process messages on its inbound sequence.</span></span> <span data-ttu-id="15ac1-252">De manera inversa, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] puede procesar el cierre de la secuencia entrante y continuar enviando mensajes en su secuencia saliente.</span><span class="sxs-lookup"><span data-stu-id="15ac1-252">Conversely, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] can process the close of the inbound sequence and continue to send messages on its outbound sequence.</span></span>  
  
### <a name="request-reply-non-addressable-initiator"></a><span data-ttu-id="15ac1-253">Iniciador no direccionable de solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="15ac1-253">Request-Reply, Non-Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="15ac1-254">Enlaces</span><span class="sxs-lookup"><span data-stu-id="15ac1-254">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="15ac1-255"> proporciona un patrón de intercambio unidireccional de mensajes de solicitud-respuesta usando dos secuencias sobre un canal HTTP.</span><span class="sxs-lookup"><span data-stu-id="15ac1-255"> provides a one-way and request-reply message exchange pattern using two sequences over one HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="15ac1-256"> usa las solicitudes HTTP para transmitir los mensajes de la secuencia de solicitud y usa las respuestas HTTP para transmitir los mensajes de la secuencia de respuesta.</span><span class="sxs-lookup"><span data-stu-id="15ac1-256"> uses the HTTP requests to transmit the request sequence’s messages and uses the HTTP responses to transmit the reply sequence’s messages.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="15ac1-257">Intercambio de CreateSequence</span><span class="sxs-lookup"><span data-stu-id="15ac1-257">CreateSequence Exchange</span></span>  
 <span data-ttu-id="15ac1-258">El iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera un mensaje `CreateSequence` con una oferta.</span><span class="sxs-lookup"><span data-stu-id="15ac1-258">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="15ac1-259">El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se asegura de que `CreateSequence` tenga una oferta antes de crear una secuencia.</span><span class="sxs-lookup"><span data-stu-id="15ac1-259">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> <span data-ttu-id="15ac1-260">El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] responde a la solicitud de `CreateSequence` con un mensaje `CreateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="15ac1-260">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder replies to the `CreateSequence` request with a `CreateSequenceResponse` message.</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="15ac1-261">Mensaje unidireccional</span><span class="sxs-lookup"><span data-stu-id="15ac1-261">One-way Message</span></span>  
 <span data-ttu-id="15ac1-262">Para completar correctamente un protocolo de intercambio de mensajes unidireccional, el iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transmite un mensaje de secuencia de solicitud en la solicitud HTTP y recibe un mensaje `SequenceAcknowledgement` independiente en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="15ac1-262">To complete a one-way message exchange protocol successfully, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a request sequence message on the HTTP request and receives a standalone `SequenceAcknowledgement` message on the HTTP response.</span></span> <span data-ttu-id="15ac1-263">La `SequenceAcknowledgement` debe confirmar el mensaje transmitido.</span><span class="sxs-lookup"><span data-stu-id="15ac1-263">The `SequenceAcknowledgement` must acknowledge the message transmitted.</span></span>  
  
 <span data-ttu-id="15ac1-264">El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] puede responder a la solicitud con una confirmación, un error o una respuesta con un cuerpo vacío y un código de estado HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="15ac1-264">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder can reply to the request with an acknowledgement, a fault, or a response with an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="two-way-messages"></a><span data-ttu-id="15ac1-265">Mensajes bidireccionales</span><span class="sxs-lookup"><span data-stu-id="15ac1-265">Two Way Messages</span></span>  
 <span data-ttu-id="15ac1-266">Para completar correctamente un protocolo de intercambio de mensajes bidireccional, el iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transmite un mensaje de secuencia de solicitud en la solicitud HTTP y recibe un mensaje de secuencia de respuesta en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="15ac1-266">To complete a two way message exchange protocol successfully, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a request sequence message on the HTTP request and receives a reply sequence message on the HTTP response.</span></span> <span data-ttu-id="15ac1-267">La respuesta debe llevar una `SequenceAcknowledgement` que confirme que se ha transmitido el mensaje de secuencia de solicitud.</span><span class="sxs-lookup"><span data-stu-id="15ac1-267">The response must carry a `SequenceAcknowledgement` acknowledging the request sequence message transmitted.</span></span>  
  
 <span data-ttu-id="15ac1-268">El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] puede responder a la solicitud con una respuesta de la aplicación, un error o una respuesta con un cuerpo vacío y un código de estado HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="15ac1-268">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder can reply to the request with an application reply, a fault or a response with an empty body and HTTP 202 status code.</span></span>  
  
 <span data-ttu-id="15ac1-269">Debido a la presencia de mensajes unidireccionales y al control de tiempo de las respuestas de la aplicación, el número de secuencia del mensaje de secuencia de solicitud y el número de secuencia del mensaje de respuesta no tienen ninguna correlación.</span><span class="sxs-lookup"><span data-stu-id="15ac1-269">Because of the presence of one-way messages and the timing of application replies, the request sequence message’s sequence number and the response message’s sequence number have no correlation.</span></span>  
  
#### <a name="retrying-replies"></a><span data-ttu-id="15ac1-270">Reintento de respuestas</span><span class="sxs-lookup"><span data-stu-id="15ac1-270">Retrying Replies</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="15ac1-271"> confía en la correlación de solicitud-respuesta HTTP para la correlación del protocolo de intercambio de mensajes bidireccional.</span><span class="sxs-lookup"><span data-stu-id="15ac1-271"> relies on HTTP request-reply correlation for two-way message exchange protocol correlation.</span></span> <span data-ttu-id="15ac1-272">Debido a esto, el iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no deja de reintentar un mensaje de secuencia de solicitud cuando éste se confirma, sino cuando la respuesta HTTP lleva una confirmación, un mensaje de usuario o un error.</span><span class="sxs-lookup"><span data-stu-id="15ac1-272">Because of this, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator does not stop retrying a request sequence message when the request sequence message is acknowledged but rather when the HTTP response carries an acknowledgement, user message, or fault.</span></span> <span data-ttu-id="15ac1-273">El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] reintenta las respuestas en la bifurcación de la solicitud HTTP de la solicitud con la que se correlaciona la respuesta.</span><span class="sxs-lookup"><span data-stu-id="15ac1-273">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder retries replies on the HTTP request leg of the request to which the reply is correlated.</span></span>  
  
#### <a name="lastmessage-exchange"></a><span data-ttu-id="15ac1-274">Intercambio de LastMessage</span><span class="sxs-lookup"><span data-stu-id="15ac1-274">LastMessage Exchange</span></span>  
 <span data-ttu-id="15ac1-275">El iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera y transmite un último mensaje con cuerpo vacío en la bifurcación de la solicitud HTTP.</span><span class="sxs-lookup"><span data-stu-id="15ac1-275">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates and transmits an empty bodied last message on the HTTP request leg.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="15ac1-276"> necesita una respuesta pero omite el mensaje de respuesta real.</span><span class="sxs-lookup"><span data-stu-id="15ac1-276"> requires a response but ignores the actual response message.</span></span> <span data-ttu-id="15ac1-277">El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] responde al último mensaje de cuerpo vacío de la secuencia de solicitud con el último mensaje de cuerpo vacío de la secuencia de respuesta.</span><span class="sxs-lookup"><span data-stu-id="15ac1-277">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder replies to the request sequence’s empty-bodied last message with the reply sequence’s empty-bodied last message.</span></span>  
  
 <span data-ttu-id="15ac1-278">Si el respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] recibe un último mensaje en el que el URI de acción no es http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] responde con un último mensaje.</span><span class="sxs-lookup"><span data-stu-id="15ac1-278">If the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder receives a last message in which the action URI is not http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] replies with a last message.</span></span> <span data-ttu-id="15ac1-279">En el caso de un protocolo de intercambio de mensajes bidireccional, el último mensaje lleva el mensaje de la aplicación; en el caso de un protocolo de intercambio de mensajes unidireccional, el último mensaje está vacío.</span><span class="sxs-lookup"><span data-stu-id="15ac1-279">In the case of a two-way message exchange protocol, the last message carries the application message; in the case of a one-way message exchange protocol, the last message is empty.</span></span>  
  
 <span data-ttu-id="15ac1-280">El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no requiere una confirmación para el último mensaje de cuerpo vacío de la secuencia de respuesta.</span><span class="sxs-lookup"><span data-stu-id="15ac1-280">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder does not require an acknowledgement for the reply sequence’s empty-bodied last message.</span></span>  
  
#### <a name="terminatesequence-exchange"></a><span data-ttu-id="15ac1-281">Intercambio de TerminateSequence</span><span class="sxs-lookup"><span data-stu-id="15ac1-281">TerminateSequence Exchange</span></span>  
 <span data-ttu-id="15ac1-282">Cuando todas las solicitudes han recibido una respuesta válida, el iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera y transmite el mensaje `TerminateSequence` de la secuencia de solicitud en la bifurcación de la solicitud HTTP.</span><span class="sxs-lookup"><span data-stu-id="15ac1-282">When all requests have received a valid reply, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates and transmits the request sequence’s `TerminateSequence` message on the HTTP request leg.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="15ac1-283"> necesita una respuesta pero omite el mensaje de respuesta real.</span><span class="sxs-lookup"><span data-stu-id="15ac1-283"> requires a response but ignores the actual response message.</span></span> <span data-ttu-id="15ac1-284">El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] responde al mensaje `TerminateSequence` de la secuencia de solicitud con el mensaje `TerminateSequence` de la secuencia de respuesta.</span><span class="sxs-lookup"><span data-stu-id="15ac1-284">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder replies to the request sequence’s `TerminateSequence` message with the reply sequence’s `TerminateSequence` message.</span></span>  
  
 <span data-ttu-id="15ac1-285">En una secuencia de apagado normal, ambos mensajes `TerminateSequence` llevan un `SequenceAcknowledgement` de intervalo completo.</span><span class="sxs-lookup"><span data-stu-id="15ac1-285">In a normal shutdown sequence, both `TerminateSequence` messages carry a full range `SequenceAcknowledgement`.</span></span>  
  
### <a name="requestreply-addressable-initiator"></a><span data-ttu-id="15ac1-286">Iniciador direccionable de solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="15ac1-286">Request/Reply, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="15ac1-287">Enlaces</span><span class="sxs-lookup"><span data-stu-id="15ac1-287">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="15ac1-288"> proporciona un patrón de intercambio de mensajes de solicitud-respuesta usando dos secuencias sobre un canal HTTP entrante y uno saliente.</span><span class="sxs-lookup"><span data-stu-id="15ac1-288"> provides a request-reply message exchange pattern using two sequences over an inbound and an outbound HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="15ac1-289"> usa las solicitudes HTTP para transmitir todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="15ac1-289"> uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="15ac1-290">Todas las respuestas HTTP tienen un cuerpo vacío y código de estado HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="15ac1-290">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="15ac1-291">Intercambio de CreateSequence</span><span class="sxs-lookup"><span data-stu-id="15ac1-291">CreateSequence Exchange</span></span>  
 <span data-ttu-id="15ac1-292">El iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera un mensaje `CreateSequence` con una oferta.</span><span class="sxs-lookup"><span data-stu-id="15ac1-292">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="15ac1-293">El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se asegura de que `CreateSequence` tenga una oferta antes de crear una secuencia.</span><span class="sxs-lookup"><span data-stu-id="15ac1-293">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="15ac1-294"> envía `CreateSequenceResponse` en la solicitud HTTP dirigida a la referencia de extremo `CreateSequence` de los `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="15ac1-294"> sends the `CreateSequenceResponse` on the HTTP request addressed to the `CreateSequence`’s `ReplyTo` endpoint reference.</span></span>  
  
#### <a name="requestreply-correlation"></a><span data-ttu-id="15ac1-295">Correlación entre solicitud y respuesta</span><span class="sxs-lookup"><span data-stu-id="15ac1-295">Request/Reply Correlation</span></span>  
 <span data-ttu-id="15ac1-296">El iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se asegura de que todos los mensajes de solicitud de la aplicación lleven un`MessageId` y una referencia de extremo `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="15ac1-296">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator ensures all application request messages bear a `MessageId` and a `ReplyTo` endpoint reference.</span></span> <span data-ttu-id="15ac1-297">El iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aplica la referencia de extremo `CreateSequence` del mensaje `ReplyTo` en cada mensaje de solicitud de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="15ac1-297">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator applies the `CreateSequence` message’s `ReplyTo` endpoint reference on each application request message.</span></span> <span data-ttu-id="15ac1-298">El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requiere que los mensajes de solicitud entrantes lleven un `MessageId` y un `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="15ac1-298">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder requires that incoming request messages bear a `MessageId` and a `ReplyTo`.</span></span> <span data-ttu-id="15ac1-299">El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se asegura de que el URI de la referencia del extremo de `CreateSequence` y de todos los mensajes de solicitud de la aplicación sean idénticos.</span><span class="sxs-lookup"><span data-stu-id="15ac1-299">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the endpoint reference’s URI of both the `CreateSequence` and all application request messages are identical.</span></span>
