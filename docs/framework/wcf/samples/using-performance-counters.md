---
title: Uso de contadores de rendimiento
ms.date: 03/30/2017
ms.assetid: 00a787af-1876-473c-a48d-f52b51e28a3f
ms.openlocfilehash: 7ffd9f5de5efb4be22968958246839e804daf23d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143582"
---
# <a name="using-performance-counters"></a><span data-ttu-id="f2521-102">Uso de contadores de rendimiento</span><span class="sxs-lookup"><span data-stu-id="f2521-102">Using Performance Counters</span></span>
<span data-ttu-id="f2521-103">En este ejemplo se muestra cómo tener acceso a los contadores de rendimiento de Windows Communication Foundation (WCF) y cómo crear contadores de rendimiento definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="f2521-103">This sample demonstrates how to access Windows Communication Foundation (WCF) performance counters and how to create user-defined performance counters.</span></span> <span data-ttu-id="f2521-104">Este ejemplo se basa en la [introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="f2521-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f2521-105">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="f2521-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="f2521-106">En este ejemplo, el cliente llama a los cuatro métodos del servicio `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="f2521-106">In this sample, the client calls the four methods of the `ICalculator` service.</span></span> <span data-ttu-id="f2521-107">El cliente continúa haciéndolo hasta que el usuario lo interrumpa.</span><span class="sxs-lookup"><span data-stu-id="f2521-107">The client continues to do this until it is interrupted by the user.</span></span> <span data-ttu-id="f2521-108">El servicio se mantiene sin cambios.</span><span class="sxs-lookup"><span data-stu-id="f2521-108">The service remains unchanged.</span></span>  
  
 <span data-ttu-id="f2521-109">Los contadores de rendimiento se habilitan en la sección de diagnóstico del archivo Web.config para el servicio, tal y como se muestra en la configuración del ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f2521-109">Performance counters are enabled in the diagnostics section of the Web.config file for the service, as shown in the following sample configuration.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics performanceCounters="All" />
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="f2521-110">Esta tarea también se puede realizar mediante la herramienta Editor de configuración [(SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span><span class="sxs-lookup"><span data-stu-id="f2521-110">This task can also be done using the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
 <span data-ttu-id="f2521-111">Cuando se habilitan los contadores de rendimiento, se habilita todo el conjunto de contadores de rendimiento WCF para el servicio.</span><span class="sxs-lookup"><span data-stu-id="f2521-111">When performance counters are enabled, the entire suite of WCF performance counters is enabled for the service.</span></span> <span data-ttu-id="f2521-112">.NET Framework mantiene automáticamente los datos de rendimiento en tres niveles: `ServiceModelService`, `ServiceModelEndpoint` y `ServiceModelOperation`.</span><span class="sxs-lookup"><span data-stu-id="f2521-112">The .NET Framework automatically maintains performance data at three levels: `ServiceModelService`, `ServiceModelEndpoint` and `ServiceModelOperation`.</span></span> <span data-ttu-id="f2521-113">Cada uno de estos niveles tiene contadores de rendimiento como "Llamadas", "Llamadas por segundo" y "Llamadas de seguridad no autorizadas".</span><span class="sxs-lookup"><span data-stu-id="f2521-113">Each of these levels has performance counters such as "Calls", "Calls per Second", and "Security Calls Not Authorized".</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f2521-114">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="f2521-114">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="f2521-115">Asegúrese de que ha realizado el procedimiento de instalación única [para los ejemplos](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="f2521-115">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="f2521-116">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f2521-116">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="f2521-117">Para ejecutar el ejemplo en una configuración de un equipo o entre equipos, siga las instrucciones de Ejecución de [los ejemplos](../../../../docs/framework/wcf/samples/running-the-samples.md)de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="f2521-117">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-view-performance-data"></a><span data-ttu-id="f2521-118">Para ver los datos de rendimiento</span><span class="sxs-lookup"><span data-stu-id="f2521-118">To view performance data</span></span>  
  
1. <span data-ttu-id="f2521-119">Inicie la herramienta Monitor de rendimiento haciendo `perfmon` clic en **Inicio**, **Ejecutar...**, escriba y haga clic en **Aceptar,** o en el Panel de control, seleccione **Herramientas administrativas** y haga doble clic en **Rendimiento**.</span><span class="sxs-lookup"><span data-stu-id="f2521-119">Start the Performance Monitor Tool by clicking **Start**, **Run…**, enter `perfmon` and click **OK,** or from Control Panel, select **Administrative Tools** and double-click **Performance**.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="f2521-120">No puede agregar los contadores hasta que el código de ejemplo se esté ejecutando.</span><span class="sxs-lookup"><span data-stu-id="f2521-120">You cannot add counters until the sample code is running.</span></span>  
  
2. <span data-ttu-id="f2521-121">Quite los contadores de rendimiento que aparecen seleccionándolos y presionando la tecla Supr.</span><span class="sxs-lookup"><span data-stu-id="f2521-121">Remove the performance counters that are listed by selecting them and pressing the Delete key.</span></span>  
  
3. <span data-ttu-id="f2521-122">Agregue contadores WCF haciendo clic con el botón derecho en el panel de gráficos y seleccionando **Agregar contadores**.</span><span class="sxs-lookup"><span data-stu-id="f2521-122">Add WCF counters by right-clicking the graph pane and selecting **Add Counters**.</span></span> <span data-ttu-id="f2521-123">En el cuadro de diálogo **Agregar contadores,** seleccione **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0 o ServiceModelService 3.0.0.0** en el cuadro de lista desplegable Objeto de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="f2521-123">In the **Add Counters** dialog box, select **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0, or ServiceModelService 3.0.0.0** in the Performance object drop down list box.</span></span> <span data-ttu-id="f2521-124">Seleccione los contadores que desea ver en la lista.</span><span class="sxs-lookup"><span data-stu-id="f2521-124">Select the counters you want to view from the list.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="f2521-125">No hay contadores de rendimiento WCF para un servicio si no hay servicios WCF que se ejecutan en el equipo.</span><span class="sxs-lookup"><span data-stu-id="f2521-125">There are no WCF performance counters for a service if there are no WCF services running on the computer.</span></span>  
  
### <a name="to-use-the-configuration-editor-to-enable-counters"></a><span data-ttu-id="f2521-126">Para utilizar el editor de configuración para habilitar los contadores</span><span class="sxs-lookup"><span data-stu-id="f2521-126">To use the Configuration Editor to enable counters</span></span>  
  
1. <span data-ttu-id="f2521-127">Abra una instancia de SvcConfigEditor.exe.</span><span class="sxs-lookup"><span data-stu-id="f2521-127">Open an instance of the SvcConfigEditor.exe.</span></span>  
  
2. <span data-ttu-id="f2521-128">En el menú Archivo, haga clic en **Abrir** y, a continuación, haga clic en **Archivo de configuración...**.</span><span class="sxs-lookup"><span data-stu-id="f2521-128">On the File menu, click **Open** and then click **Config file…**.</span></span>  
  
3. <span data-ttu-id="f2521-129">Vaya a la carpeta de servicio de la aplicación de ejemplo y abra el archivo Web.config.</span><span class="sxs-lookup"><span data-stu-id="f2521-129">Navigate to the sample application's service folder and open the Web.config file.</span></span>  
  
4. <span data-ttu-id="f2521-130">Haga clic en **Diagnóstico** en el árbol Configuración.</span><span class="sxs-lookup"><span data-stu-id="f2521-130">Click **Diagnostics** on the Configuration tree.</span></span>  
  
5. <span data-ttu-id="f2521-131">Alternar **contador de rendimiento** en la ventana **Diagnóstico** para mostrar 'Todos'.</span><span class="sxs-lookup"><span data-stu-id="f2521-131">Toggle **Performance Counter** in the **Diagnostics** window to show 'All'.</span></span>  
  
6. <span data-ttu-id="f2521-132">Guarde el archivo de configuración y cierre el editor.</span><span class="sxs-lookup"><span data-stu-id="f2521-132">Save the configuration file and exit the editor.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f2521-133">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="f2521-133">The samples may already be installed on your computer.</span></span> <span data-ttu-id="f2521-134">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="f2521-134">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="f2521-135">Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="f2521-135">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f2521-136">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="f2521-136">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\PerfCounters`  
  
## <a name="see-also"></a><span data-ttu-id="f2521-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f2521-137">See also</span></span>

- <span data-ttu-id="f2521-138">[Ejemplos de supervisión de AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="f2521-138">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
