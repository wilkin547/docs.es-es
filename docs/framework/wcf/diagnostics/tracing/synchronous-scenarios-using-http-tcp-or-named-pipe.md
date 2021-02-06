---
description: 'Más información acerca de: escenarios sincrónicos con HTTP, TCP o Named-Pipe'
title: Escenarios sincrónicos en los que se utiliza HTTP, TCP o canalizaciones con nombre
ms.date: 03/30/2017
ms.assetid: 7e90af1b-f8f6-41b9-a63a-8490ada502b1
ms.openlocfilehash: fd6605be99a9419de27f000b378720adf0ae1a14
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99635420"
---
# <a name="synchronous-scenarios-using-http-tcp-or-named-pipe"></a><span data-ttu-id="def70-103">Escenarios sincrónicos en los que se utiliza HTTP, TCP o canalizaciones con nombre</span><span class="sxs-lookup"><span data-stu-id="def70-103">Synchronous Scenarios using HTTP, TCP or Named-Pipe</span></span>

<span data-ttu-id="def70-104">En este tema se describen las actividades y transferencias para diferentes escenarios sincrónicos de solicitud/respuesta, con un cliente de un único subproceso, utilizando HTTP, TCP o canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="def70-104">This topic describes the activities and transfers for different synchronous request/reply scenarios, with a single-threaded client, using HTTP, TCP or named pipe.</span></span> <span data-ttu-id="def70-105">Vea [escenarios asincrónicos mediante http, TCP o canalizaciones con nombre](asynchronous-scenarios-using-http-tcp-or-named-pipe.md) para obtener más información sobre las solicitudes multiproceso.</span><span class="sxs-lookup"><span data-stu-id="def70-105">See [Asynchronous Scenarios using HTTP, TCP, or Named-Pipe](asynchronous-scenarios-using-http-tcp-or-named-pipe.md) for more information on multi-threaded requests.</span></span>  
  
## <a name="synchronous-requestreply-without-errors"></a><span data-ttu-id="def70-106">Solicitud/respuesta sincrónica sin errores</span><span class="sxs-lookup"><span data-stu-id="def70-106">Synchronous Request/Reply without Errors</span></span>  

 <span data-ttu-id="def70-107">En esta sección se describen las actividades y transferencias para un escenario válido sincrónico de solicitud/respuesta, con cliente de un único subproceso.</span><span class="sxs-lookup"><span data-stu-id="def70-107">This section describes the activities and transfers for a valid synchronous request/reply scenario, with single-threaded client.</span></span>  
  
### <a name="client"></a><span data-ttu-id="def70-108">Cliente</span><span class="sxs-lookup"><span data-stu-id="def70-108">Client</span></span>  
  
#### <a name="establishing-communication-with-service-endpoint"></a><span data-ttu-id="def70-109">Establecer la comunicación con el punto de conexión de servicio</span><span class="sxs-lookup"><span data-stu-id="def70-109">Establishing Communication with Service Endpoint</span></span>  

 <span data-ttu-id="def70-110">Un cliente se construye y se abre.</span><span class="sxs-lookup"><span data-stu-id="def70-110">A client is constructed and opened.</span></span> <span data-ttu-id="def70-111">Para cada uno de estos pasos, la actividad ambiente (A) se transfiere a una actividad "construir cliente" (B) y "abrir cliente" (C), respectivamente.</span><span class="sxs-lookup"><span data-stu-id="def70-111">For each of these steps, the ambient activity (A) is transferred to a "Construct Client" (B) and "Open Client" (C) activity respectively.</span></span> <span data-ttu-id="def70-112">Por cada actividad a la que se transfiere, la actividad ambiente se suspende hasta que se devuelve una transferencia, es decir, hasta que se ejecuta el código de ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="def70-112">For each activity being transferred to, the ambient activity is suspended until there is a transfer back, that is, until ServiceModel code is executed.</span></span>  
  
#### <a name="making-a-request-to-service-endpoint"></a><span data-ttu-id="def70-113">Realizar una solicitud al extremo de servicio</span><span class="sxs-lookup"><span data-stu-id="def70-113">Making a Request to Service Endpoint</span></span>  

 <span data-ttu-id="def70-114">La actividad ambiente se transfiere a una actividad "ProcessAction" (D).</span><span class="sxs-lookup"><span data-stu-id="def70-114">The ambient activity is transferred to a "ProcessAction" (D) activity.</span></span> <span data-ttu-id="def70-115">Dentro de esta actividad, se envía un mensaje de solicitud y se recibe un mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="def70-115">Within this activity, a request message is sent, and a response message is received.</span></span> <span data-ttu-id="def70-116">La actividad finaliza cuando el control vuelve al código de usuario.</span><span class="sxs-lookup"><span data-stu-id="def70-116">The activity ends when control returns to user code.</span></span> <span data-ttu-id="def70-117">Dado que se trata de una solicitud sincrónica, la actividad ambiente se suspende hasta que el control vuelve.</span><span class="sxs-lookup"><span data-stu-id="def70-117">Because this is a synchronous request, the ambient activity suspends until control returns.</span></span>  
  
