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
ms.openlocfilehash: 5853760231cbece27805923c009d83e16c9b0a5e
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211559"
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="095bc-102">Tutorial: Crear un formulario MDI con combinación de menús y controles ToolStrip</span><span class="sxs-lookup"><span data-stu-id="095bc-102">Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls</span></span>

<span data-ttu-id="095bc-103">El espacio de nombres <xref:System.Windows.Forms?displayProperty=nameWithType> es compatible con aplicaciones de interfaces de múltiples documentos (MDI) y el control <xref:System.Windows.Forms.MenuStrip> admite la combinación de menús.</span><span class="sxs-lookup"><span data-stu-id="095bc-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="095bc-104">Los formularios MDI también pueden ser compatibles con los controles <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="095bc-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>

<span data-ttu-id="095bc-105">Este tutorial muestra cómo usar <xref:System.Windows.Forms.ToolStripPanel> controles con un formulario MDI.</span><span class="sxs-lookup"><span data-stu-id="095bc-105">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="095bc-106">El formulario también admite la combinación de menús con menús secundarios.</span><span class="sxs-lookup"><span data-stu-id="095bc-106">The form also supports menu merging with child menus.</span></span> <span data-ttu-id="095bc-107">En este tutorial se muestran las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="095bc-107">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="095bc-108">Crear un proyecto de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="095bc-108">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="095bc-109">Crear el menú principal para el formulario.</span><span class="sxs-lookup"><span data-stu-id="095bc-109">Creating the main menu for your form.</span></span> <span data-ttu-id="095bc-110">El nombre real del menú variará.</span><span class="sxs-lookup"><span data-stu-id="095bc-110">The actual name of the menu will vary.</span></span>

- <span data-ttu-id="095bc-111">Agregar el <xref:System.Windows.Forms.ToolStripPanel> el control a la **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="095bc-111">Adding the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox**.</span></span>

- <span data-ttu-id="095bc-112">Creación de un formulario secundario.</span><span class="sxs-lookup"><span data-stu-id="095bc-112">Creating a child form.</span></span>

- <span data-ttu-id="095bc-113">Organizar <xref:System.Windows.Forms.ToolStripPanel> agrupar controles por orden z.</span><span class="sxs-lookup"><span data-stu-id="095bc-113">Arranging <xref:System.Windows.Forms.ToolStripPanel> controls by z-order.</span></span>

<span data-ttu-id="095bc-114">Cuando haya terminado, tendrá un formulario MDI que admite la combinación de menús y movibles <xref:System.Windows.Forms.ToolStrip> controles.</span><span class="sxs-lookup"><span data-stu-id="095bc-114">When you are finished, you will have an MDI form that supports menu merging and movable <xref:System.Windows.Forms.ToolStrip> controls.</span></span>

