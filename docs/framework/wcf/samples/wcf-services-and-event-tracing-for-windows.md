---
title: Servicios de WCF y seguimiento de eventos para Windows
ms.date: 03/30/2017
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
ms.openlocfilehash: 100f9c0ce71eedaa4061fc894521597074b21b00
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2018
ms.locfileid: "49480036"
---
# <a name="wcf-services-and-event-tracing-for-windows"></a><span data-ttu-id="22941-102">Servicios de WCF y seguimiento de eventos para Windows</span><span class="sxs-lookup"><span data-stu-id="22941-102">WCF Services and Event Tracing for Windows</span></span>
<span data-ttu-id="22941-103">Este ejemplo muestra cómo utilizar la traza analítica en Windows Communication Foundation (WCF) para emitir eventos de seguimiento de eventos para Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="22941-103">This sample demonstrates how to use the analytic tracing in Windows Communication Foundation (WCF) to emit events in Event Tracing for Windows (ETW).</span></span> <span data-ttu-id="22941-104">Los seguimientos analíticos son los eventos emitidos en puntos clave de la pila de WCF que permiten solucionar problemas de servicios WCF en el entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="22941-104">The analytic traces are events emitted at key points in the WCF stack that allow troubleshooting of WCF services in production environment.</span></span>

 <span data-ttu-id="22941-105">Seguimiento la traza analítica en servicios WCF que puede activarse en un entorno de producción con un impacto mínimo en el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="22941-105">Analytic trace in WCF services is tracing that can be turned on in a production environment with minimal impact on performance.</span></span> <span data-ttu-id="22941-106">Estos seguimientos se emiten como eventos para una sesión de ETW.</span><span class="sxs-lookup"><span data-stu-id="22941-106">These traces are emitted as events to an ETW session.</span></span>

 <span data-ttu-id="22941-107">Este ejemplo incluye un servicio WCF básico en el que los eventos se emiten desde el servicio en el registro de eventos que se pueden ver mediante el Visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="22941-107">This sample includes a basic WCF service in which events are emitted from the service to the event log, which can be viewed using Event Viewer.</span></span> <span data-ttu-id="22941-108">También es posible iniciar una sesión ETW dedicada que escucha los eventos desde el servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="22941-108">It is also possible to start a dedicated ETW session that listens for events from the WCF service.</span></span> <span data-ttu-id="22941-109">En el ejemplo se incluye un script para crear una sesión de ETW dedicada que almacena los eventos en un archivo binario que se puede leer utilizando el Visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="22941-109">The sample includes a script to create a dedicated ETW session that stores events in a binary file that can be read using Event Viewer.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="22941-110">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="22941-110">To use this sample</span></span>

1.  <span data-ttu-id="22941-111">Con Visual Studio 2012, abra el archivo de solución EtwAnalyticTraceSample.sln.</span><span class="sxs-lookup"><span data-stu-id="22941-111">Using Visual Studio 2012, open the EtwAnalyticTraceSample.sln solution file.</span></span>

2.  <span data-ttu-id="22941-112">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="22941-112">To build the solution, press CTRL+SHIFT+B.</span></span>

3.  <span data-ttu-id="22941-113">Para ejecutar la solución, presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="22941-113">To run the solution, press CTRL+F5.</span></span>

     <span data-ttu-id="22941-114">En el explorador Web, haga clic en **Calculator.svc**.</span><span class="sxs-lookup"><span data-stu-id="22941-114">In the Web browser, click **Calculator.svc**.</span></span> <span data-ttu-id="22941-115">El URI del documento WSDL para el servicio debería aparecer en el explorador.</span><span class="sxs-lookup"><span data-stu-id="22941-115">The URI of the WSDL document for the service should appear in the browser.</span></span> <span data-ttu-id="22941-116">Copie ese URI.</span><span class="sxs-lookup"><span data-stu-id="22941-116">Copy that URI.</span></span>

     <span data-ttu-id="22941-117">De forma predeterminada, el servicio empieza a escuchar las solicitudes en el puerto 1378 `http://localhost:1378/Calculator.svc`.</span><span class="sxs-lookup"><span data-stu-id="22941-117">By default, the service starts listening for requests on port 1378 `http://localhost:1378/Calculator.svc`.</span></span>

