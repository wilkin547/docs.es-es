---
title: 'Cómo: Insertar un elemento MenuStrip en un menú desplegable MDI (formularios Windows Forms)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip control [Windows Forms], inserting
- MenuStrip control [Windows Forms], merging
- MDI [Windows Forms], merging menu items
ms.assetid: 0fad444e-26d9-49af-8860-044d9c10d608
ms.openlocfilehash: 64e7e7875a635bcd4fbafb62d3ee7b7018214ee4
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44067479"
---
# <a name="how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms"></a><span data-ttu-id="2fe05-102">Cómo: Insertar un elemento MenuStrip en un menú desplegable MDI (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="2fe05-102">How to: Insert a MenuStrip into an MDI Drop-Down Menu (Windows Forms)</span></span>
<span data-ttu-id="2fe05-103">En algunas aplicaciones, el tipo de ventana secundaria de una interfaz de múltiples documentos (MDI) puede ser diferente de la ventana primaria MDI.</span><span class="sxs-lookup"><span data-stu-id="2fe05-103">In some applications, the kind of a multiple-document interface (MDI) child window can be different from the MDI parent window.</span></span> <span data-ttu-id="2fe05-104">Por ejemplo, el elemento primario MDI podría ser una hoja de cálculo y el elemento secundario MDI podría ser un gráfico.</span><span class="sxs-lookup"><span data-stu-id="2fe05-104">For example, the MDI parent might be a spreadsheet, and the MDI child might be a chart.</span></span> <span data-ttu-id="2fe05-105">En ese caso, querrá actualizar el contenido del menú del elemento primario MDI con el contenido del menú del elemento secundario MDI cuando se activan ventanas secundarias MDI de diferentes tipos.</span><span class="sxs-lookup"><span data-stu-id="2fe05-105">In that case, you want to update the contents of the MDI parent's menu with the contents of the MDI child's menu as MDI child windows of different kinds are activated.</span></span>  
  
 <span data-ttu-id="2fe05-106">El siguiente procedimiento usa la <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>, y <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> propiedades para insertar un grupo de elementos de menú desde el menú secundario MDI en la parte desplegable del menú primario MDI.</span><span class="sxs-lookup"><span data-stu-id="2fe05-106">The following procedure uses the <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>, and <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> properties to insert a group of menu items from the MDI child menu into the drop-down part of the MDI parent menu.</span></span> <span data-ttu-id="2fe05-107">Cierre la ventana secundaria MDI quita los elementos de menú insertado del elemento primario MDI.</span><span class="sxs-lookup"><span data-stu-id="2fe05-107">Closing the MDI child window removes the inserted menu items from the MDI parent.</span></span>  
  
### <a name="to-insert-a-menustrip-into-an-mdi-drop-down-menu"></a><span data-ttu-id="2fe05-108">Para insertar un elemento MenuStrip en un menú desplegable MDI</span><span class="sxs-lookup"><span data-stu-id="2fe05-108">To insert a MenuStrip into an MDI drop-down menu</span></span>  
  
1.  <span data-ttu-id="2fe05-109">Cree un formulario y establezca su propiedad <xref:System.Windows.Forms.Form.IsMdiContainer%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="2fe05-109">Create a form and set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2.  <span data-ttu-id="2fe05-110">Agregue una <xref:System.Windows.Forms.MenuStrip> a `Form1` y establezca la propiedad <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> de la <xref:System.Windows.Forms.MenuStrip> en `true`.</span><span class="sxs-lookup"><span data-stu-id="2fe05-110">Add a <xref:System.Windows.Forms.MenuStrip> to `Form1` and set the <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> property of the <xref:System.Windows.Forms.MenuStrip> to `true`.</span></span>  
  
3.  <span data-ttu-id="2fe05-111">Agregue un elemento de menú de nivel superior a la `Form1`<xref:System.Windows.Forms.MenuStrip> y establezca su propiedad <xref:System.Windows.Forms.Control.Text%2A> en `&File`.</span><span class="sxs-lookup"><span data-stu-id="2fe05-111">Add a top-level menu item to the `Form1`<xref:System.Windows.Forms.MenuStrip> and set its <xref:System.Windows.Forms.Control.Text%2A> property to `&File`.</span></span>  
  
