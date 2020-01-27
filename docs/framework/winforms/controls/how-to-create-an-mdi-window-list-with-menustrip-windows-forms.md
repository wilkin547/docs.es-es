---
title: 'Cómo: Crear una lista de ventanas MDI con MenuStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MDI [Windows Forms], creating window lists
- MenuStrip control [Windows Forms], creating window lists
ms.assetid: 04fb414b-811f-4a83-aab6-b4a24646dec5
ms.openlocfilehash: f013c3df2ab5783a22fe2c34402dc53a328cafa2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731007"
---
# <a name="how-to-create-an-mdi-window-list-with-menustrip-windows-forms"></a><span data-ttu-id="57631-102">Cómo: Crear una lista de ventanas MDI con MenuStrip (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="57631-102">How to: Create an MDI Window List with MenuStrip (Windows Forms)</span></span>
<span data-ttu-id="57631-103">Use la interfaz de múltiples documentos (MDI) para crear aplicaciones que puedan abrir varios documentos al mismo tiempo y copiar y pegar contenido de un documento al otro.</span><span class="sxs-lookup"><span data-stu-id="57631-103">Use the multiple-document interface (MDI) to create applications that can open several documents at the same time and copy and paste content from one document to the other.</span></span>  
  
 <span data-ttu-id="57631-104">En este procedimiento se muestra cómo crear una lista de todos los formularios secundarios activos en el menú ventana del elemento primario.</span><span class="sxs-lookup"><span data-stu-id="57631-104">This procedure shows you how to create a list of all the active child forms on the parent's Window menu.</span></span>  
  
### <a name="to-create-an-mdi-window-list-on-a-menustrip"></a><span data-ttu-id="57631-105">Para crear una lista de ventanas MDI en un MenuStrip</span><span class="sxs-lookup"><span data-stu-id="57631-105">To create an MDI Window list on a MenuStrip</span></span>  
  
1. <span data-ttu-id="57631-106">Cree un formulario y establezca su propiedad <xref:System.Windows.Forms.Form.IsMdiContainer%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="57631-106">Create a form and set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2. <span data-ttu-id="57631-107">Agregue un control <xref:System.Windows.Forms.MenuStrip> al formulario.</span><span class="sxs-lookup"><span data-stu-id="57631-107">Add a <xref:System.Windows.Forms.MenuStrip> to the form.</span></span>  
  
3. <span data-ttu-id="57631-108">Agregue dos elementos de menú de nivel superior a la <xref:System.Windows.Forms.MenuStrip> y establezca sus propiedades <xref:System.Windows.Forms.Control.Text%2A> en `&File` y `&Window`.</span><span class="sxs-lookup"><span data-stu-id="57631-108">Add two top-level menu items to the <xref:System.Windows.Forms.MenuStrip> and set their <xref:System.Windows.Forms.Control.Text%2A> properties to `&File` and `&Window`.</span></span>  
  
4. <span data-ttu-id="57631-109">Agregue un elemento de submenú al elemento de menú `&File` y establezca su propiedad <xref:System.Windows.Forms.ToolStripItem.Text%2A> en `&Open`.</span><span class="sxs-lookup"><span data-stu-id="57631-109">Add a submenu item to the `&File` menu item and set its <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to `&Open`.</span></span>  
  
5. <span data-ttu-id="57631-110">Establezca la propiedad <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> del <xref:System.Windows.Forms.MenuStrip> en el `&Window`<xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="57631-110">Set the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property of the <xref:System.Windows.Forms.MenuStrip> to the `&Window`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
6. <span data-ttu-id="57631-111">Agregue un formulario al proyecto y agregue el control que desee, como otro <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="57631-111">Add a form to the project and add the control you want to it, such as another <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
7. <span data-ttu-id="57631-112">Cree un controlador para el evento <xref:System.Windows.Forms.Control.Click> del <xref:System.Windows.Forms.ToolStripMenuItem>`&New`.</span><span class="sxs-lookup"><span data-stu-id="57631-112">Create an event handler for the <xref:System.Windows.Forms.Control.Click> event of the `&New`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
8. <span data-ttu-id="57631-113">En el controlador de eventos, inserte código similar al siguiente para crear y mostrar nuevas instancias de `Form2` como elementos secundarios MDI de `Form1`.</span><span class="sxs-lookup"><span data-stu-id="57631-113">Within the event handler, insert code similar to the following to create and display new instances of `Form2` as MDI children of `Form1`.</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As _  
    System.Object, ByVal e As System.EventArgs) Handles _  
    openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    private void newToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
    ```  
  
9. <span data-ttu-id="57631-114">Coloque código similar al siguiente en el <xref:System.Windows.Forms.ToolStripMenuItem> `&New`para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="57631-114">Place code like the following in the `&New`<xref:System.Windows.Forms.ToolStripMenuItem> to register the event handler.</span></span>  
  
    ```vb  
    Private Sub newToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles newToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.newToolStripMenuItem.Click += new System.EventHandler(this.newToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="57631-115">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="57631-115">Compiling the Code</span></span>  
 <span data-ttu-id="57631-116">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="57631-116">This example requires:</span></span>  
  
- <span data-ttu-id="57631-117">Dos controles <xref:System.Windows.Forms.Form> llamados `Form1` y `Form2`.</span><span class="sxs-lookup"><span data-stu-id="57631-117">Two <xref:System.Windows.Forms.Form> controls named `Form1` and `Form2`.</span></span>  
  
- <span data-ttu-id="57631-118">Un control <xref:System.Windows.Forms.MenuStrip> en `Form1` llamado `menuStrip1` y un control <xref:System.Windows.Forms.MenuStrip> en `Form2` llamado `menuStrip2`.</span><span class="sxs-lookup"><span data-stu-id="57631-118">A <xref:System.Windows.Forms.MenuStrip> control on `Form1` named `menuStrip1`, and a <xref:System.Windows.Forms.MenuStrip> control on `Form2` named `menuStrip2`.</span></span>  
  
- <span data-ttu-id="57631-119">Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="57631-119">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57631-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="57631-120">See also</span></span>

- [<span data-ttu-id="57631-121">Crear formularios principales MDI</span><span class="sxs-lookup"><span data-stu-id="57631-121">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="57631-122">Crear formularios MDI secundarios</span><span class="sxs-lookup"><span data-stu-id="57631-122">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="57631-123">Control MenuStrip</span><span class="sxs-lookup"><span data-stu-id="57631-123">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