4.  <span data-ttu-id="22941-118">Ejecute al cliente de prueba WCF (WcfTestClient.exe).</span><span class="sxs-lookup"><span data-stu-id="22941-118">Run the WCF test client (WcfTestClient.exe).</span></span>

     <span data-ttu-id="22941-119">El cliente de prueba WCF (WcfTestClient.exe) se encuentra en `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`.</span><span class="sxs-lookup"><span data-stu-id="22941-119">The WCF test client (WcfTestClient.exe) is located at `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`.</span></span>  <span data-ttu-id="22941-120">El directorio de instalación de Visual Studio 2012 de forma predeterminada es `C:\Program Files\Microsoft Visual Studio 10.0`.</span><span class="sxs-lookup"><span data-stu-id="22941-120">The default Visual Studio 2012 install dir is `C:\Program Files\Microsoft Visual Studio 10.0`.</span></span>

5.  <span data-ttu-id="22941-121">En el cliente de prueba WCF, agregue el servicio seleccionando **archivo**y, a continuación, **Agregar servicio**.</span><span class="sxs-lookup"><span data-stu-id="22941-121">Within the WCF test client, add the service by selecting **File**, and then **Add Service**.</span></span>

     <span data-ttu-id="22941-122">Agregue la dirección del punto de conexión en el cuadro de entrada.</span><span class="sxs-lookup"><span data-stu-id="22941-122">Add the endpoint address in the input box.</span></span> <span data-ttu-id="22941-123">De manera predeterminada, es `http://localhost:1378/Calculator.svc`.</span><span class="sxs-lookup"><span data-stu-id="22941-123">The default is `http://localhost:1378/Calculator.svc`.</span></span>

6.  <span data-ttu-id="22941-124">Abra la aplicación Visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="22941-124">Open the Event Viewer application.</span></span>

     <span data-ttu-id="22941-125">Antes de invocar el servicio, inicie el Visor de eventos y asegúrese de que el registro de eventos escucha eventos de seguimiento emitidos desde el servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="22941-125">Before invoking the service, start Event Viewer and ensure that the event log is listening for tracking events emitted from the WCF service.</span></span>

7.  <span data-ttu-id="22941-126">Desde el **iniciar** menú, seleccione **herramientas administrativas**y, a continuación, **Visor de eventos**.</span><span class="sxs-lookup"><span data-stu-id="22941-126">From the **Start** menu, select **Administrative Tools**, and then **Event Viewer**.</span></span>  <span data-ttu-id="22941-127">Habilitar la **analítico** y **depurar** registros.</span><span class="sxs-lookup"><span data-stu-id="22941-127">Enable the **Analytic** and **Debug** logs.</span></span>

8.  <span data-ttu-id="22941-128">En la vista de árbol en el Visor de eventos, vaya a **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación, **Aplicaciones de servidor-aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="22941-128">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="22941-129">Haga clic en **aplicaciones de servidor-aplicaciones**, seleccione **vista**y, a continuación, **mostrar registros analíticos y depuración**.</span><span class="sxs-lookup"><span data-stu-id="22941-129">Right-click **Application Server-Applications**, select **View**, and then **Show Analytic and Debug Logs**.</span></span>

     <span data-ttu-id="22941-130">Asegúrese de que el **mostrar registros analíticos y depuración** opción está activada.</span><span class="sxs-lookup"><span data-stu-id="22941-130">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span>

9. <span data-ttu-id="22941-131">Habilitar la **analítico** registro.</span><span class="sxs-lookup"><span data-stu-id="22941-131">Enable the **Analytic** log.</span></span>

     <span data-ttu-id="22941-132">En la vista de árbol en el Visor de eventos, vaya a **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación, **Aplicaciones de servidor-aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="22941-132">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="22941-133">Haga clic en **analítico** y seleccione **Habilitar registro**.</span><span class="sxs-lookup"><span data-stu-id="22941-133">Right-click **Analytic** and select **Enable Log**.</span></span>

#### <a name="to-test-the-service"></a><span data-ttu-id="22941-134">Para probar el servicio</span><span class="sxs-lookup"><span data-stu-id="22941-134">To test the service</span></span>

