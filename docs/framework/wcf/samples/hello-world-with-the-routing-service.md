---
description: 'Más información acerca de: Hola mundo con el servicio de enrutamiento'
title: "\"Hola mundo\" con el Servicio de enrutamiento"
ms.date: 03/30/2017
ms.assetid: 0f4b0d5b-6522-4ad5-9f3a-baa78316d7d1
ms.openlocfilehash: 1741c7d1f1e474864d66220fd160633997744876
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631975"
---
# <a name="hello-world-with-the-routing-service"></a><span data-ttu-id="e035a-103">"Hola mundo" con el Servicio de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="e035a-103">Hello World with the Routing Service</span></span>

<span data-ttu-id="e035a-104">Este ejemplo muestra el servicio de enrutamiento Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="e035a-104">This sample demonstrates the Windows Communication Foundation (WCF) Routing Service.</span></span> <span data-ttu-id="e035a-105">El servicio de enrutamiento es un componente de WCF que facilita la inclusión de un enrutador basado en contenido en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e035a-105">The Routing Service is a WCF component that makes it easy to include a content-based router in your application.</span></span> <span data-ttu-id="e035a-106">En este ejemplo se adapta el ejemplo de calculadora WCF estándar para comunicarse mediante el servicio de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="e035a-106">This sample adapts the standard WCF Calculator Sample to communicate using the Routing Service.</span></span> <span data-ttu-id="e035a-107">En este ejemplo, el cliente de la calculadora se configura para enviar los mensajes a un extremo que expone el enrutador.</span><span class="sxs-lookup"><span data-stu-id="e035a-107">In this sample, the Calculator client is configured to send messages to an endpoint exposed by the router.</span></span> <span data-ttu-id="e035a-108">El servicio de enrutamiento se configura para aceptar todos los mensajes que se le envíen y reenviarlos a un punto de conexión que corresponde al servicio de calculadora.</span><span class="sxs-lookup"><span data-stu-id="e035a-108">The Routing Service is configured to accept all messages sent to it and to forward them to an endpoint that corresponds to the Calculator service.</span></span> <span data-ttu-id="e035a-109">Por tanto, los mensajes enviados desde el cliente son recibidos por el enrutador y se vuelven a enrutar al servicio de calculadora real.</span><span class="sxs-lookup"><span data-stu-id="e035a-109">Thus messages sent from the client are received by the router and re-routed to the actual Calculator service.</span></span> <span data-ttu-id="e035a-110">Los mensajes del servicio de calculadora se devuelven al enrutador, que a su vez los devuelve al cliente de la calculadora.</span><span class="sxs-lookup"><span data-stu-id="e035a-110">Messages from the Calculator service are sent back to the router, which in turn passes them back to the Calculator client.</span></span>

### <a name="to-use-this-sample"></a><span data-ttu-id="e035a-111">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="e035a-111">To use this sample</span></span>

1. <span data-ttu-id="e035a-112">Con Visual Studio 2012, abra HelloRoutingService. sln.</span><span class="sxs-lookup"><span data-stu-id="e035a-112">Using Visual Studio 2012, open HelloRoutingService.sln.</span></span>