<span data-ttu-id="095bc-115">Para copiar el código de este tema como una sola lista, vea [Cómo: Crear un formulario MDI con combinación de menús y controles ToolStrip](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="095bc-115">To copy the code in this topic as a single listing, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="095bc-116">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="095bc-116">Prerequisites</span></span>

<span data-ttu-id="095bc-117">Necesitará Visual Studio para completar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="095bc-117">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="095bc-118">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="095bc-118">Create the project</span></span>

1. <span data-ttu-id="095bc-119">En Visual Studio, cree un proyecto de aplicación de Windows denominado **MDI** (**archivo** > **New** > **proyecto**  >  **Visual C#**  o **Visual Basic** > **escritorio clásico de**  >   **Aplicación de Windows Forms**).</span><span class="sxs-lookup"><span data-stu-id="095bc-119">In Visual Studio, create a Windows Application project called **MdiForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="095bc-120">En el Diseñador de formularios de Windows, seleccione el formulario.</span><span class="sxs-lookup"><span data-stu-id="095bc-120">In the Windows Forms Designer, select the form.</span></span>

3. <span data-ttu-id="095bc-121">En la ventana Propiedades, establezca el valor de la <xref:System.Windows.Forms.Form.IsMdiContainer%2A> a `true`.</span><span class="sxs-lookup"><span data-stu-id="095bc-121">In the Properties window, set the value of the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> to `true`.</span></span>

## <a name="create-the-main-menu"></a><span data-ttu-id="095bc-122">Crear el menú principal</span><span class="sxs-lookup"><span data-stu-id="095bc-122">Create the main menu</span></span>

<span data-ttu-id="095bc-123">El formulario MDI principal contiene el menú principal.</span><span class="sxs-lookup"><span data-stu-id="095bc-123">The parent MDI form contains the main menu.</span></span> <span data-ttu-id="095bc-124">El menú principal tiene un elemento de menú denominado **ventana**.</span><span class="sxs-lookup"><span data-stu-id="095bc-124">The main menu has one menu item named **Window**.</span></span> <span data-ttu-id="095bc-125">Con el **ventana** elemento de menú, puede crear formularios secundarios.</span><span class="sxs-lookup"><span data-stu-id="095bc-125">With the **Window** menu item, you can create child forms.</span></span> <span data-ttu-id="095bc-126">Los elementos de menú de formularios secundarios se combinan en el menú principal.</span><span class="sxs-lookup"><span data-stu-id="095bc-126">Menu items from child forms are merged into the main menu.</span></span>

1. <span data-ttu-id="095bc-127">Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.MenuStrip> al formulario.</span><span class="sxs-lookup"><span data-stu-id="095bc-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the form.</span></span>

2. <span data-ttu-id="095bc-128">Agregar un <xref:System.Windows.Forms.ToolStripMenuItem> a la <xref:System.Windows.Forms.MenuStrip> controlar y asígnele el nombre **ventana**.</span><span class="sxs-lookup"><span data-stu-id="095bc-128">Add a <xref:System.Windows.Forms.ToolStripMenuItem> to the <xref:System.Windows.Forms.MenuStrip> control and name it **Window**.</span></span>

3. <span data-ttu-id="095bc-129">Seleccione el control <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="095bc-129">Select the <xref:System.Windows.Forms.MenuStrip> control.</span></span>

4. <span data-ttu-id="095bc-130">En la ventana Propiedades, establezca el valor de la <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> propiedad `ToolStripMenuItem1`.</span><span class="sxs-lookup"><span data-stu-id="095bc-130">In the Properties window, set the value of the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to `ToolStripMenuItem1`.</span></span>

5. <span data-ttu-id="095bc-131">Agregar un subelemento a la **ventana** elemento de menú y, a continuación, el nombre del subelemento **New**.</span><span class="sxs-lookup"><span data-stu-id="095bc-131">Add a subitem to the **Window** menu item, and then name the subitem **New**.</span></span>

6. <span data-ttu-id="095bc-132">En la ventana Propiedades, haga clic en **eventos**.</span><span class="sxs-lookup"><span data-stu-id="095bc-132">In the Properties window, click **Events**.</span></span>

7. <span data-ttu-id="095bc-133">Haga doble clic en el <xref:System.Windows.Forms.ToolStripItem.Click> eventos.</span><span class="sxs-lookup"><span data-stu-id="095bc-133">Double-click the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>

     <span data-ttu-id="095bc-134">El Diseñador de Windows Forms genera un controlador de eventos para el <xref:System.Windows.Forms.ToolStripItem.Click> eventos.</span><span class="sxs-lookup"><span data-stu-id="095bc-134">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>

8. <span data-ttu-id="095bc-135">Inserte el código siguiente en el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="095bc-135">Insert the following code into the event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]

## <a name="add-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="095bc-136">Agregar el control ToolStripPanel al cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="095bc-136">Add the ToolStripPanel control to the Toolbox</span></span>

<span data-ttu-id="095bc-137">Cuando usas <xref:System.Windows.Forms.MenuStrip> controles con un formulario MDI que debe tener el <xref:System.Windows.Forms.ToolStripPanel> control.</span><span class="sxs-lookup"><span data-stu-id="095bc-137">When you use <xref:System.Windows.Forms.MenuStrip> controls with an MDI form you must have the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="095bc-138">Debe agregar el <xref:System.Windows.Forms.ToolStripPanel> el control a la **cuadro de herramientas** para crear el formulario MDI en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="095bc-138">You must add the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox** to build your MDI form in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="095bc-139">Abra el **cuadro de herramientas**y, a continuación, haga clic en el **todos los formularios de Windows** pestaña para mostrar los controles de formularios de Windows disponibles.</span><span class="sxs-lookup"><span data-stu-id="095bc-139">Open the **Toolbox**, and then click the **All Windows Forms** tab to show the available Windows Forms controls.</span></span>

2. <span data-ttu-id="095bc-140">Haga doble clic para abrir el menú contextual y seleccione **elegir elementos**.</span><span class="sxs-lookup"><span data-stu-id="095bc-140">Right-click to open the shortcut menu, and select **Choose Items**.</span></span>

3. <span data-ttu-id="095bc-141">En el **elegir elementos del cuadro de herramientas** cuadro de diálogo, desplácese hacia abajo el **nombre** columna hasta que encuentre **ToolStripPanel**.</span><span class="sxs-lookup"><span data-stu-id="095bc-141">In the **Choose Toolbox Items** dialog box, scroll down the **Name** column until you find **ToolStripPanel**.</span></span>

4. <span data-ttu-id="095bc-142">Seleccione la casilla de verificación por **ToolStripPanel**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="095bc-142">Select the check box by **ToolStripPanel**, and then click **OK**.</span></span>

     <span data-ttu-id="095bc-143">El <xref:System.Windows.Forms.ToolStripPanel> control aparece en el **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="095bc-143">The <xref:System.Windows.Forms.ToolStripPanel> control appears in the **Toolbox**.</span></span>

## <a name="create-a-child-form"></a><span data-ttu-id="095bc-144">Crear un formulario secundario</span><span class="sxs-lookup"><span data-stu-id="095bc-144">Create a child form</span></span>

<span data-ttu-id="095bc-145">En este procedimiento, definirá una clase de formulario secundario independiente que tiene su propio <xref:System.Windows.Forms.MenuStrip> control.</span><span class="sxs-lookup"><span data-stu-id="095bc-145">In this procedure, you will define a separate child form class that has its own <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="095bc-146">Los elementos de menú para este formulario se combinan con los del formulario primario.</span><span class="sxs-lookup"><span data-stu-id="095bc-146">The menu items for this form are merged with those of the parent form.</span></span>

1. <span data-ttu-id="095bc-147">Agregue un nuevo formulario denominado `ChildForm` al proyecto.</span><span class="sxs-lookup"><span data-stu-id="095bc-147">Add a new form named `ChildForm` to the project.</span></span>

     <span data-ttu-id="095bc-148">Para obtener más información, vea [Cómo: Agregar Windows Forms a un proyecto](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="095bc-148">For more information, see [How to: Add Windows Forms to a Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100)).</span></span>

2. <span data-ttu-id="095bc-149">Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.MenuStrip> al formulario secundario.</span><span class="sxs-lookup"><span data-stu-id="095bc-149">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the child form.</span></span>

3. <span data-ttu-id="095bc-150">Haga clic en el <xref:System.Windows.Forms.MenuStrip> glifo de etiqueta inteligente del control (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) y, a continuación, seleccione **editar elementos**.</span><span class="sxs-lookup"><span data-stu-id="095bc-150">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), and then select **Edit Items**.</span></span>

