---
title: Extraer datos de WF mediante seguimiento
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e30c68f5-8c6a-495a-bd20-667a4364c68e
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 44e49aa0c9b3b9b53b921fe90838875ab34b7772
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="extract-wf-data-using-tracking"></a><span data-ttu-id="4bf1c-102">Extraer datos de WF mediante seguimiento</span><span class="sxs-lookup"><span data-stu-id="4bf1c-102">Extract WF Data using Tracking</span></span>
<span data-ttu-id="4bf1c-103">En este ejemplo se muestra cómo utilizar el seguimiento del flujo de trabajo para extraer variables de flujo de trabajo y argumentos de las actividades.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-103">This sample demonstrates how to use workflow tracking to extract workflow variables and arguments from activities.</span></span> <span data-ttu-id="4bf1c-104">También muestra cómo agregar anotaciones a los registros de seguimiento y cómo extraer una carga de datos en los registros de seguimiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-104">It also shows the addition of annotations to tracking records and the extraction of data payload within custom tracking records.</span></span> <span data-ttu-id="4bf1c-105">En el ejemplo se utiliza el participante de seguimiento de Seguimiento de eventos para Windows (ETW) para extraer datos del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-105">The sample uses the Event Tracing for Windows (ETW) tracking participant to extract data from the workflow.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="4bf1c-106">Detalles del ejemplo</span><span class="sxs-lookup"><span data-stu-id="4bf1c-106">Sample Details</span></span>  
 <span data-ttu-id="4bf1c-107">Windows Workflow Foundation (WF) proporciona un seguimiento para ganar visibilidad en la ejecución de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-107">Windows Workflow Foundation (WF) provides tracking to gain visibility into the execution of a workflow instance.</span></span> <span data-ttu-id="4bf1c-108">El tiempo de ejecución de seguimiento emite registros de seguimiento de flujo de trabajo durante la ejecución del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-108">The tracking runtime emits workflow tracking records during the execution of the workflow.</span></span> <span data-ttu-id="4bf1c-109">Los datos de la instancia de flujo de trabajo, junto con los registros de seguimiento del flujo de trabajo, se pueden extraer del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-109">Along with the workflow tracking records, data within the workflow instance can be extracted from the workflow.</span></span> <span data-ttu-id="4bf1c-110">La siguiente lista detalla los tipos de datos que se pueden extraer de los registros de seguimiento:</span><span class="sxs-lookup"><span data-stu-id="4bf1c-110">The following list details the types of data that can be extracted from tracking records:</span></span>  
  
1.  <span data-ttu-id="4bf1c-111">Las variables de flujo de trabajo de una actividad y registros de seguimiento durante la ejecución de la actividad.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-111">Workflow variables within an activity and tracking records during activity execution.</span></span>  
  
     <span data-ttu-id="4bf1c-112">Para extraer las variables de flujo de trabajo, las variables que se van a extraer se especifican en un perfil.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-112">To extract workflow variables, the variables to be extracted are specified in a profile.</span></span> <span data-ttu-id="4bf1c-113">Las variables que se van a extraer solo se pueden especificar con `ActivityStateQueries`.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-113">Variables to be extracted can only be specified with `ActivityStateQueries`.</span></span> <span data-ttu-id="4bf1c-114">El siguiente ejemplo de código muestra un perfil de seguimiento utilizado para extraer la variable de flujo de trabajo de una actividad.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-114">The following code example demonstrates a tracking profile used to extract the workflow variable from an activity.</span></span>  
  
    ```xml  
    <activityStateQuery activityName="StockPriceService">  
         <states>  
              <state name="Closed"/>  
         </states>  
         <variables>  
              <variable name="symbol"/>  
         </variables>  
    </activityStateQuery>  
    ```  
  
2.  <span data-ttu-id="4bf1c-115">Argumentos de actividad y registros de seguimiento del estado de la actividad.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-115">Activity arguments and activity state tracking records.</span></span>  
  
     <span data-ttu-id="4bf1c-116">Los argumentos definen el flujo de datos hacia dentro o fuera de una actividad.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-116">Arguments define the way data flows in or out of an activity.</span></span> <span data-ttu-id="4bf1c-117">Los argumentos que se van a extraer se especifican mediante <xref:System.Activities.Tracking.ActivityStateQuery>. El siguiente ejemplo de código representa un perfil de seguimiento que extrae el argumento `Value`.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-117">Arguments to be extracted are specified using an <xref:System.Activities.Tracking.ActivityStateQuery>.The following code example is a tracking profile that extracts the `Value` argument.</span></span>  
  
    ```xml  
    <activityStateQuery activityName="GetStockPrice">  
         <states>  
              <state name="Closed"/>  
         </states>  
         <arguments>  
              <argument name="Value"/>  
         </arguments>  
    </activityStateQuery>  
    ```  
  
