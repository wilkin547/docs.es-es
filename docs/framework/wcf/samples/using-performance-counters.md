---
title: Uso de contadores de rendimiento
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00a787af-1876-473c-a48d-f52b51e28a3f
caps.latest.revision: "31"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 84cbbf83c240ae11099e2c9646150c810a437e71
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="using-performance-counters"></a><span data-ttu-id="dadf1-102">Uso de contadores de rendimiento</span><span class="sxs-lookup"><span data-stu-id="dadf1-102">Using Performance Counters</span></span>
<span data-ttu-id="dadf1-103">Este ejemplo muestra cómo tener acceso a los contadores de rendimiento de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y cómo crear contadores de rendimiento definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="dadf1-103">This sample demonstrates how to access [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] performance counters and how to create user-defined performance counters.</span></span> <span data-ttu-id="dadf1-104">En este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="dadf1-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dadf1-105">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="dadf1-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="dadf1-106">En este ejemplo, el cliente llama a los cuatro métodos del servicio `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="dadf1-106">In this sample, the client calls the four methods of the `ICalculator` service.</span></span> <span data-ttu-id="dadf1-107">El cliente continúa haciéndolo hasta que el usuario lo interrumpa.</span><span class="sxs-lookup"><span data-stu-id="dadf1-107">The client continues to do this until it is interrupted by the user.</span></span> <span data-ttu-id="dadf1-108">El servicio se mantiene sin cambios.</span><span class="sxs-lookup"><span data-stu-id="dadf1-108">The service remains unchanged.</span></span>  
  
 <span data-ttu-id="dadf1-109">Los contadores de rendimiento se habilitan en la sección de diagnóstico del archivo Web.config para el servicio, tal y como se muestra en la configuración del ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="dadf1-109">Performance counters are enabled in the diagnostics section of the Web.config file for the service, as shown in the following sample configuration.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics performanceCounters="All" />   
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="dadf1-110">Esta tarea también puede realizarse mediante la [herramienta Editor de configuración (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span><span class="sxs-lookup"><span data-stu-id="dadf1-110">This task can also be done using the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
 <span data-ttu-id="dadf1-111">Cuando los contadores de rendimiento se habiliten, se habilitará el conjunto completo de contadores de rendimiento [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para el servicio.</span><span class="sxs-lookup"><span data-stu-id="dadf1-111">When performance counters are enabled, the entire suite of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] performance counters is enabled for the service.</span></span> <span data-ttu-id="dadf1-112">.NET Framework mantiene automáticamente los datos de rendimiento en tres niveles: `ServiceModelService`, `ServiceModelEndpoint` y `ServiceModelOperation`.</span><span class="sxs-lookup"><span data-stu-id="dadf1-112">The .NET Framework automatically maintains performance data at three levels: `ServiceModelService`, `ServiceModelEndpoint` and `ServiceModelOperation`.</span></span> <span data-ttu-id="dadf1-113">Cada uno de estos niveles tiene contadores de rendimiento como "Llamadas", "Llamadas por segundo" y "Llamadas de seguridad no autorizadas".</span><span class="sxs-lookup"><span data-stu-id="dadf1-113">Each of these levels has performance counters such as "Calls", "Calls per Second", and "Security Calls Not Authorized".</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="dadf1-114">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="dadf1-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="dadf1-115">Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="dadf1-115">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="dadf1-116">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="dadf1-116">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="dadf1-117">Para ejecutar el ejemplo en una configuración de equipo único o varios, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="dadf1-117">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-view-performance-data"></a><span data-ttu-id="dadf1-118">Para ver los datos de rendimiento</span><span class="sxs-lookup"><span data-stu-id="dadf1-118">To view performance data</span></span>  
  
1.  <span data-ttu-id="dadf1-119">Inicie la herramienta de Monitor de rendimiento, haga clic en **iniciar**, **ejecutar...** , escriba `perfmon` y haga clic en **Aceptar,** o en el Panel de Control, seleccione **herramientas administrativas** y haga doble clic en **rendimiento**.</span><span class="sxs-lookup"><span data-stu-id="dadf1-119">Start the Performance Monitor Tool by clicking **Start**, **Run…**, enter `perfmon` and click **OK,** or from Control Panel, select **Administrative Tools** and double-click **Performance**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dadf1-120">No puede agregar los contadores hasta que el código de ejemplo se esté ejecutando.</span><span class="sxs-lookup"><span data-stu-id="dadf1-120">You cannot add counters until the sample code is running.</span></span>  
  
2.  <span data-ttu-id="dadf1-121">Quite los contadores de rendimiento que aparecen seleccionándolos y presionando la tecla Supr.</span><span class="sxs-lookup"><span data-stu-id="dadf1-121">Remove the performance counters that are listed by selecting them and pressing the Delete key.</span></span>  
  
3.  <span data-ttu-id="dadf1-122">Agregar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] contadores haciendo clic en el panel del gráfico y seleccione **agregar contadores**.</span><span class="sxs-lookup"><span data-stu-id="dadf1-122">Add [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] counters by right-clicking the graph pane and selecting **Add Counters**.</span></span> <span data-ttu-id="dadf1-123">En el **agregar contadores** cuadro de diálogo, seleccione **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0 o ServiceModelService 3.0.0.0** en el objeto de rendimiento cuadro de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="dadf1-123">In the **Add Counters** dialog box, select **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0, or ServiceModelService 3.0.0.0** in the Performance object drop down list box.</span></span> <span data-ttu-id="dadf1-124">Seleccione los contadores que desea ver en la lista.</span><span class="sxs-lookup"><span data-stu-id="dadf1-124">Select the counters you want to view from the list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dadf1-125">No hay ningún contador de rendimiento de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para un servicio si no hay ningún servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que se ejecute en el equipo.</span><span class="sxs-lookup"><span data-stu-id="dadf1-125">There are no [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] performance counters for a service if there are no [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services running on the computer.</span></span>  
  
### <a name="to-use-the-configuration-editor-to-enable-counters"></a><span data-ttu-id="dadf1-126">Para utilizar el editor de configuración para habilitar los contadores</span><span class="sxs-lookup"><span data-stu-id="dadf1-126">To use the Configuration Editor to enable counters</span></span>  
  
1.  <span data-ttu-id="dadf1-127">Abra una instancia de SvcConfigEditor.exe.</span><span class="sxs-lookup"><span data-stu-id="dadf1-127">Open an instance of the SvcConfigEditor.exe.</span></span>  
  
2.  <span data-ttu-id="dadf1-128">En el menú archivo, haga clic en **abiertos** y, a continuación, haga clic en **el archivo de configuración...** .</span><span class="sxs-lookup"><span data-stu-id="dadf1-128">On the File menu, click **Open** and then click **Config file…**.</span></span>  
  
3.  <span data-ttu-id="dadf1-129">Vaya a la carpeta de servicio de la aplicación de ejemplo y abra el archivo Web.config.</span><span class="sxs-lookup"><span data-stu-id="dadf1-129">Navigate to the sample application's service folder and open the Web.config file.</span></span>  
  
4.  <span data-ttu-id="dadf1-130">Haga clic en **diagnósticos** en el árbol de configuración.</span><span class="sxs-lookup"><span data-stu-id="dadf1-130">Click **Diagnostics** on the Configuration tree.</span></span>  
  
5.  <span data-ttu-id="dadf1-131">Alternar **contador de rendimiento** en el **diagnósticos** ventana para mostrar 'All'.</span><span class="sxs-lookup"><span data-stu-id="dadf1-131">Toggle **Performance Counter** in the **Diagnostics** window to show 'All'.</span></span>  
  
6.  <span data-ttu-id="dadf1-132">Guarde el archivo de configuración y cierre el editor.</span><span class="sxs-lookup"><span data-stu-id="dadf1-132">Save the configuration file and exit the editor.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dadf1-133">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="dadf1-133">The samples may already be installed on your computer.</span></span> <span data-ttu-id="dadf1-134">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="dadf1-134">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="dadf1-135">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dadf1-135">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dadf1-136">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="dadf1-136">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\PerfCounters`  
  
## <a name="see-also"></a><span data-ttu-id="dadf1-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="dadf1-137">See Also</span></span>  
 [<span data-ttu-id="dadf1-138">Ejemplos de supervisión de AppFabric</span><span class="sxs-lookup"><span data-stu-id="dadf1-138">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