4.  <span data-ttu-id="2fe05-112">Agregue tres elementos de submenú a la `&File` elemento de menú y establezca sus <xref:System.Windows.Forms.ToolStripItem.Text%2A> propiedades a `&Open`, `&Import from`, y `E&xit`.</span><span class="sxs-lookup"><span data-stu-id="2fe05-112">Add three submenu items to the `&File` menu item and set their <xref:System.Windows.Forms.ToolStripItem.Text%2A> properties to `&Open`, `&Import from`, and `E&xit`.</span></span>  
  
5.  <span data-ttu-id="2fe05-113">Agregar dos elementos de submenú a la `&Import from` elemento de submenú y establezca sus <xref:System.Windows.Forms.ToolStripItem.Text%2A> propiedades a `&Word` y `&Excel`.</span><span class="sxs-lookup"><span data-stu-id="2fe05-113">Add two submenu items to the `&Import from` submenu item and set their <xref:System.Windows.Forms.ToolStripItem.Text%2A> properties to `&Word` and `&Excel`.</span></span>  
  
6.  <span data-ttu-id="2fe05-114">Agregue un formulario al proyecto, agregue una <xref:System.Windows.Forms.MenuStrip> al formulario y establezca la propiedad <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> de la `Form2`<xref:System.Windows.Forms.MenuStrip> en `true`.</span><span class="sxs-lookup"><span data-stu-id="2fe05-114">Add a form to the project, add a <xref:System.Windows.Forms.MenuStrip> to the form, and set the <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> property of the `Form2`<xref:System.Windows.Forms.MenuStrip> to `true`.</span></span>  
  
7.  <span data-ttu-id="2fe05-115">Agregue un elemento de menú de nivel superior a la `Form2`<xref:System.Windows.Forms.MenuStrip> y establezca su propiedad <xref:System.Windows.Forms.ToolStripItem.Text%2A> en `&File`.</span><span class="sxs-lookup"><span data-stu-id="2fe05-115">Add a top-level menu item to the `Form2`<xref:System.Windows.Forms.MenuStrip> and set its <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to `&File`.</span></span>  
  
8.  <span data-ttu-id="2fe05-116">Agregar elementos de submenú para los `&File` menú de `Form2` en el orden siguiente: un <xref:System.Windows.Forms.ToolStripSeparator>, `&Save`, `Save and &Close`y otro <xref:System.Windows.Forms.ToolStripSeparator>.</span><span class="sxs-lookup"><span data-stu-id="2fe05-116">Add submenu items to the `&File` menu of `Form2` in the following order: a <xref:System.Windows.Forms.ToolStripSeparator>, `&Save`, `Save and &Close`, and another <xref:System.Windows.Forms.ToolStripSeparator>.</span></span>  
  
9. <span data-ttu-id="2fe05-117">Establecer el <xref:System.Windows.Forms.MergeAction> y <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> propiedades de la `Form2` los elementos de menú, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="2fe05-117">Set the <xref:System.Windows.Forms.MergeAction> and <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> properties of the `Form2` menu items as shown in the following table.</span></span>  
  
    |<span data-ttu-id="2fe05-118">Elemento de menú de Form2</span><span class="sxs-lookup"><span data-stu-id="2fe05-118">Form2 menu item</span></span>|<span data-ttu-id="2fe05-119">Valor de MergeAction</span><span class="sxs-lookup"><span data-stu-id="2fe05-119">MergeAction value</span></span>|<span data-ttu-id="2fe05-120">Valor de MergeIndex</span><span class="sxs-lookup"><span data-stu-id="2fe05-120">MergeIndex value</span></span>|  
    |---------------------|-----------------------|----------------------|  
    |<span data-ttu-id="2fe05-121">Archivo</span><span class="sxs-lookup"><span data-stu-id="2fe05-121">File</span></span>|<span data-ttu-id="2fe05-122">MatchOnly</span><span class="sxs-lookup"><span data-stu-id="2fe05-122">MatchOnly</span></span>|<span data-ttu-id="2fe05-123">-1</span><span class="sxs-lookup"><span data-stu-id="2fe05-123">-1</span></span>|  
    |<span data-ttu-id="2fe05-124">Separador</span><span class="sxs-lookup"><span data-stu-id="2fe05-124">Separator</span></span>|<span data-ttu-id="2fe05-125">Insertar</span><span class="sxs-lookup"><span data-stu-id="2fe05-125">Insert</span></span>|<span data-ttu-id="2fe05-126">2</span><span class="sxs-lookup"><span data-stu-id="2fe05-126">2</span></span>|  
    |<span data-ttu-id="2fe05-127">Guardar</span><span class="sxs-lookup"><span data-stu-id="2fe05-127">Save</span></span>|<span data-ttu-id="2fe05-128">Insertar</span><span class="sxs-lookup"><span data-stu-id="2fe05-128">Insert</span></span>|<span data-ttu-id="2fe05-129">3</span><span class="sxs-lookup"><span data-stu-id="2fe05-129">3</span></span>|  
    |<span data-ttu-id="2fe05-130">Guardar y cerrar</span><span class="sxs-lookup"><span data-stu-id="2fe05-130">Save and Close</span></span>|<span data-ttu-id="2fe05-131">Insertar</span><span class="sxs-lookup"><span data-stu-id="2fe05-131">Insert</span></span>|<span data-ttu-id="2fe05-132">4</span><span class="sxs-lookup"><span data-stu-id="2fe05-132">4</span></span>|  
    |<span data-ttu-id="2fe05-133">Separador</span><span class="sxs-lookup"><span data-stu-id="2fe05-133">Separator</span></span>|<span data-ttu-id="2fe05-134">Insertar</span><span class="sxs-lookup"><span data-stu-id="2fe05-134">Insert</span></span>|<span data-ttu-id="2fe05-135">5</span><span class="sxs-lookup"><span data-stu-id="2fe05-135">5</span></span>|  
  
