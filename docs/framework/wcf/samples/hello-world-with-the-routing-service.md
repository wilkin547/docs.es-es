---
title: "\"Hola mundo\" con el Servicio de enrutamiento"
ms.date: 03/30/2017
ms.assetid: 0f4b0d5b-6522-4ad5-9f3a-baa78316d7d1
ms.openlocfilehash: 3d91634d72481427f04e958f6dc2734829b6158b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253861"
---
# <a name="hello-world-with-the-routing-service"></a><span data-ttu-id="410c8-102">"Hola mundo" con el Servicio de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="410c8-102">Hello World with the Routing Service</span></span>

<span data-ttu-id="410c8-103">Este ejemplo muestra el servicio de enrutamiento Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="410c8-103">This sample demonstrates the Windows Communication Foundation (WCF) Routing Service.</span></span> <span data-ttu-id="410c8-104">El servicio de enrutamiento es un componente de WCF que facilita la inclusión de un enrutador basado en contenido en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="410c8-104">The Routing Service is a WCF component that makes it easy to include a content-based router in your application.</span></span> <span data-ttu-id="410c8-105">En este ejemplo se adapta el ejemplo de calculadora WCF estándar para comunicarse mediante el servicio de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="410c8-105">This sample adapts the standard WCF Calculator Sample to communicate using the Routing Service.</span></span> <span data-ttu-id="410c8-106">En este ejemplo, el cliente de la calculadora se configura para enviar los mensajes a un extremo que expone el enrutador.</span><span class="sxs-lookup"><span data-stu-id="410c8-106">In this sample, the Calculator client is configured to send messages to an endpoint exposed by the router.</span></span> <span data-ttu-id="410c8-107">El servicio de enrutamiento se configura para aceptar todos los mensajes que se le envíen y reenviarlos a un punto de conexión que corresponde al servicio de calculadora.</span><span class="sxs-lookup"><span data-stu-id="410c8-107">The Routing Service is configured to accept all messages sent to it and to forward them to an endpoint that corresponds to the Calculator service.</span></span> <span data-ttu-id="410c8-108">Por tanto, los mensajes enviados desde el cliente son recibidos por el enrutador y se vuelven a enrutar al servicio de calculadora real.</span><span class="sxs-lookup"><span data-stu-id="410c8-108">Thus messages sent from the client are received by the router and re-routed to the actual Calculator service.</span></span> <span data-ttu-id="410c8-109">Los mensajes del servicio de calculadora se devuelven al enrutador, que a su vez los devuelve al cliente de la calculadora.</span><span class="sxs-lookup"><span data-stu-id="410c8-109">Messages from the Calculator service are sent back to the router, which in turn passes them back to the Calculator client.</span></span>

### <a name="to-use-this-sample"></a><span data-ttu-id="410c8-110">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="410c8-110">To use this sample</span></span>

1. <span data-ttu-id="410c8-111">Con Visual Studio 2012, abra HelloRoutingService. sln.</span><span class="sxs-lookup"><span data-stu-id="410c8-111">Using Visual Studio 2012, open HelloRoutingService.sln.</span></span>

