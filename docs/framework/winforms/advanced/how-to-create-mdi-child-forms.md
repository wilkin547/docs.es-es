---
title: Procedimiento para crear formularios secundarios MDI
description: Obtenga información sobre cómo usar Visual Studio para crear un formulario MDI (interfaz de múltiples documentos) secundario que muestre un control RichTextBox.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- MDI [Windows Forms], creating forms
- child forms
ms.assetid: 164b69bb-2eca-4339-ada3-0679eb2c6dda
ms.openlocfilehash: 7fe5cde342f0f5ee078f888b7492cd4618bea5c4
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903186"
---
# <a name="how-to-create-mdi-child-forms"></a><span data-ttu-id="2d101-103">Cómo: crear formularios MDI secundarios</span><span class="sxs-lookup"><span data-stu-id="2d101-103">How to: Create MDI child forms</span></span>

<span data-ttu-id="2d101-104">Los formularios MDI secundarios son un elemento fundamental de [las aplicaciones de interfaz de múltiples documentos (MDI)](multiple-document-interface-mdi-applications.md), ya que estos formularios son el centro de la interacción con el usuario.</span><span class="sxs-lookup"><span data-stu-id="2d101-104">MDI child forms are an essential element of [Multiple-Document Interface (MDI) applications](multiple-document-interface-mdi-applications.md), as these forms are the center of user interaction.</span></span>

<span data-ttu-id="2d101-105">En el procedimiento siguiente, usará Visual Studio para crear un formulario MDI secundario que muestre un <xref:System.Windows.Forms.RichTextBox> control, similar a la mayoría de las aplicaciones de procesamiento de texto.</span><span class="sxs-lookup"><span data-stu-id="2d101-105">In the following procedure, you'll use Visual Studio to create an MDI child form that displays a <xref:System.Windows.Forms.RichTextBox> control, similar to most word-processing applications.</span></span> <span data-ttu-id="2d101-106">Al sustituir el <xref:System.Windows.Forms> control por otros controles, como el <xref:System.Windows.Forms.DataGridView> control, o una combinación de controles, puede crear ventanas secundarias MDI (y, por extensión, aplicaciones MDI) con diversas posibilidades.</span><span class="sxs-lookup"><span data-stu-id="2d101-106">By substituting the <xref:System.Windows.Forms> control with other controls, such as the <xref:System.Windows.Forms.DataGridView> control, or a mixture of controls, you can create MDI child windows (and, by extension, MDI applications) with diverse possibilities.</span></span>

## <a name="create-mdi-child-forms"></a><span data-ttu-id="2d101-107">Crear formularios MDI secundarios</span><span class="sxs-lookup"><span data-stu-id="2d101-107">Create MDI child forms</span></span>

1. <span data-ttu-id="2d101-108">Cree un nuevo proyecto de aplicación de Windows Forms en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2d101-108">Create a new Windows Forms application project in Visual Studio.</span></span> <span data-ttu-id="2d101-109">En la ventana **propiedades** del formulario, establezca su <xref:System.Windows.Forms.Form.IsMdiContainer%2A> propiedad en `true` y su `WindowsState` propiedad en `Maximized` .</span><span class="sxs-lookup"><span data-stu-id="2d101-109">In the **Properties** window for the form, set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true` and its `WindowsState` property to `Maximized`.</span></span>

   <span data-ttu-id="2d101-110">Esto hace que el formulario se designe como contenedor MDI de las ventanas secundarias.</span><span class="sxs-lookup"><span data-stu-id="2d101-110">This designates the form as an MDI container for child windows.</span></span>

2. <span data-ttu-id="2d101-111">Desde el `Toolbox`, arrastre un control <xref:System.Windows.Forms.MenuStrip> al formulario.</span><span class="sxs-lookup"><span data-stu-id="2d101-111">From the `Toolbox`, drag a <xref:System.Windows.Forms.MenuStrip> control to the form.</span></span> <span data-ttu-id="2d101-112">Establezca su `Text` propiedad en **archivo**.</span><span class="sxs-lookup"><span data-stu-id="2d101-112">Set its `Text` property to **File**.</span></span>

