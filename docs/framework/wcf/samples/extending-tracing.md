---
title: Extensión del seguimiento
ms.date: 03/30/2017
ms.assetid: 2b971a99-16ec-4949-ad2e-b0c8731a873f
ms.openlocfilehash: c6d62f6c334261b0dc897a1c1a2cd71d40ee4f51
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734920"
---
# <a name="extending-tracing"></a><span data-ttu-id="bbd1c-102">Extensión del seguimiento</span><span class="sxs-lookup"><span data-stu-id="bbd1c-102">Extending Tracing</span></span>
<span data-ttu-id="bbd1c-103">Este ejemplo muestra cómo extender la característica de seguimiento de Windows Communication Foundation (WCF) escribiendo seguimientos de actividad definidos por el usuario en el código del cliente y del servicio.</span><span class="sxs-lookup"><span data-stu-id="bbd1c-103">This sample demonstrates how to extend the Windows Communication Foundation (WCF) tracing feature by writing user-defined activity traces in client and service code.</span></span> <span data-ttu-id="bbd1c-104">Esto permite al usuario crear actividades de seguimiento y seguimientos de grupo en las unidades lógicas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bbd1c-104">This allows the user to create trace activities and group traces into logical units of work.</span></span> <span data-ttu-id="bbd1c-105">También es posible poner en correlación las actividades a través de las transferencias (dentro del mismo punto de conexión) y propagación (a través de los puntos de conexión).</span><span class="sxs-lookup"><span data-stu-id="bbd1c-105">It is also possible to correlate activities through transfers (within the same endpoint) and propagation (across endpoints).</span></span> <span data-ttu-id="bbd1c-106">En este ejemplo, el seguimiento se habilita para el cliente y el servicio.</span><span class="sxs-lookup"><span data-stu-id="bbd1c-106">In this sample, tracing is enabled for both the client and the service.</span></span> <span data-ttu-id="bbd1c-107">Para obtener más información sobre cómo habilitar el seguimiento en los archivos de configuración de cliente y de servicio, vea [seguimiento y registro de mensajes](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).</span><span class="sxs-lookup"><span data-stu-id="bbd1c-107">For more information about how to enable tracing in client and service configuration files, see [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).</span></span>  
  
 <span data-ttu-id="bbd1c-108">Este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="bbd1c-108">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bbd1c-109">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="bbd1c-109">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="bbd1c-110">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="bbd1c-110">The samples may already be installed on your computer.</span></span> <span data-ttu-id="bbd1c-111">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="bbd1c-111">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="bbd1c-112">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bbd1c-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bbd1c-113">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="bbd1c-113">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ExtendingTracing`  
  
## <a name="tracing-and-activity-propagation"></a><span data-ttu-id="bbd1c-114">Propagación de seguimiento y de actividad</span><span class="sxs-lookup"><span data-stu-id="bbd1c-114">Tracing and Activity Propagation</span></span>  
 <span data-ttu-id="bbd1c-115">El seguimiento de la actividad definida por el usuario permite al usuario crear sus propias actividades de seguimiento para agrupar los seguimientos en unidades lógicas de trabajo, poner en correlación las actividades a través de las transferencias y la propagación, y reducir el costo de rendimiento del seguimiento de WCF (por ejemplo, el costo de espacio en disco de un archivo de registro).</span><span class="sxs-lookup"><span data-stu-id="bbd1c-115">User-defined activity tracing allows the user to create their own trace activities to group traces into logical units of work, correlate activities through transfers and propagation, and lessen the performance cost of WCF tracing (for example, the disk space cost of a log file).</span></span>  
  
### <a name="adding-custom-sources"></a><span data-ttu-id="bbd1c-116">Adición de orígenes personalizados</span><span class="sxs-lookup"><span data-stu-id="bbd1c-116">Adding Custom Sources</span></span>  
 <span data-ttu-id="bbd1c-117">Los seguimientos definidos por el usuario pueden añadirse tanto al código de cliente como de servicio.</span><span class="sxs-lookup"><span data-stu-id="bbd1c-117">User-defined traces can be added to both client and service code.</span></span> <span data-ttu-id="bbd1c-118">La adición de orígenes de seguimiento a los archivos de configuración de cliente o de servicio permite grabar y mostrar estos seguimientos personalizados en la [herramienta de visor de seguimiento de servicio (SvcTraceViewer. exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span><span class="sxs-lookup"><span data-stu-id="bbd1c-118">Adding trace sources to the client or service configuration files allow for these custom traces to be recorded and displayed in the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="bbd1c-119">El código siguiente muestra cómo agregar un origen de seguimiento definido por el usuario denominado `ServerCalculatorTraceSource` al archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="bbd1c-119">The following code shows how to add a user-defined trace source named `ServerCalculatorTraceSource` to the configuration file.</span></span>  
  
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
  
### <a name="correlating-activities"></a><span data-ttu-id="bbd1c-120">Cómo poner en correlación las actividades</span><span class="sxs-lookup"><span data-stu-id="bbd1c-120">Correlating Activities</span></span>  
 <span data-ttu-id="bbd1c-121">Para poner en correlación directamente las actividades con los extremos, el atributo `propagateActivity` debe estar establecido en `true` en el origen de seguimiento `System.ServiceModel`.</span><span class="sxs-lookup"><span data-stu-id="bbd1c-121">To correlate activities directly across endpoints, the `propagateActivity` attribute must be set to `true` in the `System.ServiceModel` trace source.</span></span> <span data-ttu-id="bbd1c-122">Además, para propagar los seguimientos sin pasar por las actividades de WCF, el seguimiento de la actividad de ServiceModel debe estar desactivado.</span><span class="sxs-lookup"><span data-stu-id="bbd1c-122">Also, to propagate traces without going through WCF activities, ServiceModel Activity Tracing must be turned off.</span></span> <span data-ttu-id="bbd1c-123">Esto puede verse en el siguiente ejemplo de código:</span><span class="sxs-lookup"><span data-stu-id="bbd1c-123">This can be seen in the following code example.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bbd1c-124">Desactivar el seguimiento de actividades de ServiceModel no es igual que tener el nivel de seguimiento, indicado por la propiedad `switchValue`, definido en desactivado.</span><span class="sxs-lookup"><span data-stu-id="bbd1c-124">Turning off ServiceModel Activity Tracing is not the same as having the trace level, denoted by the `switchValue` property, set to off.</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Warning" propagateActivity="true">  
  
    ...  
  
       </source>  
    </sources>  
</system.diagnostics>  
```  
  