3.  <span data-ttu-id="4bf1c-118">Las anotaciones son pares clave-valor que se pueden agregar a cualquier registro de seguimiento que se emita.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-118">Annotations are key/value pairs that can be added to any tracking record that is emitted.</span></span>  
  
     <span data-ttu-id="4bf1c-119">Las anotaciones actúan como un mecanismo de etiquetado de registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-119">Annotations serve as a tagging mechanism for tracking records.</span></span> <span data-ttu-id="4bf1c-120">Las anotaciones se agregan a los registros de seguimiento a través de un perfil de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-120">Annotations are added to tracking records through a tracking profile.</span></span> <span data-ttu-id="4bf1c-121">Las anotaciones se pueden agregar a cualquier tipo de consulta de seguimiento de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-121">Annotations can be added to any type of a workflow tracking query.</span></span> <span data-ttu-id="4bf1c-122">El siguiente ejemplo de código representa un perfil de seguimiento que muestra cómo agregar una anotación a un registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-122">The following code example is a tracking profile that shows how an annotation can be added to a tracking record.</span></span>  
  
    ```xml  
    <workflowInstanceQuery>  
         <states>  
              <state name="Started"/>  
         </states>  
         <annotations>  
              <annotation name="StockPriceWorkflow" value="Begin"/>  
         </annotations>  
    </workflowInstanceQuery>  
    ```  
  
4.  <span data-ttu-id="4bf1c-123">Los registros de seguimiento personalizados se emiten por actividades definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-123">Custom tracking records are emitted from user-defined activities.</span></span>  
  
     <span data-ttu-id="4bf1c-124">Los registros de seguimiento personalizados pueden llevar datos de carga definidos dentro de esta actividad.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-124">Custom tracking records can carry payload data defined within this activity.</span></span> <span data-ttu-id="4bf1c-125">La suscripción de registros de seguimiento personalizados en un perfil de seguimiento permite la extracción de la carga dentro del registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-125">Subscribing for custom tracking records in a tracking profile allows the extraction of the payload within the tracking record.</span></span> <span data-ttu-id="4bf1c-126">Los registros de seguimiento personalizados se pueden extraer con un objeto <xref:System.Activities.Tracking.TrackingQuery> personalizado.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-126">The custom tracking records can be extracted with custom a <xref:System.Activities.Tracking.TrackingQuery>.</span></span> <span data-ttu-id="4bf1c-127">El siguiente ejemplo de código representa un perfil de seguimiento que extrae un registro de seguimiento personalizado junto con su carga.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-127">The following code example is a tracking profile that extracts a custom tracking record along with its payload.</span></span>  
  
    ```xml  
    <customTrackingQuery name="QuoteLookupEvent" activityName="GetStockPrice"/>  
    ```  
  
 <span data-ttu-id="4bf1c-128">En el ejemplo se muestra cómo extraer variables, argumentos, registros personalizados y agregar anotaciones utilizando un perfil especificado en el archivo Web.config. El seguimiento se habilita en el servicio de flujo de trabajo de ejemplo agregando un elemento de comportamiento `<etwTracking>`.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-128">The sample demonstrates the extraction of a variables, arguments, custom records and adding annotations using a profile specified in a Web.config. Tracking is enabled on the sample workflow service by adding an `<etwTracking>` behavior element.</span></span> <span data-ttu-id="4bf1c-129">El siguiente ejemplo de código habilita el seguimiento para el perfil de seguimiento `ExtractWorkflowVariables`.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-129">The following code example enables tracking for the `ExtractWorkflowVariables` tracking profile.</span></span>  
  
