---
title: 'Tutorial: Heredar de un control de formularios Windows Forms con Visual Basic'
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- inheritance [Windows Forms], custom controls
- inheritance [Windows Forms], control
- Windows Forms controls, inheritance
- inheritance [Windows Forms], walkthroughs
- custom controls [Windows Forms], inheritance
ms.assetid: fb58d7c8-b702-4478-ad31-b00cae118882
ms.openlocfilehash: 378d7b0c67791e6c48e9859e0546594df3ccc85e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931012"
---
# <a name="walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic"></a><span data-ttu-id="16348-102">Tutorial: Heredar de un control de formularios Windows Forms con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="16348-102">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>
<span data-ttu-id="16348-103">Con Visual Basic, puede crear controles personalizados eficaces a través de la *herencia*.</span><span class="sxs-lookup"><span data-stu-id="16348-103">With Visual Basic, you can create powerful custom controls through *inheritance*.</span></span> <span data-ttu-id="16348-104">A través de la herencia puede crear controles que conserven toda la funcionalidad inherente de controles de Windows Forms estándar y además incorporen funcionalidad personalizada.</span><span class="sxs-lookup"><span data-stu-id="16348-104">Through inheritance you are able to create controls that retain all of the inherent functionality of standard Windows Forms controls but also incorporate custom functionality.</span></span> <span data-ttu-id="16348-105">En este tutorial, creará un control heredado simple denominado `ValueButton`.</span><span class="sxs-lookup"><span data-stu-id="16348-105">In this walkthrough, you will create a simple inherited control called `ValueButton`.</span></span> <span data-ttu-id="16348-106">Este botón heredará la funcionalidad del control de <xref:System.Windows.Forms.Button> Windows Forms estándar y expondrá una propiedad personalizada denominada `ButtonValue`.</span><span class="sxs-lookup"><span data-stu-id="16348-106">This button will inherit functionality from the standard Windows Forms <xref:System.Windows.Forms.Button> control, and will expose a custom property called `ButtonValue`.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="16348-107">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="16348-107">Creating the Project</span></span>
 <span data-ttu-id="16348-108">Cuando cree un proyecto, especifique su nombre para establecer el espacio de nombres raíz, el nombre de ensamblado y el nombre del proyecto, y para asegurarse de que el componente predeterminado estará en el espacio de nombres correcto.</span><span class="sxs-lookup"><span data-stu-id="16348-108">When you create a new project, you specify its name in order to set the root namespace, assembly name, and project name, and to ensure that the default component will be in the correct namespace.</span></span>

### <a name="to-create-the-valuebuttonlib-control-library-and-the-valuebutton-control"></a><span data-ttu-id="16348-109">Para crear la biblioteca de controles ValueButtonLib y el control ValueButton</span><span class="sxs-lookup"><span data-stu-id="16348-109">To create the ValueButtonLib control library and the ValueButton control</span></span>

1. <span data-ttu-id="16348-110">En el menú **Archivo**, elija **Nuevo** y haga clic en **Proyecto** para abrir el cuadro de diálogo **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="16348-110">On the **File** menu, point to **New** and then click **Project** to open the **New Project** dialog box.</span></span>

