---
title: 'Tutorial: Demostración de la herencia visual'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- form inheritance [Windows Forms], walkthroughs
- visual inheritance
- inheritance [Windows Forms], walkthroughs
- walkthroughs [Windows Forms], visual inheritance
- Windows Forms, inheritance
ms.assetid: 01966086-3142-450e-8210-3fd4cb33f591
ms.openlocfilehash: 6fd504269ae9afbfd02b58276582a644674e1e0f
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040318"
---
# <a name="walkthrough-demonstrating-visual-inheritance"></a><span data-ttu-id="fb2fc-102">Tutorial: Demostración de la herencia visual</span><span class="sxs-lookup"><span data-stu-id="fb2fc-102">Walkthrough: Demonstrating Visual Inheritance</span></span>

<span data-ttu-id="fb2fc-103">La herencia visual le permite ver los controles del formulario base y agregar controles nuevos.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-103">Visual inheritance enables you to see the controls on the base form and to add new controls.</span></span> <span data-ttu-id="fb2fc-104">En este tutorial, creará un formulario base y lo compilará para convertirlo en una biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-104">In this walkthrough you will create a base form and compile it into a class library.</span></span> <span data-ttu-id="fb2fc-105">Importará la biblioteca de clases en otro proyecto y creará un nuevo formulario que herede del formulario base.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-105">You will import this class library into another project and create a new form that inherits from the base form.</span></span> <span data-ttu-id="fb2fc-106">Durante este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="fb2fc-106">During this walkthrough, you will learn how to:</span></span>

- <span data-ttu-id="fb2fc-107">Crear un proyecto de biblioteca de clases que contiene un formulario base.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-107">Create a class library project containing a base form.</span></span>

- <span data-ttu-id="fb2fc-108">Agregar un botón con propiedades que las clases derivadas del formulario base pueden modificar.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-108">Add a button with properties that derived classes of the base form can modify.</span></span>

- <span data-ttu-id="fb2fc-109">Agregar un botón que los herederos del formulario base no pueden modificar.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-109">Add a button that cannot be modified by inheritors of the base form.</span></span>

- <span data-ttu-id="fb2fc-110">Crear un proyecto que contiene un formulario que hereda de `BaseForm`.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-110">Create a project containing a form that inherits from `BaseForm`.</span></span>

<span data-ttu-id="fb2fc-111">Por último, en este tutorial se mostrará la diferencia entre los controles privados y los protegidos de un formulario heredado.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-111">Ultimately, this walkthrough will demonstrate the difference between private and protected controls on an inherited form.</span></span>

> [!CAUTION]
> <span data-ttu-id="fb2fc-112">No todos los controles admiten la herencia visual a partir de un formulario base.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-112">Not all controls support visual inheritance from a base form.</span></span> <span data-ttu-id="fb2fc-113">Los siguientes controles no admiten el escenario que se describe en este tutorial:</span><span class="sxs-lookup"><span data-stu-id="fb2fc-113">The following controls do not support the scenario described in this walkthrough:</span></span>
>
>  <xref:System.Windows.Forms.WebBrowser>
>
>  <xref:System.Windows.Forms.ToolStrip>
>
>  <xref:System.Windows.Forms.ToolStripPanel>
>
>  <xref:System.Windows.Forms.TableLayoutPanel>
>
>  <xref:System.Windows.Forms.FlowLayoutPanel>
>
>  <xref:System.Windows.Forms.DataGridView>
>
>  <span data-ttu-id="fb2fc-114">Estos controles del formulario heredado siempre son de solo lectura, independientemente de los modificadores que utilice (`private`, `protected` o `public`).</span><span class="sxs-lookup"><span data-stu-id="fb2fc-114">These controls in the inherited form are always read-only regardless of the modifiers you use (`private`, `protected`, or `public`).</span></span>

## <a name="create-a-class-library-project-containing-a-base-form"></a><span data-ttu-id="fb2fc-115">Crear un proyecto de biblioteca de clases que contenga un formulario base</span><span class="sxs-lookup"><span data-stu-id="fb2fc-115">Create a class library project containing a base form</span></span>