10. <span data-ttu-id="2fe05-136">Cree un controlador para el evento <xref:System.Windows.Forms.Control.Click> del <xref:System.Windows.Forms.ToolStripMenuItem>`&Open`.</span><span class="sxs-lookup"><span data-stu-id="2fe05-136">Create an event handler for the <xref:System.Windows.Forms.Control.Click> event of the `&Open`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
11. <span data-ttu-id="2fe05-137">En el controlador de eventos, inserte código similar al ejemplo de código siguiente para crear y mostrar nuevas instancias de `Form2` como elementos secundarios MDI de `Form1`.</span><span class="sxs-lookup"><span data-stu-id="2fe05-137">Within the event handler, insert code similar to the following code example to create and display new instances of `Form2` as MDI children of `Form1`.</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    private void openToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
    ```  
  
12. <span data-ttu-id="2fe05-138">Incluya código similar al ejemplo de código siguiente en el `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="2fe05-138">Place code similar to the following code example in the `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> to register the event handler.</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles openToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.openToolStripMenuItem.Click += new System.EventHandler(this.openToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2fe05-139">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="2fe05-139">Compiling the Code</span></span>  
 <span data-ttu-id="2fe05-140">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="2fe05-140">This example requires:</span></span>  
  
-   <span data-ttu-id="2fe05-141">Dos controles <xref:System.Windows.Forms.Form> llamados `Form1` y `Form2`.</span><span class="sxs-lookup"><span data-stu-id="2fe05-141">Two <xref:System.Windows.Forms.Form> controls named `Form1` and `Form2`.</span></span>  
  
-   <span data-ttu-id="2fe05-142">Un control <xref:System.Windows.Forms.MenuStrip> en `Form1` llamado `menuStrip1` y un control <xref:System.Windows.Forms.MenuStrip> en `Form2` llamado `menuStrip2`.</span><span class="sxs-lookup"><span data-stu-id="2fe05-142">A <xref:System.Windows.Forms.MenuStrip> control on `Form1` named `menuStrip1`, and a <xref:System.Windows.Forms.MenuStrip> control on `Form2` named `menuStrip2`.</span></span>  
  
-   <span data-ttu-id="2fe05-143">Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2fe05-143">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fe05-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="2fe05-144">See Also</span></span>  
 [<span data-ttu-id="2fe05-145">Crear formularios principales MDI</span><span class="sxs-lookup"><span data-stu-id="2fe05-145">How to: Create MDI Parent Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [<span data-ttu-id="2fe05-146">Crear formularios MDI secundarios</span><span class="sxs-lookup"><span data-stu-id="2fe05-146">How to: Create MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [<span data-ttu-id="2fe05-147">Información general sobre el control MenuStrip</span><span class="sxs-lookup"><span data-stu-id="2fe05-147">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
