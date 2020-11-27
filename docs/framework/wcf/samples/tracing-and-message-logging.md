---
title: Seguimiento y registro de mensajes
description: Obtenga información sobre cómo usar la herramienta Service Trace Viewer (SvcTraceViewer.exe) para ver los seguimientos y los registros de mensajes mediante este ejemplo de WFC.
ms.date: 03/30/2017
helpviewer_keywords:
- Tracing and logging
ms.assetid: a4f39bfc-3c5e-4d51-a312-71c5c3ce0afd
ms.openlocfilehash: ec29ac03e8930bd30ccd7e90dce3993ca9e7443a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255421"
---
# <a name="tracing-and-message-logging"></a><span data-ttu-id="5e862-103">Seguimiento y registro de mensajes</span><span class="sxs-lookup"><span data-stu-id="5e862-103">Tracing and Message Logging</span></span>

<span data-ttu-id="5e862-104">Este ejemplo muestra cómo habilitar el seguimiento y registro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="5e862-104">This sample demonstrates how to enable tracing and message logging.</span></span> <span data-ttu-id="5e862-105">Los seguimientos y registros de mensajes resultantes se ven mediante la [herramienta Service Trace Viewer (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md).</span><span class="sxs-lookup"><span data-stu-id="5e862-105">The resulting traces and message logs are viewed using the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="5e862-106">Este ejemplo se basa en el [Introducción](getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="5e862-106">This sample is based on the [Getting Started](getting-started-sample.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5e862-107">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="5e862-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="tracing"></a><span data-ttu-id="5e862-108">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="5e862-108">Tracing</span></span>  

 <span data-ttu-id="5e862-109">Windows Communication Foundation (WCF) utiliza el mecanismo de seguimiento definido en el <xref:System.Diagnostics> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="5e862-109">Windows Communication Foundation (WCF) uses the tracing mechanism defined in the <xref:System.Diagnostics> namespace.</span></span> <span data-ttu-id="5e862-110">Los orígenes de seguimiento que las aplicaciones implementan generan la información de seguimiento en este modelo de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="5e862-110">In this tracing model, trace data is produced by trace sources that applications implement.</span></span> <span data-ttu-id="5e862-111">Un nombre identifica cada origen.</span><span class="sxs-lookup"><span data-stu-id="5e862-111">Each source is identified by a name.</span></span> <span data-ttu-id="5e862-112">Los consumidores de seguimiento crean los agentes de escucha de seguimiento para los orígenes de seguimiento para los que desean recuperar información.</span><span class="sxs-lookup"><span data-stu-id="5e862-112">Trace consumers create trace listeners for the trace sources for which they want to retrieve information.</span></span> <span data-ttu-id="5e862-113">Debe crear un agente de escucha para que el origen de seguimiento reciba la información de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="5e862-113">To receive trace data, you must create a listener for the trace source.</span></span> <span data-ttu-id="5e862-114">En WCF, esto se puede hacer agregando el código siguiente al archivo de configuración del cliente o del servicio estableciendo el origen de seguimiento del modelo de servicio `switchValue` :</span><span class="sxs-lookup"><span data-stu-id="5e862-114">In WCF, this can be done by adding the following code to either the service’s or client’s configuration file by setting the Service Model trace source `switchValue`:</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Information,ActivityTracing"  
        propagateActivity="true">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name="System.ServiceModel.MessageLogging">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add initializeData="C:\logs\TracingAndLogging-service.svclog" type="System.Diagnostics.XmlWriterTraceListener"  
        name="xml" />  
    </sharedListeners>  
    <trace autoflush="true" />  
</system.diagnostics>  
```  
  
 <span data-ttu-id="5e862-115">Para obtener más información acerca de los orígenes de seguimiento, vea la sección origen de seguimiento en el tema [configurar el seguimiento](../diagnostics/tracing/configuring-tracing.md) .</span><span class="sxs-lookup"><span data-stu-id="5e862-115">For more information about trace sources, see the Trace Source section in the [Configuring Tracing](../diagnostics/tracing/configuring-tracing.md) topic.</span></span>  
  
## <a name="activity-tracing-and-propagation"></a><span data-ttu-id="5e862-116">Seguimiento de actividad y propagación</span><span class="sxs-lookup"><span data-stu-id="5e862-116">Activity Tracing and Propagation</span></span>  

 <span data-ttu-id="5e862-117">Tener `ActivityTracing` habilitado y `propagateActivity` establecido en `true` en los `system.ServiceModel` orígenes de seguimiento para el cliente y el servicio proporcionan la correlación de seguimientos dentro de las unidades lógicas de procesamiento (actividades), entre las actividades dentro de los extremos (a través de las transferencias de actividad) y entre las actividades que abarcan varios puntos de conexión (a través de la propagación de ID. de actividad).</span><span class="sxs-lookup"><span data-stu-id="5e862-117">Having `ActivityTracing` enabled and `propagateActivity` set to `true` in the `system.ServiceModel` trace sources for both the client and service provide correlation of traces within logical units of processing (activities), across activities within endpoints (through activity transfers), and across activities spanning multiple endpoints (through activity ID propagation).</span></span>  
  
 <span data-ttu-id="5e862-118">Estos tres mecanismos (actividades, transferencias y propagación) pueden ayudarle a buscar la causa principal de un error más rápidamente utilizando Service Trace Viewer tool.</span><span class="sxs-lookup"><span data-stu-id="5e862-118">These three mechanisms (activities, transfers, and propagation) can help you locate the root cause of an error more quickly using the Service Trace Viewer tool.</span></span> <span data-ttu-id="5e862-119">Para obtener más información, consulte [uso del visor de seguimiento de servicios para ver seguimientos correlacionados y solución de problemas](../diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="5e862-119">For more information, see [Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting](../diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).</span></span>  
  
 <span data-ttu-id="5e862-120">Es posible extender la traza que proporciona el ServiceModel al crear los rastros de actividad definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="5e862-120">It is possible to extend the tracing that is provided by the ServiceModel by creating user-defined activity traces.</span></span> <span data-ttu-id="5e862-121">El seguimiento de la actividad definido por el usuario le permite al usuario crear las actividades de seguimiento para:</span><span class="sxs-lookup"><span data-stu-id="5e862-121">User-defined activity tracing allows the user to create trace activities to:</span></span>  
  
- <span data-ttu-id="5e862-122">Agrupar rastros en las unidades lógicas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5e862-122">Group traces into logical units of work.</span></span>  
  
- <span data-ttu-id="5e862-123">Poner en correlación las actividades a través de las transferencias y la propagación.</span><span class="sxs-lookup"><span data-stu-id="5e862-123">Correlate activities through transfers and propagation.</span></span>  
  
- <span data-ttu-id="5e862-124">Reducir el costo de rendimiento del seguimiento de WCF (por ejemplo, el costo de espacio en disco de un archivo de registro).</span><span class="sxs-lookup"><span data-stu-id="5e862-124">Lessen the performance cost of WCF tracing (for example, the disk space cost of a log file).</span></span>  
  
 <span data-ttu-id="5e862-125">Para obtener más información sobre el seguimiento de la actividad definida por el usuario, consulte el ejemplo de [extensión de seguimiento](extending-tracing.md) .</span><span class="sxs-lookup"><span data-stu-id="5e862-125">For more information about user-defined activity trace, please see the [Extending Tracing](extending-tracing.md) sample.</span></span>  
  
## <a name="message-logging"></a><span data-ttu-id="5e862-126">Registro de mensajes</span><span class="sxs-lookup"><span data-stu-id="5e862-126">Message Logging</span></span>  

 <span data-ttu-id="5e862-127">El registro de mensajes se puede habilitar tanto en el cliente como en el servicio de cualquier aplicación WCF.</span><span class="sxs-lookup"><span data-stu-id="5e862-127">Message logging can be enabled both on the client and service of any WCF application.</span></span> <span data-ttu-id="5e862-128">Para habilitar el registro de mensajes, debe agregar el código siguiente al cliente o servicio:</span><span class="sxs-lookup"><span data-stu-id="5e862-128">To enable message logging, you must add the following code to either the client or service:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics>  
      <!-- Enable Message Logging here. -->  
      <!-- log all messages received or sent at the transport or service model levels -->  
      <messageLogging logEntireMessage="true"  
                      maxMessagesToLog="300"  
                      logMessagesAtServiceLevel="true"  
                      logMalformedMessages="true"  
                      logMessagesAtTransportLevel="true" />  
    </diagnostics>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="5e862-129">Cuando se graba un mensaje, el tipo de seguimiento depende de si se sigue paso a paso en el cliente o en el servidor.</span><span class="sxs-lookup"><span data-stu-id="5e862-129">When a message is recorded, the trace type depends on whether it is being traced at the client or the server.</span></span> <span data-ttu-id="5e862-130">Por ejemplo, un mensaje "Agregar" que se envía a un cliente se sigue paso a paso bajo la categoría "TransportWrite" en el cliente, mientras que el mismo mensaje se sigue paso a paso bajo la categoría "TransportRead" en el servicio.</span><span class="sxs-lookup"><span data-stu-id="5e862-130">For example, an "Add" message that is sent to a client is traced under the "TransportWrite" category at the client, whereas the same message is traced under the "TransportRead" category at the service.</span></span>  
  
 <span data-ttu-id="5e862-131">Configurar el agente de escucha de seguimiento agregando el código siguiente a la sección <xref:System.Diagnostics> del archivo App.config del cliente o el archivo Web.config del servicio:</span><span class="sxs-lookup"><span data-stu-id="5e862-131">Configure the trace listener by adding the following code to the <xref:System.Diagnostics> section of the client's App.config file or the service's Web.config file:</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Information,ActivityTracing"  
        propagateActivity="true">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name="System.ServiceModel.MessageLogging">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add initializeData="C:\logs\TracingAndLogging-client.svclog" type="System.Diagnostics.XmlWriterTraceListener"  
        name="xml" />  
    </sharedListeners>  
    <trace autoflush="true" />  
  </system.diagnostics>  
```  
  
 <span data-ttu-id="5e862-132">Los mensajes están registrados en formato XML en el directorio de destino especificado en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="5e862-132">Messages are logged in XML format in the target directory specified in the configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5e862-133">Los archivos de traza no se crean sin crear inicialmente el directorio de registro.</span><span class="sxs-lookup"><span data-stu-id="5e862-133">Trace files are not created without initially creating the log directory.</span></span> <span data-ttu-id="5e862-134">Asegurarse de que el directorio C:\logs\ existe, o especifique un directorio de registro alternativo en la configuración del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="5e862-134">Make sure that the directory C:\logs\ exists, or specify an alternate logging directory in the listener configuration.</span></span> <span data-ttu-id="5e862-135">Vea las instrucciones de configuración preliminar al final de este documento para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="5e862-135">See the initial setup instructions at the end of this document for more information.</span></span>  
  
 <span data-ttu-id="5e862-136">Para obtener más información acerca del registro de mensajes, consulte el tema [configuración del registro de mensajes](../diagnostics/configuring-message-logging.md) .</span><span class="sxs-lookup"><span data-stu-id="5e862-136">For more information about message logging, see the [Configuring Message Logging](../diagnostics/configuring-message-logging.md) topic.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="5e862-137">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="5e862-137">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="5e862-138">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5e862-138">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="5e862-139">Antes de ejecutar el ejemplo del Registro de mensajes y del seguimiento, cree el directorio C:\logs\ para que el servicio escriba los archivos .svc.</span><span class="sxs-lookup"><span data-stu-id="5e862-139">Before running the Tracing and Message Logging sample, create the directory C:\logs\ for the service to write the .svclog files to.</span></span> <span data-ttu-id="5e862-140">El nombre de este directorio se define en el archivo de configuración como la ruta de acceso para los rastros y los mensajes que han de registrarse y que pueden cambiarse.</span><span class="sxs-lookup"><span data-stu-id="5e862-140">The name of this directory is defined in the configuration file as the path for the traces and messages to be logged and can be changed.</span></span> <span data-ttu-id="5e862-141">Indique el acceso de escritura Network Service del usuario al directorio de registros.</span><span class="sxs-lookup"><span data-stu-id="5e862-141">Give the user Network Service write access to the logs directory.</span></span>  
  
3. <span data-ttu-id="5e862-142">Para compilar la edición de C#, C++ o Visual Basic .NET de la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5e862-142">To build the C#, C++, or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="5e862-143">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5e862-143">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="5e862-144">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="5e862-144">The samples may already be installed on your computer.</span></span> <span data-ttu-id="5e862-145">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="5e862-145">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="5e862-146">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="5e862-146">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5e862-147">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="5e862-147">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\TracingAndLogging`  
  
## <a name="see-also"></a><span data-ttu-id="5e862-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e862-148">See also</span></span>

- [<span data-ttu-id="5e862-149">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="5e862-149">Tracing</span></span>](../diagnostics/tracing/index.md)
- <span data-ttu-id="5e862-150">[Ejemplos de supervisión de AppFabric](/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="5e862-150">[AppFabric Monitoring Samples](/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
