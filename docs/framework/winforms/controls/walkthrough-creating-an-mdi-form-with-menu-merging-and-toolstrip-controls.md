---
title: "Tutorial: Crear un formulario MDI con combinación de menús y controles ToolStrip"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bca5439f247951496d82c03b57ec1fa0e21a8271
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="3f4c7-102">Tutorial: Crear un formulario MDI con combinación de menús y controles ToolStrip</span><span class="sxs-lookup"><span data-stu-id="3f4c7-102">Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls</span></span>
<span data-ttu-id="3f4c7-103">El espacio de nombres <xref:System.Windows.Forms?displayProperty=nameWithType> es compatible con aplicaciones de interfaces de múltiples documentos (MDI) y el control <xref:System.Windows.Forms.MenuStrip> admite la combinación de menús.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="3f4c7-104">Los formularios MDI también pueden ser compatibles con los controles <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="3f4c7-105">Este tutorial muestra cómo usar <xref:System.Windows.Forms.ToolStripPanel> controles con un formulario MDI.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-105">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="3f4c7-106">El formulario también admite la combinación de menús con menús secundarios.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-106">The form also supports menu merging with child menus.</span></span> <span data-ttu-id="3f4c7-107">En este tutorial se muestran las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="3f4c7-107">The following tasks are illustrated in this walkthrough:</span></span>  
  
-   <span data-ttu-id="3f4c7-108">Crear un proyecto de formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-108">Creating a Windows Forms project.</span></span>  
  
-   <span data-ttu-id="3f4c7-109">Crear el menú principal para el formulario.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-109">Creating the main menu for your form.</span></span> <span data-ttu-id="3f4c7-110">El nombre real del menú varía.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-110">The actual name of the menu will vary.</span></span>  
  
-   <span data-ttu-id="3f4c7-111">Agregar el <xref:System.Windows.Forms.ToolStripPanel> el control a la **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-111">Adding the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox**.</span></span>  
  
-   <span data-ttu-id="3f4c7-112">Crear un formulario secundario.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-112">Creating a child form.</span></span>  
  
-   <span data-ttu-id="3f4c7-113">Organizar <xref:System.Windows.Forms.ToolStripPanel> controles por orden z.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-113">Arranging <xref:System.Windows.Forms.ToolStripPanel> controls by z-order.</span></span>  
  
 <span data-ttu-id="3f4c7-114">Cuando haya terminado, tendrá un formulario MDI que admite la combinación de menús y móvil <xref:System.Windows.Forms.ToolStrip> controles.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-114">When you are finished, you will have an MDI form that supports menu merging and movable <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="3f4c7-115">Para copiar el código de este tema como una sola lista, vea [Cómo: crear un formulario MDI con combinación de menús y controles ToolStrip](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="3f4c7-115">To copy the code in this topic as a single listing, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f4c7-116">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="3f4c7-117">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="3f4c7-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="3f4c7-118">Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="3f4c7-118">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3f4c7-119">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3f4c7-119">Prerequisites</span></span>  
 <span data-ttu-id="3f4c7-120">Para poder completar este tutorial, necesitará:</span><span class="sxs-lookup"><span data-stu-id="3f4c7-120">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="3f4c7-121">Los permisos necesarios para poder crear y ejecutar proyectos de aplicación de Windows Forms en el equipo donde [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] está instalado.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-121">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] is installed.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="3f4c7-122">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="3f4c7-122">Creating the Project</span></span>  
 <span data-ttu-id="3f4c7-123">El primer paso es crear el proyecto y configurar el formulario.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-123">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="3f4c7-124">Para crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="3f4c7-124">To create the project</span></span>  
  