1. <span data-ttu-id="fb2fc-116">En Visual Studio, en el menú **archivo** , elija **nuevo** > **proyecto** para abrir el cuadro de diálogo **nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="fb2fc-116">In Visual Studio, from the **File** menu, choose **New** > **Project** to open the **New Project** dialog box.</span></span>

2. <span data-ttu-id="fb2fc-117">Cree una aplicación de Windows Forms `BaseFormLibrary`denominada.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-117">Create a Windows Forms application named `BaseFormLibrary`.</span></span>

3. <span data-ttu-id="fb2fc-118">Para crear una biblioteca de clases en lugar de una aplicación de Windows Forms estándar, en **Explorador de soluciones**, haga clic con el botón secundario en el nodo del proyecto **BaseFormLibrary** y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-118">To create a class library instead of a standard Windows Forms application, in **Solution Explorer**, right-click the **BaseFormLibrary** project node and then select **Properties**.</span></span>

4. <span data-ttu-id="fb2fc-119">En las propiedades del proyecto, cambie el **tipo de salida** de **aplicación Windows** a **biblioteca de clases**.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-119">In the properties for the project, change the **Output type** from **Windows Application** to **Class Library**.</span></span>

5. <span data-ttu-id="fb2fc-120">En el menú **archivo** , elija **guardar todo** para guardar el proyecto y los archivos en la ubicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-120">From the **File** menu, choose **Save All** to save the project and files to the default location.</span></span>

 <span data-ttu-id="fb2fc-121">Los dos procedimientos siguientes agregan botones al formulario base.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-121">The next two procedures add buttons to the base form.</span></span> <span data-ttu-id="fb2fc-122">Para ilustrar la herencia visual, proporcionará a los botones distintos niveles de acceso estableciendo sus propiedades `Modifiers`.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-122">To demonstrate visual inheritance, you will give the buttons different access levels by setting their `Modifiers` properties.</span></span>

## <a name="add-a-button-that-inheritors-of-the-base-form-can-modify"></a><span data-ttu-id="fb2fc-123">Agregar un botón que los herederos del formulario base pueden modificar</span><span class="sxs-lookup"><span data-stu-id="fb2fc-123">Add a button that inheritors of the base form can modify</span></span>

1. <span data-ttu-id="fb2fc-124">Abra **Form1** en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-124">Open **Form1** in the designer.</span></span>

2. <span data-ttu-id="fb2fc-125">En la pestaña **todos los Windows Forms** del **cuadro de herramientas**, haga doble clic en el **botón** para agregar un botón al formulario.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-125">On the **All Windows Forms** tab of the **Toolbox**, double-click **Button** to add a button to the form.</span></span> <span data-ttu-id="fb2fc-126">Use el mouse para colocar y cambiar de tamaño el botón.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-126">Use the mouse to position and resize the button.</span></span>

3. <span data-ttu-id="fb2fc-127">En la ventana Propiedades, establezca las propiedades siguientes del botón:</span><span class="sxs-lookup"><span data-stu-id="fb2fc-127">In the Properties window, set the following properties of the button:</span></span>

    - <span data-ttu-id="fb2fc-128">Establezca la propiedad **Text** en **Hello**.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-128">Set the **Text** property to **Say Hello**.</span></span>

    - <span data-ttu-id="fb2fc-129">Establezca la propiedad **(Name)** en **btnProtected**.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-129">Set the **(Name)** property to **btnProtected**.</span></span>

    - <span data-ttu-id="fb2fc-130">Establezca la propiedad Modifiers en **Protected**.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-130">Set the **Modifiers** property to **Protected**.</span></span> <span data-ttu-id="fb2fc-131">Esto hace posible que los formularios que heredan de **Form1** modifiquen las propiedades de **btnProtected**.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-131">This makes it possible for forms that inherit from **Form1** to modify the properties of **btnProtected**.</span></span>

