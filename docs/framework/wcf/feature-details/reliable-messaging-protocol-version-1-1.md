---
title: "Protocolo de mensajería de confianza versión 1,1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0da47b82-f8eb-42da-8bfe-e56ce7ba6f59
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 98fe8ac04b7ac811802466cf63c58ea4cebd791e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="reliable-messaging-protocol-version-11"></a><span data-ttu-id="a86ad-102">Protocolo de mensajería de confianza versión 1,1</span><span class="sxs-lookup"><span data-stu-id="a86ad-102">Reliable Messaging Protocol version 1.1</span></span>
<span data-ttu-id="a86ad-103">Este tema cubre los detalles de implementación de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] para el protocolo de febrero de 2007 WS-ReliableMessaging (versión 1.1) necesario para la interoperación mediante el transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="a86ad-103">This topic covers [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] implementation details for the WS-ReliableMessaging February 2007 (version 1.1) protocol necessary for interoperation using the HTTP transport.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a86ad-104"> sigue la especificación WS-ReliableMessaging con las restricciones y clarificaciones explicadas en este tema.</span><span class="sxs-lookup"><span data-stu-id="a86ad-104"> follows the WS-ReliableMessaging specification with the constraints and clarifications explained in this topic.</span></span> <span data-ttu-id="a86ad-105">Tenga en cuenta que la versión 1.1 del protocolo WS-ReliableMessaging se implementa a partir de la [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a86ad-105">Note that the WS-ReliableMessaging version 1.1 protocol is implemented starting with the [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)].</span></span>  
  
 <span data-ttu-id="a86ad-106">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementa el protocolo WS-ReliableMessaging de febrero de 2007 en <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="a86ad-106">The WS-ReliableMessaging February 2007 protocol is implemented in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] by the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span></span>  
  
 <span data-ttu-id="a86ad-107">Para su comodidad, el tema utiliza las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="a86ad-107">For convenience, the topic uses the following roles:</span></span>  
  
-   <span data-ttu-id="a86ad-108">Iniciador: el cliente que inicia la creación de la secuencia de mensajes WS-Reliable.</span><span class="sxs-lookup"><span data-stu-id="a86ad-108">Initiator: The client that initiates WS-Reliable Message sequence creation.</span></span>  
  
-   <span data-ttu-id="a86ad-109">Respondedor: el servicio que recibe las solicitudes del iniciador.</span><span class="sxs-lookup"><span data-stu-id="a86ad-109">Responder: The service that receives the initiator's requests.</span></span>  
  
 <span data-ttu-id="a86ad-110">En este documento, se utilizan los prefijos y espacios de nombres de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="a86ad-110">This document uses the prefixes and namespaces in the following table.</span></span>  
  
|<span data-ttu-id="a86ad-111">Prefijo</span><span class="sxs-lookup"><span data-stu-id="a86ad-111">Prefix</span></span>|<span data-ttu-id="a86ad-112">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="a86ad-112">Namespace</span></span>|  
|-|-|  
|<span data-ttu-id="a86ad-113">wsrm</span><span class="sxs-lookup"><span data-stu-id="a86ad-113">wsrm</span></span>|<span data-ttu-id="a86ad-114">http://docs.oasis-open.org/ws-rx/wsrm/200702</span><span class="sxs-lookup"><span data-stu-id="a86ad-114">http://docs.oasis-open.org/ws-rx/wsrm/200702</span></span>|  
|<span data-ttu-id="a86ad-115">netrm</span><span class="sxs-lookup"><span data-stu-id="a86ad-115">netrm</span></span>|<span data-ttu-id="a86ad-116">http://schemas.microsoft.com/ws/2006/05/rm</span><span class="sxs-lookup"><span data-stu-id="a86ad-116">http://schemas.microsoft.com/ws/2006/05/rm</span></span>|  
|<span data-ttu-id="a86ad-117">s</span><span class="sxs-lookup"><span data-stu-id="a86ad-117">s</span></span>|<span data-ttu-id="a86ad-118">http://www.w3.org/2003/05/soap-envelope</span><span class="sxs-lookup"><span data-stu-id="a86ad-118">http://www.w3.org/2003/05/soap-envelope</span></span>|  
|<span data-ttu-id="a86ad-119">wsa</span><span class="sxs-lookup"><span data-stu-id="a86ad-119">wsa</span></span>|<span data-ttu-id="a86ad-120">http://schemas.xmlsoap.org/ws/2005/08/addressing</span><span class="sxs-lookup"><span data-stu-id="a86ad-120">http://schemas.xmlsoap.org/ws/2005/08/addressing</span></span>|  
|<span data-ttu-id="a86ad-121">wsse</span><span class="sxs-lookup"><span data-stu-id="a86ad-121">wsse</span></span>|<span data-ttu-id="a86ad-122">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd</span><span class="sxs-lookup"><span data-stu-id="a86ad-122">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd</span></span>|  
|<span data-ttu-id="a86ad-123">wsrmp</span><span class="sxs-lookup"><span data-stu-id="a86ad-123">wsrmp</span></span>|<span data-ttu-id="a86ad-124">http://docs.oasis-open.org/ws-rx/wsrmp/200702</span><span class="sxs-lookup"><span data-stu-id="a86ad-124">http://docs.oasis-open.org/ws-rx/wsrmp/200702</span></span>|  
|<span data-ttu-id="a86ad-125">netrmp</span><span class="sxs-lookup"><span data-stu-id="a86ad-125">netrmp</span></span>|<span data-ttu-id="a86ad-126">http://schemas.microsoft.com/ws-rx/wsrmp/200702</span><span class="sxs-lookup"><span data-stu-id="a86ad-126">http://schemas.microsoft.com/ws-rx/wsrmp/200702</span></span>|  
|<span data-ttu-id="a86ad-127">wsp</span><span class="sxs-lookup"><span data-stu-id="a86ad-127">wsp</span></span>|<span data-ttu-id="a86ad-128">(Directiva WS-Policy 1.2 o WS-Policy 1.5)</span><span class="sxs-lookup"><span data-stu-id="a86ad-128">(Either WS-Policy 1.2 or WS-Policy 1.5)</span></span>|  
  
## <a name="messaging"></a><span data-ttu-id="a86ad-129">Mensajería</span><span class="sxs-lookup"><span data-stu-id="a86ad-129">Messaging</span></span>  
  
### <a name="sequence-creation"></a><span data-ttu-id="a86ad-130">Creación de secuencias</span><span class="sxs-lookup"><span data-stu-id="a86ad-130">Sequence Creation</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a86ad-131"> implementa mensajes `CreateSequence` y `CreateSequenceResponse` para establecer una secuencia de mensajería de confianza.</span><span class="sxs-lookup"><span data-stu-id="a86ad-131"> implements `CreateSequence` and `CreateSequenceResponse` messages to establish a reliable messaging sequence.</span></span> <span data-ttu-id="a86ad-132">Las siguientes restricciones son aplicables:</span><span class="sxs-lookup"><span data-stu-id="a86ad-132">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="a86ad-133">B1101: el iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza la misma referencia de extremo que `CreateSequence`, `ReplyTo` y `AcksTo` del mensaje `Offer/Endpoint`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-133">B1101: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator uses the same endpoint reference as the `CreateSequence` message’s `ReplyTo`, `AcksTo` and `Offer/Endpoint`.</span></span>  
  
-   <span data-ttu-id="a86ad-134">R1102: las referencias de extremo `AcksTo`, `ReplyTo` y `Offer/Endpoint` en el mensaje `CreateSequence` deben tener valores de dirección con representaciones de cadena idénticas, de tal modo que coincidan por octetos.</span><span class="sxs-lookup"><span data-stu-id="a86ad-134">R1102: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message must have address values with identical string representations such that they match the octet-wise.</span></span>  
  
    -   <span data-ttu-id="a86ad-135">El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] comprueba que la parte del URI de las referencias de extremo `AcksTo`, `ReplyTo` y `Endpoint` sean idénticas antes de crear una secuencia.</span><span class="sxs-lookup"><span data-stu-id="a86ad-135">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder verifies that the URI portion of the `AcksTo`, `ReplyTo` and `Endpoint` endpoint references are identical before creating a sequence.</span></span>  
  
-   <span data-ttu-id="a86ad-136">R1103: las referencias de extremo `AcksTo`, `ReplyTo` y `Offer/Endpoint` en el mensaje `CreateSequence` deberían tener el mismo conjunto de parámetros de referencia.</span><span class="sxs-lookup"><span data-stu-id="a86ad-136">R1103: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message should have the same set of reference parameters.</span></span>  
  
    -   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a86ad-137"> no exige, pero supone que los parámetros de las referencias de extremo `AcksTo`, `ReplyTo` y `Offer/Endpoint` en `CreateSequence` son idénticas y utiliza los parámetros de referencia de la referencia de extremo `ReplyTo` para las confirmaciones y los mensajes de secuencia inversa.</span><span class="sxs-lookup"><span data-stu-id="a86ad-137"> does not enforce, but assumes that reference parameters of the `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references on `CreateSequence` are identical and uses reference parameters from the `ReplyTo` endpoint reference for acknowledgements and converse sequence messages.</span></span>  
  
