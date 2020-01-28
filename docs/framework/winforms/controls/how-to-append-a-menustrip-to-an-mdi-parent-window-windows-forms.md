---
title: 'Cómo: Anexar un elemento MenuStrip a una ventana primaria MDI'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip control [Windows Forms], merging
- MenuStrip control [Windows Forms], appending
- MDI [Windows Forms], merging menu items
ms.assetid: ab70c936-b452-4653-b417-17be57bb795b
ms.openlocfilehash: 06e5c9daab8b7eb72024fff27d661c0eb3bf84c6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747159"
---
# <a name="how-to-append-a-menustrip-to-an-mdi-parent-window-windows-forms"></a><span data-ttu-id="ec601-102">Cómo: Anexar un elemento MenuStrip a una ventana primaria MDI (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="ec601-102">How to: Append a MenuStrip to an MDI Parent Window (Windows Forms)</span></span>
<span data-ttu-id="ec601-103">En algunas aplicaciones, el tipo de ventana secundaria de una interfaz de múltiples documentos (MDI) puede ser diferente de la ventana primaria MDI.</span><span class="sxs-lookup"><span data-stu-id="ec601-103">In some applications, the kind of a multiple-document interface (MDI) child window can be different from the MDI parent window.</span></span> <span data-ttu-id="ec601-104">Por ejemplo, el elemento primario MDI podría ser una hoja de cálculo y el elemento secundario MDI podría ser un gráfico.</span><span class="sxs-lookup"><span data-stu-id="ec601-104">For example, the MDI parent might be a spreadsheet, and the MDI child might be a chart.</span></span> <span data-ttu-id="ec601-105">En ese caso, querrá actualizar el contenido del menú del elemento primario MDI con el contenido del menú del elemento secundario MDI cuando se activan ventanas secundarias MDI de diferentes tipos.</span><span class="sxs-lookup"><span data-stu-id="ec601-105">In that case, you want to update the contents of the MDI parent's menu with the contents of the MDI child's menu as MDI child windows of different kinds are activated.</span></span>  
  
 <span data-ttu-id="ec601-106">El siguiente procedimiento usa las propiedades <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction> y <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> para anexar el menú secundario MDI al menú primario MDI.</span><span class="sxs-lookup"><span data-stu-id="ec601-106">The following procedure uses the <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>, and <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> properties to append the MDI child menu to the MDI parent menu.</span></span> <span data-ttu-id="ec601-107">Al cerrar la ventana secundaria MDI se quita el menú anexado del elemento primario MDI.</span><span class="sxs-lookup"><span data-stu-id="ec601-107">Closing the MDI child window removes the appended menu from the MDI parent.</span></span>  
  
 <span data-ttu-id="ec601-108">Vea también [aplicaciones de interfaz de múltiples documentos (MDI)](../advanced/multiple-document-interface-mdi-applications.md).</span><span class="sxs-lookup"><span data-stu-id="ec601-108">Also see [Multiple-Document Interface (MDI) Applications](../advanced/multiple-document-interface-mdi-applications.md).</span></span>  
  
### <a name="to-append-a-menu-item-to-an-mdi-parent"></a><span data-ttu-id="ec601-109">Para anexar un elemento de menú a un elemento primario MDI</span><span class="sxs-lookup"><span data-stu-id="ec601-109">To append a menu item to an MDI parent</span></span>  
  
1. <span data-ttu-id="ec601-110">Cree un formulario y establezca su propiedad <xref:System.Windows.Forms.Form.IsMdiContainer%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="ec601-110">Create a form and set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2. <span data-ttu-id="ec601-111">Agregue una <xref:System.Windows.Forms.MenuStrip> a `Form1` y establezca la propiedad <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> de la <xref:System.Windows.Forms.MenuStrip> en `true`.</span><span class="sxs-lookup"><span data-stu-id="ec601-111">Add a <xref:System.Windows.Forms.MenuStrip> to `Form1` and set the <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> property of the <xref:System.Windows.Forms.MenuStrip> to `true`.</span></span>  
  
3. <span data-ttu-id="ec601-112">Establezca la propiedad <xref:System.Windows.Forms.ToolStripItem.Visible%2A> de la `Form1`<xref:System.Windows.Forms.MenuStrip> en `false`.</span><span class="sxs-lookup"><span data-stu-id="ec601-112">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of the `Form1`<xref:System.Windows.Forms.MenuStrip> to `false`.</span></span>  
  
4. <span data-ttu-id="ec601-113">Agregue un elemento de menú de nivel superior a la `Form1`<xref:System.Windows.Forms.MenuStrip> y establezca su propiedad <xref:System.Windows.Forms.Control.Text%2A> en `&File`.</span><span class="sxs-lookup"><span data-stu-id="ec601-113">Add a top-level menu item to the `Form1`<xref:System.Windows.Forms.MenuStrip> and set its <xref:System.Windows.Forms.Control.Text%2A> property to `&File`.</span></span>  
  