2. <span data-ttu-id="16348-111">Seleccione la plantilla de proyecto **Windows Forms biblioteca de controles** en la lista de proyectos de Visual Basic `ValueButtonLib` y escriba en el cuadro **nombre** .</span><span class="sxs-lookup"><span data-stu-id="16348-111">Select the **Windows Forms Control Library** project template from the list of Visual Basic projects, and type `ValueButtonLib` in the **Name** box.</span></span>

     <span data-ttu-id="16348-112">El nombre del proyecto, `ValueButtonLib` también se asigna de forma predeterminada al espacio de nombres raíz.</span><span class="sxs-lookup"><span data-stu-id="16348-112">The project name, `ValueButtonLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="16348-113">El espacio de nombres raíz se utiliza para calificar los nombres de los componentes del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="16348-113">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="16348-114">Por ejemplo, si dos ensamblados proporcionan componentes denominados `ValueButton`, puede especificar su componente `ValueButton` mediante `ValueButtonLib.ValueButton`.</span><span class="sxs-lookup"><span data-stu-id="16348-114">For example, if two assemblies provide components named `ValueButton`, you can specify your `ValueButton` component using `ValueButtonLib.ValueButton`.</span></span> <span data-ttu-id="16348-115">Para más información, consulte [Espacios de nombres en Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="16348-115">For more information, see [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).</span></span>

3. <span data-ttu-id="16348-116">En el **Explorador de soluciones**, haga clic con el botón derecho en **UserControl1.vb** y elija **Cambiar nombre** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="16348-116">In **Solution Explorer**, right-click **UserControl1.vb**, then choose **Rename** from the shortcut menu.</span></span> <span data-ttu-id="16348-117">Cambie el nombre del archivo a `ValueButton.vb`.</span><span class="sxs-lookup"><span data-stu-id="16348-117">Change the file name to `ValueButton.vb`.</span></span> <span data-ttu-id="16348-118">Haga clic en el botón **Sí** cuando se le pregunte si desea cambiar el nombre de todas las referencias al elemento de código "UserControl1".</span><span class="sxs-lookup"><span data-stu-id="16348-118">Click the **Yes** button when you are asked if you want to rename all references to the code element 'UserControl1'.</span></span>

4. <span data-ttu-id="16348-119">En el **Explorador de soluciones**, haga clic en el botón **Mostrar todos los archivos**.</span><span class="sxs-lookup"><span data-stu-id="16348-119">In **Solution Explorer**, click the **Show All Files** button.</span></span>

5. <span data-ttu-id="16348-120">Abra el nodo **ValueButton.vb** para mostrar el archivo de código generado por el diseñador, **ValueButton.Designer.vb**.</span><span class="sxs-lookup"><span data-stu-id="16348-120">Open the **ValueButton.vb** node to display the designer-generated code file, **ValueButton.Designer.vb**.</span></span> <span data-ttu-id="16348-121">Abra este archivo en el **Editor de código**.</span><span class="sxs-lookup"><span data-stu-id="16348-121">Open this file in the **Code Editor**.</span></span>

6. <span data-ttu-id="16348-122">Busque la `Class` instrucción, `Partial Public Class ValueButton`, y cambie el tipo del que este <xref:System.Windows.Forms.Button>control hereda de <xref:System.Windows.Forms.UserControl> .</span><span class="sxs-lookup"><span data-stu-id="16348-122">Locate the `Class` statement, `Partial Public Class ValueButton`, and change the type from which this control inherits from <xref:System.Windows.Forms.UserControl> to <xref:System.Windows.Forms.Button>.</span></span> <span data-ttu-id="16348-123">Esto permite que el control heredado herede toda la funcionalidad del <xref:System.Windows.Forms.Button> control.</span><span class="sxs-lookup"><span data-stu-id="16348-123">This allows your inherited control to inherit all the functionality of the <xref:System.Windows.Forms.Button> control.</span></span>

7. <span data-ttu-id="16348-124">Busque el `InitializeComponent` método y quite la línea que asigna la <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="16348-124">Locate the `InitializeComponent` method and remove the line that assigns the <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> property.</span></span> <span data-ttu-id="16348-125">Esta propiedad no existe en el <xref:System.Windows.Forms.Button> control.</span><span class="sxs-lookup"><span data-stu-id="16348-125">This property does not exist in the <xref:System.Windows.Forms.Button> control.</span></span>

8. <span data-ttu-id="16348-126">En el menú **Archivo**, elija **Guardar todo** para guardar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="16348-126">From the **File** menu, choose **Save All** to save the project.</span></span>

     <span data-ttu-id="16348-127">Tenga en cuenta que ya no hay disponible ningún diseñador visual.</span><span class="sxs-lookup"><span data-stu-id="16348-127">Note that a visual designer is no longer available.</span></span> <span data-ttu-id="16348-128">Dado que <xref:System.Windows.Forms.Button> el control realiza su propia representación, no se puede modificar su apariencia en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="16348-128">Because the <xref:System.Windows.Forms.Button> control does its own painting, you are unable to modify its appearance in the designer.</span></span> <span data-ttu-id="16348-129">Su representación visual será exactamente la misma que la de la clase de la que hereda (es decir, <xref:System.Windows.Forms.Button>) a menos que se modifique en el código.</span><span class="sxs-lookup"><span data-stu-id="16348-129">Its visual representation will be exactly the same as that of the class it inherits from (that is, <xref:System.Windows.Forms.Button>) unless modified in the code.</span></span>

> [!NOTE]
> <span data-ttu-id="16348-130">Todavía puede agregar componentes, que no tienen ningún elemento de interfaz de usuario, a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="16348-130">You can still add components, which have no UI elements, to the design surface.</span></span>

## <a name="adding-a-property-to-your-inherited-control"></a><span data-ttu-id="16348-131">Agregar una propiedad al control heredado</span><span class="sxs-lookup"><span data-stu-id="16348-131">Adding a Property to Your Inherited Control</span></span>
 <span data-ttu-id="16348-132">Un uso posible de los controles de Windows Forms heredados es la creación de controles que sean idénticos en apariencia y comportamiento a los controles de Windows Forms estándar, pero que expongan propiedades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="16348-132">One possible use of inherited Windows Forms controls is the creation of controls that are identical in appearance and behavior (look and feel) to standard Windows Forms controls, but expose custom properties.</span></span> <span data-ttu-id="16348-133">En esta sección, agregará una propiedad denominada `ButtonValue` al control.</span><span class="sxs-lookup"><span data-stu-id="16348-133">In this section, you will add a property called `ButtonValue` to your control.</span></span>

### <a name="to-add-the-value-property"></a><span data-ttu-id="16348-134">Para agregar la propiedad Value</span><span class="sxs-lookup"><span data-stu-id="16348-134">To add the Value property</span></span>

1. <span data-ttu-id="16348-135">En el **Explorador de soluciones**, haga clic con el botón derecho en **ValueButton.vb** y haga clic en **Ver código** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="16348-135">In **Solution Explorer**, right-click **ValueButton.vb**, and then click **View Code** from the shortcut menu.</span></span>

2. <span data-ttu-id="16348-136">Busque la instrucción `Public Class ValueButton`.</span><span class="sxs-lookup"><span data-stu-id="16348-136">Locate the `Public Class ValueButton` statement.</span></span> <span data-ttu-id="16348-137">Justo debajo de esta declaración, escriba el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="16348-137">Immediately beneath this statement, type the following code:</span></span>

    ```vb
    ' Creates the private variable that will store the value of your
    ' property.
    Private varValue as integer
    ' Declares the property.
    Property ButtonValue() as Integer
    ' Sets the method for retrieving the value of your property.
       Get
          Return varValue
       End Get
    ' Sets the method for setting the value of your property.
       Set(ByVal Value as Integer)
          varValue = Value
       End Set
    End Property
    ```

     <span data-ttu-id="16348-138">Este código establece los métodos por los que se almacena y se recupera la propiedad `ButtonValue`.</span><span class="sxs-lookup"><span data-stu-id="16348-138">This code sets the methods by which the `ButtonValue` property is stored and retrieved.</span></span> <span data-ttu-id="16348-139">La instrucción `Get` establece el valor devuelto en el valor que se almacena en la variable privada `varValue`, y la instrucción `Set` establece el valor de la variable privada mediante la palabra clave `Value`.</span><span class="sxs-lookup"><span data-stu-id="16348-139">The `Get` statement sets the value returned to the value that is stored in the private variable `varValue`, and the `Set` statement sets the value of the private variable by use of the `Value` keyword.</span></span>

3. <span data-ttu-id="16348-140">En el menú **Archivo**, elija **Guardar todo** para guardar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="16348-140">From the **File** menu, choose **Save All** to save the project.</span></span>

## <a name="testing-your-control"></a><span data-ttu-id="16348-141">Probar el control</span><span class="sxs-lookup"><span data-stu-id="16348-141">Testing Your Control</span></span>
 <span data-ttu-id="16348-142">Los controles no son proyectos independientes; deben hospedarse en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="16348-142">Controls are not stand-alone projects; they must be hosted in a container.</span></span> <span data-ttu-id="16348-143">Para probar el control, debe proporcionar un proyecto de prueba donde pueda ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="16348-143">In order to test your control, you must provide a test project for it to run in.</span></span> <span data-ttu-id="16348-144">También debe hacer que el control resulte accesible al proyecto de prueba al compilarlo.</span><span class="sxs-lookup"><span data-stu-id="16348-144">You must also make your control accessible to the test project by building (compiling) it.</span></span> <span data-ttu-id="16348-145">En esta sección, compilará el control y lo probará en Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="16348-145">In this section, you will build your control and test it in a Windows Form.</span></span>

### <a name="to-build-your-control"></a><span data-ttu-id="16348-146">Para compilar el control</span><span class="sxs-lookup"><span data-stu-id="16348-146">To build your control</span></span>

1. <span data-ttu-id="16348-147">En el menú **Compilar** , haga clic en **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="16348-147">On the **Build** menu, click **Build Solution**.</span></span>

     <span data-ttu-id="16348-148">La compilación debería completarse correctamente sin advertencias ni errores del compilador.</span><span class="sxs-lookup"><span data-stu-id="16348-148">The build should be successful with no compiler errors or warnings.</span></span>

### <a name="to-create-a-test-project"></a><span data-ttu-id="16348-149">Para crear un proyecto de prueba</span><span class="sxs-lookup"><span data-stu-id="16348-149">To create a test project</span></span>

1. <span data-ttu-id="16348-150">En el menú **Archivo**, elija **Agregar** y haga clic en **Nuevo proyecto** para abrir el cuadro de diálogo **Agregar nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="16348-150">On the **File** menu, point to **Add** and then click **New Project** to open the **Add New Project** dialog box.</span></span>

2. <span data-ttu-id="16348-151">Seleccione el nodo proyectos de Visual Basic y haga clic en **Windows Forms aplicación**.</span><span class="sxs-lookup"><span data-stu-id="16348-151">Select the Visual Basic projects node, and click **Windows Forms Application**.</span></span>

3. <span data-ttu-id="16348-152">En el cuadro **Nombre**, escriba `Test`.</span><span class="sxs-lookup"><span data-stu-id="16348-152">In the **Name** box, type `Test`.</span></span>

4. <span data-ttu-id="16348-153">En el **Explorador de soluciones**, haga clic en el botón **Mostrar todos los archivos**.</span><span class="sxs-lookup"><span data-stu-id="16348-153">In **Solution Explorer**, click the **Show All Files** button.</span></span>

5. <span data-ttu-id="16348-154">En el **Explorador de soluciones**, haga clic con el botón derecho en el nodo **Referencias** para su proyecto de prueba y seleccione **Agregar referencia** en el menú contextual para mostrar el cuadro de diálogo **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="16348-154">In **Solution Explorer**, right-click the **References** node for your test project, then select **Add Reference** from the shortcut menu to display the **Add Reference** dialog box.</span></span>

6. <span data-ttu-id="16348-155">Haga clic en la pestaña **Proyectos**.</span><span class="sxs-lookup"><span data-stu-id="16348-155">Click the **Projects** tab.</span></span>

7. <span data-ttu-id="16348-156">Haga clic en la pestaña etiquetada como **Proyectos**.</span><span class="sxs-lookup"><span data-stu-id="16348-156">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="16348-157">El proyecto `ValueButtonLib` aparecerá bajo **Nombre de proyecto**.</span><span class="sxs-lookup"><span data-stu-id="16348-157">Your `ValueButtonLib` project will be listed under **Project Name**.</span></span> <span data-ttu-id="16348-158">Haga doble clic en el proyecto para agregar la referencia al proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="16348-158">Double-click the project to add the reference to the test project.</span></span>

8. <span data-ttu-id="16348-159">En el **Explorador de soluciones**, haga clic con el botón derecho en **Probar** y seleccione **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="16348-159">In **Solution Explorer,** right-click **Test** and select **Build**.</span></span>

### <a name="to-add-your-control-to-the-form"></a><span data-ttu-id="16348-160">Para agregar el control al formulario</span><span class="sxs-lookup"><span data-stu-id="16348-160">To add your control to the form</span></span>

1. <span data-ttu-id="16348-161">En el **Explorador de soluciones**, haga clic con el botón derecho en **Form1.vb** y elija **Ver diseñador** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="16348-161">In **Solution Explorer**, right-click **Form1.vb** and choose **View Designer** from the shortcut menu.</span></span>

2. <span data-ttu-id="16348-162">En el **cuadro de herramientas**, haga clic en **Componentes de ValueButtonLib**.</span><span class="sxs-lookup"><span data-stu-id="16348-162">In the **Toolbox**, click **ValueButtonLib Components**.</span></span> <span data-ttu-id="16348-163">Haga doble clic en **ValueButton**.</span><span class="sxs-lookup"><span data-stu-id="16348-163">Double-click **ValueButton**.</span></span>

     <span data-ttu-id="16348-164">Aparece un componente **ValueButton** en el formulario.</span><span class="sxs-lookup"><span data-stu-id="16348-164">A **ValueButton** appears on the form.</span></span>

3. <span data-ttu-id="16348-165">Haga clic con el botón derecho en **ValueButton** y seleccione **Propiedades** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="16348-165">Right-click the **ValueButton** and select **Properties** from the shortcut menu.</span></span>

4. <span data-ttu-id="16348-166">En la ventana **Propiedades**, examine las propiedades de este control.</span><span class="sxs-lookup"><span data-stu-id="16348-166">In the **Properties** window, examine the properties of this control.</span></span> <span data-ttu-id="16348-167">Observe que son idénticas a las propiedades expuestas por un botón estándar, excepto en que hay una propiedad adicional, `ButtonValue`.</span><span class="sxs-lookup"><span data-stu-id="16348-167">Note that they are identical to the properties exposed by a standard button, except that there is an additional property, `ButtonValue`.</span></span>

5. <span data-ttu-id="16348-168">Establezca la propiedad `ButtonValue` en `5`.</span><span class="sxs-lookup"><span data-stu-id="16348-168">Set the `ButtonValue` property to `5`.</span></span>

6. <span data-ttu-id="16348-169">En la pestaña **todos los Windows Forms** del **cuadro de herramientas**, haga doble clic en **etiqueta** para agregar un <xref:System.Windows.Forms.Label> control al formulario.</span><span class="sxs-lookup"><span data-stu-id="16348-169">On the **All Windows Forms** tab of the **Toolbox**, double-click **Label** to add a <xref:System.Windows.Forms.Label> control to your form.</span></span>

7. <span data-ttu-id="16348-170">Mueva la etiqueta al centro del formulario.</span><span class="sxs-lookup"><span data-stu-id="16348-170">Relocate the label to the center of the form.</span></span>

8. <span data-ttu-id="16348-171">Haga doble clic en `ValueButton1`.</span><span class="sxs-lookup"><span data-stu-id="16348-171">Double-click `ValueButton1`.</span></span>

     <span data-ttu-id="16348-172">Se abre el **Editor de código** en el evento `ValueButton1_Click`.</span><span class="sxs-lookup"><span data-stu-id="16348-172">The **Code Editor** opens to the `ValueButton1_Click` event.</span></span>

9. <span data-ttu-id="16348-173">Escriba la siguiente línea de código.</span><span class="sxs-lookup"><span data-stu-id="16348-173">Type the following line of code.</span></span>

    ```vb
    Label1.Text = CStr(ValueButton1.ButtonValue)
    ```

10. <span data-ttu-id="16348-174">En el **Explorador de soluciones**, haga clic con el botón derecho en **Probar** y elija **Establecer como proyecto de inicio** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="16348-174">In **Solution Explorer**, right-click **Test**, and choose **Set as Startup Project** from the shortcut menu.</span></span>

11. <span data-ttu-id="16348-175">En el menú **Depurar**, seleccione **Iniciar depuración**.</span><span class="sxs-lookup"><span data-stu-id="16348-175">From the **Debug** menu, select **Start Debugging**.</span></span>

     <span data-ttu-id="16348-176">Aparece `Form1`.</span><span class="sxs-lookup"><span data-stu-id="16348-176">`Form1` appears.</span></span>

12. <span data-ttu-id="16348-177">Haga clic en `Valuebutton1`.</span><span class="sxs-lookup"><span data-stu-id="16348-177">Click `Valuebutton1`.</span></span>

     <span data-ttu-id="16348-178">Se muestra el número "5" en `Label1`, lo que demuestra que la propiedad `ButtonValue` del control heredado se ha pasado a `Label1` a través del método `ValueButton1_Click`.</span><span class="sxs-lookup"><span data-stu-id="16348-178">The numeral '5' is displayed in `Label1`, demonstrating that the `ButtonValue` property of your inherited control has been passed to `Label1` through the `ValueButton1_Click` method.</span></span> <span data-ttu-id="16348-179">Por lo tanto, su control `ValueButton` hereda toda la funcionalidad del botón estándar de Windows Forms, pero expone una propiedad personalizada adicional.</span><span class="sxs-lookup"><span data-stu-id="16348-179">Thus your `ValueButton` control inherits all the functionality of the standard Windows Forms button, but exposes an additional, custom property.</span></span>

## <a name="see-also"></a><span data-ttu-id="16348-180">Vea también</span><span class="sxs-lookup"><span data-stu-id="16348-180">See also</span></span>

- [<span data-ttu-id="16348-181">Tutorial: Crear un control compuesto con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="16348-181">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](walkthrough-authoring-a-composite-control-with-visual-basic.md)
- [<span data-ttu-id="16348-182">Cómo: Mostrar un control en el cuadro de diálogo Elegir elementos del cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="16348-182">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)
- [<span data-ttu-id="16348-183">Desarrollar controles personalizados de Windows Forms con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="16348-183">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="16348-184">Fundamentos de la herencia (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16348-184">Inheritance basics (Visual Basic)</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
