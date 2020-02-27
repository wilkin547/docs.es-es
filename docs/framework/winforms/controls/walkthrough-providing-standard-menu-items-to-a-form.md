---
title: 'Tutorial: Proporcionar elementos de menú estándar a un formulario'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- menu items [Windows Forms], standard
- toolbars [Windows Forms], walkthroughs
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: dac37d98-589e-4d6d-9673-6437e8943122
ms.openlocfilehash: ee80aad445c00bb4b98b49c80495fa512150bcef
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628779"
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a><span data-ttu-id="ec0fa-102">Tutorial: Proporcionar elementos de menú estándar a un formulario</span><span class="sxs-lookup"><span data-stu-id="ec0fa-102">Walkthrough: Providing Standard Menu Items to a Form</span></span>

<span data-ttu-id="ec0fa-103">Puede proporcionar un menú estándar para los formularios con el control <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>

<span data-ttu-id="ec0fa-104">En este tutorial se muestra cómo utilizar un control de <xref:System.Windows.Forms.MenuStrip> para crear un menú estándar.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-104">This walkthrough demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a standard menu.</span></span> <span data-ttu-id="ec0fa-105">El formulario también responde cuando un usuario selecciona un elemento de menú.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-105">The form also responds when a user selects a menu item.</span></span> <span data-ttu-id="ec0fa-106">En este tutorial se muestran las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="ec0fa-106">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="ec0fa-107">Crear un proyecto de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-107">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="ec0fa-108">Crear un menú estándar.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-108">Creating a standard menu.</span></span>

- <span data-ttu-id="ec0fa-109">Crear un control de <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-109">Creating a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

- <span data-ttu-id="ec0fa-110">Control de la selección de elementos de menú.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-110">Handling menu item selection.</span></span>

<span data-ttu-id="ec0fa-111">Cuando haya terminado, tendrá un formulario con un menú estándar que muestra las selecciones de elementos de menú en un control de <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-111">When you are finished, you will have a form with a standard menu that displays menu item selections in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

