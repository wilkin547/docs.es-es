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
ms.openlocfilehash: bc91e3bde54eedb4d9dbcfcb9f7faa0ccc98e397
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43398698"
---
# <a name="walkthrough-demonstrating-visual-inheritance"></a><span data-ttu-id="42fc2-102">Tutorial: Demostración de la herencia visual</span><span class="sxs-lookup"><span data-stu-id="42fc2-102">Walkthrough: Demonstrating Visual Inheritance</span></span>
<span data-ttu-id="42fc2-103">La herencia visual le permite ver los controles del formulario base y agregar controles nuevos.</span><span class="sxs-lookup"><span data-stu-id="42fc2-103">Visual inheritance enables you to see the controls on the base form and to add new controls.</span></span> <span data-ttu-id="42fc2-104">En este tutorial, creará un formulario base y lo compilará para convertirlo en una biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="42fc2-104">In this walkthrough you will create a base form and compile it into a class library.</span></span> <span data-ttu-id="42fc2-105">Importará la biblioteca de clases en otro proyecto y creará un nuevo formulario que herede del formulario base.</span><span class="sxs-lookup"><span data-stu-id="42fc2-105">You will import this class library into another project and create a new form that inherits from the base form.</span></span> <span data-ttu-id="42fc2-106">Durante este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="42fc2-106">During this walkthrough, you will learn how to:</span></span>  
  
-   <span data-ttu-id="42fc2-107">Crear un proyecto de biblioteca de clases que contiene un formulario base.</span><span class="sxs-lookup"><span data-stu-id="42fc2-107">Create a class library project containing a base form.</span></span>  
  
-   <span data-ttu-id="42fc2-108">Agregar un botón con propiedades que las clases derivadas del formulario base pueden modificar.</span><span class="sxs-lookup"><span data-stu-id="42fc2-108">Add a button with properties that derived classes of the base form can modify.</span></span>  
  
-   <span data-ttu-id="42fc2-109">Agregar un botón que los herederos del formulario base no pueden modificar.</span><span class="sxs-lookup"><span data-stu-id="42fc2-109">Add a button that cannot be modified by inheritors of the base form.</span></span>  
  
-   <span data-ttu-id="42fc2-110">Crear un proyecto que contiene un formulario que hereda de `BaseForm`.</span><span class="sxs-lookup"><span data-stu-id="42fc2-110">Create a project containing a form that inherits from `BaseForm`.</span></span>  
  
 <span data-ttu-id="42fc2-111">Por último, en este tutorial se mostrará la diferencia entre los controles privados y los protegidos de un formulario heredado.</span><span class="sxs-lookup"><span data-stu-id="42fc2-111">Ultimately, this walkthrough will demonstrate the difference between private and protected controls on an inherited form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="42fc2-112">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="42fc2-112">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="42fc2-113">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="42fc2-113">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="42fc2-114">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="42fc2-114">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="42fc2-115">No todos los controles admiten la herencia visual a partir de un formulario base.</span><span class="sxs-lookup"><span data-stu-id="42fc2-115">Not all controls support visual inheritance from a base form.</span></span> <span data-ttu-id="42fc2-116">Los siguientes controles no admiten el escenario que se describe en este tutorial:</span><span class="sxs-lookup"><span data-stu-id="42fc2-116">The following controls do not support the scenario described in this walkthrough:</span></span>  
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
>  <span data-ttu-id="42fc2-117">Estos controles del formulario heredado siempre son de solo lectura, independientemente de los modificadores que utilice (`private`, `protected` o `public`).</span><span class="sxs-lookup"><span data-stu-id="42fc2-117">These controls in the inherited form are always read-only regardless of the modifiers you use (`private`, `protected`, or `public`).</span></span>  
  
## <a name="scenario-steps"></a><span data-ttu-id="42fc2-118">Pasos del escenario</span><span class="sxs-lookup"><span data-stu-id="42fc2-118">Scenario Steps</span></span>  
 <span data-ttu-id="42fc2-119">El primer paso es crear el formulario base.</span><span class="sxs-lookup"><span data-stu-id="42fc2-119">The first step is to create the base form.</span></span>  
  
#### <a name="to-create-a-class-library-project-containing-a-base-form"></a><span data-ttu-id="42fc2-120">Para crear un proyecto de biblioteca de clases que contenga un formulario base</span><span class="sxs-lookup"><span data-stu-id="42fc2-120">To create a class library project containing a base form</span></span>  
  
