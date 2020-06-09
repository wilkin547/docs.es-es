---
title: Extensión del seguimiento
ms.date: 03/30/2017
ms.assetid: 2b971a99-16ec-4949-ad2e-b0c8731a873f
ms.openlocfilehash: 59bdfeea41bac812840ffe166895050a6cd1ad2d
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600521"
---
# <a name="extend-tracing"></a><span data-ttu-id="b178f-102">Extender seguimiento</span><span class="sxs-lookup"><span data-stu-id="b178f-102">Extend tracing</span></span>

<span data-ttu-id="b178f-103">Este ejemplo muestra cómo extender la característica de seguimiento de Windows Communication Foundation (WCF) escribiendo seguimientos de actividad definidos por el usuario en el código del cliente y del servicio.</span><span class="sxs-lookup"><span data-stu-id="b178f-103">This sample demonstrates how to extend the Windows Communication Foundation (WCF) tracing feature by writing user-defined activity traces in client and service code.</span></span> <span data-ttu-id="b178f-104">Escribir seguimientos de actividad definidos por el usuario permite al usuario crear actividades de seguimiento y seguimientos de grupo en unidades lógicas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b178f-104">Writing user-defined activity traces allows the user to create trace activities and group traces into logical units of work.</span></span> <span data-ttu-id="b178f-105">También es posible poner en correlación las actividades a través de las transferencias (dentro del mismo punto de conexión) y propagación (a través de los puntos de conexión).</span><span class="sxs-lookup"><span data-stu-id="b178f-105">It is also possible to correlate activities through transfers (within the same endpoint) and propagation (across endpoints).</span></span> <span data-ttu-id="b178f-106">En este ejemplo, el seguimiento se habilita para el cliente y el servicio.</span><span class="sxs-lookup"><span data-stu-id="b178f-106">In this sample, tracing is enabled for both the client and the service.</span></span> <span data-ttu-id="b178f-107">Para obtener más información sobre cómo habilitar el seguimiento en los archivos de configuración de cliente y de servicio, vea [seguimiento y registro de mensajes](tracing-and-message-logging.md).</span><span class="sxs-lookup"><span data-stu-id="b178f-107">For more information about how to enable tracing in client and service configuration files, see [Tracing and Message Logging](tracing-and-message-logging.md).</span></span>  
  
 <span data-ttu-id="b178f-108">Este ejemplo se basa en el [Introducción](getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="b178f-108">This sample is based on the [Getting Started](getting-started-sample.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b178f-109">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="b178f-109">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b178f-110">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="b178f-110">The samples may already be installed on your computer.</span></span> <span data-ttu-id="b178f-111">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="b178f-111">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="b178f-112">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="b178f-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b178f-113">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="b178f-113">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ExtendingTracing`  
  
## <a name="tracing-and-activity-propagation"></a><span data-ttu-id="b178f-114">Propagación de seguimiento y de actividad</span><span class="sxs-lookup"><span data-stu-id="b178f-114">Tracing and Activity Propagation</span></span>  
 <span data-ttu-id="b178f-115">El seguimiento de la actividad definida por el usuario permite al usuario crear sus propias actividades de seguimiento para agrupar los seguimientos en unidades lógicas de trabajo, poner en correlación las actividades a través de las transferencias y la propagación, y reducir el costo de rendimiento del seguimiento de WCF (por ejemplo, el costo de espacio en disco de un archivo de registro).</span><span class="sxs-lookup"><span data-stu-id="b178f-115">User-defined activity tracing allows the user to create their own trace activities to group traces into logical units of work, correlate activities through transfers and propagation, and lessen the performance cost of WCF tracing (for example, the disk space cost of a log file).</span></span>  
  
### <a name="add-custom-sources"></a><span data-ttu-id="b178f-116">Agregar orígenes personalizados</span><span class="sxs-lookup"><span data-stu-id="b178f-116">Add custom sources</span></span>  
 <span data-ttu-id="b178f-117">Los seguimientos definidos por el usuario pueden añadirse tanto al código de cliente como de servicio.</span><span class="sxs-lookup"><span data-stu-id="b178f-117">User-defined traces can be added to both client and service code.</span></span> <span data-ttu-id="b178f-118">La adición de orígenes de seguimiento al cliente o los archivos de configuración de servicio permite que estos seguimientos personalizados se registren y se muestren en la [herramienta de visor de seguimiento de servicio (SvcTraceViewer. exe)](../service-trace-viewer-tool-svctraceviewer-exe.md).</span><span class="sxs-lookup"><span data-stu-id="b178f-118">Adding trace sources to the client or service configuration files allows for these custom traces to be recorded and displayed in the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="b178f-119">El código siguiente muestra cómo agregar un origen de seguimiento definido por el usuario denominado `ServerCalculatorTraceSource` al archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="b178f-119">The following code shows how to add a user-defined trace source named `ServerCalculatorTraceSource` to the configuration file.</span></span>  
  
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
</system.diagnostics>
....
```  
  
### <a name="correlate-activities"></a><span data-ttu-id="b178f-120">Correlación de actividades</span><span class="sxs-lookup"><span data-stu-id="b178f-120">Correlate activities</span></span>  
 <span data-ttu-id="b178f-121">Para poner en correlación directamente las actividades con los extremos, el atributo `propagateActivity` debe estar establecido en `true` en el origen de seguimiento `System.ServiceModel`.</span><span class="sxs-lookup"><span data-stu-id="b178f-121">To correlate activities directly across endpoints, the `propagateActivity` attribute must be set to `true` in the `System.ServiceModel` trace source.</span></span> <span data-ttu-id="b178f-122">Además, para propagar los seguimientos sin pasar por las actividades de WCF, el seguimiento de la actividad de ServiceModel debe estar desactivado.</span><span class="sxs-lookup"><span data-stu-id="b178f-122">Also, to propagate traces without going through WCF activities, ServiceModel Activity Tracing must be turned off.</span></span> <span data-ttu-id="b178f-123">Esto puede verse en el siguiente ejemplo de código:</span><span class="sxs-lookup"><span data-stu-id="b178f-123">This can be seen in the following code example.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b178f-124">Desactivar el seguimiento de actividades de ServiceModel no es igual que tener el nivel de seguimiento, indicado por la propiedad `switchValue`, definido en desactivado.</span><span class="sxs-lookup"><span data-stu-id="b178f-124">Turning off ServiceModel Activity Tracing is not the same as having the trace level, denoted by the `switchValue` property, set to off.</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Warning" propagateActivity="true">  
  
    ...  
  
       </source>  
    </sources>  
</system.diagnostics>  
```  
  
### <a name="lessen-performance-cost"></a><span data-ttu-id="b178f-125">Reducir el costo de rendimiento</span><span class="sxs-lookup"><span data-stu-id="b178f-125">Lessen performance cost</span></span>  
 <span data-ttu-id="b178f-126">Al establecer `ActivityTracing` en desactivado en el origen de seguimiento de `System.ServiceModel`, se genera un archivo de seguimiento que contiene solo seguimientos de actividad definidos por el usuario sin ninguno de los seguimientos de actividad de ServiceModel incluidos.</span><span class="sxs-lookup"><span data-stu-id="b178f-126">Setting `ActivityTracing` to off in the `System.ServiceModel` trace source generates a trace file that contains only user-defined activity traces, without any of the ServiceModel activity traces included.</span></span> <span data-ttu-id="b178f-127">La exclusión de los seguimientos de actividad de ServiceModel da como resultado un archivo de registro mucho más pequeño.</span><span class="sxs-lookup"><span data-stu-id="b178f-127">Excluding ServiceModel activity traces results in a much smaller log file.</span></span> <span data-ttu-id="b178f-128">Sin embargo, se pierde la oportunidad de correlacionar los seguimientos de procesamiento de WCF.</span><span class="sxs-lookup"><span data-stu-id="b178f-128">However, the opportunity to correlate WCF processing traces is lost.</span></span>  
  
## <a name="set-up-build-and-run-the-sample"></a><span data-ttu-id="b178f-129">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="b178f-129">Set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="b178f-130">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b178f-130">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="b178f-131">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b178f-131">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="b178f-132">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b178f-132">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b178f-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="b178f-133">See also</span></span>

- <span data-ttu-id="b178f-134">[Ejemplos de supervisión de AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="b178f-134">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
