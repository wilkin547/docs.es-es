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
ms.openlocfilehash: 6236190340833e3f8810387e51ad53e1cb10d37b
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45743557"
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="ef6ef-102">Tutorial: Crear un formulario MDI con combinación de menús y controles ToolStrip</span><span class="sxs-lookup"><span data-stu-id="ef6ef-102">Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls</span></span>
<span data-ttu-id="ef6ef-103">El espacio de nombres <xref:System.Windows.Forms?displayProperty=nameWithType> es compatible con aplicaciones de interfaces de múltiples documentos (MDI) y el control <xref:System.Windows.Forms.MenuStrip> admite la combinación de menús.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="ef6ef-104">Los formularios MDI también pueden ser compatibles con los controles <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="ef6ef-105">Este tutorial muestra cómo usar <xref:System.Windows.Forms.ToolStripPanel> controles con un formulario MDI.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-105">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="ef6ef-106">El formulario también admite la combinación de menús con menús secundarios.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-106">The form also supports menu merging with child menus.</span></span> <span data-ttu-id="ef6ef-107">En este tutorial se muestran las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="ef6ef-107">The following tasks are illustrated in this walkthrough:</span></span>  
  
-   <span data-ttu-id="ef6ef-108">Crear un proyecto de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-108">Creating a Windows Forms project.</span></span>  
  
-   <span data-ttu-id="ef6ef-109">Crear el menú principal para el formulario.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-109">Creating the main menu for your form.</span></span> <span data-ttu-id="ef6ef-110">El nombre real del menú variará.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-110">The actual name of the menu will vary.</span></span>  
  
-   <span data-ttu-id="ef6ef-111">Agregar el <xref:System.Windows.Forms.ToolStripPanel> el control a la **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-111">Adding the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox**.</span></span>  
  
-   <span data-ttu-id="ef6ef-112">Creación de un formulario secundario.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-112">Creating a child form.</span></span>  
  
-   <span data-ttu-id="ef6ef-113">Organizar <xref:System.Windows.Forms.ToolStripPanel> agrupar controles por orden z.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-113">Arranging <xref:System.Windows.Forms.ToolStripPanel> controls by z-order.</span></span>  
  
 <span data-ttu-id="ef6ef-114">Cuando haya terminado, tendrá un formulario MDI que admite la combinación de menús y movibles <xref:System.Windows.Forms.ToolStrip> controles.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-114">When you are finished, you will have an MDI form that supports menu merging and movable <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="ef6ef-115">Para copiar el código de este tema como una sola lista, vea [Cómo: crear un formulario MDI con combinación de menús y controles ToolStrip](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="ef6ef-115">To copy the code in this topic as a single listing, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ef6ef-116">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="ef6ef-117">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="ef6ef-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="ef6ef-118">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="ef6ef-118">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ef6ef-119">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ef6ef-119">Prerequisites</span></span>  
 <span data-ttu-id="ef6ef-120">Para poder completar este tutorial, necesitará:</span><span class="sxs-lookup"><span data-stu-id="ef6ef-120">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="ef6ef-121">Permisos suficientes para poder crear y ejecutar proyectos de aplicación de Windows Forms en el equipo donde está instalado Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-121">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="ef6ef-122">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="ef6ef-122">Creating the Project</span></span>  
 <span data-ttu-id="ef6ef-123">El primer paso es crear el proyecto y configurar el formulario.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-123">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="ef6ef-124">Para crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="ef6ef-124">To create the project</span></span>  
  
