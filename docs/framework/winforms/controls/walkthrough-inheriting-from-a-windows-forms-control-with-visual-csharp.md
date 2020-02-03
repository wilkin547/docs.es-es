---
title: Herencia de un control
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], custom controls
- inheritance [Windows Forms], control
- Windows Forms controls, inheritance
- inheritance [Windows Forms], walkthroughs
- custom controls [Windows Forms], inheritance
ms.assetid: 09476da0-8d4c-4a4c-b969-649519dfb438
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 713ccf97a73ce9684b9124a121369f22751861d0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740137"
---
# <a name="walkthrough-inherit-from-a-windows-forms-control-with-c"></a><span data-ttu-id="e6b57-102">Tutorial: heredar de un control de Windows Forms con C\#</span><span class="sxs-lookup"><span data-stu-id="e6b57-102">Walkthrough: Inherit from a Windows Forms Control with C\#</span></span>

<span data-ttu-id="e6b57-103">Con C#, puede crear controles personalizados eficaces a través de la *herencia*.</span><span class="sxs-lookup"><span data-stu-id="e6b57-103">With C#, you can create powerful custom controls through *inheritance*.</span></span> <span data-ttu-id="e6b57-104">A través de la herencia puede crear controles que conserven toda la funcionalidad inherente de controles de Windows Forms estándar y además incorporen funcionalidad personalizada.</span><span class="sxs-lookup"><span data-stu-id="e6b57-104">Through inheritance you are able to create controls that retain all of the inherent functionality of standard Windows Forms controls but also incorporate custom functionality.</span></span> <span data-ttu-id="e6b57-105">En este tutorial, creará un control heredado simple denominado `ValueButton`.</span><span class="sxs-lookup"><span data-stu-id="e6b57-105">In this walkthrough, you will create a simple inherited control called `ValueButton`.</span></span> <span data-ttu-id="e6b57-106">Este botón heredará la funcionalidad del control de <xref:System.Windows.Forms.Button> de Windows Forms estándar y expondrá una propiedad personalizada denominada `ButtonValue`.</span><span class="sxs-lookup"><span data-stu-id="e6b57-106">This button will inherit functionality from the standard Windows Forms <xref:System.Windows.Forms.Button> control, and will expose a custom property called `ButtonValue`.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="e6b57-107">Creación del proyecto</span><span class="sxs-lookup"><span data-stu-id="e6b57-107">Create the Project</span></span>

<span data-ttu-id="e6b57-108">Cuando cree un proyecto, especifique su nombre para establecer el espacio de nombres raíz, el nombre de ensamblado y el nombre del proyecto, y para asegurarse de que el componente predeterminado estará en el espacio de nombres correcto.</span><span class="sxs-lookup"><span data-stu-id="e6b57-108">When you create a new project, you specify its name in order to set the root namespace, assembly name, and project name, and to ensure that the default component will be in the correct namespace.</span></span>

### <a name="to-create-the-valuebuttonlib-control-library-and-the-valuebutton-control"></a><span data-ttu-id="e6b57-109">Para crear la biblioteca de controles ValueButtonLib y el control ValueButton</span><span class="sxs-lookup"><span data-stu-id="e6b57-109">To create the ValueButtonLib control library and the ValueButton control</span></span>