1.  <span data-ttu-id="42fc2-121">Desde el **archivo** menú, elija **New**y, a continuación, **proyecto** para abrir el **nuevo proyecto** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="42fc2-121">From the **File** menu, choose **New**, and then **Project** to open the **New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="42fc2-122">Cree una aplicación de Windows Forms denominada `BaseFormLibrary`.</span><span class="sxs-lookup"><span data-stu-id="42fc2-122">Create a Windows Forms application named `BaseFormLibrary`.</span></span>  
  
3.  <span data-ttu-id="42fc2-123">Para crear una biblioteca de clases en lugar de una aplicación de Windows Forms estándar, en **el Explorador de soluciones**, haga clic en el **BaseFormLibrary** nodo de proyecto y, a continuación, seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="42fc2-123">To create a class library instead of a standard Windows Forms application, in **Solution Explorer**, right-click the **BaseFormLibrary** project node and then select **Properties**.</span></span>  
  
4.  <span data-ttu-id="42fc2-124">En las propiedades del proyecto, cambie el **tipo de salida** desde **aplicación Windows** a **biblioteca de clases**.</span><span class="sxs-lookup"><span data-stu-id="42fc2-124">In the properties for the project, change the **Output type** from **Windows Application** to **Class Library**.</span></span>  
  
5.  <span data-ttu-id="42fc2-125">Desde el **archivo** menú, elija **guardar todo** para guardar el proyecto y archivos en la ubicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="42fc2-125">From the **File** menu, choose **Save All** to save the project and files to the default location.</span></span>  
  
 <span data-ttu-id="42fc2-126">Los dos procedimientos siguientes agregan botones al formulario base.</span><span class="sxs-lookup"><span data-stu-id="42fc2-126">The next two procedures add buttons to the base form.</span></span> <span data-ttu-id="42fc2-127">Para ilustrar la herencia visual, proporcionará a los botones distintos niveles de acceso estableciendo sus propiedades `Modifiers`.</span><span class="sxs-lookup"><span data-stu-id="42fc2-127">To demonstrate visual inheritance, you will give the buttons different access levels by setting their `Modifiers` properties.</span></span>  
  
#### <a name="to-add-a-button-that-inheritors-of-the-base-form-can-modify"></a><span data-ttu-id="42fc2-128">Para agregar un botón que los herederos del formulario base puedan modificar</span><span class="sxs-lookup"><span data-stu-id="42fc2-128">To add a button that inheritors of the base form can modify</span></span>  
  
1.  <span data-ttu-id="42fc2-129">Abra **Form1** en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="42fc2-129">Open **Form1** in the designer.</span></span>  
  
2.  <span data-ttu-id="42fc2-130">En el **todos los formularios de Windows** pestaña de la **cuadro de herramientas**, haga doble clic en **botón** para agregar un botón al formulario.</span><span class="sxs-lookup"><span data-stu-id="42fc2-130">On the **All Windows Forms** tab of the **Toolbox**, double-click **Button** to add a button to the form.</span></span> <span data-ttu-id="42fc2-131">Use el mouse para colocar y cambiar de tamaño el botón.</span><span class="sxs-lookup"><span data-stu-id="42fc2-131">Use the mouse to position and resize the button.</span></span>  
  
3.  <span data-ttu-id="42fc2-132">En la ventana Propiedades, establezca las propiedades siguientes del botón:</span><span class="sxs-lookup"><span data-stu-id="42fc2-132">In the Properties window, set the following properties of the button:</span></span>  
  
    -   <span data-ttu-id="42fc2-133">Establecer el **texto** propiedad **Say Hello**.</span><span class="sxs-lookup"><span data-stu-id="42fc2-133">Set the **Text** property to **Say Hello**.</span></span>  
  
    -   <span data-ttu-id="42fc2-134">Establecer el **(nombre)** propiedad **btnProtected**.</span><span class="sxs-lookup"><span data-stu-id="42fc2-134">Set the **(Name)** property to **btnProtected**.</span></span>  
  
    -   <span data-ttu-id="42fc2-135">Establecer el**modificadores** propiedad **Protected**.</span><span class="sxs-lookup"><span data-stu-id="42fc2-135">Set the**Modifiers** property to **Protected**.</span></span> <span data-ttu-id="42fc2-136">Esto hace posible para los formularios que heredan de **Form1** para modificar las propiedades de **btnProtected**.</span><span class="sxs-lookup"><span data-stu-id="42fc2-136">This makes it possible for forms that inherit from **Form1** to modify the properties of **btnProtected**.</span></span>  
  
4.  <span data-ttu-id="42fc2-137">Haga doble clic en el **Say Hello** para agregar un controlador de eventos para el **haga clic en** eventos.</span><span class="sxs-lookup"><span data-stu-id="42fc2-137">Double-click the **Say Hello** button to add an event handler for the **Click** event.</span></span>  
  
