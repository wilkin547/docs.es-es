---
title: "C&#243;mo: Insertar un elemento MenuStrip en un men&#250; desplegable MDI (formularios Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "MDI, combinar elementos de menú"
  - "MenuStrip (control) [Windows Forms], insertar"
  - "MenuStrip (control) [Windows Forms], combinar"
ms.assetid: 0fad444e-26d9-49af-8860-044d9c10d608
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Insertar un elemento MenuStrip en un men&#250; desplegable MDI (formularios Windows Forms)
En algunas aplicaciones, el tipo de ventana secundaria de la interfaz de múltiples documentos \(MDI\) puede ser diferente al de la ventana primaria de MDI.  Por ejemplo, el elemento primario de MDI podría ser una hoja de cálculo y el elemento secundario de MDI podría ser un gráfico.  En ese caso, desea actualizar el contenido del menú del elemento primario de MDI con el contenido del menú del elemento secundario de MDI ya que están activadas las ventanas secundarias MDI de diferentes tipos.  
  
 El siguiente procedimiento utiliza las propiedades <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction> y <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> para insertar un grupo de elementos de menú desde el menú del elemento secundario de MDI en la parte desplegable del menú del elemento primario de MDI.  Al cerrar la ventana secundaria de MDI, se quita el menú insertado del elemento primario de MDI.  
  
### Para insertar un MenuStrip en un menú desplegable de MDI  
  
1.  Cree un formulario y establezca su propiedad <xref:System.Windows.Forms.Form.IsMdiContainer%2A> en `true`.  
  
2.  Agregue un <xref:System.Windows.Forms.MenuStrip> a `Form1` y establezca la propiedad <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> de <xref:System.Windows.Forms.MenuStrip> en `true`.  
  
3.  Agregue un elemento de menú de nivel superior al `Form1` de <xref:System.Windows.Forms.MenuStrip> y establezca su propiedad <xref:System.Windows.Forms.Control.Text%2A> en `&File`.  
  
4.  Agregue tres elementos de submenú al elemento de menú `&File` y establezca sus propiedades <xref:System.Windows.Forms.ToolStripItem.Text%2A> en `&Open`, `&Import from` y `E&xit`.  
  
5.  Agregue dos elementos de submenú al elemento de submenú `&Import from` y establezca sus propiedades <xref:System.Windows.Forms.ToolStripItem.Text%2A> en `&Word` y `&Excel`.  
  
6.  Agregue un formulario al proyecto, agregue <xref:System.Windows.Forms.MenuStrip> al formulario y establezca la propiedad <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> del `Form2` de <xref:System.Windows.Forms.MenuStrip> en `true`.  
  
7.  Agregue un elemento de menú de nivel superior al `Form2` de <xref:System.Windows.Forms.MenuStrip> y establezca su propiedad <xref:System.Windows.Forms.ToolStripItem.Text%2A> en `&File`.  
  
8.  Agregue los elementos de submenú al menú `&File` de `Form2` en el orden siguiente: <xref:System.Windows.Forms.ToolStripSeparator>, `&Save`, `&Close` `and Save` y otro <xref:System.Windows.Forms.ToolStripSeparator>.  
  
9. Establezca las propiedades <xref:System.Windows.Forms.MergeAction> y <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> de los elementos de menú de `Form2` tal como se muestra en la tabla siguiente.  
  
    |Elemento de menú de Form2|valor de MergeAction|valor de MergeIndex|  
    |-------------------------------|--------------------------|-------------------------|  
    |Archivo|MatchOnly|\-1|  
    |Separator|Insert|2|  
    |Guardar|Insert|3|  
    |Guardar y cerrar|Insert|4|  
    |Separator|Insert|5|  
  
10. Agregue un controlador de eventos para el evento <xref:System.Windows.Forms.Control.Click> del botón `&Open` <xref:System.Windows.Forms.ToolStripMenuItem>.  
  
11. Dentro del controlador de eventos, inserte el código de ejemplo siguiente para crear y mostrar nuevas instancias de `Form2` como formulario MDI secundario de `Form1`.  
  
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
  
12. Copie el código similar al ejemplo de código siguiente en `&Open` <xref:System.Windows.Forms.ToolStripMenuItem> para registrar el controlador de eventos.  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles openToolStripMenuItem.Click  
  
    ```  
  
    ```csharp  
    this.openToolStripMenuItem.Click += new System.EventHandler(this.openToolStripMenuItem_Click);  
  
    ```  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Dos controles <xref:System.Windows.Forms.Form> denominados `Form1` y `Form2`.  
  
-   Un control <xref:System.Windows.Forms.MenuStrip> en `Form1` denominado `menuStrip1` y un control <xref:System.Windows.Forms.MenuStrip> en `Form2` denominado `menuStrip2`.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=fullName> y <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## Vea también  
 [Cómo: Crear formularios principales MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)   
 [Cómo: Crear formularios MDI secundarios](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)   
 [Información general sobre el control MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)