3. <span data-ttu-id="2d101-113">Haga clic en los puntos suspensivos (...) junto a la propiedad **elementos** y haga clic en **Agregar** para agregar dos elementos de menú de la franja de herramientas secundaria.</span><span class="sxs-lookup"><span data-stu-id="2d101-113">Click the ellipsis (…) next to the **Items** property, and click **Add** to add two child tool strip menu items.</span></span> <span data-ttu-id="2d101-114">Establezca la `Text` propiedad de estos elementos en **nuevo** y **ventana**.</span><span class="sxs-lookup"><span data-stu-id="2d101-114">Set the `Text` property for these items to **New** and **Window**.</span></span>

4. <span data-ttu-id="2d101-115">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="2d101-115">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

5. <span data-ttu-id="2d101-116">En el cuadro de diálogo **Agregar nuevo elemento** , seleccione **Windows Form** (en Visual Basic o en Visual C#) o **Windows Forms aplicación (.net)** (en Visual C++) en el panel **plantillas** .</span><span class="sxs-lookup"><span data-stu-id="2d101-116">In the **Add New Item** dialog box, select **Windows Form** (in Visual Basic or in Visual C#) or **Windows Forms Application (.NET)** (in Visual C++) from the **Templates** pane.</span></span> <span data-ttu-id="2d101-117">En el cuadro **nombre** , asigne al formulario el nombre **Form2**.</span><span class="sxs-lookup"><span data-stu-id="2d101-117">In the **Name** box, name the form **Form2**.</span></span> <span data-ttu-id="2d101-118">Seleccione **abrir** para agregar el formulario al proyecto.</span><span class="sxs-lookup"><span data-stu-id="2d101-118">Select **Open** to add the form to the project.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2d101-119">El formulario secundario MDI creado en este paso es un Windows Form estándar.</span><span class="sxs-lookup"><span data-stu-id="2d101-119">The MDI child form you created in this step is a standard Windows Form.</span></span> <span data-ttu-id="2d101-120">Como tal, tiene una propiedad <xref:System.Windows.Forms.Form.Opacity%2A>, que le permite controlar la transparencia del formulario.</span><span class="sxs-lookup"><span data-stu-id="2d101-120">As such, it has an <xref:System.Windows.Forms.Form.Opacity%2A> property, which enables you to control the transparency of the form.</span></span> <span data-ttu-id="2d101-121">Sin embargo, la propiedad <xref:System.Windows.Forms.Form.Opacity%2A> se diseñó para ventanas de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="2d101-121">However, the <xref:System.Windows.Forms.Form.Opacity%2A> property was designed for top-level windows.</span></span> <span data-ttu-id="2d101-122">No la use con formularios secundarios MDI porque se pueden producir problemas de dibujo.</span><span class="sxs-lookup"><span data-stu-id="2d101-122">Do not use it with MDI child forms, as painting problems can occur.</span></span>

     <span data-ttu-id="2d101-123">Este formulario será la plantilla para los formularios secundarios MDI.</span><span class="sxs-lookup"><span data-stu-id="2d101-123">This form will be the template for your MDI child forms.</span></span>

     <span data-ttu-id="2d101-124">Se abre el **Diseñador de Windows Forms** , que muestra **Form2**.</span><span class="sxs-lookup"><span data-stu-id="2d101-124">The **Windows Forms Designer** opens, displaying **Form2**.</span></span>

6. <span data-ttu-id="2d101-125">En el **cuadro de herramientas**, arrastre un control **RichTextBox** al formulario.</span><span class="sxs-lookup"><span data-stu-id="2d101-125">From the **Toolbox**, drag a **RichTextBox** control to the form.</span></span>

7. <span data-ttu-id="2d101-126">En la ventana **propiedades** , establezca la `Anchor` propiedad en **superior, izquierda** y la `Dock` propiedad en **rellenar**.</span><span class="sxs-lookup"><span data-stu-id="2d101-126">In the **Properties** window, set the `Anchor` property to **Top, Left** and the `Dock` property to **Fill**.</span></span>

   <span data-ttu-id="2d101-127">Esto hace que el control <xref:System.Windows.Forms.RichTextBox> rellene completamente el área del formulario MDI secundario, incluso cuando se cambia el tamaño del formulario.</span><span class="sxs-lookup"><span data-stu-id="2d101-127">This causes the <xref:System.Windows.Forms.RichTextBox> control to completely fill the area of the MDI child form, even when the form is resized.</span></span>

8. <span data-ttu-id="2d101-128">Haga doble clic en el elemento de menú **nuevo** para crear un <xref:System.Windows.Forms.Control.Click> controlador de eventos para él.</span><span class="sxs-lookup"><span data-stu-id="2d101-128">Double click the **New** menu item to create a <xref:System.Windows.Forms.Control.Click> event handler for it.</span></span>

9. <span data-ttu-id="2d101-129">Inserte código similar al siguiente para crear un nuevo formulario MDI secundario cuando el usuario haga clic en el **nuevo** elemento de menú.</span><span class="sxs-lookup"><span data-stu-id="2d101-129">Insert code similar to the following to create a new MDI child form when the user clicks the **New** menu item.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2d101-130">En el ejemplo siguiente, el controlador de eventos controla el evento <xref:System.Windows.Forms.Control.Click> para `MenuItem2`.</span><span class="sxs-lookup"><span data-stu-id="2d101-130">In the following example, the event handler handles the <xref:System.Windows.Forms.Control.Click> event for `MenuItem2`.</span></span> <span data-ttu-id="2d101-131">Tenga en cuenta que, en función de los detalles de la arquitectura de la aplicación, es posible que el **nuevo** elemento de menú no sea `MenuItem2` .</span><span class="sxs-lookup"><span data-stu-id="2d101-131">Be aware that, depending on the specifics of your application architecture, your **New** menu item may not be `MenuItem2`.</span></span>

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

   <span data-ttu-id="2d101-132">En C++, agregue la siguiente `#include` Directiva al principio de Form1. h:</span><span class="sxs-lookup"><span data-stu-id="2d101-132">In C++, add the following `#include` directive at the top of Form1.h:</span></span>

   ```cpp
   #include "Form2.h"
   ```

10. <span data-ttu-id="2d101-133">En la lista desplegable de la parte superior de la ventana **propiedades** , seleccione la franja de menús correspondiente a la franja de menú **archivo** y establezca la <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> propiedad en la ventana <xref:System.Windows.Forms.ToolStripMenuItem> .</span><span class="sxs-lookup"><span data-stu-id="2d101-133">In the drop-down list at the top of the **Properties** window, select the menu strip that corresponds to the **File** menu strip and set the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to the Window <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>

    <span data-ttu-id="2d101-134">Esto permite que el menú **ventana** mantenga una lista de ventanas secundarias MDI abiertas con una marca de verificación junto a la ventana secundaria activa.</span><span class="sxs-lookup"><span data-stu-id="2d101-134">This enables the **Window** menu to maintain a list of open MDI child windows with a check mark next to the active child window.</span></span>

11. <span data-ttu-id="2d101-135">Presione **F5** para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2d101-135">Press **F5** to run the application.</span></span> <span data-ttu-id="2d101-136">Al seleccionar **nuevo** en el menú **archivo** , puede crear nuevos formularios MDI secundarios, cuyo seguimiento se mantiene en el elemento de menú **ventana** .</span><span class="sxs-lookup"><span data-stu-id="2d101-136">By selecting **New** from the **File** menu, you can create new MDI child forms, which are kept track of in the **Window** menu item.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2d101-137">Cuando un formulario MDI secundario tiene un componente <xref:System.Windows.Forms.MainMenu> (por lo general, con una estructura de menús con elementos de menú) y se abre dentro de un formulario MDI primario que tiene un componente <xref:System.Windows.Forms.MainMenu> (por lo general, con una estructura de menús con elementos de menú), los elementos de menú se combinan automáticamente si ha establecido la propiedad <xref:System.Windows.Forms.MenuItem.MergeType%2A> (y, opcionalmente, la propiedad <xref:System.Windows.Forms.MenuItem.MergeOrder%2A>).</span><span class="sxs-lookup"><span data-stu-id="2d101-137">When an MDI child form has a <xref:System.Windows.Forms.MainMenu> component (with, usually, a menu structure of menu items) and it is opened within an MDI parent form that has a <xref:System.Windows.Forms.MainMenu> component (with, usually, a menu structure of menu items), the menu items will merge automatically if you have set the <xref:System.Windows.Forms.MenuItem.MergeType%2A> property (and optionally, the <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> property).</span></span> <span data-ttu-id="2d101-138">Establezca la propiedad <xref:System.Windows.Forms.MenuItem.MergeType%2A> de ambos componentes <xref:System.Windows.Forms.MainMenu> y todos los elementos de menú del formulario secundario en <xref:System.Windows.Forms.MenuMerge.MergeItems>.</span><span class="sxs-lookup"><span data-stu-id="2d101-138">Set the <xref:System.Windows.Forms.MenuItem.MergeType%2A> property of both <xref:System.Windows.Forms.MainMenu> components and all of the menu items of the child form to <xref:System.Windows.Forms.MenuMerge.MergeItems>.</span></span> <span data-ttu-id="2d101-139">Además, establezca la propiedad <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> para que los elementos de ambos menús aparezcan en el orden deseado.</span><span class="sxs-lookup"><span data-stu-id="2d101-139">Additionally, set the <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> property so that the menu items from both menus appear in the desired order.</span></span> <span data-ttu-id="2d101-140">Tenga en cuenta también que, cuando se cierra un formulario MDI primario, cada uno de los formularios MDI secundarios genera un evento <xref:System.Windows.Forms.Form.Closing> antes de que se produzca el evento <xref:System.Windows.Forms.Form.Closing> para el formulario MDI primario.</span><span class="sxs-lookup"><span data-stu-id="2d101-140">Moreover, keep in mind that when you close an MDI parent form, each of the MDI child forms raises a <xref:System.Windows.Forms.Form.Closing> event before the <xref:System.Windows.Forms.Form.Closing> event for the MDI parent is raised.</span></span> <span data-ttu-id="2d101-141">Cancelar el evento <xref:System.Windows.Forms.Form.Closing> de un elemento MDI secundario no impedirá que se produzca el evento <xref:System.Windows.Forms.Form.Closing> del elemento MDI primario; sin embargo, el argumento <xref:System.ComponentModel.CancelEventArgs> del evento <xref:System.Windows.Forms.Form.Closing> del elemento MDI primario ahora se establecerá en `true`.</span><span class="sxs-lookup"><span data-stu-id="2d101-141">Canceling an MDI child's <xref:System.Windows.Forms.Form.Closing> event will not prevent the MDI parent's <xref:System.Windows.Forms.Form.Closing> event from being raised; however, the <xref:System.ComponentModel.CancelEventArgs> argument for the MDI parent's <xref:System.Windows.Forms.Form.Closing> event will now be set to `true`.</span></span> <span data-ttu-id="2d101-142">Puede forzar el cierre del formularios MDI primario y de todos los formularios MDI secundarios estableciendo el argumento <xref:System.ComponentModel.CancelEventArgs> en `false`.</span><span class="sxs-lookup"><span data-stu-id="2d101-142">You can force the MDI parent and all MDI child forms to close by setting the <xref:System.ComponentModel.CancelEventArgs> argument to `false`.</span></span>

## <a name="see-also"></a><span data-ttu-id="2d101-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2d101-143">See also</span></span>

- [<span data-ttu-id="2d101-144">Aplicaciones de interfaz de múltiples documentos (MDI)</span><span class="sxs-lookup"><span data-stu-id="2d101-144">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="2d101-145">Procedimiento para crear formularios principales MDI</span><span class="sxs-lookup"><span data-stu-id="2d101-145">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="2d101-146">Procedimiento para determinar el formulario secundario MDI activo</span><span class="sxs-lookup"><span data-stu-id="2d101-146">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)
- [<span data-ttu-id="2d101-147">Procedimiento para enviar datos al formulario secundario MDI activo</span><span class="sxs-lookup"><span data-stu-id="2d101-147">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)
- [<span data-ttu-id="2d101-148">Procedimiento para organizar formularios secundarios MDI</span><span class="sxs-lookup"><span data-stu-id="2d101-148">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