4. <span data-ttu-id="095bc-151">En el **Editor de la colección de elementos** diálogo cuadro, agregue un nuevo <xref:System.Windows.Forms.ToolStripMenuItem> denominado **ChildMenuItem** en el menú secundario.</span><span class="sxs-lookup"><span data-stu-id="095bc-151">In the **Items Collection Editor** dialog box, add a new <xref:System.Windows.Forms.ToolStripMenuItem> named **ChildMenuItem** to the child menu.</span></span>

     <span data-ttu-id="095bc-152">Para obtener más información, consulte [Editor de colección de elementos ToolStrip](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="095bc-152">For more information, see [ToolStrip Items Collection Editor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100)).</span></span>

## <a name="test-the-form"></a><span data-ttu-id="095bc-153">Comprobar el formulario</span><span class="sxs-lookup"><span data-stu-id="095bc-153">Test the form</span></span>

1. <span data-ttu-id="095bc-154">Presione **F5** para compilar y ejecutar el formulario.</span><span class="sxs-lookup"><span data-stu-id="095bc-154">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="095bc-155">Haga clic en el **ventana** elemento de menú para abrir el menú y, a continuación, haga clic en **New**.</span><span class="sxs-lookup"><span data-stu-id="095bc-155">Click the **Window** menu item to open the menu, and then click **New**.</span></span>

     <span data-ttu-id="095bc-156">Se crea un nuevo formulario secundario en el área de cliente del formulario MDI.</span><span class="sxs-lookup"><span data-stu-id="095bc-156">A new child form is created in the form's MDI client area.</span></span> <span data-ttu-id="095bc-157">Menú del formulario secundario se combina con el menú principal.</span><span class="sxs-lookup"><span data-stu-id="095bc-157">The child form's menu is merged with the main menu.</span></span>

