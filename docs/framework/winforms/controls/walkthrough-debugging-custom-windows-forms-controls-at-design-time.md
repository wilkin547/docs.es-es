---
title: "Tutorial: Depurar controles personalizados de formularios Windows Forms en tiempo de diseño"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- debugging [Visual Studio], walkthroughs
- custom controls [Windows Forms], walkthroughs
- visual editors
- debugging [Visual Studio], Windows Forms
- custom controls [Windows Forms], debugging
- designers
- controls [Windows Forms], debugging
- walkthroughs [Windows Forms], debugging
- design-time debugging
ms.assetid: 1fd83ccd-3798-42fc-85a3-6cba99467387
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7fd38f6246d44bd24753d9c86a5b0b08819d3db7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-debugging-custom-windows-forms-controls-at-design-time"></a><span data-ttu-id="2a230-102">Tutorial: Depurar controles personalizados de formularios Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="2a230-102">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>
<span data-ttu-id="2a230-103">Cuando se crea un control personalizado, a menudo encontrará es necesario para depurar su comportamiento en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="2a230-103">When you create a custom control, you will often find it necessary to debug its design-time behavior.</span></span> <span data-ttu-id="2a230-104">Esto es especialmente cierto si va a crear un diseñador personalizado para el control personalizado.</span><span class="sxs-lookup"><span data-stu-id="2a230-104">This is especially true if you are authoring a custom designer for your custom control.</span></span> <span data-ttu-id="2a230-105">Para obtener más información, consulte [Tutorial: crear un Windows Forms Control que toma ventaja de tiempo de diseño características de Visual Studio](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).</span><span class="sxs-lookup"><span data-stu-id="2a230-105">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).</span></span>  
  
 <span data-ttu-id="2a230-106">Puede depurar sus controles personalizados mediante Visual Studio, tal y como se harían otras clases de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2a230-106">You can debug your custom controls using Visual Studio, just as you would debug any other .NET Framework classes.</span></span> <span data-ttu-id="2a230-107">La diferencia es que depurará una instancia independiente de Visual Studio que está ejecutando código del control personalizado</span><span class="sxs-lookup"><span data-stu-id="2a230-107">The difference is that you will debug a separate instance of Visual Studio that is running your custom control's code</span></span>  
  
 <span data-ttu-id="2a230-108">Las tareas ilustradas en este tutorial incluyen:</span><span class="sxs-lookup"><span data-stu-id="2a230-108">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="2a230-109">Crear un proyecto de formularios Windows Forms para hospedar el control personalizado</span><span class="sxs-lookup"><span data-stu-id="2a230-109">Creating a Windows Forms project to host your custom control</span></span>  
  
-   <span data-ttu-id="2a230-110">Crear un proyecto de biblioteca de controles</span><span class="sxs-lookup"><span data-stu-id="2a230-110">Creating a control library project</span></span>  
  
-   <span data-ttu-id="2a230-111">Agregar una propiedad al control personalizado</span><span class="sxs-lookup"><span data-stu-id="2a230-111">Adding a property to your custom control</span></span>  
  
-   <span data-ttu-id="2a230-112">Agregar el control personalizado al formulario de host</span><span class="sxs-lookup"><span data-stu-id="2a230-112">Adding your custom control to the host form</span></span>  
  
-   <span data-ttu-id="2a230-113">Configurar el proyecto para la depuración en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="2a230-113">Setting up the project for design-time debugging</span></span>  
  
-   <span data-ttu-id="2a230-114">Depurar el control personalizado en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="2a230-114">Debugging your custom control at design time</span></span>  
  
 <span data-ttu-id="2a230-115">Cuando haya terminado, tendrá un conocimiento de las tareas necesarias para depurar el comportamiento en tiempo de diseño de un control personalizado.</span><span class="sxs-lookup"><span data-stu-id="2a230-115">When you are finished, you will have an understanding of the tasks necessary for debugging the design-time behavior of a custom control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a230-116">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="2a230-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="2a230-117">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="2a230-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="2a230-118">Para obtener más información, consulte [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="2a230-118">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="2a230-119">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="2a230-119">Creating the Project</span></span>  
 <span data-ttu-id="2a230-120">El primer paso es crear el proyecto de aplicación.</span><span class="sxs-lookup"><span data-stu-id="2a230-120">The first step is to create the application project.</span></span> <span data-ttu-id="2a230-121">Este proyecto se utilizará para compilar la aplicación que hospeda el control personalizado.</span><span class="sxs-lookup"><span data-stu-id="2a230-121">You will use this project to build the application that hosts the custom control.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="2a230-122">Para crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="2a230-122">To create the project</span></span>  
  
