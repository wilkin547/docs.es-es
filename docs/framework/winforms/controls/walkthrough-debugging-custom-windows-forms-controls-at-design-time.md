---
title: Depurar controles personalizados en tiempo de diseño
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
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: d9e292a1219c24571bcb35db2fe357b0197c8812
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740187"
---
# <a name="walkthrough-debug-custom-windows-forms-controls-at-design-time"></a><span data-ttu-id="2aad9-102">Tutorial: depurar controles de Windows Forms personalizados en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="2aad9-102">Walkthrough: Debug Custom Windows Forms Controls at Design Time</span></span>

<span data-ttu-id="2aad9-103">Al crear un control personalizado, a menudo es necesario depurar su comportamiento en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="2aad9-103">When you create a custom control, you will often find it necessary to debug its design-time behavior.</span></span> <span data-ttu-id="2aad9-104">Esto es especialmente cierto si va a crear un diseñador personalizado para el control personalizado.</span><span class="sxs-lookup"><span data-stu-id="2aad9-104">This is especially true if you are authoring a custom designer for your custom control.</span></span> <span data-ttu-id="2aad9-105">Para obtener más información, vea [Tutorial: crear un control de Windows Forms que aprovecha las características en tiempo de diseño de Visual Studio](creating-a-wf-control-design-time-features.md).</span><span class="sxs-lookup"><span data-stu-id="2aad9-105">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md).</span></span>

<span data-ttu-id="2aad9-106">Puede depurar los controles personalizados mediante Visual Studio, tal y como lo haría con cualquier otra clase de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2aad9-106">You can debug your custom controls using Visual Studio, just as you would debug any other .NET Framework classes.</span></span> <span data-ttu-id="2aad9-107">La diferencia es que se depurará una instancia independiente de Visual Studio que ejecute el código del control personalizado.</span><span class="sxs-lookup"><span data-stu-id="2aad9-107">The difference is that you will debug a separate instance of Visual Studio that is running your custom control's code.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="2aad9-108">Creación del proyecto</span><span class="sxs-lookup"><span data-stu-id="2aad9-108">Create the project</span></span>

<span data-ttu-id="2aad9-109">El primer paso es crear el proyecto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2aad9-109">The first step is to create the application project.</span></span> <span data-ttu-id="2aad9-110">Usará este proyecto para compilar la aplicación que hospeda el control personalizado.</span><span class="sxs-lookup"><span data-stu-id="2aad9-110">You will use this project to build the application that hosts the custom control.</span></span>

<span data-ttu-id="2aad9-111">En Visual Studio, cree un proyecto de aplicación para Windows y asígnele el nombre **DebuggingExample**.</span><span class="sxs-lookup"><span data-stu-id="2aad9-111">In Visual Studio, create a Windows Application project, and name it **DebuggingExample**.</span></span>

## <a name="create-the-control-library-project"></a><span data-ttu-id="2aad9-112">Crear el proyecto de biblioteca de controles</span><span class="sxs-lookup"><span data-stu-id="2aad9-112">Create the control library project</span></span>

1. <span data-ttu-id="2aad9-113">Agregue un proyecto de **biblioteca de controles de Windows** a la solución.</span><span class="sxs-lookup"><span data-stu-id="2aad9-113">Add a **Windows Control Library** project to the solution.</span></span>

2. <span data-ttu-id="2aad9-114">Agregue un nuevo elemento **UserControl** al proyecto DebugControlLibrary.</span><span class="sxs-lookup"><span data-stu-id="2aad9-114">Add a new **UserControl** item to the DebugControlLibrary project.</span></span> <span data-ttu-id="2aad9-115">Asígnele el nombre **DebugControl**.</span><span class="sxs-lookup"><span data-stu-id="2aad9-115">Name it **DebugControl**.</span></span>

