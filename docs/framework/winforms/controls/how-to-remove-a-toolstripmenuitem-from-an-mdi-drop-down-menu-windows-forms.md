---
title: "C&#243;mo: Quitar un elemento ToolStripMenuItem de un men&#250; desplegable MDI (formularios Windows Forms) | Microsoft Docs"
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
  - "elementos de menú, quitar de menús desplegables de MDI"
  - "MenuStrip (control) [Windows Forms], combinar"
  - "MenuStrip (control) [Windows Forms], quitar"
ms.assetid: bdafe60d-82ee-45bc-97fe-eeefca6e54c1
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Quitar un elemento ToolStripMenuItem de un men&#250; desplegable MDI (formularios Windows Forms)
En algunas aplicaciones, el tipo de ventana secundaria de la interfaz de múltiples documentos \(MDI\) puede ser diferente al de la ventana primaria de MDI.  Por ejemplo, el elemento primario de MDI podría ser una hoja de cálculo y el elemento secundario de MDI podría ser un gráfico.  En ese caso, desea actualizar el contenido del menú del elemento primario de MDI con el contenido del menú del elemento secundario de MDI ya que están activadas las ventanas secundarias MDI de diferentes tipos.  
  
 El siguiente procedimiento utiliza las propiedades <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction> y <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> para quitar un elemento de menú secundario de la parte desplegable del menú del elemento primario de MDI.  Al cerrar la ventana secundaria MDI, se restauran los elementos de menú quitados del menú de elemento primario de MDI.  
  
### Para quitar un MenuStrip de un menú desplegable de MDI  
  
1.  Cree un formulario y establezca su propiedad <xref:System.Windows.Forms.Form.IsMdiContainer%2A> en `true`.  
  
2.  Agregue un <xref:System.Windows.Forms.MenuStrip> a `Form1` y establezca la propiedad <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> de <xref:System.Windows.Forms.MenuStrip> en `true`.  
  
3.  Agregue un elemento de menú de nivel superior en `Form1`<xref:System.Windows.Forms.MenuStrip> y establezca su propiedad de <xref:System.Windows.Forms.Control.Text%2A> a `&File`.  
  
4.  Agregue tres elementos de submenú al elemento de menú `&File` y establezca sus propiedades <xref:System.Windows.Forms.ToolStripItem.Text%2A> en `&Open`, `&Import from` y `E&xit`.  
  
5.  Agregue dos elementos de submenú al elemento de submenú `&Import from` y establezca sus propiedades <xref:System.Windows.Forms.ToolStripItem.Text%2A> en `&Word` y `&Excel`.  
  
6.  Agregue un formulario al proyecto, agregue <xref:System.Windows.Forms.MenuStrip> al formulario, y establezca la propiedad de <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> de `Form2`<xref:System.Windows.Forms.MenuStrip> a `true`.  
  
7.  Agregue un elemento de menú de nivel superior en `Form2`<xref:System.Windows.Forms.MenuStrip> y establezca su propiedad de <xref:System.Windows.Forms.ToolStripItem.Text%2A> a `&File`.  
  
8.  Agregue un elemento de submenú `&Import from` al menú `&File` de `Form2` y agregue un elemento de submenú `&Word` al menú `&File`.  
  
9. Establezca las propiedades <xref:System.Windows.Forms.MergeAction> y <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> de los elementos de menú de `Form2` tal como se muestra en la tabla siguiente.  
  
    |Elemento de menú de Form2|valor de MergeAction|valor de MergeIndex|  
    |-------------------------------|--------------------------|-------------------------|  
    |Archivo|MatchOnly|\-1|  
    |Import from|MatchOnly|\-1|  
    |Word|Quitar|\-1|  
  
10. En `Form1`, cree un controlador de eventos para el evento <xref:System.Windows.Forms.Control.Click> de `&Open`<xref:System.Windows.Forms.ToolStripMenuItem>.  
  
11. Dentro del controlador de eventos, inserte el código de ejemplo siguiente para crear y mostrar nuevas instancias de `Form2` como MDI secundario de `Form1`.  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
  
    ```  
  
     \[C\#\]  
  
    ```  
    private void openToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
  
    ```  
  
12. Coloque el código de ejemplo siguiente en `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> para registrar el controlador de eventos.  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles openToolStripMenuItem.Click  
  
    ```  
  
    ```csharp  
    this.openToolStripMenuItem.Click += new _  
    System.EventHandler(this.openToolStripMenuItem_Click);  
  
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