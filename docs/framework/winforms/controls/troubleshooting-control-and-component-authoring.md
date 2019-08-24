---
title: Solución de problemas relacionados con la creación de controles y componentes
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- troubleshooting components
- troubleshooting controls [Windows Forms]
- controls [Windows Forms], troubleshooting
- components [Windows Forms], troubleshooting
- Windows Forms controls, debugging
ms.assetid: e9c8c099-2271-4737-882f-50f336c7a55e
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 2e0b98107ac5f43c80aad6cb5ea61e6f4e1e28d3
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015713"
---
# <a name="troubleshoot-control-and-component-authoring"></a><span data-ttu-id="c83c3-102">Solucionar problemas de control y creación de componentes</span><span class="sxs-lookup"><span data-stu-id="c83c3-102">Troubleshoot Control and Component Authoring</span></span>

<span data-ttu-id="c83c3-103">En este tema se enumeran los siguientes problemas comunes que surgen al desarrollar componentes y controles:</span><span class="sxs-lookup"><span data-stu-id="c83c3-103">This topic lists the following common problems that arise when developing components and controls:</span></span>

- <span data-ttu-id="c83c3-104">No se puede agregar el control al cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="c83c3-104">Cannot Add Control to Toolbox</span></span>

- <span data-ttu-id="c83c3-105">No se puede depurar el control de usuario de Windows Forms o un componente</span><span class="sxs-lookup"><span data-stu-id="c83c3-105">Cannot Debug the Windows Forms User Control or Component</span></span>

- <span data-ttu-id="c83c3-106">El evento se genera dos veces en el control o el componente heredado</span><span class="sxs-lookup"><span data-stu-id="c83c3-106">Event Is Raised Twice in Inherited Control or Component</span></span>

- <span data-ttu-id="c83c3-107">Error en tiempo de diseño: "No se pudo crear el componente '*nombre de componente*'"</span><span class="sxs-lookup"><span data-stu-id="c83c3-107">Design-Time Error: "Failed to Create Component '*Component Name*'"</span></span>

- <span data-ttu-id="c83c3-108">STAThreadAttribute</span><span class="sxs-lookup"><span data-stu-id="c83c3-108">STAThreadAttribute</span></span>

- <span data-ttu-id="c83c3-109">El icono del componente no aparece en el cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="c83c3-109">Component Icon Does Not Appear in Toolbox</span></span>

## <a name="cannot-add-control-to-toolbox"></a><span data-ttu-id="c83c3-110">No se puede agregar el control al cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="c83c3-110">Cannot Add Control to Toolbox</span></span>

<span data-ttu-id="c83c3-111">Si desea agregar un control personalizado que creó en otro proyecto o un control de terceros al **cuadro de herramientas**, debe hacerlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="c83c3-111">If you want to add a custom control that you created in another project or a third-party control to the **Toolbox**, you must do so manually.</span></span> <span data-ttu-id="c83c3-112">Si el proyecto actual contiene el control o componente, debería aparecer en el **cuadro de herramientas** automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c83c3-112">If the current project contains your control or component, it should appear in the **Toolbox** automatically.</span></span> <span data-ttu-id="c83c3-113">Para obtener más información, vea [Tutorial: Rellenar automáticamente el cuadro de](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)herramientas con componentes personalizados.</span><span class="sxs-lookup"><span data-stu-id="c83c3-113">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>

### <a name="to-add-a-control-to-the-toolbox"></a><span data-ttu-id="c83c3-114">Para agregar un control al cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="c83c3-114">To add a control to the Toolbox</span></span>

1. <span data-ttu-id="c83c3-115">Haga clic con el botón derecho en el **cuadro de herramientas** y, en el menú contextual, seleccione **Elegir elementos**.</span><span class="sxs-lookup"><span data-stu-id="c83c3-115">Right-click the **Toolbox** and from the shortcut menu, select **Choose Items**.</span></span>

