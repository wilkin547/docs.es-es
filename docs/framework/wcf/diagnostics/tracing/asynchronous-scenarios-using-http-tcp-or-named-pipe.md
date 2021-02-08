---
description: 'Más información sobre: escenarios asincrónicos con HTTP, TCP o Named-Pipe'
title: Escenarios asincrónicos en los que se usa HTTP, TCP o canalizaciones con nombre
ms.date: 03/30/2017
ms.assetid: a4d62402-43a4-48a4-9ced-220633ebc4ce
ms.openlocfilehash: 5e01866cd20d63796741a097a6d7d774ea45d3d9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99770955"
---
# <a name="asynchronous-scenarios-using-http-tcp-or-named-pipe"></a><span data-ttu-id="e6ef3-103">Escenarios asincrónicos en los que se usa HTTP, TCP o canalizaciones con nombre</span><span class="sxs-lookup"><span data-stu-id="e6ef3-103">Asynchronous Scenarios using HTTP, TCP, or Named-Pipe</span></span>

<span data-ttu-id="e6ef3-104">En este tema se describen las actividades y transferencias para diferentes escenarios asincrónicos de solicitud-respuesta, con solicitudes de varios subprocesos, utilizando HTTP, TCP o canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="e6ef3-104">This topic describes the activities and transfers for different asynchronous request/reply scenarios, with multithreaded requests using HTTP, TCP, or named pipe.</span></span>  
  
## <a name="asynchronous-requestreply-without-errors"></a><span data-ttu-id="e6ef3-105">Solicitud-respuesta asincrónica sin errores</span><span class="sxs-lookup"><span data-stu-id="e6ef3-105">Asynchronous Request/Reply without Errors</span></span>  

 <span data-ttu-id="e6ef3-106">En esta sección se describen las actividades y transferencias para un escenario asincrónico de solicitud-respuesta válido, con clientes de varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="e6ef3-106">This section describes the activities and transfers for an asynchronous request/reply scenario, with multithreaded clients.</span></span>  
  
 <span data-ttu-id="e6ef3-107">La actividad de llamador finaliza cuando `beginCall` vuelve, y `endCall` vuelve.</span><span class="sxs-lookup"><span data-stu-id="e6ef3-107">The caller activity terminates when `beginCall` returns, and `endCall` returns.</span></span> <span data-ttu-id="e6ef3-108">Si se llama a una devolución de llamada, la devolución de llamada vuelve.</span><span class="sxs-lookup"><span data-stu-id="e6ef3-108">If a callback is called, the callback returns.</span></span>  
  
 <span data-ttu-id="e6ef3-109">La actividad llamada finaliza cuando `beginCall` vuelve, `endCall` vuelve o cuando la devolución de llamada vuelve si fue llamada desde esa actividad.</span><span class="sxs-lookup"><span data-stu-id="e6ef3-109">The called activity terminates when `beginCall` returns, `endCall` returns, or when the callback returns if it was called from that activity.</span></span>  
  
### <a name="asynchronous-client-without-callback"></a><span data-ttu-id="e6ef3-110">Cliente asincrónico sin devolución de llamada</span><span class="sxs-lookup"><span data-stu-id="e6ef3-110">Asynchronous Client without Callback</span></span>  
  
#### <a name="propagation-is-enabled-on-both-sides-using-http"></a><span data-ttu-id="e6ef3-111">La propagación está habilitada en ambos lados, utilizando HTTP</span><span class="sxs-lookup"><span data-stu-id="e6ef3-111">Propagation is Enabled on Both Sides, using HTTP</span></span>  

 ![Cliente asincrónico sin devolución de llamada en la que propagateActivity está establecido en true en ambos lados.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-no-callback.gif)
  
 <span data-ttu-id="e6ef3-113">Si `propagateActivity=true` , ProcessMessage indica a qué actividad de ProcessAction se va a transferir.</span><span class="sxs-lookup"><span data-stu-id="e6ef3-113">If `propagateActivity=true`, ProcessMessage indicates which ProcessAction activity to transfer to.</span></span>  
  
 <span data-ttu-id="e6ef3-114">Para los escenarios basados en HTTP, ReceiveBytes se invoca en el primer mensaje para enviar y existe para la duración de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="e6ef3-114">For HTTP-based scenarios, ReceiveBytes is invoked on the first message to send, and exists for the lifetime of the request.</span></span>  
  