-   <span data-ttu-id="a86ad-138">B1104: el iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no genera el elemento opcional `Expires` o `Offer/Expires` en el mensaje `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-138">B1104: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator does not generate the optional `Expires` or `Offer/Expires` element in the `CreateSequence` message.</span></span>  
  
-   <span data-ttu-id="a86ad-139">B1105: al tener acceso al mensaje `CreateSequence`, el respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza el valor `Expires` del elemento `CreateSequence` como el valor `Expires` del elemento `CreateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-139">B1105: When accessing the `CreateSequence` message, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder uses the `Expires` value in the `CreateSequence` element as the `Expires` value in the `CreateSequenceResponse` element.</span></span> <span data-ttu-id="a86ad-140">De lo contrario, el respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] lee y pasa por alto los valores `Expires` y `Offer/Expires`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-140">Otherwise, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder reads and ignores the `Expires` and `Offer/Expires` values.</span></span>  
  
-   <span data-ttu-id="a86ad-141">B1106: al tener acceso al mensaje `CreateSequenceResponse`, el iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] lee el valor opcional `Expires`, pero no lo utiliza.</span><span class="sxs-lookup"><span data-stu-id="a86ad-141">B1106: When accessing the `CreateSequenceResponse` message, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator reads the optional `Expires` value but does not use it.</span></span>  
  
-   <span data-ttu-id="a86ad-142">B1107: el iniciador y respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] siempre generan el elemento opcional `IncompleteSequenceBehavior` en los elementos `CreateSequence/Offer` y `CreateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-142">B1107: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator and Responder always generate the optional `IncompleteSequenceBehavior` element in the `CreateSequence/Offer` and `CreateSequenceResponse` elements.</span></span>  
  
-   <span data-ttu-id="a86ad-143">B1108: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] solo utiliza los valores `DiscardFollowingFirstGap` y `NoDiscard` en el elemento `IncompleteSequenceBehavior`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-143">B1108: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses only the `DiscardFollowingFirstGap` and `NoDiscard` values in the `IncompleteSequenceBehavior` element.</span></span>  
  
    -   <span data-ttu-id="a86ad-144">WS-ReliableMessaging utiliza el mecanismo `Offer` para establecer las dos secuencias correlacionadas inversas que forman una sesión.</span><span class="sxs-lookup"><span data-stu-id="a86ad-144">WS-ReliableMessaging utilizes the `Offer` mechanism to establish the two converse correlated sequences that form a session.</span></span>  
  
-   <span data-ttu-id="a86ad-145">B1109: si `CreateSequence` contiene un elemento `Offer`, el respondedor unidireccional de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] rechaza la secuencia proporcionada respondiendo con una `CreateSequenceResponse` sin un elemento `Accept`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-145">B1109: If `CreateSequence` contains an `Offer` element, the one way [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder rejects the offered sequence by responding with a `CreateSequenceResponse` without an `Accept` element.</span></span>  
  
-   <span data-ttu-id="a86ad-146">B1110: si un respondedor de mensajería de confianza rechaza la secuencia proporcionada, el iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] produce un error en la secuencia recientemente establecida.</span><span class="sxs-lookup"><span data-stu-id="a86ad-146">B1110: If a Reliable Messaging Responder rejects the offered sequence, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator faults the newly established sequence.</span></span>  
  
-   <span data-ttu-id="a86ad-147">B1111: si `CreateSequence` no contiene un elemento `Offer`, el respondedor bidireccional de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] rechaza la secuencia proporcionada respondiendo con un error de `CreateSequenceRefused`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-147">B1111: If `CreateSequence` does not contain an `Offer` element, the two-way [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder rejects the offered sequence by responding with a `CreateSequenceRefused` fault.</span></span>  
  
-   <span data-ttu-id="a86ad-148">R1112: cuando dos secuencias inversas se establecen utilizando el mecanismo `Offer`, la propiedad `[address]` de la referencia de extremo `CreateSequenceResponse/Accept/AcksTo` debe coincidir con el URI de destino del mensaje `CreateSequence` byte a byte.</span><span class="sxs-lookup"><span data-stu-id="a86ad-148">R1112: When two converse sequences are established using the `Offer` mechanism, the `[address]` property of the `CreateSequenceResponse/Accept/AcksTo` endpoint reference must match the destination URI of the `CreateSequence` message byte for byte.</span></span>  
  
-   <span data-ttu-id="a86ad-149">R1113: cuando dos secuencias inversas se establecen utilizando el mecanismo `Offer`, todos los mensajes en ambas secuencias que fluyen desde el iniciador hasta el respondedor se deben enviar a la misma referencia de extremo.</span><span class="sxs-lookup"><span data-stu-id="a86ad-149">R1113: When two converse sequences are established using the `Offer` mechanism, all messages on both sequences flowing from the Initiator to the Responder must be sent to the same endpoint reference.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a86ad-150"> utiliza WS-ReliableMessaging para establecer sesiones confiables entre el iniciador y el respondedor.</span><span class="sxs-lookup"><span data-stu-id="a86ad-150"> uses WS-ReliableMessaging to establish reliable sessions between the Initiator and the Responder.</span></span> <span data-ttu-id="a86ad-151">La implementación de WS-ReliableMessaging de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona una sesión confiable para patrones de mensajería dúplex completa y de solicitud-respuesta unidireccional.</span><span class="sxs-lookup"><span data-stu-id="a86ad-151">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WS-ReliableMessaging implementation provides a reliable session for one-way, request-reply and full duplex messaging patterns.</span></span> <span data-ttu-id="a86ad-152">El mecanismo `Offer` de WS-ReliableMessaging en `CreateSequence` y `CreateSequenceResponse` le permite establecer dos secuencias inversas correlacionadas y proporciona un protocolo de sesión que es apto para todos los extremos de mensajes.</span><span class="sxs-lookup"><span data-stu-id="a86ad-152">The WS-ReliableMessaging `Offer` mechanism on `CreateSequence` and `CreateSequenceResponse` lets you establish two correlated converse sequences and provides a session protocol that is suitable for all message endpoints.</span></span> <span data-ttu-id="a86ad-153">Dado que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona una garantía de seguridad para este tipo de sesiones, incluyendo protección de un extremo a otro para la integridad de la sesión, es práctico asegurar que los mensajes dirigidos a la misma parte lleguen al mismo destino.</span><span class="sxs-lookup"><span data-stu-id="a86ad-153">Because [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides a security guarantee for such a session including end-to-end protection for session integrity, it is practical to ensure that messages intended for the same party arrive at the same destination.</span></span> <span data-ttu-id="a86ad-154">Esto también permite el “apoyo a caballo” de confirmaciones de secuencias en mensajes de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a86ad-154">This also allows "piggy-backing" of sequence acknowledgements on application messages.</span></span> <span data-ttu-id="a86ad-155">Por lo tanto, se aplican restricciones R1102, R1112 y R1113 a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a86ad-155">Therefore, constraints R1102, R1112, and R1113 apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 <span data-ttu-id="a86ad-156">Ejemplo de mensaje `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-156">An example of a `CreateSequence` message.</span></span>  
  
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
  
 <span data-ttu-id="a86ad-157">Ejemplo de mensaje `CreateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-157">An example of a `CreateSequenceResponse` message.</span></span>  
  
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
  
### <a name="closing-a-sequence"></a><span data-ttu-id="a86ad-158">Cierre de una secuencia</span><span class="sxs-lookup"><span data-stu-id="a86ad-158">Closing a Sequence</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a86ad-159"> utiliza los mensajes `CloseSequence` y `CloseSequenceResponse` para llevar a cabo un cierre iniciado por el origen de la mensajería de confianza.</span><span class="sxs-lookup"><span data-stu-id="a86ad-159"> uses the `CloseSequence` and `CloseSequenceResponse` messages for a Reliable Messaging source-initiated shutdown.</span></span> <span data-ttu-id="a86ad-160">El destino de la mensajería de confianza de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no inicia el cierre y el origen de la mensajería de confianza de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no admite un cierre iniciado por el destino de la mensajería de confianza.</span><span class="sxs-lookup"><span data-stu-id="a86ad-160">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging destination does not initiate shutdown and the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging source does not support a Reliable Messaging destination-initiated shutdown.</span></span> <span data-ttu-id="a86ad-161">Las siguientes restricciones son aplicables:</span><span class="sxs-lookup"><span data-stu-id="a86ad-161">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="a86ad-162">B1201: el origen de la mensajería de confianza de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] siempre envía un mensaje `CloseSequence` para cerrar la secuencia.</span><span class="sxs-lookup"><span data-stu-id="a86ad-162">B1201: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging source always sends a `CloseSequence` message to shut down the sequence.</span></span>  
  
-   <span data-ttu-id="a86ad-163">B1202: el origen de la mensajería de confianza espera la confirmación del intervalo completo de mensajes de secuencia antes de enviar el mensaje `CloseSequence`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-163">B1202: The Reliable Messaging source waits for acknowledgement of the full range of sequence messages before sending the `CloseSequence` message.</span></span>  
  
-   <span data-ttu-id="a86ad-164">B1203: el origen de la mensajería de confianza siempre incluye el elemento opcional `LastMsgNumber`, a menos que la secuencia no contenga mensajes.</span><span class="sxs-lookup"><span data-stu-id="a86ad-164">B1203: The Reliable Messaging source always includes the optional `LastMsgNumber` element unless the sequence does not contain messages.</span></span>  
  
-   <span data-ttu-id="a86ad-165">R1204: el destino de la mensajería de confianza no debe iniciar el cierre mediante el envío de un mensaje `CloseSequence`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-165">R1204: The Reliable Messaging destination must not initiate shutdown by sending a `CloseSequence` message.</span></span>  
  
-   <span data-ttu-id="a86ad-166">B1205: tras recibir un mensaje `CloseSequence`, el origen de la mensajería de confianza de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] considera la secuencia incompleta y envía un error.</span><span class="sxs-lookup"><span data-stu-id="a86ad-166">B1205: Upon receiving a `CloseSequence` message, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging source considers the sequence incomplete and sends a fault.</span></span>  
  
 <span data-ttu-id="a86ad-167">Ejemplo de mensaje `CloseSequence`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-167">An example of a `CloseSequence` message.</span></span>  
  
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
  
### <a name="sequence-termination"></a><span data-ttu-id="a86ad-168">Finalización de secuencia</span><span class="sxs-lookup"><span data-stu-id="a86ad-168">Sequence Termination</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a86ad-169"> utiliza principalmente el protocolo de enlace `TerminateSequence/TerminateSequenceResponse` después de completar el protocolo de enlace `CloseSequence/CloseSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-169"> primarily uses the `TerminateSequence/TerminateSequenceResponse` handshake after completing the `CloseSequence/CloseSequenceResponse` handshake.</span></span> <span data-ttu-id="a86ad-170">El destino de la mensajería de confianza de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no inicia la finalización y el origen de la mensajería de confianza no admite una finalización de la mensajería de confianza iniciada por el destino.</span><span class="sxs-lookup"><span data-stu-id="a86ad-170">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging destination does not initiate termination and the Reliable Messaging source does not support a Reliable Messaging destination-initiated termination.</span></span> <span data-ttu-id="a86ad-171">Las siguientes restricciones son aplicables:</span><span class="sxs-lookup"><span data-stu-id="a86ad-171">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="a86ad-172">B1301: el iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] solo envía el mensaje `TerminateSequence` después de la finalización correcta del protocolo de enlace `CloseSequence/CloseSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-172">B1301: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator only sends the `TerminateSequence` message after the successful completion of the `CloseSequence/CloseSequenceResponse` handshake.</span></span>  
  
