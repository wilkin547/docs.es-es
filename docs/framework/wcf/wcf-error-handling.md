---
description: 'Más información sobre: control de errores de WCF'
title: Control de errores de WCF
ms.date: 03/30/2017
ms.assetid: 1e4b1e0f-9598-449d-9d73-90bda62305b8
ms.openlocfilehash: 57f2c5078e0f73ff57eec79041cb7a2b2d42b498
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99668180"
---
# <a name="wcf-error-handling"></a><span data-ttu-id="e2187-103">Control de errores de WCF</span><span class="sxs-lookup"><span data-stu-id="e2187-103">WCF Error Handling</span></span>

<span data-ttu-id="e2187-104">Los errores detectados por una aplicación WCF pertenecen a uno de los tres grupos:</span><span class="sxs-lookup"><span data-stu-id="e2187-104">The errors encountered by a WCF application belong to one of three groups:</span></span>  
  
1. <span data-ttu-id="e2187-105">Errores de comunicación</span><span class="sxs-lookup"><span data-stu-id="e2187-105">Communication Errors</span></span>  
  
2. <span data-ttu-id="e2187-106">Errores de proxy o canal</span><span class="sxs-lookup"><span data-stu-id="e2187-106">Proxy/Channel Errors</span></span>  
  
3. <span data-ttu-id="e2187-107">Errores de aplicación</span><span class="sxs-lookup"><span data-stu-id="e2187-107">Application Errors</span></span>  
  
 <span data-ttu-id="e2187-108">Los errores de comunicación se producen cuando una red no está disponible, un cliente usa una dirección incorrecta o el host de servicio no escucha los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="e2187-108">Communication errors occur when a network is unavailable, a client uses an incorrect address, or the service host is not listening for incoming messages.</span></span> <span data-ttu-id="e2187-109">Los errores de este tipo se devuelven al cliente como clase <xref:System.ServiceModel.CommunicationException> o clase derivada de la clase <xref:System.ServiceModel.CommunicationException>.</span><span class="sxs-lookup"><span data-stu-id="e2187-109">Errors of this type are returned to the client as <xref:System.ServiceModel.CommunicationException> or <xref:System.ServiceModel.CommunicationException>-derived classes.</span></span>  
  
 <span data-ttu-id="e2187-110">Los errores de proxy o canal son errores que se producen en el propio canal o proxy.</span><span class="sxs-lookup"><span data-stu-id="e2187-110">Proxy/Channel errors are errors that occur within the channel or proxy itself.</span></span> <span data-ttu-id="e2187-111">Los errores de este tipo incluyen: el intento por usar un proxy o canal cerrados, la existencia de una discrepancia entre el cliente y el servicio, o el rechazo de las credenciales del cliente por parte del servicio.</span><span class="sxs-lookup"><span data-stu-id="e2187-111">Errors of this type include: attempting to use a proxy or channel that has been closed, a contract mismatch exists between the client and service, or the client’s credentials are rejected by the service.</span></span> <span data-ttu-id="e2187-112">Existen muchos tipos de errores distintos en esta categoría, demasiados para enumerarlos aquí.</span><span class="sxs-lookup"><span data-stu-id="e2187-112">There are many different types of errors in this category, too many to list here.</span></span> <span data-ttu-id="e2187-113">Los errores de este tipo se devuelven al cliente tal cual (no se realiza ninguna transformación en los objetos de excepción).</span><span class="sxs-lookup"><span data-stu-id="e2187-113">Errors of this type are returned to the client as-is (no transformation is performed on the exception objects).</span></span>  
  
 <span data-ttu-id="e2187-114">Los errores de aplicación se producen durante la ejecución de una operación de servicio.</span><span class="sxs-lookup"><span data-stu-id="e2187-114">Application errors occur during the execution of a service operation.</span></span> <span data-ttu-id="e2187-115">Los errores de este tipo se envían al cliente como clase <xref:System.ServiceModel.FaultException> o clase <xref:System.ServiceModel.FaultException%601>.</span><span class="sxs-lookup"><span data-stu-id="e2187-115">Errors of this kind are sent to the client as <xref:System.ServiceModel.FaultException> or <xref:System.ServiceModel.FaultException%601>.</span></span>  
  
 <span data-ttu-id="e2187-116">El control de errores en WCF se realiza mediante una o varias de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="e2187-116">Error handling in WCF is performed by one or more of the following:</span></span>  
  
- <span data-ttu-id="e2187-117">Controlar directamente la excepción producida,</span><span class="sxs-lookup"><span data-stu-id="e2187-117">Directly handling the exception thrown.</span></span> <span data-ttu-id="e2187-118">que solo se lleva a cabo para errores de comunicación y de proxy o canal.</span><span class="sxs-lookup"><span data-stu-id="e2187-118">This is only done for communication and proxy/channel errors.</span></span>  
  
- <span data-ttu-id="e2187-119">Usar contratos de errores</span><span class="sxs-lookup"><span data-stu-id="e2187-119">Using fault contracts</span></span>  
  