2. <span data-ttu-id="c83c3-116">En el cuadro de diálogo **Elegir elementos de cuadro de herramientas**, agregue el componente:</span><span class="sxs-lookup"><span data-stu-id="c83c3-116">In the **Choose Toolbox Items** dialog box, add the component:</span></span>

    - <span data-ttu-id="c83c3-117">Si desea agregar un control o un componente de .NET Framework, haga clic en la pestaña **Componentes de .NET Framework**.</span><span class="sxs-lookup"><span data-stu-id="c83c3-117">If you want to add a .NET Framework component or control, click the **.NET Framework Components** tab.</span></span>

         <span data-ttu-id="c83c3-118">-O bien-</span><span class="sxs-lookup"><span data-stu-id="c83c3-118">– or –</span></span>

    - <span data-ttu-id="c83c3-119">Si desea agregar un componente COM o un control ActiveX, haga clic en la pestaña **Componentes COM**.</span><span class="sxs-lookup"><span data-stu-id="c83c3-119">If you want to add a COM component or ActiveX control, click the **COM Components** tab.</span></span>

3. <span data-ttu-id="c83c3-120">Si el control aparece en el cuadro de diálogo, confirme que está seleccionado y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c83c3-120">If your control is listed in the dialog box, confirm it is selected, and then click **OK**.</span></span>

     <span data-ttu-id="c83c3-121">El control se agrega al **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="c83c3-121">The control is added to the **Toolbox**.</span></span>

4. <span data-ttu-id="c83c3-122">Si el control no aparece en el cuadro de diálogo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c83c3-122">If your control is not listed in the dialog box, do the following:</span></span>

    1. <span data-ttu-id="c83c3-123">Haga clic en el botón **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="c83c3-123">Click the **Browse** button.</span></span>

    2. <span data-ttu-id="c83c3-124">Vaya a la carpeta que contiene el archivo .dll que contiene el control.</span><span class="sxs-lookup"><span data-stu-id="c83c3-124">Browse to the folder that contains the .dll file that contains your control.</span></span>

    3. <span data-ttu-id="c83c3-125">Seleccione el archivo .dll y haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="c83c3-125">Select the .dll file and click **Open**.</span></span>

         <span data-ttu-id="c83c3-126">El control aparece en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="c83c3-126">Your control appears in the dialog box.</span></span>

    4. <span data-ttu-id="c83c3-127">Confirme que el control está seleccionado y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c83c3-127">Confirm that your control is selected, and then click **OK**.</span></span>

         <span data-ttu-id="c83c3-128">El control se agrega al **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="c83c3-128">Your control is added to the **Toolbox**.</span></span>

## <a name="cannot-debug-the-windows-forms-user-control-or-component"></a><span data-ttu-id="c83c3-129">No se puede depurar el control de usuario de Windows Forms o un componente</span><span class="sxs-lookup"><span data-stu-id="c83c3-129">Cannot Debug the Windows Forms User Control or Component</span></span>

<span data-ttu-id="c83c3-130">Si el control se deriva de la <xref:System.Windows.Forms.UserControl> clase, puede depurar su comportamiento en tiempo de ejecución con el contenedor de prueba.</span><span class="sxs-lookup"><span data-stu-id="c83c3-130">If your control derives from the <xref:System.Windows.Forms.UserControl> class, you can debug its run-time behavior with the test container.</span></span> <span data-ttu-id="c83c3-131">Para obtener más información, vea [Cómo: Pruebe el comportamiento en tiempo de ejecución de un](how-to-test-the-run-time-behavior-of-a-usercontrol.md)control UserControl.</span><span class="sxs-lookup"><span data-stu-id="c83c3-131">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

<span data-ttu-id="c83c3-132">Otros controles y componentes personalizados no son proyectos independientes.</span><span class="sxs-lookup"><span data-stu-id="c83c3-132">Other custom controls and components are not stand-alone projects.</span></span> <span data-ttu-id="c83c3-133">Deben hospedarse en una aplicación, como un proyecto de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c83c3-133">They must be hosted by an application such as a Windows Forms project.</span></span> <span data-ttu-id="c83c3-134">Para depurar un control o componente, debe agregarlo a un proyecto de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c83c3-134">To debug a control or component, you must add it to a Windows Forms project.</span></span>

