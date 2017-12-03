---
title: "Reconfiguración dinámica"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b20786ae-cce6-4f91-b6cb-9cae116faf8b
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3146da86dcbe22f72ebedec57c87ac0a29ed1946
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="dynamic-reconfiguration"></a><span data-ttu-id="e0796-102">Reconfiguración dinámica</span><span class="sxs-lookup"><span data-stu-id="e0796-102">Dynamic Reconfiguration</span></span>
<span data-ttu-id="e0796-103">En este ejemplo se muestra el servicio de enrutamiento de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e0796-103">This sample demonstrates the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] routing service.</span></span> <span data-ttu-id="e0796-104">El servicio de enrutamiento es un componente de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que permite incluir fácilmente un enrutador basado en contenido en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="e0796-104">The routing service is a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] component that makes it easy to include a content-based router in your application.</span></span> <span data-ttu-id="e0796-105">En este ejemplo se adapta el ejemplo de la calculadora de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] estándar para comunicarse utilizando el servicio de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="e0796-105">This sample adapts the standard [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Calculator Sample to communicate using the routing service.</span></span> <span data-ttu-id="e0796-106">En este ejemplo se muestra el modo en que el servicio de enrutamiento puede reconfigurarse dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e0796-106">This sample shows how the routing service can be dynamically reconfigured during runtime.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e0796-107">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="e0796-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="e0796-108">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="e0796-108">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e0796-109">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e0796-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e0796-110">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="e0796-110">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\DynamicReconfiguration`  
  
## <a name="sample-details"></a><span data-ttu-id="e0796-111">Detalles del ejemplo</span><span class="sxs-lookup"><span data-stu-id="e0796-111">Sample Details</span></span>  
 <span data-ttu-id="e0796-112">Para reconfigurar el servicio de enrutamiento en tiempo de ejecución de forma dinámica, este ejemplo desencadena un temporizador cada cinco segundos que crea un nuevo objeto <xref:System.ServiceModel.Routing.RoutingConfiguration> y lo aplica.</span><span class="sxs-lookup"><span data-stu-id="e0796-112">To dynamically reconfigure the routing service during runtime, this sample fires a timer every five seconds that creates a new <xref:System.ServiceModel.Routing.RoutingConfiguration> object and applies it.</span></span> <span data-ttu-id="e0796-113">Esta configuración hace referencia al extremo de la calculadora normal o al extremo de la calculadora de redondeo.</span><span class="sxs-lookup"><span data-stu-id="e0796-113">This configuration references either the regular Calculator endpoint or the Rounding Calculator endpoint.</span></span> <span data-ttu-id="e0796-114">La aplicación cliente de la calculadora hace que sus mensajes sean devueltos por un servicio u otro, según a qué servicio de enrutamiento esté configurado para enrutar en ese momento.</span><span class="sxs-lookup"><span data-stu-id="e0796-114">The Calculator Client application has its messages returned from one service or the other, depending on which one the routing service is configured to route to at that time.</span></span>  
  
 <span data-ttu-id="e0796-115">La capacidad del servicio de enrutamiento se usa para la reconfiguración dinámica a través de un comportamiento personalizado.</span><span class="sxs-lookup"><span data-stu-id="e0796-115">The routing service’s capabilitiy for dynamic reconfiguration through a custom behavior is used.</span></span> <span data-ttu-id="e0796-116">Este comportamiento personalizado asocia una extensión de servicio, que contiene un sencillo temporizador de subprocesos que se desencadena cada cinco segundos y que resulta en una devolución de llamada al método `UpdateRules`.</span><span class="sxs-lookup"><span data-stu-id="e0796-116">This custom behavior attaches a service extension, which contains a simple thread timer that fires every five seconds, which results in a callback to the `UpdateRules` method.</span></span> <span data-ttu-id="e0796-117">Esta devolución de llamada crea y aplica la nueva configuración de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="e0796-117">This callback creates and applies the new routing configuration.</span></span> <span data-ttu-id="e0796-118">En una implementación real, esta devolución de llamada probablemente se lograría como resultado de algún otro tipo de evento, como una notificación de evento SQL o un anuncio de detección del WS.</span><span class="sxs-lookup"><span data-stu-id="e0796-118">In an actual deployment, this callback would likely be accomplished as a result of some other type of event, such as a SQL-Event notification, or a WS-Discovery announcement.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="e0796-119">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="e0796-119">To use this sample</span></span>  
  
1.  <span data-ttu-id="e0796-120">Con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], abra DynamicReconfiguration.sln.</span><span class="sxs-lookup"><span data-stu-id="e0796-120">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open DynamicReconfiguration.sln.</span></span>  
  
2.  <span data-ttu-id="e0796-121">Para abrir **el Explorador de soluciones**, seleccione **el Explorador de soluciones** desde el **vista** menú.</span><span class="sxs-lookup"><span data-stu-id="e0796-121">To open **Solution Explorer**, select **Solution Explorer** from the **View** menu.</span></span>  
  
3.  <span data-ttu-id="e0796-122">Presione **F5** o **CTRL + MAYÚS + B** en [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e0796-122">Press **F5** or **CTRL+SHIFT+B** in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span></span>  
  
    1.  <span data-ttu-id="e0796-123">Si desea iniciar de forma automática los proyectos necesarios al presionar **F5**, haga clic en la solución y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e0796-123">If you would like to auto-launch the necessary projects when you press **F5**, right-click the solution and select **Properties**.</span></span> <span data-ttu-id="e0796-124">Seleccione el **proyecto de inicio** nodo bajo **propiedades comunes** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="e0796-124">Select the **Startup Project** node under **Common Properties** in the left pane.</span></span> <span data-ttu-id="e0796-125">Seleccione el **proyectos de inicio múltiples** botón de radio y establecer todos los proyectos que tienen el **iniciar** acción.</span><span class="sxs-lookup"><span data-stu-id="e0796-125">Select the **Multiple Startup Projects**  radio button and set all of the projects to have the **Start** action.</span></span>  
  
    2.  <span data-ttu-id="e0796-126">Si compila el proyecto con **CTRL + MAYÚS + B**, debe iniciar las siguientes aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="e0796-126">If you build the project with **CTRL+SHIFT+B**, you must start the following applications:</span></span>  
  
        1.  <span data-ttu-id="e0796-127">El cliente de la calculadora (./CalculatorClient/bin/client.exe)</span><span class="sxs-lookup"><span data-stu-id="e0796-127">Calculator Client (./CalculatorClient/bin/client.exe)</span></span>  
  
        2.  <span data-ttu-id="e0796-128">El servicio de calculadora (./CalculatorService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="e0796-128">Calculator Service (./CalculatorService/bin/service.exe)</span></span>  
  
        3.  <span data-ttu-id="e0796-129">El servicio de enrutamiento de calculadora (./RoundingCalcService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="e0796-129">Routing Calculator Service (./RoundingCalcService/bin/service.exe)</span></span>  
  
        4.  <span data-ttu-id="e0796-130">RoutingService (./RoutingService/bin/RoutingService.exe)</span><span class="sxs-lookup"><span data-stu-id="e0796-130">RoutingService (./RoutingService/bin/RoutingService.exe)</span></span>  
  
4.  <span data-ttu-id="e0796-131">En la ventana de la consola del cliente de la calculadora, presione ENTRAR para iniciar el cliente y llame a las operaciones de servicio de calculadora.</span><span class="sxs-lookup"><span data-stu-id="e0796-131">In the console window of the Calculator Client, press ENTER to start the client and to call the Calculator service operations.</span></span>  
  
     <span data-ttu-id="e0796-132">El servicio de enrutamiento enruta los mensajes a la calculadora de redondeo y o bien a la calculadora normal ya que la configuración de enrutamiento cambia dinámicamente cada cinco segundos.</span><span class="sxs-lookup"><span data-stu-id="e0796-132">The routing service routes messages to the Rounding Calculator and to the regular Calculator alternately as the routing configuration changes dynamically every five seconds.</span></span> <span data-ttu-id="e0796-133">Según el extremo al que el servicio de enrutamiento está configurado para enviar los mensajes, hay diferentes resultados en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="e0796-133">Depending on which endpoint the routing service is configured to send messages to there are different outputs in the client console window.</span></span>  
  
5.  <span data-ttu-id="e0796-134">Siga presionando ENTRAR varias veces durante más de cinco segundos y observe el cambio en los resultados del servicio.</span><span class="sxs-lookup"><span data-stu-id="e0796-134">Continue pressing ENTER repeatedly over more than five seconds and observe the change in the results from the service.</span></span>  
  
    1.  <span data-ttu-id="e0796-135">Lo siguiente es el resultado que se devuelve si el servicio de enrutador está configurado para enrutar los mensajes al servicio de calculadora de redondeo.</span><span class="sxs-lookup"><span data-stu-id="e0796-135">The following is the output returned if the Router Service is configured to route messages to the Rounding Calculator service.</span></span>  
  
        ```Output  
        Add(100,15.99) = 116  
        Subtract(145,76.54) = 68.5  
        Multiply(9,81.25) = 731.2  
        Divide(22,7) = 3.1  
        ```  
  
    2.  <span data-ttu-id="e0796-136">Lo siguiente es el resultado que se devuelve si el servicio de enrutamiento está configurado para enrutar los mensajes al servicio de calculadora de redondeo.</span><span class="sxs-lookup"><span data-stu-id="e0796-136">The following is the output returned if the routing service is configured to route messages to the regular Calculator service.</span></span>  
  
        ```Output  
        Add(100,15.99) = 115.99  
        Subtract(145,76.54) = 68.46  
        Multiply(9,81.25) = 731.25  
        Divide(22,7) = 3.14285714285714  
        ```  
  
6.  <span data-ttu-id="e0796-137">El servicio de calculadora y el servicio de calculadora de redondeo también imprimen un registro de las operaciones invocadas en sus respectivas ventanas de consola.</span><span class="sxs-lookup"><span data-stu-id="e0796-137">The Calculator Service and the Rounding Calculator Service also print out a log of the operations invoked to their respective console windows.</span></span>  
  
7.  <span data-ttu-id="e0796-138">En la ventana de la consola de cliente, escriba "quit" y presione ENTRAR para salir.</span><span class="sxs-lookup"><span data-stu-id="e0796-138">In the client console window, type "quit" and press ENTER to exit.</span></span>  
  
8.  <span data-ttu-id="e0796-139">Presione ENTRAR en las ventanas de la consola de servicios para terminar los servicios.</span><span class="sxs-lookup"><span data-stu-id="e0796-139">Press ENTER in the services console windows to terminate the services.</span></span>  
  
## <a name="scenario"></a><span data-ttu-id="e0796-140">Escenario</span><span class="sxs-lookup"><span data-stu-id="e0796-140">Scenario</span></span>  
 <span data-ttu-id="e0796-141">En este ejemplo se muestra el enrutador que actúa como enrutador basado en contenido que permite exponer varios tipos o la implementación de los servicios a través de un extremo.</span><span class="sxs-lookup"><span data-stu-id="e0796-141">This sample demonstrates the router acting as a content-based router allowing multiple types or implementation of services to be exposed through one endpoint.</span></span>  
  
### <a name="real-world-scenario"></a><span data-ttu-id="e0796-142">Escenario real</span><span class="sxs-lookup"><span data-stu-id="e0796-142">Real World Scenario</span></span>  
 <span data-ttu-id="e0796-143">Contoso desea virtualizar todos sus servicios para exponer solo un extremo a través del que ofrecer acceso a varios tipos diferentes de servicios públicamente.</span><span class="sxs-lookup"><span data-stu-id="e0796-143">Contoso wants to virtualize all of their services to expose only one endpoint publicly through which they offer access to multiple different types of services.</span></span> <span data-ttu-id="e0796-144">En este caso, utilizan las capacidades de enrutamiento basado en contenido del servicio de enrutamiento para determinar dónde se deberían enviar las solicitudes entrantes.</span><span class="sxs-lookup"><span data-stu-id="e0796-144">In this case they utilize the routing service’s content-based routing capabilities to determine where the incoming requests should be sent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0796-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0796-145">See Also</span></span>  
 [<span data-ttu-id="e0796-146">Ejemplos de persistencia y el hospedaje de AppFabric</span><span class="sxs-lookup"><span data-stu-id="e0796-146">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
