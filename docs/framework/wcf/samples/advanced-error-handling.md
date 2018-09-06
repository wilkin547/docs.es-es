---
title: Control de errores avanzado
ms.date: 03/30/2017
ms.assetid: ed54b687-78af-4eda-8507-9fd081bdea1a
ms.openlocfilehash: 72fb9885408759f5781501b548f81625d258d13c
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43873921"
---
# <a name="advanced-error-handling"></a><span data-ttu-id="e9d8a-102">Control de errores avanzado</span><span class="sxs-lookup"><span data-stu-id="e9d8a-102">Advanced Error Handling</span></span>
<span data-ttu-id="e9d8a-103">Este ejemplo muestra el servicio de enrutamiento de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="e9d8a-103">This sample demonstrates the Windows Communication Foundation (WCF) routing service.</span></span> <span data-ttu-id="e9d8a-104">El servicio de enrutamiento es un componente WCF que facilita la tarea debe incluir un enrutador basado en contenido en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e9d8a-104">The routing service is a WCF component that makes it easy to include a content-based router in your application.</span></span> <span data-ttu-id="e9d8a-105">Este ejemplo muestra el modo en que el servicio de enrutamiento se recupera de los errores de forma inteligente, utilizando transacciones y otros conceptos de mensajería más complejos, como la multidifusión.</span><span class="sxs-lookup"><span data-stu-id="e9d8a-105">This sample shows how the routing service intelligently recovers from errors, using transactions and other more complex messaging concepts such as multicasting.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e9d8a-106">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="e9d8a-106">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e9d8a-107">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="e9d8a-107">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e9d8a-108">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="e9d8a-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e9d8a-109">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="e9d8a-109">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\AdvancedErrorHandling`  
  
## <a name="sample-details"></a><span data-ttu-id="e9d8a-110">Detalles del ejemplo</span><span class="sxs-lookup"><span data-stu-id="e9d8a-110">Sample Details</span></span>  
 <span data-ttu-id="e9d8a-111">En este ejemplo, el servicio de enrutamiento se configura para leer un mensaje de una cola de MSMQ y multidifundirlo a dos listas de colas.</span><span class="sxs-lookup"><span data-stu-id="e9d8a-111">In this sample, the routing service is configured to read a message from an MSMQ queue and multicast this message to two lists of queues.</span></span> <span data-ttu-id="e9d8a-112">Una lista se utiliza para las colas de servicios y la otra para las colas de registro.</span><span class="sxs-lookup"><span data-stu-id="e9d8a-112">One list is used for service queues and another is used for logging queues.</span></span>  
  
 <span data-ttu-id="e9d8a-113">Dado que, de forma predeterminada, el enlace MSMQ para el que el servicio de enrutamiento está configurado para usar admite el uso de transacciones, el servicio de enrutamiento se asegura de que el mensaje es transaccional y se recibe en al menos una cola de cada lista antes de informar a la cola entrante (`InQ`) de que el mensaje se enrutó correctamente.</span><span class="sxs-lookup"><span data-stu-id="e9d8a-113">Because, by default, the MSMQ binding that the routing service is configured to use supports the use of transactions, the routing service makes sure that the message is transactional and received by at least one queue in each list before reporting to the Inbound Queue (`InQ`) that the message was successfully routed.</span></span> <span data-ttu-id="e9d8a-114">Así, en el caso en el que tanto las colas de servicios como las colas de registro no estén disponibles, los informes del servicio de enrutamiento en las que no se pudo enrutar el mensaje y la cola entrante deberían actuar.</span><span class="sxs-lookup"><span data-stu-id="e9d8a-114">Thus, in the case where both of the service queues or both of the logging queues are unavailable, the routing service reports that the message could not be routed and the inbound queue should take some action.</span></span> <span data-ttu-id="e9d8a-115">Esta actuación consiste en mover el mensaje a la cola de mensajes no enviados del sistema.</span><span class="sxs-lookup"><span data-stu-id="e9d8a-115">This action consists of moving the message to the system dead letter queue.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="e9d8a-116">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="e9d8a-116">To use this sample</span></span>  
  
1.  > [!IMPORTANT]
    >  <span data-ttu-id="e9d8a-117">Instale MSMQ antes de ejecutar este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e9d8a-117">Install MSMQ before running this sample.</span></span> <span data-ttu-id="e9d8a-118">Si MSMQ no está instalado, se devuelve un mensaje de excepción al ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e9d8a-118">If MSMQ is not installed, an exception message is returned when running the sample.</span></span> <span data-ttu-id="e9d8a-119">Pueden encontrar instrucciones para instalar MSMQ en [instalar Message Queuing (MSMQ)](https://go.microsoft.com/fwlink/?LinkId=166437).</span><span class="sxs-lookup"><span data-stu-id="e9d8a-119">Instructions for installing MSMQ can be found at [Installing Message Queuing (MSMQ)](https://go.microsoft.com/fwlink/?LinkId=166437).</span></span>  
  
     <span data-ttu-id="e9d8a-120">Con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], abra AdvancedErrorHandling.sln.</span><span class="sxs-lookup"><span data-stu-id="e9d8a-120">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open AdvancedErrorHandling.sln.</span></span>  
  
2.  <span data-ttu-id="e9d8a-121">Presione **F5** o **CTRL + MAYÚS + B** en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e9d8a-121">Press **F5** or **CTRL+SHIFT+B** in Visual Studio.</span></span>  
  
    1.  <span data-ttu-id="e9d8a-122">Si compila la aplicación con CTRL+MAYÚS+B, debe iniciar la aplicación en ./RoutingService/bin/debug/RoutingService.exe.</span><span class="sxs-lookup"><span data-stu-id="e9d8a-122">If you build the application with CTRL+SHIFT+B, you must start the application at ./RoutingService/bin/debug/RoutingService.exe.</span></span>  
  
3.  <span data-ttu-id="e9d8a-123">En la ventana de la consola, presione ENTRAR para iniciar el cliente.</span><span class="sxs-lookup"><span data-stu-id="e9d8a-123">In the console window, press ENTER to start the client.</span></span>  
  
4.  <span data-ttu-id="e9d8a-124">El cliente devuelve estadísticas diferentes acerca de las colas en cada caso.</span><span class="sxs-lookup"><span data-stu-id="e9d8a-124">The client returns different statistics about the queues for each case.</span></span>  
  
    1.  <span data-ttu-id="e9d8a-125">El siguiente es el resultado devuelto para el caso 1 (no hay errores).</span><span class="sxs-lookup"><span data-stu-id="e9d8a-125">The following is the output returned for case 1 (no failures).</span></span>  
  
        ```Output  
        The inbound queue has 0 messages.  
        The primary service queue has 1 messages.   
        The backup service queue has 0 messages.   
        The primary logging queue has 1 messages.   
        The backup logging queue has 0 messages.   
        Press <Enter> to continue  
        ```  
  
    2.  <span data-ttu-id="e9d8a-126">El siguiente es el resultado devuelto para el caso 3 (errores en las colas de servicio y registro principales).</span><span class="sxs-lookup"><span data-stu-id="e9d8a-126">The following is the output returned for case 3 (primary service and logging queue failures).</span></span>  
  
        ```Output  
        The inbound queue has 0 messages.   
        The primary service queue does not exist.   
        The backup service queue has 1 messages.   
        The primary logging queue does not exist.   
        The backup logging queue has 1 messages.   
        Press <ENTER> to continue.  
        ```  
  
    3.  <span data-ttu-id="e9d8a-127">El siguiente es el resultado devuelto para el caso 4 (errores en las colas de registro principal y de reserva, y en la cola del servicio).</span><span class="sxs-lookup"><span data-stu-id="e9d8a-127">The following is the output returned for case 4 (primary service queue and primary and backup logging queue failures).</span></span>  
  
        ```Output  
        The inbound queue has 0 messages.   
        The primary service queue does not exist.  
        The backup service queue has 0 messages.   
        The primary logging queue does not exist.   
        The backup logging queue does not exist.   
        The System Dead Letter queue has 1 messages.   
        Press <ENTER> to Quit.  
        ```  
  
    4.  <span data-ttu-id="e9d8a-128">El siguiente es el resultado devuelto para el caso 2 (error en la cola de servicio principal).</span><span class="sxs-lookup"><span data-stu-id="e9d8a-128">The following is the output returned for case 2 (primary service queue failure).</span></span>  
  
        ```Output  
        The inbound queue has 0 messages.   
        The primary service queue does not exist.  
        The backup service queue has 1 messages.   
        The primary logging queue has 1 messages.   
        The backup logging queue has 0 messages.   
        Press <ENTER> to continue.  
        ```  
  
## <a name="configurable-via-code-or-appconfig"></a><span data-ttu-id="e9d8a-129">Configurable a través de código o App.onfig</span><span class="sxs-lookup"><span data-stu-id="e9d8a-129">Configurable Via Code or App.config</span></span>  
 <span data-ttu-id="e9d8a-130">El ejemplo viene configurado para utilizar un archivo App.config que define el comportamiento del enrutador.</span><span class="sxs-lookup"><span data-stu-id="e9d8a-130">The sample ships configured to use an App.config file to define the router’s behavior.</span></span> <span data-ttu-id="e9d8a-131">También puede cambiar el nombre del archivo RoutingService\App.config para que no se reconozca y cambiar el valor del campo `configDriven` en RoutingService\Program.cs a `false` para utilizar la configuración definida en el código.</span><span class="sxs-lookup"><span data-stu-id="e9d8a-131">You can also change the name of the RoutingService\App.config file to something else so that it is not recognized and change the value of the `configDriven` field in RoutingService\Program.cs to `false` to use the configuration defined in the code.</span></span> <span data-ttu-id="e9d8a-132">Cualquier método provoca el mismo comportamiento del enrutador.</span><span class="sxs-lookup"><span data-stu-id="e9d8a-132">Either method results in the same behavior from the router.</span></span>  
  
### <a name="scenario"></a><span data-ttu-id="e9d8a-133">Escenario</span><span class="sxs-lookup"><span data-stu-id="e9d8a-133">Scenario</span></span>  
 <span data-ttu-id="e9d8a-134">En este ejemplo se muestra que el servicio de enrutamiento puede administrar capacidades de mensajería avanzadas, como las transacciones y el contexto de recepción, y que puede utilizar estas capacidades como una parte de la administración correcta de los escenarios de error.</span><span class="sxs-lookup"><span data-stu-id="e9d8a-134">This sample demonstrates that the routing service can handle advanced messaging capabilities, such as transactions and receive context, and that it can utilize these capabilities as a part of correctly handling error scenarios.</span></span>  
  
### <a name="real-world-scenario"></a><span data-ttu-id="e9d8a-135">Escenario real</span><span class="sxs-lookup"><span data-stu-id="e9d8a-135">Real World Scenario</span></span>  
 <span data-ttu-id="e9d8a-136">Contoso desea utilizar las recepciones transaccionales a través del servicio de enrutamiento para asegurarse de que todos los servicios necesarios reciben información incluso durante condiciones de error.</span><span class="sxs-lookup"><span data-stu-id="e9d8a-136">Contoso wants to utilize transactional receives through the routing service to ensure that all necessary services receive information even during error conditions.</span></span> <span data-ttu-id="e9d8a-137">Además, desean administrar los errores de forma correcta y automática, y los errores que se van a notificar en el caso de que un mensaje no pueda entregarse ni siquiera cuando se utiliza la lógica de control de errores.</span><span class="sxs-lookup"><span data-stu-id="e9d8a-137">Furthermore, they would like errors to be handled correctly and automatically and failures to be reported in the case that a message is undeliverable even when error handling logic is utilized.</span></span> <span data-ttu-id="e9d8a-138">Para este propósito, configuran el servicio de enrutamiento para conmutar por error a puntos de conexión concretos según se prevea y para que el servicio del enrutamiento administre las situaciones de error, lo que incluye crear, completar y recuperar o anular los contextos de recepción y transacciones según convenga.</span><span class="sxs-lookup"><span data-stu-id="e9d8a-138">For this purpose, they configure the routing service to fail over to specific endpoints as expected and the routing service handles the error situations, which includes the creation, completion, and rollback/aborting of transactions/receive contexts as necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9d8a-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9d8a-139">See Also</span></span>  
 [<span data-ttu-id="e9d8a-140">Ejemplos de persistencia y el hospedaje de AppFabric</span><span class="sxs-lookup"><span data-stu-id="e9d8a-140">AppFabric Hosting and Persistence Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193961)
