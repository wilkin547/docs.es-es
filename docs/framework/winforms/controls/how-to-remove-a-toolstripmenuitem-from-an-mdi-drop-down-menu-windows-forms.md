---
title: "Cómo: Quitar un elemento ToolStripMenuItem de un menú desplegable MDI (formularios Windows Forms)"
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
- menu items [Windows Forms], removing from MDI drop-down menus
- MenuStrip control [Windows Forms], merging
- MenuStrip control [Windows Forms], removing
- MDI [Windows Forms], merging menu items
ms.assetid: bdafe60d-82ee-45bc-97fe-eeefca6e54c1
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4b265544b45ad0614985fdc1d8dbf6f9c0b909ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-remove-a-toolstripmenuitem-from-an-mdi-drop-down-menu-windows-forms"></a><span data-ttu-id="f75b2-102">Cómo: Quitar un elemento ToolStripMenuItem de un menú desplegable MDI (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="f75b2-102">How to: Remove a ToolStripMenuItem from an MDI Drop-Down Menu (Windows Forms)</span></span>
<span data-ttu-id="f75b2-103">En algunas aplicaciones, el tipo de ventana secundaria de una interfaz de múltiples documentos (MDI) puede ser diferente de la ventana primaria MDI.</span><span class="sxs-lookup"><span data-stu-id="f75b2-103">In some applications, the kind of a multiple-document interface (MDI) child window can be different from the MDI parent window.</span></span> <span data-ttu-id="f75b2-104">Por ejemplo, el elemento primario MDI podría ser una hoja de cálculo y el elemento secundario MDI podría ser un gráfico.</span><span class="sxs-lookup"><span data-stu-id="f75b2-104">For example, the MDI parent might be a spreadsheet, and the MDI child might be a chart.</span></span> <span data-ttu-id="f75b2-105">En ese caso, querrá actualizar el contenido del menú del elemento primario MDI con el contenido del menú del elemento secundario MDI cuando se activan ventanas secundarias MDI de diferentes tipos.</span><span class="sxs-lookup"><span data-stu-id="f75b2-105">In that case, you want to update the contents of the MDI parent's menu with the contents of the MDI child's menu as MDI child windows of different kinds are activated.</span></span>  
  
 <span data-ttu-id="f75b2-106">El siguiente procedimiento usa el <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>, y <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> propiedades para quitar un elemento de menú de la parte desplegable del menú primario MDI.</span><span class="sxs-lookup"><span data-stu-id="f75b2-106">The following procedure uses the <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>, and <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> properties to remove a menu item from the drop-down part of the MDI parent menu.</span></span> <span data-ttu-id="f75b2-107">Cerrar la ventana secundaria MDI restaura los elementos de menú al menú primario MDI.</span><span class="sxs-lookup"><span data-stu-id="f75b2-107">Closing the MDI child window restores the removed menu items to the MDI parent menu.</span></span>  
  
### <a name="to-remove-a-menustrip-from-an-mdi-drop-down-menu"></a><span data-ttu-id="f75b2-108">Para quitar un elemento MenuStrip en un menú de lista desplegable MDI</span><span class="sxs-lookup"><span data-stu-id="f75b2-108">To remove a MenuStrip from an MDI drop-down menu</span></span>  
  
1.  <span data-ttu-id="f75b2-109">Cree un formulario y establezca su propiedad <xref:System.Windows.Forms.Form.IsMdiContainer%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="f75b2-109">Create a form and set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2.  <span data-ttu-id="f75b2-110">Agregue una <xref:System.Windows.Forms.MenuStrip> a `Form1` y establezca la propiedad <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> de la <xref:System.Windows.Forms.MenuStrip> en `true`.</span><span class="sxs-lookup"><span data-stu-id="f75b2-110">Add a <xref:System.Windows.Forms.MenuStrip> to `Form1` and set the <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> property of the <xref:System.Windows.Forms.MenuStrip> to `true`.</span></span>  
  