- <span data-ttu-id="e2187-120">Implementar la interfaz <xref:System.ServiceModel.Dispatcher.IErrorHandler></span><span class="sxs-lookup"><span data-stu-id="e2187-120">Implementing the <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface</span></span>  
  
- <span data-ttu-id="e2187-121">Controlar eventos <xref:System.ServiceModel.ServiceHost></span><span class="sxs-lookup"><span data-stu-id="e2187-121">Handling <xref:System.ServiceModel.ServiceHost> events</span></span>  
  
## <a name="fault-contracts"></a><span data-ttu-id="e2187-122">Contrato de error</span><span class="sxs-lookup"><span data-stu-id="e2187-122">Fault Contracts</span></span>  

 <span data-ttu-id="e2187-123">Los contratos de error le permiten definir los errores que se pueden producir durante la operación de servicio en una plataforma de manera independiente.</span><span class="sxs-lookup"><span data-stu-id="e2187-123">Fault contracts allow you to define the errors that can occur during service operation in a platform independent way.</span></span> <span data-ttu-id="e2187-124">De forma predeterminada, todas las excepciones producidas desde una operación de servicio se devolverán al cliente como objeto <xref:System.ServiceModel.FaultException>.</span><span class="sxs-lookup"><span data-stu-id="e2187-124">By default all exceptions thrown from within a service operation will be returned to the client as a <xref:System.ServiceModel.FaultException> object.</span></span> <span data-ttu-id="e2187-125">El objeto <xref:System.ServiceModel.FaultException> contendrá muy poca información.</span><span class="sxs-lookup"><span data-stu-id="e2187-125">The <xref:System.ServiceModel.FaultException> object will contain very little information.</span></span> <span data-ttu-id="e2187-126">Puede controlar la información enviada al cliente mediante la definición de un contrato de error y la devolución del error como clase <xref:System.ServiceModel.FaultException%601>.</span><span class="sxs-lookup"><span data-stu-id="e2187-126">You can control the information sent to the client by defining a fault contract and returning the error as a <xref:System.ServiceModel.FaultException%601>.</span></span> <span data-ttu-id="e2187-127">Para obtener más información, vea [especificar y controlar errores en contratos y servicios](specifying-and-handling-faults-in-contracts-and-services.md).</span><span class="sxs-lookup"><span data-stu-id="e2187-127">For more information, see [Specifying and Handling Faults in Contracts and Services](specifying-and-handling-faults-in-contracts-and-services.md).</span></span>  
  
## <a name="ierrorhandler"></a><span data-ttu-id="e2187-128">IErrorHandler</span><span class="sxs-lookup"><span data-stu-id="e2187-128">IErrorHandler</span></span>  

 <span data-ttu-id="e2187-129">La interfaz <xref:System.ServiceModel.Dispatcher.IErrorHandler> le permite controlar más la respuesta de la aplicación WCF a los errores.</span><span class="sxs-lookup"><span data-stu-id="e2187-129">The <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface allows you more control over how your WCF application responds to errors.</span></span>  <span data-ttu-id="e2187-130">Proporciona control total sobre el mensaje de error devuelto al cliente y permite realizar el procesamiento de errores personalizado como el registro.</span><span class="sxs-lookup"><span data-stu-id="e2187-130">It gives you full control over the fault message that is returned to the client and allows you to perform custom error processing such as logging.</span></span>  <span data-ttu-id="e2187-131">Para obtener más información sobre el control de errores y la <xref:System.ServiceModel.Dispatcher.IErrorHandler> [generación de informes](./samples/extending-control-over-error-handling-and-reporting.md)</span><span class="sxs-lookup"><span data-stu-id="e2187-131">For more information about <xref:System.ServiceModel.Dispatcher.IErrorHandler> and [Extending Control Over Error Handling and Reporting](./samples/extending-control-over-error-handling-and-reporting.md)</span></span>  
  
## <a name="servicehost-events"></a><span data-ttu-id="e2187-132">Eventos ServiceHost</span><span class="sxs-lookup"><span data-stu-id="e2187-132">ServiceHost Events</span></span>  

 <span data-ttu-id="e2187-133">La clase <xref:System.ServiceModel.ServiceHost> hospeda servicios y define varios eventos que quizá sean necesarios para el control de errores.</span><span class="sxs-lookup"><span data-stu-id="e2187-133">The <xref:System.ServiceModel.ServiceHost> class hosts services and defines several events that may be needed for handling errors.</span></span> <span data-ttu-id="e2187-134">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e2187-134">For example:</span></span>  
  
1. <xref:System.ServiceModel.Channels.CommunicationObject.Faulted>
  
2. <xref:System.ServiceModel.ServiceHostBase.UnknownMessageReceived>
  
 <span data-ttu-id="e2187-135">Para obtener más información, vea <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="e2187-135">For more information, see <xref:System.ServiceModel.ServiceHost></span></span>
