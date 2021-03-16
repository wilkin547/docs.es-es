---
title: 'Tutorial: Creación de una aplicación de servicio de Windows'
description: En este tutorial se crea una aplicación de servicio de Windows en Visual Studio que escribe mensajes en un registro de eventos. Agregue características, establezca el estado, agregue instaladores, etc.
ms.date: 03/27/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows service applications, walkthroughs
- Windows service applications, creating
ms.assetid: e24d8a3d-edc6-485c-b6e0-5672d91fb607
ms.openlocfilehash: b6e4937b71c50f887a7eb784bc9106360a05fdc2
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102259803"
---
# <a name="tutorial-create-a-windows-service-app"></a><span data-ttu-id="b81cc-104">Tutorial: Creación de una aplicación de servicio de Windows</span><span class="sxs-lookup"><span data-stu-id="b81cc-104">Tutorial: Create a Windows service app</span></span>

<span data-ttu-id="b81cc-105">En este artículo se explica cómo crear una aplicación de servicio de Windows en Visual Studio que escribe mensajes en un registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="b81cc-105">This article demonstrates how to create a Windows service app in Visual Studio that writes messages to an event log.</span></span>

## <a name="create-a-service"></a><span data-ttu-id="b81cc-106">Creación de un servicio</span><span class="sxs-lookup"><span data-stu-id="b81cc-106">Create a service</span></span>

<span data-ttu-id="b81cc-107">Para empezar, cree el proyecto y defina los valores necesarios para que el servicio funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="b81cc-107">To begin, create the project and set the values that are required for the service to function correctly.</span></span>

1. <span data-ttu-id="b81cc-108">En el menú **Archivo** de Visual Studio, seleccione **Nuevo** > **Proyecto** (o presione **CTRL**+**Mayús**+**N**) para abrir la ventana **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="b81cc-108">From the Visual Studio **File** menu, select **New** > **Project** (or press **Ctrl**+**Shift**+**N**) to open the **New Project** window.</span></span>

2. <span data-ttu-id="b81cc-109">Vaya a la plantilla de proyecto **Windows Service (.NET Framework)** [Servicio de Windows (.NET Framework)] y selecciónela.</span><span class="sxs-lookup"><span data-stu-id="b81cc-109">Navigate to and select the **Windows Service (.NET Framework)** project template.</span></span> <span data-ttu-id="b81cc-110">Para encontrarla, expanda **Instalado** y **Visual C#**  o **Visual Basic**. Después, seleccione **Escritorio de Windows**.</span><span class="sxs-lookup"><span data-stu-id="b81cc-110">To find it, expand **Installed** and **Visual C#** or **Visual Basic**, then select **Windows Desktop**.</span></span> <span data-ttu-id="b81cc-111">También puede escribir *Servicio de Windows* en el cuadro de búsqueda en la esquina superior derecha y presionar **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="b81cc-111">Or, enter *Windows Service* in the search box on the upper right and press **Enter**.</span></span>

   ![Plantilla Servicio de Windows en el cuadro de diálogo Nuevo proyecto en Visual Studio](./media/new-project-dialog.png)

   > [!NOTE]
   > <span data-ttu-id="b81cc-113">Si no ve la plantilla **Servicio de Windows**, puede que tenga que instalar la carga de trabajo **Desarrollo de escritorio de .NET**:</span><span class="sxs-lookup"><span data-stu-id="b81cc-113">If you don't see the **Windows Service** template, you may need to install the **.NET desktop development** workload:</span></span>
   >
   > <span data-ttu-id="b81cc-114">En el cuadro de diálogo **Nuevo proyecto**, seleccione **Abrir el Instalador de Visual Studio** en la parte inferior izquierda.</span><span class="sxs-lookup"><span data-stu-id="b81cc-114">In the **New Project** dialog, select **Open Visual Studio Installer** on the lower left.</span></span> <span data-ttu-id="b81cc-115">Elija la carga de trabajo **Desarrollo de escritorio de .NET** y seleccione **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="b81cc-115">Select the **.NET desktop development** workload, and then select **Modify**.</span></span>

3. <span data-ttu-id="b81cc-116">En **Nombre**, escriba *MyNewService* y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b81cc-116">For **Name**, enter *MyNewService*, and then select **OK**.</span></span>

   <span data-ttu-id="b81cc-117">Aparecerá la pestaña **Diseño** (**Service1.cs [Diseño]** o **Service1.vb [Diseño]** ).</span><span class="sxs-lookup"><span data-stu-id="b81cc-117">The **Design** tab appears (**Service1.cs [Design]** or **Service1.vb [Design]**).</span></span>

   <span data-ttu-id="b81cc-118">La plantilla de proyecto incluye una clase de componente denominada `Service1`, que hereda de <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b81cc-118">The project template includes a component class named `Service1` that inherits from <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b81cc-119">Incluye gran parte del código de servicio básico, como el código para iniciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="b81cc-119">It includes much of the basic service code, such as the code to start the service.</span></span>

## <a name="rename-the-service"></a><span data-ttu-id="b81cc-120">Cambiar el nombre del servicio</span><span class="sxs-lookup"><span data-stu-id="b81cc-120">Rename the service</span></span>

<span data-ttu-id="b81cc-121">Cambie el nombre del servicio **Service1** por **MyNewService**.</span><span class="sxs-lookup"><span data-stu-id="b81cc-121">Rename the service from **Service1** to **MyNewService**.</span></span>

1. <span data-ttu-id="b81cc-122">En el **Explorador de soluciones**, elija **Service1.cs** o **Service1.vb** y seleccione **Cambiar nombre** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="b81cc-122">In **Solution Explorer**, select **Service1.cs**, or **Service1.vb**, and choose **Rename** from the shortcut menu.</span></span> <span data-ttu-id="b81cc-123">Cambie el nombre del archivo a **MyNewService.cs** o **MyNewService.vb** y presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="b81cc-123">Rename the file to **MyNewService.cs**, or **MyNewService.vb**, and then press **Enter**</span></span>

    <span data-ttu-id="b81cc-124">Aparecerá una ventana emergente en la que se le pregunta si quiere cambiar el nombre de todas las referencias al elemento de código *Service1*.</span><span class="sxs-lookup"><span data-stu-id="b81cc-124">A pop-up window appears asking whether you would like to rename all references to the code element *Service1*.</span></span>

2. <span data-ttu-id="b81cc-125">En la ventana emergente, seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="b81cc-125">In the pop-up window, select **Yes**.</span></span>

    <span data-ttu-id="b81cc-126">![Solicitud de cambio de nombre](./media/windows-service-rename.png "Solicitud de cambio de nombre del servicio de Windows")</span><span class="sxs-lookup"><span data-stu-id="b81cc-126">![Rename prompt](./media/windows-service-rename.png "Windows service rename prompt")</span></span>

3. <span data-ttu-id="b81cc-127">En la pestaña **Diseño**, seleccione **Propiedades** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="b81cc-127">In the **Design** tab, select **Properties** from the shortcut menu.</span></span> <span data-ttu-id="b81cc-128">En la ventana **Propiedades**, cambie el valor **ServiceName** a *MyNewService*.</span><span class="sxs-lookup"><span data-stu-id="b81cc-128">From the **Properties** window, change the **ServiceName** value to *MyNewService*.</span></span>

    <span data-ttu-id="b81cc-129">![Propiedades del servicio](./media/windows-service-properties.png "Propiedades del servicio de Windows")</span><span class="sxs-lookup"><span data-stu-id="b81cc-129">![Service properties](./media/windows-service-properties.png "Windows service properties")</span></span>

4. <span data-ttu-id="b81cc-130">Seleccione **Guardar todo** en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="b81cc-130">Select **Save All** from the **File** menu.</span></span>

## <a name="add-features-to-the-service"></a><span data-ttu-id="b81cc-131">Adición de características al servicio</span><span class="sxs-lookup"><span data-stu-id="b81cc-131">Add features to the service</span></span>