```xml  
<serviceBehaviors>  
     <behavior>  
               <etwTracking profileName="ExtractWorkflowVariables"/>  
     </behavior>  
</serviceBehaviors>  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="4bf1c-130">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="4bf1c-130">To use this sample</span></span>  
  
1.  <span data-ttu-id="4bf1c-131">Abra el archivo de solución de WFStockPriceApplication.sln con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4bf1c-131">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the WFStockPriceApplication.sln solution file.</span></span>  
  
2.  <span data-ttu-id="4bf1c-132">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-132">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="4bf1c-133">Presione F5 para ejecutar la solución.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-133">To run the solution, press F5.</span></span>  
  
     <span data-ttu-id="4bf1c-134">La ventana del explorador se abre y muestra la lista de directorios de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-134">The browser window opens and shows the directory listing for the application.</span></span>  
  
4.  <span data-ttu-id="4bf1c-135">En el explorador, haga clic en StockPriceService.xamlx.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-135">In the browser, click StockPriceService.xamlx.</span></span>  
  
5.  <span data-ttu-id="4bf1c-136">El explorador muestra la página StockPriceService, que contiene la dirección WSDL de servicio local.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-136">The browser displays the StockPriceService page, which contains the local service WSDL address.</span></span> <span data-ttu-id="4bf1c-137">Copie esta dirección.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-137">Copy this address.</span></span>  
  
     <span data-ttu-id="4bf1c-138">En el siguiente ejemplo se muestra una dirección WSDL de servicio local.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-138">The following example shows a local service WSDL address.</span></span> `http://localhost:53797/StockPriceService.xamlx?wsdl`  
  
6.  <span data-ttu-id="4bf1c-139">Antes de invocar el servicio, inicie el Visor de eventos y asegúrese de que el registro de eventos escucha los eventos de seguimiento emitidos por el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-139">Before invoking the service, start Event Viewer and ensure that the event log is listening for tracking events emitted from the workflow service.</span></span>  
  
7.  <span data-ttu-id="4bf1c-140">Desde el **iniciar** menú, seleccione **herramientas administrativas** y, a continuación, **Visor de eventos**.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-140">From the **Start** menu, select **Administrative Tools** and then **Event Viewer**.</span></span>  
  
8.  <span data-ttu-id="4bf1c-141">En la vista de árbol en el Visor de eventos, navegue hasta **Visor de eventos**, **registros de aplicaciones y servicios**, y **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-141">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, and **Microsoft**.</span></span> <span data-ttu-id="4bf1c-142">Haga clic en **Microsoft** y seleccione **vista** y, a continuación, **mostrar registros analíticos y depuración**.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-142">Right-click **Microsoft** and select **View** and then **Show Analytic and Debug Logs**.</span></span>  
  
     <span data-ttu-id="4bf1c-143">Asegúrese de que el **mostrar registros analíticos y depuración** opción está activada.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-143">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span>  
  
9. <span data-ttu-id="4bf1c-144">En la vista de árbol en el Visor de eventos, navegue hasta **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**,  **Servidor de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-144">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="4bf1c-145">Haga clic en **analítico** y seleccione **Habilitar registro**.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-145">Right-click **Analytic** and select **Enable Log**.</span></span>  
  
10. <span data-ttu-id="4bf1c-146">Mediante [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], abra el cliente de prueba de WCF.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-146">Using [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], open the WCF test client.</span></span>  
  
     <span data-ttu-id="4bf1c-147">El cliente de prueba WCF (WcfTestClient.exe) se encuentra en la \< [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] carpeta de instalación > \Common7\IDE\ carpeta.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-147">The WCF test client (WcfTestClient.exe) is located in the \<[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] installation folder>\Common7\IDE\ folder.</span></span>  
  
     <span data-ttu-id="4bf1c-148">La carpeta de instalación predeterminada de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] es C:\Archivos de programa\Microsoft Visual Studio 10.0.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-148">The default [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] installation folder is C:\Program Files\Microsoft Visual Studio 10.0.</span></span>  
  
11. <span data-ttu-id="4bf1c-149">En el cliente de prueba WCF, seleccione **Agregar servicio** desde el **archivo** menú.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-149">In WCF test client, select **Add Service** from the **File** menu.</span></span>  
  
     <span data-ttu-id="4bf1c-150">Agregue la dirección WSDL de servicio local que copió anteriormente en el cuadro de entrada.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-150">Add the local service WSDL address you copied earlier in the input box.</span></span>  
  
12. <span data-ttu-id="4bf1c-151">En el cliente de pruebas de WCF, haga doble clic en `GetStockPrice`.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-151">In WCF test client, double-click `GetStockPrice`.</span></span>  
  
     <span data-ttu-id="4bf1c-152">De este modo, se abrirá el método `GetStockPrice`.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-152">This opens the `GetStockPrice` method.</span></span> <span data-ttu-id="4bf1c-153">La solicitud acepta un parámetro.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-153">The request accepts one parameter.</span></span> <span data-ttu-id="4bf1c-154">Utilice el valor **Contoso**.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-154">Use the value **Contoso**.</span></span>  
  
