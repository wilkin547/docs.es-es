---
title: "Extensión del seguimiento"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2b971a99-16ec-4949-ad2e-b0c8731a873f
caps.latest.revision: "28"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 235b1a8454d573264f0bbe3cd5f9809d88d08209
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="extending-tracing"></a><span data-ttu-id="f5183-102">Extensión del seguimiento</span><span class="sxs-lookup"><span data-stu-id="f5183-102">Extending Tracing</span></span>
<span data-ttu-id="f5183-103">Este ejemplo muestra cómo extender la característica de seguimiento de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] escribiendo el seguimiento de la actividad definida por el usuario en el código de cliente y de servicio.</span><span class="sxs-lookup"><span data-stu-id="f5183-103">This sample demonstrates how to extend the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] tracing feature by writing user-defined activity traces in client and service code.</span></span> <span data-ttu-id="f5183-104">Esto permite al usuario crear actividades de seguimiento y seguimientos de grupo en las unidades lógicas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f5183-104">This allows the user to create trace activities and group traces into logical units of work.</span></span> <span data-ttu-id="f5183-105">También es posible poner en correlación las actividades a través de las transferencias (dentro del mismo extremo) y propagación (a través de los extremos).</span><span class="sxs-lookup"><span data-stu-id="f5183-105">It is also possible to correlate activities through transfers (within the same endpoint) and propagation (across endpoints).</span></span> <span data-ttu-id="f5183-106">En este ejemplo, el seguimiento se habilita para el cliente y el servicio.</span><span class="sxs-lookup"><span data-stu-id="f5183-106">In this sample, tracing is enabled for both the client and the service.</span></span> <span data-ttu-id="f5183-107">Para obtener más información acerca de cómo habilitar el seguimiento en los archivos de configuración de cliente y el servicio, consulte [seguimiento y registro de mensajes](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).</span><span class="sxs-lookup"><span data-stu-id="f5183-107">For more information about how to enable tracing in client and service configuration files, see [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).</span></span>  
  
 <span data-ttu-id="f5183-108">En este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="f5183-108">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f5183-109">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="f5183-109">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f5183-110">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="f5183-110">The samples may already be installed on your computer.</span></span> <span data-ttu-id="f5183-111">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="f5183-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f5183-112">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f5183-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f5183-113">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="f5183-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ExtendingTracing`  
  
## <a name="tracing-and-activity-propagation"></a><span data-ttu-id="f5183-114">Propagación de seguimiento y de actividad</span><span class="sxs-lookup"><span data-stu-id="f5183-114">Tracing and Activity Propagation</span></span>  
 <span data-ttu-id="f5183-115">El seguimiento de actividad definida por el usuario permite al usuario crear sus propias actividades de seguimiento para agrupar seguimientos en unidades lógicas de trabajo, poner en correlación las actividades a través de transferencias y propagación, y disminuir el costo de rendimiento de la traza de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] (por ejemplo, el costo del espacio en disco de un archivo de registro).</span><span class="sxs-lookup"><span data-stu-id="f5183-115">User-defined activity tracing allows the user to create their own trace activities to group traces into logical units of work, correlate activities through transfers and propagation, and lessen the performance cost of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] tracing (for example, the disk space cost of a log file).</span></span>  
  
### <a name="adding-custom-sources"></a><span data-ttu-id="f5183-116">Adición de orígenes personalizados</span><span class="sxs-lookup"><span data-stu-id="f5183-116">Adding Custom Sources</span></span>  
 <span data-ttu-id="f5183-117">Los seguimientos definidos por el usuario pueden añadirse tanto al código de cliente como de servicio.</span><span class="sxs-lookup"><span data-stu-id="f5183-117">User-defined traces can be added to both client and service code.</span></span> <span data-ttu-id="f5183-118">Agregar orígenes de seguimiento para los archivos de configuración de cliente o servicio permiten estos seguimientos personalizados que se registran y se muestra en el [herramienta Service Trace Viewer (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span><span class="sxs-lookup"><span data-stu-id="f5183-118">Adding trace sources to the client or service configuration files allow for these custom traces to be recorded and displayed in the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="f5183-119">El código siguiente muestra cómo agregar un origen de seguimiento definido por el usuario denominado `ServerCalculatorTraceSource` al archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="f5183-119">The following code shows how to add a user-defined trace source named `ServerCalculatorTraceSource` to the configuration file.</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
        <source name="System.ServiceModel" switchValue="Warning" propagateActivity="true">  
            <listeners>  
                <add type="System.Diagnostics.DefaultTraceListener" name="Default">  
                    <filter type="" />  
                </add>  
                <add name="xml">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
        <source name="ServerCalculatorTraceSource" switchValue="Information,ActivityTracing">  
            <listeners>  
                <add type="System.Diagnostics.DefaultTraceListener" name="Default">  
                    <filter type="" />  
                </add>  
                <add name="xml">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
    </sources>  
    <sharedListeners>  
       <add initializeData="C:\logs\ServerTraces.svclog" type="System.Diagnostics.XmlWriterTraceListener"  
        name="xml" traceOutputOptions="Callstack">  
            <filter type="" />  
        </add>  
    </sharedListeners>  
    <trace autoflush="true" />  
</system.diagnostics>....  
....  
```  
  
