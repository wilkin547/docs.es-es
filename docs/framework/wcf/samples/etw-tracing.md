---
title: Seguimiento ETW
description: Este ejemplo muestra cómo implementar el seguimiento de un extremo a otro (E2E) mediante el seguimiento de eventos para Windows (ETW) y ETWTraceListener.
ms.date: 03/30/2017
ms.assetid: ac99a063-e2d2-40cc-b659-d23c2f783f92
ms.openlocfilehash: 210186285ed749a5d1567becd6738939b0bd9d03
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244431"
---
# <a name="etw-tracing"></a><span data-ttu-id="ceeb7-103">Seguimiento ETW</span><span class="sxs-lookup"><span data-stu-id="ceeb7-103">ETW Tracing</span></span>
<span data-ttu-id="ceeb7-104">Este ejemplo muestra cómo implementar el seguimiento de un extremo a otro (E2E) mediante el Seguimiento de eventos para Windows (ETW) y `ETWTraceListener` que se proporciona este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-104">This sample demonstrates how to implement End-to-End (E2E) tracing using Event Tracing for Windows (ETW) and the `ETWTraceListener` that is provided with this sample.</span></span> <span data-ttu-id="ceeb7-105">El ejemplo se basa en el [Introducción](getting-started-sample.md) e incluye el seguimiento de ETW.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-105">The sample is based on the [Getting Started](getting-started-sample.md) and includes ETW tracing.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ceeb7-106">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-106">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="ceeb7-107">En este ejemplo se da por supuesto que está familiarizado con el [seguimiento y el registro de mensajes](tracing-and-message-logging.md).</span><span class="sxs-lookup"><span data-stu-id="ceeb7-107">This sample assumes that you are familiar with [Tracing and Message Logging](tracing-and-message-logging.md).</span></span>  
  
 <span data-ttu-id="ceeb7-108">Cada origen de seguimiento en el modelo de seguimiento<xref:System.Diagnostics> puede tener varios agentes de escucha de seguimiento que determinan donde y cómo se siguen paso a paso los datos.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-108">Each trace source in the <xref:System.Diagnostics> tracing model can have multiple trace listeners that determine where and how the data is traced.</span></span> <span data-ttu-id="ceeb7-109">El tipo de agente de escucha define el formato en el que la información de seguimiento está registrada.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-109">The type of listener defines the format in which trace data is logged.</span></span> <span data-ttu-id="ceeb7-110">El ejemplo de código siguiente muestra cómo agregar el agente de escucha a la configuración.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-110">The following code sample shows how to add the listener to configuration.</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
        <source name="System.ServiceModel"
             switchValue="Verbose,ActivityTracing"  
             propagateActivity="true">  
            <listeners>  
                <add type=  
                   "System.Diagnostics.DefaultTraceListener"  
                   name="Default">  
                   <filter type="" />  
                </add>  
                <add name="ETW">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
    </sources>  
    <sharedListeners>  
        <add type=  
            "Microsoft.ServiceModel.Samples.EtwTraceListener, ETWTraceListener"  
            name="ETW" traceOutputOptions="Timestamp">  
            <filter type="" />  
       </add>  
    </sharedListeners>  