2. <span data-ttu-id="e035a-113">Presione F5 o CTRL+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="e035a-113">Press F5 or CTRL+SHIFT+B.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e035a-114">Si presiona F5, el cliente de la calculadora se inicia automáticamente.</span><span class="sxs-lookup"><span data-stu-id="e035a-114">If you press F5, the Calculator Client automatically starts.</span></span> <span data-ttu-id="e035a-115">Si presiona CTRL+MAYÚS+B (para compilar), debe iniciar las siguientes aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e035a-115">If you press CTRL+SHIFT+B (build), you must start following applications yourself.</span></span>
    >
    > 1. <span data-ttu-id="e035a-116">El cliente de la calculadora (./CalculatorClient/bin/client.exe)</span><span class="sxs-lookup"><span data-stu-id="e035a-116">Calculator client (./CalculatorClient/bin/client.exe</span></span>
    > 2. <span data-ttu-id="e035a-117">El servicio de calculadora (./CalculatorService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="e035a-117">Calculator service (./CalculatorService/bin/service.exe)</span></span>
    > 3. <span data-ttu-id="e035a-118">El servicio de enrutamiento (./RoutingService/bin/RoutingService.exe)</span><span class="sxs-lookup"><span data-stu-id="e035a-118">Routing service (./RoutingService/bin/RoutingService.exe)</span></span>

3. <span data-ttu-id="e035a-119">Presione Entrar para iniciar el cliente.</span><span class="sxs-lookup"><span data-stu-id="e035a-119">Press ENTER to start the client.</span></span>

     <span data-ttu-id="e035a-120">Debería ver la siguiente salida:</span><span class="sxs-lookup"><span data-stu-id="e035a-120">You should see the following output:</span></span>

    ```console
     Add(100,15.99) = 115.99

     Subtract(145,76.54) = 68.46

     Multiply(9,81.25) = 731.25

     Divide(22,7) = 3.14285714285714
    ```

## <a name="configurable-via-code-or-appconfig"></a><span data-ttu-id="e035a-121">Configurable a través de código o de un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="e035a-121">Configurable via Code or App.Config</span></span>

 <span data-ttu-id="e035a-122">El ejemplo viene configurado para utilizar un archivo App.config que define el comportamiento del enrutador.</span><span class="sxs-lookup"><span data-stu-id="e035a-122">The sample ships configured to use an App.config file to define the router’s behavior.</span></span> <span data-ttu-id="e035a-123">También puede cambiar el nombre del archivo de configuración por otro de modo que no se reconozca y quitar el comentario de la llamada al método ConfigureRouterViaCode().</span><span class="sxs-lookup"><span data-stu-id="e035a-123">You can also change the name of the App.config file to something else so that it is not recognized and uncomment the method call to ConfigureRouterViaCode().</span></span> <span data-ttu-id="e035a-124">Cualquier método provoca el mismo comportamiento del enrutador.</span><span class="sxs-lookup"><span data-stu-id="e035a-124">Either method results in the same behavior from the router.</span></span>

### <a name="scenario"></a><span data-ttu-id="e035a-125">Escenario</span><span class="sxs-lookup"><span data-stu-id="e035a-125">Scenario</span></span>

 <span data-ttu-id="e035a-126">En este ejemplo se muestra el enrutador que actúa como suministro de mensajes básico.</span><span class="sxs-lookup"><span data-stu-id="e035a-126">This sample demonstrates the router acting as a basic message pump.</span></span> <span data-ttu-id="e035a-127">El servicio de enrutamiento actúa como un nodo de proxy transparente configurado para pasar los mensajes a un conjunto preconfigurado de puntos de conexión de destino directamente.</span><span class="sxs-lookup"><span data-stu-id="e035a-127">The routing service acts as a transparent proxy node configured to pass messages directly to a preconfigured set of destination endpoints.</span></span>

### <a name="real-world-scenario"></a><span data-ttu-id="e035a-128">Escenario real</span><span class="sxs-lookup"><span data-stu-id="e035a-128">Real World Scenario</span></span>

 <span data-ttu-id="e035a-129">Contoso desea aumentar la flexibilidad que tiene en la denominación, tratamiento, configuración y seguridad de sus servicios.</span><span class="sxs-lookup"><span data-stu-id="e035a-129">Contoso wants to increase the flexibility it has in the naming, addressing, configuration, and security of its services.</span></span> <span data-ttu-id="e035a-130">Para ello, coloca un suministro de mensajes básico delante de sus servicios de modo que actúen como punto de conexión expuesto al público.</span><span class="sxs-lookup"><span data-stu-id="e035a-130">To do this, they place a basic message pump in front of their services to act as a public facing endpoint.</span></span> <span data-ttu-id="e035a-131">Esto les permite implantar seguridad adicional delante de sus servicios reales y facilitar la implementación de soluciones escaladas horizontalmente o de versiones del servicio más adelante.</span><span class="sxs-lookup"><span data-stu-id="e035a-131">This allows them to place additional security in front of their actual services and make it easier to implement scaled out solutions or service versioning at a later date.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e035a-132">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="e035a-132">The samples may already be installed on your computer.</span></span> <span data-ttu-id="e035a-133">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="e035a-133">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="e035a-134">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="e035a-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e035a-135">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="e035a-135">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\HelloRoutingService`  
  
## <a name="see-also"></a><span data-ttu-id="e035a-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="e035a-136">See also</span></span>

- <span data-ttu-id="e035a-137">[Ejemplos de hospedaje y persistencia de AppFabric](/previous-versions/appfabric/ff383418(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="e035a-137">[AppFabric Hosting and Persistence Samples](/previous-versions/appfabric/ff383418(v=azure.10))</span></span>