-   <span data-ttu-id="a86ad-173">R1302: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] valida que el elemento `LastMsgNumber` sea coherente en todos los mensajes `CloseSequence` y `TerminateSequence` para una secuencia determinada.</span><span class="sxs-lookup"><span data-stu-id="a86ad-173">R1302: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] validates that the `LastMsgNumber` element is consistent across all `CloseSequence` and `TerminateSequence` messages for a given sequence.</span></span> <span data-ttu-id="a86ad-174">Esto significa que `LastMsgNumber` no está presente en todos los mensajes `CloseSequence` y `TerminateSequence`, o está presente y es idéntico en todos los mensajes `CloseSequence` y `TerminateSequence`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-174">This means that `LastMsgNumber` is either not present on all `CloseSequence` and `TerminateSequence` messages, or it is present and identical on all `CloseSequence` and `TerminateSequence` messages.</span></span>  
  
-   <span data-ttu-id="a86ad-175">B1303: al recibir un mensaje `TerminateSequence` después del protocolo de enlace `CloseSequence/CloseSequenceResponse`, el destino de la mensajería de confianza responde con un mensaje `TerminateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-175">B1303: When receiving a `TerminateSequence` message after the `CloseSequence/CloseSequenceResponse` handshake, the Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="a86ad-176">Puesto que el origen de la mensajería de confianza recibe la confirmación definitiva antes de enviar el mensaje `TerminateSequence`, el destino de la mensajería de confianza sabe sin duda que finaliza la secuencia y reclama recursos inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="a86ad-176">Because the Reliable Messaging source has the final acknowledgement before sending the `TerminateSequence` message, the Reliable Messaging destination knows without doubt that the sequence ends, and reclaims resources immediately.</span></span>  
  
-   <span data-ttu-id="a86ad-177">B1304: al recibir un mensaje `TerminateSequence` antes del protocolo de enlace `CloseSequence/CloseSequenceResponse`, el destino de la mensajería de confianza de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] responde con un mensaje `TerminateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-177">B1304: When receiving a `TerminateSequence` message prior to the `CloseSequence/CloseSequenceResponse` handshake, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="a86ad-178">Si el destino de la mensajería de confianza determina que no hay incoherencias en la secuencia, el destino de la mensajería de confianza espera durante un tiempo especificado por el destino de la aplicación antes de reclamar recursos, para permitir al cliente que reciba la confirmación final.</span><span class="sxs-lookup"><span data-stu-id="a86ad-178">If the Reliable Messaging destination determines that there are no inconsistencies in the sequence, the Reliable Messaging destination waits for an application destination-specified time before reclaiming resources, to allow the client the chance to receive the final acknowledgement.</span></span> <span data-ttu-id="a86ad-179">De lo contrario, el destino de la mensajería de confianza reclama recursos inmediatamente e indica al destino de la aplicación que la secuencia finaliza de manera dudosa iniciando el evento `Faulted`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-179">Otherwise, the Reliable Messaging destination reclaims resources immediately and indicates to the application destination that the sequence ends with doubt by raising the `Faulted` event.</span></span>  
  
 <span data-ttu-id="a86ad-180">Ejemplo de mensaje `TerminateSequence`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-180">An example of a `TerminateSequence` message.</span></span>  
  
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
  
### <a name="sequences"></a><span data-ttu-id="a86ad-181">Secuencias</span><span class="sxs-lookup"><span data-stu-id="a86ad-181">Sequences</span></span>  
 <span data-ttu-id="a86ad-182">A continuación, se muestra una lista de restricciones que se aplican a las secuencias:</span><span class="sxs-lookup"><span data-stu-id="a86ad-182">The following is a list of constraints that apply to sequences:</span></span>  
  
-   <span data-ttu-id="a86ad-183">B1401:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera y obtiene acceso a los números de secuencia no superiores a `xs:long`del valor inclusivo máximo, 9223372036854775807.</span><span class="sxs-lookup"><span data-stu-id="a86ad-183">B1401:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates and accesses sequence numbers no higher than `xs:long`’s maximum inclusive value, 9223372036854775807.</span></span>  
  
 <span data-ttu-id="a86ad-184">Ejemplo de encabezado `Sequence`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-184">An example of a `Sequence` header.</span></span>  
  
```xml  
<wsrm:Sequence s:mustUnderstand="1">  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:MessageNumber>1</wsrm:MessageNumber>  
</wsrm:Sequence>  
```  
  