3. <span data-ttu-id="095bc-158">Cierre el formulario secundario.</span><span class="sxs-lookup"><span data-stu-id="095bc-158">Close the child form.</span></span>

     <span data-ttu-id="095bc-159">Menú del formulario secundario se quita en el menú principal.</span><span class="sxs-lookup"><span data-stu-id="095bc-159">The child form's menu is removed from the main menu.</span></span>

4. <span data-ttu-id="095bc-160">Haga clic en **New** varias veces.</span><span class="sxs-lookup"><span data-stu-id="095bc-160">Click **New** several times.</span></span>

     <span data-ttu-id="095bc-161">Los formularios secundarios aparecen automáticamente en el **ventana** elemento de menú porque la <xref:System.Windows.Forms.MenuStrip> del control <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> se asigna la propiedad.</span><span class="sxs-lookup"><span data-stu-id="095bc-161">The child forms are automatically listed under the **Window** menu item because the <xref:System.Windows.Forms.MenuStrip> control's <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property is assigned.</span></span>

## <a name="add-toolstrip-support"></a><span data-ttu-id="095bc-162">Agregar compatibilidad de ToolStrip</span><span class="sxs-lookup"><span data-stu-id="095bc-162">Add ToolStrip support</span></span>

<span data-ttu-id="095bc-163">En este procedimiento, agregará cuatro <xref:System.Windows.Forms.ToolStrip> controles al formulario primario MDI.</span><span class="sxs-lookup"><span data-stu-id="095bc-163">In this procedure, you will add four <xref:System.Windows.Forms.ToolStrip> controls to the MDI parent form.</span></span> <span data-ttu-id="095bc-164">Cada <xref:System.Windows.Forms.ToolStrip> se agrega el control dentro de un <xref:System.Windows.Forms.ToolStripPanel> control, que está acoplada al borde del formulario.</span><span class="sxs-lookup"><span data-stu-id="095bc-164">Each <xref:System.Windows.Forms.ToolStrip> control is added inside a <xref:System.Windows.Forms.ToolStripPanel> control, which is docked to the edge of the form.</span></span>

1. <span data-ttu-id="095bc-165">Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.ToolStripPanel> al formulario.</span><span class="sxs-lookup"><span data-stu-id="095bc-165">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStripPanel> control onto the form.</span></span>