1. <span data-ttu-id="e6b57-110">En Visual Studio, cree un nuevo proyecto de **biblioteca de controles Windows Forms** y asígnele el nombre **ValueButtonLib**.</span><span class="sxs-lookup"><span data-stu-id="e6b57-110">In Visual Studio, create a new **Windows Forms Control Library** project, and name it **ValueButtonLib**.</span></span>

     <span data-ttu-id="e6b57-111">El nombre del proyecto, `ValueButtonLib` también se asigna de forma predeterminada al espacio de nombres raíz.</span><span class="sxs-lookup"><span data-stu-id="e6b57-111">The project name, `ValueButtonLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="e6b57-112">El espacio de nombres raíz se utiliza para calificar los nombres de los componentes del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e6b57-112">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="e6b57-113">Por ejemplo, si dos ensamblados proporcionan componentes denominados `ValueButton`, puede especificar su componente `ValueButton` mediante `ValueButtonLib.ValueButton`.</span><span class="sxs-lookup"><span data-stu-id="e6b57-113">For example, if two assemblies provide components named `ValueButton`, you can specify your `ValueButton` component using `ValueButtonLib.ValueButton`.</span></span> <span data-ttu-id="e6b57-114">Para más información, consulte [Espacios de nombres](../../../csharp/programming-guide/namespaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="e6b57-114">For more information, see [Namespaces](../../../csharp/programming-guide/namespaces/index.md).</span></span>

2. <span data-ttu-id="e6b57-115">En el **Explorador de soluciones**, haga clic con el botón derecho en **UserControl1.cs** y elija **Cambiar nombre** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="e6b57-115">In **Solution Explorer**, right-click **UserControl1.cs**, then choose **Rename** from the shortcut menu.</span></span> <span data-ttu-id="e6b57-116">Cambie el nombre del archivo a **ValueButton.CS**.</span><span class="sxs-lookup"><span data-stu-id="e6b57-116">Change the file name to **ValueButton.cs**.</span></span> <span data-ttu-id="e6b57-117">Haga clic en el botón **Sí** cuando se le pregunte si desea cambiar el nombre de todas las referencias al elemento de código "`UserControl1`".</span><span class="sxs-lookup"><span data-stu-id="e6b57-117">Click the **Yes** button when you are asked if you want to rename all references to the code element '`UserControl1`'.</span></span>

3. <span data-ttu-id="e6b57-118">En el **Explorador de soluciones**, haga clic con el botón derecho en **ValueButton.cs** y seleccione **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="e6b57-118">In **Solution Explorer**, right-click **ValueButton.cs** and select **View Code**.</span></span>

4. <span data-ttu-id="e6b57-119">Busque la línea de instrucción de `class`, `public partial class ValueButton`y cambie el tipo del que hereda este control de <xref:System.Windows.Forms.UserControl> a <xref:System.Windows.Forms.Button>.</span><span class="sxs-lookup"><span data-stu-id="e6b57-119">Locate the `class` statement line, `public partial class ValueButton`, and change the type from which this control inherits from <xref:System.Windows.Forms.UserControl> to <xref:System.Windows.Forms.Button>.</span></span> <span data-ttu-id="e6b57-120">Esto permite que el control heredado herede toda la funcionalidad del control <xref:System.Windows.Forms.Button>.</span><span class="sxs-lookup"><span data-stu-id="e6b57-120">This allows your inherited control to inherit all the functionality of the <xref:System.Windows.Forms.Button> control.</span></span>

5. <span data-ttu-id="e6b57-121">En el **Explorador de soluciones**, abra el nodo **ValueButton.cs** para mostrar el archivo de código generado por el diseñador, **ValueButton.Designer.cs**.</span><span class="sxs-lookup"><span data-stu-id="e6b57-121">In **Solution Explorer**, open the **ValueButton.cs** node to display the designer-generated code file, **ValueButton.Designer.cs**.</span></span> <span data-ttu-id="e6b57-122">Abra este archivo en el **Editor de código**.</span><span class="sxs-lookup"><span data-stu-id="e6b57-122">Open this file in the **Code Editor**.</span></span>

6. <span data-ttu-id="e6b57-123">Busque el método `InitializeComponent` y quite la línea que asigna la propiedad <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="e6b57-123">Locate the `InitializeComponent` method and remove the line that assigns the <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> property.</span></span> <span data-ttu-id="e6b57-124">Esta propiedad no existe en el control <xref:System.Windows.Forms.Button>.</span><span class="sxs-lookup"><span data-stu-id="e6b57-124">This property does not exist in the <xref:System.Windows.Forms.Button> control.</span></span>

7. <span data-ttu-id="e6b57-125">En el menú **Archivo**, elija **Guardar todo** para guardar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e6b57-125">From the **File** menu, choose **Save All** to save the project.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e6b57-126">Ya no hay disponible ningún diseñador visual.</span><span class="sxs-lookup"><span data-stu-id="e6b57-126">A visual designer is no longer available.</span></span> <span data-ttu-id="e6b57-127">Dado que el control <xref:System.Windows.Forms.Button> realiza su propia representación, no se puede modificar su apariencia en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="e6b57-127">Because the <xref:System.Windows.Forms.Button> control does its own painting, you are unable to modify its appearance in the designer.</span></span> <span data-ttu-id="e6b57-128">Su representación visual será exactamente la misma que la de la clase de la que hereda (es decir, <xref:System.Windows.Forms.Button>) a menos que se modifique en el código.</span><span class="sxs-lookup"><span data-stu-id="e6b57-128">Its visual representation will be exactly the same as that of the class it inherits from (that is, <xref:System.Windows.Forms.Button>) unless modified in the code.</span></span> <span data-ttu-id="e6b57-129">Todavía puede agregar componentes, que no tienen ningún elemento de interfaz de usuario, a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="e6b57-129">You can still add components, which have no UI elements, to the design surface.</span></span>

## <a name="add-a-property-to-your-inherited-control"></a><span data-ttu-id="e6b57-130">Agregar una propiedad al control heredado</span><span class="sxs-lookup"><span data-stu-id="e6b57-130">Add a Property to Your Inherited Control</span></span>

<span data-ttu-id="e6b57-131">Un uso posible de los controles de Windows Forms heredados es la creación de controles que sean idénticos en apariencia y comportamiento a los controles de Windows Forms estándar, pero que expongan propiedades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="e6b57-131">One possible use of inherited Windows Forms controls is the creation of controls that are identical in look and feel of standard Windows Forms controls, but expose custom properties.</span></span> <span data-ttu-id="e6b57-132">En esta sección, agregará una propiedad denominada `ButtonValue` al control.</span><span class="sxs-lookup"><span data-stu-id="e6b57-132">In this section, you will add a property called `ButtonValue` to your control.</span></span>

### <a name="to-add-the-value-property"></a><span data-ttu-id="e6b57-133">Para agregar la propiedad Value</span><span class="sxs-lookup"><span data-stu-id="e6b57-133">To add the Value property</span></span>

1. <span data-ttu-id="e6b57-134">En el **Explorador de soluciones**, haga clic con el botón derecho en **ValueButton.cs** y haga clic en **Ver código** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="e6b57-134">In **Solution Explorer**, right-click **ValueButton.cs**, and then click **View Code** from the shortcut menu.</span></span>

2. <span data-ttu-id="e6b57-135">Busque la instrucción `class`.</span><span class="sxs-lookup"><span data-stu-id="e6b57-135">Locate the `class` statement.</span></span> <span data-ttu-id="e6b57-136">Inmediatamente detrás de `{`, escriba el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="e6b57-136">Immediately after the `{`, type the following code:</span></span>

    ```csharp
    // Creates the private variable that will store the value of your
    // property.
    private int varValue;
    // Declares the property.
    public int ButtonValue
    {
       // Sets the method for retrieving the value of your property.
       get
       {
          return varValue;
       }
       // Sets the method for setting the value of your property.
       set
       {
          varValue = value;
       }
    }
    ```

     <span data-ttu-id="e6b57-137">Este código establece los métodos por los que se almacena y se recupera la propiedad `ButtonValue`.</span><span class="sxs-lookup"><span data-stu-id="e6b57-137">This code sets the methods by which the `ButtonValue` property is stored and retrieved.</span></span> <span data-ttu-id="e6b57-138">La instrucción `get` establece el valor devuelto en el valor que se almacena en la variable privada `varValue`, y la instrucción `set` establece el valor de la variable privada mediante la palabra clave `value`.</span><span class="sxs-lookup"><span data-stu-id="e6b57-138">The `get` statement sets the value returned to the value that is stored in the private variable `varValue`, and the `set` statement sets the value of the private variable by use of the `value` keyword.</span></span>

3. <span data-ttu-id="e6b57-139">En el menú **Archivo**, elija **Guardar todo** para guardar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e6b57-139">From the **File** menu, choose **Save All** to save the project.</span></span>

## <a name="test-the-control"></a><span data-ttu-id="e6b57-140">Prueba del control</span><span class="sxs-lookup"><span data-stu-id="e6b57-140">Test the control</span></span>

<span data-ttu-id="e6b57-141">Los controles no son proyectos independientes; deben hospedarse en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="e6b57-141">Controls are not stand-alone projects; they must be hosted in a container.</span></span> <span data-ttu-id="e6b57-142">Para probar el control, debe proporcionar un proyecto de prueba donde pueda ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="e6b57-142">In order to test your control, you must provide a test project for it to run in.</span></span> <span data-ttu-id="e6b57-143">También debe hacer que el control resulte accesible al proyecto de prueba al compilarlo.</span><span class="sxs-lookup"><span data-stu-id="e6b57-143">You must also make your control accessible to the test project by building (compiling) it.</span></span> <span data-ttu-id="e6b57-144">En esta sección, compilará el control y lo probará en Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="e6b57-144">In this section, you will build your control and test it in a Windows Form.</span></span>

### <a name="to-build-your-control"></a><span data-ttu-id="e6b57-145">Para compilar el control</span><span class="sxs-lookup"><span data-stu-id="e6b57-145">To build your control</span></span>

<span data-ttu-id="e6b57-146">En el menú **Compilar**, haga clic en **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="e6b57-146">On the **Build** menu, click **Build Solution**.</span></span> <span data-ttu-id="e6b57-147">La compilación debería completarse correctamente sin advertencias ni errores del compilador.</span><span class="sxs-lookup"><span data-stu-id="e6b57-147">The build should be successful with no compiler errors or warnings.</span></span>

### <a name="to-create-a-test-project"></a><span data-ttu-id="e6b57-148">Para crear un proyecto de prueba</span><span class="sxs-lookup"><span data-stu-id="e6b57-148">To create a test project</span></span>

1. <span data-ttu-id="e6b57-149">En el menú **Archivo**, elija **Agregar** y haga clic en **Nuevo proyecto** para abrir el cuadro de diálogo **Agregar nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="e6b57-149">On the **File** menu, point to **Add** and then click **New Project** to open the **Add New Project** dialog box.</span></span>

2. <span data-ttu-id="e6b57-150">Seleccione el nodo **Windows**, debajo del nodo **Visual C#** , y haga clic en **Aplicación de Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="e6b57-150">Select the **Windows** node, beneath the **Visual C#** node, and click **Windows Forms Application**.</span></span>

3. <span data-ttu-id="e6b57-151">En el cuadro **nombre** , escriba **prueba**.</span><span class="sxs-lookup"><span data-stu-id="e6b57-151">In the **Name** box, enter **Test**.</span></span>

4. <span data-ttu-id="e6b57-152">En el **Explorador de soluciones**, haga clic con el botón derecho en el nodo **Referencias** para su proyecto de prueba y seleccione **Agregar referencia** en el menú contextual para mostrar el cuadro de diálogo **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="e6b57-152">In **Solution Explorer**, right-click the **References** node for your test project, then select **Add Reference** from the shortcut menu to display the **Add Reference** dialog box.</span></span>

5. <span data-ttu-id="e6b57-153">Haga clic en la pestaña etiquetada como **Proyectos**.</span><span class="sxs-lookup"><span data-stu-id="e6b57-153">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="e6b57-154">El proyecto ValueButtonLib aparecerá en nombre del **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="e6b57-154">Your ValueButtonLib project will be listed under **Project Name**.</span></span> <span data-ttu-id="e6b57-155">Haga doble clic en el proyecto para agregar la referencia al proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="e6b57-155">Double-click the project to add the reference to the test project.</span></span>

6. <span data-ttu-id="e6b57-156">En el **Explorador de soluciones**, haga clic con el botón derecho en **Probar** y seleccione **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="e6b57-156">In **Solution Explorer,** right-click **Test** and select **Build**.</span></span>

### <a name="to-add-your-control-to-the-form"></a><span data-ttu-id="e6b57-157">Para agregar el control al formulario</span><span class="sxs-lookup"><span data-stu-id="e6b57-157">To add your control to the form</span></span>

1. <span data-ttu-id="e6b57-158">En el **Explorador de soluciones**, haga clic con el botón derecho en **Form1.cs** y elija **Ver diseñador** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="e6b57-158">In **Solution Explorer**, right-click **Form1.cs** and choose **View Designer** from the shortcut menu.</span></span>

2. <span data-ttu-id="e6b57-159">En el **cuadro de herramientas**, seleccione **los componentes de ValueButtonLib**.</span><span class="sxs-lookup"><span data-stu-id="e6b57-159">In the **Toolbox**, select **ValueButtonLib Components**.</span></span> <span data-ttu-id="e6b57-160">Haga doble clic en **ValueButton**.</span><span class="sxs-lookup"><span data-stu-id="e6b57-160">Double-click **ValueButton**.</span></span>

     <span data-ttu-id="e6b57-161">Aparece un componente **ValueButton** en el formulario.</span><span class="sxs-lookup"><span data-stu-id="e6b57-161">A **ValueButton** appears on the form.</span></span>

3. <span data-ttu-id="e6b57-162">Haga clic con el botón derecho en **ValueButton** y seleccione **Propiedades** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="e6b57-162">Right-click the **ValueButton** and select **Properties** from the shortcut menu.</span></span>

4. <span data-ttu-id="e6b57-163">En la ventana **Propiedades**, examine las propiedades de este control.</span><span class="sxs-lookup"><span data-stu-id="e6b57-163">In the **Properties** window, examine the properties of this control.</span></span> <span data-ttu-id="e6b57-164">Tenga en cuenta que son idénticas a las propiedades expuestas por un botón estándar, salvo que hay una propiedad adicional, ButtonValue.</span><span class="sxs-lookup"><span data-stu-id="e6b57-164">Note that they are identical to the properties exposed by a standard button, except that there is an additional property, ButtonValue.</span></span>

5. <span data-ttu-id="e6b57-165">Establezca la propiedad **ButtonValue** en **5**.</span><span class="sxs-lookup"><span data-stu-id="e6b57-165">Set the **ButtonValue** property to **5**.</span></span>

6. <span data-ttu-id="e6b57-166">En la pestaña **todos los Windows Forms** del **cuadro de herramientas**, haga doble clic en **etiqueta** para agregar un control de <xref:System.Windows.Forms.Label> al formulario.</span><span class="sxs-lookup"><span data-stu-id="e6b57-166">In the **All Windows Forms** tab of the **Toolbox**, double-click **Label** to add a <xref:System.Windows.Forms.Label> control to your form.</span></span>

7. <span data-ttu-id="e6b57-167">Mueva la etiqueta al centro del formulario.</span><span class="sxs-lookup"><span data-stu-id="e6b57-167">Relocate the label to the center of the form.</span></span>

8. <span data-ttu-id="e6b57-168">Haga doble clic en `valueButton1`.</span><span class="sxs-lookup"><span data-stu-id="e6b57-168">Double-click `valueButton1`.</span></span>

     <span data-ttu-id="e6b57-169">Se abre el **Editor de código** en el evento `valueButton1_Click`.</span><span class="sxs-lookup"><span data-stu-id="e6b57-169">The **Code Editor** opens to the `valueButton1_Click` event.</span></span>

9. <span data-ttu-id="e6b57-170">Inserte la siguiente línea de código.</span><span class="sxs-lookup"><span data-stu-id="e6b57-170">Insert the following line of code.</span></span>

    ```csharp
    label1.Text = valueButton1.ButtonValue.ToString();
    ```

10. <span data-ttu-id="e6b57-171">En el **Explorador de soluciones**, haga clic con el botón derecho en **Probar** y elija **Establecer como proyecto de inicio** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="e6b57-171">In **Solution Explorer**, right-click **Test**, and choose **Set as Startup Project** from the shortcut menu.</span></span>

11. <span data-ttu-id="e6b57-172">En el menú **Depurar**, seleccione **Iniciar depuración**.</span><span class="sxs-lookup"><span data-stu-id="e6b57-172">From the **Debug** menu, select **Start Debugging**.</span></span>

     <span data-ttu-id="e6b57-173">Aparece `Form1`.</span><span class="sxs-lookup"><span data-stu-id="e6b57-173">`Form1` appears.</span></span>

12. <span data-ttu-id="e6b57-174">Haga clic en `valueButton1`.</span><span class="sxs-lookup"><span data-stu-id="e6b57-174">Click `valueButton1`.</span></span>

     <span data-ttu-id="e6b57-175">Se muestra el número "5" en `label1`, lo que demuestra que la propiedad `ButtonValue` del control heredado se ha pasado a `label1` a través del método `valueButton1_Click`.</span><span class="sxs-lookup"><span data-stu-id="e6b57-175">The numeral '5' is displayed in `label1`, demonstrating that the `ButtonValue` property of your inherited control has been passed to `label1` through the `valueButton1_Click` method.</span></span> <span data-ttu-id="e6b57-176">Por lo tanto, su control `ValueButton` hereda toda la funcionalidad del botón estándar de Windows Forms, pero expone una propiedad personalizada adicional.</span><span class="sxs-lookup"><span data-stu-id="e6b57-176">Thus your `ValueButton` control inherits all the functionality of the standard Windows Forms button, but exposes an additional, custom property.</span></span>

## <a name="see-also"></a><span data-ttu-id="e6b57-177">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e6b57-177">See also</span></span>

- [<span data-ttu-id="e6b57-178">Cómo: Mostrar un control en el cuadro de diálogo Elegir elementos de cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="e6b57-178">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)
- [<span data-ttu-id="e6b57-179">Tutorial: Crear un control compuesto con Visual C#</span><span class="sxs-lookup"><span data-stu-id="e6b57-179">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