#### <a name="propagation-is-disabled-on-either-sides-using-http"></a><span data-ttu-id="e6ef3-115">La propagación está deshabilitada en cualquier lado, utilizando HTTP</span><span class="sxs-lookup"><span data-stu-id="e6ef3-115">Propagation is Disabled on Either Sides, using HTTP</span></span>  

 <span data-ttu-id="e6ef3-116">Si `propagateActivity=false` en cualquier lado, ProcessMessage no indica a qué actividad de ProcessAction se va a transferir.</span><span class="sxs-lookup"><span data-stu-id="e6ef3-116">If `propagateActivity=false` on either side, ProcessMessage does not indicate which ProcessAction activity to transfer to.</span></span> <span data-ttu-id="e6ef3-117">Por consiguiente, se invoca una nueva actividad ProcessAction temporal con un nuevo id.</span><span class="sxs-lookup"><span data-stu-id="e6ef3-117">Therefore, a new temporary ProcessAction activity with a new ID is invoked.</span></span> <span data-ttu-id="e6ef3-118">Cuando la respuesta asincrónica coincide con la solicitud en el código ServiceModel, el id. de actividad se puede recuperar del contexto local.</span><span class="sxs-lookup"><span data-stu-id="e6ef3-118">When the asynchronous response is matched to the request in ServiceModel code, the Activity ID can be retrieved from the local context.</span></span> <span data-ttu-id="e6ef3-119">La actividad ProcessAction actual se puede transferir a con ese id.</span><span class="sxs-lookup"><span data-stu-id="e6ef3-119">The actual ProcessAction activity can be transferred to with that ID.</span></span>  
  
 ![Cliente asincrónico sin devolución de llamada en la que propagateActivity está establecido en false en cualquier lado.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-disabled-either-side.gif)  

 <span data-ttu-id="e6ef3-121">Para los escenarios basados en HTTP, ReceiveBytes se invoca en el primer mensaje para enviar y existe para la duración de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="e6ef3-121">For HTTP-based scenarios, ReceiveBytes is invoked on the first message to send, and exists for the lifetime of the request.</span></span>  
  
 <span data-ttu-id="e6ef3-122">Una actividad procesar acción se crea en un cliente asincrónico en `propagateActivity=false` el llamador o destinatario y cuando el mensaje de respuesta no incluye un encabezado de acción.</span><span class="sxs-lookup"><span data-stu-id="e6ef3-122">A Process Action activity is created on an asynchronous client when `propagateActivity=false` at the caller or callee, and when the response message does not include an Action header.</span></span>  
  
#### <a name="propagation-is-enabled-on-both-sides-using-tcp-or-named-pipe"></a><span data-ttu-id="e6ef3-123">La propagación está habilitada en ambos lados, utilizando TCP o canalización con nombre</span><span class="sxs-lookup"><span data-stu-id="e6ef3-123">Propagation is Enabled on Both Sides, using TCP or Named Pipe</span></span>  

 ![Cliente asincrónico sin devolución de llamada en la que propagateActivity está establecido en true en ambos lados y con nombre Pipe/TCP.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-enabled-using-tcp.gif)  
  
 <span data-ttu-id="e6ef3-125">Para una canalización con nombre o escenario basado en TCP, ReceiveBytes se invoca cuando se abre el cliente, y existe para la duración de la conexión.</span><span class="sxs-lookup"><span data-stu-id="e6ef3-125">For a Named-Pipe or TCP-based scenario, ReceiveBytes is invoked when the client is opened, and exists for the lifetime of the connection.</span></span>  
  
 <span data-ttu-id="e6ef3-126">Similar a la primera imagen, si `propagateActivity=true` , ProcessMessage indica a qué actividad de ProcessAction se va a transferir.</span><span class="sxs-lookup"><span data-stu-id="e6ef3-126">Similar to the first image, if `propagateActivity=true`, ProcessMessage indicates which ProcessAction activity to transfer to.</span></span>  
  