4. <span data-ttu-id="fb2fc-132">Haga doble clic en el botón **Say Hola** para agregar un controlador de eventos para el evento **click** .</span><span class="sxs-lookup"><span data-stu-id="fb2fc-132">Double-click the **Say Hello** button to add an event handler for the **Click** event.</span></span>

5. <span data-ttu-id="fb2fc-133">Agregue la línea de código siguiente al controlador del evento:</span><span class="sxs-lookup"><span data-stu-id="fb2fc-133">Add the following line of code to the event handler:</span></span>

    ```vb
    MessageBox.Show("Hello, World!")
    ```

    ```csharp
    MessageBox.Show("Hello, World!");
    ```

## <a name="add-a-button-that-cannot-be-modified-by-inheritors-of-the-base-form"></a><span data-ttu-id="fb2fc-134">Agregar un botón que los herederos del formulario base no pueden modificar</span><span class="sxs-lookup"><span data-stu-id="fb2fc-134">Add a button that cannot be modified by inheritors of the base form</span></span>

1. <span data-ttu-id="fb2fc-135">Cambie a la vista de diseño haciendo clic en la pestaña **Form1. VB [diseño], Form1.CS [diseño] o Form1. jsl [diseño]** situado encima del editor de código o presionando F7.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-135">Switch to design view by clicking the **Form1.vb [Design], Form1.cs [Design], or Form1.jsl [Design]** tab above the code editor, or by pressing F7.</span></span>

2. <span data-ttu-id="fb2fc-136">Agregue un segundo botón y establezca sus propiedades como sigue:</span><span class="sxs-lookup"><span data-stu-id="fb2fc-136">Add a second button and set its properties as follows:</span></span>

    - <span data-ttu-id="fb2fc-137">Establezca la propiedad **Text** en **Say Goodbye**.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-137">Set the **Text** property to **Say Goodbye**.</span></span>

    - <span data-ttu-id="fb2fc-138">Establezca la propiedad **(Name)** en **btnPrivate**.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-138">Set the **(Name)** property to **btnPrivate**.</span></span>

    - <span data-ttu-id="fb2fc-139">Establezca la propiedad Modifiers en **Private**.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-139">Set the **Modifiers** property to **Private**.</span></span> <span data-ttu-id="fb2fc-140">Esto hace imposible que los formularios que heredan de **Form1** modifiquen las propiedades de **btnPrivate**.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-140">This makes it impossible for forms that inherit from **Form1** to modify the properties of **btnPrivate**.</span></span>

3. <span data-ttu-id="fb2fc-141">Haga doble clic en el botón **Say adiós** para agregar un controlador de eventos para el evento **click** .</span><span class="sxs-lookup"><span data-stu-id="fb2fc-141">Double-click the **Say Goodbye** button to add an event handler for the **Click** event.</span></span> <span data-ttu-id="fb2fc-142">Coloque la siguiente línea de código en el procedimiento de evento:</span><span class="sxs-lookup"><span data-stu-id="fb2fc-142">Place the following line of code in the event procedure:</span></span>

    ```vb
    MessageBox.Show("Goodbye!")
    ```

    ```csharp
    MessageBox.Show("Goodbye!");
    ```

4. <span data-ttu-id="fb2fc-143">En el menú compilar, elija compilar **biblioteca BaseForm** para compilar la biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-143">From the **Build** menu, choose **Build BaseForm Library** to build the class library.</span></span>

     <span data-ttu-id="fb2fc-144">Una vez compilada la biblioteca, puede crear un nuevo proyecto que herede del formulario que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-144">Once the library is built, you can create a new project that inherits from the form you just created.</span></span>

## <a name="create-a-project-containing-a-form-that-inherits-from-the-base-form"></a><span data-ttu-id="fb2fc-145">Crear un proyecto que contenga un formulario que herede del formulario base</span><span class="sxs-lookup"><span data-stu-id="fb2fc-145">Create a project containing a form that inherits from the base form</span></span>

1. <span data-ttu-id="fb2fc-146">En el menú **archivo** , elija **Agregar** y, a continuación, **nuevo proyecto** para abrir el cuadro de diálogo **Agregar nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="fb2fc-146">From the **File** menu, choose **Add** and then **New Project** to open the **Add New Project** dialog box.</span></span>