2. <span data-ttu-id="410c8-112">Presione F5 o CTRL+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="410c8-112">Press F5 or CTRL+SHIFT+B.</span></span>

    > [!NOTE]
    > <span data-ttu-id="410c8-113">Si presiona F5, el cliente de la calculadora se inicia automáticamente.</span><span class="sxs-lookup"><span data-stu-id="410c8-113">If you press F5, the Calculator Client automatically starts.</span></span> <span data-ttu-id="410c8-114">Si presiona CTRL+MAYÚS+B (para compilar), debe iniciar las siguientes aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="410c8-114">If you press CTRL+SHIFT+B (build), you must start following applications yourself.</span></span>
    >
    > 1. <span data-ttu-id="410c8-115">El cliente de la calculadora (./CalculatorClient/bin/client.exe)</span><span class="sxs-lookup"><span data-stu-id="410c8-115">Calculator client (./CalculatorClient/bin/client.exe</span></span>
    > 2. <span data-ttu-id="410c8-116">El servicio de calculadora (./CalculatorService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="410c8-116">Calculator service (./CalculatorService/bin/service.exe)</span></span>
    > 3. <span data-ttu-id="410c8-117">El servicio de enrutamiento (./RoutingService/bin/RoutingService.exe)</span><span class="sxs-lookup"><span data-stu-id="410c8-117">Routing service (./RoutingService/bin/RoutingService.exe)</span></span>

3. <span data-ttu-id="410c8-118">Presione Entrar para iniciar el cliente.</span><span class="sxs-lookup"><span data-stu-id="410c8-118">Press ENTER to start the client.</span></span>

     <span data-ttu-id="410c8-119">Debería ver la siguiente salida:</span><span class="sxs-lookup"><span data-stu-id="410c8-119">You should see the following output:</span></span>

    ```console
     Add(100,15.99) = 115.99

     Subtract(145,76.54) = 68.46

     Multiply(9,81.25) = 731.25

     Divide(22,7) = 3.14285714285714
    ```

## <a name="configurable-via-code-or-appconfig"></a><span data-ttu-id="410c8-120">Configurable a través de código o de un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="410c8-120">Configurable via Code or App.Config</span></span>

 <span data-ttu-id="410c8-121">El ejemplo viene configurado para utilizar un archivo App.config que define el comportamiento del enrutador.</span><span class="sxs-lookup"><span data-stu-id="410c8-121">The sample ships configured to use an App.config file to define the router’s behavior.</span></span> <span data-ttu-id="410c8-122">También puede cambiar el nombre del archivo de configuración por otro de modo que no se reconozca y quitar el comentario de la llamada al método ConfigureRouterViaCode().</span><span class="sxs-lookup"><span data-stu-id="410c8-122">You can also change the name of the App.config file to something else so that it is not recognized and uncomment the method call to ConfigureRouterViaCode().</span></span> <span data-ttu-id="410c8-123">Cualquier método provoca el mismo comportamiento del enrutador.</span><span class="sxs-lookup"><span data-stu-id="410c8-123">Either method results in the same behavior from the router.</span></span>

### <a name="scenario"></a><span data-ttu-id="410c8-124">Escenario</span><span class="sxs-lookup"><span data-stu-id="410c8-124">Scenario</span></span>

 <span data-ttu-id="410c8-125">En este ejemplo se muestra el enrutador que actúa como suministro de mensajes básico.</span><span class="sxs-lookup"><span data-stu-id="410c8-125">This sample demonstrates the router acting as a basic message pump.</span></span> <span data-ttu-id="410c8-126">El servicio de enrutamiento actúa como un nodo de proxy transparente configurado para pasar los mensajes a un conjunto preconfigurado de puntos de conexión de destino directamente.</span><span class="sxs-lookup"><span data-stu-id="410c8-126">The routing service acts as a transparent proxy node configured to pass messages directly to a preconfigured set of destination endpoints.</span></span>

### <a name="real-world-scenario"></a><span data-ttu-id="410c8-127">Escenario real</span><span class="sxs-lookup"><span data-stu-id="410c8-127">Real World Scenario</span></span>

 <span data-ttu-id="410c8-128">Contoso desea aumentar la flexibilidad que tiene en la denominación, tratamiento, configuración y seguridad de sus servicios.</span><span class="sxs-lookup"><span data-stu-id="410c8-128">Contoso wants to increase the flexibility it has in the naming, addressing, configuration, and security of its services.</span></span> <span data-ttu-id="410c8-129">Para ello, coloca un suministro de mensajes básico delante de sus servicios de modo que actúen como punto de conexión expuesto al público.</span><span class="sxs-lookup"><span data-stu-id="410c8-129">To do this, they place a basic message pump in front of their services to act as a public facing endpoint.</span></span> <span data-ttu-id="410c8-130">Esto les permite implantar seguridad adicional delante de sus servicios reales y facilitar la implementación de soluciones escaladas horizontalmente o de versiones del servicio más adelante.</span><span class="sxs-lookup"><span data-stu-id="410c8-130">This allows them to place additional security in front of their actual services and make it easier to implement scaled out solutions or service versioning at a later date.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="410c8-131">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="410c8-131">The samples may already be installed on your computer.</span></span> <span data-ttu-id="410c8-132">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="410c8-132">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="410c8-133">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="410c8-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="410c8-134">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="410c8-134">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\HelloRoutingService`  
  
## <a name="see-also"></a><span data-ttu-id="410c8-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="410c8-135">See also</span></span>

- <span data-ttu-id="410c8-136">[Ejemplos de hospedaje y persistencia de AppFabric](/previous-versions/appfabric/ff383418(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="410c8-136">[AppFabric Hosting and Persistence Samples](/previous-versions/appfabric/ff383418(v=azure.10))</span></span>
