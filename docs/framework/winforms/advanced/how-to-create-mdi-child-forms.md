---
title: Procedimiento para crear formularios secundarios MDI
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- MDI [Windows Forms], creating forms
- child forms
ms.assetid: 164b69bb-2eca-4339-ada3-0679eb2c6dda
ms.openlocfilehash: 73f2004470d5d1da04199af75832cefd6348ce18
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937675"
---
# <a name="how-to-create-mdi-child-forms"></a><span data-ttu-id="171c0-102">Procedimiento para crear formularios secundarios MDI</span><span class="sxs-lookup"><span data-stu-id="171c0-102">How to: Create MDI Child Forms</span></span>
<span data-ttu-id="171c0-103">Formularios secundarios MDI son un elemento esencial de [aplicaciones de interfaz de múltiples documentos (MDI)](multiple-document-interface-mdi-applications.md), ya que estos formularios son el centro de la interacción del usuario.</span><span class="sxs-lookup"><span data-stu-id="171c0-103">MDI child forms are an essential element of [Multiple-Document Interface (MDI) Applications](multiple-document-interface-mdi-applications.md), as these forms are the center of user interaction.</span></span>  
  
 <span data-ttu-id="171c0-104">En el siguiente procedimiento, va a crear formulario MDI secundario que muestra un control <xref:System.Windows.Forms.RichTextBox>, similar a la mayoría de las aplicaciones de procesamiento de texto.</span><span class="sxs-lookup"><span data-stu-id="171c0-104">In the following procedure, you will create MDI child form that displays a <xref:System.Windows.Forms.RichTextBox> control, similar to most word-processing applications.</span></span> <span data-ttu-id="171c0-105">Sustituir el control <xref:System.Windows.Forms> por otros controles, como el control <xref:System.Windows.Forms.DataGridView>, o por una mezcla de controles permite crear ventanas secundarias MDI (y, por extensión, aplicaciones MDI) con diversas posibilidades.</span><span class="sxs-lookup"><span data-stu-id="171c0-105">Substituting the <xref:System.Windows.Forms> control with other controls, such as the <xref:System.Windows.Forms.DataGridView> control, or a mixture of controls enables you to create MDI child windows (and, by extension, MDI applications) with diverse possibilities.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="171c0-106">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="171c0-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="171c0-107">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="171c0-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="171c0-108">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="171c0-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-mdi-child-forms"></a><span data-ttu-id="171c0-109">Para crear formularios secundarios MDI</span><span class="sxs-lookup"><span data-stu-id="171c0-109">To create MDI child forms</span></span>  
  