2. <span data-ttu-id="095bc-166">Con el <xref:System.Windows.Forms.ToolStripPanel> control seleccionado, haga doble clic en el <xref:System.Windows.Forms.ToolStrip> en controlar la **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="095bc-166">With the <xref:System.Windows.Forms.ToolStripPanel> control selected, double-click the <xref:System.Windows.Forms.ToolStrip> control in the **Toolbox**.</span></span>

     <span data-ttu-id="095bc-167">Un <xref:System.Windows.Forms.ToolStrip> control se crea en el <xref:System.Windows.Forms.ToolStripPanel> control.</span><span class="sxs-lookup"><span data-stu-id="095bc-167">A <xref:System.Windows.Forms.ToolStrip> control is created in the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

3. <span data-ttu-id="095bc-168">Seleccione el control <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="095bc-168">Select the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

4. <span data-ttu-id="095bc-169">En la ventana Propiedades, cambie el valor del control <xref:System.Windows.Forms.Control.Dock%2A> propiedad <xref:System.Windows.Forms.DockStyle.Left>.</span><span class="sxs-lookup"><span data-stu-id="095bc-169">In the Properties window, change the value of the control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Left>.</span></span>

     <span data-ttu-id="095bc-170">El <xref:System.Windows.Forms.ToolStripPanel> controlar lo acopla en el lado izquierdo del formulario, bajo el menú principal.</span><span class="sxs-lookup"><span data-stu-id="095bc-170">The <xref:System.Windows.Forms.ToolStripPanel> control docks to the left side of the form, underneath the main menu.</span></span> <span data-ttu-id="095bc-171">El área de cliente MDI cambia de tamaño para ajustarse a la <xref:System.Windows.Forms.ToolStripPanel> control.</span><span class="sxs-lookup"><span data-stu-id="095bc-171">The MDI client area resizes to fit the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

5. <span data-ttu-id="095bc-172">Repita los pasos 1 a 4.</span><span class="sxs-lookup"><span data-stu-id="095bc-172">Repeat steps 1 through 4.</span></span>

     <span data-ttu-id="095bc-173">Acoplar el nuevo <xref:System.Windows.Forms.ToolStripPanel> control a la parte superior del formulario.</span><span class="sxs-lookup"><span data-stu-id="095bc-173">Dock the new <xref:System.Windows.Forms.ToolStripPanel> control to the top of the form.</span></span>

     <span data-ttu-id="095bc-174">El <xref:System.Windows.Forms.ToolStripPanel> está acoplado el control bajo el menú principal, pero a la derecha de la primera <xref:System.Windows.Forms.ToolStripPanel> control.</span><span class="sxs-lookup"><span data-stu-id="095bc-174">The <xref:System.Windows.Forms.ToolStripPanel> control is docked underneath the main menu, but to the right of the first <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="095bc-175">Este paso muestra la importancia del orden z para colocar correctamente <xref:System.Windows.Forms.ToolStripPanel> controles.</span><span class="sxs-lookup"><span data-stu-id="095bc-175">This step illustrates the importance of z-order in correctly positioning <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>

6. <span data-ttu-id="095bc-176">Repita los pasos del 1 al 4 para dos más <xref:System.Windows.Forms.ToolStripPanel> controles.</span><span class="sxs-lookup"><span data-stu-id="095bc-176">Repeat steps 1 through 4 for two more <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>

     <span data-ttu-id="095bc-177">Acoplar el nuevo <xref:System.Windows.Forms.ToolStripPanel> controles a la derecha e inferior del formulario.</span><span class="sxs-lookup"><span data-stu-id="095bc-177">Dock the new <xref:System.Windows.Forms.ToolStripPanel> controls to the right and bottom of the form.</span></span>

## <a name="arrange-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="095bc-178">Organizar los controles ToolStripPanel por orden Z</span><span class="sxs-lookup"><span data-stu-id="095bc-178">Arrange ToolStripPanel controls by Z-order</span></span>