### <a name="request-acknowledgement"></a><span data-ttu-id="a86ad-185">Solicitar confirmación</span><span class="sxs-lookup"><span data-stu-id="a86ad-185">Request Acknowledgement</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a86ad-186"> utiliza el encabezado `AckRequested` como un mecanismo de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="a86ad-186"> uses the `AckRequested` header as a keep-alive mechanism.</span></span>  
  
 <span data-ttu-id="a86ad-187">Ejemplo de encabezado `AckRequested`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-187">An example of an `AckRequested` header.</span></span>  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement"></a><span data-ttu-id="a86ad-188">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="a86ad-188">SequenceAcknowledgement</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a86ad-189"> utiliza un mecanismo de "apoyo a caballo" para las confirmaciones de secuencias proporcionadas en la mensajería de confianza de WS.</span><span class="sxs-lookup"><span data-stu-id="a86ad-189"> uses a "piggy-back" mechanism for sequence acknowledgements provided in WS-Reliable Messaging.</span></span> <span data-ttu-id="a86ad-190">Las siguientes restricciones son aplicables:</span><span class="sxs-lookup"><span data-stu-id="a86ad-190">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="a86ad-191">R1601: Cuando dos secuencias inversas se establecen utilizando el `Offer` mecanismo, el `SequenceAcknowledgement` encabezado puede incluirse en cualquier mensaje de aplicación transmitido al destinatario previsto.</span><span class="sxs-lookup"><span data-stu-id="a86ad-191">R1601: When two converse sequences are established using the `Offer` mechanism, the `SequenceAcknowledgement` header may be included in any application message transmitted to the intended recipient.</span></span> <span data-ttu-id="a86ad-192">El extremo remoto debe poder tener acceso a un encabezado `SequenceAcknowledgement` superpuesto.</span><span class="sxs-lookup"><span data-stu-id="a86ad-192">The remote endpoint must be able to access a piggybacked `SequenceAcknowledgement` header.</span></span>  
  
-   <span data-ttu-id="a86ad-193">B1602: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no genera encabezados `SequenceAcknowledgement` que contengan elementos `Nack`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-193">B1602: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not generate `SequenceAcknowledgement` headers that contain `Nack` elements.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a86ad-194"> valida que cada elemento `Nack` contiene un número de secuencia, pero omite de otra forma el elemento y el valor de `Nack`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-194"> validates that each `Nack` element contains a sequence number, but otherwise ignores the `Nack` element and value.</span></span>  
  
 <span data-ttu-id="a86ad-195">Ejemplo de encabezado `SequenceAcknowledgement`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-195">An example of a `SequenceAcknowledgement` header.</span></span>  
  
```xml  
<wsrm:SequenceAcknowledgement>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:AcknowledgementRange Lower="1" Upper="1"></wsrm:AcknowledgementRange>  
</wsrm:SequenceAcknowledgement>  
```  
  
### <a name="ws-reliablemessaging-faults"></a><span data-ttu-id="a86ad-196">Errores de WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="a86ad-196">WS-ReliableMessaging Faults</span></span>  
 <span data-ttu-id="a86ad-197">A continuación, se muestra una lista de restricciones que se aplican a la implementación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] de errores de WS-ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="a86ad-197">The following is a list of constraints that apply to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementation of WS-ReliableMessaging faults.</span></span> <span data-ttu-id="a86ad-198">Las siguientes restricciones son aplicables:</span><span class="sxs-lookup"><span data-stu-id="a86ad-198">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="a86ad-199">B1701: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no genera `MessageNumberRollover` errores.</span><span class="sxs-lookup"><span data-stu-id="a86ad-199">B1701: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not generate `MessageNumberRollover` faults.</span></span>  
  
-   <span data-ttu-id="a86ad-200">B1702: sobre SOAP 1.2, cuando el extremo de servicio alcanza su límite de conexiones y no puede procesar nuevas conexiones, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera un subcódigo de error `CreateSequenceRefused` anidado, `netrm:ConnectionLimitReached`, como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a86ad-200">B1702: Over SOAP 1.2, when the service endpoint reaches its connection limit and cannot process new connections, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates a nested `CreateSequenceRefused` fault subcode, `netrm:ConnectionLimitReached`, as shown in the following example.</span></span>  
  
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
  
### <a name="ws-addressing-faults"></a><span data-ttu-id="a86ad-201">Errores WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="a86ad-201">WS-Addressing Faults</span></span>  
 <span data-ttu-id="a86ad-202">Dado que WS-ReliableMessaging utiliza WS-Addressing, la implementación de WS-ReliableMessaging de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] puede generar y transmitir errores de WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="a86ad-202">Because WS-ReliableMessaging uses WS-Addressing, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WS-ReliableMessaging implementation may generate and transmit WS-Addressing faults.</span></span> <span data-ttu-id="a86ad-203">Esta sección cubre los errores de WS-Addressing que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera explícitamente y transmite en la capa de WS-ReliableMessaging:</span><span class="sxs-lookup"><span data-stu-id="a86ad-203">This section covers the WS-Addressing faults that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] explicitly generates and transmits at the WS-ReliableMessaging layer:</span></span>  
  
