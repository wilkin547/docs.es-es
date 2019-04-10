---
title: 'Tutorial: Depurar controles personalizados de formularios Windows Forms en tiempo de diseño'
ms.date: 03/30/2017
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
ms.openlocfilehash: db6266f30c4fb62364f3c40a75a4a11ef853c1cb
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59325363"
---
# <a name="walkthrough-debugging-custom-windows-forms-controls-at-design-time"></a><span data-ttu-id="66320-102">Tutorial: Depurar controles personalizados de formularios Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="66320-102">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>
<span data-ttu-id="66320-103">Cuando se crea un control personalizado, a menudo encontrará lo necesario para depurar su comportamiento en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="66320-103">When you create a custom control, you will often find it necessary to debug its design-time behavior.</span></span> <span data-ttu-id="66320-104">Esto es especialmente cierto si va a crear un diseñador personalizado para el control personalizado.</span><span class="sxs-lookup"><span data-stu-id="66320-104">This is especially true if you are authoring a custom designer for your custom control.</span></span> <span data-ttu-id="66320-105">Para obtener más información, consulte [Tutorial: Crear un Windows Forms Control que aprovecha las características de tiempo de diseño de Visual Studio](creating-a-wf-control-design-time-features.md).</span><span class="sxs-lookup"><span data-stu-id="66320-105">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md).</span></span>  
  
 <span data-ttu-id="66320-106">Puede depurar sus controles personalizados mediante Visual Studio, simplemente como lo haría cualquier otras clases de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="66320-106">You can debug your custom controls using Visual Studio, just as you would debug any other .NET Framework classes.</span></span> <span data-ttu-id="66320-107">La diferencia es que desea depurar una instancia independiente de Visual Studio que se está ejecutando código del control personalizado</span><span class="sxs-lookup"><span data-stu-id="66320-107">The difference is that you will debug a separate instance of Visual Studio that is running your custom control's code</span></span>  
  
 <span data-ttu-id="66320-108">Las tareas ilustradas en este tutorial incluyen:</span><span class="sxs-lookup"><span data-stu-id="66320-108">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="66320-109">Crear un proyecto de Windows Forms para hospedar el control personalizado</span><span class="sxs-lookup"><span data-stu-id="66320-109">Creating a Windows Forms project to host your custom control</span></span>  
  
-   <span data-ttu-id="66320-110">Crear un proyecto de biblioteca de controles</span><span class="sxs-lookup"><span data-stu-id="66320-110">Creating a control library project</span></span>  
  
-   <span data-ttu-id="66320-111">Agregar una propiedad al control personalizado</span><span class="sxs-lookup"><span data-stu-id="66320-111">Adding a property to your custom control</span></span>  
  
-   <span data-ttu-id="66320-112">Agregar el control personalizado al formulario de host</span><span class="sxs-lookup"><span data-stu-id="66320-112">Adding your custom control to the host form</span></span>  
  
-   <span data-ttu-id="66320-113">Configurar el proyecto para la depuración de tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="66320-113">Setting up the project for design-time debugging</span></span>  
  
-   <span data-ttu-id="66320-114">Depurar el control personalizado en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="66320-114">Debugging your custom control at design time</span></span>  
  
 <span data-ttu-id="66320-115">Cuando haya terminado, tendrá una comprensión de las tareas necesarias para depurar el comportamiento en tiempo de diseño de un control personalizado.</span><span class="sxs-lookup"><span data-stu-id="66320-115">When you are finished, you will have an understanding of the tasks necessary for debugging the design-time behavior of a custom control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="66320-116">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="66320-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="66320-117">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="66320-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="66320-118">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="66320-118">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="66320-119">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="66320-119">Creating the Project</span></span>  
 <span data-ttu-id="66320-120">El primer paso es crear el proyecto de aplicación.</span><span class="sxs-lookup"><span data-stu-id="66320-120">The first step is to create the application project.</span></span> <span data-ttu-id="66320-121">Este proyecto se utilizará para compilar la aplicación que hospeda el control personalizado.</span><span class="sxs-lookup"><span data-stu-id="66320-121">You will use this project to build the application that hosts the custom control.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="66320-122">Para crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="66320-122">To create the project</span></span>  
  
