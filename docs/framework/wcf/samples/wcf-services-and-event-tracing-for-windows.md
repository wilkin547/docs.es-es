---
title: Servicios de WCF y seguimiento de eventos para Windows
ms.date: 03/30/2017
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
ms.openlocfilehash: b8a1f30f20aa2c541a574a070b3644569d633ca2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183211"
---
# <a name="wcf-services-and-event-tracing-for-windows"></a><span data-ttu-id="389ba-102">Servicios de WCF y seguimiento de eventos para Windows</span><span class="sxs-lookup"><span data-stu-id="389ba-102">WCF Services and Event Tracing for Windows</span></span>
<span data-ttu-id="389ba-103">En este ejemplo se muestra cómo usar el seguimiento analítico en Windows Communication Foundation (WCF) para emitir eventos en Seguimiento de eventos para Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="389ba-103">This sample demonstrates how to use the analytic tracing in Windows Communication Foundation (WCF) to emit events in Event Tracing for Windows (ETW).</span></span> <span data-ttu-id="389ba-104">Los seguimientos analíticos son eventos emitidos en puntos clave de la pila de WCF que permiten la solución de problemas de servicios WCF en el entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="389ba-104">The analytic traces are events emitted at key points in the WCF stack that allow troubleshooting of WCF services in production environment.</span></span>

 <span data-ttu-id="389ba-105">Seguimiento analítico en los servicios WCF es el seguimiento que se puede activar en un entorno de producción con un impacto mínimo en el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="389ba-105">Analytic trace in WCF services is tracing that can be turned on in a production environment with minimal impact on performance.</span></span> <span data-ttu-id="389ba-106">Estos seguimientos se emiten como eventos para una sesión de ETW.</span><span class="sxs-lookup"><span data-stu-id="389ba-106">These traces are emitted as events to an ETW session.</span></span>

 <span data-ttu-id="389ba-107">Este ejemplo incluye un servicio WCF básico en el que los eventos se emiten desde el servicio al registro de eventos, que se puede ver mediante el Visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="389ba-107">This sample includes a basic WCF service in which events are emitted from the service to the event log, which can be viewed using Event Viewer.</span></span> <span data-ttu-id="389ba-108">También es posible iniciar una sesión ETW dedicada que escucha eventos del servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="389ba-108">It is also possible to start a dedicated ETW session that listens for events from the WCF service.</span></span> <span data-ttu-id="389ba-109">En el ejemplo se incluye un script para crear una sesión de ETW dedicada que almacena los eventos en un archivo binario que se puede leer utilizando el Visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="389ba-109">The sample includes a script to create a dedicated ETW session that stores events in a binary file that can be read using Event Viewer.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="389ba-110">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="389ba-110">To use this sample</span></span>

1. <span data-ttu-id="389ba-111">Con Visual Studio 2012, abra el archivo de solución EtwAnalyticTraceSample.sln.</span><span class="sxs-lookup"><span data-stu-id="389ba-111">Using Visual Studio 2012, open the EtwAnalyticTraceSample.sln solution file.</span></span>

2. <span data-ttu-id="389ba-112">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="389ba-112">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="389ba-113">Para ejecutar la solución, presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="389ba-113">To run the solution, press CTRL+F5.</span></span>

     <span data-ttu-id="389ba-114">En el explorador web, haga clic en **Calculator.svc**.</span><span class="sxs-lookup"><span data-stu-id="389ba-114">In the Web browser, click **Calculator.svc**.</span></span> <span data-ttu-id="389ba-115">El URI del documento WSDL para el servicio debería aparecer en el explorador.</span><span class="sxs-lookup"><span data-stu-id="389ba-115">The URI of the WSDL document for the service should appear in the browser.</span></span> <span data-ttu-id="389ba-116">Copie ese URI.</span><span class="sxs-lookup"><span data-stu-id="389ba-116">Copy that URI.</span></span>

     <span data-ttu-id="389ba-117">De forma predeterminada, el servicio comienza a escuchar `http://localhost:1378/Calculator.svc`las solicitudes en el puerto 1378.</span><span class="sxs-lookup"><span data-stu-id="389ba-117">By default, the service starts listening for requests on port 1378 `http://localhost:1378/Calculator.svc`.</span></span>