### <a name="correlating-activities"></a><span data-ttu-id="f5183-120">Cómo poner en correlación las actividades</span><span class="sxs-lookup"><span data-stu-id="f5183-120">Correlating Activities</span></span>  
 <span data-ttu-id="f5183-121">Para poner en correlación directamente las actividades con los extremos, el atributo `propagateActivity` debe estar establecido en `true` en el origen de seguimiento `System.ServiceModel`.</span><span class="sxs-lookup"><span data-stu-id="f5183-121">To correlate activities directly across endpoints, the `propagateActivity` attribute must be set to `true` in the `System.ServiceModel` trace source.</span></span> <span data-ttu-id="f5183-122">Además, para propagar los seguimientos sin pasar por las actividades de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], se debe desactivar el seguimiento de la actividad de ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="f5183-122">Also, to propagate traces without going through [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] activities, ServiceModel Activity Tracing must be turned off.</span></span> <span data-ttu-id="f5183-123">Esto puede verse en el siguiente ejemplo de código:</span><span class="sxs-lookup"><span data-stu-id="f5183-123">This can be seen in the following code example.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f5183-124">Desactivar el seguimiento de actividades de ServiceModel no es igual que tener el nivel de seguimiento, indicado por la propiedad `switchValue`, definido en desactivado.</span><span class="sxs-lookup"><span data-stu-id="f5183-124">Turning off ServiceModel Activity Tracing is not the same as having the trace level, denoted by the `switchValue` property, set to off.</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Warning" propagateActivity="true">  
  
    ...  
  
       </source>  
    </sources>  
</system.diagnostics>  
```  
  
### <a name="lessening-performance-cost"></a><span data-ttu-id="f5183-125">Disminución del coste de rendimiento</span><span class="sxs-lookup"><span data-stu-id="f5183-125">Lessening Performance Cost</span></span>  
 <span data-ttu-id="f5183-126">Al establecer `ActivityTracing` en desactivado en el origen de seguimiento de `System.ServiceModel`, se genera un archivo de seguimiento que contiene solo seguimientos de actividad definidos por el usuario sin ninguno de los seguimientos de actividad de ServiceModel incluidos.</span><span class="sxs-lookup"><span data-stu-id="f5183-126">Setting `ActivityTracing` to off in the `System.ServiceModel` trace source generates a trace file that contains only user-defined activity traces, without any of the ServiceModel activity traces included.</span></span> <span data-ttu-id="f5183-127">Esto genera un archivo de registro de mucho menor tamaño.</span><span class="sxs-lookup"><span data-stu-id="f5183-127">This results in a log file of much smaller size.</span></span> <span data-ttu-id="f5183-128">Sin embargo, se pierde la oportunidad de poner en correlación los seguimientos de procesamiento de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5183-128">However, the opportunity to correlate [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] processing traces is lost.</span></span>  
  
##### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f5183-129">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="f5183-129">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="f5183-130">Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f5183-130">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="f5183-131">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f5183-131">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="f5183-132">Para ejecutar el ejemplo en una configuración de equipo único o varios, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f5183-132">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5183-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5183-133">See Also</span></span>  
 [<span data-ttu-id="f5183-134">Ejemplos de supervisión de AppFabric</span><span class="sxs-lookup"><span data-stu-id="f5183-134">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