-   <span data-ttu-id="a86ad-204">B1801:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera y transmite el `Message Addressing Header Required` de error cuando se cumple alguna de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="a86ad-204">B1801:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates and transmits the `Message Addressing Header Required` fault when one of the following is true:</span></span>  
  
    -   <span data-ttu-id="a86ad-205">A un mensaje `CreateSequence`, `CloseSequence`, o `TerminateSequence` le falta un encabezado `MessageId`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-205">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `MessageId` header.</span></span>  
  
    -   <span data-ttu-id="a86ad-206">A un mensaje `CreateSequence`, `CloseSequence`, o `TerminateSequence` le falta un encabezado `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-206">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `ReplyTo` header.</span></span>  
  
    -   <span data-ttu-id="a86ad-207">A un mensaje `CreateSequenceResponse`, `CloseSequenceResponse`, o `TerminateSequenceResponse` le falta un encabezado `RelatesTo`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-207">A `CreateSequenceResponse`, `CloseSequenceResponse`, or `TerminateSequenceResponse` message is missing a `RelatesTo` header.</span></span>  
  
-   <span data-ttu-id="a86ad-208">B1802:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera y transmite el `Endpoint Unavailable` error para indicar que no hay ningún extremo escuchando que puede procesar la secuencia en función de examen de los encabezados de direccionamiento en el `CreateSequence` mensaje.</span><span class="sxs-lookup"><span data-stu-id="a86ad-208">B1802:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates and transmits the `Endpoint Unavailable` fault to indicate there is no endpoint listening that can process the sequence based on examination of the addressing headers in the `CreateSequence` message.</span></span>  
  
## <a name="protocol-composition"></a><span data-ttu-id="a86ad-209">Composición de protocolos</span><span class="sxs-lookup"><span data-stu-id="a86ad-209">Protocol Composition</span></span>  
  
### <a name="composition-with-ws-addressing"></a><span data-ttu-id="a86ad-210">Composición con WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="a86ad-210">Composition with WS-Addressing</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a86ad-211"> admite dos versiones de WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] y las recomendaciones de WS-Addressing 1.0 de W3C [WS-ADDR-CORE] y [WS-ADDR-SOAP].</span><span class="sxs-lookup"><span data-stu-id="a86ad-211"> supports two versions of WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] and W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] and [WS-ADDR-SOAP].</span></span>  
  
 <span data-ttu-id="a86ad-212">Aunque la especificación de WS-ReliableMessaging solo menciona WS-Addressing 2004/08, no restringe la versión de WS-Addressing que se ha de utilizar.</span><span class="sxs-lookup"><span data-stu-id="a86ad-212">While the WS-ReliableMessaging specification mentions only WS-Addressing 2004/08, it does not restrict the WS-Addressing version to be used.</span></span> <span data-ttu-id="a86ad-213">A continuación, se muestra una lista de restricciones que se aplican a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="a86ad-213">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="a86ad-214">R2101: WS-Addressing 2004/08 y WS-Addressing 1.0 se pueden utilizar con la mensajería de confianza de WS.</span><span class="sxs-lookup"><span data-stu-id="a86ad-214">R2101: Both WS-Addressing 2004/08 and WS-Addressing 1.0 can be used with WS-Reliable Messaging.</span></span>  
  
-   <span data-ttu-id="a86ad-215">R2102: se debe utilizar una única versión de WS-Addressing a lo largo de una secuencia de WS-ReliableMessaging determinada o un par de secuencias inversas correlacionadas mediante el mecanismo `Offer`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-215">R2102: A single version of WS-Addressing must be used throughout a given WS-ReliableMessaging sequence or a pair of converse sequences correlated by using the `Offer` mechanism.</span></span>  
  
### <a name="composition-with-soap"></a><span data-ttu-id="a86ad-216">Composición con SOAP</span><span class="sxs-lookup"><span data-stu-id="a86ad-216">Composition with SOAP</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a86ad-217"> admite el uso de SOAP 1.1 y SOAP 1.2 con la mensajería de confianza de WS.</span><span class="sxs-lookup"><span data-stu-id="a86ad-217"> supports the use of both SOAP 1.1 and SOAP 1.2 with WS-Reliable Messaging.</span></span>  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a><span data-ttu-id="a86ad-218">Composición con WS-Security y WS-SecureConversation</span><span class="sxs-lookup"><span data-stu-id="a86ad-218">Composition with WS-Security and WS-SecureConversation</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a86ad-219"> proporciona protección para secuencias de WS-ReliableMessaging mediante el transporte seguro (HTTPS), la composición con WS-Security y la composición con WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="a86ad-219"> provides protection for WS-ReliableMessaging sequences by using secure Transport (HTTPS), composition with WS-Security, and composition with WS-Secure Conversation.</span></span> <span data-ttu-id="a86ad-220">Los protocolos WS-ReliableMessaging 1.1, WS-Security 1.1 y WS-Secure Conversation 1.3 deberían utilizarse conjuntamente.</span><span class="sxs-lookup"><span data-stu-id="a86ad-220">The WS-ReliableMessaging 1.1 protocol, WS-Security 1.1 and WS-Secure Conversation 1.3 protocol should be used together.</span></span> <span data-ttu-id="a86ad-221">A continuación, se muestra una lista de restricciones que se aplican a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="a86ad-221">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="a86ad-222">R2301: para proteger la integridad de una secuencia de WS-ReliableMessaging además de la integridad y confidencialidad de los mensajes individuales, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requiere que se utilice WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="a86ad-222">R2301: To protect the integrity of a WS-ReliableMessaging sequence in addition to the integrity and confidentiality of individual messages, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requires that WS-Secure Conversation must be used.</span></span>  
  
-   <span data-ttu-id="a86ad-223">R2302:AWS-Secure Conversation debe establecerse antes de establecer secuencias de WS-ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="a86ad-223">R2302:AWS-Secure Conversation session must be established prior to establishing WS-ReliableMessaging sequence(s).</span></span>  
  
-   <span data-ttu-id="a86ad-224">R2303: si la duración de la secuencia de WS-ReliableMessaging supera la duración de la sesión de WS-Secure Conversation, el `SecurityContextToken` establecido mediante WS-Secure Conversation se debe renovar utilizando el enlace de renovación de WS-Secure Conversation correspondiente.</span><span class="sxs-lookup"><span data-stu-id="a86ad-224">R2303: If the WS-ReliableMessaging sequence lifetime exceeds the WS-Secure Conversation session’s lifetime, the `SecurityContextToken` established by using WS-Secure Conversation must be renewed by using the corresponding WS-Secure Conversation Renewal binding.</span></span>  
  
-   <span data-ttu-id="a86ad-225">B2304:WS-ReliableMessaging secuencia o un par de secuencias inversas correlacionadas siempre están enlazados a una sola sesión de WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="a86ad-225">B2304:WS-ReliableMessaging sequence or a pair of correlated converse sequences are always bound to a single WS-SecureConversation session.</span></span>  
  
-   <span data-ttu-id="a86ad-226">R2305: cuando se compone con WS-Secure Conversation, el respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requiere que el mensaje `CreateSequence` contenga el elemento `wsse:SecurityTokenReference` y el encabezado `wsrm:UsesSequenceSTR`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-226">R2305: When composed with WS-Secure Conversation, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] responder requires that the `CreateSequence` message contain the `wsse:SecurityTokenReference` element and the `wsrm:UsesSequenceSTR` header.</span></span>  
  
 <span data-ttu-id="a86ad-227">Ejemplo de encabezado `UsesSequenceSTR`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-227">An example of a `UsesSequenceSTR` header.</span></span>  
  
```xml  
<wsrm:UsesSequenceSTR></wsrm:UsesSequenceSTR>  
```  
  
### <a name="composition-with-ssltls-sessions"></a><span data-ttu-id="a86ad-228">Composición con sesiones de SSL/TLS</span><span class="sxs-lookup"><span data-stu-id="a86ad-228">Composition with SSL/TLS sessions</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a86ad-229"> no admite la composición con sesiones de SSL/TLS:</span><span class="sxs-lookup"><span data-stu-id="a86ad-229"> does not support composition with SSL/TLS sessions:</span></span>  
  
-   <span data-ttu-id="a86ad-230">B2401: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no genera el encabezado `wsrm:UsesSequenceSSL`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-230">B2401: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not generate the `wsrm:UsesSequenceSSL` header.</span></span>  
  
-   <span data-ttu-id="a86ad-231">R2402: un iniciador de la mensajería de confianza no debe enviar un mensaje `CreateSequence` con un encabezado `wsrm:UsesSequenceSSL` a un respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a86ad-231">R2402: A Reliable Messaging Initiator must not send a `CreateSequence` message with a `wsrm:UsesSequenceSSL` header to a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder.</span></span>  
  
### <a name="composition-with-ws-policy"></a><span data-ttu-id="a86ad-232">Composición con WS-Policy</span><span class="sxs-lookup"><span data-stu-id="a86ad-232">Composition with WS-Policy</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a86ad-233"> admite dos versiones de WS-Policy: WS-Policy 1.2 y WS-Policy 1.5.</span><span class="sxs-lookup"><span data-stu-id="a86ad-233"> supports two versions of WS-Policy: WS-Policy 1.2 and WS-Policy 1.5.</span></span>  
  
## <a name="ws-reliablemessaging-ws-policy-assertion"></a><span data-ttu-id="a86ad-234">Aserción de WS-Policy de WS-ReliableMessaging </span><span class="sxs-lookup"><span data-stu-id="a86ad-234">WS-ReliableMessaging WS-Policy Assertion</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a86ad-235"> utiliza la aserción de WS-Policy de WS-ReliableMessaging `wsrm:RMAssertion` para describir funciones de extremos.</span><span class="sxs-lookup"><span data-stu-id="a86ad-235"> uses WS-ReliableMessaging WS-Policy Assertion `wsrm:RMAssertion` to describe endpoints capabilities.</span></span> <span data-ttu-id="a86ad-236">A continuación, se muestra una lista de restricciones que se aplican a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="a86ad-236">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="a86ad-237">B3001: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] adjunta la aserción `wsrmn:RMAssertion` de WS-Policy Assertion a elementos `wsdl:binding`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-237">B3001: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] attaches `wsrmn:RMAssertion` WS-Policy Assertion to `wsdl:binding` elements.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a86ad-238"> admite datos adjuntos para los elementos `wsdl:binding` y `wsdl:port`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-238"> supports both attachments to `wsdl:binding` and `wsdl:port` elements.</span></span>  
  
-   <span data-ttu-id="a86ad-239">B3002: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] nunca genera la etiqueta `wsp:Optional`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-239">B3002: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] never generates the `wsp:Optional` tag.</span></span>  
  
-   <span data-ttu-id="a86ad-240">B3003: al tener acceso la aserción de WS-Policy `wsrmp:RMAssertion`, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] omite la etiqueta `wsp:Optional` y trata la directiva WS-RM como obligatoria.</span><span class="sxs-lookup"><span data-stu-id="a86ad-240">B3003: When accessing the `wsrmp:RMAssertion` WS-Policy Assertion, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ignores the `wsp:Optional` tag and treats the WS-RM policy as mandatory.</span></span>  
  
-   <span data-ttu-id="a86ad-241">R3004: puesto que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no compone con sesiones de SSL/TLS, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no acepta ninguna directiva que especifique `wsrmp:SequenceTransportSecurity`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-241">R3004: Because [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not compose with SSL/TLS sessions, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not accept policy that specifies `wsrmp:SequenceTransportSecurity`.</span></span>  
  
-   <span data-ttu-id="a86ad-242">B3005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] siempre genera el elemento `wsrmp:DeliveryAssurance`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-242">B3005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] always generates the `wsrmp:DeliveryAssurance` element.</span></span>  
  
-   <span data-ttu-id="a86ad-243">B3006: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] siempre especifica la garantía de entrega `wsrmp:ExactlyOnce`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-243">B3006: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] always specifies the `wsrmp:ExactlyOnce` delivery assurance.</span></span>  
  
-   <span data-ttu-id="a86ad-244">B3007: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera y lee las siguientes propiedades de la aserción de WS-ReliableMessaging y proporciona control sobre ellas en el elemento [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] de `ReliableSessionBindingElement`:</span><span class="sxs-lookup"><span data-stu-id="a86ad-244">B3007: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates and reads the following properties of the WS-ReliableMessaging assertion and provides control over them on the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]`ReliableSessionBindingElement`:</span></span>  
  
    -   `netrmp:InactivityTimeout`  
  
    -   `netrmp:AcknowledgementInterval`  
  
     <span data-ttu-id="a86ad-245">Ejemplo de `RMAssertion`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-245">An example of a `RMAssertion`.</span></span>  
  
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
  
## <a name="flow-control-ws-reliablemessaging-extension"></a><span data-ttu-id="a86ad-246">Extensión de WS-ReliableMessaging de control de flujo</span><span class="sxs-lookup"><span data-stu-id="a86ad-246">Flow Control WS-ReliableMessaging Extension</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a86ad-247"> utiliza la extensibilidad de WS-ReliableMessaging para proporcionar un mayor control adicional y opcional sobre el flujo de mensajes de secuencias.</span><span class="sxs-lookup"><span data-stu-id="a86ad-247"> uses WS-ReliableMessaging extensibility to provide optional additional tighter control over sequence message flow.</span></span>  
  
 <span data-ttu-id="a86ad-248">Control de flujo se habilita estableciendo el `ReliableSessionBindingElement`del `FlowControlEnabled``boolean` propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-248">Flow control is enabled by setting the `ReliableSessionBindingElement`’s `FlowControlEnabled``boolean` property to `true`.</span></span> <span data-ttu-id="a86ad-249">A continuación, se muestra una lista de restricciones que se aplican a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="a86ad-249">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="a86ad-250">B4001: cuando está habilitado el control de flujo de la mensajería de confianza, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera un elemento `netrm:BufferRemaining` en la extensibilidad de elementos del encabezado `SequenceAcknowledgement`, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a86ad-250">B4001: When Reliable Messaging Flow Control is enabled, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates a `netrm:BufferRemaining` element in the element extensibility of the `SequenceAcknowledgement` header, as shown in the following example.</span></span>  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="1" Lower="1"/>             
      <netrm:BufferRemaining>8</netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   <span data-ttu-id="a86ad-251">B4002: incluso cuando está habilitado el control de flujo de la mensajería de confianza, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no requiere un elemento `netrm:BufferRemaining` en el encabezado `SequenceAcknowledgement`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-251">B4002: Even when Reliable Messaging Flow Control is enabled, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not require a `netrm:BufferRemaining` element in the `SequenceAcknowledgement` header.</span></span>  
  
-   <span data-ttu-id="a86ad-252">B4003: el destino de la mensajería de confianza de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza `netrm:BufferRemaining` para indicar cuántos mensajes nuevos puede almacenar en búfer.</span><span class="sxs-lookup"><span data-stu-id="a86ad-252">B4003: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging Destination uses `netrm:BufferRemaining` to indicate how many new messages it can buffer.</span></span>  
  
-   <span data-ttu-id="a86ad-253">B4004:when confiable de mensajería de flujo de Control está habilitado, el [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] origen de la mensajería confiable utiliza el valor de `netrm:BufferRemaining` para la transmisión de mensajes del acelerador.</span><span class="sxs-lookup"><span data-stu-id="a86ad-253">B4004:When Reliable Messaging Flow Control is enabled, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging Source uses the value of `netrm:BufferRemaining` to throttle message transmission.</span></span>  
  
-   <span data-ttu-id="a86ad-254">B4005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera valores enteros de `netrm:BufferRemaining` entre 0 y 4.096, ambos incluidos, y lee valores enteros entre 0 y el valor `xs:int` 214748364 de `maxInclusive`, ambos incluidos.</span><span class="sxs-lookup"><span data-stu-id="a86ad-254">B4005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates `netrm:BufferRemaining` integer values between 0 and 4096 inclusive, and reads integer values between 0 and `xs:int`’s `maxInclusive` value 214748364 inclusive.</span></span>  
  
## <a name="message-exchange-patterns"></a><span data-ttu-id="a86ad-255">Modelos de intercambio de mensajes</span><span class="sxs-lookup"><span data-stu-id="a86ad-255">Message Exchange Patterns</span></span>  
 <span data-ttu-id="a86ad-256">En esta sección se describe el comportamiento de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cuando se utiliza WS-ReliableMessaging para patrones de intercambio de mensajes diferentes.</span><span class="sxs-lookup"><span data-stu-id="a86ad-256">This section describes [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]'s behavior when WS-ReliableMessaging is used for different Message Exchange Patterns.</span></span> <span data-ttu-id="a86ad-257">Para cada patrón de intercambio de mensajes, se consideran los dos escenarios de implementación siguientes:</span><span class="sxs-lookup"><span data-stu-id="a86ad-257">For each Message Exchange Pattern the following two deployments scenarios are considered:</span></span>  
  
-   <span data-ttu-id="a86ad-258">Iniciador no direccionable: el iniciador está tras un firewall; el respondedor solo puede entregar mensajes al iniciador mediante respuestas HTTP.</span><span class="sxs-lookup"><span data-stu-id="a86ad-258">Non-Addressable Initiator: Initiator is behind a firewall; Responder can deliver messages to the Initiator only on HTTP responses.</span></span>  
  
-   <span data-ttu-id="a86ad-259">Iniciador direccionable: el iniciador y el respondedor pueden enviar solicitudes HTTP; en otras palabras, se pueden establecer dos conexiones HTTP inversas.</span><span class="sxs-lookup"><span data-stu-id="a86ad-259">Addressable Initiator: Initiator and Responder both can be sent HTTP requests; in other words, two converse HTTP connections can be established.</span></span>  
  
### <a name="one-way-non-addressable-initiator"></a><span data-ttu-id="a86ad-260">Iniciador unidireccional no direccionable</span><span class="sxs-lookup"><span data-stu-id="a86ad-260">One-way, Non-addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="a86ad-261">Enlaces</span><span class="sxs-lookup"><span data-stu-id="a86ad-261">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a86ad-262"> proporciona un patrón de intercambio de mensajes unidireccional usando una secuencia sobre un canal HTTP.</span><span class="sxs-lookup"><span data-stu-id="a86ad-262"> provides a one-way message exchange pattern using one sequence over one HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a86ad-263"> usa solicitudes HTTP para transmitir todos los mensajes del iniciador al respondedor y respuestas HTTP para transmitir todos los mensajes del respondedor al iniciador.</span><span class="sxs-lookup"><span data-stu-id="a86ad-263"> uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="a86ad-264">Intercambio de CreateSequence</span><span class="sxs-lookup"><span data-stu-id="a86ad-264">CreateSequence Exchange</span></span>  
 <span data-ttu-id="a86ad-265">El iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transmite un mensaje `CreateSequence` sin elemento `Offer` en una solicitud HTTP y espera el mensaje `CreateSequenceResponse` en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="a86ad-265">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="a86ad-266">El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] crea una secuencia y transmite el mensaje `CreateSequenceResponse` sin elemento `Accept` en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="a86ad-266">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on the HTTP response.</span></span>  
  
#### <a name="sequenceacknowledgement"></a><span data-ttu-id="a86ad-267">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="a86ad-267">SequenceAcknowledgement</span></span>  
 <span data-ttu-id="a86ad-268">El iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] procesa las confirmaciones en la respuesta de todos los mensajes, salvo en los mensajes de error y el mensaje `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-268">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator processes acknowledgements on the reply of all messages except the `CreateSequence` message and fault messages.</span></span> <span data-ttu-id="a86ad-269">El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] siempre transmite una confirmación independiente en la respuesta HTTP a todos los mensajes de `AckRequested` y secuencias.</span><span class="sxs-lookup"><span data-stu-id="a86ad-269">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder always transmits a stand-alone acknowledgement on the HTTP response to all sequence and `AckRequested` messages.</span></span>  
  