1. <span data-ttu-id="171c0-110">Cree un nuevo proyecto de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="171c0-110">Create a new Windows Forms project.</span></span> <span data-ttu-id="171c0-111">En **las propiedades de Windows** del formulario, establezca su <xref:System.Windows.Forms.Form.IsMdiContainer%2A> propiedad `true`y su `WindowsState` propiedad `Maximized`.</span><span class="sxs-lookup"><span data-stu-id="171c0-111">In **the Properties Windows** for the form, set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`, and its `WindowsState` property to `Maximized`.</span></span>  
  
     <span data-ttu-id="171c0-112">Esto hace que el formulario se designe como contenedor MDI de las ventanas secundarias.</span><span class="sxs-lookup"><span data-stu-id="171c0-112">This designates the form as an MDI container for child windows.</span></span>  
  
2. <span data-ttu-id="171c0-113">Desde el `Toolbox`, arrastre un control <xref:System.Windows.Forms.MenuStrip> al formulario.</span><span class="sxs-lookup"><span data-stu-id="171c0-113">From the `Toolbox`, drag a <xref:System.Windows.Forms.MenuStrip> control to the form.</span></span> <span data-ttu-id="171c0-114">Establezca su `Text` propiedad **archivo**.</span><span class="sxs-lookup"><span data-stu-id="171c0-114">Set its `Text` property to **File**.</span></span>  
  
3. <span data-ttu-id="171c0-115">Haga clic en el botón de puntos suspensivos (...) junto a la **elementos** propiedad y haga clic en **agregar** para agregar dos elementos de menú de franja de herramientas secundarios.</span><span class="sxs-lookup"><span data-stu-id="171c0-115">Click the ellipses (…) next to the **Items** property, and click **Add** to add two child tool strip menu items.</span></span> <span data-ttu-id="171c0-116">Establecer el `Text` propiedad para que estos elementos **New** y **ventana**.</span><span class="sxs-lookup"><span data-stu-id="171c0-116">Set the `Text` property for these items to **New** and **Window**.</span></span>  
  
4. <span data-ttu-id="171c0-117">En **el Explorador de soluciones**, haga clic en el proyecto, seleccione **agregar**y, a continuación, seleccione **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="171c0-117">In **Solution Explorer**, right-click the project, point to **Add**, and then select **Add New Item**.</span></span>  
  
5. <span data-ttu-id="171c0-118">En el **Agregar nuevo elemento** cuadro de diálogo, seleccione **formulario Windows** (en Visual Basic o Visual C#) o **aplicación de Windows Forms (. NET)** (en [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) desde el  **Plantillas** panel.</span><span class="sxs-lookup"><span data-stu-id="171c0-118">In the **Add New Item** dialog box, select **Windows Form** (in Visual Basic or in Visual C#) or **Windows Forms Application (.NET)** (in [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) from the **Templates** pane.</span></span> <span data-ttu-id="171c0-119">En el **nombre** cuadro, asigne el nombre del formulario **Form2**.</span><span class="sxs-lookup"><span data-stu-id="171c0-119">In the **Name** box, name the form **Form2**.</span></span> <span data-ttu-id="171c0-120">Haga clic en el **abierto** para agregar el formulario al proyecto.</span><span class="sxs-lookup"><span data-stu-id="171c0-120">Click the **Open** button to add the form to the project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="171c0-121">El formulario secundario MDI creado en este paso es un Windows Form estándar.</span><span class="sxs-lookup"><span data-stu-id="171c0-121">The MDI child form you created in this step is a standard Windows Form.</span></span> <span data-ttu-id="171c0-122">Como tal, tiene una propiedad <xref:System.Windows.Forms.Form.Opacity%2A>, que le permite controlar la transparencia del formulario.</span><span class="sxs-lookup"><span data-stu-id="171c0-122">As such, it has an <xref:System.Windows.Forms.Form.Opacity%2A> property, which enables you to control the transparency of the form.</span></span> <span data-ttu-id="171c0-123">Sin embargo, la propiedad <xref:System.Windows.Forms.Form.Opacity%2A> se diseñó para ventanas de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="171c0-123">However, the <xref:System.Windows.Forms.Form.Opacity%2A> property was designed for top-level windows.</span></span> <span data-ttu-id="171c0-124">No la use con formularios secundarios MDI porque se pueden producir problemas de dibujo.</span><span class="sxs-lookup"><span data-stu-id="171c0-124">Do not use it with MDI child forms, as painting problems can occur.</span></span>  
  
     <span data-ttu-id="171c0-125">Este formulario será la plantilla para los formularios secundarios MDI.</span><span class="sxs-lookup"><span data-stu-id="171c0-125">This form will be the template for your MDI child forms.</span></span>  
  
     <span data-ttu-id="171c0-126">El **Diseñador de Windows Forms** se abre, mostrando **Form2**.</span><span class="sxs-lookup"><span data-stu-id="171c0-126">The **Windows Forms Designer** opens, displaying **Form2**.</span></span>  
  
6. <span data-ttu-id="171c0-127">Desde el **cuadro de herramientas**, arrastre un **RichTextBox** control al formulario.</span><span class="sxs-lookup"><span data-stu-id="171c0-127">From the **Toolbox**, drag a **RichTextBox** control to the form.</span></span>  
  
7. <span data-ttu-id="171c0-128">En el **propiedades** ventana, establezca el `Anchor` propiedad **superior, izquierdo** y el `Dock` propiedad **rellenar**.</span><span class="sxs-lookup"><span data-stu-id="171c0-128">In the **Properties** window, set the `Anchor` property to **Top, Left** and the `Dock` property to **Fill**.</span></span>  
  
     <span data-ttu-id="171c0-129">Esto hace que el control <xref:System.Windows.Forms.RichTextBox> rellene completamente el área del formulario MDI secundario, incluso cuando se cambia el tamaño del formulario.</span><span class="sxs-lookup"><span data-stu-id="171c0-129">This causes the <xref:System.Windows.Forms.RichTextBox> control to completely fill the area of the MDI child form, even when the form is resized.</span></span>  
  
8. <span data-ttu-id="171c0-130">Haga doble clic en el **New** elemento de menú para crear un <xref:System.Windows.Forms.Control.Click> controlador de eventos para él.</span><span class="sxs-lookup"><span data-stu-id="171c0-130">Double click the **New** menu item to create a <xref:System.Windows.Forms.Control.Click> event handler for it.</span></span>  
  
9. <span data-ttu-id="171c0-131">Inserte código similar al siguiente para crear un nuevo formulario MDI secundario cuando el usuario hace clic en el **New** elemento de menú.</span><span class="sxs-lookup"><span data-stu-id="171c0-131">Insert code similar to the following to create a new MDI child form when the user clicks the **New** menu item.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="171c0-132">En el ejemplo siguiente, el controlador de eventos controla el evento <xref:System.Windows.Forms.Control.Click> para `MenuItem2`.</span><span class="sxs-lookup"><span data-stu-id="171c0-132">In the following example, the event handler handles the <xref:System.Windows.Forms.Control.Click> event for `MenuItem2`.</span></span> <span data-ttu-id="171c0-133">Tenga en cuenta que, según las particularidades de la arquitectura de aplicaciones, su **New** no puede ser el elemento de menú `MenuItem2`.</span><span class="sxs-lookup"><span data-stu-id="171c0-133">Be aware that, depending on the specifics of your application architecture, your **New** menu item may not be `MenuItem2`.</span></span>  
  
    ```vb  
    Protected Sub MDIChildNew_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MenuItem2.Click  
       Dim NewMDIChild As New Form2()  
       'Set the Parent Form of the Child window.  
       NewMDIChild.MdiParent = Me  
       'Display the new form.  
       NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    protected void MDIChildNew_Click(object sender, System.EventArgs e){  
       Form2 newMDIChild = new Form2();  
       // Set the Parent Form of the Child window.  
       newMDIChild.MdiParent = this;  
       // Display the new form.  
       newMDIChild.Show();  
    }  
    ```  
  
    ```cpp  
    private:  
       void menuItem2_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          Form2^ newMDIChild = gcnew Form2();  
          // Set the Parent Form of the Child window.  
          newMDIChild->MdiParent = this;  
          // Display the new form.  
          newMDIChild->Show();  
       }  
    ```  
  
     <span data-ttu-id="171c0-134">En [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)], agregue la siguiente directiva `#include` al principio de Form1.h:</span><span class="sxs-lookup"><span data-stu-id="171c0-134">In [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)], add the following `#include` directive at the top of Form1.h:</span></span>  
  
    ```cpp  
    #include "Form2.h"  
    ```  
  
