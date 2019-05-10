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
ms.openlocfilehash: ebfacadfee3ea069359a72ea0402751e9e6280d7
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211507"
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a><span data-ttu-id="d7a32-102">Tutorial: Proporcionar elementos de menú estándar a un formulario</span><span class="sxs-lookup"><span data-stu-id="d7a32-102">Walkthrough: Providing Standard Menu Items to a Form</span></span>

<span data-ttu-id="d7a32-103">Puede proporcionar un menú estándar para los formularios con el control <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="d7a32-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>

<span data-ttu-id="d7a32-104">Este tutorial muestra cómo usar un <xref:System.Windows.Forms.MenuStrip> control para crear un menú estándar.</span><span class="sxs-lookup"><span data-stu-id="d7a32-104">This walkthrough demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a standard menu.</span></span> <span data-ttu-id="d7a32-105">El formulario también responde cuando un usuario selecciona un elemento de menú.</span><span class="sxs-lookup"><span data-stu-id="d7a32-105">The form also responds when a user selects a menu item.</span></span> <span data-ttu-id="d7a32-106">En este tutorial se muestran las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="d7a32-106">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="d7a32-107">Crear un proyecto de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d7a32-107">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="d7a32-108">Crear un menú estándar.</span><span class="sxs-lookup"><span data-stu-id="d7a32-108">Creating a standard menu.</span></span>

- <span data-ttu-id="d7a32-109">Creación de un <xref:System.Windows.Forms.StatusStrip> control.</span><span class="sxs-lookup"><span data-stu-id="d7a32-109">Creating a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

- <span data-ttu-id="d7a32-110">Control de selección de elementos de menú.</span><span class="sxs-lookup"><span data-stu-id="d7a32-110">Handling menu item selection.</span></span>

<span data-ttu-id="d7a32-111">Cuando haya terminado, tendrá un formulario con un menú estándar que muestra las selecciones de elementos de menú en un <xref:System.Windows.Forms.StatusStrip> control.</span><span class="sxs-lookup"><span data-stu-id="d7a32-111">When you are finished, you will have a form with a standard menu that displays menu item selections in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

