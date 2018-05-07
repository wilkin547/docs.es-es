---
title: 'Cómo: Quitar un elemento ToolStripMenuItem de un menú desplegable MDI (formularios Windows Forms)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- menu items [Windows Forms], removing from MDI drop-down menus
- MenuStrip control [Windows Forms], merging
- MenuStrip control [Windows Forms], removing
- MDI [Windows Forms], merging menu items
ms.assetid: bdafe60d-82ee-45bc-97fe-eeefca6e54c1
ms.openlocfilehash: 0649e99c682464928aaae68451b2cb29d5675485
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-remove-a-toolstripmenuitem-from-an-mdi-drop-down-menu-windows-forms"></a>Cómo: Quitar un elemento ToolStripMenuItem de un menú desplegable MDI (formularios Windows Forms)
En algunas aplicaciones, el tipo de ventana secundaria de una interfaz de múltiples documentos (MDI) puede ser diferente de la ventana primaria MDI. Por ejemplo, el elemento primario MDI podría ser una hoja de cálculo y el elemento secundario MDI podría ser un gráfico. En ese caso, querrá actualizar el contenido del menú del elemento primario MDI con el contenido del menú del elemento secundario MDI cuando se activan ventanas secundarias MDI de diferentes tipos.  
  
 El siguiente procedimiento usa el <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>, y <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> propiedades para quitar un elemento de menú de la parte desplegable del menú primario MDI. Cerrar la ventana secundaria MDI restaura los elementos de menú al menú primario MDI.  
  
### <a name="to-remove-a-menustrip-from-an-mdi-drop-down-menu"></a>Para quitar un elemento MenuStrip en un menú de lista desplegable MDI  
  
1.  Cree un formulario y establezca su propiedad <xref:System.Windows.Forms.Form.IsMdiContainer%2A> en `true`.  
  
2.  Agregue una <xref:System.Windows.Forms.MenuStrip> a `Form1` y establezca la propiedad <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> de la <xref:System.Windows.Forms.MenuStrip> en `true`.  
  
3.  Agregue un elemento de menú de nivel superior a la `Form1`<xref:System.Windows.Forms.MenuStrip> y establezca su propiedad <xref:System.Windows.Forms.Control.Text%2A> en `&File`.  
  
4.  Agregue tres elementos de submenú en el `&File` elemento de menú y establezca sus <xref:System.Windows.Forms.ToolStripItem.Text%2A> propiedades para `&Open`, `&Import from`, y `E&xit`.  
  
5.  Agregar dos elementos de submenú a la `&Import from` elemento de submenú y establezca sus <xref:System.Windows.Forms.ToolStripItem.Text%2A> propiedades `&Word` y `&Excel`.  
  
6.  Agregue un formulario al proyecto, agregue una <xref:System.Windows.Forms.MenuStrip> al formulario y establezca la propiedad <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> de la `Form2`<xref:System.Windows.Forms.MenuStrip> en `true`.  
  
7.  Agregue un elemento de menú de nivel superior a la `Form2`<xref:System.Windows.Forms.MenuStrip> y establezca su propiedad <xref:System.Windows.Forms.ToolStripItem.Text%2A> en `&File`.  
  
8.  Agregar un `&Import from` elemento de submenú a la `&File` menú de `Form2`y agregue un `&Word` elemento de submenú al `&File` menú.  
  
9. Establecer el <xref:System.Windows.Forms.MergeAction> y <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> propiedades de la `Form2` elementos de menú, como se muestra en la tabla siguiente.  
  
    |Elemento de menú de Form2|Valor de MergeAction|Valor de MergeIndex|  
    |---------------------|-----------------------|----------------------|  
    |Archivo|MatchOnly|-1|  
    |Importar desde|MatchOnly|-1|  
    |Palabra|Quitar|-1|  
  
10. En `Form1`, cree un controlador de eventos para el <xref:System.Windows.Forms.Control.Click> eventos de la `&Open` <xref:System.Windows.Forms.ToolStripMenuItem>.  
  
11. En el controlador de eventos, inserte código similar al ejemplo de código siguiente para crear y mostrar nuevas instancias de `Form2` como elementos secundarios MDI de `Form1`:  
  
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
  
12. Incluya código similar al ejemplo de código siguiente en el `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> para registrar el controlador de eventos.  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles openToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.openToolStripMenuItem.Click += new _  
    System.EventHandler(this.openToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Dos controles <xref:System.Windows.Forms.Form> llamados `Form1` y `Form2`.  
  
-   Un control <xref:System.Windows.Forms.MenuStrip> en `Form1` llamado `menuStrip1` y un control <xref:System.Windows.Forms.MenuStrip> en `Form2` llamado `menuStrip2`.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también  
 [Crear formularios principales MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [Crear formularios MDI secundarios](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [Información general sobre el control MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
