---
description: Más información acerca de cómo controlar excepciones y errores
title: Administración de excepciones y errores
ms.date: 03/30/2017
ms.assetid: a64d01c6-f221-4f58-93e5-da4e87a5682e
ms.openlocfilehash: 9851d63705ba8b28819b11e3893bcd6b019d565d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99735080"
---
# <a name="handling-exceptions-and-faults"></a><span data-ttu-id="ff783-103">Administración de excepciones y errores</span><span class="sxs-lookup"><span data-stu-id="ff783-103">Handling Exceptions and Faults</span></span>

<span data-ttu-id="ff783-104">Las excepciones se utilizan para comunicar localmente los errores dentro del servicio o la implementación del cliente.</span><span class="sxs-lookup"><span data-stu-id="ff783-104">Exceptions are used to communicate errors locally within the service or the client implementation.</span></span> <span data-ttu-id="ff783-105">Los errores, por otro lado, se utilizan para comunicar los errores en los límites del servicio, como del servidor al cliente o viceversa.</span><span class="sxs-lookup"><span data-stu-id="ff783-105">Faults, on the other hand, are used to communicate errors across service boundaries, such as from the server to the client or vice versa.</span></span> <span data-ttu-id="ff783-106">Además de los errores, los canales de transporte utilizan a menudo mecanismos específicos del transporte para comunicar los errores del nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="ff783-106">In addition to faults, transport channels often use transport-specific mechanisms to communicate transport-level errors.</span></span> <span data-ttu-id="ff783-107">Por ejemplo, el transporte HTTP utiliza códigos de estado como 404 para comunicar una dirección URL del extremo no existente (no hay ningún extremo para devolver un error).</span><span class="sxs-lookup"><span data-stu-id="ff783-107">For example, HTTP transport uses status codes such as 404 to communicate a non-existing endpoint URL (there is no endpoint to send back a fault).</span></span> <span data-ttu-id="ff783-108">Este documento se compone de tres secciones que proporcionan una guía a los autores del canal personalizado.</span><span class="sxs-lookup"><span data-stu-id="ff783-108">This document consists of three sections that provide guidance to custom channel authors.</span></span> <span data-ttu-id="ff783-109">La primera sección proporciona una guía sobre cuándo y cómo definir y producir las excepciones.</span><span class="sxs-lookup"><span data-stu-id="ff783-109">The first section provides guidance on when and how to define and throw exceptions.</span></span> <span data-ttu-id="ff783-110">La segunda sección proporciona una guía sobre la generación y utilización de errores.</span><span class="sxs-lookup"><span data-stu-id="ff783-110">The second section provides guidance around generating and consuming faults.</span></span> <span data-ttu-id="ff783-111">La tercera sección explica cómo proporcionar información de seguimiento para ayudar al usuario de su canal personalizado a solucionar problemas de las aplicaciones en ejecución.</span><span class="sxs-lookup"><span data-stu-id="ff783-111">The third section explains how to provide trace information to aid the user of your custom channel in troubleshooting running applications.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="ff783-112">Excepciones</span><span class="sxs-lookup"><span data-stu-id="ff783-112">Exceptions</span></span>  

 <span data-ttu-id="ff783-113">Hay dos cosas que deben tenerse presente al producir una excepción: primero tiene que ser de un tipo que permite a los usuarios escribir código correcto que pueda reaccionar apropiadamente a la excepción.</span><span class="sxs-lookup"><span data-stu-id="ff783-113">There are two things to keep in mind when throwing an exception: First it has to be of a type that allows users to write correct code that can react appropriately to the exception.</span></span> <span data-ttu-id="ff783-114">Segundo, tiene que proporcionar suficiente información para que el usuario entienda qué salió mal, el impacto del error, y cómo corregirlo.</span><span class="sxs-lookup"><span data-stu-id="ff783-114">Second, it has to provide enough information for the user to understand what went wrong, the failure impact, and how to fix it.</span></span> <span data-ttu-id="ff783-115">En las secciones siguientes se proporcionan instrucciones sobre los tipos de excepción y los mensajes para los canales Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="ff783-115">The following sections give guidance around exception types and messages for Windows Communication Foundation (WCF) channels.</span></span> <span data-ttu-id="ff783-116">También hay una guía general sobre las excepciones en .NET en el documento Instrucciones de diseño para excepciones.</span><span class="sxs-lookup"><span data-stu-id="ff783-116">There is also general guidance around exceptions in .NET in the Design Guidelines for Exceptions document.</span></span>  
  
### <a name="exception-types"></a><span data-ttu-id="ff783-117">Tipos de excepción</span><span class="sxs-lookup"><span data-stu-id="ff783-117">Exception Types</span></span>  

 <span data-ttu-id="ff783-118">Todas las excepciones iniciadas por canales deben ser <xref:System.TimeoutException?displayProperty=nameWithType>, <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType>o un tipo derivado de <xref:System.ServiceModel.CommunicationException>.</span><span class="sxs-lookup"><span data-stu-id="ff783-118">All exceptions thrown by channels must be either a <xref:System.TimeoutException?displayProperty=nameWithType>, <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType>, or a type derived from <xref:System.ServiceModel.CommunicationException>.</span></span> <span data-ttu-id="ff783-119">(También se pueden producir excepciones como <xref:System.ObjectDisposedException>, pero solo para indicar que el código de llamada ha empleado mal el canal.</span><span class="sxs-lookup"><span data-stu-id="ff783-119">(Exceptions such as <xref:System.ObjectDisposedException> may also be thrown, but only to indicate that the calling code has misused the channel.</span></span> <span data-ttu-id="ff783-120">Si un canal se utiliza correctamente, solo debe iniciar las excepciones especificadas). WCF proporciona siete tipos de excepción que se derivan de <xref:System.ServiceModel.CommunicationException> y están diseñados para que los usen los canales.</span><span class="sxs-lookup"><span data-stu-id="ff783-120">If a channel is used correctly, it must only throw the given exceptions.) WCF provides seven exception types that derive from <xref:System.ServiceModel.CommunicationException> and are designed to be used by channels.</span></span> <span data-ttu-id="ff783-121">Hay otras excepciones derivadas de <xref:System.ServiceModel.CommunicationException> que están diseñadas para ser utilizadas por otras partes del sistema.</span><span class="sxs-lookup"><span data-stu-id="ff783-121">There are other <xref:System.ServiceModel.CommunicationException>-derived exceptions that are designed to be used by other parts of the system.</span></span> <span data-ttu-id="ff783-122">Estos tipos de excepción son:</span><span class="sxs-lookup"><span data-stu-id="ff783-122">These exception types are:</span></span>  
  