-   <span data-ttu-id="2a230-123">Cree un proyecto de aplicación de Windows denominado "DebuggingExample".</span><span class="sxs-lookup"><span data-stu-id="2a230-123">Create a Windows Application project called "DebuggingExample".</span></span> <span data-ttu-id="2a230-124">Para ver detalles, consulte [Cómo: Crear un nuevo proyecto de aplicación de Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span><span class="sxs-lookup"><span data-stu-id="2a230-124">For details, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
## <a name="creating-a-control-library-project"></a><span data-ttu-id="2a230-125">Crear un proyecto de biblioteca de controles</span><span class="sxs-lookup"><span data-stu-id="2a230-125">Creating a Control Library Project</span></span>  
 <span data-ttu-id="2a230-126">El siguiente paso es crear el proyecto de biblioteca de controles y configurar el control personalizado.</span><span class="sxs-lookup"><span data-stu-id="2a230-126">The next step is to create the control library project and set up the custom control.</span></span>  
  
#### <a name="to-create-the-control-library-project"></a><span data-ttu-id="2a230-127">Para crear el proyecto de biblioteca de controles</span><span class="sxs-lookup"><span data-stu-id="2a230-127">To create the control library project</span></span>  
  
1.  <span data-ttu-id="2a230-128">Agregar un **biblioteca de controles de Windows** proyecto a la solución.</span><span class="sxs-lookup"><span data-stu-id="2a230-128">Add a **Windows Control Library** project to the solution.</span></span>  
  
2.  <span data-ttu-id="2a230-129">Agregue un nuevo **UserControl** elemento al proyecto DebugControlLibrary.</span><span class="sxs-lookup"><span data-stu-id="2a230-129">Add a new **UserControl** item to the DebugControlLibrary project.</span></span> <span data-ttu-id="2a230-130">Para obtener más información, consulte [NIB: Cómo: agregar nuevos elementos de proyecto](http://msdn.microsoft.com/en-us/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).</span><span class="sxs-lookup"><span data-stu-id="2a230-130">For details, see [NIB:How to: Add New Project Items](http://msdn.microsoft.com/en-us/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).</span></span> <span data-ttu-id="2a230-131">Asigne al archivo de origen nuevo un nombre de base de "DebugControl".</span><span class="sxs-lookup"><span data-stu-id="2a230-131">Give the new source file a base name of "DebugControl".</span></span>  
  
3.  <span data-ttu-id="2a230-132">Mediante el **el Explorador de soluciones**, elimine el control predeterminado del proyecto eliminando el archivo de código con un nombre de base de "`UserControl1`".</span><span class="sxs-lookup"><span data-stu-id="2a230-132">Using the **Solution Explorer**, delete the project's default control by deleting the code file with a base name of "`UserControl1`".</span></span> <span data-ttu-id="2a230-133">Para obtener más información, consulte [NIB: Cómo: quitar, eliminar y excluir elementos](http://msdn.microsoft.com/en-us/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).</span><span class="sxs-lookup"><span data-stu-id="2a230-133">For details, see [NIB:How to: Remove, Delete, and Exclude Items](http://msdn.microsoft.com/en-us/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).</span></span>  
  
4.  <span data-ttu-id="2a230-134">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="2a230-134">Build the solution.</span></span>  
  
## <a name="checkpoint"></a><span data-ttu-id="2a230-135">Punto de control</span><span class="sxs-lookup"><span data-stu-id="2a230-135">Checkpoint</span></span>  
 <span data-ttu-id="2a230-136">En este momento, podrá ver el control personalizado en el **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="2a230-136">At this point, you will be able to see your custom control in the **Toolbox**.</span></span>  
  
#### <a name="to-check-your-progress"></a><span data-ttu-id="2a230-137">Para comprobar su progreso</span><span class="sxs-lookup"><span data-stu-id="2a230-137">To check your progress</span></span>  
  
-   <span data-ttu-id="2a230-138">Busque la nueva ficha denominada **componentes de DebugControlLibrary** y haga clic para seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="2a230-138">Find the new tab called **DebugControlLibrary Components** and click to select it.</span></span> <span data-ttu-id="2a230-139">Cuando se abre, verá el control aparece como **DebugControl** con el icono predeterminado junto a él.</span><span class="sxs-lookup"><span data-stu-id="2a230-139">When it opens, you will see your control listed as **DebugControl** with the default icon beside it.</span></span>  
  
## <a name="adding-a-property-to-your-custom-control"></a><span data-ttu-id="2a230-140">Agregar una propiedad al Control personalizado</span><span class="sxs-lookup"><span data-stu-id="2a230-140">Adding a Property to Your Custom Control</span></span>  
 <span data-ttu-id="2a230-141">Para demostrar que se está ejecutando código del control personalizado en tiempo de diseño, agregará una propiedad y establezca un punto de interrupción en el código que implementa la propiedad.</span><span class="sxs-lookup"><span data-stu-id="2a230-141">To demonstrate that your custom control's code is running at design-time, you will add a property and set a breakpoint in the code that implements the property.</span></span>  
  
#### <a name="to-add-a-property-to-your-custom-control"></a><span data-ttu-id="2a230-142">Para agregar una propiedad al control personalizado</span><span class="sxs-lookup"><span data-stu-id="2a230-142">To add a property to your custom control</span></span>  
  
1.  <span data-ttu-id="2a230-143">Abra **DebugControl** en el **Editor de código**.</span><span class="sxs-lookup"><span data-stu-id="2a230-143">Open **DebugControl** in the **Code Editor**.</span></span> <span data-ttu-id="2a230-144">Agregue el código siguiente a la definición de clase:</span><span class="sxs-lookup"><span data-stu-id="2a230-144">Add the following code to the class definition:</span></span>  
  
    ```vb  
    Private demoStringValue As String = Nothing  
    <BrowsableAttribute(true)>  
    Public Property DemoString() As String  
  
        Get  
            Return Me.demoStringValue  
        End Get  
  
        Set(ByVal value As String)  
            Me.demoStringValue = value  
        End Set  
  
    End Property  
    ```  
  
    ```csharp  
    private string demoStringValue = null;  
    [Browsable(true)]  
    public string DemoString  
    {  
        get  
        {  
            return this.demoStringValue;  
        }  
        set  
        {  
            demoStringValue = value;  
        }  
    }  
    ```  
  
2.  <span data-ttu-id="2a230-145">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="2a230-145">Build the solution.</span></span>  
  
## <a name="adding-your-custom-control-to-the-host-form"></a><span data-ttu-id="2a230-146">Agregar el Control personalizado al formulario de Host</span><span class="sxs-lookup"><span data-stu-id="2a230-146">Adding Your Custom Control to the Host Form</span></span>  
 <span data-ttu-id="2a230-147">Para depurar el comportamiento en tiempo de diseño del control personalizado, deberá colocar una instancia de la clase de control personalizado en un formulario de host.</span><span class="sxs-lookup"><span data-stu-id="2a230-147">To debug the design-time behavior of your custom control, you will place an instance of the custom control class on a host form.</span></span>  
  
#### <a name="to-add-your-custom-control-to-the-host-form"></a><span data-ttu-id="2a230-148">Para agregar el control personalizado en el formulario de host</span><span class="sxs-lookup"><span data-stu-id="2a230-148">To add your custom control to the host form</span></span>  
  
1.  <span data-ttu-id="2a230-149">En el proyecto "DebuggingExample", abra Form1 en el **Diseñador de Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="2a230-149">In the "DebuggingExample" project, open Form1 in the **Windows Forms Designer**.</span></span>  
  
2.  <span data-ttu-id="2a230-150">En el **cuadro de herramientas**, abra el **componentes de DebugControlLibrary** pestaña y arrastre un **DebugControl** instancia en el formulario.</span><span class="sxs-lookup"><span data-stu-id="2a230-150">In the **Toolbox**, open the **DebugControlLibrary Components** tab and drag a **DebugControl** instance onto the form.</span></span>  
  
3.  <span data-ttu-id="2a230-151">Buscar el `DemoString` propiedad personalizada en el **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="2a230-151">Find the `DemoString` custom property in the **Properties** window.</span></span> <span data-ttu-id="2a230-152">Tenga en cuenta que puede cambiar el valor tal y como lo haría con cualquier otra propiedad.</span><span class="sxs-lookup"><span data-stu-id="2a230-152">Note that you can change its value as you would any other property.</span></span> <span data-ttu-id="2a230-153">Tenga en cuenta también que, cuando la `DemoString` propiedad está seleccionada, la cadena de descripción de la propiedad aparece en la parte inferior de la **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="2a230-153">Also note that when the `DemoString` property is selected, the property's description string appears at the bottom of the **Properties** window.</span></span>  
  
## <a name="setting-up-the-project-for-design-time-debugging"></a><span data-ttu-id="2a230-154">Configurar el proyecto para la depuración en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="2a230-154">Setting Up the Project for Design-Time Debugging</span></span>  
 <span data-ttu-id="2a230-155">Para depurar el comportamiento en tiempo de diseño del control personalizado, que desea depurar una instancia independiente de Visual Studio que está ejecutando código del control personalizado.</span><span class="sxs-lookup"><span data-stu-id="2a230-155">To debug your custom control's design-time behavior, you will debug a separate instance of Visual Studio that is running your custom control's code.</span></span>  
  
#### <a name="to-set-up-the-project-for-design-time-debugging"></a><span data-ttu-id="2a230-156">Para configurar el proyecto para la depuración en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="2a230-156">To set up the project for design-time debugging</span></span>  
  
1.  <span data-ttu-id="2a230-157">Haga doble clic en el **DebugControlLibrary** del proyecto en el **el Explorador de soluciones** y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2a230-157">Right-click on the **DebugControlLibrary** project in the **Solution Explorer** and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="2a230-158">En el **DebugControlLibrary** hoja de propiedades, seleccione la **depurar** ficha.</span><span class="sxs-lookup"><span data-stu-id="2a230-158">In the **DebugControlLibrary** property sheet, select the **Debug** tab.</span></span>  
  
     <span data-ttu-id="2a230-159">En el **acción de inicio** sección, seleccione **iniciar programa externo**.</span><span class="sxs-lookup"><span data-stu-id="2a230-159">In the **Start Action** section, select **Start external program**.</span></span> <span data-ttu-id="2a230-160">Estará depurando una instancia independiente de Visual Studio, haga clic en el botón de puntos suspensivos (![de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) botón para buscar el IDE de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2a230-160">You will be debugging a separate instance of Visual Studio, so click the ellipsis (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button to browse for the Visual Studio IDE.</span></span> <span data-ttu-id="2a230-161">El nombre del archivo ejecutable es **devenv.exe**, y si ha instalado en la ubicación predeterminada, su ruta de acceso es %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.</span><span class="sxs-lookup"><span data-stu-id="2a230-161">The name of the executable file is **devenv.exe**, and if you installed to the default location, its path is %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.</span></span>  
  
3.  <span data-ttu-id="2a230-162">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2a230-162">Click **OK** to close the dialog box.</span></span>  
  
4.  <span data-ttu-id="2a230-163">Haga clic en el **DebugControlLibrary** de proyecto y seleccione **establecer como proyecto de inicio** para habilitar esta configuración de depuración.</span><span class="sxs-lookup"><span data-stu-id="2a230-163">Right-click the **DebugControlLibrary** project and select **Set as StartUp Project** to enable this debugging configuration.</span></span>  
  
## <a name="debugging-your-custom-control-at-design-time"></a><span data-ttu-id="2a230-164">Depurar el Control personalizado en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="2a230-164">Debugging Your Custom Control at Design Time</span></span>  
 <span data-ttu-id="2a230-165">Ahora está listo para depurar el control personalizado mientras se ejecuta en modo de diseño.</span><span class="sxs-lookup"><span data-stu-id="2a230-165">Now you are ready to debug your custom control as it runs in design mode.</span></span> <span data-ttu-id="2a230-166">Cuando se inicia la sesión de depuración, se creará una nueva instancia de Visual Studio, y podrá utilizarla para cargar la solución "DebuggingExample".</span><span class="sxs-lookup"><span data-stu-id="2a230-166">When you start the debugging session, a new instance of Visual Studio will be created, and you will use it to load the "DebuggingExample" solution.</span></span> <span data-ttu-id="2a230-167">Cuando abra Form1 en el **Diseñador de formularios**, una instancia del control personalizado se crearán y empezará a ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="2a230-167">When you open Form1 in the **Forms Designer**, an instance of your custom control will be created and will start running.</span></span>  
  
#### <a name="to-debug-your-custom-control-at-design-time"></a><span data-ttu-id="2a230-168">Para depurar el control personalizado en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="2a230-168">To debug your custom control at design time</span></span>  
  
1.  <span data-ttu-id="2a230-169">Abra la **DebugControl** archivo de código fuente en el **Editor de código** y establecer un punto de interrupción en la `Set` descriptor de acceso de la `DemoString` propiedad.</span><span class="sxs-lookup"><span data-stu-id="2a230-169">Open the **DebugControl** source file in the **Code Editor** and place a breakpoint on the `Set` accessor of the `DemoString` property.</span></span>  
  
2.  <span data-ttu-id="2a230-170">Presione F5 para iniciar la sesión de depuración.</span><span class="sxs-lookup"><span data-stu-id="2a230-170">Press F5 to start the debugging session.</span></span> <span data-ttu-id="2a230-171">Tenga en cuenta que se crea una nueva instancia de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2a230-171">Note that a new instance of Visual Studio is created.</span></span> <span data-ttu-id="2a230-172">Puede distinguir entre las instancias de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="2a230-172">You can distinguish between the instances in two ways:</span></span>  
  
    -   <span data-ttu-id="2a230-173">La instancia de depuración tiene la palabra **ejecutando** en su barra de título</span><span class="sxs-lookup"><span data-stu-id="2a230-173">The debugging instance has the word **Running** in its title bar</span></span>  
  
    -   <span data-ttu-id="2a230-174">La instancia de depuración tiene la **iniciar** situado en su **depurar** deshabilitado de la barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="2a230-174">The debugging instance has the **Start** button on its **Debug** toolbar disabled</span></span>  
  
     <span data-ttu-id="2a230-175">El punto de interrupción se establece en la instancia de depuración.</span><span class="sxs-lookup"><span data-stu-id="2a230-175">Your breakpoint is set in the debugging instance.</span></span>  
  
3.  <span data-ttu-id="2a230-176">En la nueva instancia de Visual Studio, abra la solución "DebuggingExample".</span><span class="sxs-lookup"><span data-stu-id="2a230-176">In the new instance of Visual Studio, open the "DebuggingExample" solution.</span></span> <span data-ttu-id="2a230-177">Puede encontrar fácilmente la solución seleccionando **proyectos recientes** desde el **archivo** menú.</span><span class="sxs-lookup"><span data-stu-id="2a230-177">You can easily find the solution by selecting **Recent Projects** from the **File** menu.</span></span> <span data-ttu-id="2a230-178">El archivo de solución "DebuggingExample.sln" se mostrará como los archivos usados recientemente.</span><span class="sxs-lookup"><span data-stu-id="2a230-178">The "DebuggingExample.sln" solution file will be listed as the most recently used file.</span></span>  
  
4.  <span data-ttu-id="2a230-179">Abra Form1 en el **Diseñador de formularios** y seleccione la **DebugControl** control.</span><span class="sxs-lookup"><span data-stu-id="2a230-179">Open Form1 in the **Forms Designer** and select the **DebugControl** control.</span></span>  
  
5.  <span data-ttu-id="2a230-180">Cambie el valor de la `DemoString` propiedad.</span><span class="sxs-lookup"><span data-stu-id="2a230-180">Change the value of the `DemoString` property.</span></span> <span data-ttu-id="2a230-181">Tenga en cuenta que cuando se confirma el cambio, la instancia de depuración de Visual Studio adquiere el foco y la ejecución se detiene en el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="2a230-181">Note that when you commit the change, the debugging instance of Visual Studio acquires focus and execution stops at your breakpoint.</span></span> <span data-ttu-id="2a230-182">Puede paso a paso a través del descriptor de acceso de propiedad al igual que la haría cualquier otro código.</span><span class="sxs-lookup"><span data-stu-id="2a230-182">You can single-step through the property accessor just as your would any other code.</span></span>  
  
6.  <span data-ttu-id="2a230-183">Cuando haya terminado con la sesión de depuración, puede salir descartando la instancia de host de Visual Studio o haciendo clic en el **Detener depuración** botón en la instancia de depuración.</span><span class="sxs-lookup"><span data-stu-id="2a230-183">When you are finished with your debugging session, you can exit by dismissing the hosted instance of Visual Studio or by clicking the **Stop Debugging** button in the debugging instance.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="2a230-184">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="2a230-184">Next Steps</span></span>  
 <span data-ttu-id="2a230-185">Ahora que puede depurar los controles personalizados en tiempo de diseño, hay muchas posibilidades de ampliar la interacción del control con el IDE de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2a230-185">Now that you can debug your custom controls at design time, there are many possibilities for expanding your control's interaction with the Visual Studio IDE.</span></span>  
  
-   <span data-ttu-id="2a230-186">Puede usar el <xref:System.ComponentModel.Component.DesignMode%2A> propiedad de la <xref:System.ComponentModel.Component> clase para escribir código que solo se ejecutará en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="2a230-186">You can use the <xref:System.ComponentModel.Component.DesignMode%2A> property of the <xref:System.ComponentModel.Component> class to write code that will only execute at design time.</span></span> <span data-ttu-id="2a230-187">Para obtener información detallada, vea <xref:System.ComponentModel.Component.DesignMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="2a230-187">For details, see <xref:System.ComponentModel.Component.DesignMode%2A>.</span></span>  
  
-   <span data-ttu-id="2a230-188">Hay varios atributos puede aplicar a las propiedades del control para manipular la interacción del control personalizado con el diseñador.</span><span class="sxs-lookup"><span data-stu-id="2a230-188">There are several attributes you can apply to your control's properties to manipulate your custom control's interaction with the designer.</span></span> <span data-ttu-id="2a230-189">Puede encontrar estos atributos en el <xref:System.ComponentModel?displayProperty=nameWithType> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="2a230-189">You can find these attributes in the <xref:System.ComponentModel?displayProperty=nameWithType> namespace.</span></span>  
  
-   <span data-ttu-id="2a230-190">Puede escribir un diseñador personalizado para el control personalizado.</span><span class="sxs-lookup"><span data-stu-id="2a230-190">You can write a custom designer for your custom control.</span></span> <span data-ttu-id="2a230-191">Esto proporciona un control completo sobre la experiencia de diseño mediante la infraestructura del diseñador extensible expuesta por Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2a230-191">This gives you complete control over the design experience using the extensible designer infrastructure exposed by Visual Studio.</span></span> <span data-ttu-id="2a230-192">Para obtener más información, consulte [Tutorial: crear un Windows Forms Control que toma ventaja de tiempo de diseño características de Visual Studio](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).</span><span class="sxs-lookup"><span data-stu-id="2a230-192">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a230-193">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a230-193">See Also</span></span>  
 [<span data-ttu-id="2a230-194">Tutorial: Crear un control de Windows Forms que aproveche las características en tiempo de diseño de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2a230-194">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
 [<span data-ttu-id="2a230-195">Cómo: obtener acceso a servicios en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="2a230-195">How to: Access Design-Time Services</span></span>](http://msdn.microsoft.com/library/c186c4b6-076c-438d-9ed3-f13da29c8c1f)  
 [<span data-ttu-id="2a230-196">Cómo: obtener acceso a la compatibilidad en tiempo de diseño en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2a230-196">How to: Access Design-Time Support in Windows Forms</span></span>](http://msdn.microsoft.com/library/a84f8579-1f47-41b9-ba37-69030b0aff09)