#### <a name="propagation-is-disabled-on-either-sides-using-tcp-or-named-pipe"></a><span data-ttu-id="e6ef3-127">La propagación está deshabilitada en cualquier lado, utilizando TCP o canalización con nombre</span><span class="sxs-lookup"><span data-stu-id="e6ef3-127">Propagation is Disabled on Either Sides, using TCP or Named Pipe</span></span>  

 <span data-ttu-id="e6ef3-128">Para una canalización con nombre o escenario basado en TCP, ReceiveBytes se invoca cuando se abre el cliente, y existe para la duración de la conexión.</span><span class="sxs-lookup"><span data-stu-id="e6ef3-128">For a Named-Pipe or TCP-based scenario, ReceiveBytes is invoked when the client is opened, and exists for the lifetime of the connection.</span></span>  
  
 <span data-ttu-id="e6ef3-129">De forma similar a la segunda imagen, si se `propagateActivity=false` encuentra en cualquier lado, ProcessMessage no indica a qué actividad de ProcessAction se va a transferir.</span><span class="sxs-lookup"><span data-stu-id="e6ef3-129">Similar to the second image, if `propagateActivity=false` on either side, ProcessMessage does not indicate which ProcessAction activity to transfer to.</span></span> <span data-ttu-id="e6ef3-130">Por consiguiente, se invoca una nueva actividad ProcessAction temporal con un nuevo id.</span><span class="sxs-lookup"><span data-stu-id="e6ef3-130">Therefore, a new temporary ProcessAction activity with a new ID is invoked.</span></span> <span data-ttu-id="e6ef3-131">Cuando la respuesta asincrónica coincide con la solicitud en el código ServiceModel, el id. de actividad se puede recuperar del contexto local.</span><span class="sxs-lookup"><span data-stu-id="e6ef3-131">When the asynchronous response is matched to the request in ServiceModel code, the Activity ID can be retrieved from the local context.</span></span> <span data-ttu-id="e6ef3-132">La actividad ProcessAction actual se puede transferir a con ese id.</span><span class="sxs-lookup"><span data-stu-id="e6ef3-132">The actual ProcessAction activity can be transferred to with that ID.</span></span>  
  
 ![Cliente asincrónico sin devolución de llamada en la que propagateActivity está establecido en false en cualquier lado y canalización con nombre/TCP.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-disabled-using-tcp.gif)  