<span data-ttu-id="ec0fa-112">Para copiar el código de este tema como una sola lista, vea [Cómo: proporcionar elementos de menú estándar a un formulario](how-to-provide-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="ec0fa-112">To copy the code in this topic as a single listing, see [How to: Provide Standard Menu Items to a Form](how-to-provide-standard-menu-items-to-a-form.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ec0fa-113">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="ec0fa-113">Prerequisites</span></span>

<span data-ttu-id="ec0fa-114">Necesitará Visual Studio para completar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-114">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="ec0fa-115">Creación del proyecto</span><span class="sxs-lookup"><span data-stu-id="ec0fa-115">Create the project</span></span>

1. <span data-ttu-id="ec0fa-116">En Visual Studio, cree un proyecto de aplicación para Windows denominado **StandardMenuForm** (**archivo** > **nuevo** **proyecto** de >  > **Visual C#**  o **Visual Basic** > **aplicación**de **escritorio clásico** > Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-116">In Visual Studio, create a Windows application project called **StandardMenuForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="ec0fa-117">En el Diseñador de Windows Forms, seleccione el formulario.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-117">In the Windows Forms Designer, select the form.</span></span>

## <a name="create-a-standard-menu"></a><span data-ttu-id="ec0fa-118">Crear un menú estándar</span><span class="sxs-lookup"><span data-stu-id="ec0fa-118">Create a standard menu</span></span>

<span data-ttu-id="ec0fa-119">El Diseñador de Windows Forms puede rellenar automáticamente un control <xref:System.Windows.Forms.MenuStrip> con elementos de menú estándar.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-119">The Windows Forms Designer can automatically populate a <xref:System.Windows.Forms.MenuStrip> control with standard menu items.</span></span>

1. <span data-ttu-id="ec0fa-120">En el **cuadro de herramientas**, arrastre un control <xref:System.Windows.Forms.MenuStrip> al formulario.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-120">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto your form.</span></span>

2. <span data-ttu-id="ec0fa-121">Haga clic en el glifo de acciones del diseñador del <xref:System.Windows.Forms.MenuStrip> del control (![flecha negra pequeña](./media/designer-actions-glyph.gif)) y seleccione **insertar elementos estándar**.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-121">Click the <xref:System.Windows.Forms.MenuStrip> control's designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) and select **Insert Standard Items**.</span></span>

     <span data-ttu-id="ec0fa-122">El control <xref:System.Windows.Forms.MenuStrip> se rellena con los elementos de menú estándar.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-122">The <xref:System.Windows.Forms.MenuStrip> control is populated with the standard menu items.</span></span>

3. <span data-ttu-id="ec0fa-123">Haga clic en el elemento de menú **archivo** para ver sus elementos de menú predeterminados y sus iconos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-123">Click the **File** menu item to see its default menu items and corresponding icons.</span></span>

## <a name="create-a-statusstrip-control"></a><span data-ttu-id="ec0fa-124">Crear un control StatusStrip</span><span class="sxs-lookup"><span data-stu-id="ec0fa-124">Create a StatusStrip control</span></span>

<span data-ttu-id="ec0fa-125">Use el control <xref:System.Windows.Forms.StatusStrip> para mostrar el estado de las aplicaciones de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-125">Use the <xref:System.Windows.Forms.StatusStrip> control to display status for your Windows Forms applications.</span></span> <span data-ttu-id="ec0fa-126">En el ejemplo actual, los elementos de menú seleccionados por el usuario se muestran en un control de <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-126">In the current example, menu items selected by the user are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

1. <span data-ttu-id="ec0fa-127">En el **cuadro de herramientas**, arrastre un control <xref:System.Windows.Forms.StatusStrip> al formulario.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.StatusStrip> control onto your form.</span></span>

     <span data-ttu-id="ec0fa-128">El control <xref:System.Windows.Forms.StatusStrip> se acopla automáticamente a la parte inferior del formulario.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-128">The <xref:System.Windows.Forms.StatusStrip> control automatically docks to the bottom of the form.</span></span>

2. <span data-ttu-id="ec0fa-129">Haga clic en el botón desplegable del control de <xref:System.Windows.Forms.StatusStrip> y seleccione **StatusLabel** para agregar un control de <xref:System.Windows.Forms.ToolStripStatusLabel> al control de <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-129">Click the <xref:System.Windows.Forms.StatusStrip> control's drop-down button and select **StatusLabel** to add a <xref:System.Windows.Forms.ToolStripStatusLabel> control to the <xref:System.Windows.Forms.StatusStrip> control.</span></span>

## <a name="handle-item-selection"></a><span data-ttu-id="ec0fa-130">Controlar la selección de elementos</span><span class="sxs-lookup"><span data-stu-id="ec0fa-130">Handle item selection</span></span>

<span data-ttu-id="ec0fa-131">Controle el evento <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> para responder cuando el usuario selecciona un elemento de menú.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-131">Handle the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event to respond when the user selects a menu item.</span></span>

1. <span data-ttu-id="ec0fa-132">Haga clic en el elemento de menú **archivo** que creó en la sección crear un menú estándar.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-132">Click the **File** menu item that you created in the Creating a Standard Menu section.</span></span>

2. <span data-ttu-id="ec0fa-133">En la ventana **Propiedades**, haga clic en **Eventos**.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-133">In the **Properties** window, click **Events**.</span></span>

3. <span data-ttu-id="ec0fa-134">Haga doble clic en el evento <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-134">Double-click the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>

     <span data-ttu-id="ec0fa-135">El Diseñador de Windows Forms genera un controlador de eventos para el evento <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-135">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>

4. <span data-ttu-id="ec0fa-136">Inserte el código siguiente en el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-136">Insert the following code into the event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]

5. <span data-ttu-id="ec0fa-137">Inserte el `UpdateStatus` definición del método de utilidad en el formulario.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-137">Insert the `UpdateStatus` utility method definition into the form.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]

## <a name="checkpoint--test-your-form"></a><span data-ttu-id="ec0fa-138">Punto de control: prueba del formulario</span><span class="sxs-lookup"><span data-stu-id="ec0fa-138">Checkpoint -test your form</span></span>

1. <span data-ttu-id="ec0fa-139">Presione **F5** para compilar y ejecutar el formulario.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-139">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="ec0fa-140">Haga clic en el elemento de menú **archivo** para abrir el menú.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-140">Click the **File** menu item to open the menu.</span></span>

3. <span data-ttu-id="ec0fa-141">En el menú **archivo** , haga clic en uno de los elementos para seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-141">On the **File** menu, click one of the items to select it.</span></span>

     <span data-ttu-id="ec0fa-142">El control <xref:System.Windows.Forms.StatusStrip> muestra el elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-142">The <xref:System.Windows.Forms.StatusStrip> control displays the selected item.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ec0fa-143">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="ec0fa-143">Next steps</span></span>

<span data-ttu-id="ec0fa-144">En este tutorial, ha creado un formulario con un menú estándar.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-144">In this walkthrough, you have created a form with a standard menu.</span></span> <span data-ttu-id="ec0fa-145">Puede usar la familia de controles de <xref:System.Windows.Forms.ToolStrip> para muchos otros propósitos:</span><span class="sxs-lookup"><span data-stu-id="ec0fa-145">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="ec0fa-146">Crear menús contextuales para los controles con <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-146">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="ec0fa-147">Para obtener más información, vea [información general sobre el componente ContextMenu](contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="ec0fa-147">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="ec0fa-148">Cree un formulario de interfaz de múltiples documentos (MDI) con controles de acoplamiento <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-148">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="ec0fa-149">Para obtener más información, vea [Tutorial: crear un formulario MDI con combinación de menús y controles ToolStrip](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="ec0fa-149">For more information, see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

- <span data-ttu-id="ec0fa-150">Dé a los <xref:System.Windows.Forms.ToolStrip> controles un aspecto profesional.</span><span class="sxs-lookup"><span data-stu-id="ec0fa-150">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="ec0fa-151">Para obtener más información, vea [Cómo: establecer el representador de ToolStrip para una aplicación](how-to-set-the-toolstrip-renderer-for-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="ec0fa-151">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ec0fa-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ec0fa-152">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="ec0fa-153">MenuStrip (control)</span><span class="sxs-lookup"><span data-stu-id="ec0fa-153">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
