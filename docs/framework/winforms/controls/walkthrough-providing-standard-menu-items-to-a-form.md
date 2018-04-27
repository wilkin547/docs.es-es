---
title: 'Tutorial: Proporcionar elementos de menú estándar a un formulario'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- menu items [Windows Forms], standard
- toolbars [Windows Forms], walkthroughs
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: dac37d98-589e-4d6d-9673-6437e8943122
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 00988266804207e85bc715342f888fd29348066e
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a><span data-ttu-id="3b2ee-102">Tutorial: Proporcionar elementos de menú estándar a un formulario</span><span class="sxs-lookup"><span data-stu-id="3b2ee-102">Walkthrough: Providing Standard Menu Items to a Form</span></span>
<span data-ttu-id="3b2ee-103">Puede proporcionar un menú estándar para los formularios con el control <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="3b2ee-104">Este tutorial muestra cómo utilizar un <xref:System.Windows.Forms.MenuStrip> control para crear un menú estándar.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-104">This walkthrough demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a standard menu.</span></span> <span data-ttu-id="3b2ee-105">El formulario también responde cuando un usuario selecciona un elemento de menú.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-105">The form also responds when a user selects a menu item.</span></span> <span data-ttu-id="3b2ee-106">En este tutorial se muestran las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="3b2ee-106">The following tasks are illustrated in this walkthrough:</span></span>  
  
-   <span data-ttu-id="3b2ee-107">Crear un proyecto de formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-107">Creating a Windows Forms project.</span></span>  
  
-   <span data-ttu-id="3b2ee-108">Crear un menú estándar.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-108">Creating a standard menu.</span></span>  
  