3. <span data-ttu-id="2aad9-116">Para eliminar el control predeterminado del proyecto en **Explorador de soluciones**, elimine el archivo de código con un nombre base de UserControl1.</span><span class="sxs-lookup"><span data-stu-id="2aad9-116">In **Solution Explorer**, delete the project's default control by deleting the code file with a base name of UserControl1.</span></span>

4. <span data-ttu-id="2aad9-117">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="2aad9-117">Build the solution.</span></span>

## <a name="checkpoint"></a><span data-ttu-id="2aad9-118">Punto de control</span><span class="sxs-lookup"><span data-stu-id="2aad9-118">Checkpoint</span></span>

<span data-ttu-id="2aad9-119">Llegados a este punto, podrá ver el control personalizado en el cuadro de **herramientas**.</span><span class="sxs-lookup"><span data-stu-id="2aad9-119">At this point, you will be able to see your custom control in the **Toolbox**.</span></span>

<span data-ttu-id="2aad9-120">Para comprobar el progreso, busque la nueva pestaña denominada **componentes de DebugControlLibrary** y haga clic para seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="2aad9-120">To check your progress, find the new tab called **DebugControlLibrary Components** and click to select it.</span></span> <span data-ttu-id="2aad9-121">Cuando se abra, verá que el control aparece como **DebugControl** con el icono predeterminado situado junto a él.</span><span class="sxs-lookup"><span data-stu-id="2aad9-121">When it opens, you will see your control listed as **DebugControl** with the default icon beside it.</span></span>

## <a name="add-a-property-to-your-custom-control"></a><span data-ttu-id="2aad9-122">Agregar una propiedad a un control personalizado</span><span class="sxs-lookup"><span data-stu-id="2aad9-122">Add a property to your custom control</span></span>

<span data-ttu-id="2aad9-123">Para demostrar que el código del control personalizado se está ejecutando en tiempo de diseño, agregará una propiedad y establecerá un punto de interrupción en el código que implementa la propiedad.</span><span class="sxs-lookup"><span data-stu-id="2aad9-123">To demonstrate that your custom control's code is running at design-time, you will add a property and set a breakpoint in the code that implements the property.</span></span>

1. <span data-ttu-id="2aad9-124">Abra **DebugControl** en el **Editor de código**.</span><span class="sxs-lookup"><span data-stu-id="2aad9-124">Open **DebugControl** in the **Code Editor**.</span></span> <span data-ttu-id="2aad9-125">Agregue el código siguiente a la definición de clase:</span><span class="sxs-lookup"><span data-stu-id="2aad9-125">Add the following code to the class definition:</span></span>

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

2. <span data-ttu-id="2aad9-126">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="2aad9-126">Build the solution.</span></span>

## <a name="add-your-custom-control-to-the-host-form"></a><span data-ttu-id="2aad9-127">Agregar el control personalizado al formulario de host</span><span class="sxs-lookup"><span data-stu-id="2aad9-127">Add your custom control to the host form</span></span>

<span data-ttu-id="2aad9-128">Para depurar el comportamiento en tiempo de diseño del control personalizado, colocará una instancia de la clase de control personalizada en un formulario host.</span><span class="sxs-lookup"><span data-stu-id="2aad9-128">To debug the design-time behavior of your custom control, you will place an instance of the custom control class on a host form.</span></span>

1. <span data-ttu-id="2aad9-129">En el proyecto "DebuggingExample", abra Form1 en el **Diseñador de Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="2aad9-129">In the "DebuggingExample" project, open Form1 in the **Windows Forms Designer**.</span></span>

2. <span data-ttu-id="2aad9-130">En el **cuadro de herramientas**, abra la pestaña **componentes de DebugControlLibrary** y arrastre una instancia de **DebugControl** al formulario.</span><span class="sxs-lookup"><span data-stu-id="2aad9-130">In the **Toolbox**, open the **DebugControlLibrary Components** tab and drag a **DebugControl** instance onto the form.</span></span>