5. <span data-ttu-id="ec601-114">Agregue un elemento de submenú al elemento de menú `&File` y establezca su propiedad <xref:System.Windows.Forms.Form.Text%2A> en `&Open`.</span><span class="sxs-lookup"><span data-stu-id="ec601-114">Add a submenu item to the `&File` menu item and set its <xref:System.Windows.Forms.Form.Text%2A> property to `&Open`.</span></span>  
  
6. <span data-ttu-id="ec601-115">Agregue un formulario al proyecto, agregue una <xref:System.Windows.Forms.MenuStrip> al formulario y establezca la propiedad <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> de la `Form2`<xref:System.Windows.Forms.MenuStrip> en `true`.</span><span class="sxs-lookup"><span data-stu-id="ec601-115">Add a form to the project, add a <xref:System.Windows.Forms.MenuStrip> to the form, and set the <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> property of the `Form2`<xref:System.Windows.Forms.MenuStrip> to `true`.</span></span>  
  
7. <span data-ttu-id="ec601-116">Agregue un elemento de menú de nivel superior a la `Form2`<xref:System.Windows.Forms.MenuStrip> y establezca su propiedad <xref:System.Windows.Forms.Form.Text%2A> en `&Special`.</span><span class="sxs-lookup"><span data-stu-id="ec601-116">Add a top-level menu item to the `Form2`<xref:System.Windows.Forms.MenuStrip> and set its <xref:System.Windows.Forms.Form.Text%2A> property to `&Special`.</span></span>  
  
8. <span data-ttu-id="ec601-117">Agregue dos elementos de submenú al elemento de menú `&Special` y establezca sus propiedades <xref:System.Windows.Forms.Form.Text%2A> en `Command&1` y `Command&2`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="ec601-117">Add two submenu items to the `&Special` menu item and set their <xref:System.Windows.Forms.Form.Text%2A> properties to `Command&1` and `Command&2`, respectively.</span></span>  
  
9. <span data-ttu-id="ec601-118">Establezca la propiedad <xref:System.Windows.Forms.MergeAction> de los elementos de menú `&Special`, `Command&1` y `Command&2` en <xref:System.Windows.Forms.MergeAction.Append>.</span><span class="sxs-lookup"><span data-stu-id="ec601-118">Set the <xref:System.Windows.Forms.MergeAction> property of the `&Special`, `Command&1`, and `Command&2` menu items to <xref:System.Windows.Forms.MergeAction.Append>.</span></span>  
  
10. <span data-ttu-id="ec601-119">Cree un controlador de eventos para el evento <xref:System.Windows.Forms.Control.Click> de la <xref:System.Windows.Forms.ToolStripMenuItem>de `&Open`.</span><span class="sxs-lookup"><span data-stu-id="ec601-119">Create an event handler for the <xref:System.Windows.Forms.Control.Click> event of the `&Open` <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
11. <span data-ttu-id="ec601-120">En el controlador de eventos, inserte código similar al ejemplo de código siguiente para crear y mostrar nuevas instancias de `Form2` como elementos secundarios MDI de `Form1`.</span><span class="sxs-lookup"><span data-stu-id="ec601-120">Within the event handler, insert code similar to the following code example to create and display new instances of `Form2` as MDI children of `Form1`.</span></span>  
  
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
  
12. <span data-ttu-id="ec601-121">Incluya código similar al ejemplo de código siguiente en el `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="ec601-121">Place code similar to the following code example in the `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> to register the event handler.</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles openToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.openToolStripMenuItem.Click += new System.EventHandler(this.openToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ec601-122">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="ec601-122">Compiling the Code</span></span>  
 <span data-ttu-id="ec601-123">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="ec601-123">This example requires:</span></span>  
  
- <span data-ttu-id="ec601-124">Dos controles <xref:System.Windows.Forms.Form> llamados `Form1` y `Form2`.</span><span class="sxs-lookup"><span data-stu-id="ec601-124">Two <xref:System.Windows.Forms.Form> controls named `Form1` and `Form2`.</span></span>  
  
- <span data-ttu-id="ec601-125">Un control <xref:System.Windows.Forms.MenuStrip> en `Form1` llamado `menuStrip1` y un control <xref:System.Windows.Forms.MenuStrip> en `Form2` llamado `menuStrip2`.</span><span class="sxs-lookup"><span data-stu-id="ec601-125">A <xref:System.Windows.Forms.MenuStrip> control on `Form1` named `menuStrip1`, and a <xref:System.Windows.Forms.MenuStrip> control on `Form2` named `menuStrip2`.</span></span>  
  
- <span data-ttu-id="ec601-126">Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ec601-126">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>