|<span data-ttu-id="ff783-123">Tipo de excepción</span><span class="sxs-lookup"><span data-stu-id="ff783-123">Exception Type</span></span>|<span data-ttu-id="ff783-124">Significado</span><span class="sxs-lookup"><span data-stu-id="ff783-124">Meaning</span></span>|<span data-ttu-id="ff783-125">Contenido de excepción interno</span><span class="sxs-lookup"><span data-stu-id="ff783-125">Inner Exception Content</span></span>|<span data-ttu-id="ff783-126">Estrategia de recuperación</span><span class="sxs-lookup"><span data-stu-id="ff783-126">Recovery Strategy</span></span>|  
|--------------------|-------------|-----------------------------|-----------------------|  
|<xref:System.ServiceModel.AddressAlreadyInUseException>|<span data-ttu-id="ff783-127">La dirección del punto de conexión especificada para realizar escuchas ya se está utilizando.</span><span class="sxs-lookup"><span data-stu-id="ff783-127">The endpoint address specified for listening is already in use.</span></span>|<span data-ttu-id="ff783-128">Si está presente, proporciona más detalles sobre el error de transporte que produjo esta excepción.</span><span class="sxs-lookup"><span data-stu-id="ff783-128">If present, provides more details about the transport error that caused this exception.</span></span> <span data-ttu-id="ff783-129">Por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ff783-129">For example.</span></span> <span data-ttu-id="ff783-130"><xref:System.IO.PipeException>, <xref:System.Net.HttpListenerException>, o <xref:System.Net.Sockets.SocketException>.</span><span class="sxs-lookup"><span data-stu-id="ff783-130"><xref:System.IO.PipeException>, <xref:System.Net.HttpListenerException>, or <xref:System.Net.Sockets.SocketException>.</span></span>|<span data-ttu-id="ff783-131">Pruebe una dirección diferente.</span><span class="sxs-lookup"><span data-stu-id="ff783-131">Try a different address.</span></span>|  
|<xref:System.ServiceModel.AddressAccessDeniedException>|<span data-ttu-id="ff783-132">El proceso no tiene acceso a la dirección del extremo especificada para realizar escuchas.</span><span class="sxs-lookup"><span data-stu-id="ff783-132">The process is not allowed access to the endpoint address specified for listening.</span></span>|<span data-ttu-id="ff783-133">Si está presente, proporciona más detalles sobre el error de transporte que produjo esta excepción.</span><span class="sxs-lookup"><span data-stu-id="ff783-133">If present, provides more details about the transport error that caused this exception.</span></span> <span data-ttu-id="ff783-134">Por ejemplo, <xref:System.IO.PipeException> o <xref:System.Net.HttpListenerException>.</span><span class="sxs-lookup"><span data-stu-id="ff783-134">For example, <xref:System.IO.PipeException>, or <xref:System.Net.HttpListenerException>.</span></span>|<span data-ttu-id="ff783-135">Intente con credenciales diferentes.</span><span class="sxs-lookup"><span data-stu-id="ff783-135">Try with different credentials.</span></span>|  
|<xref:System.ServiceModel.CommunicationObjectFaultedException>|<span data-ttu-id="ff783-136">El <xref:System.ServiceModel.ICommunicationObject> que se está usando está en estado de error (para obtener más información, vea [Descripción de los cambios de estado](understanding-state-changes.md)).</span><span class="sxs-lookup"><span data-stu-id="ff783-136">The <xref:System.ServiceModel.ICommunicationObject> being used is in the Faulted state (for more information, see [Understanding State Changes](understanding-state-changes.md)).</span></span> <span data-ttu-id="ff783-137">Tenga en cuenta que cuando un objeto con varias llamadas pendientes realiza una transición al estado de error, solo una llamada produce una excepción que está relacionada con el error y el resto de las llamadas inician <xref:System.ServiceModel.CommunicationObjectFaultedException>.</span><span class="sxs-lookup"><span data-stu-id="ff783-137">Note that when an object with multiple pending calls transitions to the Faulted state, only one call throws an exception that is related to the failure and the rest of the calls throw a <xref:System.ServiceModel.CommunicationObjectFaultedException>.</span></span> <span data-ttu-id="ff783-138">Normalmente se produce esta excepción porque una aplicación pasa por alto alguna excepción e intenta utilizar un objeto que ya ha fallado, posiblemente en un subproceso diferente al que detectó la excepción original.</span><span class="sxs-lookup"><span data-stu-id="ff783-138">This exception is typically thrown because an application overlooks some exception and tries to use an already faulted object, possibly on a thread other than the one that caught the original exception.</span></span>|<span data-ttu-id="ff783-139">Si está presente, proporciona detalles sobre la excepción interna.</span><span class="sxs-lookup"><span data-stu-id="ff783-139">If present provides details about the inner exception.</span></span>|<span data-ttu-id="ff783-140">Crear un nuevo objeto.</span><span class="sxs-lookup"><span data-stu-id="ff783-140">Create a new object.</span></span> <span data-ttu-id="ff783-141">Tenga en cuenta que dependiendo de lo que provocó que<xref:System.ServiceModel.ICommunicationObject> fallase en primer lugar, puede haber otro trabajo implicado para recuperarlo.</span><span class="sxs-lookup"><span data-stu-id="ff783-141">Note that depending on what caused the <xref:System.ServiceModel.ICommunicationObject> to fault in the first place, there may be other work required to recover.</span></span>|  
|<xref:System.ServiceModel.CommunicationObjectAbortedException>|<span data-ttu-id="ff783-142">Se <xref:System.ServiceModel.ICommunicationObject> ha anulado el que se está usando (para obtener más información, vea [Descripción de los cambios de estado](understanding-state-changes.md)).</span><span class="sxs-lookup"><span data-stu-id="ff783-142">The <xref:System.ServiceModel.ICommunicationObject> being used has been Aborted (for more information, see [Understanding State Changes](understanding-state-changes.md)).</span></span> <span data-ttu-id="ff783-143">De forma similar a <xref:System.ServiceModel.CommunicationObjectFaultedException> , esta excepción indica que la aplicación ha llamado a <xref:System.ServiceModel.ICommunicationObject.Abort%2A> en el objeto, posiblemente desde otro subproceso, y que el objeto ya no se puede utilizar por esa razón.</span><span class="sxs-lookup"><span data-stu-id="ff783-143">Similar to <xref:System.ServiceModel.CommunicationObjectFaultedException>, this exception indicates the application has called <xref:System.ServiceModel.ICommunicationObject.Abort%2A> on the object, possibly from another thread, and the object is no longer usable for that reason.</span></span>|<span data-ttu-id="ff783-144">Si está presente, proporciona detalles sobre la excepción interna.</span><span class="sxs-lookup"><span data-stu-id="ff783-144">If present provides details about the inner exception.</span></span>|<span data-ttu-id="ff783-145">Crear un nuevo objeto.</span><span class="sxs-lookup"><span data-stu-id="ff783-145">Create a new object.</span></span> <span data-ttu-id="ff783-146">Tenga en cuenta que dependiendo de lo que provocó la anulación de <xref:System.ServiceModel.ICommunicationObject> en primer lugar, puede haber otro trabajo implicado para recuperarlo.</span><span class="sxs-lookup"><span data-stu-id="ff783-146">Note that depending on what caused the <xref:System.ServiceModel.ICommunicationObject> to abort in the first place, there may be other work required to recover.</span></span>|  
|<xref:System.ServiceModel.EndpointNotFoundException>|<span data-ttu-id="ff783-147">El punto de conexión remoto de destino no está realizando escuchas.</span><span class="sxs-lookup"><span data-stu-id="ff783-147">The target remote endpoint is not listening.</span></span> <span data-ttu-id="ff783-148">Esto puede ser el resultado de que cualquier parte de la dirección de punto de conexión sea incorrecta, irresoluble, o que el punto de conexión esté caído.</span><span class="sxs-lookup"><span data-stu-id="ff783-148">This can result from any part of the endpoint address being incorrect, irresolvable, or the endpoint being down.</span></span> <span data-ttu-id="ff783-149">Los ejemplos incluyen error de DNS, Administrador de la cola no disponible y servicio no ejecutándose.</span><span class="sxs-lookup"><span data-stu-id="ff783-149">Examples include DNS error, Queue Manager not available, and service not running.</span></span>|<span data-ttu-id="ff783-150">La excepción interna proporciona detalles, normalmente del transporte subyacente.</span><span class="sxs-lookup"><span data-stu-id="ff783-150">The inner exception provides details, typically from the underlying transport.</span></span>|<span data-ttu-id="ff783-151">Pruebe una dirección diferente.</span><span class="sxs-lookup"><span data-stu-id="ff783-151">Try a different address.</span></span> <span data-ttu-id="ff783-152">Alternativamente, el remitente puede esperar un poco e intentarlo de nuevo en caso de que el servicio estuviera caído</span><span class="sxs-lookup"><span data-stu-id="ff783-152">Alternatively, the sender may wait a while and try again in case the service was down</span></span>|  
|<xref:System.ServiceModel.ProtocolException>|<span data-ttu-id="ff783-153">Los protocolos de comunicación, como se describe en la Directiva del punto de conexión, no coinciden entre los extremos.</span><span class="sxs-lookup"><span data-stu-id="ff783-153">The communication protocols, as described by the endpoint's policy, are mismatched between endpoints.</span></span> <span data-ttu-id="ff783-154">Por ejemplo, el tipo de contenido de marco no coincide o se ha excedido el tamaño máximo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="ff783-154">For example, framing content type mismatch or max message size exceeded.</span></span>|<span data-ttu-id="ff783-155">Si está presente, proporciona más información sobre el error de protocolo concreto.</span><span class="sxs-lookup"><span data-stu-id="ff783-155">If present provides more information about the specific protocol error.</span></span> <span data-ttu-id="ff783-156">Por ejemplo, <xref:System.ServiceModel.QuotaExceededException> es la excepción interna cuando la causa del error es que se ha superado MaxReceivedMessageSize.</span><span class="sxs-lookup"><span data-stu-id="ff783-156">For example, <xref:System.ServiceModel.QuotaExceededException> is the inner exception when the error cause is exceeding MaxReceivedMessageSize.</span></span>|<span data-ttu-id="ff783-157">Recuperación: Asegurarse de que la configuración de protocolo del remitente y el destinatario coincidan.</span><span class="sxs-lookup"><span data-stu-id="ff783-157">Recovery: Ensure sender and received protocol settings match.</span></span> <span data-ttu-id="ff783-158">Una manera de hacerlo es volver a importar los metadatos del punto de conexión de servicio (Directiva) y utilizar el enlace generado para volver a crear el canal.</span><span class="sxs-lookup"><span data-stu-id="ff783-158">One way to do this is to re-import the service endpoint's metadata (policy) and use the generated binding to recreate the channel.</span></span>|  
|<xref:System.ServiceModel.ServerTooBusyException>|<span data-ttu-id="ff783-159">El extremo remoto está realizando escuchas pero no está preparado para procesar los mensajes.</span><span class="sxs-lookup"><span data-stu-id="ff783-159">The remote endpoint is listening but is not prepared to process messages.</span></span>|<span data-ttu-id="ff783-160">Si está presente, la excepción interna proporciona el error de SOAP o detalles del error en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="ff783-160">If present, the inner Exception provides the SOAP fault or transport-level error details.</span></span>|<span data-ttu-id="ff783-161">Recuperación: espere y vuelva a intentar después la operación.</span><span class="sxs-lookup"><span data-stu-id="ff783-161">Recovery: Wait and retry the operation later.</span></span>|  
|<xref:System.TimeoutException>|<span data-ttu-id="ff783-162">La operación no se completó dentro del período de tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="ff783-162">The operation failed to complete within the timeout period.</span></span>|<span data-ttu-id="ff783-163">Puede proporcionar los detalles sobre el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="ff783-163">May provide details about the timeout.</span></span>|<span data-ttu-id="ff783-164">Espere y reintente después la operación.</span><span class="sxs-lookup"><span data-stu-id="ff783-164">Wait and retry the operation later.</span></span>|  
  
 <span data-ttu-id="ff783-165">Solo defina un nuevo tipo de excepción si ese tipo se corresponde con una estrategia de recuperación concreta diferente de todos los tipos de excepción existentes.</span><span class="sxs-lookup"><span data-stu-id="ff783-165">Define a new exception type only if that type corresponds to a specific recovery strategy different from all of the existing exception types.</span></span> <span data-ttu-id="ff783-166">Si define un nuevo tipo de excepción, debe derivar de <xref:System.ServiceModel.CommunicationException> o una de sus clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="ff783-166">If you do define a new exception type, it must derive from <xref:System.ServiceModel.CommunicationException> or one of its derived classes.</span></span>  
  
