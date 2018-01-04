---
title: Servicios de WCF y seguimiento de eventos para Windows
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cb8924cc04442e3b9eda5e251e6dcdc57f5660c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="wcf-services-and-event-tracing-for-windows"></a><span data-ttu-id="93a68-102">Servicios de WCF y seguimiento de eventos para Windows</span><span class="sxs-lookup"><span data-stu-id="93a68-102">WCF Services and Event Tracing for Windows</span></span>
<span data-ttu-id="93a68-103">Este ejemplo muestra cómo utilizar la traza analítica en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] para emitir eventos en Seguimiento de eventos para Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="93a68-103">This sample demonstrates how to use the analytic tracing in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] to emit events in Event Tracing for Windows (ETW).</span></span> <span data-ttu-id="93a68-104">Los seguimientos analíticos son los eventos emitidos en los puntos clave de la pila de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que permiten solucionar problemas de los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="93a68-104">The analytic traces are events emitted at key points in the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] stack that allow troubleshooting of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services in production environment.</span></span>  
  
 <span data-ttu-id="93a68-105">El seguimiento analítico de servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se puede activar en un entorno de producción con una repercusión mínima en el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="93a68-105">Analytic trace in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services is tracing that can be turned on in a production environment with minimal impact on performance.</span></span> <span data-ttu-id="93a68-106">Estos seguimientos se emiten como eventos para una sesión de ETW.</span><span class="sxs-lookup"><span data-stu-id="93a68-106">These traces are emitted as events to an ETW session.</span></span>  
  
 <span data-ttu-id="93a68-107">En este ejemplo se incluye un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] básico en el que los eventos se emiten desde l servicio al registro de eventos, que se puede ver con el Visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="93a68-107">This sample includes a basic [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service in which events are emitted from the service to the event log, which can be viewed using Event Viewer.</span></span> <span data-ttu-id="93a68-108">También es posible iniciar una sesión de ETW dedicada que realice escuchas para los eventos del servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93a68-108">It is also possible to start a dedicated ETW session that listens for events from the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="93a68-109">En el ejemplo se incluye un script para crear una sesión de ETW dedicada que almacena los eventos en un archivo binario que se puede leer utilizando el Visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="93a68-109">The sample includes a script to create a dedicated ETW session that stores events in a binary file that can be read using Event Viewer.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="93a68-110">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="93a68-110">To use this sample</span></span>  
  
1.  <span data-ttu-id="93a68-111">Con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], abra el archivo de solución EtwAnalyticTraceSample.sln.</span><span class="sxs-lookup"><span data-stu-id="93a68-111">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the EtwAnalyticTraceSample.sln solution file.</span></span>  
  
