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
ms.openlocfilehash: 39adcbd6d915f8b086df7e425efbe08ae8680a45
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2019
ms.locfileid: "65882462"
---
# <a name="walkthrough-debugging-custom-windows-forms-controls-at-design-time"></a><span data-ttu-id="38eb8-102">Tutorial: Depurar controles personalizados de formularios Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="38eb8-102">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>

<span data-ttu-id="38eb8-103">Cuando se crea un control personalizado, a menudo encontrará lo necesario para depurar su comportamiento en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="38eb8-103">When you create a custom control, you will often find it necessary to debug its design-time behavior.</span></span> <span data-ttu-id="38eb8-104">Esto es especialmente cierto si va a crear un diseñador personalizado para el control personalizado.</span><span class="sxs-lookup"><span data-stu-id="38eb8-104">This is especially true if you are authoring a custom designer for your custom control.</span></span> <span data-ttu-id="38eb8-105">Para obtener más información, consulte [Tutorial: Crear un Windows Forms Control que aprovecha las características de tiempo de diseño de Visual Studio](creating-a-wf-control-design-time-features.md).</span><span class="sxs-lookup"><span data-stu-id="38eb8-105">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md).</span></span>

<span data-ttu-id="38eb8-106">Puede depurar sus controles personalizados mediante Visual Studio, simplemente como lo haría cualquier otras clases de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="38eb8-106">You can debug your custom controls using Visual Studio, just as you would debug any other .NET Framework classes.</span></span> <span data-ttu-id="38eb8-107">La diferencia es que desea depurar una instancia independiente de Visual Studio que se está ejecutando código del control personalizado</span><span class="sxs-lookup"><span data-stu-id="38eb8-107">The difference is that you will debug a separate instance of Visual Studio that is running your custom control's code</span></span>

<span data-ttu-id="38eb8-108">Las tareas ilustradas en este tutorial incluyen:</span><span class="sxs-lookup"><span data-stu-id="38eb8-108">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="38eb8-109">Crear un proyecto de Windows Forms para hospedar el control personalizado</span><span class="sxs-lookup"><span data-stu-id="38eb8-109">Creating a Windows Forms project to host your custom control</span></span>

- <span data-ttu-id="38eb8-110">Crear un proyecto de biblioteca de controles</span><span class="sxs-lookup"><span data-stu-id="38eb8-110">Creating a control library project</span></span>

- <span data-ttu-id="38eb8-111">Agregar una propiedad al control personalizado</span><span class="sxs-lookup"><span data-stu-id="38eb8-111">Adding a property to your custom control</span></span>

- <span data-ttu-id="38eb8-112">Agregar el control personalizado al formulario de host</span><span class="sxs-lookup"><span data-stu-id="38eb8-112">Adding your custom control to the host form</span></span>

- <span data-ttu-id="38eb8-113">Configurar el proyecto para la depuración de tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="38eb8-113">Setting up the project for design-time debugging</span></span>

- <span data-ttu-id="38eb8-114">Depurar el control personalizado en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="38eb8-114">Debugging your custom control at design time</span></span>

<span data-ttu-id="38eb8-115">Cuando haya terminado, tendrá una comprensión de las tareas necesarias para depurar el comportamiento en tiempo de diseño de un control personalizado.</span><span class="sxs-lookup"><span data-stu-id="38eb8-115">When you are finished, you will have an understanding of the tasks necessary for debugging the design-time behavior of a custom control.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="38eb8-116">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="38eb8-116">Create the project</span></span>

<span data-ttu-id="38eb8-117">El primer paso es crear el proyecto de aplicación.</span><span class="sxs-lookup"><span data-stu-id="38eb8-117">The first step is to create the application project.</span></span> <span data-ttu-id="38eb8-118">Este proyecto se utilizará para compilar la aplicación que hospeda el control personalizado.</span><span class="sxs-lookup"><span data-stu-id="38eb8-118">You will use this project to build the application that hosts the custom control.</span></span>