<span data-ttu-id="b81cc-132">En esta sección, agregará un registro de eventos personalizado al servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="b81cc-132">In this section, you add a custom event log to the Windows service.</span></span> <span data-ttu-id="b81cc-133">El componente <xref:System.Diagnostics.EventLog> es un ejemplo del tipo de componente que se puede agregar a un servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="b81cc-133">The <xref:System.Diagnostics.EventLog> component is an example of the type of component you can add to a Windows service.</span></span>

### <a name="add-custom-event-log-functionality"></a><span data-ttu-id="b81cc-134">Adición de la funcionalidad de registro de eventos personalizado</span><span class="sxs-lookup"><span data-stu-id="b81cc-134">Add custom event log functionality</span></span>

1. <span data-ttu-id="b81cc-135">En el **Explorador de soluciones**, en el menú contextual de **MyNewService.cs** o **MyNewService.vb**, elija **Diseñador de vistas**.</span><span class="sxs-lookup"><span data-stu-id="b81cc-135">In **Solution Explorer**, from the shortcut menu for **MyNewService.cs**, or **MyNewService.vb**, choose **View Designer**.</span></span>

2. <span data-ttu-id="b81cc-136">En el **Cuadro de herramientas**, expanda **Componentes** y arrastre el componente **EventLog** a la pestaña **Service1.cs [Diseño]** o  **Service1.vb [Diseño]** .</span><span class="sxs-lookup"><span data-stu-id="b81cc-136">In **Toolbox**, expand **Components**, and then drag the **EventLog** component to the **Service1.cs [Design]**, or **Service1.vb [Design]** tab.</span></span>

3. <span data-ttu-id="b81cc-137">En el **Explorador de soluciones**, en el menú contextual de **MyNewService.cs** o **MyNewService.vb**, elija **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="b81cc-137">In **Solution Explorer**, from the shortcut menu for **MyNewService.cs**, or **MyNewService.vb**, choose **View Code**.</span></span>