2.  <span data-ttu-id="93a68-112">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="93a68-112">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="93a68-113">Para ejecutar la solución, presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="93a68-113">To run the solution, press CTRL+F5.</span></span>  
  
     <span data-ttu-id="93a68-114">En el explorador Web, haga clic en **Calculator.svc**.</span><span class="sxs-lookup"><span data-stu-id="93a68-114">In the Web browser, click **Calculator.svc**.</span></span> <span data-ttu-id="93a68-115">El URI del documento WSDL para el servicio debería aparecer en el explorador.</span><span class="sxs-lookup"><span data-stu-id="93a68-115">The URI of the WSDL document for the service should appear in the browser.</span></span> <span data-ttu-id="93a68-116">Copie ese URI.</span><span class="sxs-lookup"><span data-stu-id="93a68-116">Copy that URI.</span></span>  
  
     <span data-ttu-id="93a68-117">De forma predeterminada, el servicio empieza a realizar escuchas para las solicitudes en el puerto 1378 (http://localhost:1378/Calculator.svc).</span><span class="sxs-lookup"><span data-stu-id="93a68-117">By default, the service starts listening for requests on port 1378 (http://localhost:1378/Calculator.svc).</span></span>  
  
4.  <span data-ttu-id="93a68-118">Ejecute el cliente de prueba de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] (WcfTestClient.exe).</span><span class="sxs-lookup"><span data-stu-id="93a68-118">Run the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] test client (WcfTestClient.exe).</span></span>  
  
     <span data-ttu-id="93a68-119">El [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cliente de prueba (WcfTestClient.exe) se encuentra en la \< [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] directorio de instalación > \Common7\IDE\ WcfTestClient.exe (valor predeterminado [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] directorio de instalación es C:\Program Files\Microsoft Visual Studio 10.0).</span><span class="sxs-lookup"><span data-stu-id="93a68-119">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] test client (WcfTestClient.exe) is located in the \<[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Install Dir>\Common7\IDE\ WcfTestClient.exe (default [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] install dir is C:\Program Files\Microsoft Visual Studio 10.0).</span></span>  
  
5.  <span data-ttu-id="93a68-120">En el [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cliente de prueba, agregue el servicio seleccionando **archivo**y, a continuación, **Agregar servicio**.</span><span class="sxs-lookup"><span data-stu-id="93a68-120">Within the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] test client, add the service by selecting **File**, and then **Add Service**.</span></span>  
  
     <span data-ttu-id="93a68-121">Agregue la dirección del punto de conexión en el cuadro de entrada.</span><span class="sxs-lookup"><span data-stu-id="93a68-121">Add the endpoint address in the input box.</span></span> <span data-ttu-id="93a68-122">El valor predeterminado es http://localhost:1378/Calculator.svc.</span><span class="sxs-lookup"><span data-stu-id="93a68-122">The default is http://localhost:1378/Calculator.svc.</span></span>  
  
6.  <span data-ttu-id="93a68-123">Abra la aplicación Visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="93a68-123">Open the Event Viewer application.</span></span>  
  
     <span data-ttu-id="93a68-124">Antes de invocar el servicio, inicie el Visor de eventos y asegúrese de que el registro de eventos escucha los eventos de seguimiento emitidos por el servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93a68-124">Before invoking the service, start Event Viewer and ensure that the event log is listening for tracking events emitted from the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
7.  <span data-ttu-id="93a68-125">Desde el **iniciar** menú, seleccione **herramientas administrativas**y, a continuación, **Visor de eventos**.</span><span class="sxs-lookup"><span data-stu-id="93a68-125">From the **Start** menu, select **Administrative Tools**, and then **Event Viewer**.</span></span>  <span data-ttu-id="93a68-126">Habilitar la **analítico** y **depurar** registros.</span><span class="sxs-lookup"><span data-stu-id="93a68-126">Enable the **Analytic** and **Debug** logs.</span></span>  
  
8.  <span data-ttu-id="93a68-127">En la vista de árbol en el Visor de eventos, navegue hasta **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación, **Servidor de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="93a68-127">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="93a68-128">Haga clic en **servidor de aplicaciones**, seleccione **vista**y, a continuación, **mostrar registros analíticos y depuración**.</span><span class="sxs-lookup"><span data-stu-id="93a68-128">Right-click **Application Server-Applications**, select **View**, and then **Show Analytic and Debug Logs**.</span></span>  
  
     <span data-ttu-id="93a68-129">Asegúrese de que el **mostrar registros analíticos y depuración** opción está activada.</span><span class="sxs-lookup"><span data-stu-id="93a68-129">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span>  
  
9. <span data-ttu-id="93a68-130">Habilitar la **analítico** registro.</span><span class="sxs-lookup"><span data-stu-id="93a68-130">Enable the **Analytic** log.</span></span>  
  
     <span data-ttu-id="93a68-131">En la vista de árbol en el Visor de eventos, navegue hasta **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación, **Servidor de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="93a68-131">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="93a68-132">Haga clic en **analítico** y seleccione **Habilitar registro**.</span><span class="sxs-lookup"><span data-stu-id="93a68-132">Right-click **Analytic** and select **Enable Log**.</span></span>  
  
#### <a name="to-test-the-service"></a><span data-ttu-id="93a68-133">Para probar el servicio</span><span class="sxs-lookup"><span data-stu-id="93a68-133">To test the service</span></span>  
  
1.  <span data-ttu-id="93a68-134">Cambie de nuevo al cliente de prueba de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], haga doble clic en `Divide` y mantenga los valores predeterminados, que especifican el denominador 0.</span><span class="sxs-lookup"><span data-stu-id="93a68-134">Switch back to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] test client and double-click `Divide` and keep the default values, which specify a denominator of 0.</span></span>  
  
     <span data-ttu-id="93a68-135">Si el denominador es 0, el servicio produce un error.</span><span class="sxs-lookup"><span data-stu-id="93a68-135">If the denominator is 0, then the service throws a fault.</span></span>  
  