3. <span data-ttu-id="2aad9-131">Busque la propiedad personalizada `DemoString` en la ventana **propiedades** .</span><span class="sxs-lookup"><span data-stu-id="2aad9-131">Find the `DemoString` custom property in the **Properties** window.</span></span> <span data-ttu-id="2aad9-132">Tenga en cuenta que puede cambiar su valor como lo haría con cualquier otra propiedad.</span><span class="sxs-lookup"><span data-stu-id="2aad9-132">Note that you can change its value as you would any other property.</span></span> <span data-ttu-id="2aad9-133">Tenga en cuenta también que cuando se selecciona la propiedad `DemoString`, la cadena de descripción de la propiedad aparece en la parte inferior de la ventana **propiedades** .</span><span class="sxs-lookup"><span data-stu-id="2aad9-133">Also note that when the `DemoString` property is selected, the property's description string appears at the bottom of the **Properties** window.</span></span>

## <a name="set-up-the-project-for-design-time-debugging"></a><span data-ttu-id="2aad9-134">Configurar el proyecto para la depuración en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="2aad9-134">Set up the project for design-time debugging</span></span>

<span data-ttu-id="2aad9-135">Para depurar el comportamiento en tiempo de diseño del control personalizado, depurará una instancia independiente de Visual Studio que ejecute el código del control personalizado.</span><span class="sxs-lookup"><span data-stu-id="2aad9-135">To debug your custom control's design-time behavior, you will debug a separate instance of Visual Studio that is running your custom control's code.</span></span>

1. <span data-ttu-id="2aad9-136">Haga clic con el botón derecho en el proyecto **DebugControlLibrary** en el **Explorador de soluciones** y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2aad9-136">Right-click on the **DebugControlLibrary** project in the **Solution Explorer** and select **Properties**.</span></span>

2. <span data-ttu-id="2aad9-137">En la hoja de propiedades **DebugControlLibrary** , seleccione la pestaña **depurar** .</span><span class="sxs-lookup"><span data-stu-id="2aad9-137">In the **DebugControlLibrary** property sheet, select the **Debug** tab.</span></span>

     <span data-ttu-id="2aad9-138">En la sección **acción de inicio** , seleccione **programa externo de inicio**.</span><span class="sxs-lookup"><span data-stu-id="2aad9-138">In the **Start Action** section, select **Start external program**.</span></span> <span data-ttu-id="2aad9-139">Va a depurar una instancia independiente de Visual Studio, por lo que debe hacer clic en los puntos suspensivos (![el botón de puntos suspensivos (...) en el botón ventana Propiedades de Visual Studio](./media/visual-studio-ellipsis-button.png)) para buscar el IDE de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2aad9-139">You will be debugging a separate instance of Visual Studio, so click the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio](./media/visual-studio-ellipsis-button.png)) button to browse for the Visual Studio IDE.</span></span> <span data-ttu-id="2aad9-140">El nombre del archivo ejecutable es **devenv. exe**y, si lo instaló en la ubicación predeterminada, su ruta de acceso es *% ProgramFiles (x86)% \ Microsoft Visual Studio\2019\\\<Edition > \Common7\IDE*.</span><span class="sxs-lookup"><span data-stu-id="2aad9-140">The name of the executable file is **devenv.exe**, and if you installed to the default location, its path is *%ProgramFiles(x86)%\Microsoft Visual Studio\2019\\\<edition>\Common7\IDE*.</span></span>

3. <span data-ttu-id="2aad9-141">Seleccione **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2aad9-141">Select **OK** to close the dialog box.</span></span>

4. <span data-ttu-id="2aad9-142">Haga clic con el botón derecho en el proyecto **DebugControlLibrary** y seleccione **establecer como proyecto de inicio** para habilitar esta configuración de depuración.</span><span class="sxs-lookup"><span data-stu-id="2aad9-142">Right-click the **DebugControlLibrary** project and select **Set as StartUp Project** to enable this debugging configuration.</span></span>