5.  <span data-ttu-id="42fc2-138">Agregue la línea de código siguiente al controlador del evento:</span><span class="sxs-lookup"><span data-stu-id="42fc2-138">Add the following line of code to the event handler:</span></span>  
  
    ```vb  
    MessageBox.Show("Hello, World!")  
    ```  
  
    ```csharp  
    MessageBox.Show("Hello, World!");  
    ```  
  
#### <a name="to-add-a-button-that-cannot-be-modified-by-inheritors-of-the-base-form"></a><span data-ttu-id="42fc2-139">Para agregar un botón que los herederos del formulario base no puedan modificar</span><span class="sxs-lookup"><span data-stu-id="42fc2-139">To add a button that cannot be modified by inheritors of the base form</span></span>  
  
1.  <span data-ttu-id="42fc2-140">Cambiar a vista de diseño, haga clic en el **Form1.vb [Diseño], Form1.cs [Diseño] o Form1.jsl [Diseño]** ficha encima del editor de código o presionando F7.</span><span class="sxs-lookup"><span data-stu-id="42fc2-140">Switch to design view by clicking the **Form1.vb [Design], Form1.cs [Design], or Form1.jsl [Design]** tab above the code editor, or by pressing F7.</span></span>  
  
2.  <span data-ttu-id="42fc2-141">Agregue un segundo botón y establezca sus propiedades como sigue:</span><span class="sxs-lookup"><span data-stu-id="42fc2-141">Add a second button and set its properties as follows:</span></span>  
  
    -   <span data-ttu-id="42fc2-142">Establecer el **texto** propiedad **Say Goodbye**.</span><span class="sxs-lookup"><span data-stu-id="42fc2-142">Set the **Text** property to **Say Goodbye**.</span></span>  
  
    -   <span data-ttu-id="42fc2-143">Establecer el **(nombre)** propiedad **btnPrivate**.</span><span class="sxs-lookup"><span data-stu-id="42fc2-143">Set the **(Name)** property to **btnPrivate**.</span></span>  
  
    -   <span data-ttu-id="42fc2-144">Establecer el **modificadores** propiedad **privada**.</span><span class="sxs-lookup"><span data-stu-id="42fc2-144">Set the **Modifiers** property to **Private**.</span></span> <span data-ttu-id="42fc2-145">Esto hace imposible que los formularios que heredan de **Form1** para modificar las propiedades de **btnPrivate**.</span><span class="sxs-lookup"><span data-stu-id="42fc2-145">This makes it impossible for forms that inherit from **Form1** to modify the properties of **btnPrivate**.</span></span>  
  
3.  <span data-ttu-id="42fc2-146">Haga doble clic en el **Say Goodbye** para agregar un controlador de eventos para el **haga clic en** eventos.</span><span class="sxs-lookup"><span data-stu-id="42fc2-146">Double-click the **Say Goodbye** button to add an event handler for the **Click** event.</span></span> <span data-ttu-id="42fc2-147">Coloque la siguiente línea de código en el procedimiento de evento:</span><span class="sxs-lookup"><span data-stu-id="42fc2-147">Place the following line of code in the event procedure:</span></span>  
  
    ```vb  
    MessageBox.Show("Goodbye!")  
    ```  
  
    ```csharp  
    MessageBox.Show("Goodbye!");  
    ```  
  
4.  <span data-ttu-id="42fc2-148">Desde el **compilar** menú, elija **compilar biblioteca BaseForm** para compilar la biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="42fc2-148">From the **Build** menu, choose **Build BaseForm Library** to build the class library.</span></span>  
  
     <span data-ttu-id="42fc2-149">Una vez compilada la biblioteca, puede crear un nuevo proyecto que herede del formulario que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="42fc2-149">Once the library is built, you can create a new project that inherits from the form you just created.</span></span>  
  
#### <a name="to-create-a-project-containing-a-form-that-inherits-from-the-base-form"></a><span data-ttu-id="42fc2-150">Para crear un proyecto que contenga un formulario que herede del formulario base</span><span class="sxs-lookup"><span data-stu-id="42fc2-150">To create a project containing a form that inherits from the base form</span></span>  
  
1.  <span data-ttu-id="42fc2-151">Desde el **archivo** menú, elija **agregar** y, a continuación, **nuevo proyecto** para abrir el **Agregar nuevo proyecto** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="42fc2-151">From the **File** menu, choose **Add** and then **New Project** to open the **Add New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="42fc2-152">Cree una aplicación de Windows Forms denominada `InheritanceTest`.</span><span class="sxs-lookup"><span data-stu-id="42fc2-152">Create a Windows Forms application named `InheritanceTest`.</span></span>  
  