### <a name="to-debug-a-control-or-component"></a><span data-ttu-id="c83c3-135">Para depurar un control o componente</span><span class="sxs-lookup"><span data-stu-id="c83c3-135">To debug a control or component</span></span>

1. <span data-ttu-id="c83c3-136">Para compilar la solución, en el menú **Compilar**, haga clic en **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="c83c3-136">From the **Build** menu, click **Build Solution** to build your solution.</span></span>

2. <span data-ttu-id="c83c3-137">En el menú **Archivo**, elija **Agregar** y, luego, elija **Nuevo proyecto** para agregar un proyecto de prueba a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c83c3-137">From the **File** menu, choose **Add**, and then **New Project** to add a test project to your application.</span></span>

3. <span data-ttu-id="c83c3-138">En el cuadro de diálogo **Agregar nuevo proyecto**, elija **Aplicación de Windows** como tipo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="c83c3-138">In the **Add New Project** dialog box choose **Windows Application** for the type of project.</span></span>

4. <span data-ttu-id="c83c3-139">En el **Explorador de soluciones**, haga clic con el botón derecho en el nodo **Referencias** del nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="c83c3-139">In **Solution Explorer**, right-click the **References** node for the new project.</span></span> <span data-ttu-id="c83c3-140">En el menú contextual, haga clic en **Agregar referencia** para agregar una referencia al proyecto que contiene el control o componente.</span><span class="sxs-lookup"><span data-stu-id="c83c3-140">On the shortcut menu, click **Add Reference** to add a reference to the project containing the control or component.</span></span>

5. <span data-ttu-id="c83c3-141">Crear una instancia de un control o componente en el proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="c83c3-141">Create an instance of your control or component in the test project.</span></span> <span data-ttu-id="c83c3-142">Si el componente está en el **cuadro de herramientas**, puede arrastrarlo a la superficie del diseñador o puede crear la instancia mediante programación, tal y como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="c83c3-142">If your component is in the **Toolbox**, you can drag it to your designer surface, or you can create the instance programmatically, as shown in the following code example.</span></span>

    ```vb
    Dim Component1 As New MyNeatComponent()
    ```

    ```csharp
    MyNeatComponent Component1 = new MyNeatComponent();
    ```

   <span data-ttu-id="c83c3-143">Ahora puede depurar el control o componente como de costumbre.</span><span class="sxs-lookup"><span data-stu-id="c83c3-143">You can now debug your control or component as usual.</span></span>

<span data-ttu-id="c83c3-144">Para obtener más información sobre la depuración, vea depuración [ [en Visual Studio](/visualstudio/debugger/debugging-in-visual-studio) y Tutorial: Depurar controles de Windows Forms personalizados en](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="c83c3-144">For more information about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio) and [Walkthrough: Debugging Custom Windows Forms Controls at Design Time](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).</span></span>

## <a name="event-is-raised-twice-in-inherited-control-or-component"></a><span data-ttu-id="c83c3-145">El evento se genera dos veces en el control o el componente heredado</span><span class="sxs-lookup"><span data-stu-id="c83c3-145">Event Is Raised Twice in Inherited Control or Component</span></span>