#### <a name="closesequence-exchange"></a><span data-ttu-id="a86ad-270">Intercambio de CloseSequence</span><span class="sxs-lookup"><span data-stu-id="a86ad-270">CloseSequence Exchange</span></span>  
 <span data-ttu-id="a86ad-271">El iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transmite un mensaje `CloseSequence` en una solicitud HTTP y espera el mensaje `CreateSequenceResponse` en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="a86ad-271">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CloseSequence` message on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="a86ad-272">El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transmite el mensaje `CloseSequenceResponse` en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="a86ad-272">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>  
  
#### <a name="terminatesequence-exchange"></a><span data-ttu-id="a86ad-273">Intercambio de TerminateSequence</span><span class="sxs-lookup"><span data-stu-id="a86ad-273">TerminateSequence Exchange</span></span>  
 <span data-ttu-id="a86ad-274">El iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transmite un mensaje `TerminateSequence` en una solicitud HTTP y espera el mensaje `TerminateSequenceResponse` en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="a86ad-274">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `TerminateSequence` message on an HTTP request and expects the `TerminateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="a86ad-275">El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transmite el mensaje `TerminateSequenceResponse` en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="a86ad-275">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>  
  
### <a name="one-way-addressable-initiator"></a><span data-ttu-id="a86ad-276">Iniciador unidireccional y direccionable</span><span class="sxs-lookup"><span data-stu-id="a86ad-276">One Way, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="a86ad-277">Enlaces</span><span class="sxs-lookup"><span data-stu-id="a86ad-277">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a86ad-278"> proporciona un patrón de intercambio de mensajes unidireccional usando una secuencia sobre un canal HTTP entrante y uno saliente.</span><span class="sxs-lookup"><span data-stu-id="a86ad-278"> provides a one-way message exchange pattern using one sequence over one inbound and one outbound HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a86ad-279"> usa las solicitudes HTTP para transmitir todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="a86ad-279"> uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="a86ad-280">Todas las respuestas HTTP tienen un cuerpo vacío y código de estado HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="a86ad-280">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="a86ad-281">Intercambio de CreateSequence</span><span class="sxs-lookup"><span data-stu-id="a86ad-281">CreateSequence Exchange</span></span>  
 <span data-ttu-id="a86ad-282">El iniciador [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transmite un mensaje `CreateSequence` sin elemento `Offer` en una solicitud HTTP.</span><span class="sxs-lookup"><span data-stu-id="a86ad-282">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request.</span></span> <span data-ttu-id="a86ad-283">El respondedor [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] crea una secuencia y transmite el mensaje `CreateSequenceResponse` sin elemento `Accept` en una solicitud HTTP.</span><span class="sxs-lookup"><span data-stu-id="a86ad-283">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on an HTTP request.</span></span>  
  
### <a name="duplex-addressable-initiator"></a><span data-ttu-id="a86ad-284">Iniciador dúplex y direccionable</span><span class="sxs-lookup"><span data-stu-id="a86ad-284">Duplex, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="a86ad-285">Enlaces</span><span class="sxs-lookup"><span data-stu-id="a86ad-285">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a86ad-286"> proporciona un patrón de intercambio de mensajes totalmente asincrónico y bidireccional utilizando dos secuencias sobre un canal HTTP entrante y uno saliente.</span><span class="sxs-lookup"><span data-stu-id="a86ad-286"> provides a fully-asynchronous, two-way message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="a86ad-287">Este patrón de intercambio de mensajes se puede mezclar con el patrón de intercambio de mensajes del iniciador de `Request/Reply`, `Addressable` de una manera limitada.</span><span class="sxs-lookup"><span data-stu-id="a86ad-287">This message exchange pattern can be mixed with the `Request/Reply`, `Addressable` Initiator message exchange pattern in a limited way.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a86ad-288"> usa solicitudes HTTP para transmitir todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="a86ad-288"> uses HTTP requests to transmit all messages.</span></span> <span data-ttu-id="a86ad-289">Todas las respuestas HTTP tienen un cuerpo vacío y código de estado HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="a86ad-289">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="a86ad-290">Intercambio de CreateSequence</span><span class="sxs-lookup"><span data-stu-id="a86ad-290">CreateSequence Exchange</span></span>  
 <span data-ttu-id="a86ad-291">El iniciador [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transmite un mensaje `CreateSequence` con un elemento `Offer` en una solicitud HTTP.</span><span class="sxs-lookup"><span data-stu-id="a86ad-291">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="a86ad-292">El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] asegura que la `CreateSequence` tiene un elemento `Offer`, a continuación, crea una secuencia y transmite el mensaje `CreateSequenceResponse` con un elemento `Accept`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-292">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has an `Offer` element, then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>  
  
#### <a name="sequence-lifetime"></a><span data-ttu-id="a86ad-293">Duración de la secuencia</span><span class="sxs-lookup"><span data-stu-id="a86ad-293">Sequence Lifetime</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a86ad-294"> trata las dos secuencias como una sesión totalmente dúplex.</span><span class="sxs-lookup"><span data-stu-id="a86ad-294"> treats the two sequences as one fully-duplex session.</span></span>  
  
 <span data-ttu-id="a86ad-295">Tras generar un error que provoca un error en una secuencia, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] espera que el extremo remoto genere un error en ambas secuencias.</span><span class="sxs-lookup"><span data-stu-id="a86ad-295">Upon generating a fault that faults one sequence, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] expects the remote endpoint to fault both sequences.</span></span> <span data-ttu-id="a86ad-296">Tras leer un error que provoca un error en una secuencia, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] genera un error en ambas secuencias.</span><span class="sxs-lookup"><span data-stu-id="a86ad-296">Upon reading a fault that faults one sequence, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] faults both sequences.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a86ad-297"> puede cerrar su secuencia saliente y continuar procesando mensajes en su secuencia entrante.</span><span class="sxs-lookup"><span data-stu-id="a86ad-297"> can close its outbound sequence and continue to process messages on its inbound sequence.</span></span> <span data-ttu-id="a86ad-298">De manera inversa, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] puede procesar el cierre de la secuencia entrante y continuar enviando mensajes en su secuencia saliente.</span><span class="sxs-lookup"><span data-stu-id="a86ad-298">Conversely, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] can process the close of the inbound sequence and continue to send messages on its outbound sequence.</span></span>  
  