<span data-ttu-id="095bc-179">La posición de un acoplado <xref:System.Windows.Forms.ToolStripPanel> control en el formulario MDI viene determinada por la posición del control en el orden z.</span><span class="sxs-lookup"><span data-stu-id="095bc-179">The position of a docked <xref:System.Windows.Forms.ToolStripPanel> control on your MDI form is determined by the control's position in the z-order.</span></span> <span data-ttu-id="095bc-180">Puede organizar fácilmente el orden z de los controles en la ventana Esquema del documento.</span><span class="sxs-lookup"><span data-stu-id="095bc-180">You can easily arrange the z-order of your controls in the Document Outline window.</span></span>

1. <span data-ttu-id="095bc-181">En el **vista** menú, haga clic en **Other Windows**y, a continuación, haga clic en **esquema del documento**.</span><span class="sxs-lookup"><span data-stu-id="095bc-181">In the **View** menu, click **Other Windows**, and then click **Document Outline**.</span></span>

     <span data-ttu-id="095bc-182">La organización de su <xref:System.Windows.Forms.ToolStripPanel> controles desde el procedimiento anterior no es estándar.</span><span class="sxs-lookup"><span data-stu-id="095bc-182">The arrangement of your <xref:System.Windows.Forms.ToolStripPanel> controls from the previous procedure is nonstandard.</span></span> <span data-ttu-id="095bc-183">Esto es porque el orden z no es correcto.</span><span class="sxs-lookup"><span data-stu-id="095bc-183">This is because the z-order is not correct.</span></span> <span data-ttu-id="095bc-184">Utilice la ventana Esquema del documento para cambiar el orden z de los controles.</span><span class="sxs-lookup"><span data-stu-id="095bc-184">Use the Document Outline window to change the z-order of the controls.</span></span>

2. <span data-ttu-id="095bc-185">En la ventana Esquema del documento, seleccione **ToolStripPanel4**.</span><span class="sxs-lookup"><span data-stu-id="095bc-185">In the Document Outline window, select **ToolStripPanel4**.</span></span>

3. <span data-ttu-id="095bc-186">Haga clic en el botón de flecha abajo varias veces, hasta **ToolStripPanel4** en la parte inferior de la lista.</span><span class="sxs-lookup"><span data-stu-id="095bc-186">Click the down-arrow button repeatedly, until **ToolStripPanel4** is at the bottom of the list.</span></span>

     <span data-ttu-id="095bc-187">El **ToolStripPanel4** está acoplado el control a la parte inferior del formulario, debajo de los demás controles.</span><span class="sxs-lookup"><span data-stu-id="095bc-187">The **ToolStripPanel4** control is docked to the bottom of the form, underneath the other controls.</span></span>

4. <span data-ttu-id="095bc-188">Seleccione **ToolStripPanel2**.</span><span class="sxs-lookup"><span data-stu-id="095bc-188">Select **ToolStripPanel2**.</span></span>

5. <span data-ttu-id="095bc-189">Haga clic en el botón de flecha hacia abajo una vez para colocar el control en tercer lugar en la lista.</span><span class="sxs-lookup"><span data-stu-id="095bc-189">Click the down-arrow button one time to position the control third in the list.</span></span>

     <span data-ttu-id="095bc-190">El **ToolStripPanel2** está acoplado el control a la parte superior del formulario, bajo el menú principal y encima de los otros controles.</span><span class="sxs-lookup"><span data-stu-id="095bc-190">The **ToolStripPanel2** control is docked to the top of the form, underneath the main menu and above the other controls.</span></span>

6. <span data-ttu-id="095bc-191">Seleccione los distintos controles en el **esquema del documento** ventana y moverlos a distintas posiciones en el orden z.</span><span class="sxs-lookup"><span data-stu-id="095bc-191">Select various controls in the **Document Outline** window and move them to different positions in the z-order.</span></span> <span data-ttu-id="095bc-192">Tenga en cuenta el efecto del orden z de colocación de los controles acoplados.</span><span class="sxs-lookup"><span data-stu-id="095bc-192">Note the effect of the z-order on the placement of docked controls.</span></span> <span data-ttu-id="095bc-193">Utilice CTRL-Z o **deshacer** en el **editar** menú Deshacer los cambios.</span><span class="sxs-lookup"><span data-stu-id="095bc-193">Use CTRL-Z or **Undo** on the **Edit** menu to undo your changes.</span></span>

