---
title: 'Tutorial: Crear un formulario MDI con combinación de menús y controles ToolStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- MDI [Windows Forms], creating forms
- multiple document interface forms
- MDI forms
- ToolStrip control [Windows Forms]
- MDI forms [Windows Forms], creating
- MDI forms [Windows Forms], walkthroughs
ms.assetid: fbab4221-74af-42d0-bbf4-3c97f7b2e544
ms.openlocfilehash: e0343b98cb71521b35418e70550a93e0bfe20fa8
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628792"
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="926dd-102">Tutorial: Crear un formulario MDI con combinación de menús y controles ToolStrip</span><span class="sxs-lookup"><span data-stu-id="926dd-102">Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls</span></span>

<span data-ttu-id="926dd-103">El espacio de nombres <xref:System.Windows.Forms?displayProperty=nameWithType> es compatible con aplicaciones de interfaces de múltiples documentos (MDI) y el control <xref:System.Windows.Forms.MenuStrip> admite la combinación de menús.</span><span class="sxs-lookup"><span data-stu-id="926dd-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="926dd-104">Los formularios MDI también pueden ser compatibles con los controles <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="926dd-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>

<span data-ttu-id="926dd-105">En este tutorial se muestra cómo utilizar los controles <xref:System.Windows.Forms.ToolStripPanel> con un formulario MDI.</span><span class="sxs-lookup"><span data-stu-id="926dd-105">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="926dd-106">El formulario también admite la combinación de menús con menús secundarios.</span><span class="sxs-lookup"><span data-stu-id="926dd-106">The form also supports menu merging with child menus.</span></span> <span data-ttu-id="926dd-107">En este tutorial se muestran las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="926dd-107">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="926dd-108">Crear un proyecto de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="926dd-108">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="926dd-109">Crear el menú principal del formulario.</span><span class="sxs-lookup"><span data-stu-id="926dd-109">Creating the main menu for your form.</span></span> <span data-ttu-id="926dd-110">El nombre real del menú variará.</span><span class="sxs-lookup"><span data-stu-id="926dd-110">The actual name of the menu will vary.</span></span>

- <span data-ttu-id="926dd-111">Agregar el control <xref:System.Windows.Forms.ToolStripPanel> al **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="926dd-111">Adding the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox**.</span></span>

- <span data-ttu-id="926dd-112">Crear un formulario secundario.</span><span class="sxs-lookup"><span data-stu-id="926dd-112">Creating a child form.</span></span>

- <span data-ttu-id="926dd-113">Organizar los controles de <xref:System.Windows.Forms.ToolStripPanel> por orden z.</span><span class="sxs-lookup"><span data-stu-id="926dd-113">Arranging <xref:System.Windows.Forms.ToolStripPanel> controls by z-order.</span></span>

<span data-ttu-id="926dd-114">Cuando haya terminado, tendrá un formulario MDI que admite la combinación de menús y los controles de <xref:System.Windows.Forms.ToolStrip> móviles.</span><span class="sxs-lookup"><span data-stu-id="926dd-114">When you are finished, you will have an MDI form that supports menu merging and movable <xref:System.Windows.Forms.ToolStrip> controls.</span></span>