#### <a name="closing-communication-with-service-endpoint"></a><span data-ttu-id="def70-118">Cerrar la comunicación con el punto de conexión de servicio</span><span class="sxs-lookup"><span data-stu-id="def70-118">Closing Communication with Service Endpoint</span></span>  

 <span data-ttu-id="def70-119">La actividad de cierre (I) del cliente se crea a partir de la actividad ambiente.</span><span class="sxs-lookup"><span data-stu-id="def70-119">The client's close activity (I) is created from the ambient activity.</span></span> <span data-ttu-id="def70-120">Esto es idéntico a nuevo y abrir.</span><span class="sxs-lookup"><span data-stu-id="def70-120">This is identical to new and open.</span></span>  
  
### <a name="server"></a><span data-ttu-id="def70-121">Servidor</span><span class="sxs-lookup"><span data-stu-id="def70-121">Server</span></span>  
  
#### <a name="setting-up-a-service-host"></a><span data-ttu-id="def70-122">Configurar un host de servicio</span><span class="sxs-lookup"><span data-stu-id="def70-122">Setting up a Service Host</span></span>  

 <span data-ttu-id="def70-123">Las actividades nuevas y de abrir (N y O) del ServiceHost se crean a partir de la actividad ambiente (M).</span><span class="sxs-lookup"><span data-stu-id="def70-123">The ServiceHost’s new and open activities (N and O) are created from the ambient activity (M).</span></span>  
  
 <span data-ttu-id="def70-124">Una actividad de escucha (P) se crea abriendo un ServiceHost para cada escucha.</span><span class="sxs-lookup"><span data-stu-id="def70-124">A listener activity (P) is created from opening a ServiceHost for each listener.</span></span> <span data-ttu-id="def70-125">La actividad de la escucha espera a recibir y procesar los datos.</span><span class="sxs-lookup"><span data-stu-id="def70-125">The listener activity waits to receive and process data.</span></span>  
  
#### <a name="receiving-data-on-the-wire"></a><span data-ttu-id="def70-126">Recibir los datos en la conexión</span><span class="sxs-lookup"><span data-stu-id="def70-126">Receiving Data on the Wire</span></span>  

 <span data-ttu-id="def70-127">Cuando los datos llegan en la conexión, se crea una actividad "ReceiveBytes" Si aún no existe (Q) para procesar los datos recibidos.</span><span class="sxs-lookup"><span data-stu-id="def70-127">When data arrives on the wire, a "ReceiveBytes" activity is created if it does not already exist (Q) to process the received data.</span></span> <span data-ttu-id="def70-128">Esta actividad se puede reutilizar para varios mensajes dentro de una conexión o cola.</span><span class="sxs-lookup"><span data-stu-id="def70-128">This activity can be reused for multiple messages within a connection or queue.</span></span>  
  
 <span data-ttu-id="def70-129">La actividad ReceiveBytes inicia una actividad ProcessMessage (R) si tiene bastantes datos para formar un mensaje de acción SOAP.</span><span class="sxs-lookup"><span data-stu-id="def70-129">The ReceiveBytes activity launches a ProcessMessage activity (R) if it has enough data to form a SOAP action message.</span></span>  
  
 <span data-ttu-id="def70-130">En actividad R, se procesan los encabezados del mensaje y se comprueba el encabezado de activityID.</span><span class="sxs-lookup"><span data-stu-id="def70-130">In activity R, the message headers are processed, and the activityID header is verified.</span></span> <span data-ttu-id="def70-131">Si este encabezado está presente, el id. de actividad se establece en la actividad ProcessAction; de lo contrario, se crea un nuevo id.</span><span class="sxs-lookup"><span data-stu-id="def70-131">If this header is present, the activity ID is set to the ProcessAction activity; otherwise, a new ID is created.</span></span>  
  
 <span data-ttu-id="def70-132">Se crea la actividad ProcessAction (S) y se transfiere cuando se procesa la llamada.</span><span class="sxs-lookup"><span data-stu-id="def70-132">ProcessAction activity (S) is created and being transferred to, when the call is processed.</span></span> <span data-ttu-id="def70-133">Esta actividad finaliza cuando todo el procesamiento relacionado con el mensaje entrante se completa, incluidos la ejecución del código de usuario (T) y el envío del mensaje de respuesta si es aplicable.</span><span class="sxs-lookup"><span data-stu-id="def70-133">This activity ends when all processing related to the incoming message is completed, including executing user code (T) and sending the response message if applicable.</span></span>  
  