#### <a name="to-add-an-inherited-form"></a><span data-ttu-id="42fc2-153">Para agregar un formulario heredado</span><span class="sxs-lookup"><span data-stu-id="42fc2-153">To add an inherited form</span></span>  
  
1.  <span data-ttu-id="42fc2-154">En **el Explorador de soluciones**, haga clic en el **InheritanceTest** proyecto, seleccione **agregar**y, a continuación, seleccione**nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="42fc2-154">In **Solution Explorer**, right-click the **InheritanceTest** project, select **Add**, and then select**New Item**.</span></span>  
  
2.  <span data-ttu-id="42fc2-155">En el **Agregar nuevo elemento** cuadro de diálogo, seleccione el **Windows Forms** categoría (si tiene una lista de categorías) y, a continuación, seleccione el **formulario heredado** plantilla.</span><span class="sxs-lookup"><span data-stu-id="42fc2-155">In the **Add New Item** dialog box, select the **Windows Forms** category (if you have a list of categories) and then select the **Inherited Form** template.</span></span>  
  
3.  <span data-ttu-id="42fc2-156">Deje el nombre predeterminado de `Form2` y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="42fc2-156">Leave the default name of `Form2` and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="42fc2-157">En el **selector de herencia** cuadro de diálogo, seleccione **Form1** desde el **BaseFormLibrary** proyecto como el formulario para heredar de y haga clic en **Aceptar** .</span><span class="sxs-lookup"><span data-stu-id="42fc2-157">In the **Inheritance Picker** dialog box, select **Form1** from the **BaseFormLibrary** project as the form to inherit from and click **OK**.</span></span>  
  
     <span data-ttu-id="42fc2-158">Esto crea un formulario en el **InheritanceTest** proyecto que se deriva de la forma en **BaseFormLibrary**.</span><span class="sxs-lookup"><span data-stu-id="42fc2-158">This creates a form in the **InheritanceTest** project that derives from the form in **BaseFormLibrary**.</span></span>  
  
5.  <span data-ttu-id="42fc2-159">Abra el formulario heredado (**Form2**) en el diseñador haciendo doble clic en él, si aún no está abierto.</span><span class="sxs-lookup"><span data-stu-id="42fc2-159">Open the inherited form (**Form2**) in the designer by double-clicking it, if it is not already open.</span></span>  
  
     <span data-ttu-id="42fc2-160">En el diseñador, los botones heredados tienen un símbolo (![captura de pantalla de VisualBasicInheritanceSymbol](../../../../docs/framework/winforms/advanced/media/vbinheritanceglyph.gif "vbInheritanceGlyph")) en la esquina superior para indicar que son heredados.</span><span class="sxs-lookup"><span data-stu-id="42fc2-160">In the designer, the inherited buttons have a symbol (![VisualBasicInheritanceSymbol screenshot](../../../../docs/framework/winforms/advanced/media/vbinheritanceglyph.gif "vbInheritanceGlyph")) in their upper corner, indicating they are inherited.</span></span>  
  
6.  <span data-ttu-id="42fc2-161">Seleccione el **Say Hello** botón y observe los controladores de tamaño.</span><span class="sxs-lookup"><span data-stu-id="42fc2-161">Select the **Say Hello** button and observe the resize handles.</span></span> <span data-ttu-id="42fc2-162">Como este botón está protegido, los herederos pueden moverlo, cambiarlo de tamaño, cambiar su descripción y realizar otras modificaciones.</span><span class="sxs-lookup"><span data-stu-id="42fc2-162">Because this button is protected, the inheritors can move it, resize it, change its caption, and make other modifications.</span></span>  
  
7.  <span data-ttu-id="42fc2-163">Seleccione privado **Say Goodbye** botón y tenga en cuenta que no tiene controladores de tamaño.</span><span class="sxs-lookup"><span data-stu-id="42fc2-163">Select the private **Say Goodbye** button, and notice that it does not have resize handles.</span></span> <span data-ttu-id="42fc2-164">Además, en el **propiedades** ventana, las propiedades de este botón aparecen en gris para indicar que no se pueden modificar.</span><span class="sxs-lookup"><span data-stu-id="42fc2-164">Additionally, in the **Properties** window, the properties of this button are grayed to indicate they cannot be modified.</span></span>  
  