1.  <span data-ttu-id="22941-135">Vuelva al cliente de prueba WCF y haga doble clic en `Divide` y mantenga los valores predeterminados, que especifican el denominador 0.</span><span class="sxs-lookup"><span data-stu-id="22941-135">Switch back to WCF test client and double-click `Divide` and keep the default values, which specify a denominator of 0.</span></span>

     <span data-ttu-id="22941-136">Si el denominador es 0, el servicio produce un error.</span><span class="sxs-lookup"><span data-stu-id="22941-136">If the denominator is 0, then the service throws a fault.</span></span>

2.  <span data-ttu-id="22941-137">Observe los eventos emitidos desde el servicio.</span><span class="sxs-lookup"><span data-stu-id="22941-137">Observe the events emitted from the service.</span></span>

     <span data-ttu-id="22941-138">Cambie al Visor de eventos y navegue hasta **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación, **Aplicaciones de servidor-aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="22941-138">Switch back to Event Viewer and navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="22941-139">Haga clic en **analítico** y seleccione **actualizar**.</span><span class="sxs-lookup"><span data-stu-id="22941-139">Right-click **Analytic** and select **Refresh**.</span></span>

     <span data-ttu-id="22941-140">Los eventos de seguimiento analítico de WCF se muestran en el visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="22941-140">The WCF analytic trace events are displayed in the event viewer.</span></span> <span data-ttu-id="22941-141">Observe que dado que el servicio inició un error, se muestra un evento de seguimiento del error en el visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="22941-141">Notice that because a fault was thrown by the service an error trace event is displayed in the event viewer.</span></span>

3.  <span data-ttu-id="22941-142">Repita los pasos 1 y 2, pero con entradas válidas.</span><span class="sxs-lookup"><span data-stu-id="22941-142">Repeat steps 1 and 2, but with valid inputs.</span></span> <span data-ttu-id="22941-143">El valor del parámetro `N2` puede ser cualquier número distinto de 0.</span><span class="sxs-lookup"><span data-stu-id="22941-143">The value of the `N2` parameter can be any number other than 0.</span></span>

     <span data-ttu-id="22941-144">Actualice el canal analítico para ver los eventos de WCF que no incluyen ningún evento de error.</span><span class="sxs-lookup"><span data-stu-id="22941-144">Refresh the analytic channel to view the WCF events do not include any error events.</span></span>

 <span data-ttu-id="22941-145">En el ejemplo se muestran los eventos de seguimiento analíticos emitidos desde un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="22941-145">The sample demonstrates the analytic trace events emitted from a WCF service.</span></span>

#### <a name="to-cleanup-optional"></a><span data-ttu-id="22941-146">Para realizar la limpieza (Opcional)</span><span class="sxs-lookup"><span data-stu-id="22941-146">To cleanup (Optional)</span></span>

1.  <span data-ttu-id="22941-147">Abra el Visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="22941-147">Open Event Viewer.</span></span>

2.  <span data-ttu-id="22941-148">Vaya a **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación,  **Aplicaciones de servidor**.</span><span class="sxs-lookup"><span data-stu-id="22941-148">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="22941-149">Haga clic en **analítico** y seleccione **Deshabilitar registro**.</span><span class="sxs-lookup"><span data-stu-id="22941-149">Right-click **Analytic** and select **Disable Log**.</span></span>

3.  <span data-ttu-id="22941-150">Vaya a **Visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación,  **Aplicaciones de servidor**.</span><span class="sxs-lookup"><span data-stu-id="22941-150">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="22941-151">Haga clic en **analítico** y seleccione **Vaciar registro**.</span><span class="sxs-lookup"><span data-stu-id="22941-151">Right-click **Analytic** and select **Clear Log**.</span></span>

4.  <span data-ttu-id="22941-152">Elija la **borrar** opción para borrar los eventos.</span><span class="sxs-lookup"><span data-stu-id="22941-152">Choose the **Clear** option to clear the events.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="22941-153">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="22941-153">The samples may already be installed on your computer.</span></span> <span data-ttu-id="22941-154">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="22941-154">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="22941-155">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="22941-155">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="22941-156">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="22941-156">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## <a name="see-also"></a><span data-ttu-id="22941-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="22941-157">See Also</span></span>  
 [<span data-ttu-id="22941-158">Ejemplos de supervisión de AppFabric</span><span class="sxs-lookup"><span data-stu-id="22941-158">AppFabric Monitoring Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193959)