### <a name="lessening-performance-cost"></a><span data-ttu-id="bbd1c-125">Disminución del coste de rendimiento</span><span class="sxs-lookup"><span data-stu-id="bbd1c-125">Lessening Performance Cost</span></span>  
 <span data-ttu-id="bbd1c-126">Al establecer `ActivityTracing` en desactivado en el origen de seguimiento de `System.ServiceModel`, se genera un archivo de seguimiento que contiene solo seguimientos de actividad definidos por el usuario sin ninguno de los seguimientos de actividad de ServiceModel incluidos.</span><span class="sxs-lookup"><span data-stu-id="bbd1c-126">Setting `ActivityTracing` to off in the `System.ServiceModel` trace source generates a trace file that contains only user-defined activity traces, without any of the ServiceModel activity traces included.</span></span> <span data-ttu-id="bbd1c-127">Esto genera un archivo de registro de mucho menor tamaño.</span><span class="sxs-lookup"><span data-stu-id="bbd1c-127">This results in a log file of much smaller size.</span></span> <span data-ttu-id="bbd1c-128">Sin embargo, se pierde la oportunidad de correlacionar los seguimientos de procesamiento de WCF.</span><span class="sxs-lookup"><span data-stu-id="bbd1c-128">However, the opportunity to correlate WCF processing traces is lost.</span></span>  
  
##### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="bbd1c-129">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="bbd1c-129">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="bbd1c-130">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="bbd1c-130">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="bbd1c-131">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="bbd1c-131">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="bbd1c-132">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="bbd1c-132">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbd1c-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="bbd1c-133">See also</span></span>

- <span data-ttu-id="bbd1c-134">[Ejemplos de supervisión de AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="bbd1c-134">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