### <a name="exception-messages"></a><span data-ttu-id="ff783-167">Mensajes de excepción</span><span class="sxs-lookup"><span data-stu-id="ff783-167">Exception Messages</span></span>  

 <span data-ttu-id="ff783-168">Los mensajes de excepción se destinan al usuario no al programa de modo que deberían proporcionar la información suficiente para ayudar al usuario a entender y resolver el problema.</span><span class="sxs-lookup"><span data-stu-id="ff783-168">Exception messages are targeted at the user not the program so they should provide sufficient information to help the user understand and solve the problem.</span></span> <span data-ttu-id="ff783-169">Las tres partes esenciales de un mensaje de excepción bueno son:</span><span class="sxs-lookup"><span data-stu-id="ff783-169">The three essential parts of a good exception message are:</span></span>  
  
 <span data-ttu-id="ff783-170">Qué sucedió.</span><span class="sxs-lookup"><span data-stu-id="ff783-170">What happened.</span></span> <span data-ttu-id="ff783-171">Proporcione una descripción clara del problema con los términos relacionados con la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="ff783-171">Provide a clear description of the problem using terms that relate to the user's experience.</span></span> <span data-ttu-id="ff783-172">Por ejemplo, un mensaje de excepción malo sería "Sección de configuración no válida".</span><span class="sxs-lookup"><span data-stu-id="ff783-172">For example, a bad exception message would be "Invalid configuration section".</span></span> <span data-ttu-id="ff783-173">Esto deja al usuario preguntándose qué sección de configuración es incorrecta y por qué es incorrecta.</span><span class="sxs-lookup"><span data-stu-id="ff783-173">This leaves the user wondering which configuration section is incorrect and why it is incorrect.</span></span> <span data-ttu-id="ff783-174">Un mensaje mejorado sería "sección de configuración no válida \<customBinding> ".</span><span class="sxs-lookup"><span data-stu-id="ff783-174">An improved message would be "Invalid configuration section \<customBinding>".</span></span> <span data-ttu-id="ff783-175">Un mensaje aún mejor sería no "No se puede agregar el transporte denominado myTransport al enlace denominado myBinding porque el enlace ya tiene un transporte denominado myTransport."</span><span class="sxs-lookup"><span data-stu-id="ff783-175">An even better message would be "Cannot add the transport named myTransport to the binding named myBinding because the binding already has a transport named myTransport".</span></span> <span data-ttu-id="ff783-176">Se trata de un mensaje muy específico que usa términos y nombres que el usuario puede identificar fácilmente en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ff783-176">This is a very specific message using terms and names that the user can easily identify in the application's configuration file.</span></span> <span data-ttu-id="ff783-177">Sin embargo, todavía faltan algunos componentes clave.</span><span class="sxs-lookup"><span data-stu-id="ff783-177">However, there are still a few key components missing.</span></span>  
  
 <span data-ttu-id="ff783-178">La importancia del error.</span><span class="sxs-lookup"><span data-stu-id="ff783-178">The significance of the error.</span></span> <span data-ttu-id="ff783-179">A menos que el mensaje diga claramente qué significa el error, es probable que el usuario se pregunte si es un error irrecuperable o si se puede omitir.</span><span class="sxs-lookup"><span data-stu-id="ff783-179">Unless the message states clearly what the error means, the user is likely to wonder whether it is a fatal error or if it can be ignored.</span></span> <span data-ttu-id="ff783-180">En general, los mensajes deberían conducir al error mediante el significado o la importancia.</span><span class="sxs-lookup"><span data-stu-id="ff783-180">In general, messages should lead with the meaning or significance of the error.</span></span> <span data-ttu-id="ff783-181">Para mejorar el ejemplo anterior, el mensaje podría ser “ServiceHost no se ha podido abrir debido a un error de configuración: No puede agregar el transporte denominado myTransport al enlace denominado myBinding porque el enlace ya tiene un transporte denominado myTransport.”</span><span class="sxs-lookup"><span data-stu-id="ff783-181">To improve the previous example, the message could be "ServiceHost failed to Open due to a configuration error: Cannot add the transport named myTransport to the binding named myBinding because the binding already has a transport named myTransport".</span></span>  
  
 <span data-ttu-id="ff783-182">Cómo el usuario debería corregir el problema.</span><span class="sxs-lookup"><span data-stu-id="ff783-182">How the user should correct the problem.</span></span> <span data-ttu-id="ff783-183">La parte más importante del mensaje está ayudar al usuario a corregir el problema.</span><span class="sxs-lookup"><span data-stu-id="ff783-183">The most important part of the message is helping the user fix the problem.</span></span> <span data-ttu-id="ff783-184">El mensaje debería incluir alguna guía o sugerencias sobre qué comprobar o corregir para solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="ff783-184">The message should include some guidance or hints about what to check or fix to remedy the problem.</span></span> <span data-ttu-id="ff783-185">Por ejemplo, "ServiceHost no se ha podido abrir debido a un error de configuración: No puede agregar el transporte denominado myTransport al enlace denominado myBinding porque el enlace ya tiene un transporte denominado myTransport.</span><span class="sxs-lookup"><span data-stu-id="ff783-185">For example, "ServiceHost failed to Open due to a configuration error: Cannot add the transport named myTransport to the binding named myBinding because the binding already has a transport named myTransport.</span></span> <span data-ttu-id="ff783-186">Asegúrese de que solo haya un transporte en el enlace."</span><span class="sxs-lookup"><span data-stu-id="ff783-186">Please ensure there is only one transport in the binding".</span></span>  
  
## <a name="communicating-faults"></a><span data-ttu-id="ff783-187">Comunicar los errores</span><span class="sxs-lookup"><span data-stu-id="ff783-187">Communicating Faults</span></span>  

 <span data-ttu-id="ff783-188">SOAP 1.1 y SOAP 1.2 definen una estructura concreta para los errores.</span><span class="sxs-lookup"><span data-stu-id="ff783-188">SOAP 1.1 and SOAP 1.2 both define a specific structure for faults.</span></span> <span data-ttu-id="ff783-189">Hay algunas diferencias entre las dos especificaciones pero en general, los tipos Message y MessageFault se utilizan para crear y utilizar los errores.</span><span class="sxs-lookup"><span data-stu-id="ff783-189">There are some differences between the two specifications but in general, the Message and MessageFault types are used to create and consume faults.</span></span>  
  
 <span data-ttu-id="ff783-190">![Control de excepciones y errores](./media/wcfc-soap1-1andsoap1-2faultcomparisonc.gif "wcfc_SOAP1-1AndSOAP1-2FaultComparisonc")</span><span class="sxs-lookup"><span data-stu-id="ff783-190">![Handling exceptions and faults](./media/wcfc-soap1-1andsoap1-2faultcomparisonc.gif "wcfc_SOAP1-1AndSOAP1-2FaultComparisonc")</span></span>  