## <a name="checkpoint---test-your-form"></a><span data-ttu-id="095bc-194">Punto de comprobación: probar el formulario</span><span class="sxs-lookup"><span data-stu-id="095bc-194">Checkpoint - test your form</span></span>

1. <span data-ttu-id="095bc-195">Presione **F5** para compilar y ejecutar el formulario.</span><span class="sxs-lookup"><span data-stu-id="095bc-195">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="095bc-196">Haga clic en el control de un <xref:System.Windows.Forms.ToolStrip> control y arrastre el control a otras posiciones en el formulario.</span><span class="sxs-lookup"><span data-stu-id="095bc-196">Click the grip of a <xref:System.Windows.Forms.ToolStrip> control and drag the control to different positions on the form.</span></span>

     <span data-ttu-id="095bc-197">Puede arrastrar un <xref:System.Windows.Forms.ToolStrip> control desde uno <xref:System.Windows.Forms.ToolStripPanel> control a otro.</span><span class="sxs-lookup"><span data-stu-id="095bc-197">You can drag a <xref:System.Windows.Forms.ToolStrip> control from one <xref:System.Windows.Forms.ToolStripPanel> control to another.</span></span>

## <a name="next-steps"></a><span data-ttu-id="095bc-198">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="095bc-198">Next steps</span></span>

<span data-ttu-id="095bc-199">En este tutorial, ha creado un formulario MDI principal con <xref:System.Windows.Forms.ToolStrip> controles y combinación de menús.</span><span class="sxs-lookup"><span data-stu-id="095bc-199">In this walkthrough, you have created an MDI parent form with <xref:System.Windows.Forms.ToolStrip> controls and menu merging.</span></span> <span data-ttu-id="095bc-200">Puede usar el <xref:System.Windows.Forms.ToolStrip> familia de controles para muchos otros objetivos:</span><span class="sxs-lookup"><span data-stu-id="095bc-200">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="095bc-201">Crear menús contextuales para los controles con <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="095bc-201">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="095bc-202">Para obtener más información, consulte [información general del componente ContextMenu](contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="095bc-202">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="095bc-203">Crea un formulario con un menú estándar rellenado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="095bc-203">Created a form with an automatically populated standard menu.</span></span> <span data-ttu-id="095bc-204">Para obtener más información, vea [Tutorial: Proporcionar elementos de menú estándar a un formulario](walkthrough-providing-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="095bc-204">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>

- <span data-ttu-id="095bc-205">Asigne a su <xref:System.Windows.Forms.ToolStrip> controla un aspecto profesional.</span><span class="sxs-lookup"><span data-stu-id="095bc-205">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="095bc-206">Para obtener más información, vea [Cómo: Establecer la representación de ToolStrip para una aplicación](how-to-set-the-toolstrip-renderer-for-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="095bc-206">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="095bc-207">Vea también</span><span class="sxs-lookup"><span data-stu-id="095bc-207">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="095bc-208">Cómo: Crear formularios principales MDI</span><span class="sxs-lookup"><span data-stu-id="095bc-208">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="095bc-209">Cómo: Crear formularios MDI secundarios</span><span class="sxs-lookup"><span data-stu-id="095bc-209">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="095bc-210">Cómo: Insertar un elemento MenuStrip en un menú desplegable MDI</span><span class="sxs-lookup"><span data-stu-id="095bc-210">How to: Insert a MenuStrip into an MDI Drop-Down Menu</span></span>](how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)
- [<span data-ttu-id="095bc-211">Control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="095bc-211">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