2. <span data-ttu-id="fb2fc-147">Cree una aplicación de Windows Forms `InheritanceTest`denominada.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-147">Create a Windows Forms application named `InheritanceTest`.</span></span>

## <a name="add-an-inherited-form"></a><span data-ttu-id="fb2fc-148">Agregar un formulario heredado</span><span class="sxs-lookup"><span data-stu-id="fb2fc-148">Add an inherited form</span></span>

1. <span data-ttu-id="fb2fc-149">En **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **InheritanceTest** , seleccione **Agregar**y, a continuación, seleccione **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-149">In **Solution Explorer**, right-click the **InheritanceTest** project, select **Add**, and then select **New Item**.</span></span>

2. <span data-ttu-id="fb2fc-150">En el cuadro de diálogo **Agregar nuevo elemento** , seleccione la categoría **Windows Forms** (si tiene una lista de categorías) y, a continuación, seleccione la plantilla de **formulario heredado** .</span><span class="sxs-lookup"><span data-stu-id="fb2fc-150">In the **Add New Item** dialog box, select the **Windows Forms** category (if you have a list of categories) and then select the **Inherited Form** template.</span></span>

3. <span data-ttu-id="fb2fc-151">Deje el nombre `Form2` predeterminado y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-151">Leave the default name of `Form2` and then click **Add**.</span></span>

4. <span data-ttu-id="fb2fc-152">En el cuadro de diálogo **selector de herencia** , seleccione **Form1** desde el proyecto **BaseFormLibrary** como el formulario del que se va a heredar y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-152">In the **Inheritance Picker** dialog box, select **Form1** from the **BaseFormLibrary** project as the form to inherit from and click **OK**.</span></span>

     <span data-ttu-id="fb2fc-153">Esto crea un formulario en el proyecto **InheritanceTest** que se deriva del formulario en **BaseFormLibrary**.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-153">This creates a form in the **InheritanceTest** project that derives from the form in **BaseFormLibrary**.</span></span>