<span data-ttu-id="d7a32-112">Para copiar el código de este tema como una sola lista, vea [Cómo: Proporcionar elementos de menú estándar a un formulario](how-to-provide-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="d7a32-112">To copy the code in this topic as a single listing, see [How to: Provide Standard Menu Items to a Form](how-to-provide-standard-menu-items-to-a-form.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d7a32-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d7a32-113">Prerequisites</span></span>

<span data-ttu-id="d7a32-114">Necesitará Visual Studio para completar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="d7a32-114">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="d7a32-115">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="d7a32-115">Create the project</span></span>

1. <span data-ttu-id="d7a32-116">En Visual Studio, cree un proyecto de aplicación de Windows denominado **StandardMenuForm** (**archivo** > **New** > **proyecto**   >  **Visual C#**  o **Visual Basic** > **escritorio clásico de**  >  **Aplicación de Windows Forms**).</span><span class="sxs-lookup"><span data-stu-id="d7a32-116">In Visual Studio, create a Windows application project called **StandardMenuForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="d7a32-117">En el Diseñador de formularios de Windows, seleccione el formulario.</span><span class="sxs-lookup"><span data-stu-id="d7a32-117">In the Windows Forms Designer, select the form.</span></span>

## <a name="create-a-standard-menu"></a><span data-ttu-id="d7a32-118">Crear un menú estándar</span><span class="sxs-lookup"><span data-stu-id="d7a32-118">Create a standard menu</span></span>

<span data-ttu-id="d7a32-119">El Diseñador de Windows Forms puede rellenar automáticamente un <xref:System.Windows.Forms.MenuStrip> control con elementos de menú estándar.</span><span class="sxs-lookup"><span data-stu-id="d7a32-119">The Windows Forms Designer can automatically populate a <xref:System.Windows.Forms.MenuStrip> control with standard menu items.</span></span>

1. <span data-ttu-id="d7a32-120">Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.MenuStrip> control al formulario.</span><span class="sxs-lookup"><span data-stu-id="d7a32-120">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto your form.</span></span>

2. <span data-ttu-id="d7a32-121">Haga clic en el <xref:System.Windows.Forms.MenuStrip> glifo de etiqueta inteligente del control (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) y seleccione **insertar elementos estándar**.</span><span class="sxs-lookup"><span data-stu-id="d7a32-121">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) and select **Insert Standard Items**.</span></span>

     <span data-ttu-id="d7a32-122">El <xref:System.Windows.Forms.MenuStrip> control se rellena con los elementos de menú estándar.</span><span class="sxs-lookup"><span data-stu-id="d7a32-122">The <xref:System.Windows.Forms.MenuStrip> control is populated with the standard menu items.</span></span>

3. <span data-ttu-id="d7a32-123">Haga clic en el **archivo** elemento de menú para ver sus elementos de menú predeterminados y los iconos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="d7a32-123">Click the **File** menu item to see its default menu items and corresponding icons.</span></span>

## <a name="create-a-statusstrip-control"></a><span data-ttu-id="d7a32-124">Crear un control StatusStrip</span><span class="sxs-lookup"><span data-stu-id="d7a32-124">Create a StatusStrip control</span></span>

<span data-ttu-id="d7a32-125">Use el <xref:System.Windows.Forms.StatusStrip> control para mostrar el estado de las aplicaciones de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d7a32-125">Use the <xref:System.Windows.Forms.StatusStrip> control to display status for your Windows Forms applications.</span></span> <span data-ttu-id="d7a32-126">En el ejemplo actual, se muestran los elementos de menú seleccionados por el usuario en un <xref:System.Windows.Forms.StatusStrip> control.</span><span class="sxs-lookup"><span data-stu-id="d7a32-126">In the current example, menu items selected by the user are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

1. <span data-ttu-id="d7a32-127">Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.StatusStrip> control al formulario.</span><span class="sxs-lookup"><span data-stu-id="d7a32-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.StatusStrip> control onto your form.</span></span>

     <span data-ttu-id="d7a32-128">El <xref:System.Windows.Forms.StatusStrip> control se acopla automáticamente a la parte inferior del formulario.</span><span class="sxs-lookup"><span data-stu-id="d7a32-128">The <xref:System.Windows.Forms.StatusStrip> control automatically docks to the bottom of the form.</span></span>

2. <span data-ttu-id="d7a32-129">Haga clic en el <xref:System.Windows.Forms.StatusStrip> del control de botón de lista desplegable y seleccione **StatusLabel como** para agregar un <xref:System.Windows.Forms.ToolStripStatusLabel> el control a la <xref:System.Windows.Forms.StatusStrip> control.</span><span class="sxs-lookup"><span data-stu-id="d7a32-129">Click the <xref:System.Windows.Forms.StatusStrip> control's drop-down button and select **StatusLabel** to add a <xref:System.Windows.Forms.ToolStripStatusLabel> control to the <xref:System.Windows.Forms.StatusStrip> control.</span></span>

## <a name="handle-item-selection"></a><span data-ttu-id="d7a32-130">Controlar la selección de elementos</span><span class="sxs-lookup"><span data-stu-id="d7a32-130">Handle item selection</span></span>

<span data-ttu-id="d7a32-131">Controlar la <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> eventos para responder cuando el usuario selecciona un elemento de menú.</span><span class="sxs-lookup"><span data-stu-id="d7a32-131">Handle the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event to respond when the user selects a menu item.</span></span>

1. <span data-ttu-id="d7a32-132">Haga clic en el **archivo** elemento de menú que creó en la creación una sección de menú estándar.</span><span class="sxs-lookup"><span data-stu-id="d7a32-132">Click the **File** menu item that you created in the Creating a Standard Menu section.</span></span>

2. <span data-ttu-id="d7a32-133">En la ventana **Propiedades**, haga clic en **Eventos**.</span><span class="sxs-lookup"><span data-stu-id="d7a32-133">In the **Properties** window, click **Events**.</span></span>

3. <span data-ttu-id="d7a32-134">Haga doble clic en el <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> eventos.</span><span class="sxs-lookup"><span data-stu-id="d7a32-134">Double-click the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>

     <span data-ttu-id="d7a32-135">El Diseñador de Windows Forms genera un controlador de eventos para el <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> eventos.</span><span class="sxs-lookup"><span data-stu-id="d7a32-135">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>

4. <span data-ttu-id="d7a32-136">Inserte el código siguiente en el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="d7a32-136">Insert the following code into the event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]

5. <span data-ttu-id="d7a32-137">Insertar el `UpdateStatus` definición de método de utilidad en el formulario.</span><span class="sxs-lookup"><span data-stu-id="d7a32-137">Insert the `UpdateStatus` utility method definition into the form.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]

