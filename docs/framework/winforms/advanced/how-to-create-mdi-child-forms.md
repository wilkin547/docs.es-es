---
title: Procedimiento para crear formularios secundarios MDI
ms.date: 03/30/2017
dev_langs:
- CSharp
- CPP
- VB
helpviewer_keywords:
- MDI [Windows Forms], creating forms
- child forms
ms.assetid: 164b69bb-2eca-4339-ada3-0679eb2c6dda
ms.openlocfilehash: f5e8682caf658d159f044528f040b99676355448
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040107"
---
# <a name="how-to-create-mdi-child-forms"></a><span data-ttu-id="c2490-102">Procedimiento Crear formularios MDI secundarios</span><span class="sxs-lookup"><span data-stu-id="c2490-102">How to: Create MDI child forms</span></span>

<span data-ttu-id="c2490-103">Los formularios MDI secundarios son un elemento fundamental de [las aplicaciones de interfaz de múltiples documentos (MDI)](multiple-document-interface-mdi-applications.md), ya que estos formularios son el centro de la interacción con el usuario.</span><span class="sxs-lookup"><span data-stu-id="c2490-103">MDI child forms are an essential element of [Multiple-Document Interface (MDI) applications](multiple-document-interface-mdi-applications.md), as these forms are the center of user interaction.</span></span>

<span data-ttu-id="c2490-104">En el procedimiento siguiente, usará Visual Studio para crear un formulario MDI secundario que muestre un <xref:System.Windows.Forms.RichTextBox> control, similar a la mayoría de las aplicaciones de procesamiento de texto.</span><span class="sxs-lookup"><span data-stu-id="c2490-104">In the following procedure, you'll use Visual Studio to create an MDI child form that displays a <xref:System.Windows.Forms.RichTextBox> control, similar to most word-processing applications.</span></span> <span data-ttu-id="c2490-105">Al sustituir el <xref:System.Windows.Forms> control por otros controles, como el <xref:System.Windows.Forms.DataGridView> control, o una combinación de controles, puede crear ventanas secundarias MDI (y, por extensión, aplicaciones MDI) con diversas posibilidades.</span><span class="sxs-lookup"><span data-stu-id="c2490-105">By substituting the <xref:System.Windows.Forms> control with other controls, such as the <xref:System.Windows.Forms.DataGridView> control, or a mixture of controls, you can create MDI child windows (and, by extension, MDI applications) with diverse possibilities.</span></span>

## <a name="create-mdi-child-forms"></a><span data-ttu-id="c2490-106">Crear formularios MDI secundarios</span><span class="sxs-lookup"><span data-stu-id="c2490-106">Create MDI child forms</span></span>

1. <span data-ttu-id="c2490-107">Cree un nuevo proyecto de aplicación de Windows Forms en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c2490-107">Create a new Windows Forms application project in Visual Studio.</span></span> <span data-ttu-id="c2490-108">En la **ventana Propiedades** del formulario, <xref:System.Windows.Forms.Form.IsMdiContainer%2A> establezca su propiedad en `true` y su `WindowsState` propiedad en `Maximized`.</span><span class="sxs-lookup"><span data-stu-id="c2490-108">In the **Properties** window for the form, set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true` and its `WindowsState` property to `Maximized`.</span></span>

   <span data-ttu-id="c2490-109">Esto hace que el formulario se designe como contenedor MDI de las ventanas secundarias.</span><span class="sxs-lookup"><span data-stu-id="c2490-109">This designates the form as an MDI container for child windows.</span></span>

2. <span data-ttu-id="c2490-110">Desde el `Toolbox`, arrastre un control <xref:System.Windows.Forms.MenuStrip> al formulario.</span><span class="sxs-lookup"><span data-stu-id="c2490-110">From the `Toolbox`, drag a <xref:System.Windows.Forms.MenuStrip> control to the form.</span></span> <span data-ttu-id="c2490-111">Establezca su `Text` propiedad en **archivo**.</span><span class="sxs-lookup"><span data-stu-id="c2490-111">Set its `Text` property to **File**.</span></span>