<span data-ttu-id="ff783-191">Error de SOAP 1.2 (izquierda) y error de SOAP 1.1 (derecha).</span><span class="sxs-lookup"><span data-stu-id="ff783-191">SOAP 1.2 Fault (left) and SOAP 1.1 Fault (right).</span></span> <span data-ttu-id="ff783-192">Tenga en cuenta que en SOAP 1.1 solo el elemento Fault está calificado con el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="ff783-192">Note that in SOAP 1.1 only the Fault element is namespace qualified.</span></span>  
  
 <span data-ttu-id="ff783-193">SOAP define un mensaje de error como un mensaje que contiene solo un elemento de error (un elemento cuyo nombre es `<env:Fault>`.</span><span class="sxs-lookup"><span data-stu-id="ff783-193">SOAP defines a fault message as a message that contains only a fault element (an element whose name is `<env:Fault>`) as a child of `<env:Body>`.</span></span> <span data-ttu-id="ff783-194">El contenido del elemento de error difiere ligeramente entre SOAP 1.1 y SOAP 1.2 como se muestra en la figura 1.</span><span class="sxs-lookup"><span data-stu-id="ff783-194">The contents of the fault element differ slightly between SOAP 1.1 and SOAP 1.2 as shown in figure 1.</span></span> <span data-ttu-id="ff783-195">Sin embargo, la clase <xref:System.ServiceModel.Channels.MessageFault?displayProperty=nameWithType> normaliza estas diferencias en un modelo de objetos:</span><span class="sxs-lookup"><span data-stu-id="ff783-195">However, the <xref:System.ServiceModel.Channels.MessageFault?displayProperty=nameWithType> class normalizes these differences into one object model:</span></span>  
  
```csharp
public abstract class MessageFault  
{  
    protected MessageFault();  
  
    public virtual string Actor { get; }  
    public virtual string Node { get; }  
    public static string DefaultAction { get; }  
    public abstract FaultCode Code { get; }  
    public abstract bool HasDetail { get; }  
    public abstract FaultReason Reason { get; }  
  
    public T GetDetail<T>();  
    public T GetDetail<T>( XmlObjectSerializer serializer);  
    public System.Xml.XmlDictionaryReader GetReaderAtDetailContents();  
  
    // other methods omitted  
}  
```  
  
 <span data-ttu-id="ff783-196">La propiedad `Code` corresponde a (o `env:Code` en SOAP 1.1) `faultCode` e identifica el tipo del error.</span><span class="sxs-lookup"><span data-stu-id="ff783-196">The `Code` property corresponds to the `env:Code` (or `faultCode` in SOAP 1.1) and identifies the type of the fault.</span></span> <span data-ttu-id="ff783-197">SOAP 1.2 define cinco valores permitidos para `faultCode` (por ejemplo, Remitente y Receptor) y define un elemento `Subcode` que puede contener cualquier valor de subcódigo.</span><span class="sxs-lookup"><span data-stu-id="ff783-197">SOAP 1.2 defines five allowable values for `faultCode` (for example, Sender and Receiver) and defines a `Subcode` element which can contain any subcode value.</span></span> <span data-ttu-id="ff783-198">(Consulte la [especificación de SOAP 1,2](https://www.w3.org/TR/soap12-part1/#tabsoapfaultcodes) para ver la lista de códigos de error permitidos y su significado). SOAP 1,1 tiene un mecanismo ligeramente diferente: define cuatro `faultCode` valores (por ejemplo, cliente y servidor) que se pueden extender definiendo los completamente nuevos o utilizando la notación de puntos para crear más específicos `faultCodes` , por ejemplo, Client. Authentication.</span><span class="sxs-lookup"><span data-stu-id="ff783-198">(See the [SOAP 1.2 specification](https://www.w3.org/TR/soap12-part1/#tabsoapfaultcodes) for the list of allowable fault codes and their meaning.) SOAP 1.1 has a slightly different mechanism: It defines four `faultCode` values (for example, Client and Server) that can be extended either by defining entirely new ones or by using the dot notation to create more specific `faultCodes`, for example, Client.Authentication.</span></span>  
  
 <span data-ttu-id="ff783-199">Al utilizar MessageFault para programar los errores, FaultCode.Name y FaultCode.Namespace se asignan al nombre y espacio de nombres de `env:Code` de SOAP 1.2 `faultCode`ó SOAP 1.1.</span><span class="sxs-lookup"><span data-stu-id="ff783-199">When you use MessageFault to program faults, the FaultCode.Name and FaultCode.Namespace maps to the name and namespace of the SOAP 1.2 `env:Code` or the SOAP 1.1 `faultCode`.</span></span> <span data-ttu-id="ff783-200">FaultCode.SubCode se asigna a `env:Subcode` para SOAP 1.2 y es NULL para SOAP 1.1.</span><span class="sxs-lookup"><span data-stu-id="ff783-200">The FaultCode.SubCode maps to `env:Subcode` for SOAP 1.2 and is null for SOAP 1.1.</span></span>  
  
 <span data-ttu-id="ff783-201">Debería crear nuevos subcódigos de error (o nuevos códigos de error si utiliza SOAP 1.1) si es interesante para distinguir mediante programación un error.</span><span class="sxs-lookup"><span data-stu-id="ff783-201">You should create new fault subcodes (or new fault codes if using SOAP 1.1) if it is interesting to programmatically distinguish a fault.</span></span> <span data-ttu-id="ff783-202">Esto es análogo a crear un nuevo tipo de excepción.</span><span class="sxs-lookup"><span data-stu-id="ff783-202">This is analogous to creating a new exception type.</span></span> <span data-ttu-id="ff783-203">Debería evitar utilizar la notación de puntos con códigos de error de SOAP 1.1.</span><span class="sxs-lookup"><span data-stu-id="ff783-203">You should avoid using the dot notation with SOAP 1.1 fault codes.</span></span> <span data-ttu-id="ff783-204">(El [Perfil básico de WS-I](http://www.ws-i.org/Profiles/BasicProfile-1.1-2004-08-24.html#SOAP_Custom_Fault_Codes) también desaconseja el uso de la notación de puntos de código de error).</span><span class="sxs-lookup"><span data-stu-id="ff783-204">(The [WS-I Basic Profile](http://www.ws-i.org/Profiles/BasicProfile-1.1-2004-08-24.html#SOAP_Custom_Fault_Codes) also discourages the use of the fault code dot notation.)</span></span>  
  
```csharp
public class FaultCode  
{  
    public FaultCode(string name);  
    public FaultCode(string name, FaultCode subCode);  
    public FaultCode(string name, string ns);  
    public FaultCode(string name, string ns, FaultCode subCode);  
  
    public bool IsPredefinedFault { get; }  
    public bool IsReceiverFault { get; }  
    public bool IsSenderFault { get; }  
    public string Name { get; }  
    public string Namespace { get; }  
    public FaultCode SubCode { get; }  
  
//  methods omitted  
  
}  
```  
  
 <span data-ttu-id="ff783-205">La `Reason` propiedad corresponde a `env:Reason` (o `faultString` en SOAP 1,1) una descripción inteligible de la condición de error análoga al mensaje de una excepción.</span><span class="sxs-lookup"><span data-stu-id="ff783-205">The `Reason` property corresponds to the `env:Reason` (or `faultString` in SOAP 1.1) a human-readable description of the error condition analogous to an exception's message.</span></span> <span data-ttu-id="ff783-206">La clase `FaultReason` (y SOAP `env:Reason/faultString`) tiene compatibilidad integrada para tener varias traducciones en interés de la globalización.</span><span class="sxs-lookup"><span data-stu-id="ff783-206">The `FaultReason` class (and SOAP `env:Reason/faultString`) has built-in support for having multiple translations in the interest of globalization.</span></span>  
  
```csharp
public class FaultReason  
{  
    public FaultReason(FaultReasonText translation);  
    public FaultReason(IEnumerable<FaultReasonText> translations);  
    public FaultReason(string text);  
  
    public SynchronizedReadOnlyCollection<FaultReasonText> Translations
    {
       get;
    }  
  
 }  
```  
  
 <span data-ttu-id="ff783-207">El contenido de los detalles del error se expone en MessageFault con varios métodos, entre los que se incluyen `GetDetail` \<T> y `GetReaderAtDetailContents` ().</span><span class="sxs-lookup"><span data-stu-id="ff783-207">The fault detail contents are exposed on MessageFault using various methods including the `GetDetail`\<T> and `GetReaderAtDetailContents`().</span></span> <span data-ttu-id="ff783-208">El detalle del error es un elemento opaco para llevar el detalle adicional sobre el error.</span><span class="sxs-lookup"><span data-stu-id="ff783-208">The fault detail is an opaque element for carrying additional detail about the fault.</span></span> <span data-ttu-id="ff783-209">Esto es útil si es algún detalle estructurado arbitrario que desea llevar con el error.</span><span class="sxs-lookup"><span data-stu-id="ff783-209">This is useful if there is some arbitrary structured detail that you want to carry with the fault.</span></span>  
  
### <a name="generating-faults"></a><span data-ttu-id="ff783-210">Generar errores</span><span class="sxs-lookup"><span data-stu-id="ff783-210">Generating Faults</span></span>  

 <span data-ttu-id="ff783-211">En esta sección se explica el proceso de generar un error en respuesta a una condición de error detectada en un canal o en una propiedad de mensaje creada por el canal.</span><span class="sxs-lookup"><span data-stu-id="ff783-211">This section explains the process of generating a fault in response to an error condition detected in a channel or in a message property created by the channel.</span></span> <span data-ttu-id="ff783-212">Un ejemplo típico es devolver un error en respuesta a un mensaje de solicitud que contiene datos no válidos.</span><span class="sxs-lookup"><span data-stu-id="ff783-212">A typical example is sending back a fault in response to a request message that contains invalid data.</span></span>  
  
 <span data-ttu-id="ff783-213">Al generar un error, el canal personalizado no debería enviar directamente el error, más bien, debería iniciar una excepción y permitir a la capa anterior decidir si convertir esa excepción en un error y cómo enviarlo.</span><span class="sxs-lookup"><span data-stu-id="ff783-213">When generating a fault, the custom channel should not send the fault directly, rather, it should throw an exception and let the layer above decide whether to convert that exception to a fault and how to send it.</span></span> <span data-ttu-id="ff783-214">Para ayudar en esta conversión, el canal debería proporcionar una implementación `FaultConverter` que pueda convertir la excepción iniciada por el canal personalizado en el error adecuado.</span><span class="sxs-lookup"><span data-stu-id="ff783-214">To aid in this conversion, the channel should provide a `FaultConverter` implementation that can convert the exception thrown by the custom channel to the appropriate fault.</span></span> <span data-ttu-id="ff783-215">`FaultConverter` se define como:</span><span class="sxs-lookup"><span data-stu-id="ff783-215">`FaultConverter` is defined as:</span></span>  
  
```csharp
public class FaultConverter  
{  
    public static FaultConverter GetDefaultFaultConverter(  
                                   MessageVersion version);  
    protected abstract bool OnTryCreateFaultMessage(  
                                   Exception exception,
                                   out Message message);  
    public bool TryCreateFaultMessage(  
                                   Exception exception,
                                   out Message message);  
}  
```  
  
 <span data-ttu-id="ff783-216">Cada canal que genera errores personalizados debe implementar `FaultConverter` y devolverlo de una llamada a `GetProperty<FaultConverter>`.</span><span class="sxs-lookup"><span data-stu-id="ff783-216">Each channel that generates custom faults must implement `FaultConverter` and return it from a call to `GetProperty<FaultConverter>`.</span></span> <span data-ttu-id="ff783-217">La `OnTryCreateFaultMessage` implementación personalizada debe convertir la excepción en un error o un delegado en el del canal interno `FaultConverter` .</span><span class="sxs-lookup"><span data-stu-id="ff783-217">The custom `OnTryCreateFaultMessage` implementation must either convert the exception to a fault or delegate to the inner channel's `FaultConverter`.</span></span> <span data-ttu-id="ff783-218">Si el canal es un transporte, debe convertir la excepción o el delegado en el codificador `FaultConverter` o el valor predeterminado `FaultConverter` proporcionado en WCF.</span><span class="sxs-lookup"><span data-stu-id="ff783-218">If the channel is a transport it must either convert the exception or delegate to the encoder's `FaultConverter` or the default `FaultConverter` provided in WCF .</span></span> <span data-ttu-id="ff783-219">El `FaultConverter` predeterminado convierte los errores que corresponden a los mensajes de error especificados por WS-Addressing y SOAP.</span><span class="sxs-lookup"><span data-stu-id="ff783-219">The default `FaultConverter` converts errors corresponding to fault messages specified by WS-Addressing and SOAP.</span></span> <span data-ttu-id="ff783-220">A continuación se incluye un ejemplo de implementación `OnTryCreateFaultMessage`:</span><span class="sxs-lookup"><span data-stu-id="ff783-220">Here is an example `OnTryCreateFaultMessage` implementation.</span></span>  
  
```csharp
public override bool OnTryCreateFaultMessage(Exception exception,
                                             out Message message)  
{  
    if (exception is ...)  
    {  
        message = ...;  
        return true;  
    }  
  
#if IMPLEMENTING_TRANSPORT_CHANNEL  
    FaultConverter encoderConverter =
                    this.encoder.GetProperty<FaultConverter>();  
    if ((encoderConverter != null) &&
        (encoderConverter.TryCreateFaultMessage(  
         exception, out message)))  
    {  
        return true;  
    }  
  
    FaultConverter defaultConverter =
                   FaultConverter.GetDefaultFaultConverter(  
                   this.channel.messageVersion);  
    return defaultConverter.TryCreateFaultMessage(  
                   exception,
                   out message);  
#else  
    FaultConverter inner =
                   this.innerChannel.GetProperty<FaultConverter>();  
    if (inner != null)  
    {  
        return inner.TryCreateFaultMessage(exception, out message);  
    }  
    else  
    {  
        message = null;  
        return false;  
    }  
#endif  
}  
```  
  
 <span data-ttu-id="ff783-221">Una implicación de este patrón es que las excepciones iniciadas entre las capas para las condiciones de error que requieren los errores deben contener suficiente información para que el generador del error correspondiente cree el error correcto.</span><span class="sxs-lookup"><span data-stu-id="ff783-221">An implication of this pattern is that exceptions thrown between layers for error conditions that require faults must contain enough information for the corresponding fault generator to create the correct fault.</span></span> <span data-ttu-id="ff783-222">Como un autor del canal personalizado, puede definir tipos de excepción que correspondan a condiciones de error diferentes si tales excepciones aún no existen.</span><span class="sxs-lookup"><span data-stu-id="ff783-222">As a custom channel author, you may define exception types that correspond to different fault conditions if such exceptions do not already exist.</span></span> <span data-ttu-id="ff783-223">Observe que las excepciones que atraviesan las capas del canal deberían comunicar la condición de error en lugar de los datos del error opacos.</span><span class="sxs-lookup"><span data-stu-id="ff783-223">Note that exceptions traversing channel layers should communicate the error condition rather than opaque fault data.</span></span>  
  
### <a name="fault-categories"></a><span data-ttu-id="ff783-224">Categorías de error</span><span class="sxs-lookup"><span data-stu-id="ff783-224">Fault Categories</span></span>  

 <span data-ttu-id="ff783-225">Generalmente hay tres categorías de errores:</span><span class="sxs-lookup"><span data-stu-id="ff783-225">There are generally three categories of faults:</span></span>  
  
1. <span data-ttu-id="ff783-226">Errores que son penetrantes a lo largo de la pila completa.</span><span class="sxs-lookup"><span data-stu-id="ff783-226">Faults that are pervasive throughout the entire stack.</span></span> <span data-ttu-id="ff783-227">Estos errores se podrían encontrar en cualquier capa en la pila del canal, por ejemplo InvalidCardinalityAddressingException.</span><span class="sxs-lookup"><span data-stu-id="ff783-227">These faults could be encountered at any layer in the channel stack, for example InvalidCardinalityAddressingException.</span></span>  
  
2. <span data-ttu-id="ff783-228">Errores que se pueden encontrar en cualquier parte sobre una cierta capa en la pila, por ejemplo, algunos errores que pertenecen a una transacción fluida o a las funciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ff783-228">Faults that can be encountered anywhere above a certain layer in the stack for example some errors that pertain to a flowed transaction or to security roles.</span></span>  
  
3. <span data-ttu-id="ff783-229">Errores dirigidos a una capa única en la pila, por ejemplo, errores como los errores de número de secuencia de WS-RM.</span><span class="sxs-lookup"><span data-stu-id="ff783-229">Faults that are directed at a single layer in the stack, for example errors like WS-RM sequence number faults.</span></span>  
  
 <span data-ttu-id="ff783-230">Categoría 1.</span><span class="sxs-lookup"><span data-stu-id="ff783-230">Category 1.</span></span> <span data-ttu-id="ff783-231">Los errores son generalmente errores de WS-Addressing y de SOAP.</span><span class="sxs-lookup"><span data-stu-id="ff783-231">Faults are generally WS-Addressing and SOAP faults.</span></span> <span data-ttu-id="ff783-232">La `FaultConverter` clase base proporcionada por WCF convierte los errores correspondientes a los mensajes de error especificados por WS-Addressing y SOAP, por lo que no es necesario controlar la conversión de estas excepciones usted mismo.</span><span class="sxs-lookup"><span data-stu-id="ff783-232">The base `FaultConverter` class provided by WCF converts errors corresponding to fault messages specified by WS-Addressing and SOAP so you do not have to handle conversion of these exceptions yourself.</span></span>  
  
 <span data-ttu-id="ff783-233">Categoría 2.</span><span class="sxs-lookup"><span data-stu-id="ff783-233">Category 2.</span></span> <span data-ttu-id="ff783-234">Los errores se producen cuando una capa agrega una propiedad al mensaje que no usa completamente la información del mensaje que pertenece a esa capa.</span><span class="sxs-lookup"><span data-stu-id="ff783-234">Faults occur when a layer adds a property to the message that does not completely consume message information that pertains to that layer.</span></span> <span data-ttu-id="ff783-235">Se pueden detectar los errores más adelante cuando una capa superior pide a la propiedad de mensaje que procese más información del mensaje.</span><span class="sxs-lookup"><span data-stu-id="ff783-235">Errors may be detected later when a higher layer asks the message property to process message information further.</span></span> <span data-ttu-id="ff783-236">Tales canales deberían implementar la `GetProperty` especificada previamente para permitir a la capa superior devolver el error correcto.</span><span class="sxs-lookup"><span data-stu-id="ff783-236">Such channels should implement the `GetProperty` specified previously to enable the higher layer to send back the correct fault.</span></span> <span data-ttu-id="ff783-237">Un ejemplo de esto es TransactionMessageProperty.</span><span class="sxs-lookup"><span data-stu-id="ff783-237">An example of this is the TransactionMessageProperty.</span></span> <span data-ttu-id="ff783-238">Esta propiedad se agrega al mensaje sin validar totalmente todos los datos en el encabezado (hacer esto puede implicar ponerse en contacto con el coordinador de transacciones distribuidas (DTC).</span><span class="sxs-lookup"><span data-stu-id="ff783-238">This property is added to the message without fully validating all the data in the header (doing so may involve contacting the distributed transaction coordinator (DTC).</span></span>  
  
 <span data-ttu-id="ff783-239">Categoría 3.</span><span class="sxs-lookup"><span data-stu-id="ff783-239">Category 3.</span></span> <span data-ttu-id="ff783-240">Los errores solo son generados y enviados por una capa única en el procesador.</span><span class="sxs-lookup"><span data-stu-id="ff783-240">Faults are only generated and sent by a single layer in the processor.</span></span> <span data-ttu-id="ff783-241">Por consiguiente todas las excepciones están contenidas dentro de la capa.</span><span class="sxs-lookup"><span data-stu-id="ff783-241">Therefore all the exceptions are contained within the layer.</span></span> <span data-ttu-id="ff783-242">Para mejorar la coherencia entre los canales y facilitar el mantenimiento, su canal personalizado debería utilizar el patrón especificado previamente para generar mensajes de error incluso para los errores internos.</span><span class="sxs-lookup"><span data-stu-id="ff783-242">To improve consistency among channels and ease maintenance, your custom channel should use the pattern specified previously to generate fault messages even for internal faults.</span></span>  
  
### <a name="interpreting-received-faults"></a><span data-ttu-id="ff783-243">Errores de interpretación recibidos</span><span class="sxs-lookup"><span data-stu-id="ff783-243">Interpreting Received Faults</span></span>  

 <span data-ttu-id="ff783-244">Esta sección proporciona una guía para generar la excepción adecuada al recibir un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="ff783-244">This section provides guidance for generating the appropriate exception when receiving a fault message.</span></span> <span data-ttu-id="ff783-245">El árbol de decisión para procesar un mensaje en cada capa en la pila es como sigue:</span><span class="sxs-lookup"><span data-stu-id="ff783-245">The decision tree for processing a message at every layer in the stack is as follows:</span></span>  
  
1. <span data-ttu-id="ff783-246">Si la capa considera que el mensaje no es válido, la capa debe realizar su procesamiento de "mensaje no válido".</span><span class="sxs-lookup"><span data-stu-id="ff783-246">If the layer considers the message to be invalid, the layer should do its 'invalid message' processing.</span></span> <span data-ttu-id="ff783-247">Tal procesamiento es específico de la capa, pero podría incluir la colocación del mensaje, el seguimiento o el inicio de una excepción que se convierta en un error.</span><span class="sxs-lookup"><span data-stu-id="ff783-247">Such processing is specific to the layer but could include dropping the message, tracing, or throwing an exception that gets converted to a fault.</span></span> <span data-ttu-id="ff783-248">Los ejemplos incluyen seguridad al recibir un mensaje que no está correctamente protegido o RM al recibir un mensaje con un número de secuencia no válido.</span><span class="sxs-lookup"><span data-stu-id="ff783-248">Examples include security receiving a message that is not secured properly, or RM receiving a message with a bad sequence number.</span></span>  
  
2. <span data-ttu-id="ff783-249">De lo contrario, si el mensaje es un mensaje de error que se aplica específicamente a la capa, y el mensaje no es significativo fuera de la interacción de la capa, la capa debería controlar la condición de error.</span><span class="sxs-lookup"><span data-stu-id="ff783-249">Otherwise, if the message is a fault message that applies specifically to the layer, and the message is not meaningful outside the layer's interaction, the layer should handle the error condition.</span></span> <span data-ttu-id="ff783-250">Un ejemplo de esto es un error de secuencia de RM rechazada que no tiene sentido para las capas sobre el canal RM y que implica un error en el canal RM y el inicio de las operaciones pendientes.</span><span class="sxs-lookup"><span data-stu-id="ff783-250">An example of this is an RM Sequence Refused fault that is meaningless to layers above the RM channel and that implies faulting the RM channel and throwing from pending operations.</span></span>  
  
3. <span data-ttu-id="ff783-251">De lo contrario, el mensaje se debería devolver de Solicitud() o Recepción().</span><span class="sxs-lookup"><span data-stu-id="ff783-251">Otherwise, the message should be returned from Request() or Receive().</span></span> <span data-ttu-id="ff783-252">Esto incluye los casos donde la capa reconoce el error, pero el error apenas indica que hubo un error en una solicitud y no implica un error en el canal y el inicio de las operaciones pendientes.</span><span class="sxs-lookup"><span data-stu-id="ff783-252">This includes cases where the layer recognizes the fault, but the fault just indicates that a request failed and does not imply faulting the channel and throwing from pending operations.</span></span> <span data-ttu-id="ff783-253">Para mejorar la utilidad en este tipo de caso, la capa debería implementar `GetProperty<FaultConverter>``FaultConverter` y devolver una clase derivada `OnTryCreateException` que pueda convertir el error en una excepción invalidando .</span><span class="sxs-lookup"><span data-stu-id="ff783-253">To improve usability in such a case, the layer should implement `GetProperty<FaultConverter>` and return a `FaultConverter` derived class that can convert the fault to an exception by overriding `OnTryCreateException`.</span></span>  
  
 <span data-ttu-id="ff783-254">El modelo de objetos siguiente permite convertir los mensajes en excepciones:</span><span class="sxs-lookup"><span data-stu-id="ff783-254">The following object model supports converting messages to exceptions:</span></span>  
  
```csharp
public class FaultConverter  
{  
    public static FaultConverter GetDefaultFaultConverter(  
                                  MessageVersion version);  
    protected abstract bool OnTryCreateException(  
                                 Message message,
                                 MessageFault fault,
                                 out Exception exception);  
    public bool TryCreateException(  
                                 Message message,
                                 MessageFault fault,
                                 out Exception exception);  
}  
```  
  
 <span data-ttu-id="ff783-255">Una capa del canal puede implementar `GetProperty<FaultConverter>` para permitir convertir los mensajes de error en excepciones.</span><span class="sxs-lookup"><span data-stu-id="ff783-255">A channel layer can implement `GetProperty<FaultConverter>` to support converting fault messages to exceptions.</span></span> <span data-ttu-id="ff783-256">Para ello, invalide `OnTryCreateException` e inspeccione el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="ff783-256">To do so, override `OnTryCreateException` and inspect the fault message.</span></span> <span data-ttu-id="ff783-257">Si se reconoce, haga la conversión, de lo contrario pida al canal interno que lo convierta.</span><span class="sxs-lookup"><span data-stu-id="ff783-257">If recognized, do the conversion, otherwise ask the inner channel to convert it.</span></span> <span data-ttu-id="ff783-258">Los canales de transporte deberían delegar a `FaultConverter.GetDefaultFaultConverter` para obtener el SOAP predeterminado/FaultConverter de WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="ff783-258">Transport channels should delegate to `FaultConverter.GetDefaultFaultConverter` to get the default SOAP/WS-Addressing FaultConverter.</span></span>  
  
 <span data-ttu-id="ff783-259">Una implementación típica se parece a:</span><span class="sxs-lookup"><span data-stu-id="ff783-259">A typical implementation looks like this:</span></span>  
  
```csharp
public override bool OnTryCreateException(  
                            Message message,
                            MessageFault fault,
                            out Exception exception)  
{  
    if (message.Action == "...")  
    {  
        exception = ...;  
        return true;  
    }  
    // OR  
    if ((fault.Code.Name == "...") && (fault.Code.Namespace == "..."))  
    {  
        exception = ...;  
        return true;  
    }  
  
    if (fault.IsMustUnderstand)  
    {  
        if (fault.WasHeaderNotUnderstood(  
                   message.Headers, "...", "..."))  
        {  
            exception = new ProtocolException(...);  
            return true;  
        }  
    }  
  
#if IMPLEMENTING_TRANSPORT_CHANNEL  
    FaultConverter encoderConverter =
              this.encoder.GetProperty<FaultConverter>();  
    if ((encoderConverter != null) &&
        (encoderConverter.TryCreateException(  
                              message, fault, out exception)))  
    {  
        return true;  
    }  
  
    FaultConverter defaultConverter =  
             FaultConverter.GetDefaultFaultConverter(  
                             this.channel.messageVersion);  
    return defaultConverter.TryCreateException(  
                             message, fault, out exception);  
#else  
    FaultConverter inner =
                    this.innerChannel.GetProperty<FaultConverter>();  
    if (inner != null)  
    {  
        return inner.TryCreateException(message, fault, out exception);  
    }  
    else  
    {  
        exception = null;  
        return false;  
    }  
#endif  
}  
```  
  
 <span data-ttu-id="ff783-260">Para las condiciones de error concretas que tienen escenarios de recuperación distintos, considere definir una clase derivada de `ProtocolException`.</span><span class="sxs-lookup"><span data-stu-id="ff783-260">For specific fault conditions that have distinct recovery scenarios, consider defining a derived class of `ProtocolException`.</span></span>  
  
### <a name="mustunderstand-processing"></a><span data-ttu-id="ff783-261">Procesamiento de MustUnderstand</span><span class="sxs-lookup"><span data-stu-id="ff783-261">MustUnderstand Processing</span></span>  

 <span data-ttu-id="ff783-262">SOAP define un error general para señalar que el receptor no entendió un encabezado necesario.</span><span class="sxs-lookup"><span data-stu-id="ff783-262">SOAP defines a general fault for signaling that a required header was not understood by the receiver.</span></span> <span data-ttu-id="ff783-263">Este error se conoce como el error `mustUnderstand`.</span><span class="sxs-lookup"><span data-stu-id="ff783-263">This fault is known as the `mustUnderstand` fault.</span></span> <span data-ttu-id="ff783-264">En WCF, los canales personalizados nunca generan `mustUnderstand` errores.</span><span class="sxs-lookup"><span data-stu-id="ff783-264">In WCF, custom channels never generate `mustUnderstand` faults.</span></span> <span data-ttu-id="ff783-265">En su lugar, el distribuidor de WCF, que se encuentra en la parte superior de la pila de comunicación de WCF, comprueba que todos los encabezados que se marcaron como MustUnderstand = true se entendieron en la pila subyacente.</span><span class="sxs-lookup"><span data-stu-id="ff783-265">Instead, the WCF Dispatcher, which is located at the top of the WCF communication stack, checks to see that all headers that were marked as MustUnderstand=true were understood by the underlying stack.</span></span> <span data-ttu-id="ff783-266">Si alguno se entendió, se genera un error `mustUnderstand` en ese punto.</span><span class="sxs-lookup"><span data-stu-id="ff783-266">If any were not understood, a `mustUnderstand` fault is generated at that point.</span></span> <span data-ttu-id="ff783-267">(El usuario puede decidir desactivar este procesamiento `mustUnderstand` y hacer que la aplicación reciba todos los encabezados de mensajes.</span><span class="sxs-lookup"><span data-stu-id="ff783-267">(The user can choose to turn off this `mustUnderstand` processing and have the application receive all message headers.</span></span> <span data-ttu-id="ff783-268">En ese caso, la aplicación es responsable de realizar el `mustUnderstand` procesamiento). El error generado incluye un encabezado NotUnderstood que contiene los nombres de todos los encabezados con MustUnderstand = true que no se entendieron.</span><span class="sxs-lookup"><span data-stu-id="ff783-268">In that case the application is responsible for performing `mustUnderstand` processing.) The generated fault includes a NotUnderstood header that contains the names of all headers with MustUnderstand=true that were not understood.</span></span>  
  
 <span data-ttu-id="ff783-269">Si su canal de protocolo envía un encabezado personalizado con MustUnderstand=true y recibe un error `mustUnderstand`, debe deducir si ese error se debe al encabezado enviado.</span><span class="sxs-lookup"><span data-stu-id="ff783-269">If your protocol channel sends a custom header with MustUnderstand=true and receives a `mustUnderstand` fault, it must figure out whether that fault is due to the header it sent.</span></span> <span data-ttu-id="ff783-270">Hay dos miembros en la clase `MessageFault` que son útiles para esto:</span><span class="sxs-lookup"><span data-stu-id="ff783-270">There are two members on the `MessageFault` class that are useful for this:</span></span>  
  
```csharp
public class MessageFault  
{  
    ...  
    public bool IsMustUnderstandFault { get; }  
    public static bool WasHeaderNotUnderstood(MessageHeaders headers,
        string name, string ns) { }  
    ...  
  
}  
```  
  
 <span data-ttu-id="ff783-271">`IsMustUnderstandFault` devuelve `true` si el error es un error `mustUnderstand`.</span><span class="sxs-lookup"><span data-stu-id="ff783-271">`IsMustUnderstandFault` returns `true` if the fault is a `mustUnderstand` fault.</span></span> <span data-ttu-id="ff783-272">`WasHeaderNotUnderstood` devuelve `true` si el encabezado con el nombre y el espacio de nombres especificados está incluido en el error como un encabezado NotUnderstood.</span><span class="sxs-lookup"><span data-stu-id="ff783-272">`WasHeaderNotUnderstood` returns `true` if the header with the specified name and namespace is included in the fault as a NotUnderstood header.</span></span>  <span data-ttu-id="ff783-273">En caso contrario, devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="ff783-273">Otherwise, it returns `false`.</span></span>  
  
 <span data-ttu-id="ff783-274">Si un canal emite un encabezado que está marcado como MustUnderstand = true, esa capa también debería implementar el patrón API de generación de excepción y convertir los errores `mustUnderstand` producidos por ese encabezado en una excepción más útil como se ha descrito previamente.</span><span class="sxs-lookup"><span data-stu-id="ff783-274">If a channel emits a header that is marked MustUnderstand = true, then that layer should also implement the Exception Generation API pattern and should convert `mustUnderstand` faults caused by that header to a more useful exception as described previously.</span></span>  
  
## <a name="tracing"></a><span data-ttu-id="ff783-275">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="ff783-275">Tracing</span></span>  

 <span data-ttu-id="ff783-276">.NET Framework proporciona un mecanismo para efectuar el seguimiento de la ejecución del programa como una manera de ayudar a diagnosticar aplicaciones de producción o los problemas intermitentes donde no es posible adjuntar simplemente un depurador y avanzar a través del código.</span><span class="sxs-lookup"><span data-stu-id="ff783-276">The .NET Framework provides a mechanism to trace program execution as a way to aid diagnosing production applications or intermittent problems where it is not possible to just attach a debugger and step through the code.</span></span> <span data-ttu-id="ff783-277">Los componentes básicos de este mecanismo están en el espacio de nombres <xref:System.Diagnostics?displayProperty=nameWithType> y consisten en:</span><span class="sxs-lookup"><span data-stu-id="ff783-277">The core components of this mechanism are in the <xref:System.Diagnostics?displayProperty=nameWithType> namespace and consist of:</span></span>  
  
- <span data-ttu-id="ff783-278"><xref:System.Diagnostics.TraceSource?displayProperty=nameWithType>, que es el origen de información de seguimiento que se va a escribir, <xref:System.Diagnostics.TraceListener?displayProperty=nameWithType>, que es una clase base abstracta para escuchas concretas que reciben la información a seguir de <xref:System.Diagnostics.TraceSource> y la entregan a un destino específico de escucha.</span><span class="sxs-lookup"><span data-stu-id="ff783-278"><xref:System.Diagnostics.TraceSource?displayProperty=nameWithType>, which is the source of trace information to be written, <xref:System.Diagnostics.TraceListener?displayProperty=nameWithType>, which is an abstract base class for concrete listeners that receive the information to be traced from the <xref:System.Diagnostics.TraceSource> and output it to a listener-specific destination.</span></span> <span data-ttu-id="ff783-279">Por ejemplo, <xref:System.Diagnostics.XmlWriterTraceListener> genera información de seguimiento a un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="ff783-279">For example, <xref:System.Diagnostics.XmlWriterTraceListener> outputs trace information to an XML file.</span></span> <span data-ttu-id="ff783-280">Finalmente, <xref:System.Diagnostics.TraceSwitch?displayProperty=nameWithType>, que permite al usuario de la aplicación controlar el nivel de detalle del seguimiento y normalmente se especifica en configuración.</span><span class="sxs-lookup"><span data-stu-id="ff783-280">Finally, <xref:System.Diagnostics.TraceSwitch?displayProperty=nameWithType>, which lets the application user control the tracing verbosity and is typically specified in configuration.</span></span>  
  
- <span data-ttu-id="ff783-281">Además de los componentes principales, puede usar la [herramienta Service Trace Viewer (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) para ver y buscar los seguimientos de WCF.</span><span class="sxs-lookup"><span data-stu-id="ff783-281">In addition to the core components, you can use the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) to view and search WCF traces.</span></span> <span data-ttu-id="ff783-282">La herramienta está diseñada específicamente para los archivos de seguimiento generados por WCF y se escriben con <xref:System.Diagnostics.XmlWriterTraceListener> .</span><span class="sxs-lookup"><span data-stu-id="ff783-282">The tool is designed specifically for trace files generated by WCF and written out using <xref:System.Diagnostics.XmlWriterTraceListener>.</span></span> <span data-ttu-id="ff783-283">La figura siguiente muestra los diferentes componentes implicados en el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ff783-283">The following figure shows the various components involved in tracing.</span></span>  
  
 <span data-ttu-id="ff783-284">![Control de excepciones y errores](./media/wcfc-tracinginchannelsc.gif "wcfc_TracingInChannelsc")</span><span class="sxs-lookup"><span data-stu-id="ff783-284">![Handling exceptions and faults](./media/wcfc-tracinginchannelsc.gif "wcfc_TracingInChannelsc")</span></span>  
  
### <a name="tracing-from-a-custom-channel"></a><span data-ttu-id="ff783-285">Seguimiento desde un canal personalizado</span><span class="sxs-lookup"><span data-stu-id="ff783-285">Tracing from a Custom Channel</span></span>  

 <span data-ttu-id="ff783-286">Los canales personalizados deberían escribir los mensajes de seguimiento para ayudar en los problemas de diagnóstico cuando no es posible adjuntar un depurador a la aplicación en ejecución.</span><span class="sxs-lookup"><span data-stu-id="ff783-286">Custom channels should write out trace messages to assist in diagnosing problems when it is not possible to attach a debugger to the running application.</span></span> <span data-ttu-id="ff783-287">Esto implica dos tareas de alto nivel: crear una instancia de <xref:System.Diagnostics.TraceSource> y llamar a sus métodos para escribir las trazas.</span><span class="sxs-lookup"><span data-stu-id="ff783-287">This involves two high level tasks: Instantiating a <xref:System.Diagnostics.TraceSource> and calling its methods to write traces.</span></span>  
  
 <span data-ttu-id="ff783-288">Al crear una instancia de <xref:System.Diagnostics.TraceSource>, la cadena que especifica se convierte en el nombre de ese origen.</span><span class="sxs-lookup"><span data-stu-id="ff783-288">When instantiating a <xref:System.Diagnostics.TraceSource>, the string you specify becomes the name of that source.</span></span> <span data-ttu-id="ff783-289">Este nombre se utiliza para configurar (habilitar/deshabilitar/establecer nivel de seguimiento) el origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ff783-289">This name is used to configure (enable/disable/set tracing level) the trace source.</span></span> <span data-ttu-id="ff783-290">También aparece en el resultado del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ff783-290">It also appears in the trace output itself.</span></span> <span data-ttu-id="ff783-291">Los canales personalizados deberían utilizar un nombre de origen único para ayudar a los lectores del resultado de seguimiento a entender de dónde procede la información de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ff783-291">Custom channels should use a unique source name to help readers of the trace output understand where the trace information comes from.</span></span> <span data-ttu-id="ff783-292">Utilizar el nombre del ensamblado que está escribiendo la información como el nombre del origen de seguimiento es lo más habitual.</span><span class="sxs-lookup"><span data-stu-id="ff783-292">Using the name of the assembly that is writing the information as the name of the trace source is the common practice.</span></span> <span data-ttu-id="ff783-293">Por ejemplo, WCF usa System. ServiceModel como el origen de seguimiento para la información escrita desde el ensamblado System. ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="ff783-293">For example, WCF uses System.ServiceModel as the trace source for information written from the System.ServiceModel assembly.</span></span>  
  
 <span data-ttu-id="ff783-294">Una vez tenga un origen de seguimiento, llame a sus métodos <xref:System.Diagnostics.TraceSource.TraceData%2A>, <xref:System.Diagnostics.TraceSource.TraceEvent%2A>o <xref:System.Diagnostics.TraceSource.TraceInformation%2A> para escribir las entradas de seguimiento en las escuchas de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ff783-294">Once you have a trace source, you call its <xref:System.Diagnostics.TraceSource.TraceData%2A>, <xref:System.Diagnostics.TraceSource.TraceEvent%2A>, or <xref:System.Diagnostics.TraceSource.TraceInformation%2A> methods to write trace entries to the trace listeners.</span></span> <span data-ttu-id="ff783-295">Para cada entrada de seguimiento que escriba, necesita clasificar el tipo de evento como uno de los tipos de evento definidos en <xref:System.Diagnostics.TraceEventType>.</span><span class="sxs-lookup"><span data-stu-id="ff783-295">For each trace entry you write, you need to classify the type of event as one of the event types defined in <xref:System.Diagnostics.TraceEventType>.</span></span> <span data-ttu-id="ff783-296">Esta clasificación y la configuración del nivel seguimiento en configuración determinan si la entrada de seguimiento se genera en la escucha.</span><span class="sxs-lookup"><span data-stu-id="ff783-296">This classification and the trace level setting in configuration determine whether the trace entry is output to the listener.</span></span> <span data-ttu-id="ff783-297">Por ejemplo, establecer el nivel de seguimiento en configuración en `Warning` permite `Warning`, `Error` y que se escriban las entradas de seguimiento `Critical` pero bloquea entradas de información y detalladas.</span><span class="sxs-lookup"><span data-stu-id="ff783-297">For example, setting the trace level in configuration to `Warning` allows `Warning`, `Error` and `Critical` trace entries to be written but blocks Information and Verbose entries.</span></span> <span data-ttu-id="ff783-298">A continuación un ejemplo para crear instancias de un origen de seguimiento y escribir una entrada en el nivel de información:</span><span class="sxs-lookup"><span data-stu-id="ff783-298">Here is an example of instantiating a trace source and writing out an entry at Information level:</span></span>  
  
```csharp
using System.Diagnostics;  
//...  
TraceSource udpSource = new TraceSource("Microsoft.Samples.Udp");  
//...  
udpsource.TraceInformation("UdpInputChannel received a message");  
```  
  
> [!IMPORTANT]
> <span data-ttu-id="ff783-299">Se recomienda encarecidamente que especifique un nombre del origen de seguimiento que sea único para su canal personalizado para ayudar a los lectores de resultados de seguimiento a entender de dónde procede el resultado.</span><span class="sxs-lookup"><span data-stu-id="ff783-299">It is highly recommended that you specify a trace source name that is unique to your custom channel to help trace output readers understand where the output came from.</span></span>  
  
#### <a name="integrating-with-the-trace-viewer"></a><span data-ttu-id="ff783-300">Integrar con el visor de seguimiento</span><span class="sxs-lookup"><span data-stu-id="ff783-300">Integrating with the Trace Viewer</span></span>  

 <span data-ttu-id="ff783-301">Los seguimientos generados por el canal se pueden mostrar en un formato legible por la [herramienta del visor de seguimiento de servicio (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) mediante <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType> como agente de escucha de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ff783-301">Traces generated by your channel can be output in a format readable by the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) by using <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType> as the trace listener.</span></span> <span data-ttu-id="ff783-302">Esto no es algo que usted, como el programador del canal, necesite hacer.</span><span class="sxs-lookup"><span data-stu-id="ff783-302">This is not something you, as the channel developer, need to do.</span></span> <span data-ttu-id="ff783-303">En su lugar, es el usuario de la aplicación (o la persona que soluciona el problema de la aplicación) que necesita configurar este agente de escucha de seguimiento en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ff783-303">Rather, it is the application user (or the person troubleshooting the application) that needs to configure this trace listener in the application's configuration file.</span></span> <span data-ttu-id="ff783-304">Por ejemplo, la configuración siguiente genera información de seguimiento de <xref:System.ServiceModel?displayProperty=nameWithType> y `Microsoft.Samples.Udp` en el archivo denominado `TraceEventsFile.e2e`:</span><span class="sxs-lookup"><span data-stu-id="ff783-304">For example, the following configuration outputs trace information from both <xref:System.ServiceModel?displayProperty=nameWithType> and `Microsoft.Samples.Udp` to the file named `TraceEventsFile.e2e`:</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <!-- configure System.ServiceModel trace source -->  
      <source name="System.ServiceModel" switchValue="Verbose"
              propagateActivity="true">  
        <listeners>  
          <add name="e2e" />  
        </listeners>  
      </source>  
      <!-- configure Microsoft.Samples.Udp trace source -->  
      <source name="Microsoft.Samples.Udp" switchValue="Verbose" >  
        <listeners>  
          <add name="e2e" />  
        </listeners>  
      </source>  
    </sources>  
    <!--   
    Define a shared trace listener that outputs to TraceFile.e2e  
    The listener name is e2e   
    -->  
    <sharedListeners>  
      <add name="e2e" type="System.Diagnostics.XmlWriterTraceListener"  
        initializeData=".\TraceFile.e2e"/>  
    </sharedListeners>  
    <trace autoflush="true" />  
  </system.diagnostics>  
</configuration>  
```  
  
#### <a name="tracing-structured-data"></a><span data-ttu-id="ff783-305">Seguimiento de datos estructurados</span><span class="sxs-lookup"><span data-stu-id="ff783-305">Tracing Structured Data</span></span>  

 <span data-ttu-id="ff783-306"><xref:System.Diagnostics.TraceSource?displayProperty=nameWithType> tiene un método <xref:System.Diagnostics.TraceSource.TraceData%2A> que toma uno o más objetos que deben incluirse en la entrada de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ff783-306"><xref:System.Diagnostics.TraceSource?displayProperty=nameWithType> has a <xref:System.Diagnostics.TraceSource.TraceData%2A> method that takes one or more objects that are to be included in the trace entry.</span></span> <span data-ttu-id="ff783-307">En general, se llama al método <xref:System.Object.ToString%2A?displayProperty=nameWithType> en cada objeto y la cadena resultante se escribe como parte de la entrada de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ff783-307">In general, the <xref:System.Object.ToString%2A?displayProperty=nameWithType> method is called on each object and the resulting string is written as part of the trace entry.</span></span> <span data-ttu-id="ff783-308">Al utilizar <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType> para generar las trazas, puede pasar <xref:System.Xml.XPath.IXPathNavigable?displayProperty=nameWithType> como el objeto de datos a <xref:System.Diagnostics.TraceSource.TraceData%2A>.</span><span class="sxs-lookup"><span data-stu-id="ff783-308">When using <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType> to output traces, you can pass an <xref:System.Xml.XPath.IXPathNavigable?displayProperty=nameWithType> as the data object to <xref:System.Diagnostics.TraceSource.TraceData%2A>.</span></span> <span data-ttu-id="ff783-309">La entrada de seguimiento resultante incluye el XML proporcionado por <xref:System.Xml.XPath.XPathNavigator?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ff783-309">The resulting trace entry includes the XML provided by the <xref:System.Xml.XPath.XPathNavigator?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ff783-310">A continuación un ejemplo con datos de la aplicación XML:</span><span class="sxs-lookup"><span data-stu-id="ff783-310">Here is an example entry with XML application data:</span></span>  
  
```xml  
<E2ETraceEvent xmlns="http://schemas.microsoft.com/2004/06/E2ETraceEvent">  
  <System xmlns="...">  
    <EventID>12</EventID>  
    <Type>3</Type>  
    <SubType Name="Information">0</SubType>  
    <Level>8</Level>  
    <TimeCreated SystemTime="2006-01-13T22:58:03.0654832Z" />  
    <Source Name="Microsoft.ServiceModel.Samples.Udp" />  
    <Correlation ActivityID="{00000000-0000-0000-0000-000000000000}" />  
    <Execution  ProcessName="UdpTestConsole"
                ProcessID="3348" ThreadID="4" />  
    <Channel />  
    <Computer>COMPUTER-LT01</Computer>  
  </System>  
<!-- XML application data -->  
  <ApplicationData>  
  <TraceData>  
   <DataItem>  
   <TraceRecord
     Severity="Information"  
     xmlns="…">  
        <TraceIdentifier>some trace id</TraceIdentifier>  
        <Description>EndReceive called</Description>  
        <AppDomain>UdpTestConsole.exe</AppDomain>  
        <Source>UdpInputChannel</Source>  
      </TraceRecord>  
    </DataItem>  
  </TraceData>  
  </ApplicationData>  
</E2ETraceEvent>  
```  
  
 <span data-ttu-id="ff783-311">El visor de seguimiento de WCF entiende el esquema del `TraceRecord` elemento mostrado previamente y extrae los datos de sus elementos secundarios y los muestra en formato tabular.</span><span class="sxs-lookup"><span data-stu-id="ff783-311">The WCF trace viewer understands the schema of the `TraceRecord` element shown previously and extracts the data from its child elements and displays it in a tabular format.</span></span> <span data-ttu-id="ff783-312">Su canal debería utilizar este esquema al seguir paso a paso los datos de aplicación estructurados para ayudar a los usuarios de Svctraceviewer.exe a leer los datos.</span><span class="sxs-lookup"><span data-stu-id="ff783-312">Your channel should use this schema when tracing structured application data to help Svctraceviewer.exe users read the data.</span></span>
