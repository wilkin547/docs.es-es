---
title: Seguimiento ETW
ms.date: 03/30/2017
ms.assetid: ac99a063-e2d2-40cc-b659-d23c2f783f92
ms.openlocfilehash: 07379a464e6635a3de10c08647dbc769a5885e4e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183706"
---
# <a name="etw-tracing"></a><span data-ttu-id="8bf8b-102">Seguimiento ETW</span><span class="sxs-lookup"><span data-stu-id="8bf8b-102">ETW Tracing</span></span>
<span data-ttu-id="8bf8b-103">Este ejemplo muestra cómo implementar el seguimiento de un extremo a otro (E2E) mediante el Seguimiento de eventos para Windows (ETW) y `ETWTraceListener` que se proporciona este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-103">This sample demonstrates how to implement End-to-End (E2E) tracing using Event Tracing for Windows (ETW) and the `ETWTraceListener` that is provided with this sample.</span></span> <span data-ttu-id="8bf8b-104">El ejemplo se basa en la [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md) e incluye el seguimiento ETW.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) and includes ETW tracing.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8bf8b-105">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-105">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="8bf8b-106">En este ejemplo se supone que está familiarizado con [El seguimiento y](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md)el registro de mensajes .</span><span class="sxs-lookup"><span data-stu-id="8bf8b-106">This sample assumes that you are familiar with [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).</span></span>  
  
 <span data-ttu-id="8bf8b-107">Cada origen de seguimiento en el modelo de seguimiento<xref:System.Diagnostics> puede tener varios agentes de escucha de seguimiento que determinan donde y cómo se siguen paso a paso los datos.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-107">Each trace source in the <xref:System.Diagnostics> tracing model can have multiple trace listeners that determine where and how the data is traced.</span></span> <span data-ttu-id="8bf8b-108">El tipo de agente de escucha define el formato en el que la información de seguimiento está registrada.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-108">The type of listener defines the format in which trace data is logged.</span></span> <span data-ttu-id="8bf8b-109">El ejemplo de código siguiente muestra cómo agregar el agente de escucha a la configuración.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-109">The following code sample shows how to add the listener to configuration.</span></span>  
  
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
  
 <span data-ttu-id="8bf8b-110">Antes de utilizar este agente de escucha, se debe iniciar una Sesión de seguimiento de ETW.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-110">Before using this listener, an ETW Trace Session must be started.</span></span> <span data-ttu-id="8bf8b-111">Esta sesión se puede iniciar utilizando Logman.exe o Tracelog.exe.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-111">This session can be started by using Logman.exe or Tracelog.exe.</span></span> <span data-ttu-id="8bf8b-112">Un archivo SetupETW.bat está incluido con este ejemplo para que pueda preparar la Sesión de seguimiento ETW junto con un archivo CleanupETW.bat para cerrar la sesión y completar el archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-112">A SetupETW.bat file is included with this sample so that you can set up the ETW Trace Session along with a CleanupETW.bat file for closing the session and completing the log file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8bf8b-113">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-113">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span> <span data-ttu-id="8bf8b-114">Para obtener más información acerca de estas herramientas, consulte<https://go.microsoft.com/fwlink/?LinkId=56580></span><span class="sxs-lookup"><span data-stu-id="8bf8b-114">For more information about these tools, see <https://go.microsoft.com/fwlink/?LinkId=56580></span></span>  
  
 <span data-ttu-id="8bf8b-115">Al utilizar ETWTraceListener, los rastros están registrados en archivos .etl binarios.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-115">When using the ETWTraceListener, traces are logged in binary .etl files.</span></span> <span data-ttu-id="8bf8b-116">Con el seguimiento ServiceModel activado, todos los rastros generados aparecen en el mismo archivo.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-116">With ServiceModel tracing turned on, all generated traces appear in the same file.</span></span> <span data-ttu-id="8bf8b-117">Utilice la herramienta [Service Trace Viewer (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) para ver los archivos de registro .etl y .svclog.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-117">Use [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) for viewing .etl and .svclog log files.</span></span> <span data-ttu-id="8bf8b-118">El visor crea una vista de un extremo a otro del sistema que permite hacer el seguimiento un mensaje de su origen a su destino y punto de consumo.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-118">The viewer creates an end-to-end view of the system that makes it possible to trace a message from its source to its destination and point of consumption.</span></span>  
  
 <span data-ttu-id="8bf8b-119">El Agente de escucha de seguimiento de ETW admite el registro circular.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-119">The ETW Trace Listener supports circular logging.</span></span> <span data-ttu-id="8bf8b-120">Para habilitar esta característica, vaya a `cmd` **Inicio**, **Ejecutar** y escriba para iniciar una consola de comandos.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-120">To enable this feature, go to **Start**, **Run** and type `cmd` to start a command console.</span></span> <span data-ttu-id="8bf8b-121">En el comando siguiente, reemplace el parámetro `<logfilename>` con el nombre de su archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-121">In the following command, replace the `<logfilename>` parameter with the name of your log file.</span></span>  
  
```console  
logman create trace Wcf -o <logfilename> -p "{411a0819-c24b-428c-83e2-26b41091702e}" -f bincirc -max 1000  
```  
  
 <span data-ttu-id="8bf8b-122">Los modificadores `-f` y `-max` son opcionales.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-122">The `-f` and `-max` switches are optional.</span></span> <span data-ttu-id="8bf8b-123">Especifican respectivamente el formato circular binario y un tamaño de registro de máximo de 1000MB.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-123">They specify the binary circular format and max log size of 1000MB respectively.</span></span> <span data-ttu-id="8bf8b-124">El modificador `-p` se utiliza para especificar el proveedor de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-124">The `-p` switch is used to specify the trace provider.</span></span> <span data-ttu-id="8bf8b-125">En nuestro ejemplo, `"{411a0819-c24b-428c-83e2-26b41091702e}"` es el GUID para "Proveedor del Ejemplo de "XML ETW.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-125">In our example, `"{411a0819-c24b-428c-83e2-26b41091702e}"` is the GUID for "XML ETW Sample Provider".</span></span>  
  
 <span data-ttu-id="8bf8b-126">Para iniciar la sesión, escriba el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-126">To start the session, type in the following command.</span></span>  
  
```console  
logman start Wcf  
```  
  
 <span data-ttu-id="8bf8b-127">Después de haber terminado de registrarse, puede detener la sesión con el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-127">After you have finished logging, you can stop the session with the following command.</span></span>  
  
```console  
logman stop Wcf  
```  
  
 <span data-ttu-id="8bf8b-128">Este proceso genera registros circulares binarios que puede procesar con la herramienta de su elección, incluida la herramienta [Service Trace Viewer (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) o Tracerpt.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-128">This process generates binary circular logs that you can process with your tool of choice, including [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) or Tracerpt.</span></span>  
  
 <span data-ttu-id="8bf8b-129">También puede revisar el ejemplo [de seguimiento circular](../../../../docs/framework/wcf/samples/circular-tracing.md) para obtener más información sobre un agente de escucha alternativo para realizar el registro circular.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-129">You can also review the [Circular Tracing](../../../../docs/framework/wcf/samples/circular-tracing.md) sample for more information on an alternative listener to perform circular logging.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8bf8b-130">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="8bf8b-130">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="8bf8b-131">Asegúrese de que ha realizado el procedimiento de instalación única [para los ejemplos](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="8bf8b-131">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="8bf8b-132">Para compilar la solución, siga las instrucciones de Creación de [ejemplos](../../../../docs/framework/wcf/samples/building-the-samples.md)de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="8bf8b-132">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="8bf8b-133">Para utilizar los comandos RegisterProvider.bat, SetupETW.bat y CleanupETW.bat, debe ejecutarlos en una cuenta de administrador local.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-133">To use the RegisterProvider.bat, SetupETW.bat and CleanupETW.bat commands, you must run under a local administrator account.</span></span> <span data-ttu-id="8bf8b-134">Si utiliza Windows Vista o posterior, también debe ejecutar el símbolo del sistema con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-134">If you are using Windows Vista or later, you must also run the command prompt with elevated privileges.</span></span> <span data-ttu-id="8bf8b-135">Para ello, haga clic con el botón derecho en el icono del símbolo del sistema y, a continuación, haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-135">To do so, right-click the command prompt icon, then click **Run as administrator**.</span></span>  
  
3. <span data-ttu-id="8bf8b-136">Antes de ejecutar el ejemplo, ejecute RegisterProvider.bat en el cliente y servidor.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-136">Before running the sample, run RegisterProvider.bat on the client and server.</span></span> <span data-ttu-id="8bf8b-137">Esto prepara el archivo ETWTracingSampleLog.etl resultante para generar rastros que puedan ser leídos por el visor de seguimiento de servicios.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-137">This sets up the resulting ETWTracingSampleLog.etl file to generate traces that can be read by the Service Trace Viewer.</span></span> <span data-ttu-id="8bf8b-138">Este archivo se puede buscar en la carpeta C:\logs.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-138">This file can be found in the C:\logs folder.</span></span> <span data-ttu-id="8bf8b-139">Si esta carpeta no existe, se debe crear; de lo contrario, no se generará ningún seguimiento.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-139">If this folder does not exist, it must be created or no traces are generated.</span></span> <span data-ttu-id="8bf8b-140">A continuación, ejecute SetupETW.bat en los equipos servidor y cliente para comenzar la sesión de seguimiento de ETW.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-140">Then, run SetupETW.bat on the client and server computers to begin the ETW Trace Session.</span></span> <span data-ttu-id="8bf8b-141">El archivo SetupETW.bat se encuentra en la carpeta CS\Client.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-141">The SetupETW.bat file can be found under the CS\Client folder.</span></span>  
  
4. <span data-ttu-id="8bf8b-142">Para ejecutar el ejemplo en una configuración de un equipo o entre equipos, siga las instrucciones de Ejecución de [los ejemplos](../../../../docs/framework/wcf/samples/running-the-samples.md)de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="8bf8b-142">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
5. <span data-ttu-id="8bf8b-143">Cuando complete el ejemplo, ejecute CleanupETW.bat para completar la creación del archivo ETWTracingSampleLog.etl.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-143">When the sample is completed, run CleanupETW.bat to complete the creation of the ETWTracingSampleLog.etl file.</span></span>  
  
6. <span data-ttu-id="8bf8b-144">Abra el archivo ETWTracingSampleLog.etl desde dentro del Visor de seguimiento de servicios.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-144">Open the ETWTracingSampleLog.etl file from within the Service Trace Viewer.</span></span> <span data-ttu-id="8bf8b-145">Le solicitarán que guarde el archivo con formato binario como un archivo .svclog.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-145">You will be prompted to save the binary formatted file as a .svclog file.</span></span>  
  
7. <span data-ttu-id="8bf8b-146">Abra el archivo .svclog creado recientemente desde el Visor de seguimiento de servicios para ver los seguimientos de ServiceModel y ETW.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-146">Open the newly created .svclog file from within the Service Trace Viewer to view the ETW and ServiceModel traces.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="8bf8b-147">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-147">The samples may already be installed on your computer.</span></span> <span data-ttu-id="8bf8b-148">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-148">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="8bf8b-149">Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="8bf8b-149">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8bf8b-150">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="8bf8b-150">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\AnalyticTrace`  
  
## <a name="see-also"></a><span data-ttu-id="8bf8b-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8bf8b-151">See also</span></span>

- <span data-ttu-id="8bf8b-152">[Ejemplos de supervisión de AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="8bf8b-152">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