### <a name="asynchronous-client-with-callback"></a><span data-ttu-id="e6ef3-134">Cliente asincrónico con devolución de llamada</span><span class="sxs-lookup"><span data-stu-id="e6ef3-134">Asynchronous client with Callback</span></span>  

 <span data-ttu-id="e6ef3-135">Este escenario agrega las actividades G y A', para la devolución de llamada y `endCall`y sus transferencias dentro/fuera.</span><span class="sxs-lookup"><span data-stu-id="e6ef3-135">This scenario adds activities G and A’, for the callback and `endCall`, and their transfers in/out.</span></span>  
  
 <span data-ttu-id="e6ef3-136">En esta sección solo se muestra el uso de HTTP con `propagateActivity` = `true` .</span><span class="sxs-lookup"><span data-stu-id="e6ef3-136">This section only demonstrates using HTTP with `propagateActivity`=`true`.</span></span> <span data-ttu-id="e6ef3-137">Sin embargo, las actividades y transferencias adicionales también se aplican a los otros casos (es decir, `propagateActivity` = `false` mediante TCP o canalizaciones con nombre).</span><span class="sxs-lookup"><span data-stu-id="e6ef3-137">However, the additional activities and transfers also apply to the other cases (that is, `propagateActivity`=`false`, using TCP or Named-Pipe).</span></span>  
  
 <span data-ttu-id="e6ef3-138">La devolución de llamada crea una nueva actividad (G) cuando el cliente llama al código de usuario para notificar que los resultados están listos.</span><span class="sxs-lookup"><span data-stu-id="e6ef3-138">The callback creates a new activity (G) when the client calls user code to notify that results are ready.</span></span> <span data-ttu-id="e6ef3-139">A continuación, el código de usuario llama a `endCall` dentro de la devolución de llamada (como se muestra en la figura 5) o fuera de la devolución de llamada (figura 6).</span><span class="sxs-lookup"><span data-stu-id="e6ef3-139">User code then calls `endCall` within the callback (as shown in Figure 5) or outside the callback (Figure 6).</span></span> <span data-ttu-id="e6ef3-140">Dado que no se sabe a qué actividad `endCall` de usuario se está llamando, esta actividad se etiqueta `A’` .</span><span class="sxs-lookup"><span data-stu-id="e6ef3-140">Because it is not known which user activity `endCall` is being called from, this activity is labeled `A’`.</span></span> <span data-ttu-id="e6ef3-141">Es posible que A' puede ser idéntico o diferente de A.</span><span class="sxs-lookup"><span data-stu-id="e6ef3-141">It is possible that A’ can be identical to or different from A.</span></span>  
  
 ![Muestra un cliente asincrónico con devolución de llamada, endcall en devolución de llamada.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-callback-endcall-in-callback.gif)  

 ![Muestra un cliente asincrónico con devolución de llamada, endcall fuera de la devolución de llamada.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-callback-endcall-outside-callback.gif)  

### <a name="asynchronous-server-with-callback"></a><span data-ttu-id="e6ef3-144">Servidor asincrónico con devolución de llamada</span><span class="sxs-lookup"><span data-stu-id="e6ef3-144">Asynchronous Server with Callback</span></span>  

 ![Muestra un servidor asincrónico con devolución de llamada.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-server-callback.gif)  

 <span data-ttu-id="e6ef3-146">La pila del canal llama al cliente al recibir el mensaje: las trazas para este procesamiento se emiten en la propia actividad ProcessRequest.</span><span class="sxs-lookup"><span data-stu-id="e6ef3-146">The channel stack calls back the client on Message Receive: traces for this processing are emitted in the ProcessRequest activity itself.</span></span>  
  
## <a name="asynchronous-requestreply-with-errors"></a><span data-ttu-id="e6ef3-147">Solicitud-respuesta asincrónica con errores</span><span class="sxs-lookup"><span data-stu-id="e6ef3-147">Asynchronous Request/Reply with Errors</span></span>  

 <span data-ttu-id="e6ef3-148">Los errores del mensaje de error se reciben durante `endCall`.</span><span class="sxs-lookup"><span data-stu-id="e6ef3-148">Fault message errors are received during `endCall`.</span></span> <span data-ttu-id="e6ef3-149">De lo contrario, las actividades y transferencias son similares a los escenarios anteriores.</span><span class="sxs-lookup"><span data-stu-id="e6ef3-149">Otherwise, activities and transfers are similar to previous scenarios.</span></span>  
  
## <a name="asynchronous-one-way-with-or-without-errors"></a><span data-ttu-id="e6ef3-150">Unidireccional asincrónico con o sin errores</span><span class="sxs-lookup"><span data-stu-id="e6ef3-150">Asynchronous One-Way with or without Errors</span></span>  

 <span data-ttu-id="e6ef3-151">No se devuelve ninguna respuesta o error al cliente.</span><span class="sxs-lookup"><span data-stu-id="e6ef3-151">No response or fault is returned to the client.</span></span>
