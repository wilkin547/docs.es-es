---
title: Filtrar Anexar un elemento MenuStrip a una ventana primaria MDI (formularios Windows Forms)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip control [Windows Forms], merging
- MenuStrip control [Windows Forms], appending
- MDI [Windows Forms], merging menu items
ms.assetid: ab70c936-b452-4653-b417-17be57bb795b
ms.openlocfilehash: a335531b090983de4e2b3daccc9f956930cbad6e
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59298947"
---
# <a name="how-to-append-a-menustrip-to-an-mdi-parent-window-windows-forms"></a>Filtrar Anexar un elemento MenuStrip a una ventana primaria MDI (formularios Windows Forms)
En algunas aplicaciones, el tipo de ventana secundaria de una interfaz de múltiples documentos (MDI) puede ser diferente de la ventana primaria MDI. Por ejemplo, el elemento primario MDI podría ser una hoja de cálculo y el elemento secundario MDI podría ser un gráfico. En ese caso, querrá actualizar el contenido del menú del elemento primario MDI con el contenido del menú del elemento secundario MDI cuando se activan ventanas secundarias MDI de diferentes tipos.  
  
 El siguiente procedimiento usa las propiedades <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction> y <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> para anexar el menú secundario MDI al menú primario MDI. Al cerrar la ventana secundaria MDI se quita el menú anexado del elemento primario MDI.  
  
 Consulte también [aplicaciones de interfaz de múltiples documentos (MDI)](../advanced/multiple-document-interface-mdi-applications.md).  
  
### <a name="to-append-a-menu-item-to-an-mdi-parent"></a>Para anexar un elemento de menú a un elemento primario MDI  
  
1. Cree un formulario y establezca su propiedad <xref:System.Windows.Forms.Form.IsMdiContainer%2A> en `true`.  
  
2. Agregue una <xref:System.Windows.Forms.MenuStrip> a `Form1` y establezca la propiedad <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> de la <xref:System.Windows.Forms.MenuStrip> en `true`.  
  
3. Establecer el <xref:System.Windows.Forms.ToolStripItem.Visible%2A> propiedad de la `Form1`<xref:System.Windows.Forms.MenuStrip> a `false`.  
  
4. Agregue un elemento de menú de nivel superior a la `Form1`<xref:System.Windows.Forms.MenuStrip> y establezca su <xref:System.Windows.Forms.Control.Text%2A> propiedad `&File`.  
  
5. Agregue un elemento de submenú al elemento de menú `&File` y establezca su propiedad <xref:System.Windows.Forms.Form.Text%2A> en `&Open`.  
  
6. Agregue un formulario al proyecto, agregue un <xref:System.Windows.Forms.MenuStrip> al formulario y establezca el <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> propiedad de la `Form2`<xref:System.Windows.Forms.MenuStrip> a `true`.  
  
7. Agregue un elemento de menú de nivel superior a la `Form2`<xref:System.Windows.Forms.MenuStrip> y establezca su <xref:System.Windows.Forms.Form.Text%2A> propiedad `&Special`.  
  
8. Agregue dos elementos de submenú al elemento de menú `&Special` y establezca sus propiedades <xref:System.Windows.Forms.Form.Text%2A> en `Command&1` y `Command&2`, respectivamente.  
  
9. Establezca la propiedad <xref:System.Windows.Forms.MergeAction> de los elementos de menú `&Special`, `Command&1` y `Command&2` en <xref:System.Windows.Forms.MergeAction.Append>.  
  
10. Crear un controlador de eventos para el <xref:System.Windows.Forms.Control.Click> eventos de la `&New`<xref:System.Windows.Forms.ToolStripMenuItem>.  
  
11. En el controlador de eventos, inserte código similar al ejemplo de código siguiente para crear y mostrar nuevas instancias de `Form2` como elementos secundarios MDI de `Form1`.  
  
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
  
12. Incluya código similar al siguiente ejemplo de código en el `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> para registrar el controlador de eventos.  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles openToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.openToolStripMenuItem.Click += new System.EventHandler(this.openToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Dos controles <xref:System.Windows.Forms.Form> llamados `Form1` y `Form2`.  
  
-   Un control <xref:System.Windows.Forms.MenuStrip> en `Form1` llamado `menuStrip1` y un control <xref:System.Windows.Forms.MenuStrip> en `Form2` llamado `menuStrip2`.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.