#### <a name="closing-a-service-host"></a><span data-ttu-id="def70-134">Cerrar un host de servicio</span><span class="sxs-lookup"><span data-stu-id="def70-134">Closing a Service Host</span></span>  

 <span data-ttu-id="def70-135">La actividad de cierre del ServiceHost (Z) se crea a partir de la actividad ambiente.</span><span class="sxs-lookup"><span data-stu-id="def70-135">The ServiceHost’s close activity (Z) is created from the ambient activity.</span></span>  
  
 ![Diagrama que muestra escenarios sincrónicos: HTTP, TCP o canalizaciones con nombre.](./media/synchronous-scenarios-using-http-tcp-or-named-pipe/synchronous-scenario-http-tcp-named-pipes.gif)  
  
 <span data-ttu-id="def70-137">En \<A: name> , `A` es un símbolo de acceso directo que describe la actividad en el texto anterior y en la tabla 3.</span><span class="sxs-lookup"><span data-stu-id="def70-137">In \<A: name>, `A` is a shortcut symbol that describes the activity in the previous text and in table 3.</span></span> <span data-ttu-id="def70-138">`Name` es un nombre abreviado de la actividad.</span><span class="sxs-lookup"><span data-stu-id="def70-138">`Name` is a shortened name of the activity.</span></span>  
  
 <span data-ttu-id="def70-139">Si es `propagateActivity` = `true` , la acción procesar en el cliente y el servicio tienen el mismo identificador de actividad.</span><span class="sxs-lookup"><span data-stu-id="def70-139">If `propagateActivity`=`true`, Process Action on both the client and service have the same activity ID.</span></span>  
  
## <a name="synchronous-requestreply-with-errors"></a><span data-ttu-id="def70-140">Solicitud/respuesta sincrónica con Errores</span><span class="sxs-lookup"><span data-stu-id="def70-140">Synchronous Request/Reply with Errors</span></span>  

 <span data-ttu-id="def70-141">La única diferencia con el escenario anterior es que un mensaje de error SOAP se devuelve como un mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="def70-141">The only difference with the previous scenario is that a SOAP fault message is returned as a response message.</span></span> <span data-ttu-id="def70-142">Si `propagateActivity` = `true` es, se agrega el ID. de actividad del mensaje de solicitud al mensaje de error de SOAP.</span><span class="sxs-lookup"><span data-stu-id="def70-142">If `propagateActivity`=`true`, the activity ID of the request message is added to the SOAP fault message.</span></span>  
  
## <a name="synchronous-one-way-without-errors"></a><span data-ttu-id="def70-143">Unidireccional sincrónico sin errores</span><span class="sxs-lookup"><span data-stu-id="def70-143">Synchronous One-Way without Errors</span></span>  

 <span data-ttu-id="def70-144">La única diferencia con el primer escenario es que ningún mensaje se devuelve al servidor.</span><span class="sxs-lookup"><span data-stu-id="def70-144">The only difference with the first scenario is that no message is returned to the server.</span></span> <span data-ttu-id="def70-145">Para los protocolos basados en HTTP, un estado (valid o error) se devuelve todavía al cliente.</span><span class="sxs-lookup"><span data-stu-id="def70-145">For HTTP-based protocols, a status (valid or error) is still returned to the client.</span></span> <span data-ttu-id="def70-146">Esto se debe a que HTTP es el único protocolo con una semántica de solicitud-respuesta que forma parte de la pila del protocolo WCF.</span><span class="sxs-lookup"><span data-stu-id="def70-146">This is because HTTP is the only protocol with a request-response semantics that is part of the WCF protocol stack.</span></span> <span data-ttu-id="def70-147">Dado que el procesamiento de TCP está oculto en WCF, no se envía ninguna confirmación al cliente.</span><span class="sxs-lookup"><span data-stu-id="def70-147">Because TCP processing is hidden from WCF, no acknowledgement is sent to the client.</span></span>  
  
## <a name="synchronous-one-way-with-errors"></a><span data-ttu-id="def70-148">Unidireccional sincrónico con errores</span><span class="sxs-lookup"><span data-stu-id="def70-148">Synchronous One-Way with Errors</span></span>  

 <span data-ttu-id="def70-149">Si un error se produce procesando el mensaje (Q o más allá), ninguna notificación se devuelve al cliente.</span><span class="sxs-lookup"><span data-stu-id="def70-149">If an error occurs while processing the message (Q or beyond), no notification is returned to the client.</span></span> <span data-ttu-id="def70-150">Esto es idéntico al escenario "Unidireccional sincrónico sin errores".</span><span class="sxs-lookup"><span data-stu-id="def70-150">This is identical to the "Synchronous One-Way without Errors" scenario.</span></span> <span data-ttu-id="def70-151">No debería utilizar un escenario unidireccional si desea recibir un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="def70-151">You should not use a One-Way scenario if you want to receive an error message.</span></span>  
  
## <a name="duplex"></a><span data-ttu-id="def70-152">Dúplex</span><span class="sxs-lookup"><span data-stu-id="def70-152">Duplex</span></span>  

 <span data-ttu-id="def70-153">La diferencia con los escenarios anteriores es que el cliente actúa como un servicio, en el que crea las actividades ReceiveBytes y ProcessMessage, similares a los escenarios asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="def70-153">The difference with the previous scenarios is that the client acts as a service, in which it creates the ReceiveBytes and ProcessMessage activities, similar to the Asynchronous scenarios.</span></span>