5. <span data-ttu-id="fb2fc-154">Abra el formulario heredado (**Form2**) en el diseñador haciendo doble clic en él, si aún no está abierto.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-154">Open the inherited form (**Form2**) in the designer by double-clicking it, if it is not already open.</span></span>

     <span data-ttu-id="fb2fc-155">En el diseñador, los botones heredados tienen un símbolo (</span><span class="sxs-lookup"><span data-stu-id="fb2fc-155">In the designer, the inherited buttons have a symbol (</span></span>![Captura de pantalla del símbolo de herencia Visual Basic.](./media/walkthrough-demonstrating-visual-inheritance/visual-basic-inheritance-glyph.gif)<span data-ttu-id="fb2fc-157">) en la esquina superior, lo que indica que se han heredado.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-157">) in their upper corner, indicating they are inherited.</span></span>

6. <span data-ttu-id="fb2fc-158">Seleccione el botón **Say Hola** y observe los controladores de tamaño.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-158">Select the **Say Hello** button and observe the resize handles.</span></span> <span data-ttu-id="fb2fc-159">Como este botón está protegido, los herederos pueden moverlo, cambiarlo de tamaño, cambiar su descripción y realizar otras modificaciones.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-159">Because this button is protected, the inheritors can move it, resize it, change its caption, and make other modifications.</span></span>

7. <span data-ttu-id="fb2fc-160">Seleccione el botón privado **decir adiós** y observe que no tiene controladores de tamaño.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-160">Select the private **Say Goodbye** button, and notice that it does not have resize handles.</span></span> <span data-ttu-id="fb2fc-161">Además, en la ventana **propiedades** , las propiedades de este botón aparecen atenuadas para indicar que no se pueden modificar.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-161">Additionally, in the **Properties** window, the properties of this button are grayed to indicate they cannot be modified.</span></span>

8. <span data-ttu-id="fb2fc-162">Si usa visual C#:</span><span class="sxs-lookup"><span data-stu-id="fb2fc-162">If you are using Visual C#:</span></span>

    1. <span data-ttu-id="fb2fc-163">En **Explorador de soluciones**, haga clic con el botón secundario en **Form1** en el proyecto **InheritanceTest** y seleccione **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-163">In **Solution Explorer**, right-click **Form1** in the **InheritanceTest** project and then choose **Delete**.</span></span> <span data-ttu-id="fb2fc-164">En el cuadro de mensaje que aparece, haga clic en **Aceptar** para confirmar la eliminación.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-164">In the message box that appears, click **OK** to confirm the deletion.</span></span>

    2. <span data-ttu-id="fb2fc-165">Abra el archivo Program.cs y cambie la línea `Application.Run(new Form1());` por `Application.Run(new Form2());`.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-165">Open the Program.cs file and change the line `Application.Run(new Form1());` to `Application.Run(new Form2());`.</span></span>

9. <span data-ttu-id="fb2fc-166">En **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **InheritanceTest** y seleccione **establecer como proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-166">In **Solution Explorer**, right-click the **InheritanceTest** project and select **Set As Startup Project**.</span></span>

10. <span data-ttu-id="fb2fc-167">En **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **InheritanceTest** y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-167">In **Solution Explorer**, right-click the **InheritanceTest** project and select **Properties**.</span></span>

11. <span data-ttu-id="fb2fc-168">En las páginas de propiedades de **InheritanceTest** , establezca el **objeto de inicio** para que sea el formulario heredado (**Form2**).</span><span class="sxs-lookup"><span data-stu-id="fb2fc-168">In the **InheritanceTest** property pages, set the **Startup object** to be the inherited form (**Form2**).</span></span>

12. <span data-ttu-id="fb2fc-169">Presione **F5** para ejecutar la aplicación y observe el comportamiento del formulario heredado.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-169">Press **F5** to run the application, and observe the behavior of the inherited form.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fb2fc-170">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="fb2fc-170">Next steps</span></span>

<span data-ttu-id="fb2fc-171">La herencia de los controles de usuario funciona más o menos de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-171">Inheritance for user controls works in much the same way.</span></span> <span data-ttu-id="fb2fc-172">Abra un proyecto nuevo de biblioteca de clases y agregue un control de usuario.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-172">Open a new class library project and add a user control.</span></span> <span data-ttu-id="fb2fc-173">Coloque en él controles constituyentes y compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-173">Place constituent controls on it and compile the project.</span></span> <span data-ttu-id="fb2fc-174">Abra otro proyecto nuevo de biblioteca de clases y agregue una referencia a la biblioteca de clases compilada.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-174">Open another new class library project and add a reference to the compiled class library.</span></span> <span data-ttu-id="fb2fc-175">Además, intente agregar un control heredado (mediante el cuadro de diálogo **agregar nuevos elementos** ) al proyecto y usando el **selector de herencia**.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-175">Also, try adding an inherited control (through the **Add New Items** dialog box) to the project and using the **Inheritance Picker**.</span></span> <span data-ttu-id="fb2fc-176">Agregue un control de usuario y cambie la `Inherits` instrucción`:` (en C#visual).</span><span class="sxs-lookup"><span data-stu-id="fb2fc-176">Add a user control, and change the `Inherits` (`:` in Visual C#) statement.</span></span> <span data-ttu-id="fb2fc-177">Para obtener más información, consulte [Cómo Heredar](how-to-inherit-windows-forms.md)Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="fb2fc-177">For more information, see [How to: Inherit Windows Forms](how-to-inherit-windows-forms.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fb2fc-178">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb2fc-178">See also</span></span>

- [<span data-ttu-id="fb2fc-179">Cómo: Heredar Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fb2fc-179">How to: Inherit Windows Forms</span></span>](how-to-inherit-windows-forms.md)
- [<span data-ttu-id="fb2fc-180">Herencia visual de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fb2fc-180">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
- [<span data-ttu-id="fb2fc-181">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fb2fc-181">Windows Forms</span></span>](../index.md)