1.  <span data-ttu-id="ef6ef-125">Cree un proyecto de aplicación de Windows denominado **MDI** (**archivo** > **New** > **proyecto**  >  **Visual C#** o **Visual Basic** > **escritorio clásico de** > **Windows Forms Application**).</span><span class="sxs-lookup"><span data-stu-id="ef6ef-125">Create a Windows Application project called **MdiForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2.  <span data-ttu-id="ef6ef-126">En el Diseñador de formularios de Windows, seleccione el formulario.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-126">In the Windows Forms Designer, select the form.</span></span>  
  
3.  <span data-ttu-id="ef6ef-127">En la ventana Propiedades, establezca el valor de la <xref:System.Windows.Forms.Form.IsMdiContainer%2A> a `true`.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-127">In the Properties window, set the value of the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> to `true`.</span></span>  
  
## <a name="creating-the-main-menu"></a><span data-ttu-id="ef6ef-128">Crear el menú principal</span><span class="sxs-lookup"><span data-stu-id="ef6ef-128">Creating the Main Menu</span></span>  
 <span data-ttu-id="ef6ef-129">El formulario MDI principal contiene el menú principal.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-129">The parent MDI form contains the main menu.</span></span> <span data-ttu-id="ef6ef-130">El menú principal tiene un elemento de menú denominado **ventana**.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-130">The main menu has one menu item named **Window**.</span></span> <span data-ttu-id="ef6ef-131">Con el **ventana** elemento de menú, puede crear formularios secundarios.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-131">With the **Window** menu item, you can create child forms.</span></span> <span data-ttu-id="ef6ef-132">Los elementos de menú de formularios secundarios se combinan en el menú principal.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-132">Menu items from child forms are merged into the main menu.</span></span>  
  
#### <a name="to-create-the-main-menu"></a><span data-ttu-id="ef6ef-133">Para crear el menú principal</span><span class="sxs-lookup"><span data-stu-id="ef6ef-133">To create the Main menu</span></span>  
  
1.  <span data-ttu-id="ef6ef-134">Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.MenuStrip> al formulario.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the form.</span></span>  
  
2.  <span data-ttu-id="ef6ef-135">Agregar un <xref:System.Windows.Forms.ToolStripMenuItem> a la <xref:System.Windows.Forms.MenuStrip> controlar y asígnele el nombre **ventana**.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-135">Add a <xref:System.Windows.Forms.ToolStripMenuItem> to the <xref:System.Windows.Forms.MenuStrip> control and name it **Window**.</span></span>  
  
3.  <span data-ttu-id="ef6ef-136">Seleccione el control <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-136">Select the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
4.  <span data-ttu-id="ef6ef-137">En la ventana Propiedades, establezca el valor de la <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> propiedad `ToolStripMenuItem1`.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-137">In the Properties window, set the value of the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to `ToolStripMenuItem1`.</span></span>  
  
5.  <span data-ttu-id="ef6ef-138">Agregar un subelemento a la **ventana** elemento de menú y, a continuación, el nombre del subelemento **New**.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-138">Add a subitem to the **Window** menu item, and then name the subitem **New**.</span></span>  
  
6.  <span data-ttu-id="ef6ef-139">En la ventana Propiedades, haga clic en **eventos**.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-139">In the Properties window, click **Events**.</span></span>  
  
7.  <span data-ttu-id="ef6ef-140">Haga doble clic en el <xref:System.Windows.Forms.ToolStripItem.Click> eventos.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-140">Double-click the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>  
  
     <span data-ttu-id="ef6ef-141">El Diseñador de Windows Forms genera un controlador de eventos para el <xref:System.Windows.Forms.ToolStripItem.Click> eventos.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-141">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>  
  
8.  <span data-ttu-id="ef6ef-142">Inserte el código siguiente en el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-142">Insert the following code into the event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]  
  
## <a name="adding-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="ef6ef-143">Agregar el Control ToolStripPanel al cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="ef6ef-143">Adding the ToolStripPanel Control to the Toolbox</span></span>  
 <span data-ttu-id="ef6ef-144">Cuando usas <xref:System.Windows.Forms.MenuStrip> controles con un formulario MDI que debe tener el <xref:System.Windows.Forms.ToolStripPanel> control.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-144">When you use <xref:System.Windows.Forms.MenuStrip> controls with an MDI form you must have the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="ef6ef-145">Debe agregar el <xref:System.Windows.Forms.ToolStripPanel> el control a la **cuadro de herramientas** para crear el formulario MDI en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-145">You must add the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox** to build your MDI form in the Windows Forms Designer.</span></span>  
  
#### <a name="to-add-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="ef6ef-146">Para agregar el control ToolStripPanel al cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="ef6ef-146">To add the ToolStripPanel control to the Toolbox</span></span>  
  
1.  <span data-ttu-id="ef6ef-147">Abra el **cuadro de herramientas**y, a continuación, haga clic en el **todos los formularios de Windows** pestaña para mostrar los controles de formularios de Windows disponibles.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-147">Open the **Toolbox**, and then click the **All Windows Forms** tab to show the available Windows Forms controls.</span></span>  
  
2.  <span data-ttu-id="ef6ef-148">Haga doble clic para abrir el menú contextual y seleccione **elegir elementos**.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-148">Right-click to open the shortcut menu, and select **Choose Items**.</span></span>  
  
3.  <span data-ttu-id="ef6ef-149">En el **elegir elementos del cuadro de herramientas** cuadro de diálogo, desplácese hacia abajo el **nombre** columna hasta que encuentre **ToolStripPanel**.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-149">In the **Choose Toolbox Items** dialog box, scroll down the **Name** column until you find **ToolStripPanel**.</span></span>  
  
4.  <span data-ttu-id="ef6ef-150">Seleccione la casilla de verificación por **ToolStripPanel**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-150">Select the check box by **ToolStripPanel**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="ef6ef-151">El <xref:System.Windows.Forms.ToolStripPanel> control aparece en el **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-151">The <xref:System.Windows.Forms.ToolStripPanel> control appears in the **Toolbox**.</span></span>  
  
## <a name="creating-a-child-form"></a><span data-ttu-id="ef6ef-152">Creación de un formulario secundario</span><span class="sxs-lookup"><span data-stu-id="ef6ef-152">Creating a Child Form</span></span>  
 <span data-ttu-id="ef6ef-153">En este procedimiento, definirá una clase de formulario secundario independiente que tiene su propio <xref:System.Windows.Forms.MenuStrip> control.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-153">In this procedure, you will define a separate child form class that has its own <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="ef6ef-154">Los elementos de menú para este formulario se combinan con los del formulario primario.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-154">The menu items for this form are merged with those of the parent form.</span></span>  
  
#### <a name="to-define-a-child-form"></a><span data-ttu-id="ef6ef-155">Para definir un formulario secundario</span><span class="sxs-lookup"><span data-stu-id="ef6ef-155">To define a child form</span></span>  
  
1.  <span data-ttu-id="ef6ef-156">Agregue un nuevo formulario denominado `ChildForm` al proyecto.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-156">Add a new form named `ChildForm` to the project.</span></span>  
  
     <span data-ttu-id="ef6ef-157">Para obtener más información, consulte [Cómo: agregar Windows Forms a un proyecto](https://msdn.microsoft.com/library/3d7bb25f-fd90-47cf-9378-fa0d764686c1).</span><span class="sxs-lookup"><span data-stu-id="ef6ef-157">For more information, see [How to: Add Windows Forms to a Project](https://msdn.microsoft.com/library/3d7bb25f-fd90-47cf-9378-fa0d764686c1).</span></span>  
  
2.  <span data-ttu-id="ef6ef-158">Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.MenuStrip> al formulario secundario.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-158">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the child form.</span></span>  
  
3.  <span data-ttu-id="ef6ef-159">Haga clic en el <xref:System.Windows.Forms.MenuStrip> glifo de etiqueta inteligente del control (![glifo de etiqueta inteligente](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) y, a continuación, seleccione **editar elementos**.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-159">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), and then select **Edit Items**.</span></span>  
  
4.  <span data-ttu-id="ef6ef-160">En el **Editor de la colección de elementos** diálogo cuadro, agregue un nuevo <xref:System.Windows.Forms.ToolStripMenuItem> denominado **ChildMenuItem** en el menú secundario.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-160">In the **Items Collection Editor** dialog box, add a new <xref:System.Windows.Forms.ToolStripMenuItem> named **ChildMenuItem** to the child menu.</span></span>  
  
     <span data-ttu-id="ef6ef-161">Para obtener más información, consulte [Editor de colección de elementos ToolStrip](https://msdn.microsoft.com/library/e681f3ab-94ba-4b2b-ac64-1dfad46caa25).</span><span class="sxs-lookup"><span data-stu-id="ef6ef-161">For more information, see [ToolStrip Items Collection Editor](https://msdn.microsoft.com/library/e681f3ab-94ba-4b2b-ac64-1dfad46caa25).</span></span>  
  
## <a name="testing-the-form"></a><span data-ttu-id="ef6ef-162">Comprobar el formulario</span><span class="sxs-lookup"><span data-stu-id="ef6ef-162">Testing the Form</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="ef6ef-163">Para probar el formulario</span><span class="sxs-lookup"><span data-stu-id="ef6ef-163">To test your form</span></span>  
  
1.  <span data-ttu-id="ef6ef-164">Presione F5 para compilar y ejecutar el formulario.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-164">Press F5 to compile and run your form.</span></span>  
  
2.  <span data-ttu-id="ef6ef-165">Haga clic en el **ventana** elemento de menú para abrir el menú y, a continuación, haga clic en **New**.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-165">Click the **Window** menu item to open the menu, and then click **New**.</span></span>  
  
     <span data-ttu-id="ef6ef-166">Se crea un nuevo formulario secundario en el área de cliente del formulario MDI.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-166">A new child form is created in the form's MDI client area.</span></span> <span data-ttu-id="ef6ef-167">Menú del formulario secundario se combina con el menú principal.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-167">The child form's menu is merged with the main menu.</span></span>  
  
3.  <span data-ttu-id="ef6ef-168">Cierre el formulario secundario.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-168">Close the child form.</span></span>  
  
     <span data-ttu-id="ef6ef-169">Menú del formulario secundario se quita en el menú principal.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-169">The child form's menu is removed from the main menu.</span></span>  
  
4.  <span data-ttu-id="ef6ef-170">Haga clic en **New** varias veces.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-170">Click **New** several times.</span></span>  
  
     <span data-ttu-id="ef6ef-171">Los formularios secundarios aparecen automáticamente en el **ventana** elemento de menú porque la <xref:System.Windows.Forms.MenuStrip> del control <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> se asigna la propiedad.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-171">The child forms are automatically listed under the **Window** menu item because the <xref:System.Windows.Forms.MenuStrip> control's <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property is assigned.</span></span>  
  
## <a name="adding-toolstrip-support"></a><span data-ttu-id="ef6ef-172">Agregar compatibilidad de ToolStrip</span><span class="sxs-lookup"><span data-stu-id="ef6ef-172">Adding ToolStrip Support</span></span>  
 <span data-ttu-id="ef6ef-173">En este procedimiento, agregará cuatro <xref:System.Windows.Forms.ToolStrip> controles al formulario primario MDI.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-173">In this procedure, you will add four <xref:System.Windows.Forms.ToolStrip> controls to the MDI parent form.</span></span> <span data-ttu-id="ef6ef-174">Cada <xref:System.Windows.Forms.ToolStrip> se agrega el control dentro de un <xref:System.Windows.Forms.ToolStripPanel> control, que está acoplada al borde del formulario.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-174">Each <xref:System.Windows.Forms.ToolStrip> control is added inside a <xref:System.Windows.Forms.ToolStripPanel> control, which is docked to the edge of the form.</span></span>  
  
#### <a name="to-add-toolstrip-controls-to-the-mdi-parent-form"></a><span data-ttu-id="ef6ef-175">Para agregar los controles ToolStrip al formulario primario MDI</span><span class="sxs-lookup"><span data-stu-id="ef6ef-175">To add ToolStrip controls to the MDI parent form</span></span>  
  
1.  <span data-ttu-id="ef6ef-176">Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.ToolStripPanel> al formulario.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-176">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStripPanel> control onto the form.</span></span>  
  
2.  <span data-ttu-id="ef6ef-177">Con el <xref:System.Windows.Forms.ToolStripPanel> control seleccionado, haga doble clic en el <xref:System.Windows.Forms.ToolStrip> en controlar la **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-177">With the <xref:System.Windows.Forms.ToolStripPanel> control selected, double-click the <xref:System.Windows.Forms.ToolStrip> control in the **Toolbox**.</span></span>  
  
     <span data-ttu-id="ef6ef-178">Un <xref:System.Windows.Forms.ToolStrip> control se crea en el <xref:System.Windows.Forms.ToolStripPanel> control.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-178">A <xref:System.Windows.Forms.ToolStrip> control is created in the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
3.  <span data-ttu-id="ef6ef-179">Seleccione el control <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-179">Select the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
4.  <span data-ttu-id="ef6ef-180">En la ventana Propiedades, cambie el valor del control <xref:System.Windows.Forms.Control.Dock%2A> propiedad <xref:System.Windows.Forms.DockStyle.Left>.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-180">In the Properties window, change the value of the control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Left>.</span></span>  
  
     <span data-ttu-id="ef6ef-181">El <xref:System.Windows.Forms.ToolStripPanel> controlar lo acopla en el lado izquierdo del formulario, bajo el menú principal.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-181">The <xref:System.Windows.Forms.ToolStripPanel> control docks to the left side of the form, underneath the main menu.</span></span> <span data-ttu-id="ef6ef-182">El área de cliente MDI cambia de tamaño para ajustarse a la <xref:System.Windows.Forms.ToolStripPanel> control.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-182">The MDI client area resizes to fit the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
5.  <span data-ttu-id="ef6ef-183">Repita los pasos 1 a 4.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-183">Repeat steps 1 through 4.</span></span>  
  
     <span data-ttu-id="ef6ef-184">Acoplar el nuevo <xref:System.Windows.Forms.ToolStripPanel> control a la parte superior del formulario.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-184">Dock the new <xref:System.Windows.Forms.ToolStripPanel> control to the top of the form.</span></span>  
  
     <span data-ttu-id="ef6ef-185">El <xref:System.Windows.Forms.ToolStripPanel> está acoplado el control bajo el menú principal, pero a la derecha de la primera <xref:System.Windows.Forms.ToolStripPanel> control.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-185">The <xref:System.Windows.Forms.ToolStripPanel> control is docked underneath the main menu, but to the right of the first <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="ef6ef-186">Este paso muestra la importancia del orden z para colocar correctamente <xref:System.Windows.Forms.ToolStripPanel> controles.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-186">This step illustrates the importance of z-order in correctly positioning <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>  
  
6.  <span data-ttu-id="ef6ef-187">Repita los pasos del 1 al 4 para dos más <xref:System.Windows.Forms.ToolStripPanel> controles.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-187">Repeat steps 1 through 4 for two more <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>  
  
     <span data-ttu-id="ef6ef-188">Acoplar el nuevo <xref:System.Windows.Forms.ToolStripPanel> controles a la derecha e inferior del formulario.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-188">Dock the new <xref:System.Windows.Forms.ToolStripPanel> controls to the right and bottom of the form.</span></span>  
  
## <a name="arranging-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="ef6ef-189">Organizar controles ToolStripPanel por orden Z</span><span class="sxs-lookup"><span data-stu-id="ef6ef-189">Arranging ToolStripPanel Controls by Z-order</span></span>  
 <span data-ttu-id="ef6ef-190">La posición de un acoplado <xref:System.Windows.Forms.ToolStripPanel> control en el formulario MDI viene determinada por la posición del control en el orden z.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-190">The position of a docked <xref:System.Windows.Forms.ToolStripPanel> control on your MDI form is determined by the control's position in the z-order.</span></span> <span data-ttu-id="ef6ef-191">Puede organizar fácilmente el orden z de los controles en la ventana Esquema del documento.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-191">You can easily arrange the z-order of your controls in the Document Outline window.</span></span>  
  
#### <a name="to-arrange-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="ef6ef-192">Para organizar los controles ToolStripPanel por orden Z</span><span class="sxs-lookup"><span data-stu-id="ef6ef-192">To arrange ToolStripPanel controls by Z-order</span></span>  
  
1.  <span data-ttu-id="ef6ef-193">En el **vista** menú, haga clic en **Other Windows**y, a continuación, haga clic en **esquema del documento**.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-193">In the **View** menu, click **Other Windows**, and then click **Document Outline**.</span></span>  
  
     <span data-ttu-id="ef6ef-194">La organización de su <xref:System.Windows.Forms.ToolStripPanel> controles desde el procedimiento anterior no es estándar.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-194">The arrangement of your <xref:System.Windows.Forms.ToolStripPanel> controls from the previous procedure is nonstandard.</span></span> <span data-ttu-id="ef6ef-195">Esto es porque el orden z no es correcto.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-195">This is because the z-order is not correct.</span></span> <span data-ttu-id="ef6ef-196">Utilice la ventana Esquema del documento para cambiar el orden z de los controles.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-196">Use the Document Outline window to change the z-order of the controls.</span></span>  
  
2.  <span data-ttu-id="ef6ef-197">En la ventana Esquema del documento, seleccione **ToolStripPanel4**.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-197">In the Document Outline window, select **ToolStripPanel4**.</span></span>  
  
3.  <span data-ttu-id="ef6ef-198">Haga clic en el botón de flecha abajo varias veces, hasta **ToolStripPanel4** en la parte inferior de la lista.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-198">Click the down-arrow button repeatedly, until **ToolStripPanel4** is at the bottom of the list.</span></span>  
  
     <span data-ttu-id="ef6ef-199">El **ToolStripPanel4** está acoplado el control a la parte inferior del formulario, debajo de los demás controles.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-199">The **ToolStripPanel4** control is docked to the bottom of the form, underneath the other controls.</span></span>  
  
4.  <span data-ttu-id="ef6ef-200">Seleccione **ToolStripPanel2**.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-200">Select **ToolStripPanel2**.</span></span>  
  
5.  <span data-ttu-id="ef6ef-201">Haga clic en el botón de flecha hacia abajo una vez para colocar el control en tercer lugar en la lista.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-201">Click the down-arrow button one time to position the control third in the list.</span></span>  
  
     <span data-ttu-id="ef6ef-202">El **ToolStripPanel2** está acoplado el control a la parte superior del formulario, bajo el menú principal y encima de los otros controles.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-202">The **ToolStripPanel2** control is docked to the top of the form, underneath the main menu and above the other controls.</span></span>  
  
6.  <span data-ttu-id="ef6ef-203">Seleccione los distintos controles en el **esquema del documento** ventana y moverlos a distintas posiciones en el orden z.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-203">Select various controls in the **Document Outline** window and move them to different positions in the z-order.</span></span> <span data-ttu-id="ef6ef-204">Tenga en cuenta el efecto del orden z de colocación de los controles acoplados.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-204">Note the effect of the z-order on the placement of docked controls.</span></span> <span data-ttu-id="ef6ef-205">Utilice CTRL-Z o **deshacer** en el **editar** menú Deshacer los cambios.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-205">Use CTRL-Z or **Undo** on the **Edit** menu to undo your changes.</span></span>  
  
## <a name="checkpoint"></a><span data-ttu-id="ef6ef-206">Punto de control</span><span class="sxs-lookup"><span data-stu-id="ef6ef-206">Checkpoint</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="ef6ef-207">Para probar el formulario</span><span class="sxs-lookup"><span data-stu-id="ef6ef-207">To test your form</span></span>  
  
1.  <span data-ttu-id="ef6ef-208">Presione F5 para compilar y ejecutar el formulario.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-208">Press F5 to compile and run your form.</span></span>  
  
2.  <span data-ttu-id="ef6ef-209">Haga clic en el control de un <xref:System.Windows.Forms.ToolStrip> control y arrastre el control a otras posiciones en el formulario.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-209">Click the grip of a <xref:System.Windows.Forms.ToolStrip> control and drag the control to different positions on the form.</span></span>  
  
     <span data-ttu-id="ef6ef-210">Puede arrastrar un <xref:System.Windows.Forms.ToolStrip> control desde uno <xref:System.Windows.Forms.ToolStripPanel> control a otro.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-210">You can drag a <xref:System.Windows.Forms.ToolStrip> control from one <xref:System.Windows.Forms.ToolStripPanel> control to another.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ef6ef-211">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="ef6ef-211">Next Steps</span></span>  
 <span data-ttu-id="ef6ef-212">En este tutorial, ha creado un formulario MDI principal con <xref:System.Windows.Forms.ToolStrip> controles y combinación de menús.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-212">In this walkthrough, you have created an MDI parent form with <xref:System.Windows.Forms.ToolStrip> controls and menu merging.</span></span> <span data-ttu-id="ef6ef-213">Puede usar el <xref:System.Windows.Forms.ToolStrip> familia de controles para muchos otros objetivos:</span><span class="sxs-lookup"><span data-stu-id="ef6ef-213">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>  
  
-   <span data-ttu-id="ef6ef-214">Crear menús contextuales para los controles con <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-214">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="ef6ef-215">Para obtener más información, consulte [información general del componente ContextMenu](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="ef6ef-215">For more information, see [ContextMenu Component Overview](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="ef6ef-216">Crea un formulario con un menú estándar rellenado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-216">Created a form with an automatically populated standard menu.</span></span> <span data-ttu-id="ef6ef-217">Para obtener más información, consulte [Tutorial: proporcionar elementos de menú estándar a un formulario](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="ef6ef-217">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>  
  
-   <span data-ttu-id="ef6ef-218">Asigne a su <xref:System.Windows.Forms.ToolStrip> controla un aspecto profesional.</span><span class="sxs-lookup"><span data-stu-id="ef6ef-218">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="ef6ef-219">Para obtener más información, consulte [Cómo: establecer la representación de ToolStrip para una aplicación](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="ef6ef-219">For more information, see [How to: Set the ToolStrip Renderer for an Application](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef6ef-220">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef6ef-220">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [<span data-ttu-id="ef6ef-221">Crear formularios principales MDI</span><span class="sxs-lookup"><span data-stu-id="ef6ef-221">How to: Create MDI Parent Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [<span data-ttu-id="ef6ef-222">Crear formularios MDI secundarios</span><span class="sxs-lookup"><span data-stu-id="ef6ef-222">How to: Create MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [<span data-ttu-id="ef6ef-223">Insertar un elemento MenuStrip en un menú desplegable MDI</span><span class="sxs-lookup"><span data-stu-id="ef6ef-223">How to: Insert a MenuStrip into an MDI Drop-Down Menu</span></span>](../../../../docs/framework/winforms/controls/how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)  
 [<span data-ttu-id="ef6ef-224">Control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="ef6ef-224">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