<span data-ttu-id="38eb8-119">En Visual Studio, cree un proyecto de aplicación de Windows denominado "DebuggingExample" (**archivo** > **New** > **proyecto**  >  **Visual C#**  o **Visual Basic** > **escritorio clásico de** > **deaplicacióndeformulariosdeWindows**).</span><span class="sxs-lookup"><span data-stu-id="38eb8-119">In Visual Studio, create a Windows Application project called "DebuggingExample" (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

## <a name="create-the-control-library-project"></a><span data-ttu-id="38eb8-120">Crear el proyecto de biblioteca de controles</span><span class="sxs-lookup"><span data-stu-id="38eb8-120">Create the control library project</span></span>

1. <span data-ttu-id="38eb8-121">Agregar un **biblioteca de controles de Windows** proyecto a la solución.</span><span class="sxs-lookup"><span data-stu-id="38eb8-121">Add a **Windows Control Library** project to the solution.</span></span>

2. <span data-ttu-id="38eb8-122">Agregue un nuevo **UserControl** al proyecto DebugControlLibrary.</span><span class="sxs-lookup"><span data-stu-id="38eb8-122">Add a new **UserControl** item to the DebugControlLibrary project.</span></span> <span data-ttu-id="38eb8-123">Para obtener más detalles, vea [Cómo: Agregar nuevos elementos de proyecto](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="38eb8-123">For details, see [How to: Add New Project Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span></span> <span data-ttu-id="38eb8-124">Asigne el nuevo archivo de origen en un nombre de base de "DebugControl".</span><span class="sxs-lookup"><span data-stu-id="38eb8-124">Give the new source file a base name of "DebugControl".</span></span>

3. <span data-ttu-id="38eb8-125">Mediante el **el Explorador de soluciones**, elimine el control predeterminado del proyecto eliminando el archivo de código con el nombre de base "`UserControl1`".</span><span class="sxs-lookup"><span data-stu-id="38eb8-125">Using the **Solution Explorer**, delete the project's default control by deleting the code file with a base name of "`UserControl1`".</span></span> <span data-ttu-id="38eb8-126">Para obtener más detalles, vea [Cómo: Quitar, eliminar y excluir elementos](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="38eb8-126">For details, see [How to: Remove, Delete, and Exclude Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span></span>

4. <span data-ttu-id="38eb8-127">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="38eb8-127">Build the solution.</span></span>

## <a name="checkpoint"></a><span data-ttu-id="38eb8-128">Punto de control</span><span class="sxs-lookup"><span data-stu-id="38eb8-128">Checkpoint</span></span>

<span data-ttu-id="38eb8-129">En este momento, podrá ver el control personalizado en el **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="38eb8-129">At this point, you will be able to see your custom control in the **Toolbox**.</span></span>

<span data-ttu-id="38eb8-130">Para comprobar el progreso, busque la nueva ficha denominada **DebugControlLibrary componentes** y haga clic para seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="38eb8-130">To check your progress, find the new tab called **DebugControlLibrary Components** and click to select it.</span></span> <span data-ttu-id="38eb8-131">Cuando se abre, verá el control aparece como **DebugControl** con el icono predeterminado junto a él.</span><span class="sxs-lookup"><span data-stu-id="38eb8-131">When it opens, you will see your control listed as **DebugControl** with the default icon beside it.</span></span>

## <a name="add-a-property-to-your-custom-control"></a><span data-ttu-id="38eb8-132">Agregar una propiedad al control personalizado</span><span class="sxs-lookup"><span data-stu-id="38eb8-132">Add a property to your custom control</span></span>

<span data-ttu-id="38eb8-133">Para demostrar que se está ejecutando código del control personalizado en tiempo de diseño, agregará una propiedad y establecer un punto de interrupción en el código que implementa la propiedad.</span><span class="sxs-lookup"><span data-stu-id="38eb8-133">To demonstrate that your custom control's code is running at design-time, you will add a property and set a breakpoint in the code that implements the property.</span></span>

1. <span data-ttu-id="38eb8-134">Abra **DebugControl** en el **Editor de código**.</span><span class="sxs-lookup"><span data-stu-id="38eb8-134">Open **DebugControl** in the **Code Editor**.</span></span> <span data-ttu-id="38eb8-135">Agregue el código siguiente a la definición de clase:</span><span class="sxs-lookup"><span data-stu-id="38eb8-135">Add the following code to the class definition:</span></span>

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

2. <span data-ttu-id="38eb8-136">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="38eb8-136">Build the solution.</span></span>

## <a name="add-your-custom-control-to-the-host-form"></a><span data-ttu-id="38eb8-137">Agregar el control personalizado al formulario de host</span><span class="sxs-lookup"><span data-stu-id="38eb8-137">Add your custom control to the host form</span></span>

<span data-ttu-id="38eb8-138">Para depurar el comportamiento en tiempo de diseño del control personalizado, colocará una instancia de la clase de control personalizado en un formulario de host.</span><span class="sxs-lookup"><span data-stu-id="38eb8-138">To debug the design-time behavior of your custom control, you will place an instance of the custom control class on a host form.</span></span>

1. <span data-ttu-id="38eb8-139">En el proyecto "DebuggingExample", abra Form1 en el **Diseñador de Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="38eb8-139">In the "DebuggingExample" project, open Form1 in the **Windows Forms Designer**.</span></span>

2. <span data-ttu-id="38eb8-140">En el **cuadro de herramientas**, abra el **DebugControlLibrary componentes** pestaña y arrastre un **DebugControl** instancia hasta el formulario.</span><span class="sxs-lookup"><span data-stu-id="38eb8-140">In the **Toolbox**, open the **DebugControlLibrary Components** tab and drag a **DebugControl** instance onto the form.</span></span>

3. <span data-ttu-id="38eb8-141">Buscar el `DemoString` propiedad personalizada en el **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="38eb8-141">Find the `DemoString` custom property in the **Properties** window.</span></span> <span data-ttu-id="38eb8-142">Tenga en cuenta que puede cambiar su valor como lo haría con cualquier otra propiedad.</span><span class="sxs-lookup"><span data-stu-id="38eb8-142">Note that you can change its value as you would any other property.</span></span> <span data-ttu-id="38eb8-143">Tenga en cuenta también que, cuando el `DemoString` propiedad está seleccionada, la cadena de descripción de la propiedad aparece en la parte inferior de la **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="38eb8-143">Also note that when the `DemoString` property is selected, the property's description string appears at the bottom of the **Properties** window.</span></span>

## <a name="set-up-the-project-for-design-time-debugging"></a><span data-ttu-id="38eb8-144">Configurar el proyecto para la depuración de tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="38eb8-144">Set up the project for design-time debugging</span></span>

<span data-ttu-id="38eb8-145">Para depurar el comportamiento en tiempo de diseño del control personalizado, que desea depurar una instancia independiente de Visual Studio que se está ejecutando código del control personalizado.</span><span class="sxs-lookup"><span data-stu-id="38eb8-145">To debug your custom control's design-time behavior, you will debug a separate instance of Visual Studio that is running your custom control's code.</span></span>

1. <span data-ttu-id="38eb8-146">Haga doble clic en el **DebugControlLibrary** del proyecto en el **el Explorador de soluciones** y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="38eb8-146">Right-click on the **DebugControlLibrary** project in the **Solution Explorer** and select **Properties**.</span></span>

2. <span data-ttu-id="38eb8-147">En el **DebugControlLibrary** hoja de propiedades, seleccione la **depurar** ficha.</span><span class="sxs-lookup"><span data-stu-id="38eb8-147">In the **DebugControlLibrary** property sheet, select the **Debug** tab.</span></span>

     <span data-ttu-id="38eb8-148">En el **acción de inicio** sección, seleccione **iniciar programa externo**.</span><span class="sxs-lookup"><span data-stu-id="38eb8-148">In the **Start Action** section, select **Start external program**.</span></span> <span data-ttu-id="38eb8-149">Puede depurar una instancia independiente de Visual Studio, haga clic en el botón de puntos suspensivos (![los puntos suspensivos (...) en la ventana Propiedades de Visual Studio.](./media/visual-studio-ellipsis-button.png)) botón para buscar el IDE de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="38eb8-149">You will be debugging a separate instance of Visual Studio, so click the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button to browse for the Visual Studio IDE.</span></span> <span data-ttu-id="38eb8-150">El nombre del archivo ejecutable es **devenv.exe**, y si ha instalado en la ubicación predeterminada, su ruta de acceso es %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.</span><span class="sxs-lookup"><span data-stu-id="38eb8-150">The name of the executable file is **devenv.exe**, and if you installed to the default location, its path is %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.</span></span>

3. <span data-ttu-id="38eb8-151">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="38eb8-151">Click **OK** to close the dialog box.</span></span>

4. <span data-ttu-id="38eb8-152">Haga clic en el **DebugControlLibrary** del proyecto y seleccione **establecer como proyecto de inicio** para habilitar esta configuración de depuración.</span><span class="sxs-lookup"><span data-stu-id="38eb8-152">Right-click the **DebugControlLibrary** project and select **Set as StartUp Project** to enable this debugging configuration.</span></span>

## <a name="debug-your-custom-control-at-design-time"></a><span data-ttu-id="38eb8-153">Depurar el control personalizado en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="38eb8-153">Debug your custom control at design time</span></span>

<span data-ttu-id="38eb8-154">Ahora está listo para depurar el control personalizado mientras se ejecuta en modo de diseño.</span><span class="sxs-lookup"><span data-stu-id="38eb8-154">Now you are ready to debug your custom control as it runs in design mode.</span></span> <span data-ttu-id="38eb8-155">Al iniciar la sesión de depuración, se creará una nueva instancia de Visual Studio y se usará para cargar la solución "DebuggingExample".</span><span class="sxs-lookup"><span data-stu-id="38eb8-155">When you start the debugging session, a new instance of Visual Studio will be created, and you will use it to load the "DebuggingExample" solution.</span></span> <span data-ttu-id="38eb8-156">Cuando se abre Form1 en el **Diseñador de formularios**, una instancia del control personalizado se crea y se volverá a ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="38eb8-156">When you open Form1 in the **Forms Designer**, an instance of your custom control will be created and will start running.</span></span>

1. <span data-ttu-id="38eb8-157">Abra el **DebugControl** archivo de código fuente en el **Editor de código** y coloque un punto de interrupción en el `Set` descriptor de acceso de la `DemoString` propiedad.</span><span class="sxs-lookup"><span data-stu-id="38eb8-157">Open the **DebugControl** source file in the **Code Editor** and place a breakpoint on the `Set` accessor of the `DemoString` property.</span></span>

2. <span data-ttu-id="38eb8-158">Presione F5 para iniciar la sesión de depuración.</span><span class="sxs-lookup"><span data-stu-id="38eb8-158">Press F5 to start the debugging session.</span></span> <span data-ttu-id="38eb8-159">Tenga en cuenta que se crea una nueva instancia de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="38eb8-159">Note that a new instance of Visual Studio is created.</span></span> <span data-ttu-id="38eb8-160">Puede distinguir entre las instancias de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="38eb8-160">You can distinguish between the instances in two ways:</span></span>

    - <span data-ttu-id="38eb8-161">La instancia de depuración con la palabra **ejecutando** en su barra de título</span><span class="sxs-lookup"><span data-stu-id="38eb8-161">The debugging instance has the word **Running** in its title bar</span></span>

    - <span data-ttu-id="38eb8-162">La instancia de depuración tiene el **iniciar** situado en su **depurar** deshabilitado de la barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="38eb8-162">The debugging instance has the **Start** button on its **Debug** toolbar disabled</span></span>

     <span data-ttu-id="38eb8-163">El punto de interrupción se establece en la instancia de depuración.</span><span class="sxs-lookup"><span data-stu-id="38eb8-163">Your breakpoint is set in the debugging instance.</span></span>

3. <span data-ttu-id="38eb8-164">En la nueva instancia de Visual Studio, abra la solución "DebuggingExample".</span><span class="sxs-lookup"><span data-stu-id="38eb8-164">In the new instance of Visual Studio, open the "DebuggingExample" solution.</span></span> <span data-ttu-id="38eb8-165">Puede encontrar fácilmente la solución seleccionando **proyectos recientes** desde el **archivo** menú.</span><span class="sxs-lookup"><span data-stu-id="38eb8-165">You can easily find the solution by selecting **Recent Projects** from the **File** menu.</span></span> <span data-ttu-id="38eb8-166">El archivo de solución "DebuggingExample.sln" se mostrará como los archivos usados recientemente.</span><span class="sxs-lookup"><span data-stu-id="38eb8-166">The "DebuggingExample.sln" solution file will be listed as the most recently used file.</span></span>

4. <span data-ttu-id="38eb8-167">Abra Form1 en el **Diseñador de formularios** y seleccione el **DebugControl** control.</span><span class="sxs-lookup"><span data-stu-id="38eb8-167">Open Form1 in the **Forms Designer** and select the **DebugControl** control.</span></span>

5. <span data-ttu-id="38eb8-168">Cambie el valor de la propiedad `DemoString` .</span><span class="sxs-lookup"><span data-stu-id="38eb8-168">Change the value of the `DemoString` property.</span></span> <span data-ttu-id="38eb8-169">Tenga en cuenta que cuando se confirma el cambio, la instancia de depuración de Visual Studio adquiere el foco y la ejecución se detiene en el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="38eb8-169">Note that when you commit the change, the debugging instance of Visual Studio acquires focus and execution stops at your breakpoint.</span></span> <span data-ttu-id="38eb8-170">Puede paso a paso a través del descriptor de acceso de propiedad al igual que su cualquier otro código.</span><span class="sxs-lookup"><span data-stu-id="38eb8-170">You can single-step through the property accessor just as your would any other code.</span></span>

6. <span data-ttu-id="38eb8-171">Cuando haya terminado con la sesión de depuración, puede salir descartando la instancia hospedada de Visual Studio o haciendo clic en el **Detener depuración** botón en la instancia de depuración.</span><span class="sxs-lookup"><span data-stu-id="38eb8-171">When you are finished with your debugging session, you can exit by dismissing the hosted instance of Visual Studio or by clicking the **Stop Debugging** button in the debugging instance.</span></span>

## <a name="next-steps"></a><span data-ttu-id="38eb8-172">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="38eb8-172">Next steps</span></span>

<span data-ttu-id="38eb8-173">Ahora que puede depurar controles personalizados en tiempo de diseño, hay muchas posibilidades para expandir la interacción del control con el IDE de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="38eb8-173">Now that you can debug your custom controls at design time, there are many possibilities for expanding your control's interaction with the Visual Studio IDE.</span></span>

- <span data-ttu-id="38eb8-174">Puede usar el <xref:System.ComponentModel.Component.DesignMode%2A> propiedad de la <xref:System.ComponentModel.Component> clase para escribir código que solo se ejecutará en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="38eb8-174">You can use the <xref:System.ComponentModel.Component.DesignMode%2A> property of the <xref:System.ComponentModel.Component> class to write code that will only execute at design time.</span></span> <span data-ttu-id="38eb8-175">Para obtener información detallada, vea <xref:System.ComponentModel.Component.DesignMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="38eb8-175">For details, see <xref:System.ComponentModel.Component.DesignMode%2A>.</span></span>

- <span data-ttu-id="38eb8-176">Hay varios atributos puede aplicar a las propiedades del control para manipular la interacción del control personalizado con el diseñador.</span><span class="sxs-lookup"><span data-stu-id="38eb8-176">There are several attributes you can apply to your control's properties to manipulate your custom control's interaction with the designer.</span></span> <span data-ttu-id="38eb8-177">Puede encontrar estos atributos en el <xref:System.ComponentModel?displayProperty=nameWithType> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="38eb8-177">You can find these attributes in the <xref:System.ComponentModel?displayProperty=nameWithType> namespace.</span></span>

- <span data-ttu-id="38eb8-178">Puede escribir un diseñador personalizado para el control personalizado.</span><span class="sxs-lookup"><span data-stu-id="38eb8-178">You can write a custom designer for your custom control.</span></span> <span data-ttu-id="38eb8-179">Esto le ofrece control completo sobre la experiencia de diseño mediante la infraestructura del diseñador extensible expuesta por Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="38eb8-179">This gives you complete control over the design experience using the extensible designer infrastructure exposed by Visual Studio.</span></span> <span data-ttu-id="38eb8-180">Para obtener más información, consulte [Tutorial: Crear un Windows Forms Control que aprovecha las características de tiempo de diseño de Visual Studio](creating-a-wf-control-design-time-features.md).</span><span class="sxs-lookup"><span data-stu-id="38eb8-180">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="38eb8-181">Vea también</span><span class="sxs-lookup"><span data-stu-id="38eb8-181">See also</span></span>

- [<span data-ttu-id="38eb8-182">Tutorial: Crear un Control de Windows Forms que aproveche las características de tiempo de diseño de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="38eb8-182">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)
- <span data-ttu-id="38eb8-183">[Cómo: Acceso a servicios en tiempo de diseño](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171822(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="38eb8-183">[How to: Access Design-Time Services](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171822(v=vs.120))</span></span>
- <span data-ttu-id="38eb8-184">[Cómo: Compatibilidad de tiempo de diseño de acceso en Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171827(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="38eb8-184">[How to: Access Design-Time Support in Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171827(v=vs.120))</span></span>