4. <span data-ttu-id="389ba-118">Ejecute el cliente de prueba WCF (WcfTestClient.exe).</span><span class="sxs-lookup"><span data-stu-id="389ba-118">Run the WCF test client (WcfTestClient.exe).</span></span>

     <span data-ttu-id="389ba-119">El cliente de prueba WCF (WcfTestClient.exe) se encuentra en `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`.</span><span class="sxs-lookup"><span data-stu-id="389ba-119">The WCF test client (WcfTestClient.exe) is located at `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`.</span></span>  <span data-ttu-id="389ba-120">El dir de instalación predeterminado de `C:\Program Files\Microsoft Visual Studio 10.0`Visual Studio 2012 es .</span><span class="sxs-lookup"><span data-stu-id="389ba-120">The default Visual Studio 2012 install dir is `C:\Program Files\Microsoft Visual Studio 10.0`.</span></span>

5. <span data-ttu-id="389ba-121">En el cliente de prueba WCF, agregue el servicio seleccionando **Archivo**y, a continuación, **Agregar servicio**.</span><span class="sxs-lookup"><span data-stu-id="389ba-121">Within the WCF test client, add the service by selecting **File**, and then **Add Service**.</span></span>

     <span data-ttu-id="389ba-122">Agregue la dirección del punto de conexión en el cuadro de entrada.</span><span class="sxs-lookup"><span data-stu-id="389ba-122">Add the endpoint address in the input box.</span></span> <span data-ttu-id="389ba-123">El valor predeterminado es `http://localhost:1378/Calculator.svc`.</span><span class="sxs-lookup"><span data-stu-id="389ba-123">The default is `http://localhost:1378/Calculator.svc`.</span></span>

6. <span data-ttu-id="389ba-124">Abra la aplicación Visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="389ba-124">Open the Event Viewer application.</span></span>

     <span data-ttu-id="389ba-125">Antes de invocar el servicio, inicie el Visor de eventos y asegúrese de que el registro de eventos está escuchando los eventos de seguimiento emitidos desde el servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="389ba-125">Before invoking the service, start Event Viewer and ensure that the event log is listening for tracking events emitted from the WCF service.</span></span>

7. <span data-ttu-id="389ba-126">En el menú **Inicio** , seleccione **Herramientas administrativas**y, a continuación, Visor **de eventos**.</span><span class="sxs-lookup"><span data-stu-id="389ba-126">From the **Start** menu, select **Administrative Tools**, and then **Event Viewer**.</span></span>  <span data-ttu-id="389ba-127">Habilite los registros **analíticos** y **de depuración.**</span><span class="sxs-lookup"><span data-stu-id="389ba-127">Enable the **Analytic** and **Debug** logs.</span></span>

8. <span data-ttu-id="389ba-128">En la vista de árbol del Visor de eventos, vaya a **Visor de**eventos , **Registros**de aplicaciones y servicios , **Microsoft**, **Windows**y, a continuación, Aplicaciones **del servidor**de aplicaciones .</span><span class="sxs-lookup"><span data-stu-id="389ba-128">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="389ba-129">Haga clic con el botón secundario en **Application Server-Applications**, seleccione **View**y, a continuación, Mostrar registros **analíticos y de depuración**.</span><span class="sxs-lookup"><span data-stu-id="389ba-129">Right-click **Application Server-Applications**, select **View**, and then **Show Analytic and Debug Logs**.</span></span>

     <span data-ttu-id="389ba-130">Asegúrese de que la opción Mostrar registros **analíticos y de depuración** esté marcada.</span><span class="sxs-lookup"><span data-stu-id="389ba-130">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span>

9. <span data-ttu-id="389ba-131">Habilite el registro **analítico.**</span><span class="sxs-lookup"><span data-stu-id="389ba-131">Enable the **Analytic** log.</span></span>

     <span data-ttu-id="389ba-132">En la vista de árbol del Visor de eventos, vaya a **Visor de**eventos , **Registros**de aplicaciones y servicios , **Microsoft**, **Windows**y, a continuación, Aplicaciones **del servidor**de aplicaciones .</span><span class="sxs-lookup"><span data-stu-id="389ba-132">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="389ba-133">Haga clic con el botón derecho en **Analítico** y seleccione **Habilitar registro**.</span><span class="sxs-lookup"><span data-stu-id="389ba-133">Right-click **Analytic** and select **Enable Log**.</span></span>

#### <a name="to-test-the-service"></a><span data-ttu-id="389ba-134">Para probar el servicio</span><span class="sxs-lookup"><span data-stu-id="389ba-134">To test the service</span></span>

1. <span data-ttu-id="389ba-135">Vuelva al cliente de prueba `Divide` WCF y haga doble clic y mantenga los valores predeterminados, que especifican un denominador de 0.</span><span class="sxs-lookup"><span data-stu-id="389ba-135">Switch back to WCF test client and double-click `Divide` and keep the default values, which specify a denominator of 0.</span></span>

     <span data-ttu-id="389ba-136">Si el denominador es 0, el servicio produce un error.</span><span class="sxs-lookup"><span data-stu-id="389ba-136">If the denominator is 0, then the service throws a fault.</span></span>

