---
title: Servicios de WCF y seguimiento de eventos para Windows
ms.date: 03/30/2017
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
ms.openlocfilehash: ea917ee87b598fc3ad01df70d9aedfadfd1396a4
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="wcf-services-and-event-tracing-for-windows"></a><span data-ttu-id="084bf-102">Servicios de WCF y seguimiento de eventos para Windows</span><span class="sxs-lookup"><span data-stu-id="084bf-102">WCF Services and Event Tracing for Windows</span></span>
<span data-ttu-id="084bf-103">Este ejemplo muestra cómo utilizar la traza analítica en Windows Communication Foundation (WCF) para emitir eventos de seguimiento de eventos para Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="084bf-103">This sample demonstrates how to use the analytic tracing in Windows Communication Foundation (WCF) to emit events in Event Tracing for Windows (ETW).</span></span> <span data-ttu-id="084bf-104">Los seguimientos analíticos son los eventos emitidos en puntos clave de la pila de WCF que permiten solucionar problemas de servicios WCF en el entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="084bf-104">The analytic traces are events emitted at key points in the WCF stack that allow troubleshooting of WCF services in production environment.</span></span>  
  
 <span data-ttu-id="084bf-105">Traza analítica en los servicios WCF traza que pueden activarse en un entorno de producción con un impacto mínimo en el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="084bf-105">Analytic trace in WCF services is tracing that can be turned on in a production environment with minimal impact on performance.</span></span> <span data-ttu-id="084bf-106">Estos seguimientos se emiten como eventos para una sesión de ETW.</span><span class="sxs-lookup"><span data-stu-id="084bf-106">These traces are emitted as events to an ETW session.</span></span>  
  
 <span data-ttu-id="084bf-107">Este ejemplo incluye un servicio WCF básico en el que se emiten los eventos desde el servicio en el registro de eventos, que puede verse mediante el Visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="084bf-107">This sample includes a basic WCF service in which events are emitted from the service to the event log, which can be viewed using Event Viewer.</span></span> <span data-ttu-id="084bf-108">También es posible iniciar una sesión ETW dedicada que realiza escuchas de eventos desde el servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="084bf-108">It is also possible to start a dedicated ETW session that listens for events from the WCF service.</span></span> <span data-ttu-id="084bf-109">En el ejemplo se incluye un script para crear una sesión de ETW dedicada que almacena los eventos en un archivo binario que se puede leer utilizando el Visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="084bf-109">The sample includes a script to create a dedicated ETW session that stores events in a binary file that can be read using Event Viewer.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="084bf-110">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="084bf-110">To use this sample</span></span>  
  
1.  <span data-ttu-id="084bf-111">Con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], abra el archivo de solución EtwAnalyticTraceSample.sln.</span><span class="sxs-lookup"><span data-stu-id="084bf-111">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the EtwAnalyticTraceSample.sln solution file.</span></span>  
  