<span data-ttu-id="c83c3-146">Probablemente se debe a una cláusula `Handles` duplicada.</span><span class="sxs-lookup"><span data-stu-id="c83c3-146">This is likely due to a duplicated `Handles` clause.</span></span> <span data-ttu-id="c83c3-147">Para obtener más información, consulte [Solución de problemas de controladores de eventos heredados en Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="c83c3-147">For more information, see [Troubleshooting Inherited Event Handlers in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).</span></span>

## <a name="design-time-error-failed-to-create-component-component-name"></a><span data-ttu-id="c83c3-148">Error en tiempo de diseño: "No se pudo crear el componente ' nombre de componente '"</span><span class="sxs-lookup"><span data-stu-id="c83c3-148">Design-Time Error: "Failed to Create Component 'Component Name'"</span></span>

<span data-ttu-id="c83c3-149">El componente o el control deben proporcionar un constructor sin parámetros sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="c83c3-149">Your component or control must provide a parameterless constructor with no parameters.</span></span> <span data-ttu-id="c83c3-150">Cuando el entorno de diseño crea una instancia de un componente o control, no intenta proporcionar ningún parámetro a las sobrecargas del constructor que toman parámetros.</span><span class="sxs-lookup"><span data-stu-id="c83c3-150">When the design environment creates an instance of your component or control, it does not attempt to provide any parameters to constructor overloads that take parameters.</span></span>

## <a name="stathreadattribute"></a><span data-ttu-id="c83c3-151">STAThreadAttribute</span><span class="sxs-lookup"><span data-stu-id="c83c3-151">STAThreadAttribute</span></span>

<span data-ttu-id="c83c3-152"><xref:System.STAThreadAttribute> Informa al Common Language Runtime (CLR) que Windows Forms utiliza el modelo de apartamento de un solo subproceso.</span><span class="sxs-lookup"><span data-stu-id="c83c3-152">The <xref:System.STAThreadAttribute> informs the common language runtime (CLR) that Windows Forms uses the single-threaded apartment model.</span></span> <span data-ttu-id="c83c3-153">Podría observar un comportamiento imprevisto si no aplica este atributo al método `Main` de su aplicación de formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c83c3-153">You may notice unintended behavior if you do not apply this attribute to your Windows Forms application's `Main` method.</span></span> <span data-ttu-id="c83c3-154">Por ejemplo, puede que no aparezcan imágenes de fondo <xref:System.Windows.Forms.ListView>para controles como.</span><span class="sxs-lookup"><span data-stu-id="c83c3-154">For example, background images may not appear for controls like <xref:System.Windows.Forms.ListView>.</span></span> <span data-ttu-id="c83c3-155">Algunos controles también pueden requerir este atributo para que los comportamientos de Autocompletar y arrastrar y colocar sean correctos.</span><span class="sxs-lookup"><span data-stu-id="c83c3-155">Some controls may also require this attribute for correct AutoComplete and drag-and-drop behavior.</span></span>

## <a name="component-icon-does-not-appear-in-toolbox"></a><span data-ttu-id="c83c3-156">El icono del componente no aparece en el cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="c83c3-156">Component Icon Does Not Appear in Toolbox</span></span>

<span data-ttu-id="c83c3-157">Cuando se usa <xref:System.Drawing.ToolboxBitmapAttribute> para asociar un icono al componente personalizado, el mapa de bits no aparece en el cuadro de herramientas para los componentes generados automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c83c3-157">When you use <xref:System.Drawing.ToolboxBitmapAttribute> to associate an icon with your custom component, the bitmap does not appear in the Toolbox for autogenerated components.</span></span> <span data-ttu-id="c83c3-158">Para ver el mapa de bits, vuelva a cargar el control con el cuadro de diálogo **Elegir elementos del cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="c83c3-158">To see the bitmap, reload the control by using the **Choose Toolbox Items** dialog box.</span></span> <span data-ttu-id="c83c3-159">Para obtener más información, vea [Cómo: Proporcione un mapa de bits del cuadro](how-to-provide-a-toolbox-bitmap-for-a-control.md)de herramientas para un control.</span><span class="sxs-lookup"><span data-stu-id="c83c3-159">For more information, see [How to: Provide a Toolbox Bitmap for a Control](how-to-provide-a-toolbox-bitmap-for-a-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c83c3-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="c83c3-160">See also</span></span>

- [<span data-ttu-id="c83c3-161">Desarrollar controles de Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="c83c3-161">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
- [<span data-ttu-id="c83c3-162">Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados</span><span class="sxs-lookup"><span data-stu-id="c83c3-162">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
- [<span data-ttu-id="c83c3-163">Cómo: Probar el comportamiento en tiempo de ejecución de un control UserControl</span><span class="sxs-lookup"><span data-stu-id="c83c3-163">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)
- [<span data-ttu-id="c83c3-164">Tutorial: Depurar controles personalizados de Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="c83c3-164">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)