### <a name="request-reply-and-one-way-non-addressable-initiator"></a><span data-ttu-id="a86ad-299">Iniciador de solicitud-respuesta unidireccional y no direccionable</span><span class="sxs-lookup"><span data-stu-id="a86ad-299">Request-Reply and One-Way, Non-Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="a86ad-300">Enlaces</span><span class="sxs-lookup"><span data-stu-id="a86ad-300">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a86ad-301"> proporciona un patrón de intercambio unidireccional de mensajes de solicitud-respuesta usando dos secuencias sobre un canal HTTP.</span><span class="sxs-lookup"><span data-stu-id="a86ad-301"> provides a one-way and request-reply message exchange pattern using two sequences over one HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a86ad-302"> usa solicitudes HTTP para transmitir todos los mensajes del iniciador al respondedor y respuestas HTTP para transmitir todos los mensajes del respondedor al iniciador.</span><span class="sxs-lookup"><span data-stu-id="a86ad-302"> uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="a86ad-303">Intercambio de CreateSequence</span><span class="sxs-lookup"><span data-stu-id="a86ad-303">CreateSequence Exchange</span></span>  
 <span data-ttu-id="a86ad-304">El iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transmite un mensaje `CreateSequence` con un elemento `Offer` en una solicitud HTTP y espera el mensaje `CreateSequenceResponse` en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="a86ad-304">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="a86ad-305">El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] crea una secuencia y transmite el mensaje `CreateSequenceResponse` con un elemento `Accept` en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="a86ad-305">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element on the HTTP response.</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="a86ad-306">Mensaje unidireccional</span><span class="sxs-lookup"><span data-stu-id="a86ad-306">One-way Message</span></span>  
 <span data-ttu-id="a86ad-307">Para completar correctamente un intercambio de mensajes unidireccional, el iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transmite un mensaje de secuencia de solicitud en la solicitud HTTP y recibe un mensaje `SequenceAcknowledgement` independiente en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="a86ad-307">To complete a one-way message exchange successfully, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a request sequence message on the HTTP request and receives a standalone `SequenceAcknowledgement` message on the HTTP response.</span></span> <span data-ttu-id="a86ad-308">La `SequenceAcknowledgement` debe confirmar el mensaje transmitido.</span><span class="sxs-lookup"><span data-stu-id="a86ad-308">The `SequenceAcknowledgement` must acknowledge the message transmitted.</span></span>  
  
 <span data-ttu-id="a86ad-309">El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] puede responder a la solicitud con una confirmación, un error o una respuesta con un cuerpo vacío y un código de estado HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="a86ad-309">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder may reply to the request with an acknowledgement, a fault, or a response with an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="two-way-messages"></a><span data-ttu-id="a86ad-310">Mensajes bidireccionales</span><span class="sxs-lookup"><span data-stu-id="a86ad-310">Two Way Messages</span></span>  
 <span data-ttu-id="a86ad-311">Para completar correctamente un protocolo de intercambio de mensajes bidireccional, el iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transmite un mensaje de secuencia de solicitud en la solicitud HTTP y recibe un mensaje de secuencia de respuesta en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="a86ad-311">To complete a two way message exchange protocol successfully, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a request sequence message on the HTTP request and receives a reply sequence message on the HTTP response.</span></span> <span data-ttu-id="a86ad-312">La respuesta debe llevar una `SequenceAcknowledgement` que confirme que se ha transmitido el mensaje de secuencia de solicitud.</span><span class="sxs-lookup"><span data-stu-id="a86ad-312">The response must carry a `SequenceAcknowledgement` acknowledging the request sequence message transmitted.</span></span>  
  
 <span data-ttu-id="a86ad-313">El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] puede responder a la solicitud con una respuesta de la aplicación, un error o una respuesta con un cuerpo vacío y un código de estado HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="a86ad-313">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder may reply to the request with an application reply, a fault or a response with an empty body and HTTP 202 status code.</span></span>  
  
 <span data-ttu-id="a86ad-314">Debido a la presencia de mensajes unidireccionales y al control de tiempo de las respuestas de la aplicación, el número de secuencia del mensaje de secuencia de solicitud y el número de secuencia del mensaje de respuesta no tienen ninguna correlación.</span><span class="sxs-lookup"><span data-stu-id="a86ad-314">Because of the presence of one-way messages and the timing of application replies, the request sequence message’s sequence number and the response message’s sequence number have no correlation.</span></span>  
  