3. <span data-ttu-id="c2490-112">Haga clic en los puntos suspensivos (...) junto a la propiedad **elementos** y haga clic en **Agregar** para agregar dos elementos de menú de la franja de herramientas secundaria.</span><span class="sxs-lookup"><span data-stu-id="c2490-112">Click the ellipsis (…) next to the **Items** property, and click **Add** to add two child tool strip menu items.</span></span> <span data-ttu-id="c2490-113">Establezca la `Text` propiedad de estos elementos en **nuevo** y **ventana**.</span><span class="sxs-lookup"><span data-stu-id="c2490-113">Set the `Text` property for these items to **New** and **Window**.</span></span>

4. <span data-ttu-id="c2490-114">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="c2490-114">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

5. <span data-ttu-id="c2490-115">En el cuadro de diálogo **Agregar nuevo elemento** , **Seleccione Windows Form** (en Visual Basic o en C#visual) o **Windows Forms aplicación (.net)** (en C++visual) en el panel **plantillas** .</span><span class="sxs-lookup"><span data-stu-id="c2490-115">In the **Add New Item** dialog box, select **Windows Form** (in Visual Basic or in Visual C#) or **Windows Forms Application (.NET)** (in Visual C++) from the **Templates** pane.</span></span> <span data-ttu-id="c2490-116">En el cuadro **nombre** , asigne al formulario el nombre **Form2**.</span><span class="sxs-lookup"><span data-stu-id="c2490-116">In the **Name** box, name the form **Form2**.</span></span> <span data-ttu-id="c2490-117">Seleccione **abrir** para agregar el formulario al proyecto.</span><span class="sxs-lookup"><span data-stu-id="c2490-117">Select **Open** to add the form to the project.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c2490-118">El formulario secundario MDI creado en este paso es un Windows Form estándar.</span><span class="sxs-lookup"><span data-stu-id="c2490-118">The MDI child form you created in this step is a standard Windows Form.</span></span> <span data-ttu-id="c2490-119">Como tal, tiene una propiedad <xref:System.Windows.Forms.Form.Opacity%2A>, que le permite controlar la transparencia del formulario.</span><span class="sxs-lookup"><span data-stu-id="c2490-119">As such, it has an <xref:System.Windows.Forms.Form.Opacity%2A> property, which enables you to control the transparency of the form.</span></span> <span data-ttu-id="c2490-120">Sin embargo, la propiedad <xref:System.Windows.Forms.Form.Opacity%2A> se diseñó para ventanas de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="c2490-120">However, the <xref:System.Windows.Forms.Form.Opacity%2A> property was designed for top-level windows.</span></span> <span data-ttu-id="c2490-121">No la use con formularios secundarios MDI porque se pueden producir problemas de dibujo.</span><span class="sxs-lookup"><span data-stu-id="c2490-121">Do not use it with MDI child forms, as painting problems can occur.</span></span>

     <span data-ttu-id="c2490-122">Este formulario será la plantilla para los formularios secundarios MDI.</span><span class="sxs-lookup"><span data-stu-id="c2490-122">This form will be the template for your MDI child forms.</span></span>

     <span data-ttu-id="c2490-123">Se abre el **Diseñador de Windows Forms** , que muestra **Form2**.</span><span class="sxs-lookup"><span data-stu-id="c2490-123">The **Windows Forms Designer** opens, displaying **Form2**.</span></span>

6. <span data-ttu-id="c2490-124">En el **cuadro de herramientas**, arrastre un control **RichTextBox** al formulario.</span><span class="sxs-lookup"><span data-stu-id="c2490-124">From the **Toolbox**, drag a **RichTextBox** control to the form.</span></span>

7. <span data-ttu-id="c2490-125">En la ventana **propiedades** , establezca la `Anchor` propiedad en **superior, izquierda** y la `Dock` propiedad enrellenar.</span><span class="sxs-lookup"><span data-stu-id="c2490-125">In the **Properties** window, set the `Anchor` property to **Top, Left** and the `Dock` property to **Fill**.</span></span>

   <span data-ttu-id="c2490-126">Esto hace que el control <xref:System.Windows.Forms.RichTextBox> rellene completamente el área del formulario MDI secundario, incluso cuando se cambia el tamaño del formulario.</span><span class="sxs-lookup"><span data-stu-id="c2490-126">This causes the <xref:System.Windows.Forms.RichTextBox> control to completely fill the area of the MDI child form, even when the form is resized.</span></span>

8. <span data-ttu-id="c2490-127">Haga doble clic en el elemento de menú nuevo <xref:System.Windows.Forms.Control.Click> para crear un controlador de eventos para él.</span><span class="sxs-lookup"><span data-stu-id="c2490-127">Double click the **New** menu item to create a <xref:System.Windows.Forms.Control.Click> event handler for it.</span></span>

9. <span data-ttu-id="c2490-128">Inserte código similar al siguiente para crear un nuevo formulario MDI secundario cuando el usuario haga clic en el **nuevo** elemento de menú.</span><span class="sxs-lookup"><span data-stu-id="c2490-128">Insert code similar to the following to create a new MDI child form when the user clicks the **New** menu item.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c2490-129">En el ejemplo siguiente, el controlador de eventos controla el evento <xref:System.Windows.Forms.Control.Click> para `MenuItem2`.</span><span class="sxs-lookup"><span data-stu-id="c2490-129">In the following example, the event handler handles the <xref:System.Windows.Forms.Control.Click> event for `MenuItem2`.</span></span> <span data-ttu-id="c2490-130">Tenga en cuenta que, en función de los detalles de la arquitectura de la aplicación , es posible que el nuevo `MenuItem2`elemento de menú no sea.</span><span class="sxs-lookup"><span data-stu-id="c2490-130">Be aware that, depending on the specifics of your application architecture, your **New** menu item may not be `MenuItem2`.</span></span>

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

   <span data-ttu-id="c2490-131">En C++, agregue la siguiente `#include` Directiva al principio de Form1. h:</span><span class="sxs-lookup"><span data-stu-id="c2490-131">In C++, add the following `#include` directive at the top of Form1.h:</span></span>

   ```cpp
   #include "Form2.h"
   ```

10. <span data-ttu-id="c2490-132">En la lista desplegable de la parte superior de la ventana **propiedades** , seleccione la franja de menús correspondiente a la franja de menú **archivo** y establezca <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> la propiedad en la <xref:System.Windows.Forms.ToolStripMenuItem>ventana.</span><span class="sxs-lookup"><span data-stu-id="c2490-132">In the drop-down list at the top of the **Properties** window, select the menu strip that corresponds to the **File** menu strip and set the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to the Window <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>

    <span data-ttu-id="c2490-133">Esto permite que el menú **ventana** mantenga una lista de ventanas secundarias MDI abiertas con una marca de verificación junto a la ventana secundaria activa.</span><span class="sxs-lookup"><span data-stu-id="c2490-133">This enables the **Window** menu to maintain a list of open MDI child windows with a check mark next to the active child window.</span></span>

11. <span data-ttu-id="c2490-134">Presione **F5** para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c2490-134">Press **F5** to run the application.</span></span> <span data-ttu-id="c2490-135">Al seleccionar **nuevo** en el menú **archivo** , puede crear nuevos formularios MDI secundarios, cuyo seguimiento se mantiene en el elemento de menú **ventana** .</span><span class="sxs-lookup"><span data-stu-id="c2490-135">By selecting **New** from the **File** menu, you can create new MDI child forms, which are kept track of in the **Window** menu item.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c2490-136">Cuando un formulario MDI secundario tiene un componente <xref:System.Windows.Forms.MainMenu> (por lo general, con una estructura de menús con elementos de menú) y se abre dentro de un formulario MDI primario que tiene un componente <xref:System.Windows.Forms.MainMenu> (por lo general, con una estructura de menús con elementos de menú), los elementos de menú se combinan automáticamente si ha establecido la propiedad <xref:System.Windows.Forms.MenuItem.MergeType%2A> (y, opcionalmente, la propiedad <xref:System.Windows.Forms.MenuItem.MergeOrder%2A>).</span><span class="sxs-lookup"><span data-stu-id="c2490-136">When an MDI child form has a <xref:System.Windows.Forms.MainMenu> component (with, usually, a menu structure of menu items) and it is opened within an MDI parent form that has a <xref:System.Windows.Forms.MainMenu> component (with, usually, a menu structure of menu items), the menu items will merge automatically if you have set the <xref:System.Windows.Forms.MenuItem.MergeType%2A> property (and optionally, the <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> property).</span></span> <span data-ttu-id="c2490-137">Establezca la propiedad <xref:System.Windows.Forms.MenuItem.MergeType%2A> de ambos componentes <xref:System.Windows.Forms.MainMenu> y todos los elementos de menú del formulario secundario en <xref:System.Windows.Forms.MenuMerge.MergeItems>.</span><span class="sxs-lookup"><span data-stu-id="c2490-137">Set the <xref:System.Windows.Forms.MenuItem.MergeType%2A> property of both <xref:System.Windows.Forms.MainMenu> components and all of the menu items of the child form to <xref:System.Windows.Forms.MenuMerge.MergeItems>.</span></span> <span data-ttu-id="c2490-138">Además, establezca la propiedad <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> para que los elementos de ambos menús aparezcan en el orden deseado.</span><span class="sxs-lookup"><span data-stu-id="c2490-138">Additionally, set the <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> property so that the menu items from both menus appear in the desired order.</span></span> <span data-ttu-id="c2490-139">Tenga en cuenta también que, cuando se cierra un formulario MDI primario, cada uno de los formularios MDI secundarios genera un evento <xref:System.Windows.Forms.Form.Closing> antes de que se produzca el evento <xref:System.Windows.Forms.Form.Closing> para el formulario MDI primario.</span><span class="sxs-lookup"><span data-stu-id="c2490-139">Moreover, keep in mind that when you close an MDI parent form, each of the MDI child forms raises a <xref:System.Windows.Forms.Form.Closing> event before the <xref:System.Windows.Forms.Form.Closing> event for the MDI parent is raised.</span></span> <span data-ttu-id="c2490-140">Cancelar el evento <xref:System.Windows.Forms.Form.Closing> de un elemento MDI secundario no impedirá que se produzca el evento <xref:System.Windows.Forms.Form.Closing> del elemento MDI primario; sin embargo, el argumento <xref:System.ComponentModel.CancelEventArgs> del evento <xref:System.Windows.Forms.Form.Closing> del elemento MDI primario ahora se establecerá en `true`.</span><span class="sxs-lookup"><span data-stu-id="c2490-140">Canceling an MDI child's <xref:System.Windows.Forms.Form.Closing> event will not prevent the MDI parent's <xref:System.Windows.Forms.Form.Closing> event from being raised; however, the <xref:System.ComponentModel.CancelEventArgs> argument for the MDI parent's <xref:System.Windows.Forms.Form.Closing> event will now be set to `true`.</span></span> <span data-ttu-id="c2490-141">Puede forzar el cierre del formularios MDI primario y de todos los formularios MDI secundarios estableciendo el argumento <xref:System.ComponentModel.CancelEventArgs> en `false`.</span><span class="sxs-lookup"><span data-stu-id="c2490-141">You can force the MDI parent and all MDI child forms to close by setting the <xref:System.ComponentModel.CancelEventArgs> argument to `false`.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2490-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="c2490-142">See also</span></span>

- [<span data-ttu-id="c2490-143">Aplicaciones de interfaz de múltiples documentos (MDI)</span><span class="sxs-lookup"><span data-stu-id="c2490-143">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="c2490-144">Procedimientos: Crear formularios MDI primarios</span><span class="sxs-lookup"><span data-stu-id="c2490-144">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="c2490-145">Cómo: Determinar el elemento secundario MDI activo</span><span class="sxs-lookup"><span data-stu-id="c2490-145">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)
- [<span data-ttu-id="c2490-146">Procedimientos: Enviar datos al elemento secundario MDI activo</span><span class="sxs-lookup"><span data-stu-id="c2490-146">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)
- [<span data-ttu-id="c2490-147">Procedimientos: Organizar formularios MDI secundarios</span><span class="sxs-lookup"><span data-stu-id="c2490-147">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