3.  <span data-ttu-id="f75b2-111">Agregue un elemento de menú de nivel superior a la `Form1`<xref:System.Windows.Forms.MenuStrip> y establezca su propiedad <xref:System.Windows.Forms.Control.Text%2A> en `&File`.</span><span class="sxs-lookup"><span data-stu-id="f75b2-111">Add a top-level menu item to the `Form1`<xref:System.Windows.Forms.MenuStrip> and set its <xref:System.Windows.Forms.Control.Text%2A> property to `&File`.</span></span>  
  
4.  <span data-ttu-id="f75b2-112">Agregue tres elementos de submenú en el `&File` elemento de menú y establezca sus <xref:System.Windows.Forms.ToolStripItem.Text%2A> propiedades para `&Open`, `&Import from`, y `E&xit`.</span><span class="sxs-lookup"><span data-stu-id="f75b2-112">Add three submenu items to the `&File` menu item and set their <xref:System.Windows.Forms.ToolStripItem.Text%2A> properties to `&Open`, `&Import from`, and `E&xit`.</span></span>  
  
5.  <span data-ttu-id="f75b2-113">Agregar dos elementos de submenú a la `&Import from` elemento de submenú y establezca sus <xref:System.Windows.Forms.ToolStripItem.Text%2A> propiedades `&Word` y `&Excel`.</span><span class="sxs-lookup"><span data-stu-id="f75b2-113">Add two submenu items to the `&Import from` submenu item and set their <xref:System.Windows.Forms.ToolStripItem.Text%2A> properties to `&Word` and `&Excel`.</span></span>  
  
6.  <span data-ttu-id="f75b2-114">Agregue un formulario al proyecto, agregue una <xref:System.Windows.Forms.MenuStrip> al formulario y establezca la propiedad <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> de la `Form2`<xref:System.Windows.Forms.MenuStrip> en `true`.</span><span class="sxs-lookup"><span data-stu-id="f75b2-114">Add a form to the project, add a <xref:System.Windows.Forms.MenuStrip> to the form, and set the <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> property of the `Form2`<xref:System.Windows.Forms.MenuStrip> to `true`.</span></span>  
  
7.  <span data-ttu-id="f75b2-115">Agregue un elemento de menú de nivel superior a la `Form2`<xref:System.Windows.Forms.MenuStrip> y establezca su propiedad <xref:System.Windows.Forms.ToolStripItem.Text%2A> en `&File`.</span><span class="sxs-lookup"><span data-stu-id="f75b2-115">Add a top-level menu item to the `Form2`<xref:System.Windows.Forms.MenuStrip> and set its <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to `&File`.</span></span>  
  
8.  <span data-ttu-id="f75b2-116">Agregar un `&Import from` elemento de submenú a la `&File` menú de `Form2`y agregue un `&Word` elemento de submenú al `&File` menú.</span><span class="sxs-lookup"><span data-stu-id="f75b2-116">Add an `&Import from` submenu item to the `&File` menu of `Form2`, and add an `&Word` submenu item to the `&File` menu.</span></span>  
  