## <a name="checkpoint--test-your-form"></a><span data-ttu-id="d7a32-138">Punto de comprobación: probar el formulario</span><span class="sxs-lookup"><span data-stu-id="d7a32-138">Checkpoint -test your form</span></span>

1. <span data-ttu-id="d7a32-139">Presione **F5** para compilar y ejecutar el formulario.</span><span class="sxs-lookup"><span data-stu-id="d7a32-139">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="d7a32-140">Haga clic en el **archivo** elemento de menú para abrir el menú.</span><span class="sxs-lookup"><span data-stu-id="d7a32-140">Click the **File** menu item to open the menu.</span></span>

3. <span data-ttu-id="d7a32-141">En el **archivo** menú, haga clic en uno de los elementos para seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="d7a32-141">On the **File** menu, click one of the items to select it.</span></span>

     <span data-ttu-id="d7a32-142">El <xref:System.Windows.Forms.StatusStrip> control muestra el elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="d7a32-142">The <xref:System.Windows.Forms.StatusStrip> control displays the selected item.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d7a32-143">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="d7a32-143">Next steps</span></span>

<span data-ttu-id="d7a32-144">En este tutorial, ha creado un formulario con un menú estándar.</span><span class="sxs-lookup"><span data-stu-id="d7a32-144">In this walkthrough, you have created a form with a standard menu.</span></span> <span data-ttu-id="d7a32-145">Puede usar el <xref:System.Windows.Forms.ToolStrip> familia de controles para muchos otros objetivos:</span><span class="sxs-lookup"><span data-stu-id="d7a32-145">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="d7a32-146">Crear menús contextuales para los controles con <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="d7a32-146">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="d7a32-147">Para obtener más información, consulte [información general del componente ContextMenu](contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="d7a32-147">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="d7a32-148">Crear un formulario de múltiples documentos (MDI) de la interfaz con acoplamiento <xref:System.Windows.Forms.ToolStrip> controles.</span><span class="sxs-lookup"><span data-stu-id="d7a32-148">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="d7a32-149">Para obtener más información, vea [Tutorial: Crear un formulario MDI con combinación de menús y controles ToolStrip](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="d7a32-149">For more information, see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

- <span data-ttu-id="d7a32-150">Asigne a su <xref:System.Windows.Forms.ToolStrip> controla un aspecto profesional.</span><span class="sxs-lookup"><span data-stu-id="d7a32-150">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="d7a32-151">Para obtener más información, vea [Cómo: Establecer la representación de ToolStrip para una aplicación](how-to-set-the-toolstrip-renderer-for-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="d7a32-151">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d7a32-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7a32-152">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="d7a32-153">Control MenuStrip</span><span class="sxs-lookup"><span data-stu-id="d7a32-153">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