2.  <span data-ttu-id="93a68-136">Observe los eventos emitidos desde el servicio.</span><span class="sxs-lookup"><span data-stu-id="93a68-136">Observe the events emitted from the service.</span></span>  
  
     <span data-ttu-id="93a68-137">Cambie al Visor de eventos y navegue hasta **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación, **Servidor de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="93a68-137">Switch back to Event Viewer and navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="93a68-138">Haga clic en **analítico** y seleccione **actualizar**.</span><span class="sxs-lookup"><span data-stu-id="93a68-138">Right-click **Analytic** and select **Refresh**.</span></span>  
  
     <span data-ttu-id="93a68-139">Los eventos de seguimiento analítico de WCF se muestran en el visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="93a68-139">The WCF analytic trace events are displayed in the event viewer.</span></span> <span data-ttu-id="93a68-140">Observe que dado que el servicio inició un error, se muestra un evento de seguimiento del error en el visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="93a68-140">Notice that because a fault was thrown by the service an error trace event is displayed in the event viewer.</span></span>  
  
3.  <span data-ttu-id="93a68-141">Repita los pasos 1 y 2, pero con entradas válidas.</span><span class="sxs-lookup"><span data-stu-id="93a68-141">Repeat steps 1 and 2, but with valid inputs.</span></span> <span data-ttu-id="93a68-142">El valor del parámetro `N2` puede ser cualquier número distinto de 0.</span><span class="sxs-lookup"><span data-stu-id="93a68-142">The value of the `N2` parameter can be any number other than 0.</span></span>  
  
     <span data-ttu-id="93a68-143">Actualice el canal analítico para ver los eventos de WCF que no incluyen ningún evento de error.</span><span class="sxs-lookup"><span data-stu-id="93a68-143">Refresh the analytic channel to view the WCF events do not include any error events.</span></span>  
  
 <span data-ttu-id="93a68-144">En el ejemplo se muestran los eventos de seguimiento analíticos emitidos desde un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="93a68-144">The sample demonstrates the analytic trace events emitted from a WCF service.</span></span>  
  
#### <a name="to-cleanup-optional"></a><span data-ttu-id="93a68-145">Para realizar la limpieza (Opcional)</span><span class="sxs-lookup"><span data-stu-id="93a68-145">To cleanup (Optional)</span></span>  
  
1.  <span data-ttu-id="93a68-146">Abra el Visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="93a68-146">Open Event Viewer.</span></span>  
  
2.  <span data-ttu-id="93a68-147">Vaya a **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación,  **Aplicaciones de servidor**.</span><span class="sxs-lookup"><span data-stu-id="93a68-147">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="93a68-148">Haga clic en **analítico** y seleccione **Deshabilitar registro**.</span><span class="sxs-lookup"><span data-stu-id="93a68-148">Right-click **Analytic** and select **Disable Log**.</span></span>  
  
3.  <span data-ttu-id="93a68-149">Vaya a **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación,  **Aplicaciones de servidor**.</span><span class="sxs-lookup"><span data-stu-id="93a68-149">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="93a68-150">Haga clic en **analítico** y seleccione **Vaciar registro**.</span><span class="sxs-lookup"><span data-stu-id="93a68-150">Right-click **Analytic** and select **Clear Log**.</span></span>  
  
4.  <span data-ttu-id="93a68-151">Elija la **borrar** opción para borrar los eventos.</span><span class="sxs-lookup"><span data-stu-id="93a68-151">Choose the **Clear** option to clear the events.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="93a68-152">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="93a68-152">The samples may already be installed on your computer.</span></span> <span data-ttu-id="93a68-153">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="93a68-153">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="93a68-154">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="93a68-154">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="93a68-155">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="93a68-155">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## <a name="see-also"></a><span data-ttu-id="93a68-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="93a68-156">See Also</span></span>  
 [<span data-ttu-id="93a68-157">Ejemplos de supervisión de AppFabric</span><span class="sxs-lookup"><span data-stu-id="93a68-157">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