13. <span data-ttu-id="4bf1c-155">Haga clic en **invocar**.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-155">Click **Invoke**.</span></span>  
  
14. <span data-ttu-id="4bf1c-156">Cambie al Visor de eventos y navegue hasta **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**,  **Servidor de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-156">Switch back to Event Viewer and navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="4bf1c-157">Haga clic en **analítico** y seleccione **actualizar**.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-157">Right-click **Analytic** and select **Refresh**.</span></span> <span data-ttu-id="4bf1c-158">Los eventos de flujo de trabajo se encuentran en el intervalo de identificadores de evento que va del 100 al 199.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-158">The workflow events are in the event ID ranges 100-199.</span></span>  
  
     <span data-ttu-id="4bf1c-159">Los eventos contienen las anotaciones, las variables, los argumentos y los registros de seguimiento personalizados que se pueden ver en el Visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-159">The events contain the annotations, variables, arguments and custom tracking records that can be viewed in the event viewer.</span></span>  
  
## <a name="cleaning-up-in-the-event-viewer"></a><span data-ttu-id="4bf1c-160">Limpiar el Visor de eventos</span><span class="sxs-lookup"><span data-stu-id="4bf1c-160">Cleaning up in the Event Viewer</span></span>  
 <span data-ttu-id="4bf1c-161">Para limpiar el canal analítico del registro de eventos en el Visor de eventos realice lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-161">The analytic channel in the event log can be cleaned up in the Event Viewer by doing the following.</span></span>  
  
#### <a name="to-clean-up-optional"></a><span data-ttu-id="4bf1c-162">Para realizar la limpieza (Opcional)</span><span class="sxs-lookup"><span data-stu-id="4bf1c-162">To clean up (Optional)</span></span>  
  
1.  <span data-ttu-id="4bf1c-163">Abra el Visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-163">Open Event Viewer.</span></span>  
  
2.  <span data-ttu-id="4bf1c-164">Vaya a **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**, **aplicación Aplicaciones de servidor**.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-164">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="4bf1c-165">Haga clic en **analítico** y seleccione **Deshabilitar registro**.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-165">Right-click **Analytic** and select **Disable Log**.</span></span>  
  
3.  <span data-ttu-id="4bf1c-166">Vaya a **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**, **aplicación Aplicaciones de servidor**.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-166">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="4bf1c-167">Haga clic en **analítico** y seleccione **Vaciar registro**.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-167">Right-click **Analytic** and select **Clear Log**.</span></span>  
  
     <span data-ttu-id="4bf1c-168">Elija la **borrar** opción para borrar los eventos.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-168">Choose the **Clear** option to clear the events.</span></span>  
  
## <a name="known-issue"></a><span data-ttu-id="4bf1c-169">Problema conocido</span><span class="sxs-lookup"><span data-stu-id="4bf1c-169">Known Issue</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4bf1c-170">Existe un problema conocido en el Visor de eventos en virtud del cual el visor no puede descodificar eventos de ETW.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-170">There is a known issue in the Event Viewer where it may fail to decode ETW events.</span></span> <span data-ttu-id="4bf1c-171">Es posible que vea un mensaje de error similar el siguiente.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-171">You may see an error message that looks like the following.</span></span>  
>   
>  `The description for Event ID <id> from source Microsoft-Windows-Application Server-Applications cannot be found. Either the component that raises this event is not installed on your local computer or the installation is corrupted. You can install or repair the component on the local computer.`  
>   
>  <span data-ttu-id="4bf1c-172">Si se produce este error, haga clic en **actualizar** en el panel Acciones.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-172">If you encounter this error, click **Refresh** in the actions pane.</span></span> <span data-ttu-id="4bf1c-173">El evento debería descodificarse ahora correctamente.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-173">The event should now decode properly.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4bf1c-174">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-174">The samples may already be installed on your computer.</span></span> <span data-ttu-id="4bf1c-175">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-175">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="4bf1c-176">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4bf1c-176">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4bf1c-177">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="4bf1c-177">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\ExtractWfData`  
  
## <a name="see-also"></a><span data-ttu-id="4bf1c-178">Vea también</span><span class="sxs-lookup"><span data-stu-id="4bf1c-178">See Also</span></span>  
 [<span data-ttu-id="4bf1c-179">Ejemplos de supervisión de AppFabric</span><span class="sxs-lookup"><span data-stu-id="4bf1c-179">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