8.  <span data-ttu-id="42fc2-165">Si está utilizando Visual C#:</span><span class="sxs-lookup"><span data-stu-id="42fc2-165">If you are using Visual C#:</span></span>  
  
    1.  <span data-ttu-id="42fc2-166">En **el Explorador de soluciones**, haga clic en **Form1** en el **InheritanceTest** proyecto y, a continuación, elija **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="42fc2-166">In **Solution Explorer**, right-click **Form1** in the **InheritanceTest** project and then choose **Delete**.</span></span> <span data-ttu-id="42fc2-167">En el cuadro de mensaje que aparece, haga clic en **Aceptar** para confirmar la eliminación.</span><span class="sxs-lookup"><span data-stu-id="42fc2-167">In the message box that appears, click **OK** to confirm the deletion.</span></span>  
  
    2.  <span data-ttu-id="42fc2-168">Abra el archivo Program.cs y cambie la línea `Application.Run(new Form1());` por `Application.Run(new Form2());`.</span><span class="sxs-lookup"><span data-stu-id="42fc2-168">Open the Program.cs file and change the line `Application.Run(new Form1());` to `Application.Run(new Form2());`.</span></span>  
  
9. <span data-ttu-id="42fc2-169">En **el Explorador de soluciones**, haga clic en el **InheritanceTest** del proyecto y seleccione **establecer como proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="42fc2-169">In **Solution Explorer**, right-click the **InheritanceTest** project and select **Set As Startup Project**.</span></span>  
  
10. <span data-ttu-id="42fc2-170">En **el Explorador de soluciones**, haga clic en el **InheritanceTest** del proyecto y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="42fc2-170">In **Solution Explorer**, right-click the **InheritanceTest** project and select **Properties**.</span></span>  
  
11. <span data-ttu-id="42fc2-171">En el **InheritanceTest** páginas de propiedades, establezca la **objeto Startup** sea el formulario heredado (**Form2**).</span><span class="sxs-lookup"><span data-stu-id="42fc2-171">In the **InheritanceTest** property pages, set the **Startup object** to be the inherited form (**Form2**).</span></span>  
  
12. <span data-ttu-id="42fc2-172">Presione F5 para ejecutar la aplicación y observe el comportamiento del formulario heredado.</span><span class="sxs-lookup"><span data-stu-id="42fc2-172">Press F5 to run the application, and observe the behavior of the inherited form.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="42fc2-173">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="42fc2-173">Next Steps</span></span>  
 <span data-ttu-id="42fc2-174">La herencia de los controles de usuario funciona más o menos de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="42fc2-174">Inheritance for user controls works in much the same way.</span></span> <span data-ttu-id="42fc2-175">Abra un proyecto nuevo de biblioteca de clases y agregue un control de usuario.</span><span class="sxs-lookup"><span data-stu-id="42fc2-175">Open a new class library project and add a user control.</span></span> <span data-ttu-id="42fc2-176">Coloque en él controles constituyentes y compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="42fc2-176">Place constituent controls on it and compile the project.</span></span> <span data-ttu-id="42fc2-177">Abra otro proyecto nuevo de biblioteca de clases y agregue una referencia a la biblioteca de clases compilada.</span><span class="sxs-lookup"><span data-stu-id="42fc2-177">Open another new class library project and add a reference to the compiled class library.</span></span> <span data-ttu-id="42fc2-178">Además, pruebe a agregar un control heredado (a través de la **agregar nuevos elementos** cuadro de diálogo) al proyecto y el uso de la **selector de herencia**.</span><span class="sxs-lookup"><span data-stu-id="42fc2-178">Also, try adding an inherited control (through the **Add New Items** dialog box) to the project and using the **Inheritance Picker**.</span></span> <span data-ttu-id="42fc2-179">Agregue un control de usuario y cambie la `Inherits` (`:` en Visual C#) instrucción.</span><span class="sxs-lookup"><span data-stu-id="42fc2-179">Add a user control, and change the `Inherits` (`:` in Visual C#) statement.</span></span> <span data-ttu-id="42fc2-180">Para obtener más información, consulte [Cómo: heredar Windows Forms](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="42fc2-180">For more information, see [How to: Inherit Windows Forms](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42fc2-181">Vea también</span><span class="sxs-lookup"><span data-stu-id="42fc2-181">See Also</span></span>  
 [<span data-ttu-id="42fc2-182">Cómo: Heredar formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="42fc2-182">How to: Inherit Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)  
 [<span data-ttu-id="42fc2-183">Herencia visual de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="42fc2-183">Windows Forms Visual Inheritance</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)  
 [<span data-ttu-id="42fc2-184">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="42fc2-184">Windows Forms</span></span>](../../../../docs/framework/winforms/index.md)