<span data-ttu-id="926dd-115">Para copiar el código de este tema como una sola lista, vea [Cómo: crear un formulario MDI con combinación de menús y controles ToolStrip](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="926dd-115">To copy the code in this topic as a single listing, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="926dd-116">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="926dd-116">Prerequisites</span></span>

<span data-ttu-id="926dd-117">Necesitará Visual Studio para completar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="926dd-117">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="926dd-118">Creación del proyecto</span><span class="sxs-lookup"><span data-stu-id="926dd-118">Create the project</span></span>

1. <span data-ttu-id="926dd-119">En Visual Studio, cree un proyecto de aplicación para Windows denominado **MdiForm** (**archivo** > **nuevo** **proyecto** de >  > **Visual C#**  o **Visual Basic** > **aplicación**de **escritorio clásico** > Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="926dd-119">In Visual Studio, create a Windows Application project called **MdiForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="926dd-120">En el Diseñador de Windows Forms, seleccione el formulario.</span><span class="sxs-lookup"><span data-stu-id="926dd-120">In the Windows Forms Designer, select the form.</span></span>

3. <span data-ttu-id="926dd-121">En el ventana Propiedades, establezca el valor de la <xref:System.Windows.Forms.Form.IsMdiContainer%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="926dd-121">In the Properties window, set the value of the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> to `true`.</span></span>

## <a name="create-the-main-menu"></a><span data-ttu-id="926dd-122">Crear el menú principal</span><span class="sxs-lookup"><span data-stu-id="926dd-122">Create the main menu</span></span>

<span data-ttu-id="926dd-123">El formulario MDI primario contiene el menú principal.</span><span class="sxs-lookup"><span data-stu-id="926dd-123">The parent MDI form contains the main menu.</span></span> <span data-ttu-id="926dd-124">El menú principal tiene un elemento de menú denominado **Window**.</span><span class="sxs-lookup"><span data-stu-id="926dd-124">The main menu has one menu item named **Window**.</span></span> <span data-ttu-id="926dd-125">Con el elemento de menú **ventana** , puede crear formularios secundarios.</span><span class="sxs-lookup"><span data-stu-id="926dd-125">With the **Window** menu item, you can create child forms.</span></span> <span data-ttu-id="926dd-126">Los elementos de menú de los formularios secundarios se combinan en el menú principal.</span><span class="sxs-lookup"><span data-stu-id="926dd-126">Menu items from child forms are merged into the main menu.</span></span>

1. <span data-ttu-id="926dd-127">En el **cuadro de herramientas**, arrastre un control <xref:System.Windows.Forms.MenuStrip> al formulario.</span><span class="sxs-lookup"><span data-stu-id="926dd-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the form.</span></span>

2. <span data-ttu-id="926dd-128">Agregue un <xref:System.Windows.Forms.ToolStripMenuItem> al control <xref:System.Windows.Forms.MenuStrip> y asígnele el nombre **Window**.</span><span class="sxs-lookup"><span data-stu-id="926dd-128">Add a <xref:System.Windows.Forms.ToolStripMenuItem> to the <xref:System.Windows.Forms.MenuStrip> control and name it **Window**.</span></span>

3. <span data-ttu-id="926dd-129">Seleccione el control <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="926dd-129">Select the <xref:System.Windows.Forms.MenuStrip> control.</span></span>

4. <span data-ttu-id="926dd-130">En el ventana Propiedades, establezca el valor de la propiedad <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> en `ToolStripMenuItem1`.</span><span class="sxs-lookup"><span data-stu-id="926dd-130">In the Properties window, set the value of the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to `ToolStripMenuItem1`.</span></span>

5. <span data-ttu-id="926dd-131">Agregue un subelemento al elemento de menú **ventana** y, a continuación, asigne el nombre **New**al subelemento.</span><span class="sxs-lookup"><span data-stu-id="926dd-131">Add a subitem to the **Window** menu item, and then name the subitem **New**.</span></span>

6. <span data-ttu-id="926dd-132">En el ventana Propiedades, haga clic en **eventos**.</span><span class="sxs-lookup"><span data-stu-id="926dd-132">In the Properties window, click **Events**.</span></span>

7. <span data-ttu-id="926dd-133">Haga doble clic en el evento <xref:System.Windows.Forms.ToolStripItem.Click>.</span><span class="sxs-lookup"><span data-stu-id="926dd-133">Double-click the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>

     <span data-ttu-id="926dd-134">El Diseñador de Windows Forms genera un controlador de eventos para el evento <xref:System.Windows.Forms.ToolStripItem.Click>.</span><span class="sxs-lookup"><span data-stu-id="926dd-134">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>

8. <span data-ttu-id="926dd-135">Inserte el código siguiente en el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="926dd-135">Insert the following code into the event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]

## <a name="add-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="926dd-136">Agregar el control ToolStripPanel al cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="926dd-136">Add the ToolStripPanel control to the Toolbox</span></span>

<span data-ttu-id="926dd-137">Cuando use <xref:System.Windows.Forms.MenuStrip> controles con un formulario MDI, debe tener el control <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="926dd-137">When you use <xref:System.Windows.Forms.MenuStrip> controls with an MDI form you must have the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="926dd-138">Debe agregar el control <xref:System.Windows.Forms.ToolStripPanel> al cuadro de **herramientas** para compilar el formulario MDI en el diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="926dd-138">You must add the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox** to build your MDI form in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="926dd-139">Abra el **cuadro de herramientas**y, a continuación, haga clic en la pestaña **todos los Windows Forms** para mostrar los controles de Windows Forms disponibles.</span><span class="sxs-lookup"><span data-stu-id="926dd-139">Open the **Toolbox**, and then click the **All Windows Forms** tab to show the available Windows Forms controls.</span></span>

2. <span data-ttu-id="926dd-140">Haga clic con el botón derecho para abrir el menú contextual y seleccione **elegir elementos**.</span><span class="sxs-lookup"><span data-stu-id="926dd-140">Right-click to open the shortcut menu, and select **Choose Items**.</span></span>

3. <span data-ttu-id="926dd-141">En el cuadro de diálogo **elegir elementos del cuadro de herramientas** , desplácese hacia abajo en la columna **nombre** hasta que encuentre **ToolStripPanel**.</span><span class="sxs-lookup"><span data-stu-id="926dd-141">In the **Choose Toolbox Items** dialog box, scroll down the **Name** column until you find **ToolStripPanel**.</span></span>

4. <span data-ttu-id="926dd-142">Active la casilla de **ToolStripPanel**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="926dd-142">Select the check box by **ToolStripPanel**, and then click **OK**.</span></span>

     <span data-ttu-id="926dd-143">El control <xref:System.Windows.Forms.ToolStripPanel> aparece en el **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="926dd-143">The <xref:System.Windows.Forms.ToolStripPanel> control appears in the **Toolbox**.</span></span>

## <a name="create-a-child-form"></a><span data-ttu-id="926dd-144">Crear un formulario secundario</span><span class="sxs-lookup"><span data-stu-id="926dd-144">Create a child form</span></span>

<span data-ttu-id="926dd-145">En este procedimiento, definirá una clase de formulario secundario independiente que tiene su propio control <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="926dd-145">In this procedure, you will define a separate child form class that has its own <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="926dd-146">Los elementos de menú para este formulario se combinan con los del formulario primario.</span><span class="sxs-lookup"><span data-stu-id="926dd-146">The menu items for this form are merged with those of the parent form.</span></span>

1. <span data-ttu-id="926dd-147">Agregue un nuevo formulario denominado `ChildForm` al proyecto.</span><span class="sxs-lookup"><span data-stu-id="926dd-147">Add a new form named `ChildForm` to the project.</span></span>

     <span data-ttu-id="926dd-148">Para obtener más información, vea [Cómo: agregar Windows Forms a un proyecto](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="926dd-148">For more information, see [How to: Add Windows Forms to a Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100)).</span></span>

2. <span data-ttu-id="926dd-149">En el **cuadro de herramientas**, arrastre un control <xref:System.Windows.Forms.MenuStrip> al formulario secundario.</span><span class="sxs-lookup"><span data-stu-id="926dd-149">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the child form.</span></span>

3. <span data-ttu-id="926dd-150">Haga clic en el glifo de acciones del diseñador del <xref:System.Windows.Forms.MenuStrip> del control (![flecha negra pequeña](./media/designer-actions-glyph.gif)) y, a continuación, seleccione **Editar elementos**.</span><span class="sxs-lookup"><span data-stu-id="926dd-150">Click the <xref:System.Windows.Forms.MenuStrip> control's designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)), and then select **Edit Items**.</span></span>

4. <span data-ttu-id="926dd-151">En el cuadro de diálogo Editor de la **colección de elementos** , agregue una nueva <xref:System.Windows.Forms.ToolStripMenuItem> denominada **ChildMenuItem** al menú secundario.</span><span class="sxs-lookup"><span data-stu-id="926dd-151">In the **Items Collection Editor** dialog box, add a new <xref:System.Windows.Forms.ToolStripMenuItem> named **ChildMenuItem** to the child menu.</span></span>

     <span data-ttu-id="926dd-152">Para obtener más información, vea [Editor de colecciones de elementos ToolStrip](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="926dd-152">For more information, see [ToolStrip Items Collection Editor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100)).</span></span>

## <a name="test-the-form"></a><span data-ttu-id="926dd-153">Prueba del formulario</span><span class="sxs-lookup"><span data-stu-id="926dd-153">Test the form</span></span>

1. <span data-ttu-id="926dd-154">Presione **F5** para compilar y ejecutar el formulario.</span><span class="sxs-lookup"><span data-stu-id="926dd-154">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="926dd-155">Haga clic en el elemento de menú **ventana** para abrir el menú y, a continuación, haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="926dd-155">Click the **Window** menu item to open the menu, and then click **New**.</span></span>

     <span data-ttu-id="926dd-156">Se crea un nuevo formulario secundario en el área cliente MDI del formulario.</span><span class="sxs-lookup"><span data-stu-id="926dd-156">A new child form is created in the form's MDI client area.</span></span> <span data-ttu-id="926dd-157">El menú del formulario secundario se combina con el menú principal.</span><span class="sxs-lookup"><span data-stu-id="926dd-157">The child form's menu is merged with the main menu.</span></span>

3. <span data-ttu-id="926dd-158">Cierre el formulario secundario.</span><span class="sxs-lookup"><span data-stu-id="926dd-158">Close the child form.</span></span>

     <span data-ttu-id="926dd-159">El menú del formulario secundario se quita del menú principal.</span><span class="sxs-lookup"><span data-stu-id="926dd-159">The child form's menu is removed from the main menu.</span></span>

4. <span data-ttu-id="926dd-160">Haga clic en **nuevo** varias veces.</span><span class="sxs-lookup"><span data-stu-id="926dd-160">Click **New** several times.</span></span>

     <span data-ttu-id="926dd-161">Los formularios secundarios aparecen automáticamente en el elemento de menú **ventana** porque se asigna la propiedad <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> del control <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="926dd-161">The child forms are automatically listed under the **Window** menu item because the <xref:System.Windows.Forms.MenuStrip> control's <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property is assigned.</span></span>

## <a name="add-toolstrip-support"></a><span data-ttu-id="926dd-162">Agregar compatibilidad con ToolStrip</span><span class="sxs-lookup"><span data-stu-id="926dd-162">Add ToolStrip support</span></span>

<span data-ttu-id="926dd-163">En este procedimiento, agregará cuatro controles <xref:System.Windows.Forms.ToolStrip> al formulario MDI primario.</span><span class="sxs-lookup"><span data-stu-id="926dd-163">In this procedure, you will add four <xref:System.Windows.Forms.ToolStrip> controls to the MDI parent form.</span></span> <span data-ttu-id="926dd-164">Cada control de <xref:System.Windows.Forms.ToolStrip> se agrega dentro de un control <xref:System.Windows.Forms.ToolStripPanel>, que está acoplado al borde del formulario.</span><span class="sxs-lookup"><span data-stu-id="926dd-164">Each <xref:System.Windows.Forms.ToolStrip> control is added inside a <xref:System.Windows.Forms.ToolStripPanel> control, which is docked to the edge of the form.</span></span>

1. <span data-ttu-id="926dd-165">En el **cuadro de herramientas**, arrastre un control <xref:System.Windows.Forms.ToolStripPanel> al formulario.</span><span class="sxs-lookup"><span data-stu-id="926dd-165">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStripPanel> control onto the form.</span></span>

2. <span data-ttu-id="926dd-166">Con el control <xref:System.Windows.Forms.ToolStripPanel> seleccionado, haga doble clic en el control <xref:System.Windows.Forms.ToolStrip> en el **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="926dd-166">With the <xref:System.Windows.Forms.ToolStripPanel> control selected, double-click the <xref:System.Windows.Forms.ToolStrip> control in the **Toolbox**.</span></span>

     <span data-ttu-id="926dd-167">Se crea un control <xref:System.Windows.Forms.ToolStrip> en el control <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="926dd-167">A <xref:System.Windows.Forms.ToolStrip> control is created in the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

3. <span data-ttu-id="926dd-168">Seleccione el control <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="926dd-168">Select the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

4. <span data-ttu-id="926dd-169">En el ventana Propiedades, cambie el valor de la propiedad <xref:System.Windows.Forms.Control.Dock%2A> del control por <xref:System.Windows.Forms.DockStyle.Left>.</span><span class="sxs-lookup"><span data-stu-id="926dd-169">In the Properties window, change the value of the control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Left>.</span></span>

     <span data-ttu-id="926dd-170">El control <xref:System.Windows.Forms.ToolStripPanel> acopla en el lado izquierdo del formulario, debajo del menú principal.</span><span class="sxs-lookup"><span data-stu-id="926dd-170">The <xref:System.Windows.Forms.ToolStripPanel> control docks to the left side of the form, underneath the main menu.</span></span> <span data-ttu-id="926dd-171">El área del cliente MDI cambia de tamaño para ajustarse al control <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="926dd-171">The MDI client area resizes to fit the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

5. <span data-ttu-id="926dd-172">Repita los pasos del 1 al 4.</span><span class="sxs-lookup"><span data-stu-id="926dd-172">Repeat steps 1 through 4.</span></span>

     <span data-ttu-id="926dd-173">Acople el nuevo control <xref:System.Windows.Forms.ToolStripPanel> en la parte superior del formulario.</span><span class="sxs-lookup"><span data-stu-id="926dd-173">Dock the new <xref:System.Windows.Forms.ToolStripPanel> control to the top of the form.</span></span>

     <span data-ttu-id="926dd-174">El control <xref:System.Windows.Forms.ToolStripPanel> se acopla debajo del menú principal, pero a la derecha del primer control <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="926dd-174">The <xref:System.Windows.Forms.ToolStripPanel> control is docked underneath the main menu, but to the right of the first <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="926dd-175">Este paso muestra la importancia del orden z en el posicionamiento correcto de los controles <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="926dd-175">This step illustrates the importance of z-order in correctly positioning <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>

6. <span data-ttu-id="926dd-176">Repita los pasos del 1 al 4 para dos controles más <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="926dd-176">Repeat steps 1 through 4 for two more <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>

     <span data-ttu-id="926dd-177">Acople los nuevos controles de <xref:System.Windows.Forms.ToolStripPanel> a la parte derecha e inferior del formulario.</span><span class="sxs-lookup"><span data-stu-id="926dd-177">Dock the new <xref:System.Windows.Forms.ToolStripPanel> controls to the right and bottom of the form.</span></span>

## <a name="arrange-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="926dd-178">Organizar los controles ToolStripPanel por orden Z</span><span class="sxs-lookup"><span data-stu-id="926dd-178">Arrange ToolStripPanel controls by Z-order</span></span>

<span data-ttu-id="926dd-179">La posición de un control de <xref:System.Windows.Forms.ToolStripPanel> acoplado en el formulario MDI viene determinada por la posición del control en el orden z.</span><span class="sxs-lookup"><span data-stu-id="926dd-179">The position of a docked <xref:System.Windows.Forms.ToolStripPanel> control on your MDI form is determined by the control's position in the z-order.</span></span> <span data-ttu-id="926dd-180">Puede organizar fácilmente el orden z de los controles en la ventana esquema del documento.</span><span class="sxs-lookup"><span data-stu-id="926dd-180">You can easily arrange the z-order of your controls in the Document Outline window.</span></span>

1. <span data-ttu-id="926dd-181">En el menú **Ver** , haga clic en **otras ventanas**y, a continuación, haga clic en **esquema del documento**.</span><span class="sxs-lookup"><span data-stu-id="926dd-181">In the **View** menu, click **Other Windows**, and then click **Document Outline**.</span></span>

     <span data-ttu-id="926dd-182">La organización de los controles de <xref:System.Windows.Forms.ToolStripPanel> del procedimiento anterior no es estándar.</span><span class="sxs-lookup"><span data-stu-id="926dd-182">The arrangement of your <xref:System.Windows.Forms.ToolStripPanel> controls from the previous procedure is nonstandard.</span></span> <span data-ttu-id="926dd-183">Esto se debe a que el orden z no es correcto.</span><span class="sxs-lookup"><span data-stu-id="926dd-183">This is because the z-order is not correct.</span></span> <span data-ttu-id="926dd-184">Use la ventana esquema del documento para cambiar el orden z de los controles.</span><span class="sxs-lookup"><span data-stu-id="926dd-184">Use the Document Outline window to change the z-order of the controls.</span></span>

2. <span data-ttu-id="926dd-185">En la ventana esquema del documento, seleccione **ToolStripPanel4**.</span><span class="sxs-lookup"><span data-stu-id="926dd-185">In the Document Outline window, select **ToolStripPanel4**.</span></span>

3. <span data-ttu-id="926dd-186">Haga clic repetidamente en el botón de flecha abajo, hasta que **ToolStripPanel4** esté en la parte inferior de la lista.</span><span class="sxs-lookup"><span data-stu-id="926dd-186">Click the down-arrow button repeatedly, until **ToolStripPanel4** is at the bottom of the list.</span></span>

     <span data-ttu-id="926dd-187">El control **ToolStripPanel4** se acopla a la parte inferior del formulario, debajo de los demás controles.</span><span class="sxs-lookup"><span data-stu-id="926dd-187">The **ToolStripPanel4** control is docked to the bottom of the form, underneath the other controls.</span></span>

4. <span data-ttu-id="926dd-188">Seleccione **ToolStripPanel2**.</span><span class="sxs-lookup"><span data-stu-id="926dd-188">Select **ToolStripPanel2**.</span></span>

5. <span data-ttu-id="926dd-189">Haga clic en el botón de flecha abajo una vez para colocar el control en tercer lugar en la lista.</span><span class="sxs-lookup"><span data-stu-id="926dd-189">Click the down-arrow button one time to position the control third in the list.</span></span>

     <span data-ttu-id="926dd-190">El control **ToolStripPanel2** se acopla a la parte superior del formulario, debajo del menú principal y encima de los demás controles.</span><span class="sxs-lookup"><span data-stu-id="926dd-190">The **ToolStripPanel2** control is docked to the top of the form, underneath the main menu and above the other controls.</span></span>

6. <span data-ttu-id="926dd-191">Seleccione varios controles en la ventana **esquema del documento** y muévalos a posiciones diferentes en el orden z.</span><span class="sxs-lookup"><span data-stu-id="926dd-191">Select various controls in the **Document Outline** window and move them to different positions in the z-order.</span></span> <span data-ttu-id="926dd-192">Observe el efecto del orden z en la posición de los controles acoplados.</span><span class="sxs-lookup"><span data-stu-id="926dd-192">Note the effect of the z-order on the placement of docked controls.</span></span> <span data-ttu-id="926dd-193">Use CTRL-Z o **Deshacer** en el menú **edición** para deshacer los cambios.</span><span class="sxs-lookup"><span data-stu-id="926dd-193">Use CTRL-Z or **Undo** on the **Edit** menu to undo your changes.</span></span>

## <a name="checkpoint---test-your-form"></a><span data-ttu-id="926dd-194">Punto de control: prueba del formulario</span><span class="sxs-lookup"><span data-stu-id="926dd-194">Checkpoint - test your form</span></span>

1. <span data-ttu-id="926dd-195">Presione **F5** para compilar y ejecutar el formulario.</span><span class="sxs-lookup"><span data-stu-id="926dd-195">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="926dd-196">Haga clic en el control de un control de <xref:System.Windows.Forms.ToolStrip> y arrastre el control a distintas posiciones del formulario.</span><span class="sxs-lookup"><span data-stu-id="926dd-196">Click the grip of a <xref:System.Windows.Forms.ToolStrip> control and drag the control to different positions on the form.</span></span>

     <span data-ttu-id="926dd-197">Puede arrastrar un control de <xref:System.Windows.Forms.ToolStrip> de un control <xref:System.Windows.Forms.ToolStripPanel> a otro.</span><span class="sxs-lookup"><span data-stu-id="926dd-197">You can drag a <xref:System.Windows.Forms.ToolStrip> control from one <xref:System.Windows.Forms.ToolStripPanel> control to another.</span></span>

## <a name="next-steps"></a><span data-ttu-id="926dd-198">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="926dd-198">Next steps</span></span>

<span data-ttu-id="926dd-199">En este tutorial, ha creado un formulario MDI primario con <xref:System.Windows.Forms.ToolStrip> controles y la combinación de menús.</span><span class="sxs-lookup"><span data-stu-id="926dd-199">In this walkthrough, you have created an MDI parent form with <xref:System.Windows.Forms.ToolStrip> controls and menu merging.</span></span> <span data-ttu-id="926dd-200">Puede usar la familia de controles de <xref:System.Windows.Forms.ToolStrip> para muchos otros propósitos:</span><span class="sxs-lookup"><span data-stu-id="926dd-200">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="926dd-201">Crear menús contextuales para los controles con <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="926dd-201">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="926dd-202">Para obtener más información, vea [información general sobre el componente ContextMenu](contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="926dd-202">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="926dd-203">Ha creado un formulario con un menú estándar rellenado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="926dd-203">Created a form with an automatically populated standard menu.</span></span> <span data-ttu-id="926dd-204">Para obtener más información, vea [Tutorial: proporcionar elementos de menú estándar a un formulario](walkthrough-providing-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="926dd-204">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>

- <span data-ttu-id="926dd-205">Dé a los <xref:System.Windows.Forms.ToolStrip> controles un aspecto profesional.</span><span class="sxs-lookup"><span data-stu-id="926dd-205">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="926dd-206">Para obtener más información, vea [Cómo: establecer el representador de ToolStrip para una aplicación](how-to-set-the-toolstrip-renderer-for-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="926dd-206">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="926dd-207">Consulte también</span><span class="sxs-lookup"><span data-stu-id="926dd-207">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="926dd-208">Crear formularios principales MDI</span><span class="sxs-lookup"><span data-stu-id="926dd-208">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="926dd-209">Crear formularios MDI secundarios</span><span class="sxs-lookup"><span data-stu-id="926dd-209">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="926dd-210">Insertar un elemento MenuStrip en un menú desplegable MDI</span><span class="sxs-lookup"><span data-stu-id="926dd-210">How to: Insert a MenuStrip into an MDI Drop-Down Menu</span></span>](how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)
- [<span data-ttu-id="926dd-211">ToolStrip (control)</span><span class="sxs-lookup"><span data-stu-id="926dd-211">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