-   <span data-ttu-id="3b2ee-109">Crear un <xref:System.Windows.Forms.StatusStrip> control.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-109">Creating a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
-   <span data-ttu-id="3b2ee-110">Control de selección de elementos de menú.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-110">Handling menu item selection.</span></span>  
  
 <span data-ttu-id="3b2ee-111">Cuando haya terminado, tendrá un formulario con un menú estándar que muestra las selecciones de elementos de menú en un <xref:System.Windows.Forms.StatusStrip> control.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-111">When you are finished, you will have a form with a standard menu that displays menu item selections in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
 <span data-ttu-id="3b2ee-112">Para copiar el código de este tema como una sola lista, vea [Cómo: proporcionar elementos de menú estándar a un formulario](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="3b2ee-112">To copy the code in this topic as a single listing, see [How to: Provide Standard Menu Items to a Form](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3b2ee-113">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-113">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="3b2ee-114">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="3b2ee-114">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="3b2ee-115">Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="3b2ee-115">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3b2ee-116">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3b2ee-116">Prerequisites</span></span>  
 <span data-ttu-id="3b2ee-117">Para poder completar este tutorial, necesitará:</span><span class="sxs-lookup"><span data-stu-id="3b2ee-117">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="3b2ee-118">Permisos suficientes para poder crear y ejecutar proyectos de aplicación de Windows Forms en el equipo donde está instalado Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-118">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="3b2ee-119">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="3b2ee-119">Creating the Project</span></span>  
 <span data-ttu-id="3b2ee-120">El primer paso es crear el proyecto y configurar el formulario.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-120">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="3b2ee-121">Para crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="3b2ee-121">To create the project</span></span>  
  
1.  <span data-ttu-id="3b2ee-122">Crear un proyecto de aplicación de Windows denominado **StandardMenuForm**.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-122">Create a Windows application project called **StandardMenuForm**.</span></span>  
  
     <span data-ttu-id="3b2ee-123">Para más información, consulte [Cómo: Crear un proyecto de aplicación para Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span><span class="sxs-lookup"><span data-stu-id="3b2ee-123">For more information, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="3b2ee-124">En el Diseñador de Windows Forms, seleccione el formulario.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-124">In the Windows Forms Designer, select the form.</span></span>  
  
## <a name="creating-a-standard-menu"></a><span data-ttu-id="3b2ee-125">Crear un menú estándar</span><span class="sxs-lookup"><span data-stu-id="3b2ee-125">Creating a Standard Menu</span></span>  
 <span data-ttu-id="3b2ee-126">El Diseñador de Windows Forms puede rellenar automáticamente un <xref:System.Windows.Forms.MenuStrip> control con elementos de menú estándar.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-126">The Windows Forms Designer can automatically populate a <xref:System.Windows.Forms.MenuStrip> control with standard menu items.</span></span>  
  
#### <a name="to-create-a-standard-menu"></a><span data-ttu-id="3b2ee-127">Para crear un menú estándar</span><span class="sxs-lookup"><span data-stu-id="3b2ee-127">To create a standard menu</span></span>  
  
1.  <span data-ttu-id="3b2ee-128">Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.MenuStrip> control al formulario.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-128">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto your form.</span></span>  
  
2.  <span data-ttu-id="3b2ee-129">Haga clic en el <xref:System.Windows.Forms.MenuStrip> glifo de etiqueta inteligente del control (![glifo de etiqueta inteligente](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) y seleccione **insertar elementos estándar**.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-129">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) and select **Insert Standard Items**.</span></span>  
  
     <span data-ttu-id="3b2ee-130">El <xref:System.Windows.Forms.MenuStrip> se rellena con los elementos de menú estándar.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-130">The <xref:System.Windows.Forms.MenuStrip> control is populated with the standard menu items.</span></span>  
  
3.  <span data-ttu-id="3b2ee-131">Haga clic en el **archivo** elemento de menú para ver sus elementos de menú predeterminados y los iconos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-131">Click the **File** menu item to see its default menu items and corresponding icons.</span></span>  
  
## <a name="creating-a-statusstrip-control"></a><span data-ttu-id="3b2ee-132">Crear un Control StatusStrip</span><span class="sxs-lookup"><span data-stu-id="3b2ee-132">Creating a StatusStrip Control</span></span>  
 <span data-ttu-id="3b2ee-133">Use el <xref:System.Windows.Forms.StatusStrip> control para mostrar el estado de las aplicaciones de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-133">Use the <xref:System.Windows.Forms.StatusStrip> control to display status for your Windows Forms applications.</span></span> <span data-ttu-id="3b2ee-134">En el ejemplo actual, se muestran los elementos de menú seleccionados por el usuario en un <xref:System.Windows.Forms.StatusStrip> control.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-134">In the current example, menu items selected by the user are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
#### <a name="to-create-a-statusstrip-control"></a><span data-ttu-id="3b2ee-135">Para crear un control StatusStrip</span><span class="sxs-lookup"><span data-stu-id="3b2ee-135">To create a StatusStrip control</span></span>  
  
1.  <span data-ttu-id="3b2ee-136">Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.StatusStrip> control al formulario.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-136">From the **Toolbox**, drag a <xref:System.Windows.Forms.StatusStrip> control onto your form.</span></span>  
  
     <span data-ttu-id="3b2ee-137">El <xref:System.Windows.Forms.StatusStrip> control automáticamente se acopla a la parte inferior del formulario.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-137">The <xref:System.Windows.Forms.StatusStrip> control automatically docks to the bottom of the form.</span></span>  
  
2.  <span data-ttu-id="3b2ee-138">Haga clic en el <xref:System.Windows.Forms.StatusStrip> del control de botón de lista desplegable y seleccione **StatusLabel como** para agregar una <xref:System.Windows.Forms.ToolStripStatusLabel> el control a la <xref:System.Windows.Forms.StatusStrip> control.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-138">Click the <xref:System.Windows.Forms.StatusStrip> control's drop-down button and select **StatusLabel** to add a <xref:System.Windows.Forms.ToolStripStatusLabel> control to the <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
## <a name="handling-item-selection"></a><span data-ttu-id="3b2ee-139">Selección de elementos de control</span><span class="sxs-lookup"><span data-stu-id="3b2ee-139">Handling Item Selection</span></span>  
 <span data-ttu-id="3b2ee-140">Controlar la <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> evento para responder cuando el usuario selecciona un elemento de menú.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-140">Handle the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event to respond when the user selects a menu item.</span></span>  
  
#### <a name="to-handle-item-selection"></a><span data-ttu-id="3b2ee-141">Para controlar la selección de elementos</span><span class="sxs-lookup"><span data-stu-id="3b2ee-141">To handle item selection</span></span>  
  
1.  <span data-ttu-id="3b2ee-142">Haga clic en el **archivo** elemento de menú que creó en la creación una sección de menú estándar.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-142">Click the **File** menu item that you created in the Creating a Standard Menu section.</span></span>  
  
2.  <span data-ttu-id="3b2ee-143">En el **propiedades** ventana, haga clic en **eventos**.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-143">In the **Properties** window, click **Events**.</span></span>  
  
3.  <span data-ttu-id="3b2ee-144">Haga doble clic en el <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> eventos.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-144">Double-click the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>  
  
     <span data-ttu-id="3b2ee-145">El Diseñador de Windows Forms genera un controlador de eventos para el <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> eventos.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-145">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>  
  
4.  <span data-ttu-id="3b2ee-146">Inserte el código siguiente en el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-146">Insert the following code into the event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]  
  
5.  <span data-ttu-id="3b2ee-147">Insertar el `UpdateStatus` definición de método de utilidad en el formulario.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-147">Insert the `UpdateStatus` utility method definition into the form.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]  
  
## <a name="checkpoint"></a><span data-ttu-id="3b2ee-148">Punto de control</span><span class="sxs-lookup"><span data-stu-id="3b2ee-148">Checkpoint</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="3b2ee-149">Para comprobar el formulario</span><span class="sxs-lookup"><span data-stu-id="3b2ee-149">To test your form</span></span>  
  
1.  <span data-ttu-id="3b2ee-150">Presione F5 para compilar y ejecutar el formulario.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-150">Press F5 to compile and run your form.</span></span>  
  
2.  <span data-ttu-id="3b2ee-151">Haga clic en el **archivo** elemento de menú para abrir el menú.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-151">Click the **File** menu item to open the menu.</span></span>  
  
3.  <span data-ttu-id="3b2ee-152">En el **archivo** menú, haga clic en uno de los elementos para seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-152">On the **File** menu, click one of the items to select it.</span></span>  
  
     <span data-ttu-id="3b2ee-153">El <xref:System.Windows.Forms.StatusStrip> control muestra el elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-153">The <xref:System.Windows.Forms.StatusStrip> control displays the selected item.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="3b2ee-154">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="3b2ee-154">Next Steps</span></span>  
 <span data-ttu-id="3b2ee-155">En este tutorial, ha creado un formulario con un menú estándar.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-155">In this walkthrough, you have created a form with a standard menu.</span></span> <span data-ttu-id="3b2ee-156">Puede usar el <xref:System.Windows.Forms.ToolStrip> familia de controles para muchos otros objetivos:</span><span class="sxs-lookup"><span data-stu-id="3b2ee-156">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>  
  
-   <span data-ttu-id="3b2ee-157">Crear menús contextuales para los controles con <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-157">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="3b2ee-158">Para obtener más información, consulte [información general del componente ContextMenu](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="3b2ee-158">For more information, see [ContextMenu Component Overview](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="3b2ee-159">Crear un formulario de múltiples documentos (MDI) de la interfaz con acoplamiento <xref:System.Windows.Forms.ToolStrip> controles.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-159">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="3b2ee-160">Para obtener más información, consulte [Tutorial: crear un formulario MDI con combinación de menús y controles ToolStrip](../../../../docs/framework/winforms/controls/walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="3b2ee-160">For more information, see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](../../../../docs/framework/winforms/controls/walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
-   <span data-ttu-id="3b2ee-161">Asigne el <xref:System.Windows.Forms.ToolStrip> controla un aspecto profesional.</span><span class="sxs-lookup"><span data-stu-id="3b2ee-161">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="3b2ee-162">Para obtener más información, consulte [Cómo: establecer la representación de ToolStrip para una aplicación](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="3b2ee-162">For more information, see [How to: Set the ToolStrip Renderer for an Application](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b2ee-163">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b2ee-163">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [<span data-ttu-id="3b2ee-164">Control MenuStrip</span><span class="sxs-lookup"><span data-stu-id="3b2ee-164">MenuStrip Control</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)