2. <span data-ttu-id="389ba-137">Observe los eventos emitidos desde el servicio.</span><span class="sxs-lookup"><span data-stu-id="389ba-137">Observe the events emitted from the service.</span></span>

     <span data-ttu-id="389ba-138">Vuelva al Visor de eventos y vaya a **Visor de**eventos , **Registros**de aplicaciones y servicios , **Microsoft**, **Windows**y, a continuación, Aplicaciones **del servidor**de aplicaciones .</span><span class="sxs-lookup"><span data-stu-id="389ba-138">Switch back to Event Viewer and navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="389ba-139">Haga clic con el botón derecho en **Analítico** y seleccione **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="389ba-139">Right-click **Analytic** and select **Refresh**.</span></span>

     <span data-ttu-id="389ba-140">Los eventos de seguimiento analítico de WCF se muestran en el visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="389ba-140">The WCF analytic trace events are displayed in the event viewer.</span></span> <span data-ttu-id="389ba-141">Observe que dado que el servicio inició un error, se muestra un evento de seguimiento del error en el visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="389ba-141">Notice that because a fault was thrown by the service an error trace event is displayed in the event viewer.</span></span>

3. <span data-ttu-id="389ba-142">Repita los pasos 1 y 2, pero con entradas válidas.</span><span class="sxs-lookup"><span data-stu-id="389ba-142">Repeat steps 1 and 2, but with valid inputs.</span></span> <span data-ttu-id="389ba-143">El valor del parámetro `N2` puede ser cualquier número distinto de 0.</span><span class="sxs-lookup"><span data-stu-id="389ba-143">The value of the `N2` parameter can be any number other than 0.</span></span>

     <span data-ttu-id="389ba-144">Actualice el canal analítico para ver los eventos de WCF que no incluyen ningún evento de error.</span><span class="sxs-lookup"><span data-stu-id="389ba-144">Refresh the analytic channel to view the WCF events do not include any error events.</span></span>

 <span data-ttu-id="389ba-145">En el ejemplo se muestran los eventos de seguimiento analíticos emitidos desde un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="389ba-145">The sample demonstrates the analytic trace events emitted from a WCF service.</span></span>

#### <a name="to-cleanup-optional"></a><span data-ttu-id="389ba-146">Para realizar la limpieza (Opcional)</span><span class="sxs-lookup"><span data-stu-id="389ba-146">To cleanup (Optional)</span></span>

1. <span data-ttu-id="389ba-147">Abra el Visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="389ba-147">Open Event Viewer.</span></span>

2. <span data-ttu-id="389ba-148">Vaya a **Visor de**eventos , **Registros**de aplicaciones y servicios , **Microsoft**, **Windows**y, a continuación, **Aplicaciones de servidor de**aplicaciones .</span><span class="sxs-lookup"><span data-stu-id="389ba-148">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="389ba-149">Haga clic con el botón derecho en **Analítico** y seleccione **Desactivar registro**.</span><span class="sxs-lookup"><span data-stu-id="389ba-149">Right-click **Analytic** and select **Disable Log**.</span></span>

3. <span data-ttu-id="389ba-150">Vaya a **Visor de**eventos , **Registros**de aplicaciones y servicios , **Microsoft**, **Windows**y, a continuación, **Aplicaciones de servidor de**aplicaciones .</span><span class="sxs-lookup"><span data-stu-id="389ba-150">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="389ba-151">Haga clic con el botón derecho en **Analítico** y seleccione **Borrar registro**.</span><span class="sxs-lookup"><span data-stu-id="389ba-151">Right-click **Analytic** and select **Clear Log**.</span></span>

4. <span data-ttu-id="389ba-152">Elija la opción **Borrar** para borrar los eventos.</span><span class="sxs-lookup"><span data-stu-id="389ba-152">Choose the **Clear** option to clear the events.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="389ba-153">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="389ba-153">The samples may already be installed on your computer.</span></span> <span data-ttu-id="389ba-154">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="389ba-154">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="389ba-155">Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="389ba-155">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="389ba-156">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="389ba-156">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## <a name="see-also"></a><span data-ttu-id="389ba-157">Consulte también</span><span class="sxs-lookup"><span data-stu-id="389ba-157">See also</span></span>

- <span data-ttu-id="389ba-158">[Ejemplos de supervisión de AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="389ba-158">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
