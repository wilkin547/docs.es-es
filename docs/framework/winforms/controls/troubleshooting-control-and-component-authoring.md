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
ms.openlocfilehash: 3ae8a889bf69913d234e31804335ddb08560c30c
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59343420"
---
# <a name="troubleshooting-control-and-component-authoring"></a><span data-ttu-id="ebcd8-102">Solución de problemas relacionados con la creación de controles y componentes</span><span class="sxs-lookup"><span data-stu-id="ebcd8-102">Troubleshooting Control and Component Authoring</span></span>
<span data-ttu-id="ebcd8-103">En este tema se enumeran los siguientes problemas comunes que surgen cuando se desarrollan componentes y controles.</span><span class="sxs-lookup"><span data-stu-id="ebcd8-103">This topic lists the following common problems that arise when developing components and controls.</span></span> <span data-ttu-id="ebcd8-104">Para obtener más información, vea [Programar con componentes](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0ffkdtkf(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="ebcd8-104">For more information, see [Programming with Components](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0ffkdtkf(v=vs.120)).</span></span>  
  
-   <span data-ttu-id="ebcd8-105">No se puede agregar el control al cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="ebcd8-105">Cannot Add Control to Toolbox</span></span>  
  
-   <span data-ttu-id="ebcd8-106">No se puede depurar el control de usuario de Windows Forms o un componente</span><span class="sxs-lookup"><span data-stu-id="ebcd8-106">Cannot Debug the Windows Forms User Control or Component</span></span>  
  
-   <span data-ttu-id="ebcd8-107">El evento se genera dos veces en el control o el componente heredado</span><span class="sxs-lookup"><span data-stu-id="ebcd8-107">Event Is Raised Twice in Inherited Control or Component</span></span>  
  
-   <span data-ttu-id="ebcd8-108">Error en tiempo de diseño: "No se pudo crear el componente '*nombre del componente*'"</span><span class="sxs-lookup"><span data-stu-id="ebcd8-108">Design-Time Error: "Failed to Create Component '*Component Name*'"</span></span>  
  
-   <span data-ttu-id="ebcd8-109">STAThreadAttribute</span><span class="sxs-lookup"><span data-stu-id="ebcd8-109">STAThreadAttribute</span></span>  
  
-   <span data-ttu-id="ebcd8-110">El icono del componente no aparece en el cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="ebcd8-110">Component Icon Does Not Appear in Toolbox</span></span>  
  
## <a name="cannot-add-control-to-toolbox"></a><span data-ttu-id="ebcd8-111">No se puede agregar el control al cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="ebcd8-111">Cannot Add Control to Toolbox</span></span>  
 <span data-ttu-id="ebcd8-112">Si desea agregar un control personalizado que creó en otro proyecto o un control de terceros al **cuadro de herramientas**, debe hacerlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="ebcd8-112">If you want to add a custom control that you created in another project or a third-party control to the **Toolbox**, you must do so manually.</span></span> <span data-ttu-id="ebcd8-113">Si el proyecto actual contiene el control o componente, debería aparecer en el **cuadro de herramientas** automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ebcd8-113">If the current project contains your control or component, it should appear in the **Toolbox** automatically.</span></span> <span data-ttu-id="ebcd8-114">Para obtener más información, vea [Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span><span class="sxs-lookup"><span data-stu-id="ebcd8-114">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>  
  
#### <a name="to-add-a-control-to-the-toolbox"></a><span data-ttu-id="ebcd8-115">Para agregar un control al cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="ebcd8-115">To add a control to the Toolbox</span></span>  
  
1. <span data-ttu-id="ebcd8-116">Haga clic con el botón derecho en el **cuadro de herramientas** y, en el menú contextual, seleccione **Elegir elementos**.</span><span class="sxs-lookup"><span data-stu-id="ebcd8-116">Right-click the **Toolbox** and from the shortcut menu, select **Choose Items**.</span></span>  
  
2. <span data-ttu-id="ebcd8-117">En el cuadro de diálogo **Elegir elementos de cuadro de herramientas**, agregue el componente:</span><span class="sxs-lookup"><span data-stu-id="ebcd8-117">In the **Choose Toolbox Items** dialog box, add the component:</span></span>  
  
    -   <span data-ttu-id="ebcd8-118">Si desea agregar un control o un componente de .NET Framework, haga clic en la pestaña **Componentes de .NET Framework**.</span><span class="sxs-lookup"><span data-stu-id="ebcd8-118">If you want to add a .NET Framework component or control, click the **.NET Framework Components** tab.</span></span>  
  
         <span data-ttu-id="ebcd8-119">-O bien-</span><span class="sxs-lookup"><span data-stu-id="ebcd8-119">– or –</span></span>  
  
    -   <span data-ttu-id="ebcd8-120">Si desea agregar un componente COM o un control ActiveX, haga clic en la pestaña **Componentes COM**.</span><span class="sxs-lookup"><span data-stu-id="ebcd8-120">If you want to add a COM component or ActiveX control, click the **COM Components** tab.</span></span>  
  
3. <span data-ttu-id="ebcd8-121">Si el control aparece en el cuadro de diálogo, confirme que está seleccionado y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ebcd8-121">If your control is listed in the dialog box, confirm it is selected, and then click **OK**.</span></span>  
  
     <span data-ttu-id="ebcd8-122">El control se agrega al **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="ebcd8-122">The control is added to the **Toolbox**.</span></span>  
  
4. <span data-ttu-id="ebcd8-123">Si el control no aparece en el cuadro de diálogo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ebcd8-123">If your control is not listed in the dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="ebcd8-124">Haga clic en el botón **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="ebcd8-124">Click the **Browse** button.</span></span>  
  
    2.  <span data-ttu-id="ebcd8-125">Vaya a la carpeta que contiene el archivo .dll que contiene el control.</span><span class="sxs-lookup"><span data-stu-id="ebcd8-125">Browse to the folder that contains the .dll file that contains your control.</span></span>  
  
    3.  <span data-ttu-id="ebcd8-126">Seleccione el archivo .dll y haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="ebcd8-126">Select the .dll file and click **Open**.</span></span>  
  
         <span data-ttu-id="ebcd8-127">El control aparece en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ebcd8-127">Your control appears in the dialog box.</span></span>  
  
    4.  <span data-ttu-id="ebcd8-128">Confirme que el control está seleccionado y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ebcd8-128">Confirm that your control is selected, and then click **OK**.</span></span>  
  
         <span data-ttu-id="ebcd8-129">El control se agrega al **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="ebcd8-129">Your control is added to the **Toolbox**.</span></span>  
  
## <a name="cannot-debug-the-windows-forms-user-control-or-component"></a><span data-ttu-id="ebcd8-130">No se puede depurar el control de usuario de Windows Forms o un componente</span><span class="sxs-lookup"><span data-stu-id="ebcd8-130">Cannot Debug the Windows Forms User Control or Component</span></span>  
 <span data-ttu-id="ebcd8-131">Si el control se deriva de la <xref:System.Windows.Forms.UserControl> (clase), puede depurar su comportamiento en tiempo de ejecución con el contenedor de prueba.</span><span class="sxs-lookup"><span data-stu-id="ebcd8-131">If your control derives from the <xref:System.Windows.Forms.UserControl> class, you can debug its run-time behavior with the test container.</span></span> <span data-ttu-id="ebcd8-132">Para obtener más información, vea [Cómo: Probar el comportamiento de tiempo de ejecución de una clase UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="ebcd8-132">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>  
  
 <span data-ttu-id="ebcd8-133">Otros controles y componentes personalizados no son proyectos independientes.</span><span class="sxs-lookup"><span data-stu-id="ebcd8-133">Other custom controls and components are not stand-alone projects.</span></span> <span data-ttu-id="ebcd8-134">Deben hospedarse en una aplicación, como un proyecto de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ebcd8-134">They must be hosted by an application such as a Windows Forms project.</span></span> <span data-ttu-id="ebcd8-135">Para depurar un control o componente, debe agregarlo a un proyecto de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ebcd8-135">To debug a control or component, you must add it to a Windows Forms project.</span></span>  
  
#### <a name="to-debug-a-control-or-component"></a><span data-ttu-id="ebcd8-136">Para depurar un control o componente</span><span class="sxs-lookup"><span data-stu-id="ebcd8-136">To debug a control or component</span></span>  
  
1. <span data-ttu-id="ebcd8-137">Para compilar la solución, en el menú **Compilar**, haga clic en **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="ebcd8-137">From the **Build** menu, click **Build Solution** to build your solution.</span></span>  
  
2. <span data-ttu-id="ebcd8-138">En el menú **Archivo**, elija **Agregar** y, luego, elija **Nuevo proyecto** para agregar un proyecto de prueba a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ebcd8-138">From the **File** menu, choose **Add**, and then **New Project** to add a test project to your application.</span></span>  
  
3. <span data-ttu-id="ebcd8-139">En el cuadro de diálogo **Agregar nuevo proyecto**, elija **Aplicación de Windows** como tipo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="ebcd8-139">In the **Add New Project** dialog box choose **Windows Application** for the type of project.</span></span>  
  
4. <span data-ttu-id="ebcd8-140">En el **Explorador de soluciones**, haga clic con el botón derecho en el nodo **Referencias** del nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="ebcd8-140">In **Solution Explorer**, right-click the **References** node for the new project.</span></span> <span data-ttu-id="ebcd8-141">En el menú contextual, haga clic en **Agregar referencia** para agregar una referencia al proyecto que contiene el control o componente.</span><span class="sxs-lookup"><span data-stu-id="ebcd8-141">On the shortcut menu, click **Add Reference** to add a reference to the project containing the control or component.</span></span>  
  
5. <span data-ttu-id="ebcd8-142">Crear una instancia de un control o componente en el proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="ebcd8-142">Create an instance of your control or component in the test project.</span></span> <span data-ttu-id="ebcd8-143">Si el componente está en el **cuadro de herramientas**, puede arrastrarlo a la superficie del diseñador o puede crear la instancia mediante programación, tal y como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="ebcd8-143">If your component is in the **Toolbox**, you can drag it to your designer surface, or you can create the instance programmatically, as shown in the following code example.</span></span>  
  
    ```vb  
    Dim Component1 As New MyNeatComponent()  
    ```  
  
    ```csharp  
    MyNeatComponent Component1 = new MyNeatComponent();  
    ```  
  
     <span data-ttu-id="ebcd8-144">Ahora puede depurar el control o componente como de costumbre.</span><span class="sxs-lookup"><span data-stu-id="ebcd8-144">You can now debug your control or component as usual.</span></span>  
  
 <span data-ttu-id="ebcd8-145">Para obtener más información sobre la depuración, vea [depuración en Visual Studio](/visualstudio/debugger/debugging-in-visual-studio) y [Tutorial: Controles de depuración personalizado Windows Forms en tiempo de diseño](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="ebcd8-145">For more information about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio) and [Walkthrough: Debugging Custom Windows Forms Controls at Design Time](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).</span></span>  
  
## <a name="event-is-raised-twice-in-inherited-control-or-component"></a><span data-ttu-id="ebcd8-146">El evento se genera dos veces en el control o el componente heredado</span><span class="sxs-lookup"><span data-stu-id="ebcd8-146">Event Is Raised Twice in Inherited Control or Component</span></span>  
 <span data-ttu-id="ebcd8-147">Probablemente se debe a una cláusula `Handles` duplicada.</span><span class="sxs-lookup"><span data-stu-id="ebcd8-147">This is likely due to a duplicated `Handles` clause.</span></span> <span data-ttu-id="ebcd8-148">Para obtener más información, consulte [Solución de problemas de controladores de eventos heredados en Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="ebcd8-148">For more information, see [Troubleshooting Inherited Event Handlers in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).</span></span>  
  
## <a name="design-time-error-failed-to-create-component-component-name"></a><span data-ttu-id="ebcd8-149">Error en tiempo de diseño: "No se pudo crear el componente 'Nombre de componente'"</span><span class="sxs-lookup"><span data-stu-id="ebcd8-149">Design-Time Error: "Failed to Create Component 'Component Name'"</span></span>  
 <span data-ttu-id="ebcd8-150">El componente o el control deben proporcionar un constructor predeterminado sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="ebcd8-150">Your component or control must provide a default constructor with no parameters.</span></span> <span data-ttu-id="ebcd8-151">Cuando el entorno de diseño crea una instancia de un componente o control, no intenta proporcionar ningún parámetro a las sobrecargas del constructor que toman parámetros.</span><span class="sxs-lookup"><span data-stu-id="ebcd8-151">When the design environment creates an instance of your component or control, it does not attempt to provide any parameters to constructor overloads that take parameters.</span></span>  
  
## <a name="stathreadattribute"></a><span data-ttu-id="ebcd8-152">STAThreadAttribute</span><span class="sxs-lookup"><span data-stu-id="ebcd8-152">STAThreadAttribute</span></span>  
 <span data-ttu-id="ebcd8-153">El <xref:System.STAThreadAttribute> informa a common language runtime (CLR) que Windows Forms utiliza el modelo de subprocesamiento controlado simple.</span><span class="sxs-lookup"><span data-stu-id="ebcd8-153">The <xref:System.STAThreadAttribute> informs the common language runtime (CLR) that Windows Forms uses the single-threaded apartment model.</span></span> <span data-ttu-id="ebcd8-154">Podría observar un comportamiento imprevisto si no aplica este atributo al método `Main` de su aplicación de formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ebcd8-154">You may notice unintended behavior if you do not apply this attribute to your Windows Forms application's `Main` method.</span></span> <span data-ttu-id="ebcd8-155">Por ejemplo, no pueden aparecer las imágenes de fondo para controles como <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="ebcd8-155">For example, background images may not appear for controls like <xref:System.Windows.Forms.ListView>.</span></span> <span data-ttu-id="ebcd8-156">Algunos controles también pueden requerir este atributo para que los comportamientos de Autocompletar y arrastrar y colocar sean correctos.</span><span class="sxs-lookup"><span data-stu-id="ebcd8-156">Some controls may also require this attribute for correct AutoComplete and drag-and-drop behavior.</span></span>  
  
## <a name="component-icon-does-not-appear-in-toolbox"></a><span data-ttu-id="ebcd8-157">El icono del componente no aparece en el cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="ebcd8-157">Component Icon Does Not Appear in Toolbox</span></span>  
 <span data-ttu-id="ebcd8-158">Cuando usas <xref:System.Drawing.ToolboxBitmapAttribute> para asociar un icono a su componente personalizado, el mapa de bits no aparece en el cuadro de herramientas para los componentes generados automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ebcd8-158">When you use <xref:System.Drawing.ToolboxBitmapAttribute> to associate an icon with your custom component, the bitmap does not appear in the Toolbox for autogenerated components.</span></span> <span data-ttu-id="ebcd8-159">Para ver el mapa de bits, vuelva a cargar el control con el cuadro de diálogo **Elegir elementos del cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="ebcd8-159">To see the bitmap, reload the control by using the **Choose Toolbox Items** dialog box.</span></span> <span data-ttu-id="ebcd8-160">Para obtener más información, vea [Cómo: Proporcionar un mapa de bits del cuadro de herramientas para un Control](how-to-provide-a-toolbox-bitmap-for-a-control.md).</span><span class="sxs-lookup"><span data-stu-id="ebcd8-160">For more information, see [How to: Provide a Toolbox Bitmap for a Control](how-to-provide-a-toolbox-bitmap-for-a-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebcd8-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="ebcd8-161">See also</span></span>

- [<span data-ttu-id="ebcd8-162">Desarrollar controles de formularios Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="ebcd8-162">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
- [<span data-ttu-id="ebcd8-163">Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados</span><span class="sxs-lookup"><span data-stu-id="ebcd8-163">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
- [<span data-ttu-id="ebcd8-164">Filtrar para comprobar el comportamiento de UserControl en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="ebcd8-164">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)
- [<span data-ttu-id="ebcd8-165">Tutorial: Depurar controles personalizados de formularios Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="ebcd8-165">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)
- [<span data-ttu-id="ebcd8-166">Creación de componentes</span><span class="sxs-lookup"><span data-stu-id="ebcd8-166">Component Authoring</span></span>](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/5dya64wy(v=vs.120))
- [<span data-ttu-id="ebcd8-167">Solución de problemas relacionados con el desarrollo en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="ebcd8-167">Troubleshooting Design-Time Development</span></span>](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171843(v=vs.120))