1.  <span data-ttu-id="3f4c7-125">Cree un proyecto de aplicación de Windows denominado **MDI**.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-125">Create a Windows Application project called **MdiForm**.</span></span>  
  
     <span data-ttu-id="3f4c7-126">Para obtener más información, consulta [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span><span class="sxs-lookup"><span data-stu-id="3f4c7-126">For more information, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="3f4c7-127">En el Diseñador de Windows Forms, seleccione el formulario.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-127">In the Windows Forms Designer, select the form.</span></span>  
  
3.  <span data-ttu-id="3f4c7-128">En la ventana Propiedades, establezca el valor de la <xref:System.Windows.Forms.Form.IsMdiContainer%2A> a `true`.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-128">In the Properties window, set the value of the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> to `true`.</span></span>  
  
## <a name="creating-the-main-menu"></a><span data-ttu-id="3f4c7-129">Crear el menú principal</span><span class="sxs-lookup"><span data-stu-id="3f4c7-129">Creating the Main Menu</span></span>  
 <span data-ttu-id="3f4c7-130">El formulario MDI principal contiene el menú principal.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-130">The parent MDI form contains the main menu.</span></span> <span data-ttu-id="3f4c7-131">El menú principal tiene un elemento de menú denominado **ventana**.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-131">The main menu has one menu item named **Window**.</span></span> <span data-ttu-id="3f4c7-132">Con el **ventana** elemento de menú, puede crear formularios secundarios.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-132">With the **Window** menu item, you can create child forms.</span></span> <span data-ttu-id="3f4c7-133">Elementos de menú de formularios secundarios se combinan en el menú principal.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-133">Menu items from child forms are merged into the main menu.</span></span>  
  
#### <a name="to-create-the-main-menu"></a><span data-ttu-id="3f4c7-134">Para crear el menú principal</span><span class="sxs-lookup"><span data-stu-id="3f4c7-134">To create the Main menu</span></span>  
  
1.  <span data-ttu-id="3f4c7-135">Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.MenuStrip> al formulario.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-135">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the form.</span></span>  
  
2.  <span data-ttu-id="3f4c7-136">Agregar un <xref:System.Windows.Forms.ToolStripMenuItem> a la <xref:System.Windows.Forms.MenuStrip> controlar y asígnele el nombre **ventana**.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-136">Add a <xref:System.Windows.Forms.ToolStripMenuItem> to the <xref:System.Windows.Forms.MenuStrip> control and name it **Window**.</span></span>  
  
3.  <span data-ttu-id="3f4c7-137">Seleccione el control <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-137">Select the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
4.  <span data-ttu-id="3f4c7-138">En la ventana Propiedades, establezca el valor de la <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> propiedad `ToolStripMenuItem1`.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-138">In the Properties window, set the value of the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to `ToolStripMenuItem1`.</span></span>  
  
5.  <span data-ttu-id="3f4c7-139">Agregar un subelemento a la **ventana** elemento de menú y, a continuación, el nombre del subelemento **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-139">Add a subitem to the **Window** menu item, and then name the subitem **New**.</span></span>  
  
6.  <span data-ttu-id="3f4c7-140">En la ventana Propiedades, haga clic en **eventos**.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-140">In the Properties window, click **Events**.</span></span>  
  
7.  <span data-ttu-id="3f4c7-141">Haga doble clic en el <xref:System.Windows.Forms.ToolStripItem.Click> eventos.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-141">Double-click the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>  
  
     <span data-ttu-id="3f4c7-142">El Diseñador de Windows Forms genera un controlador de eventos para el <xref:System.Windows.Forms.ToolStripItem.Click> eventos.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-142">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>  
  
8.  <span data-ttu-id="3f4c7-143">Inserte el código siguiente en el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-143">Insert the following code into the event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]  
  
## <a name="adding-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="3f4c7-144">Agregar el Control ToolStripPanel al cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="3f4c7-144">Adding the ToolStripPanel Control to the Toolbox</span></span>  
 <span data-ttu-id="3f4c7-145">Cuando usas <xref:System.Windows.Forms.MenuStrip> controles con un formulario MDI que debe tener el <xref:System.Windows.Forms.ToolStripPanel> control.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-145">When you use <xref:System.Windows.Forms.MenuStrip> controls with an MDI form you must have the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="3f4c7-146">Debe agregar el <xref:System.Windows.Forms.ToolStripPanel> el control a la **cuadro de herramientas** para crear el formulario MDI en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-146">You must add the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox** to build your MDI form in the Windows Forms Designer.</span></span>  
  
#### <a name="to-add-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="3f4c7-147">Para agregar el control ToolStripPanel al cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="3f4c7-147">To add the ToolStripPanel control to the Toolbox</span></span>  
  
1.  <span data-ttu-id="3f4c7-148">Abra la **cuadro de herramientas**y, a continuación, haga clic en el **todos los formularios Windows Forms** ficha para mostrar los controles de formularios Windows Forms disponibles.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-148">Open the **Toolbox**, and then click the **All Windows Forms** tab to show the available Windows Forms controls.</span></span>  
  
2.  <span data-ttu-id="3f4c7-149">Haga clic en para abrir el menú contextual y seleccione **elegir elementos**.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-149">Right-click to open the shortcut menu, and select **Choose Items**.</span></span>  
  
3.  <span data-ttu-id="3f4c7-150">En el **elegir elementos del cuadro de herramientas** cuadro de diálogo, desplácese hacia abajo por la **nombre** columna hasta que encuentre **ToolStripPanel**.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-150">In the **Choose Toolbox Items** dialog box, scroll down the **Name** column until you find **ToolStripPanel**.</span></span>  
  
4.  <span data-ttu-id="3f4c7-151">Active la casilla de verificación por **ToolStripPanel**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-151">Select the check box by **ToolStripPanel**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="3f4c7-152">El <xref:System.Windows.Forms.ToolStripPanel> control aparece en el **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-152">The <xref:System.Windows.Forms.ToolStripPanel> control appears in the **Toolbox**.</span></span>  
  
## <a name="creating-a-child-form"></a><span data-ttu-id="3f4c7-153">Crear un formulario secundario</span><span class="sxs-lookup"><span data-stu-id="3f4c7-153">Creating a Child Form</span></span>  
 <span data-ttu-id="3f4c7-154">En este procedimiento, definirá una clase de formulario secundario independiente que tiene su propio <xref:System.Windows.Forms.MenuStrip> control.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-154">In this procedure, you will define a separate child form class that has its own <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="3f4c7-155">Los elementos de menú para este formulario se combinan con los del formulario primario.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-155">The menu items for this form are merged with those of the parent form.</span></span>  
  
#### <a name="to-define-a-child-form"></a><span data-ttu-id="3f4c7-156">Para definir un formulario secundario</span><span class="sxs-lookup"><span data-stu-id="3f4c7-156">To define a child form</span></span>  
  
1.  <span data-ttu-id="3f4c7-157">Agregue un nuevo formulario denominado `ChildForm` al proyecto.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-157">Add a new form named `ChildForm` to the project.</span></span>  
  
     <span data-ttu-id="3f4c7-158">Para obtener más información, consulte [Cómo: agregar Windows Forms a un proyecto](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1).</span><span class="sxs-lookup"><span data-stu-id="3f4c7-158">For more information, see [How to: Add Windows Forms to a Project](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1).</span></span>  
  
2.  <span data-ttu-id="3f4c7-159">Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.MenuStrip> control en el formulario secundario.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-159">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the child form.</span></span>  
  
3.  <span data-ttu-id="3f4c7-160">Haga clic en el <xref:System.Windows.Forms.MenuStrip> glifo de etiqueta inteligente del control (![glifo de etiqueta inteligente](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) y, a continuación, seleccione **editar elementos**.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-160">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), and then select **Edit Items**.</span></span>  
  
4.  <span data-ttu-id="3f4c7-161">En el **Editor de la colección de elementos** diálogo cuadro, agregue un nuevo <xref:System.Windows.Forms.ToolStripMenuItem> denominado **ChildMenuItem** al menú secundario.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-161">In the **Items Collection Editor** dialog box, add a new <xref:System.Windows.Forms.ToolStripMenuItem> named **ChildMenuItem** to the child menu.</span></span>  
  
     <span data-ttu-id="3f4c7-162">Para obtener más información, consulte [Editor de colección de elementos ToolStrip](http://msdn.microsoft.com/en-us/e681f3ab-94ba-4b2b-ac64-1dfad46caa25).</span><span class="sxs-lookup"><span data-stu-id="3f4c7-162">For more information, see [ToolStrip Items Collection Editor](http://msdn.microsoft.com/en-us/e681f3ab-94ba-4b2b-ac64-1dfad46caa25).</span></span>  
  
## <a name="testing-the-form"></a><span data-ttu-id="3f4c7-163">Comprobar el formulario</span><span class="sxs-lookup"><span data-stu-id="3f4c7-163">Testing the Form</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="3f4c7-164">Para comprobar el formulario</span><span class="sxs-lookup"><span data-stu-id="3f4c7-164">To test your form</span></span>  
  
1.  <span data-ttu-id="3f4c7-165">Presione F5 para compilar y ejecutar el formulario.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-165">Press F5 to compile and run your form.</span></span>  
  
2.  <span data-ttu-id="3f4c7-166">Haga clic en el **ventana** elemento de menú para abrir el menú y, a continuación, haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-166">Click the **Window** menu item to open the menu, and then click **New**.</span></span>  
  
     <span data-ttu-id="3f4c7-167">Se crea un nuevo formulario secundario en el área de cliente del formulario MDI.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-167">A new child form is created in the form's MDI client area.</span></span> <span data-ttu-id="3f4c7-168">Menú del formulario secundario se combina con el menú principal.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-168">The child form's menu is merged with the main menu.</span></span>  
  
3.  <span data-ttu-id="3f4c7-169">Cierre el formulario secundario.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-169">Close the child form.</span></span>  
  
     <span data-ttu-id="3f4c7-170">Menú del formulario secundario se quita en el menú principal.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-170">The child form's menu is removed from the main menu.</span></span>  
  
4.  <span data-ttu-id="3f4c7-171">Haga clic en **New** varias veces.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-171">Click **New** several times.</span></span>  
  
     <span data-ttu-id="3f4c7-172">Los formularios secundarios aparecen automáticamente en el W**ventana** menú elemento porque el <xref:System.Windows.Forms.MenuStrip> del control <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> se asigna la propiedad.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-172">The child forms are automatically listed under the W**indow** menu item because the <xref:System.Windows.Forms.MenuStrip> control's <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property is assigned.</span></span>  
  
## <a name="adding-toolstrip-support"></a><span data-ttu-id="3f4c7-173">Agregar compatibilidad de ToolStrip</span><span class="sxs-lookup"><span data-stu-id="3f4c7-173">Adding ToolStrip Support</span></span>  
 <span data-ttu-id="3f4c7-174">En este procedimiento, agregará cuatro <xref:System.Windows.Forms.ToolStrip> controles al formulario primario MDI.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-174">In this procedure, you will add four <xref:System.Windows.Forms.ToolStrip> controls to the MDI parent form.</span></span> <span data-ttu-id="3f4c7-175">Cada <xref:System.Windows.Forms.ToolStrip> se agrega control dentro de un <xref:System.Windows.Forms.ToolStripPanel> control, que está acoplado al borde del formulario.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-175">Each <xref:System.Windows.Forms.ToolStrip> control is added inside a <xref:System.Windows.Forms.ToolStripPanel> control, which is docked to the edge of the form.</span></span>  
  
#### <a name="to-add-toolstrip-controls-to-the-mdi-parent-form"></a><span data-ttu-id="3f4c7-176">Para agregar controles ToolStrip al formulario primario MDI</span><span class="sxs-lookup"><span data-stu-id="3f4c7-176">To add ToolStrip controls to the MDI parent form</span></span>  
  
1.  <span data-ttu-id="3f4c7-177">Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.ToolStripPanel> al formulario.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-177">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStripPanel> control onto the form.</span></span>  
  
2.  <span data-ttu-id="3f4c7-178">Con el <xref:System.Windows.Forms.ToolStripPanel> control seleccionado, haga doble clic en el <xref:System.Windows.Forms.ToolStrip> controlar en el **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-178">With the <xref:System.Windows.Forms.ToolStripPanel> control selected, double-click the <xref:System.Windows.Forms.ToolStrip> control in the **Toolbox**.</span></span>  
  
     <span data-ttu-id="3f4c7-179">A <xref:System.Windows.Forms.ToolStrip> control se crea en el <xref:System.Windows.Forms.ToolStripPanel> control.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-179">A <xref:System.Windows.Forms.ToolStrip> control is created in the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
3.  <span data-ttu-id="3f4c7-180">Seleccione el control <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-180">Select the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
4.  <span data-ttu-id="3f4c7-181">En la ventana Propiedades, cambie el valor del control <xref:System.Windows.Forms.Control.Dock%2A> propiedad <xref:System.Windows.Forms.DockStyle.Left>.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-181">In the Properties window, change the value of the control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Left>.</span></span>  
  
     <span data-ttu-id="3f4c7-182">El <xref:System.Windows.Forms.ToolStripPanel> controlar lo acopla en el lado izquierdo del formulario, bajo el menú principal.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-182">The <xref:System.Windows.Forms.ToolStripPanel> control docks to the left side of the form, underneath the main menu.</span></span> <span data-ttu-id="3f4c7-183">El área de cliente MDI cambia el tamaño para ajustar el <xref:System.Windows.Forms.ToolStripPanel> control.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-183">The MDI client area resizes to fit the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
5.  <span data-ttu-id="3f4c7-184">Repita los pasos del 1 al 4.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-184">Repeat steps 1 through 4.</span></span>  
  
     <span data-ttu-id="3f4c7-185">Acoplar el nuevo <xref:System.Windows.Forms.ToolStripPanel> control a la parte superior del formulario.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-185">Dock the new <xref:System.Windows.Forms.ToolStripPanel> control to the top of the form.</span></span>  
  
     <span data-ttu-id="3f4c7-186">El <xref:System.Windows.Forms.ToolStripPanel> control está acoplado bajo el menú principal, pero a la derecha de la primera <xref:System.Windows.Forms.ToolStripPanel> control.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-186">The <xref:System.Windows.Forms.ToolStripPanel> control is docked underneath the main menu, but to the right of the first <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="3f4c7-187">Este paso ilustran la importancia del orden z para colocar correctamente <xref:System.Windows.Forms.ToolStripPanel> controles.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-187">This step illustrates the importance of z-order in correctly positioning <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>  
  
6.  <span data-ttu-id="3f4c7-188">Repita los pasos del 1 al 4 para dos más <xref:System.Windows.Forms.ToolStripPanel> controles.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-188">Repeat steps 1 through 4 for two more <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>  
  
     <span data-ttu-id="3f4c7-189">Acoplar el nuevo <xref:System.Windows.Forms.ToolStripPanel> controles a la derecha e inferior del formulario.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-189">Dock the new <xref:System.Windows.Forms.ToolStripPanel> controls to the right and bottom of the form.</span></span>  
  
## <a name="arranging-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="3f4c7-190">Organizar los controles ToolStripPanel por orden Z</span><span class="sxs-lookup"><span data-stu-id="3f4c7-190">Arranging ToolStripPanel Controls by Z-order</span></span>  
 <span data-ttu-id="3f4c7-191">La posición de un acoplada <xref:System.Windows.Forms.ToolStripPanel> control en el formulario MDI viene determinado por la posición del control en el orden z.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-191">The position of a docked <xref:System.Windows.Forms.ToolStripPanel> control on your MDI form is determined by the control's position in the z-order.</span></span> <span data-ttu-id="3f4c7-192">Puede organizar con facilidad el orden z de los controles en la ventana Esquema del documento.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-192">You can easily arrange the z-order of your controls in the Document Outline window.</span></span>  
  
#### <a name="to-arrange-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="3f4c7-193">Para organizar los controles ToolStripPanel por orden Z</span><span class="sxs-lookup"><span data-stu-id="3f4c7-193">To arrange ToolStripPanel controls by Z-order</span></span>  
  
1.  <span data-ttu-id="3f4c7-194">En el **vista** menú, haga clic en **otras ventanas**y, a continuación, haga clic en **esquema del documento**.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-194">In the **View** menu, click **Other Windows**, and then click **Document Outline**.</span></span>  
  
     <span data-ttu-id="3f4c7-195">La organización de su <xref:System.Windows.Forms.ToolStripPanel> controles desde el procedimiento anterior no es estándar.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-195">The arrangement of your <xref:System.Windows.Forms.ToolStripPanel> controls from the previous procedure is nonstandard.</span></span> <span data-ttu-id="3f4c7-196">Esto es porque el orden z no es correcto.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-196">This is because the z-order is not correct.</span></span> <span data-ttu-id="3f4c7-197">Utilice la ventana Esquema del documento para cambiar el orden z de los controles.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-197">Use the Document Outline window to change the z-order of the controls.</span></span>  
  
2.  <span data-ttu-id="3f4c7-198">En la ventana Esquema del documento, seleccione **ToolStripPanel4**.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-198">In the Document Outline window, select **ToolStripPanel4**.</span></span>  
  
3.  <span data-ttu-id="3f4c7-199">Haga clic en el botón de flecha abajo y otra vez, hasta que **ToolStripPanel4** en la parte inferior de la lista.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-199">Click the down-arrow button repeatedly, until **ToolStripPanel4** is at the bottom of the list.</span></span>  
  
     <span data-ttu-id="3f4c7-200">El **ToolStripPanel4** control está acoplado a la parte inferior del formulario, debajo de los demás controles.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-200">The **ToolStripPanel4** control is docked to the bottom of the form, underneath the other controls.</span></span>  
  
4.  <span data-ttu-id="3f4c7-201">Seleccione **ToolStripPanel2**.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-201">Select **ToolStripPanel2**.</span></span>  
  
5.  <span data-ttu-id="3f4c7-202">Haga clic una vez en el botón de flecha abajo para colocar el control en tercer lugar en la lista.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-202">Click the down-arrow button one time to position the control third in the list.</span></span>  
  
     <span data-ttu-id="3f4c7-203">El **ToolStripPanel2** control está acoplado a la parte superior del formulario, bajo el menú principal y encima de los otros controles.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-203">The **ToolStripPanel2** control is docked to the top of the form, underneath the main menu and above the other controls.</span></span>  
  
6.  <span data-ttu-id="3f4c7-204">Seleccione los distintos controles en el **esquema del documento** ventana y moverlos a distintas posiciones en el orden z.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-204">Select various controls in the **Document Outline** window and move them to different positions in the z-order.</span></span> <span data-ttu-id="3f4c7-205">Tenga en cuenta el efecto del orden z en la posición de los controles acoplados.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-205">Note the effect of the z-order on the placement of docked controls.</span></span> <span data-ttu-id="3f4c7-206">Utilice CTRL-Z o **deshacer** en el **editar** menú para deshacer los cambios.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-206">Use CTRL-Z or **Undo** on the **Edit** menu to undo your changes.</span></span>  
  
## <a name="checkpoint"></a><span data-ttu-id="3f4c7-207">Punto de control</span><span class="sxs-lookup"><span data-stu-id="3f4c7-207">Checkpoint</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="3f4c7-208">Para comprobar el formulario</span><span class="sxs-lookup"><span data-stu-id="3f4c7-208">To test your form</span></span>  
  
1.  <span data-ttu-id="3f4c7-209">Presione F5 para compilar y ejecutar el formulario.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-209">Press F5 to compile and run your form.</span></span>  
  
2.  <span data-ttu-id="3f4c7-210">Haga clic en el control de un <xref:System.Windows.Forms.ToolStrip> controlar y arrastrar el control a otras posiciones en el formulario.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-210">Click the grip of a <xref:System.Windows.Forms.ToolStrip> control and drag the control to different positions on the form.</span></span>  
  
     <span data-ttu-id="3f4c7-211">Puede arrastrar una <xref:System.Windows.Forms.ToolStrip> control de una <xref:System.Windows.Forms.ToolStripPanel> control a otro.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-211">You can drag a <xref:System.Windows.Forms.ToolStrip> control from one <xref:System.Windows.Forms.ToolStripPanel> control to another.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="3f4c7-212">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="3f4c7-212">Next Steps</span></span>  
 <span data-ttu-id="3f4c7-213">En este tutorial, ha creado un formulario MDI principal con <xref:System.Windows.Forms.ToolStrip> controles y combinación de menús.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-213">In this walkthrough, you have created an MDI parent form with <xref:System.Windows.Forms.ToolStrip> controls and menu merging.</span></span> <span data-ttu-id="3f4c7-214">Puede usar el <xref:System.Windows.Forms.ToolStrip> familia de controles para muchos otros objetivos:</span><span class="sxs-lookup"><span data-stu-id="3f4c7-214">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>  
  
-   <span data-ttu-id="3f4c7-215">Crear menús contextuales para los controles con <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-215">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="3f4c7-216">Para obtener más información, consulte [información general del componente ContextMenu](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="3f4c7-216">For more information, see [ContextMenu Component Overview](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="3f4c7-217">Crea un formulario con un menú estándar rellenado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-217">Created a form with an automatically populated standard menu.</span></span> <span data-ttu-id="3f4c7-218">Para obtener más información, consulte [Tutorial: proporcionar elementos de menú estándar a un formulario](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="3f4c7-218">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>  
  
-   <span data-ttu-id="3f4c7-219">Asigne el <xref:System.Windows.Forms.ToolStrip> controla un aspecto profesional.</span><span class="sxs-lookup"><span data-stu-id="3f4c7-219">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="3f4c7-220">Para obtener más información, consulte [Cómo: establecer la representación de ToolStrip para una aplicación](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="3f4c7-220">For more information, see [How to: Set the ToolStrip Renderer for an Application](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f4c7-221">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f4c7-221">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [<span data-ttu-id="3f4c7-222">Crear formularios principales MDI</span><span class="sxs-lookup"><span data-stu-id="3f4c7-222">How to: Create MDI Parent Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [<span data-ttu-id="3f4c7-223">Crear formularios MDI secundarios</span><span class="sxs-lookup"><span data-stu-id="3f4c7-223">How to: Create MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [<span data-ttu-id="3f4c7-224">Insertar un elemento MenuStrip en un menú desplegable MDI</span><span class="sxs-lookup"><span data-stu-id="3f4c7-224">How to: Insert a MenuStrip into an MDI Drop-Down Menu</span></span>](../../../../docs/framework/winforms/controls/how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)  
 [<span data-ttu-id="3f4c7-225">Control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="3f4c7-225">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