10. <span data-ttu-id="171c0-135">En la lista desplegable en la parte superior de la **propiedades** ventana, seleccione la franja de menú que corresponde a la **archivo** banda del menú y establezca el <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> propiedad a la ventana <xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="171c0-135">In the drop-down list at the top of the **Properties** window, select the menu strip that corresponds to the **File** menu strip and set the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to the Window <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
     <span data-ttu-id="171c0-136">Esto habilitará la **ventana** menú para mantener una lista de ventanas MDI secundarias abiertas con una marca de verificación situada junto a la ventana secundaria activa.</span><span class="sxs-lookup"><span data-stu-id="171c0-136">This will enable the **Window** menu to maintain a list of open MDI child windows with a check mark next to the active child window.</span></span>  
  
11. <span data-ttu-id="171c0-137">Presione F5 para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="171c0-137">Press F5 to run the application.</span></span> <span data-ttu-id="171c0-138">Seleccionando **New** desde el **archivo** menú, puede crear nuevos formularios MDI secundarios, que se mantiene un seguimiento en el **ventana** elemento de menú.</span><span class="sxs-lookup"><span data-stu-id="171c0-138">By selecting **New** from the **File** menu, you can create new MDI child forms, which are kept track of in the **Window** menu item.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="171c0-139">Cuando un formulario MDI secundario tiene un componente <xref:System.Windows.Forms.MainMenu> (por lo general, con una estructura de menús con elementos de menú) y se abre dentro de un formulario MDI primario que tiene un componente <xref:System.Windows.Forms.MainMenu> (por lo general, con una estructura de menús con elementos de menú), los elementos de menú se combinan automáticamente si ha establecido la propiedad <xref:System.Windows.Forms.MenuItem.MergeType%2A> (y, opcionalmente, la propiedad <xref:System.Windows.Forms.MenuItem.MergeOrder%2A>).</span><span class="sxs-lookup"><span data-stu-id="171c0-139">When an MDI child form has a <xref:System.Windows.Forms.MainMenu> component (with, usually, a menu structure of menu items) and it is opened within an MDI parent form that has a <xref:System.Windows.Forms.MainMenu> component (with, usually, a menu structure of menu items), the menu items will merge automatically if you have set the <xref:System.Windows.Forms.MenuItem.MergeType%2A> property (and optionally, the <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> property).</span></span> <span data-ttu-id="171c0-140">Establezca la propiedad <xref:System.Windows.Forms.MenuItem.MergeType%2A> de ambos componentes <xref:System.Windows.Forms.MainMenu> y todos los elementos de menú del formulario secundario en <xref:System.Windows.Forms.MenuMerge.MergeItems>.</span><span class="sxs-lookup"><span data-stu-id="171c0-140">Set the <xref:System.Windows.Forms.MenuItem.MergeType%2A> property of both <xref:System.Windows.Forms.MainMenu> components and all of the menu items of the child form to <xref:System.Windows.Forms.MenuMerge.MergeItems>.</span></span> <span data-ttu-id="171c0-141">Además, establezca la propiedad <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> para que los elementos de ambos menús aparezcan en el orden deseado.</span><span class="sxs-lookup"><span data-stu-id="171c0-141">Additionally, set the <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> property so that the menu items from both menus appear in the desired order.</span></span> <span data-ttu-id="171c0-142">Tenga en cuenta también que, cuando se cierra un formulario MDI primario, cada uno de los formularios MDI secundarios genera un evento <xref:System.Windows.Forms.Form.Closing> antes de que se produzca el evento <xref:System.Windows.Forms.Form.Closing> para el formulario MDI primario.</span><span class="sxs-lookup"><span data-stu-id="171c0-142">Moreover, keep in mind that when you close an MDI parent form, each of the MDI child forms raises a <xref:System.Windows.Forms.Form.Closing> event before the <xref:System.Windows.Forms.Form.Closing> event for the MDI parent is raised.</span></span> <span data-ttu-id="171c0-143">Cancelar el evento <xref:System.Windows.Forms.Form.Closing> de un elemento MDI secundario no impedirá que se produzca el evento <xref:System.Windows.Forms.Form.Closing> del elemento MDI primario; sin embargo, el argumento <xref:System.ComponentModel.CancelEventArgs> del evento <xref:System.Windows.Forms.Form.Closing> del elemento MDI primario ahora se establecerá en `true`.</span><span class="sxs-lookup"><span data-stu-id="171c0-143">Canceling an MDI child's <xref:System.Windows.Forms.Form.Closing> event will not prevent the MDI parent's <xref:System.Windows.Forms.Form.Closing> event from being raised; however, the <xref:System.ComponentModel.CancelEventArgs> argument for the MDI parent's <xref:System.Windows.Forms.Form.Closing> event will now be set to `true`.</span></span> <span data-ttu-id="171c0-144">Puede forzar el cierre del formularios MDI primario y de todos los formularios MDI secundarios estableciendo el argumento <xref:System.ComponentModel.CancelEventArgs> en `false`.</span><span class="sxs-lookup"><span data-stu-id="171c0-144">You can force the MDI parent and all MDI child forms to close by setting the <xref:System.ComponentModel.CancelEventArgs> argument to `false`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="171c0-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="171c0-145">See also</span></span>

- [<span data-ttu-id="171c0-146">Aplicaciones de interfaz de múltiples documentos (MDI)</span><span class="sxs-lookup"><span data-stu-id="171c0-146">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="171c0-147">Cómo: Crear formularios principales MDI</span><span class="sxs-lookup"><span data-stu-id="171c0-147">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="171c0-148">Cómo: Determinar el formulario secundario MDI activo</span><span class="sxs-lookup"><span data-stu-id="171c0-148">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)
- [<span data-ttu-id="171c0-149">Cómo: Enviar datos al formulario secundario MDI activo</span><span class="sxs-lookup"><span data-stu-id="171c0-149">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)
- [<span data-ttu-id="171c0-150">Cómo: Organizar formularios MDI secundarios</span><span class="sxs-lookup"><span data-stu-id="171c0-150">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