</system.diagnostics>  
```  
  
 <span data-ttu-id="ceeb7-111">Antes de utilizar este agente de escucha, se debe iniciar una Sesión de seguimiento de ETW.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-111">Before using this listener, an ETW Trace Session must be started.</span></span> <span data-ttu-id="ceeb7-112">Esta sesión se puede iniciar utilizando Logman.exe o Tracelog.exe.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-112">This session can be started by using Logman.exe or Tracelog.exe.</span></span> <span data-ttu-id="ceeb7-113">Un archivo SetupETW.bat está incluido con este ejemplo para que pueda preparar la Sesión de seguimiento ETW junto con un archivo CleanupETW.bat para cerrar la sesión y completar el archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-113">A SetupETW.bat file is included with this sample so that you can set up the ETW Trace Session along with a CleanupETW.bat file for closing the session and completing the log file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ceeb7-114">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-114">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span> <span data-ttu-id="ceeb7-115">Para obtener más información acerca de estas herramientas, consulte<https://go.microsoft.com/fwlink/?LinkId=56580></span><span class="sxs-lookup"><span data-stu-id="ceeb7-115">For more information about these tools, see <https://go.microsoft.com/fwlink/?LinkId=56580></span></span>  
  
 <span data-ttu-id="ceeb7-116">Al utilizar ETWTraceListener, los rastros están registrados en archivos .etl binarios.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-116">When using the ETWTraceListener, traces are logged in binary .etl files.</span></span> <span data-ttu-id="ceeb7-117">Con el seguimiento ServiceModel activado, todos los rastros generados aparecen en el mismo archivo.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-117">With ServiceModel tracing turned on, all generated traces appear in the same file.</span></span> <span data-ttu-id="ceeb7-118">Use la [herramienta Service Trace Viewer (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) para ver los archivos de registro. ETL y. svclog.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-118">Use [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) for viewing .etl and .svclog log files.</span></span> <span data-ttu-id="ceeb7-119">El visor crea una vista de un extremo a otro del sistema que permite hacer el seguimiento un mensaje de su origen a su destino y punto de consumo.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-119">The viewer creates an end-to-end view of the system that makes it possible to trace a message from its source to its destination and point of consumption.</span></span>  
  
 <span data-ttu-id="ceeb7-120">El Agente de escucha de seguimiento de ETW admite el registro circular.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-120">The ETW Trace Listener supports circular logging.</span></span> <span data-ttu-id="ceeb7-121">Para habilitar esta característica, vaya a **Inicio**, **Ejecutar** y escriba `cmd` para iniciar una consola de comandos.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-121">To enable this feature, go to **Start**, **Run** and type `cmd` to start a command console.</span></span> <span data-ttu-id="ceeb7-122">En el comando siguiente, reemplace el parámetro `<logfilename>` con el nombre de su archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-122">In the following command, replace the `<logfilename>` parameter with the name of your log file.</span></span>  
  
```console  
logman create trace Wcf -o <logfilename> -p "{411a0819-c24b-428c-83e2-26b41091702e}" -f bincirc -max 1000  
```  
  
 <span data-ttu-id="ceeb7-123">Los modificadores `-f` y `-max` son opcionales.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-123">The `-f` and `-max` switches are optional.</span></span> <span data-ttu-id="ceeb7-124">Especifican respectivamente el formato circular binario y un tamaño de registro de máximo de 1000MB.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-124">They specify the binary circular format and max log size of 1000MB respectively.</span></span> <span data-ttu-id="ceeb7-125">El modificador `-p` se utiliza para especificar el proveedor de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-125">The `-p` switch is used to specify the trace provider.</span></span> <span data-ttu-id="ceeb7-126">En nuestro ejemplo, `"{411a0819-c24b-428c-83e2-26b41091702e}"` es el GUID para "Proveedor del Ejemplo de "XML ETW.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-126">In our example, `"{411a0819-c24b-428c-83e2-26b41091702e}"` is the GUID for "XML ETW Sample Provider".</span></span>  
  
 <span data-ttu-id="ceeb7-127">Para iniciar la sesión, escriba el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-127">To start the session, type in the following command.</span></span>  
  
```console  
logman start Wcf  
```  
  
 <span data-ttu-id="ceeb7-128">Después de haber terminado de registrarse, puede detener la sesión con el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-128">After you have finished logging, you can stop the session with the following command.</span></span>  
  
```console  
logman stop Wcf  
```  
  
 <span data-ttu-id="ceeb7-129">Este proceso genera registros circulares binarios que se pueden procesar con la herramienta de elección, incluida la [herramienta de visor de seguimiento de servicio (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) o tracerpt.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-129">This process generates binary circular logs that you can process with your tool of choice, including [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) or Tracerpt.</span></span>  
  
 <span data-ttu-id="ceeb7-130">También puede revisar el ejemplo de [seguimiento circular](circular-tracing.md) para obtener más información sobre un agente de escucha alternativo para realizar el registro circular.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-130">You can also review the [Circular Tracing](circular-tracing.md) sample for more information on an alternative listener to perform circular logging.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ceeb7-131">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="ceeb7-131">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="ceeb7-132">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ceeb7-132">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="ceeb7-133">Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ceeb7-133">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="ceeb7-134">Para utilizar los comandos RegisterProvider.bat, SetupETW.bat y CleanupETW.bat, debe ejecutarlos en una cuenta de administrador local.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-134">To use the RegisterProvider.bat, SetupETW.bat and CleanupETW.bat commands, you must run under a local administrator account.</span></span> <span data-ttu-id="ceeb7-135">Si usa Windows Vista o posterior, también debe ejecutar el símbolo del sistema con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-135">If you are using Windows Vista or later, you must also run the command prompt with elevated privileges.</span></span> <span data-ttu-id="ceeb7-136">Para ello, haga clic con el botón secundario en el icono símbolo del sistema y, a continuación, haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-136">To do so, right-click the command prompt icon, then click **Run as administrator**.</span></span>  
  
3. <span data-ttu-id="ceeb7-137">Antes de ejecutar el ejemplo, ejecute RegisterProvider.bat en el cliente y servidor.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-137">Before running the sample, run RegisterProvider.bat on the client and server.</span></span> <span data-ttu-id="ceeb7-138">Esto prepara el archivo ETWTracingSampleLog.etl resultante para generar rastros que puedan ser leídos por el visor de seguimiento de servicios.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-138">This sets up the resulting ETWTracingSampleLog.etl file to generate traces that can be read by the Service Trace Viewer.</span></span> <span data-ttu-id="ceeb7-139">Este archivo se puede buscar en la carpeta C:\logs.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-139">This file can be found in the C:\logs folder.</span></span> <span data-ttu-id="ceeb7-140">Si esta carpeta no existe, se debe crear; de lo contrario, no se generará ningún seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-140">If this folder does not exist, it must be created or no traces are generated.</span></span> <span data-ttu-id="ceeb7-141">A continuación, ejecute SetupETW.bat en los equipos servidor y cliente para comenzar la sesión de seguimiento de ETW.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-141">Then, run SetupETW.bat on the client and server computers to begin the ETW Trace Session.</span></span> <span data-ttu-id="ceeb7-142">El archivo SetupETW.bat se encuentra en la carpeta CS\Client.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-142">The SetupETW.bat file can be found under the CS\Client folder.</span></span>  
  
4. <span data-ttu-id="ceeb7-143">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ceeb7-143">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
5. <span data-ttu-id="ceeb7-144">Cuando complete el ejemplo, ejecute CleanupETW.bat para completar la creación del archivo ETWTracingSampleLog.etl.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-144">When the sample is completed, run CleanupETW.bat to complete the creation of the ETWTracingSampleLog.etl file.</span></span>  
  
6. <span data-ttu-id="ceeb7-145">Abra el archivo ETWTracingSampleLog.etl desde dentro del Visor de seguimiento de servicios.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-145">Open the ETWTracingSampleLog.etl file from within the Service Trace Viewer.</span></span> <span data-ttu-id="ceeb7-146">Le solicitarán que guarde el archivo con formato binario como un archivo .svclog.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-146">You will be prompted to save the binary formatted file as a .svclog file.</span></span>  
  
7. <span data-ttu-id="ceeb7-147">Abra el archivo .svclog creado recientemente desde el Visor de seguimiento de servicios para ver los seguimientos de ServiceModel y ETW.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-147">Open the newly created .svclog file from within the Service Trace Viewer to view the ETW and ServiceModel traces.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ceeb7-148">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-148">The samples may already be installed on your computer.</span></span> <span data-ttu-id="ceeb7-149">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-149">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="ceeb7-150">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-150">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ceeb7-151">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="ceeb7-151">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\AnalyticTrace`  
  
## <a name="see-also"></a><span data-ttu-id="ceeb7-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="ceeb7-152">See also</span></span>

- <span data-ttu-id="ceeb7-153">[Ejemplos de supervisión de AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="ceeb7-153">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