-   <span data-ttu-id="66320-123">Cree un proyecto de aplicación de Windows denominado "DebuggingExample" (**archivo** > **New** > **proyecto**  >  **Visual C#** o **Visual Basic** > **escritorio clásico de** > **aplicación de Windows Forms**).</span><span class="sxs-lookup"><span data-stu-id="66320-123">Create a Windows Application project called "DebuggingExample" (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
## <a name="creating-a-control-library-project"></a><span data-ttu-id="66320-124">Crear un proyecto de biblioteca de controles</span><span class="sxs-lookup"><span data-stu-id="66320-124">Creating a Control Library Project</span></span>  
 <span data-ttu-id="66320-125">El siguiente paso es crear el proyecto de biblioteca de controles y configurar el control personalizado.</span><span class="sxs-lookup"><span data-stu-id="66320-125">The next step is to create the control library project and set up the custom control.</span></span>  
  
#### <a name="to-create-the-control-library-project"></a><span data-ttu-id="66320-126">Para crear el proyecto de biblioteca de control</span><span class="sxs-lookup"><span data-stu-id="66320-126">To create the control library project</span></span>  
  
1. <span data-ttu-id="66320-127">Agregar un **biblioteca de controles de Windows** proyecto a la solución.</span><span class="sxs-lookup"><span data-stu-id="66320-127">Add a **Windows Control Library** project to the solution.</span></span>  
  
2. <span data-ttu-id="66320-128">Agregue un nuevo **UserControl** al proyecto DebugControlLibrary.</span><span class="sxs-lookup"><span data-stu-id="66320-128">Add a new **UserControl** item to the DebugControlLibrary project.</span></span> <span data-ttu-id="66320-129">Para obtener más detalles, vea [Cómo: Agregar nuevos elementos de proyecto](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="66320-129">For details, see [How to: Add New Project Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span></span> <span data-ttu-id="66320-130">Asigne el nuevo archivo de origen en un nombre de base de "DebugControl".</span><span class="sxs-lookup"><span data-stu-id="66320-130">Give the new source file a base name of "DebugControl".</span></span>  
  
3. <span data-ttu-id="66320-131">Mediante el **el Explorador de soluciones**, elimine el control predeterminado del proyecto eliminando el archivo de código con el nombre de base "`UserControl1`".</span><span class="sxs-lookup"><span data-stu-id="66320-131">Using the **Solution Explorer**, delete the project's default control by deleting the code file with a base name of "`UserControl1`".</span></span> <span data-ttu-id="66320-132">Para obtener más detalles, vea [Cómo: Quitar, eliminar y excluir elementos](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="66320-132">For details, see [How to: Remove, Delete, and Exclude Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span></span>  
  
4. <span data-ttu-id="66320-133">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="66320-133">Build the solution.</span></span>  
  
## <a name="checkpoint"></a><span data-ttu-id="66320-134">Punto de control</span><span class="sxs-lookup"><span data-stu-id="66320-134">Checkpoint</span></span>  
 <span data-ttu-id="66320-135">En este momento, podrá ver el control personalizado en el **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="66320-135">At this point, you will be able to see your custom control in the **Toolbox**.</span></span>  
  
#### <a name="to-check-your-progress"></a><span data-ttu-id="66320-136">Para comprobar su progreso</span><span class="sxs-lookup"><span data-stu-id="66320-136">To check your progress</span></span>  
  
-   <span data-ttu-id="66320-137">Busque la nueva pestaña denominada **DebugControlLibrary componentes** y haga clic para seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="66320-137">Find the new tab called **DebugControlLibrary Components** and click to select it.</span></span> <span data-ttu-id="66320-138">Cuando se abre, verá el control aparece como **DebugControl** con el icono predeterminado junto a él.</span><span class="sxs-lookup"><span data-stu-id="66320-138">When it opens, you will see your control listed as **DebugControl** with the default icon beside it.</span></span>  
  
## <a name="adding-a-property-to-your-custom-control"></a><span data-ttu-id="66320-139">Agregar una propiedad al Control personalizado</span><span class="sxs-lookup"><span data-stu-id="66320-139">Adding a Property to Your Custom Control</span></span>  
 <span data-ttu-id="66320-140">Para demostrar que se está ejecutando código del control personalizado en tiempo de diseño, agregará una propiedad y establecer un punto de interrupción en el código que implementa la propiedad.</span><span class="sxs-lookup"><span data-stu-id="66320-140">To demonstrate that your custom control's code is running at design-time, you will add a property and set a breakpoint in the code that implements the property.</span></span>  
  
#### <a name="to-add-a-property-to-your-custom-control"></a><span data-ttu-id="66320-141">Para agregar una propiedad al control personalizado</span><span class="sxs-lookup"><span data-stu-id="66320-141">To add a property to your custom control</span></span>  
  
1. <span data-ttu-id="66320-142">Abra **DebugControl** en el **Editor de código**.</span><span class="sxs-lookup"><span data-stu-id="66320-142">Open **DebugControl** in the **Code Editor**.</span></span> <span data-ttu-id="66320-143">Agregue el código siguiente a la definición de clase:</span><span class="sxs-lookup"><span data-stu-id="66320-143">Add the following code to the class definition:</span></span>  
  
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
  
2. <span data-ttu-id="66320-144">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="66320-144">Build the solution.</span></span>  
  
## <a name="adding-your-custom-control-to-the-host-form"></a><span data-ttu-id="66320-145">Agregar el Control personalizado al formulario de Host</span><span class="sxs-lookup"><span data-stu-id="66320-145">Adding Your Custom Control to the Host Form</span></span>  
 <span data-ttu-id="66320-146">Para depurar el comportamiento en tiempo de diseño del control personalizado, colocará una instancia de la clase de control personalizado en un formulario de host.</span><span class="sxs-lookup"><span data-stu-id="66320-146">To debug the design-time behavior of your custom control, you will place an instance of the custom control class on a host form.</span></span>  
  
#### <a name="to-add-your-custom-control-to-the-host-form"></a><span data-ttu-id="66320-147">Para agregar el control personalizado a la forma de host</span><span class="sxs-lookup"><span data-stu-id="66320-147">To add your custom control to the host form</span></span>  
  
1. <span data-ttu-id="66320-148">En el proyecto "DebuggingExample", abra Form1 en el **Diseñador de Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="66320-148">In the "DebuggingExample" project, open Form1 in the **Windows Forms Designer**.</span></span>  
  
2. <span data-ttu-id="66320-149">En el **cuadro de herramientas**, abra el **DebugControlLibrary componentes** pestaña y arrastre un **DebugControl** instancia hasta el formulario.</span><span class="sxs-lookup"><span data-stu-id="66320-149">In the **Toolbox**, open the **DebugControlLibrary Components** tab and drag a **DebugControl** instance onto the form.</span></span>  
  
3. <span data-ttu-id="66320-150">Buscar el `DemoString` propiedad personalizada en el **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="66320-150">Find the `DemoString` custom property in the **Properties** window.</span></span> <span data-ttu-id="66320-151">Tenga en cuenta que puede cambiar su valor como lo haría con cualquier otra propiedad.</span><span class="sxs-lookup"><span data-stu-id="66320-151">Note that you can change its value as you would any other property.</span></span> <span data-ttu-id="66320-152">Tenga en cuenta también que, cuando el `DemoString` propiedad está seleccionada, la cadena de descripción de la propiedad aparece en la parte inferior de la **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="66320-152">Also note that when the `DemoString` property is selected, the property's description string appears at the bottom of the **Properties** window.</span></span>  
  
## <a name="setting-up-the-project-for-design-time-debugging"></a><span data-ttu-id="66320-153">Configurar el proyecto para la depuración de tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="66320-153">Setting Up the Project for Design-Time Debugging</span></span>  
 <span data-ttu-id="66320-154">Para depurar el comportamiento en tiempo de diseño del control personalizado, que desea depurar una instancia independiente de Visual Studio que se está ejecutando código del control personalizado.</span><span class="sxs-lookup"><span data-stu-id="66320-154">To debug your custom control's design-time behavior, you will debug a separate instance of Visual Studio that is running your custom control's code.</span></span>  
  
#### <a name="to-set-up-the-project-for-design-time-debugging"></a><span data-ttu-id="66320-155">Para configurar el proyecto para la depuración de tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="66320-155">To set up the project for design-time debugging</span></span>  
  
1. <span data-ttu-id="66320-156">Haga doble clic en el **DebugControlLibrary** del proyecto en el **el Explorador de soluciones** y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="66320-156">Right-click on the **DebugControlLibrary** project in the **Solution Explorer** and select **Properties**.</span></span>  
  
2. <span data-ttu-id="66320-157">En el **DebugControlLibrary** hoja de propiedades, seleccione la **depurar** ficha.</span><span class="sxs-lookup"><span data-stu-id="66320-157">In the **DebugControlLibrary** property sheet, select the **Debug** tab.</span></span>  
  
     <span data-ttu-id="66320-158">En el **acción de inicio** sección, seleccione **iniciar programa externo**.</span><span class="sxs-lookup"><span data-stu-id="66320-158">In the **Start Action** section, select **Start external program**.</span></span> <span data-ttu-id="66320-159">Puede depurar una instancia independiente de Visual Studio, haga clic en el botón de puntos suspensivos (![de pantalla de VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) botón para buscar el IDE de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="66320-159">You will be debugging a separate instance of Visual Studio, so click the ellipsis (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) button to browse for the Visual Studio IDE.</span></span> <span data-ttu-id="66320-160">El nombre del archivo ejecutable es **devenv.exe**, y si ha instalado en la ubicación predeterminada, su ruta de acceso es %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.</span><span class="sxs-lookup"><span data-stu-id="66320-160">The name of the executable file is **devenv.exe**, and if you installed to the default location, its path is %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.</span></span>  
  
3. <span data-ttu-id="66320-161">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="66320-161">Click **OK** to close the dialog box.</span></span>  
  
4. <span data-ttu-id="66320-162">Haga clic en el **DebugControlLibrary** del proyecto y seleccione **establecer como proyecto de inicio** para habilitar esta configuración de depuración.</span><span class="sxs-lookup"><span data-stu-id="66320-162">Right-click the **DebugControlLibrary** project and select **Set as StartUp Project** to enable this debugging configuration.</span></span>  
  
## <a name="debugging-your-custom-control-at-design-time"></a><span data-ttu-id="66320-163">Depurar el Control personalizado en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="66320-163">Debugging Your Custom Control at Design Time</span></span>  
 <span data-ttu-id="66320-164">Ahora está listo para depurar el control personalizado mientras se ejecuta en modo de diseño.</span><span class="sxs-lookup"><span data-stu-id="66320-164">Now you are ready to debug your custom control as it runs in design mode.</span></span> <span data-ttu-id="66320-165">Al iniciar la sesión de depuración, se creará una nueva instancia de Visual Studio y se usará para cargar la solución "DebuggingExample".</span><span class="sxs-lookup"><span data-stu-id="66320-165">When you start the debugging session, a new instance of Visual Studio will be created, and you will use it to load the "DebuggingExample" solution.</span></span> <span data-ttu-id="66320-166">Cuando se abre Form1 en el **Diseñador de formularios**, una instancia del control personalizado se crea y se volverá a ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="66320-166">When you open Form1 in the **Forms Designer**, an instance of your custom control will be created and will start running.</span></span>  
  
#### <a name="to-debug-your-custom-control-at-design-time"></a><span data-ttu-id="66320-167">Para depurar el control personalizado en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="66320-167">To debug your custom control at design time</span></span>  
  
1. <span data-ttu-id="66320-168">Abra el **DebugControl** archivo de código fuente en el **Editor de código** y coloque un punto de interrupción en el `Set` descriptor de acceso de la `DemoString` propiedad.</span><span class="sxs-lookup"><span data-stu-id="66320-168">Open the **DebugControl** source file in the **Code Editor** and place a breakpoint on the `Set` accessor of the `DemoString` property.</span></span>  
  
2. <span data-ttu-id="66320-169">Presione F5 para iniciar la sesión de depuración.</span><span class="sxs-lookup"><span data-stu-id="66320-169">Press F5 to start the debugging session.</span></span> <span data-ttu-id="66320-170">Tenga en cuenta que se crea una nueva instancia de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="66320-170">Note that a new instance of Visual Studio is created.</span></span> <span data-ttu-id="66320-171">Puede distinguir entre las instancias de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="66320-171">You can distinguish between the instances in two ways:</span></span>  
  
    -   <span data-ttu-id="66320-172">La instancia de depuración con la palabra **ejecutando** en su barra de título</span><span class="sxs-lookup"><span data-stu-id="66320-172">The debugging instance has the word **Running** in its title bar</span></span>  
  
    -   <span data-ttu-id="66320-173">La instancia de depuración tiene el **iniciar** situado en su **depurar** deshabilitado de la barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="66320-173">The debugging instance has the **Start** button on its **Debug** toolbar disabled</span></span>  
  
     <span data-ttu-id="66320-174">El punto de interrupción se establece en la instancia de depuración.</span><span class="sxs-lookup"><span data-stu-id="66320-174">Your breakpoint is set in the debugging instance.</span></span>  
  
3. <span data-ttu-id="66320-175">En la nueva instancia de Visual Studio, abra la solución "DebuggingExample".</span><span class="sxs-lookup"><span data-stu-id="66320-175">In the new instance of Visual Studio, open the "DebuggingExample" solution.</span></span> <span data-ttu-id="66320-176">Puede encontrar fácilmente la solución seleccionando **proyectos recientes** desde el **archivo** menú.</span><span class="sxs-lookup"><span data-stu-id="66320-176">You can easily find the solution by selecting **Recent Projects** from the **File** menu.</span></span> <span data-ttu-id="66320-177">El archivo de solución "DebuggingExample.sln" se mostrará como los archivos usados recientemente.</span><span class="sxs-lookup"><span data-stu-id="66320-177">The "DebuggingExample.sln" solution file will be listed as the most recently used file.</span></span>  
  
4. <span data-ttu-id="66320-178">Abra Form1 en el **Diseñador de formularios** y seleccione el **DebugControl** control.</span><span class="sxs-lookup"><span data-stu-id="66320-178">Open Form1 in the **Forms Designer** and select the **DebugControl** control.</span></span>  
  
5. <span data-ttu-id="66320-179">Cambie el valor de la propiedad `DemoString` .</span><span class="sxs-lookup"><span data-stu-id="66320-179">Change the value of the `DemoString` property.</span></span> <span data-ttu-id="66320-180">Tenga en cuenta que cuando se confirma el cambio, la instancia de depuración de Visual Studio adquiere el foco y la ejecución se detiene en el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="66320-180">Note that when you commit the change, the debugging instance of Visual Studio acquires focus and execution stops at your breakpoint.</span></span> <span data-ttu-id="66320-181">Puede paso a paso a través del descriptor de acceso de propiedad al igual que su cualquier otro código.</span><span class="sxs-lookup"><span data-stu-id="66320-181">You can single-step through the property accessor just as your would any other code.</span></span>  
  
6. <span data-ttu-id="66320-182">Cuando haya terminado con la sesión de depuración, puede salir descartando la instancia hospedada de Visual Studio o haciendo clic en el **Detener depuración** botón en la instancia de depuración.</span><span class="sxs-lookup"><span data-stu-id="66320-182">When you are finished with your debugging session, you can exit by dismissing the hosted instance of Visual Studio or by clicking the **Stop Debugging** button in the debugging instance.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="66320-183">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="66320-183">Next Steps</span></span>  
 <span data-ttu-id="66320-184">Ahora que puede depurar controles personalizados en tiempo de diseño, hay muchas posibilidades para expandir la interacción del control con el IDE de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="66320-184">Now that you can debug your custom controls at design time, there are many possibilities for expanding your control's interaction with the Visual Studio IDE.</span></span>  
  
-   <span data-ttu-id="66320-185">Puede usar el <xref:System.ComponentModel.Component.DesignMode%2A> propiedad de la <xref:System.ComponentModel.Component> clase para escribir código que solo se ejecutará en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="66320-185">You can use the <xref:System.ComponentModel.Component.DesignMode%2A> property of the <xref:System.ComponentModel.Component> class to write code that will only execute at design time.</span></span> <span data-ttu-id="66320-186">Para obtener información detallada, vea <xref:System.ComponentModel.Component.DesignMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="66320-186">For details, see <xref:System.ComponentModel.Component.DesignMode%2A>.</span></span>  
  
-   <span data-ttu-id="66320-187">Hay varios atributos puede aplicar a las propiedades del control para manipular la interacción del control personalizado con el diseñador.</span><span class="sxs-lookup"><span data-stu-id="66320-187">There are several attributes you can apply to your control's properties to manipulate your custom control's interaction with the designer.</span></span> <span data-ttu-id="66320-188">Puede encontrar estos atributos en el <xref:System.ComponentModel?displayProperty=nameWithType> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="66320-188">You can find these attributes in the <xref:System.ComponentModel?displayProperty=nameWithType> namespace.</span></span>  
  
-   <span data-ttu-id="66320-189">Puede escribir un diseñador personalizado para el control personalizado.</span><span class="sxs-lookup"><span data-stu-id="66320-189">You can write a custom designer for your custom control.</span></span> <span data-ttu-id="66320-190">Esto le ofrece control completo sobre la experiencia de diseño mediante la infraestructura del diseñador extensible expuesta por Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="66320-190">This gives you complete control over the design experience using the extensible designer infrastructure exposed by Visual Studio.</span></span> <span data-ttu-id="66320-191">Para obtener más información, consulte [Tutorial: Crear un Windows Forms Control que aprovecha las características de tiempo de diseño de Visual Studio](creating-a-wf-control-design-time-features.md).</span><span class="sxs-lookup"><span data-stu-id="66320-191">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66320-192">Vea también</span><span class="sxs-lookup"><span data-stu-id="66320-192">See also</span></span>

- [<span data-ttu-id="66320-193">Tutorial: Crear un control de formularios Windows Forms que aproveche las características en tiempo de diseño de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="66320-193">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)
- [<span data-ttu-id="66320-194">Filtrar Acceso a servicios en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="66320-194">How to: Access Design-Time Services</span></span>](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171822(v=vs.120))
- [<span data-ttu-id="66320-195">Filtrar Compatibilidad de tiempo de diseño de acceso en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="66320-195">How to: Access Design-Time Support in Windows Forms</span></span>](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171827(v=vs.120))