2.  <span data-ttu-id="084bf-112">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="084bf-112">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="084bf-113">Para ejecutar la solución, presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="084bf-113">To run the solution, press CTRL+F5.</span></span>  
  
     <span data-ttu-id="084bf-114">En el explorador Web, haga clic en **Calculator.svc**.</span><span class="sxs-lookup"><span data-stu-id="084bf-114">In the Web browser, click **Calculator.svc**.</span></span> <span data-ttu-id="084bf-115">El URI del documento WSDL para el servicio debería aparecer en el explorador.</span><span class="sxs-lookup"><span data-stu-id="084bf-115">The URI of the WSDL document for the service should appear in the browser.</span></span> <span data-ttu-id="084bf-116">Copie ese URI.</span><span class="sxs-lookup"><span data-stu-id="084bf-116">Copy that URI.</span></span>  
  
     <span data-ttu-id="084bf-117">De forma predeterminada, el servicio inicia la escucha de solicitudes en el puerto 1378 (http://localhost:1378/Calculator.svc).</span><span class="sxs-lookup"><span data-stu-id="084bf-117">By default, the service starts listening for requests on port 1378 (http://localhost:1378/Calculator.svc).</span></span>  
  
4.  <span data-ttu-id="084bf-118">Ejecute al cliente de prueba WCF (WcfTestClient.exe).</span><span class="sxs-lookup"><span data-stu-id="084bf-118">Run the WCF test client (WcfTestClient.exe).</span></span>  
  
     <span data-ttu-id="084bf-119">El cliente de prueba WCF (WcfTestClient.exe) se encuentra en la \< [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] directorio de instalación > \Common7\IDE\ WcfTestClient.exe (valor predeterminado [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] directorio de instalación es C:\Program Files\Microsoft Visual Studio 10.0).</span><span class="sxs-lookup"><span data-stu-id="084bf-119">The WCF test client (WcfTestClient.exe) is located in the \<[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Install Dir>\Common7\IDE\ WcfTestClient.exe (default [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] install dir is C:\Program Files\Microsoft Visual Studio 10.0).</span></span>  
  
5.  <span data-ttu-id="084bf-120">En el cliente de prueba WCF, agregue el servicio seleccionando **archivo**y, a continuación, **Agregar servicio**.</span><span class="sxs-lookup"><span data-stu-id="084bf-120">Within the WCF test client, add the service by selecting **File**, and then **Add Service**.</span></span>  
  
     <span data-ttu-id="084bf-121">Agregue la dirección del punto de conexión en el cuadro de entrada.</span><span class="sxs-lookup"><span data-stu-id="084bf-121">Add the endpoint address in the input box.</span></span> <span data-ttu-id="084bf-122">De manera predeterminada, es http://localhost:1378/Calculator.svc.</span><span class="sxs-lookup"><span data-stu-id="084bf-122">The default is http://localhost:1378/Calculator.svc.</span></span>  
  
6.  <span data-ttu-id="084bf-123">Abra la aplicación Visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="084bf-123">Open the Event Viewer application.</span></span>  
  
     <span data-ttu-id="084bf-124">Antes de invocar el servicio, inicie el Visor de eventos y asegúrese de que el registro de eventos escucha eventos de seguimiento emitidos desde el servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="084bf-124">Before invoking the service, start Event Viewer and ensure that the event log is listening for tracking events emitted from the WCF service.</span></span>  
  
7.  <span data-ttu-id="084bf-125">Desde el **iniciar** menú, seleccione **herramientas administrativas**y, a continuación, **Visor de eventos**.</span><span class="sxs-lookup"><span data-stu-id="084bf-125">From the **Start** menu, select **Administrative Tools**, and then **Event Viewer**.</span></span>  <span data-ttu-id="084bf-126">Habilitar la **analítico** y **depurar** registros.</span><span class="sxs-lookup"><span data-stu-id="084bf-126">Enable the **Analytic** and **Debug** logs.</span></span>  
  
8.  <span data-ttu-id="084bf-127">En la vista de árbol en el Visor de eventos, navegue hasta **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación, **Servidor de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="084bf-127">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="084bf-128">Haga clic en **servidor de aplicaciones**, seleccione **vista**y, a continuación, **mostrar registros analíticos y depuración**.</span><span class="sxs-lookup"><span data-stu-id="084bf-128">Right-click **Application Server-Applications**, select **View**, and then **Show Analytic and Debug Logs**.</span></span>  
  
     <span data-ttu-id="084bf-129">Asegúrese de que el **mostrar registros analíticos y depuración** opción está activada.</span><span class="sxs-lookup"><span data-stu-id="084bf-129">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span>  
  
9. <span data-ttu-id="084bf-130">Habilitar la **analítico** registro.</span><span class="sxs-lookup"><span data-stu-id="084bf-130">Enable the **Analytic** log.</span></span>  
  
     <span data-ttu-id="084bf-131">En la vista de árbol en el Visor de eventos, navegue hasta **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación, **Servidor de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="084bf-131">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="084bf-132">Haga clic en **analítico** y seleccione **Habilitar registro**.</span><span class="sxs-lookup"><span data-stu-id="084bf-132">Right-click **Analytic** and select **Enable Log**.</span></span>  
  
#### <a name="to-test-the-service"></a><span data-ttu-id="084bf-133">Para probar el servicio</span><span class="sxs-lookup"><span data-stu-id="084bf-133">To test the service</span></span>  
  
1.  <span data-ttu-id="084bf-134">Volver al cliente de prueba WCF y haga doble clic en `Divide` y mantenga los valores predeterminados, que especifican el denominador 0.</span><span class="sxs-lookup"><span data-stu-id="084bf-134">Switch back to WCF test client and double-click `Divide` and keep the default values, which specify a denominator of 0.</span></span>  
  
     <span data-ttu-id="084bf-135">Si el denominador es 0, el servicio produce un error.</span><span class="sxs-lookup"><span data-stu-id="084bf-135">If the denominator is 0, then the service throws a fault.</span></span>  
  
2.  <span data-ttu-id="084bf-136">Observe los eventos emitidos desde el servicio.</span><span class="sxs-lookup"><span data-stu-id="084bf-136">Observe the events emitted from the service.</span></span>  
  
     <span data-ttu-id="084bf-137">Cambie al Visor de eventos y navegue hasta **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación, **Servidor de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="084bf-137">Switch back to Event Viewer and navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="084bf-138">Haga clic en **analítico** y seleccione **actualizar**.</span><span class="sxs-lookup"><span data-stu-id="084bf-138">Right-click **Analytic** and select **Refresh**.</span></span>  
  
     <span data-ttu-id="084bf-139">Los eventos de seguimiento analítico de WCF se muestran en el visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="084bf-139">The WCF analytic trace events are displayed in the event viewer.</span></span> <span data-ttu-id="084bf-140">Observe que dado que el servicio inició un error, se muestra un evento de seguimiento del error en el visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="084bf-140">Notice that because a fault was thrown by the service an error trace event is displayed in the event viewer.</span></span>  
  
3.  <span data-ttu-id="084bf-141">Repita los pasos 1 y 2, pero con entradas válidas.</span><span class="sxs-lookup"><span data-stu-id="084bf-141">Repeat steps 1 and 2, but with valid inputs.</span></span> <span data-ttu-id="084bf-142">El valor del parámetro `N2` puede ser cualquier número distinto de 0.</span><span class="sxs-lookup"><span data-stu-id="084bf-142">The value of the `N2` parameter can be any number other than 0.</span></span>  
  
     <span data-ttu-id="084bf-143">Actualice el canal analítico para ver los eventos de WCF que no incluyen ningún evento de error.</span><span class="sxs-lookup"><span data-stu-id="084bf-143">Refresh the analytic channel to view the WCF events do not include any error events.</span></span>  
  
 <span data-ttu-id="084bf-144">En el ejemplo se muestran los eventos de seguimiento analíticos emitidos desde un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="084bf-144">The sample demonstrates the analytic trace events emitted from a WCF service.</span></span>  
  
#### <a name="to-cleanup-optional"></a><span data-ttu-id="084bf-145">Para realizar la limpieza (Opcional)</span><span class="sxs-lookup"><span data-stu-id="084bf-145">To cleanup (Optional)</span></span>  
  
1.  <span data-ttu-id="084bf-146">Abra el Visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="084bf-146">Open Event Viewer.</span></span>  
  
2.  <span data-ttu-id="084bf-147">Vaya a **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación,  **Aplicaciones de servidor**.</span><span class="sxs-lookup"><span data-stu-id="084bf-147">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="084bf-148">Haga clic en **analítico** y seleccione **Deshabilitar registro**.</span><span class="sxs-lookup"><span data-stu-id="084bf-148">Right-click **Analytic** and select **Disable Log**.</span></span>  
  
3.  <span data-ttu-id="084bf-149">Vaya a **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación,  **Aplicaciones de servidor**.</span><span class="sxs-lookup"><span data-stu-id="084bf-149">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="084bf-150">Haga clic en **analítico** y seleccione **Vaciar registro**.</span><span class="sxs-lookup"><span data-stu-id="084bf-150">Right-click **Analytic** and select **Clear Log**.</span></span>  
  
4.  <span data-ttu-id="084bf-151">Elija la **borrar** opción para borrar los eventos.</span><span class="sxs-lookup"><span data-stu-id="084bf-151">Choose the **Clear** option to clear the events.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="084bf-152">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="084bf-152">The samples may already be installed on your computer.</span></span> <span data-ttu-id="084bf-153">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="084bf-153">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="084bf-154">Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="084bf-154">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="084bf-155">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="084bf-155">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## <a name="see-also"></a><span data-ttu-id="084bf-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="084bf-156">See Also</span></span>  
 [<span data-ttu-id="084bf-157">Ejemplos de supervisión de AppFabric</span><span class="sxs-lookup"><span data-stu-id="084bf-157">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