## <a name="debug-your-custom-control-at-design-time"></a><span data-ttu-id="2aad9-143">Depurar el control personalizado en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="2aad9-143">Debug your custom control at design time</span></span>

<span data-ttu-id="2aad9-144">Ahora está listo para depurar el control personalizado mientras se ejecuta en modo de diseño.</span><span class="sxs-lookup"><span data-stu-id="2aad9-144">Now you are ready to debug your custom control as it runs in design mode.</span></span> <span data-ttu-id="2aad9-145">Al iniciar la sesión de depuración, se creará una nueva instancia de Visual Studio y se usará para cargar la solución "DebuggingExample".</span><span class="sxs-lookup"><span data-stu-id="2aad9-145">When you start the debugging session, a new instance of Visual Studio will be created, and you will use it to load the "DebuggingExample" solution.</span></span> <span data-ttu-id="2aad9-146">Cuando abra Form1 en el **Diseñador de formularios**, se creará una instancia del control personalizado y comenzará a ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="2aad9-146">When you open Form1 in the **Forms Designer**, an instance of your custom control will be created and will start running.</span></span>

1. <span data-ttu-id="2aad9-147">Abra el archivo de origen **DebugControl** en el **Editor de código** y coloque un punto de interrupción en el descriptor de acceso `Set` de la propiedad `DemoString`.</span><span class="sxs-lookup"><span data-stu-id="2aad9-147">Open the **DebugControl** source file in the **Code Editor** and place a breakpoint on the `Set` accessor of the `DemoString` property.</span></span>

2. <span data-ttu-id="2aad9-148">Presione **F5** para iniciar la sesión de depuración.</span><span class="sxs-lookup"><span data-stu-id="2aad9-148">Press **F5** to start the debugging session.</span></span> <span data-ttu-id="2aad9-149">Se crea una nueva instancia de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2aad9-149">A new instance of Visual Studio is created.</span></span> <span data-ttu-id="2aad9-150">Puede distinguir entre las instancias de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="2aad9-150">You can distinguish between the instances in two ways:</span></span>

    - <span data-ttu-id="2aad9-151">La instancia de depuración tiene la palabra en **ejecución** en la barra de título</span><span class="sxs-lookup"><span data-stu-id="2aad9-151">The debugging instance has the word **Running** in its title bar</span></span>

    - <span data-ttu-id="2aad9-152">La instancia de depuración tiene el botón **iniciar** en la barra de herramientas de **depuración** deshabilitada</span><span class="sxs-lookup"><span data-stu-id="2aad9-152">The debugging instance has the **Start** button on its **Debug** toolbar disabled</span></span>

   <span data-ttu-id="2aad9-153">El punto de interrupción se establece en la instancia de depuración.</span><span class="sxs-lookup"><span data-stu-id="2aad9-153">Your breakpoint is set in the debugging instance.</span></span>

3. <span data-ttu-id="2aad9-154">En la nueva instancia de Visual Studio, abra la solución "DebuggingExample".</span><span class="sxs-lookup"><span data-stu-id="2aad9-154">In the new instance of Visual Studio, open the "DebuggingExample" solution.</span></span> <span data-ttu-id="2aad9-155">Puede encontrar fácilmente la solución seleccionando **proyectos recientes** en el menú **archivo** .</span><span class="sxs-lookup"><span data-stu-id="2aad9-155">You can easily find the solution by selecting **Recent Projects** from the **File** menu.</span></span> <span data-ttu-id="2aad9-156">El archivo de solución "DebuggingExample. sln" se mostrará como el archivo usado más recientemente.</span><span class="sxs-lookup"><span data-stu-id="2aad9-156">The "DebuggingExample.sln" solution file will be listed as the most recently used file.</span></span>

4. <span data-ttu-id="2aad9-157">Abra Form1 en el **Diseñador de formularios** y seleccione el control **DebugControl** .</span><span class="sxs-lookup"><span data-stu-id="2aad9-157">Open Form1 in the **Forms Designer** and select the **DebugControl** control.</span></span>