#### <a name="retrying-replies"></a><span data-ttu-id="a86ad-315">Reintento de respuestas</span><span class="sxs-lookup"><span data-stu-id="a86ad-315">Retrying Replies</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a86ad-316"> confía en la correlación de solicitud-respuesta HTTP para la correlación del protocolo de intercambio de mensajes bidireccional.</span><span class="sxs-lookup"><span data-stu-id="a86ad-316"> relies on HTTP request-reply correlation for two-way message exchange protocol correlation.</span></span> <span data-ttu-id="a86ad-317">Debido a esto, el iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no deja de reintentar un mensaje de secuencia de solicitud cuando se confirma el mensaje de secuencia de solicitud, sino cuando la respuesta HTTP lleva una `SequenceAcknowledgement`, una respuesta de la aplicación o error.</span><span class="sxs-lookup"><span data-stu-id="a86ad-317">Because of this, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator does not stop retrying a request sequence message when the request sequence message is acknowledged but rather when the HTTP response carries a `SequenceAcknowledgement`, application reply, or fault.</span></span> <span data-ttu-id="a86ad-318">El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] reintenta las respuestas en la respuesta HTTP de la solicitud con la que se correlaciona la respuesta.</span><span class="sxs-lookup"><span data-stu-id="a86ad-318">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder retries replies on the HTTP response of the request to which the reply is correlated.</span></span>  
  
#### <a name="closesequence-exchange"></a><span data-ttu-id="a86ad-319">Intercambio de CloseSequence</span><span class="sxs-lookup"><span data-stu-id="a86ad-319">CloseSequence Exchange</span></span>  
 <span data-ttu-id="a86ad-320">Después de recibir todos los mensajes de secuencia de respuesta y confirmaciones para todos los mensajes de secuencia de solicitud unidireccionales, el iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transmite un mensaje `CloseSequence` para la secuencia de la solicitud en una solicitud HTTP y espera la `CloseSequenceResponse` en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="a86ad-320">After receiving all reply sequence messages and acknowledgements for all one way request sequence messages, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CloseSequence` message for the request sequence on an HTTP request and expects the `CloseSequenceResponse` on the HTTP response.</span></span>  
  
 <span data-ttu-id="a86ad-321">Al cerrar implícitamente la secuencia de la solicitud, se cierra la secuencia de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="a86ad-321">Closing the request sequence implicitly closes the reply sequence.</span></span> <span data-ttu-id="a86ad-322">Esto significa que el iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] incluye la `SequenceAcknowledgement` final de la secuencia de respuesta en el mensaje `CloseSequence` y la secuencia de respuesta no tiene un intercambio de `CloseSequence`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-322">This means the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator includes the reply sequence’s Final `SequenceAcknowledgement` on the `CloseSequence` message and the reply sequence does not have a `CloseSequence` exchange.</span></span>  
  
 <span data-ttu-id="a86ad-323">El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] garantiza que todas las respuestas se confirmen y transmite el mensaje `CloseSequenceResponse` en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="a86ad-323">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures all replies are acknowledged and transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>  
  
#### <a name="terminatesequence-exchange"></a><span data-ttu-id="a86ad-324">Intercambio de TerminateSequence</span><span class="sxs-lookup"><span data-stu-id="a86ad-324">TerminateSequence Exchange</span></span>  
 <span data-ttu-id="a86ad-325">Después de recibir el mensaje `CloseSequenceResponse`, el iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transmite un mensaje `TerminateSequence` para la secuencia de la solicitud en una solicitud HTTP y espera la `TerminateSequenceResponse` en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="a86ad-325">After receiving the `CloseSequenceResponse` message, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `TerminateSequence` message for the request sequence on an HTTP request and expects the `TerminateSequenceResponse` on the HTTP response.</span></span>  
  
 <span data-ttu-id="a86ad-326">Al igual que en el intercambio de `CloseSequence`, al finalizar la secuencia de solicitud, se finaliza la secuencia de respuesta.</span><span class="sxs-lookup"><span data-stu-id="a86ad-326">Like the `CloseSequence` exchange, terminating the request sequence implicitly terminates the reply sequence.</span></span> <span data-ttu-id="a86ad-327">Esto significa que el iniciador de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] incluye la `SequenceAcknowledgement` final de la secuencia de respuesta en el mensaje `TerminateSequence` y la secuencia de respuesta no tiene un intercambio de `TerminateSequence`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-327">This means the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator includes the reply sequence’s final `SequenceAcknowledgement` on the `TerminateSequence` message and the reply sequence does not have a `TerminateSequence` exchange.</span></span>  
  
 <span data-ttu-id="a86ad-328">El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transmite el mensaje `TerminateSequenceResponse` en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="a86ad-328">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>  
  
### <a name="requestreply-addressable-initiator"></a><span data-ttu-id="a86ad-329">Iniciador direccionable de solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="a86ad-329">Request/Reply, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="a86ad-330">Enlaces</span><span class="sxs-lookup"><span data-stu-id="a86ad-330">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a86ad-331"> proporciona un patrón de intercambio de mensajes de solicitud-respuesta utilizando dos secuencias sobre un canal HTTP entrante y uno saliente.</span><span class="sxs-lookup"><span data-stu-id="a86ad-331"> provides a request-reply message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="a86ad-332">Este patrón de intercambio de mensajes se puede mezclar con el patrón de intercambio de mensajes del iniciador de `Duplex, Addressable` de una manera limitada.</span><span class="sxs-lookup"><span data-stu-id="a86ad-332">This message exchange pattern can be mixed with the `Duplex, Addressable` Initiator message exchange pattern in a limited way.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a86ad-333"> usa las solicitudes HTTP para transmitir todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="a86ad-333"> uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="a86ad-334">Todas las respuestas HTTP tienen un cuerpo vacío y código de estado HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="a86ad-334">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="a86ad-335">Intercambio de CreateSequence</span><span class="sxs-lookup"><span data-stu-id="a86ad-335">CreateSequence Exchange</span></span>  
 <span data-ttu-id="a86ad-336">El iniciador [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transmite un mensaje `CreateSequence` con un elemento `Offer` en una solicitud HTTP.</span><span class="sxs-lookup"><span data-stu-id="a86ad-336">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="a86ad-337">El respondedor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] asegura que la `CreateSequence` tiene un elemento `Offer`, a continuación, crea una secuencia y transmite el mensaje `CreateSequenceResponse` con un elemento `Accept`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-337">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has an `Offer` element then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>  
  
#### <a name="requestreply-correlation"></a><span data-ttu-id="a86ad-338">Correlación entre solicitud y respuesta</span><span class="sxs-lookup"><span data-stu-id="a86ad-338">Request/Reply Correlation</span></span>  
 <span data-ttu-id="a86ad-339">Lo siguiente se aplica a todas las solicitudes y respuestas correlacionadas:</span><span class="sxs-lookup"><span data-stu-id="a86ad-339">The following applies to all correlated requests and replies:</span></span>  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a86ad-340"> garantiza que todos los mensajes de solicitud de la aplicación llevan una referencia de extremo `ReplyTo` y un `MessageId`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-340"> ensures all application request messages bear a `ReplyTo` endpoint reference and a `MessageId`.</span></span>  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a86ad-341"> aplica la referencia del extremo local como cada `ReplyTo` de mensaje de solicitud de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a86ad-341"> applies the local endpoint reference as each application request message’s `ReplyTo`.</span></span> <span data-ttu-id="a86ad-342">La referencia del extremo local es la `CreateSequence` del mensaje `ReplyTo` para el iniciador y la `CreateSequence` del mensaje `To` para el respondedor.</span><span class="sxs-lookup"><span data-stu-id="a86ad-342">The local endpoint reference is the `CreateSequence` message’s `ReplyTo` for the Initiator and the `CreateSequence` message’s `To` for the Responder.</span></span>  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a86ad-343"> garantiza que los mensajes de solicitud entrantes lleven un `MessageId` y una `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-343"> ensures that incoming request messages bear a `MessageId` and a `ReplyTo`.</span></span>  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a86ad-344"> garantiza que el URI de la referencia de extremo `ReplyTo` de todos los mensajes de solicitud de aplicaciones coinciden con la referencia del extremo local tal y como se definió anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a86ad-344"> ensures the `ReplyTo` endpoint reference’s URI of all application request messages match the local endpoint reference as defined earlier.</span></span>  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a86ad-345"> garantiza que todas las respuestas llevan los encabezados `RelatesTo` y `To` correctos que siguen las reglas de correlación de solicitud/respuesta de `wsa`.</span><span class="sxs-lookup"><span data-stu-id="a86ad-345"> ensures that all replies bear the correct `RelatesTo` and `To` headers following `wsa` request/reply correlation rules.</span></span>