9. <span data-ttu-id="f75b2-117">Establecer el <xref:System.Windows.Forms.MergeAction> y <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> propiedades de la `Form2` elementos de menú, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="f75b2-117">Set the <xref:System.Windows.Forms.MergeAction> and <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> properties of the `Form2` menu items as shown in the following table.</span></span>  
  
    |<span data-ttu-id="f75b2-118">Elemento de menú de Form2</span><span class="sxs-lookup"><span data-stu-id="f75b2-118">Form2 menu item</span></span>|<span data-ttu-id="f75b2-119">Valor de MergeAction</span><span class="sxs-lookup"><span data-stu-id="f75b2-119">MergeAction value</span></span>|<span data-ttu-id="f75b2-120">Valor de MergeIndex</span><span class="sxs-lookup"><span data-stu-id="f75b2-120">MergeIndex value</span></span>|  
    |---------------------|-----------------------|----------------------|  
    |<span data-ttu-id="f75b2-121">Archivo</span><span class="sxs-lookup"><span data-stu-id="f75b2-121">File</span></span>|<span data-ttu-id="f75b2-122">MatchOnly</span><span class="sxs-lookup"><span data-stu-id="f75b2-122">MatchOnly</span></span>|<span data-ttu-id="f75b2-123">-1</span><span class="sxs-lookup"><span data-stu-id="f75b2-123">-1</span></span>|  
    |<span data-ttu-id="f75b2-124">Importar desde</span><span class="sxs-lookup"><span data-stu-id="f75b2-124">Import from</span></span>|<span data-ttu-id="f75b2-125">MatchOnly</span><span class="sxs-lookup"><span data-stu-id="f75b2-125">MatchOnly</span></span>|<span data-ttu-id="f75b2-126">-1</span><span class="sxs-lookup"><span data-stu-id="f75b2-126">-1</span></span>|  
    |<span data-ttu-id="f75b2-127">Palabra</span><span class="sxs-lookup"><span data-stu-id="f75b2-127">Word</span></span>|<span data-ttu-id="f75b2-128">Quitar</span><span class="sxs-lookup"><span data-stu-id="f75b2-128">Remove</span></span>|<span data-ttu-id="f75b2-129">-1</span><span class="sxs-lookup"><span data-stu-id="f75b2-129">-1</span></span>|  
  
10. <span data-ttu-id="f75b2-130">En `Form1`, cree un controlador de eventos para el <xref:System.Windows.Forms.Control.Click> eventos de la `&Open` <xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="f75b2-130">In `Form1`, create an event handler for the <xref:System.Windows.Forms.Control.Click> event of the `&Open`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
11. <span data-ttu-id="f75b2-131">En el controlador de eventos, inserte código similar al ejemplo de código siguiente para crear y mostrar nuevas instancias de `Form2` como elementos secundarios MDI de `Form1`:</span><span class="sxs-lookup"><span data-stu-id="f75b2-131">Within the event handler, insert code similar to the following code example to create and display new instances of `Form2` as MDI children of `Form1`:</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles openToolStripMenuItem.Click  
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
  
12. <span data-ttu-id="f75b2-132">Incluya código similar al ejemplo de código siguiente en el `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="f75b2-132">Place code similar to the following code example in the `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> to register the event handler.</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles openToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.openToolStripMenuItem.Click += new _  
    System.EventHandler(this.openToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f75b2-133">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="f75b2-133">Compiling the Code</span></span>  
 <span data-ttu-id="f75b2-134">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="f75b2-134">This example requires:</span></span>  
  
-   <span data-ttu-id="f75b2-135">Dos controles <xref:System.Windows.Forms.Form> llamados `Form1` y `Form2`.</span><span class="sxs-lookup"><span data-stu-id="f75b2-135">Two <xref:System.Windows.Forms.Form> controls named `Form1` and `Form2`.</span></span>  
  
-   <span data-ttu-id="f75b2-136">Un control <xref:System.Windows.Forms.MenuStrip> en `Form1` llamado `menuStrip1` y un control <xref:System.Windows.Forms.MenuStrip> en `Form2` llamado `menuStrip2`.</span><span class="sxs-lookup"><span data-stu-id="f75b2-136">A <xref:System.Windows.Forms.MenuStrip> control on `Form1` named `menuStrip1`, and a <xref:System.Windows.Forms.MenuStrip> control on `Form2` named `menuStrip2`.</span></span>  
  
-   <span data-ttu-id="f75b2-137">Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f75b2-137">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f75b2-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="f75b2-138">See Also</span></span>  
 [<span data-ttu-id="f75b2-139">Crear formularios principales MDI</span><span class="sxs-lookup"><span data-stu-id="f75b2-139">How to: Create MDI Parent Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [<span data-ttu-id="f75b2-140">Crear formularios MDI secundarios</span><span class="sxs-lookup"><span data-stu-id="f75b2-140">How to: Create MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [<span data-ttu-id="f75b2-141">Información general sobre el control MenuStrip</span><span class="sxs-lookup"><span data-stu-id="f75b2-141">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