4. <span data-ttu-id="b81cc-138">Defina un registro de eventos personalizado.</span><span class="sxs-lookup"><span data-stu-id="b81cc-138">Define a custom event log.</span></span> <span data-ttu-id="b81cc-139">Para C#, edite el constructor `MyNewService()` existente; para Visual Basic, agregue el constructor `New()`:</span><span class="sxs-lookup"><span data-stu-id="b81cc-139">For C#, edit the existing `MyNewService()` constructor; for Visual Basic, add the `New()` constructor:</span></span>

   [!code-csharp[VbRadconService#2](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#2)]
   [!code-vb[VbRadconService#2](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#2)]

5. <span data-ttu-id="b81cc-140">Agregue una instrucción `using` a **MyNewService.cs** (si no existe) o una instrucción `Imports` a **MyNewService.vb** para el espacio de nombres <xref:System.Diagnostics?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="b81cc-140">Add a `using` statement to **MyNewService.cs** (if it doesn't already exist), or an `Imports` statement **MyNewService.vb**, for the <xref:System.Diagnostics?displayProperty=nameWithType> namespace:</span></span>

    ```csharp
    using System.Diagnostics;
    ```

    ```vb
    Imports System.Diagnostics
    ```

6. <span data-ttu-id="b81cc-141">Seleccione **Guardar todo** en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="b81cc-141">Select **Save All** from the **File** menu.</span></span>

### <a name="define-what-occurs-when-the-service-starts"></a><span data-ttu-id="b81cc-142">Definición de qué ocurre al iniciar el servicio</span><span class="sxs-lookup"><span data-stu-id="b81cc-142">Define what occurs when the service starts</span></span>

<span data-ttu-id="b81cc-143">En el editor de código para **MyNewService.cs** o **MyNewService.vb**, busque el método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> (Visual Studio creó automáticamente una definición de método vacía al crear el proyecto).</span><span class="sxs-lookup"><span data-stu-id="b81cc-143">In the code editor for **MyNewService.cs** or **MyNewService.vb**, locate the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method; Visual Studio automatically created an empty method definition when you created the project.</span></span> <span data-ttu-id="b81cc-144">Agregue código que escriba una entrada en el registro de eventos cuando el servicio se inicia:</span><span class="sxs-lookup"><span data-stu-id="b81cc-144">Add code that writes an entry to the event log when the service starts:</span></span>

[!code-csharp[VbRadconService#3](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#3)]
[!code-vb[VbRadconService#3](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#3)]

#### <a name="polling"></a><span data-ttu-id="b81cc-145">Sondeo</span><span class="sxs-lookup"><span data-stu-id="b81cc-145">Polling</span></span>

<span data-ttu-id="b81cc-146">Dado que una aplicación de servicio está diseñada para ejecutarse a largo plazo, suele sondear o supervisar el sistema, que se estableció en el método <xref:System.ServiceProcess.ServiceBase.OnStart%2A>.</span><span class="sxs-lookup"><span data-stu-id="b81cc-146">Because a service application is designed to be long-running, it usually polls or monitors the system, which you set up in the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method.</span></span> <span data-ttu-id="b81cc-147">El método `OnStart` debe volver al sistema operativo después de que haya comenzado el funcionamiento del servicio, a fin de que el sistema no se bloquee.</span><span class="sxs-lookup"><span data-stu-id="b81cc-147">The `OnStart` method must return to the operating system after the service's operation has begun so that the system isn't blocked.</span></span>

<span data-ttu-id="b81cc-148">Para establecer un mecanismo de sondeo sencillo, use el componente <xref:System.Timers.Timer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b81cc-148">To set up a simple polling mechanism, use the <xref:System.Timers.Timer?displayProperty=nameWithType> component.</span></span> <span data-ttu-id="b81cc-149">El temporizador genera un evento <xref:System.Timers.Timer.Elapsed> a intervalos regulares, momento en el que el servicio puede realizar la supervisión.</span><span class="sxs-lookup"><span data-stu-id="b81cc-149">The timer raises an <xref:System.Timers.Timer.Elapsed> event at regular intervals, at which time your service can do its monitoring.</span></span> <span data-ttu-id="b81cc-150">Use el componente <xref:System.Timers.Timer> como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="b81cc-150">You use the <xref:System.Timers.Timer> component as follows:</span></span>

- <span data-ttu-id="b81cc-151">Establezca las propiedades del componente <xref:System.Timers.Timer> en el método `MyNewService.OnStart`.</span><span class="sxs-lookup"><span data-stu-id="b81cc-151">Set the properties of the <xref:System.Timers.Timer> component in the `MyNewService.OnStart` method.</span></span>
- <span data-ttu-id="b81cc-152">Inicie el temporizador mediante una llamada al método <xref:System.Timers.Timer.Start%2A>.</span><span class="sxs-lookup"><span data-stu-id="b81cc-152">Start the timer by calling the <xref:System.Timers.Timer.Start%2A> method.</span></span>

##### <a name="set-up-the-polling-mechanism"></a><span data-ttu-id="b81cc-153">Establezca el mecanismo de sondeo.</span><span class="sxs-lookup"><span data-stu-id="b81cc-153">Set up the polling mechanism.</span></span>

1. <span data-ttu-id="b81cc-154">Agregue el código siguiente en el evento `MyNewService.OnStart` para configurar el mecanismo de sondeo:</span><span class="sxs-lookup"><span data-stu-id="b81cc-154">Add the following code in the `MyNewService.OnStart` event to set up the polling mechanism:</span></span>

   ```csharp
   // Set up a timer that triggers every minute.
   Timer timer = new Timer();
   timer.Interval = 60000; // 60 seconds
   timer.Elapsed += new ElapsedEventHandler(this.OnTimer);
   timer.Start();
   ```

   ```vb
   ' Set up a timer that triggers every minute.
   Dim timer As Timer = New Timer()
   timer.Interval = 60000 ' 60 seconds
   AddHandler timer.Elapsed, AddressOf Me.OnTimer
   timer.Start()
   ```

2. <span data-ttu-id="b81cc-155">Agregue una instrucción `using` a **MyNewService.cs** o una instrucción `Imports` a **MyNewService.vb** para el espacio de nombres <xref:System.Timers?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="b81cc-155">Add a `using` statement to **MyNewService.cs**, or an `Imports` statement to **MyNewService.vb**, for the <xref:System.Timers?displayProperty=nameWithType> namespace:</span></span>

   ```csharp
   using System.Timers;
   ```

   ```vb
   Imports System.Timers
   ```

3. <span data-ttu-id="b81cc-156">En la clase `MyNewService`, agregue el método `OnTimer` para controlar el evento <xref:System.Timers.Timer.Elapsed?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="b81cc-156">In the `MyNewService` class, add the `OnTimer` method to handle the <xref:System.Timers.Timer.Elapsed?displayProperty=nameWithType> event:</span></span>

   ```csharp
   public void OnTimer(object sender, ElapsedEventArgs args)
   {
       // TODO: Insert monitoring activities here.
       eventLog1.WriteEntry("Monitoring the System", EventLogEntryType.Information, eventId++);
   }
   ```

   ```vb
   Private Sub OnTimer(sender As Object, e As Timers.ElapsedEventArgs)
      ' TODO: Insert monitoring activities here.
      eventLog1.WriteEntry("Monitoring the System", EventLogEntryType.Information, eventId)
      eventId = eventId + 1
   End Sub
   ```

4. <span data-ttu-id="b81cc-157">En la clase `MyNewService`, agregue una variable de miembro.</span><span class="sxs-lookup"><span data-stu-id="b81cc-157">In the `MyNewService` class, add a member variable.</span></span> <span data-ttu-id="b81cc-158">Contiene el identificador del siguiente evento para escribir en el registro de eventos:</span><span class="sxs-lookup"><span data-stu-id="b81cc-158">It contains the identifier of the next event to write into the event log:</span></span>

   ```csharp
   private int eventId = 1;
   ```

   ```vb
   Private eventId As Integer = 1
   ```

<span data-ttu-id="b81cc-159">En lugar de ejecutar todo el trabajo en el subproceso principal, puede ejecutar las tareas mediante el uso de subprocesos de trabajo en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="b81cc-159">Instead of running all your work on the main thread, you can run tasks by using background worker threads.</span></span> <span data-ttu-id="b81cc-160">Para obtener más información, vea <xref:System.ComponentModel.BackgroundWorker?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="b81cc-160">For more information, see <xref:System.ComponentModel.BackgroundWorker?displayProperty=fullName>.</span></span>

### <a name="define-what-occurs-when-the-service-is-stopped"></a><span data-ttu-id="b81cc-161">Definición de qué ocurre al detener el servicio</span><span class="sxs-lookup"><span data-stu-id="b81cc-161">Define what occurs when the service is stopped</span></span>

<span data-ttu-id="b81cc-162">Inserte una línea de código en el método <xref:System.ServiceProcess.ServiceBase.OnStop%2A> que agregue una entrada al registro de eventos cuando el servicio se detenga:</span><span class="sxs-lookup"><span data-stu-id="b81cc-162">Insert a line of code in the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method that adds an entry to the event log when the service is stopped:</span></span>

[!code-csharp[VbRadconService#2](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#4)]
[!code-vb[VbRadconService#4](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#4)]

### <a name="define-other-actions-for-the-service"></a><span data-ttu-id="b81cc-163">Definición de otras acciones para el servicio</span><span class="sxs-lookup"><span data-stu-id="b81cc-163">Define other actions for the service</span></span>

<span data-ttu-id="b81cc-164">Puede invalidar los métodos <xref:System.ServiceProcess.ServiceBase.OnPause%2A>, <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> y <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> para definir un procesamiento adicional para el componente.</span><span class="sxs-lookup"><span data-stu-id="b81cc-164">You can override the <xref:System.ServiceProcess.ServiceBase.OnPause%2A>, <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>, and <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> methods to define additional processing for your component.</span></span>

<span data-ttu-id="b81cc-165">En el siguiente código se muestra cómo reemplazar el método <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> en la clase `MyNewService`:</span><span class="sxs-lookup"><span data-stu-id="b81cc-165">The following code shows how you to override the <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> method in the `MyNewService` class:</span></span>

[!code-csharp[VbRadconService#5](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#5)]
[!code-vb[VbRadconService#5](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#5)]

## <a name="set-service-status"></a><span data-ttu-id="b81cc-166">Definición del estado de servicio</span><span class="sxs-lookup"><span data-stu-id="b81cc-166">Set service status</span></span>

<span data-ttu-id="b81cc-167">Los servicios informan de su estado al [Administrador de control de servicios](/windows/desktop/Services/service-control-manager) para que los usuarios puedan saber si un servicio funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="b81cc-167">Services report their status to the [Service Control Manager](/windows/desktop/Services/service-control-manager) so that a user can tell whether a service is functioning correctly.</span></span> <span data-ttu-id="b81cc-168">De forma predeterminada, un servicio que hereda de <xref:System.ServiceProcess.ServiceBase> notifica un conjunto limitado de opciones de estado, entre las que se incluyen SERVICE_STOPPED, SERVICE_PAUSED y SERVICE_RUNNING.</span><span class="sxs-lookup"><span data-stu-id="b81cc-168">By default, a service that inherits from <xref:System.ServiceProcess.ServiceBase> reports a limited set of status settings, which include SERVICE_STOPPED, SERVICE_PAUSED, and SERVICE_RUNNING.</span></span> <span data-ttu-id="b81cc-169">Si un servicio tarda un poco en iniciarse, es útil informar de un estado SERVICE_START_PENDING.</span><span class="sxs-lookup"><span data-stu-id="b81cc-169">If a service takes a while to start up, it's useful to report a SERVICE_START_PENDING status.</span></span>

<span data-ttu-id="b81cc-170">Puede implementar las opciones de estado SERVICE_START_PENDING y SERVICE_STOP_PENDING si agrega código que llama a la función [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) de Windows.</span><span class="sxs-lookup"><span data-stu-id="b81cc-170">You can implement the SERVICE_START_PENDING and SERVICE_STOP_PENDING status settings by adding code that calls the Windows [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) function.</span></span>

### <a name="implement-service-pending-status"></a><span data-ttu-id="b81cc-171">Implementación del estado pendiente del servicio</span><span class="sxs-lookup"><span data-stu-id="b81cc-171">Implement service pending status</span></span>

1. <span data-ttu-id="b81cc-172">Agregue una instrucción `using` a **MyNewService.cs** o una instrucción `Imports` a **MyNewService.vb** para el espacio de nombres <xref:System.Runtime.InteropServices?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="b81cc-172">Add a `using` statement to **MyNewService.cs**, or an `Imports` statement to **MyNewService.vb**, for the <xref:System.Runtime.InteropServices?displayProperty=nameWithType> namespace:</span></span>

    ```csharp
    using System.Runtime.InteropServices;
    ```

    ```vb
    Imports System.Runtime.InteropServices
    ```

2. <span data-ttu-id="b81cc-173">Agregue el código siguiente a **MyNewService.cs** o **MyNewService.vb** para declarar los valores de `ServiceState` y para agregar una estructura para el estado, que usará en una llamada de invocación de plataforma:</span><span class="sxs-lookup"><span data-stu-id="b81cc-173">Add the following code to **MyNewService.cs**, or **MyNewService.vb**, to declare the `ServiceState` values and to add a structure for the status, which you'll use in a platform invoke call:</span></span>

    ```csharp
    public enum ServiceState
    {
        SERVICE_STOPPED = 0x00000001,
        SERVICE_START_PENDING = 0x00000002,
        SERVICE_STOP_PENDING = 0x00000003,
        SERVICE_RUNNING = 0x00000004,
        SERVICE_CONTINUE_PENDING = 0x00000005,
        SERVICE_PAUSE_PENDING = 0x00000006,
        SERVICE_PAUSED = 0x00000007,
    }

    [StructLayout(LayoutKind.Sequential)]
    public struct ServiceStatus
    {
        public int dwServiceType;
        public ServiceState dwCurrentState;
        public int dwControlsAccepted;
        public int dwWin32ExitCode;
        public int dwServiceSpecificExitCode;
        public int dwCheckPoint;
        public int dwWaitHint;
    };
    ```

    ```vb
    Public Enum ServiceState
        SERVICE_STOPPED = 1
        SERVICE_START_PENDING = 2
        SERVICE_STOP_PENDING = 3
        SERVICE_RUNNING = 4
        SERVICE_CONTINUE_PENDING = 5
        SERVICE_PAUSE_PENDING = 6
        SERVICE_PAUSED = 7
    End Enum

    <StructLayout(LayoutKind.Sequential)>
    Public Structure ServiceStatus
        Public dwServiceType As Long
        Public dwCurrentState As ServiceState
        Public dwControlsAccepted As Long
        Public dwWin32ExitCode As Long
        Public dwServiceSpecificExitCode As Long
        Public dwCheckPoint As Long
        Public dwWaitHint As Long
    End Structure
    ```

    > [!NOTE]
    > <span data-ttu-id="b81cc-174">El Administrador de control de servicios usa los miembros `dwWaitHint` y `dwCheckpoint` de la [estructura SERVICE_STATUS](/windows/win32/api/winsvc/ns-winsvc-service_status) para determinar durante cuánto tiempo hay que esperar a que un servicio de Windows se inicie o apague.</span><span class="sxs-lookup"><span data-stu-id="b81cc-174">The Service Control Manager uses the `dwWaitHint` and `dwCheckpoint` members of the [SERVICE_STATUS structure](/windows/win32/api/winsvc/ns-winsvc-service_status) to determine how much time to wait for a Windows service to start or shut down.</span></span> <span data-ttu-id="b81cc-175">Si los métodos `OnStart` y `OnStop` se ejecutan durante mucho tiempo, el servicio puede solicitar más tiempo por medio de una nueva llamada a `SetServiceStatus` con un valor de `dwCheckPoint` incrementado.</span><span class="sxs-lookup"><span data-stu-id="b81cc-175">If your `OnStart` and `OnStop` methods run long, your service can request more time by calling `SetServiceStatus` again with an incremented `dwCheckPoint` value.</span></span>

3. <span data-ttu-id="b81cc-176">En la clase `MyNewService`, declare la [función SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) mediante la [invocación de plataforma](../interop/consuming-unmanaged-dll-functions.md):</span><span class="sxs-lookup"><span data-stu-id="b81cc-176">In the `MyNewService` class, declare the [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) function by using [platform invoke](../interop/consuming-unmanaged-dll-functions.md):</span></span>

    ```csharp
    [DllImport("advapi32.dll", SetLastError = true)]
    private static extern bool SetServiceStatus(System.IntPtr handle, ref ServiceStatus serviceStatus);
    ```

    ```vb
    Declare Auto Function SetServiceStatus Lib "advapi32.dll" (ByVal handle As IntPtr, ByRef serviceStatus As ServiceStatus) As Boolean
    ```

4. <span data-ttu-id="b81cc-177">Para implementar el estado SERVICE_START_PENDING, agregue el código siguiente al principio del método <xref:System.ServiceProcess.ServiceBase.OnStart%2A>:</span><span class="sxs-lookup"><span data-stu-id="b81cc-177">To implement the SERVICE_START_PENDING status, add the following code to the beginning of the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method:</span></span>

    ```csharp
    // Update the service state to Start Pending.
    ServiceStatus serviceStatus = new ServiceStatus();
    serviceStatus.dwCurrentState = ServiceState.SERVICE_START_PENDING;
    serviceStatus.dwWaitHint = 100000;
    SetServiceStatus(this.ServiceHandle, ref serviceStatus);
    ```

    ```vb
    ' Update the service state to Start Pending.
    Dim serviceStatus As ServiceStatus = New ServiceStatus()
    serviceStatus.dwCurrentState = ServiceState.SERVICE_START_PENDING
    serviceStatus.dwWaitHint = 100000
    SetServiceStatus(Me.ServiceHandle, serviceStatus)
    ```

5. <span data-ttu-id="b81cc-178">Agregue código al final del método `OnStart` para establecer el estado en SERVICE_RUNNING:</span><span class="sxs-lookup"><span data-stu-id="b81cc-178">Add code to the end of the `OnStart` method to set the status to SERVICE_RUNNING:</span></span>

    ```csharp
    // Update the service state to Running.
    serviceStatus.dwCurrentState = ServiceState.SERVICE_RUNNING;
    SetServiceStatus(this.ServiceHandle, ref serviceStatus);
    ```

    ```vb
    ' Update the service state to Running.
    serviceStatus.dwCurrentState = ServiceState.SERVICE_RUNNING
    SetServiceStatus(Me.ServiceHandle, serviceStatus)
    ```

6. <span data-ttu-id="b81cc-179">(Opcional) Si <xref:System.ServiceProcess.ServiceBase.OnStop%2A> es un método de ejecución prolongada, repita este procedimiento en el método `OnStop`.</span><span class="sxs-lookup"><span data-stu-id="b81cc-179">(Optional) If <xref:System.ServiceProcess.ServiceBase.OnStop%2A> is a long-running method, repeat this procedure in the `OnStop` method.</span></span> <span data-ttu-id="b81cc-180">Implemente el estado SERVICE_STOP_PENDING y devuelva el estado SERVICE_STOPPED antes de que finalice el método `OnStop`.</span><span class="sxs-lookup"><span data-stu-id="b81cc-180">Implement the SERVICE_STOP_PENDING status and return the SERVICE_STOPPED status before the `OnStop` method exits.</span></span>

   <span data-ttu-id="b81cc-181">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b81cc-181">For example:</span></span>

    ```csharp
    // Update the service state to Stop Pending.
    ServiceStatus serviceStatus = new ServiceStatus();
    serviceStatus.dwCurrentState = ServiceState.SERVICE_STOP_PENDING;
    serviceStatus.dwWaitHint = 100000;
    SetServiceStatus(this.ServiceHandle, ref serviceStatus);

    // Update the service state to Stopped.
    serviceStatus.dwCurrentState = ServiceState.SERVICE_STOPPED;
    SetServiceStatus(this.ServiceHandle, ref serviceStatus);
    ```

    ```vb
    ' Update the service state to Stop Pending.
    Dim serviceStatus As ServiceStatus = New ServiceStatus()
    serviceStatus.dwCurrentState = ServiceState.SERVICE_STOP_PENDING
    serviceStatus.dwWaitHint = 100000
    SetServiceStatus(Me.ServiceHandle, serviceStatus)

    ' Update the service state to Stopped.
    serviceStatus.dwCurrentState = ServiceState.SERVICE_STOPPED
    SetServiceStatus(Me.ServiceHandle, serviceStatus)
    ```

## <a name="add-installers-to-the-service"></a><span data-ttu-id="b81cc-182">Adición de instaladores al servicio</span><span class="sxs-lookup"><span data-stu-id="b81cc-182">Add installers to the service</span></span>

<span data-ttu-id="b81cc-183">Para poder ejecutar un servicio de Windows, antes debe instalarlo, lo que lo registra con el Administrador de control de servicios.</span><span class="sxs-lookup"><span data-stu-id="b81cc-183">Before you run a Windows service, you need to install it, which registers it with the Service Control Manager.</span></span> <span data-ttu-id="b81cc-184">Agregue instaladores al proyecto que controlen los detalles del registro.</span><span class="sxs-lookup"><span data-stu-id="b81cc-184">Add installers to your project to handle the registration details.</span></span>

1. <span data-ttu-id="b81cc-185">En el **Explorador de soluciones**, en el menú contextual de **MyNewService.cs** o **MyNewService.vb**, elija **Diseñador de vistas**.</span><span class="sxs-lookup"><span data-stu-id="b81cc-185">In **Solution Explorer**, from the shortcut menu for **MyNewService.cs**, or **MyNewService.vb**, choose **View Designer**.</span></span>

2. <span data-ttu-id="b81cc-186">En la vista **Diseño**, seleccione el área de fondo y, después, elija **Agregar instalador** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="b81cc-186">In the **Design** view, select the background area, then choose **Add Installer** from the shortcut menu.</span></span>

     <span data-ttu-id="b81cc-187">De forma predeterminada, Visual Studio agrega al proyecto una clase de componente denominada `ProjectInstaller`, que contiene dos instaladores.</span><span class="sxs-lookup"><span data-stu-id="b81cc-187">By default, Visual Studio adds a component class named `ProjectInstaller`, which contains two installers, to your project.</span></span> <span data-ttu-id="b81cc-188">Estos instaladores son para el servicio y para el proceso asociado al servicio.</span><span class="sxs-lookup"><span data-stu-id="b81cc-188">These installers are for your service and for the service's associated process.</span></span>

3. <span data-ttu-id="b81cc-189">En la vista **Diseño** de **ProjectInstaller**, seleccione **serviceInstaller1** para un proyecto de Visual C# o **ServiceInstaller1** para un proyecto de Visual Basic. Después, seleccione **Propiedades** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="b81cc-189">In the **Design** view for **ProjectInstaller**, select **serviceInstaller1** for a Visual C# project, or **ServiceInstaller1** for a Visual Basic project, then choose **Properties** from the shortcut menu.</span></span>

4. <span data-ttu-id="b81cc-190">En la ventana **Propiedades**, compruebe que la propiedad <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> esté establecida en **MyNewService**.</span><span class="sxs-lookup"><span data-stu-id="b81cc-190">In the **Properties** window, verify the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property is set to **MyNewService**.</span></span>

5. <span data-ttu-id="b81cc-191">Agregue texto a la propiedad <xref:System.ServiceProcess.ServiceInstaller.Description%2A>, como *Servicio de ejemplo*.</span><span class="sxs-lookup"><span data-stu-id="b81cc-191">Add text to the <xref:System.ServiceProcess.ServiceInstaller.Description%2A> property, such as *A sample service*.</span></span>

     <span data-ttu-id="b81cc-192">Este texto aparece en la columna **Descripción** de la ventana **Servicios** y describe el servicio al usuario.</span><span class="sxs-lookup"><span data-stu-id="b81cc-192">This text appears in the **Description** column of the **Services** window and describes the service to the user.</span></span>

    <span data-ttu-id="b81cc-193">![Descripción del servicio en la ventana Servicios](./media/windows-service-description.png "Descripción del servicio").</span><span class="sxs-lookup"><span data-stu-id="b81cc-193">![Service description in the Services window.](./media/windows-service-description.png "Service description")</span></span>

6. <span data-ttu-id="b81cc-194">Agregue texto a la propiedad <xref:System.ServiceProcess.ServiceInstaller.DisplayName%2A>.</span><span class="sxs-lookup"><span data-stu-id="b81cc-194">Add text to the <xref:System.ServiceProcess.ServiceInstaller.DisplayName%2A> property.</span></span> <span data-ttu-id="b81cc-195">Por ejemplo, *Nombre para mostrar de MyNewService*.</span><span class="sxs-lookup"><span data-stu-id="b81cc-195">For example, *MyNewService Display Name*.</span></span>

     <span data-ttu-id="b81cc-196">Este texto aparece en la columna **Nombre para mostrar** de la ventana **Servicios**.</span><span class="sxs-lookup"><span data-stu-id="b81cc-196">This text appears in the **Display Name** column of the **Services** window.</span></span> <span data-ttu-id="b81cc-197">Este nombre puede ser diferente de la propiedad <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A>, que es el nombre usado por el sistema (por ejemplo, el nombre que usa en el comando `net start` para iniciar el servicio).</span><span class="sxs-lookup"><span data-stu-id="b81cc-197">This name can be different from the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property, which is the name the system uses (for example, the name you use for the `net start` command to start your service).</span></span>

7. <span data-ttu-id="b81cc-198">Establezca la propiedad <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> en <xref:System.ServiceProcess.ServiceStartMode.Automatic> en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="b81cc-198">Set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to <xref:System.ServiceProcess.ServiceStartMode.Automatic> from the drop-down list.</span></span>

8. <span data-ttu-id="b81cc-199">Cuando haya terminado, la ventana **Propiedades** debería tener un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="b81cc-199">When you're finished, the **Properties** windows should look like the following figure:</span></span>

     <span data-ttu-id="b81cc-200">![Propiedades del instalador de un servicio de Windows](./media/windows-service-installer-properties.png "Propiedades del instalador del servicio de Windows")</span><span class="sxs-lookup"><span data-stu-id="b81cc-200">![Installer Properties for a Windows service](./media/windows-service-installer-properties.png "Windows service installer properties")</span></span>

9. <span data-ttu-id="b81cc-201">En la vista **Diseño** de **ProjectInstaller**, seleccione **serviceProcessInstaller1** para un proyecto de Visual C# o **ServiceProcessInstaller1** para un proyecto de Visual Basic. Después, seleccione **Propiedades** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="b81cc-201">In the **Design** view for **ProjectInstaller**, choose **serviceProcessInstaller1** for a Visual C# project, or **ServiceProcessInstaller1** for a Visual Basic project, then choose **Properties** from the shortcut menu.</span></span> <span data-ttu-id="b81cc-202">Establezca la propiedad <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> en <xref:System.ServiceProcess.ServiceAccount.LocalSystem> en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="b81cc-202">Set the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> property to <xref:System.ServiceProcess.ServiceAccount.LocalSystem> from the drop-down list.</span></span>

     <span data-ttu-id="b81cc-203">Esta opción instala el servicio y lo ejecuta mediante el uso de la cuenta del sistema local.</span><span class="sxs-lookup"><span data-stu-id="b81cc-203">This setting installs the service and runs it by using the local system account.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="b81cc-204">La cuenta <xref:System.ServiceProcess.ServiceAccount.LocalSystem> tiene amplios permisos, incluida la capacidad para escribir en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="b81cc-204">The <xref:System.ServiceProcess.ServiceAccount.LocalSystem> account has broad permissions, including the ability to write to the event log.</span></span> <span data-ttu-id="b81cc-205">Utilice esta cuenta con precaución porque podría aumentar el riesgo de ataques por parte de software malintencionado.</span><span class="sxs-lookup"><span data-stu-id="b81cc-205">Use this account with caution, because it might increase your risk of attacks from malicious software.</span></span> <span data-ttu-id="b81cc-206">Para otras tareas, considere la posibilidad de usar la cuenta <xref:System.ServiceProcess.ServiceAccount.LocalService> , que actúa como un usuario sin privilegios en el equipo local y presenta credenciales anónimas a cualquier servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="b81cc-206">For other tasks, consider using the <xref:System.ServiceProcess.ServiceAccount.LocalService> account, which acts as a non-privileged user on the local computer and presents anonymous credentials to any remote server.</span></span> <span data-ttu-id="b81cc-207">En este ejemplo se produce un error si intenta usar la cuenta <xref:System.ServiceProcess.ServiceAccount.LocalService> , ya que necesita permiso de escritura en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="b81cc-207">This example fails if you try to use the <xref:System.ServiceProcess.ServiceAccount.LocalService> account, because it needs permission to write to the event log.</span></span>

<span data-ttu-id="b81cc-208">Para más información sobre los instaladores, consulte [Procedimiento para agregar instaladores a una aplicación de servicio](how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="b81cc-208">For more information about installers, see [How to: Add installers to your service application](how-to-add-installers-to-your-service-application.md).</span></span>

## <a name="optional-set-startup-parameters"></a><span data-ttu-id="b81cc-209">(Opcional) Establecer parámetros de inicio</span><span class="sxs-lookup"><span data-stu-id="b81cc-209">(Optional) Set startup parameters</span></span>

> [!NOTE]
> <span data-ttu-id="b81cc-210">Antes de decidirse a agregar parámetros de inicio, piense en si es la mejor manera de pasar información al servicio.</span><span class="sxs-lookup"><span data-stu-id="b81cc-210">Before you decide to add startup parameters, consider whether it's the best way to pass information to your service.</span></span> <span data-ttu-id="b81cc-211">Aunque son fáciles de usar y analizar, y los usuarios pueden reemplazarlos fácilmente, pueden ser más difíciles de descubrir y usar para los usuarios sin documentación.</span><span class="sxs-lookup"><span data-stu-id="b81cc-211">Although they're easy to use and parse, and a user can easily override them, they might be harder for a user to discover and use without documentation.</span></span> <span data-ttu-id="b81cc-212">Por lo general, si el servicio requiere más de unos pocos parámetros de inicio, debe usar el Registro o un archivo de configuración en su lugar.</span><span class="sxs-lookup"><span data-stu-id="b81cc-212">Generally, if your service requires more than just a few startup parameters, you should use the registry or a configuration file instead.</span></span>

<span data-ttu-id="b81cc-213">Un servicio de Windows puede aceptar argumentos de línea de comandos o parámetros de inicio.</span><span class="sxs-lookup"><span data-stu-id="b81cc-213">A Windows service can accept command-line arguments, or startup parameters.</span></span> <span data-ttu-id="b81cc-214">Cuando se agrega código para procesar los parámetros de inicio, los usuarios pueden iniciar el servicio con sus propios parámetros de inicio personalizados en la ventana de propiedades del servicio.</span><span class="sxs-lookup"><span data-stu-id="b81cc-214">When you add code to process startup parameters, a user can start your service with their own custom startup parameters in the service properties window.</span></span> <span data-ttu-id="b81cc-215">Aun así, estos parámetros de inicio no se conservan la próxima vez que se inicia el servicio.</span><span class="sxs-lookup"><span data-stu-id="b81cc-215">However, these startup parameters aren't persisted the next time the service starts.</span></span> <span data-ttu-id="b81cc-216">Para establecer los parámetros de inicio de forma permanente, establézcalos en el Registro.</span><span class="sxs-lookup"><span data-stu-id="b81cc-216">To set startup parameters permanently, set them in the registry.</span></span>

<span data-ttu-id="b81cc-217">Cada servicio de Windows tiene una entrada del Registro en la subclave **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services**.</span><span class="sxs-lookup"><span data-stu-id="b81cc-217">Each Windows service has a registry entry under the **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services** subkey.</span></span> <span data-ttu-id="b81cc-218">En la subclave de cada servicio, use la subclave **Parameters** para almacenar la información a la que puede tener acceso su servicio.</span><span class="sxs-lookup"><span data-stu-id="b81cc-218">Under each service's subkey, use the **Parameters** subkey to store information that your service can access.</span></span> <span data-ttu-id="b81cc-219">Puede usar archivos de configuración de aplicación para un servicio de Windows del mismo modo que lo hace para otros tipos de programas.</span><span class="sxs-lookup"><span data-stu-id="b81cc-219">You can use application configuration files for a Windows service the same way you do for other types of programs.</span></span> <span data-ttu-id="b81cc-220">Para ver un ejemplo de código, consulte <xref:System.Configuration.ConfigurationManager.AppSettings?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b81cc-220">For sample code, see <xref:System.Configuration.ConfigurationManager.AppSettings?displayProperty=nameWithType>.</span></span>

### <a name="to-add-startup-parameters"></a><span data-ttu-id="b81cc-221">Para agregar parámetros de inicio</span><span class="sxs-lookup"><span data-stu-id="b81cc-221">To add startup parameters</span></span>

1. <span data-ttu-id="b81cc-222">Seleccione **Program.cs** o **MyNewService.Designer.vb** y, después, **Ver código** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="b81cc-222">Select **Program.cs**, or **MyNewService.Designer.vb**, then choose **View Code** from the shortcut menu.</span></span> <span data-ttu-id="b81cc-223">En el método `Main`, cambie el código para agregar un parámetro de entrada y pasarlo al constructor del servicio:</span><span class="sxs-lookup"><span data-stu-id="b81cc-223">In the `Main` method, change the code to add an input parameter and pass it to the service constructor:</span></span>

   [!code-csharp[VbRadconService](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/Program-add-parameter.cs?highlight=1,6)]
   [!code-vb[VbRadconService](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.Designer-add-parameter.vb?highlight=1-2)]

2. <span data-ttu-id="b81cc-224">En **MyNewService.cs** o **MyNewService.vb**, cambie el constructor `MyNewService` para procesar el parámetro de entrada de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="b81cc-224">In **MyNewService.cs**, or **MyNewService.vb**, change the `MyNewService` constructor to process the input parameter as follows:</span></span>

   ```csharp
   using System.Diagnostics;

   public MyNewService(string[] args)
   {
       InitializeComponent();

       string eventSourceName = "MySource";
       string logName = "MyNewLog";

       if (args.Length > 0)
       {
          eventSourceName = args[0];
       }

       if (args.Length > 1)
       {
           logName = args[1];
       }

       eventLog1 = new EventLog();

       if (!EventLog.SourceExists(eventSourceName))
       {
           EventLog.CreateEventSource(eventSourceName, logName);
       }

       eventLog1.Source = eventSourceName;
       eventLog1.Log = logName;
   }
   ```

   ```vb
   Imports System.Diagnostics

   Public Sub New(ByVal cmdArgs() As String)
       InitializeComponent()
       Dim eventSourceName As String = "MySource"
       Dim logName As String = "MyNewLog"
       If (cmdArgs.Count() > 0) Then
           eventSourceName = cmdArgs(0)
       End If
       If (cmdArgs.Count() > 1) Then
           logName = cmdArgs(1)
       End If
       eventLog1 = New EventLog()
       If (Not EventLog.SourceExists(eventSourceName)) Then
           EventLog.CreateEventSource(eventSourceName, logName)
       End If
       eventLog1.Source = eventSourceName
       eventLog1.Log = logName
   End Sub
   ```

   <span data-ttu-id="b81cc-225">Este código establece el nombre del origen del evento y del registro según los parámetros de inicio que proporciona el usuario.</span><span class="sxs-lookup"><span data-stu-id="b81cc-225">This code sets the event source and log name according to the startup parameters that the user supplies.</span></span> <span data-ttu-id="b81cc-226">Si no se proporciona ningún argumento, usa los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="b81cc-226">If no arguments are supplied, it uses default values.</span></span>

3. <span data-ttu-id="b81cc-227">Para especificar los argumentos de línea de comandos, agregue el código siguiente a la clase `ProjectInstaller` en **ProjectInstaller.cs** o **ProjectInstaller.vb**:</span><span class="sxs-lookup"><span data-stu-id="b81cc-227">To specify the command-line arguments, add the following code to the `ProjectInstaller` class in **ProjectInstaller.cs**, or **ProjectInstaller.vb**:</span></span>

   ```csharp
   protected override void OnBeforeInstall(IDictionary savedState)
   {
       string parameter = "MySource1\" \"MyLogFile1";
       Context.Parameters["assemblypath"] = "\"" + Context.Parameters["assemblypath"] + "\" \"" + parameter + "\"";
       base.OnBeforeInstall(savedState);
   }
   ```

   ```vb
   Protected Overrides Sub OnBeforeInstall(ByVal savedState As IDictionary)
       Dim parameter As String = "MySource1"" ""MyLogFile1"
       Context.Parameters("assemblypath") = """" + Context.Parameters("assemblypath") + """ """ + parameter + """"
       MyBase.OnBeforeInstall(savedState)
   End Sub
   ```

   <span data-ttu-id="b81cc-228">Normalmente, este valor contiene la ruta de acceso completa al archivo ejecutable para el servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="b81cc-228">Typically, this value contains the full path to the executable for the Windows service.</span></span> <span data-ttu-id="b81cc-229">Para que el servicio se inicie correctamente, el usuario debe incluir comillas en la ruta de acceso y en cada parámetro individual.</span><span class="sxs-lookup"><span data-stu-id="b81cc-229">For the service to start up correctly, the user must supply quotation marks for the path and each individual parameter.</span></span> <span data-ttu-id="b81cc-230">Un usuario puede cambiar los parámetros en la entrada del Registro **ImagePath** para cambiar los parámetros de inicio para el servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="b81cc-230">A user can change the parameters in the **ImagePath** registry entry to change the startup parameters for the Windows service.</span></span> <span data-ttu-id="b81cc-231">Aun así, lo mejor es cambiar el valor mediante programación y exponer la funcionalidad de una manera más fácil, por ejemplo, mediante una utilidad de administración o configuración.</span><span class="sxs-lookup"><span data-stu-id="b81cc-231">However, a better way is to change the value programmatically and expose the functionality in a user-friendly way, such as by using a management or configuration utility.</span></span>

## <a name="build-the-service"></a><span data-ttu-id="b81cc-232">Compilación del servicio</span><span class="sxs-lookup"><span data-stu-id="b81cc-232">Build the service</span></span>

1. <span data-ttu-id="b81cc-233">En el **Explorador de soluciones**, seleccione **Propiedades** en el menú contextual del proyecto **MyNewService**.</span><span class="sxs-lookup"><span data-stu-id="b81cc-233">In **Solution Explorer**, choose **Properties** from the shortcut menu for the **MyNewService** project.</span></span>

   <span data-ttu-id="b81cc-234">Aparecerán las páginas de propiedades del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b81cc-234">The property pages for your project appear.</span></span>

2. <span data-ttu-id="b81cc-235">En la pestaña **Aplicación**, en la lista **Objeto de inicio**, elija **MyNewService.Program**, o bien **Sub Main** para proyectos de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b81cc-235">On the **Application** tab, in the **Startup object** list, choose **MyNewService.Program**, or **Sub Main** for Visual Basic projects.</span></span>

3. <span data-ttu-id="b81cc-236">Para compilar el proyecto, en el **Explorador de soluciones**, seleccione **Compilar** en el menú contextual del proyecto (o bien presione **CTRL**+**Mayús**+**B**).</span><span class="sxs-lookup"><span data-stu-id="b81cc-236">To build the project, in **Solution Explorer**, choose **Build** from the shortcut menu for your project (or press **Ctrl**+**Shift**+**B**).</span></span>

## <a name="install-the-service"></a><span data-ttu-id="b81cc-237">Instalación del servicio</span><span class="sxs-lookup"><span data-stu-id="b81cc-237">Install the service</span></span>

<span data-ttu-id="b81cc-238">Ahora que ha compilado el servicio de Windows, puede instalarlo.</span><span class="sxs-lookup"><span data-stu-id="b81cc-238">Now that you've built the Windows service, you can install it.</span></span> <span data-ttu-id="b81cc-239">Para instalar un servicio de Windows, debe tener credenciales de administrador en el equipo en el que lo va a instalar.</span><span class="sxs-lookup"><span data-stu-id="b81cc-239">To install a Windows service, you must have administrator credentials on the computer where it's installed.</span></span>

1. <span data-ttu-id="b81cc-240">Abra un [Símbolo del sistema para desarrolladores para Visual Studio](/visualstudio/ide/reference/command-prompt-powershell) con credenciales administrativas.</span><span class="sxs-lookup"><span data-stu-id="b81cc-240">Open [Developer Command Prompt for Visual Studio](/visualstudio/ide/reference/command-prompt-powershell) with administrative credentials.</span></span>

2. <span data-ttu-id="b81cc-241">En **Developer Command Prompt for Visual Studio** (Símbolo del sistema para desarrolladores de Visual Studio), desplácese hasta la carpeta que contiene la salida del proyecto (de forma predeterminada, es el subdirectorio *\bin\Debug* del proyecto).</span><span class="sxs-lookup"><span data-stu-id="b81cc-241">In **Developer Command Prompt for Visual Studio**, navigate to the folder that contains your project's output (by default, the *\bin\Debug* subdirectory of your project).</span></span>

3. <span data-ttu-id="b81cc-242">Escriba el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="b81cc-242">Enter the following command:</span></span>

    ```shell
    installutil MyNewService.exe
    ```

    <span data-ttu-id="b81cc-243">Si el servicio se instala correctamente, el comando indica que la instalación ha sido correcta.</span><span class="sxs-lookup"><span data-stu-id="b81cc-243">If the service installs successfully, the command reports success.</span></span>

    <span data-ttu-id="b81cc-244">Si el sistema no encuentra *installutil.exe*, asegúrese de que existe en el equipo.</span><span class="sxs-lookup"><span data-stu-id="b81cc-244">If the system can't find *installutil.exe*, make sure that it exists on your computer.</span></span> <span data-ttu-id="b81cc-245">Esta herramienta se instala con .NET Framework en la carpeta *%windir%\Microsoft.NET\Framework[64]\\&lt;[versión de Framework]&gt;* .</span><span class="sxs-lookup"><span data-stu-id="b81cc-245">This tool is installed with the .NET Framework to the folder *%windir%\Microsoft.NET\Framework[64]\\&lt;framework version&gt;*.</span></span> <span data-ttu-id="b81cc-246">Por ejemplo, la ruta de acceso predeterminada para la versión de 64 bits es *%windir%\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.</span><span class="sxs-lookup"><span data-stu-id="b81cc-246">For example, the default path for the 64-bit version is *%windir%\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.</span></span>

    <span data-ttu-id="b81cc-247">Si se produce un error en el proceso **installutil.exe**, compruebe el registro de instalación para averiguar a qué se debe.</span><span class="sxs-lookup"><span data-stu-id="b81cc-247">If the **installutil.exe** process fails, check the install log to find out why.</span></span> <span data-ttu-id="b81cc-248">De manera predeterminada, el registro está en la misma carpeta que el ejecutable del servicio.</span><span class="sxs-lookup"><span data-stu-id="b81cc-248">By default, the log is in the same folder as the service executable.</span></span> <span data-ttu-id="b81cc-249">Puede producirse un error en la instalación en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b81cc-249">The installation can fail if:</span></span>
    - <span data-ttu-id="b81cc-250">La clase <xref:System.ComponentModel.RunInstallerAttribute> no está presente en la clase `ProjectInstaller`.</span><span class="sxs-lookup"><span data-stu-id="b81cc-250">The <xref:System.ComponentModel.RunInstallerAttribute> class isn't present on the `ProjectInstaller` class.</span></span>
    - <span data-ttu-id="b81cc-251">El atributo no se ha establecido en `true`.</span><span class="sxs-lookup"><span data-stu-id="b81cc-251">The attribute isn't set to `true`.</span></span>
    - <span data-ttu-id="b81cc-252">La clase `ProjectInstaller` no se ha definido como `public`.</span><span class="sxs-lookup"><span data-stu-id="b81cc-252">The `ProjectInstaller` class isn't defined as `public`.</span></span>

<span data-ttu-id="b81cc-253">Para obtener más información, vea [Cómo: Instalar y desinstalar servicios](how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="b81cc-253">For more information, see [How to: Install and uninstall services](how-to-install-and-uninstall-services.md).</span></span>

## <a name="start-and-run-the-service"></a><span data-ttu-id="b81cc-254">Inicio y ejecución del servicio</span><span class="sxs-lookup"><span data-stu-id="b81cc-254">Start and run the service</span></span>

1. <span data-ttu-id="b81cc-255">En Windows, abra la aplicación de escritorio **Servicios**.</span><span class="sxs-lookup"><span data-stu-id="b81cc-255">In Windows, open the **Services** desktop app.</span></span> <span data-ttu-id="b81cc-256">Presione **Windows**+**R** para abrir el cuadro **Ejecutar**, escriba *services.msc* y presione la tecla **ENTRAR** o haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b81cc-256">Press **Windows**+**R** to open the **Run** box, enter *services.msc*, and then press **Enter** or select **OK**.</span></span>

     <span data-ttu-id="b81cc-257">El servicio debería aparecer en **Servicios**, mostrado en orden alfabético por el nombre para mostrar que se haya establecido.</span><span class="sxs-lookup"><span data-stu-id="b81cc-257">You should see your service listed in **Services**, displayed alphabetically by the display name that you set for it.</span></span>

     ![MyNewService en la ventana Servicios.](./media/windowsservices-serviceswindow.PNG)

2. <span data-ttu-id="b81cc-259">Para iniciar el servicio, seleccione **Iniciar** en el menú contextual del servicio.</span><span class="sxs-lookup"><span data-stu-id="b81cc-259">To start the service, choose **Start** from the service's shortcut menu.</span></span>

3. <span data-ttu-id="b81cc-260">Para detener el servicio, seleccione **Detener** en el menú contextual del servicio.</span><span class="sxs-lookup"><span data-stu-id="b81cc-260">To stop the service, choose **Stop** from the service's shortcut menu.</span></span>

4. <span data-ttu-id="b81cc-261">(Opcional) En la línea de comandos, use los comandos **net start &lt;nombre del servicio&gt;** y **net stop &lt;nombre del servicio&gt;** para iniciar y detener el servicio.</span><span class="sxs-lookup"><span data-stu-id="b81cc-261">(Optional) From the command line, use the commands **net start &lt;service name&gt;** and **net stop &lt;service name&gt;** to start and stop your service.</span></span>

### <a name="verify-the-event-log-output-of-your-service"></a><span data-ttu-id="b81cc-262">Verificación de la salida del registro de eventos del servicio</span><span class="sxs-lookup"><span data-stu-id="b81cc-262">Verify the event log output of your service</span></span>

1. <span data-ttu-id="b81cc-263">En Windows, abra la aplicación de escritorio **Visor de eventos**.</span><span class="sxs-lookup"><span data-stu-id="b81cc-263">In Windows, open the **Event Viewer** desktop app.</span></span> <span data-ttu-id="b81cc-264">Escriba *Visor de eventos* en la barra de búsqueda de Windows y, después, seleccione **Visor de eventos** en los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b81cc-264">Enter *Event Viewer* in the Windows search bar, and then select **Event Viewer** from the search results.</span></span>

   > [!TIP]
   > <span data-ttu-id="b81cc-265">Para obtener acceso a los registros de eventos en Visual Studio, abra el **Explorador de servidores** en el menú **Vista** (o presione **CTRL**+**Alt**+**S**) y expanda el nodo **Registros de eventos** para el equipo local.</span><span class="sxs-lookup"><span data-stu-id="b81cc-265">In Visual Studio, you can access event logs by opening **Server Explorer** from the **View** menu (or press **Ctrl**+**Alt**+**S**) and expanding the **Event Logs** node for the local computer.</span></span>

2. <span data-ttu-id="b81cc-266">En **Visor de eventos**, expanda **Registros de aplicaciones y servicios**.</span><span class="sxs-lookup"><span data-stu-id="b81cc-266">In **Event Viewer**, expand **Applications and Services Logs**.</span></span>

3. <span data-ttu-id="b81cc-267">Localice la lista correspondiente a **MyNewLog** (o **MyLogFile1** si ha seguido el procedimiento para agregar argumentos de línea de comandos) y expándala.</span><span class="sxs-lookup"><span data-stu-id="b81cc-267">Locate the listing for **MyNewLog** (or **MyLogFile1** if you followed the procedure to add command-line arguments) and expand it.</span></span> <span data-ttu-id="b81cc-268">Debería ver las entradas de las dos acciones (iniciar y detener) que el servicio ha llevado a cabo.</span><span class="sxs-lookup"><span data-stu-id="b81cc-268">You should see the entries for the two actions (start and stop) that your service performed.</span></span>

     ![Uso del Visor de eventos para consultar las entradas del registro de eventos](./media/windows-service-event-viewer.png)

## <a name="clean-up-resources"></a><span data-ttu-id="b81cc-270">Limpiar los recursos</span><span class="sxs-lookup"><span data-stu-id="b81cc-270">Clean up resources</span></span>

<span data-ttu-id="b81cc-271">Si ya no necesita la aplicación de servicio de Windows, puede quitarla.</span><span class="sxs-lookup"><span data-stu-id="b81cc-271">If you no longer need the Windows service app, you can remove it.</span></span>

1. <span data-ttu-id="b81cc-272">Abra un **Símbolo del sistema para desarrolladores para Visual Studio** con credenciales administrativas.</span><span class="sxs-lookup"><span data-stu-id="b81cc-272">Open **Developer Command Prompt for Visual Studio** with administrative credentials.</span></span>

2. <span data-ttu-id="b81cc-273">En la ventana **Developer Command Prompt for Visual Studio** (Símbolo del sistema para desarrolladores de Visual Studio), desplácese hasta la carpeta que contiene la salida del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b81cc-273">In the **Developer Command Prompt for Visual Studio** window, navigate to the folder that contains your project's output.</span></span>

3. <span data-ttu-id="b81cc-274">Escriba el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="b81cc-274">Enter the following command:</span></span>

    ```shell
    installutil.exe /u MyNewService.exe
    ```

   <span data-ttu-id="b81cc-275">Si el servicio se desinstala correctamente, el comando indica que el servicio se ha quitado correctamente.</span><span class="sxs-lookup"><span data-stu-id="b81cc-275">If the service uninstalls successfully, the command reports that your service was successfully removed.</span></span> <span data-ttu-id="b81cc-276">Para obtener más información, vea [Cómo: Instalar y desinstalar servicios](how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="b81cc-276">For more information, see [How to: Install and uninstall services](how-to-install-and-uninstall-services.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="b81cc-277">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="b81cc-277">Next steps</span></span>

<span data-ttu-id="b81cc-278">Ahora que ha creado el servicio, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b81cc-278">Now that you've created the service, you can:</span></span>

- <span data-ttu-id="b81cc-279">Crear un programa de instalación independiente a fin de que otros usuarios lo puedan emplear para instalar el servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="b81cc-279">Create a standalone setup program for others to use to install your Windows service.</span></span> <span data-ttu-id="b81cc-280">Use el [Conjunto de herramientas de WiX](https://wixtoolset.org/) con el objeto de crear un instalador para un servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="b81cc-280">Use the [WiX Toolset](https://wixtoolset.org/) to create an installer for a Windows service.</span></span> <span data-ttu-id="b81cc-281">Para otras ideas, vea [Crear un paquete de instalador](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).</span><span class="sxs-lookup"><span data-stu-id="b81cc-281">For other ideas, see [Create an installer package](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).</span></span>

- <span data-ttu-id="b81cc-282">Explorar el componente <xref:System.ServiceProcess.ServiceController>, que permite enviar comandos al servicio instalado.</span><span class="sxs-lookup"><span data-stu-id="b81cc-282">Explore the <xref:System.ServiceProcess.ServiceController> component, which enables you to send commands to the service you've installed.</span></span>

- <span data-ttu-id="b81cc-283">En lugar de crear el registro de eventos cuando se ejecuta la aplicación, use un instalador para crearlo al instalar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b81cc-283">Instead of creating the event log when the application runs, use an installer to create an event log when you install the application.</span></span> <span data-ttu-id="b81cc-284">El instalador elimina el registro de eventos cuando se desinstala la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b81cc-284">The event log is deleted by the installer when you uninstall the application.</span></span> <span data-ttu-id="b81cc-285">Para obtener más información, vea <xref:System.Diagnostics.EventLogInstaller>.</span><span class="sxs-lookup"><span data-stu-id="b81cc-285">For more information, see <xref:System.Diagnostics.EventLogInstaller>.</span></span>

## <a name="see-also"></a><span data-ttu-id="b81cc-286">Vea también</span><span class="sxs-lookup"><span data-stu-id="b81cc-286">See also</span></span>

- [<span data-ttu-id="b81cc-287">Aplicaciones de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="b81cc-287">Windows service applications</span></span>](index.md)
- [<span data-ttu-id="b81cc-288">Introducción a las aplicaciones de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="b81cc-288">Introduction to Windows service applications</span></span>](introduction-to-windows-service-applications.md)
- [<span data-ttu-id="b81cc-289">Cómo: Depurar aplicaciones de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="b81cc-289">How to: Debug Windows service applications</span></span>](how-to-debug-windows-service-applications.md)
- [<span data-ttu-id="b81cc-290">Servicios (Windows)</span><span class="sxs-lookup"><span data-stu-id="b81cc-290">Services (Windows)</span></span>](/windows/desktop/Services/services)