5. <span data-ttu-id="2aad9-158">Cambie el valor de la propiedad `DemoString` .</span><span class="sxs-lookup"><span data-stu-id="2aad9-158">Change the value of the `DemoString` property.</span></span> <span data-ttu-id="2aad9-159">Al confirmar el cambio, la instancia de depuración de Visual Studio adquiere el foco y la ejecución se detiene en el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="2aad9-159">When you commit the change, the debugging instance of Visual Studio acquires focus and execution stops at your breakpoint.</span></span> <span data-ttu-id="2aad9-160">Puede recorrer el descriptor de acceso de la propiedad de la misma forma que cualquier otro código.</span><span class="sxs-lookup"><span data-stu-id="2aad9-160">You can single-step through the property accessor just as your would any other code.</span></span>

6. <span data-ttu-id="2aad9-161">Para detener la depuración, salga de la instancia hospedada de Visual Studio o seleccione el botón **detener depuración** en la instancia de depuración.</span><span class="sxs-lookup"><span data-stu-id="2aad9-161">To stop debugging, exit the hosted instance of Visual Studio or select the **Stop Debugging** button in the debugging instance.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2aad9-162">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="2aad9-162">Next steps</span></span>

<span data-ttu-id="2aad9-163">Ahora que puede depurar los controles personalizados en tiempo de diseño, hay muchas posibilidades de expandir la interacción del control con el IDE de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2aad9-163">Now that you can debug your custom controls at design time, there are many possibilities for expanding your control's interaction with the Visual Studio IDE.</span></span>

- <span data-ttu-id="2aad9-164">Puede usar la propiedad <xref:System.ComponentModel.Component.DesignMode%2A> de la clase <xref:System.ComponentModel.Component> para escribir código que solo se ejecutará en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="2aad9-164">You can use the <xref:System.ComponentModel.Component.DesignMode%2A> property of the <xref:System.ComponentModel.Component> class to write code that will only execute at design time.</span></span> <span data-ttu-id="2aad9-165">Para obtener información detallada, consulte <xref:System.ComponentModel.Component.DesignMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="2aad9-165">For details, see <xref:System.ComponentModel.Component.DesignMode%2A>.</span></span>

- <span data-ttu-id="2aad9-166">Hay varios atributos que se pueden aplicar a las propiedades del control para manipular la interacción del control personalizado con el diseñador.</span><span class="sxs-lookup"><span data-stu-id="2aad9-166">There are several attributes you can apply to your control's properties to manipulate your custom control's interaction with the designer.</span></span> <span data-ttu-id="2aad9-167">Puede encontrar estos atributos en el espacio de nombres <xref:System.ComponentModel?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2aad9-167">You can find these attributes in the <xref:System.ComponentModel?displayProperty=nameWithType> namespace.</span></span>

- <span data-ttu-id="2aad9-168">Puede escribir un diseñador personalizado para el control personalizado.</span><span class="sxs-lookup"><span data-stu-id="2aad9-168">You can write a custom designer for your custom control.</span></span> <span data-ttu-id="2aad9-169">Esto le proporciona un control completo sobre la experiencia de diseño mediante la infraestructura de diseñador extensible expuesta por Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2aad9-169">This gives you complete control over the design experience using the extensible designer infrastructure exposed by Visual Studio.</span></span> <span data-ttu-id="2aad9-170">Para obtener más información, vea [Tutorial: crear un control de Windows Forms que aprovecha las características en tiempo de diseño de Visual Studio](creating-a-wf-control-design-time-features.md).</span><span class="sxs-lookup"><span data-stu-id="2aad9-170">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2aad9-171">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2aad9-171">See also</span></span>

- [<span data-ttu-id="2aad9-172">Tutorial: Crear un control de Windows Forms que aproveche las características en tiempo de diseño de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2aad9-172">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)
