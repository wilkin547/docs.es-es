---
title: "C&#243;mo: Crear una lista de ventanas MDI con MenuStrip (formularios Windows Forms) | Microsoft Docs"
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
  - "MDI, crear listas de ventanas"
  - "MenuStrip (control) [Windows Forms], crear listas de ventanas"
ms.assetid: 04fb414b-811f-4a83-aab6-b4a24646dec5
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# C&#243;mo: Crear una lista de ventanas MDI con MenuStrip (formularios Windows Forms)
Utilice la interfaz de múltiples documentos \(MDI\) para crear aplicaciones que abran varios documentos al mismo tiempo, y copie y pegue el contenido de un documento a otro.  
  
 Este procedimiento muestra cómo crear una lista de todos los formularios secundarios activos en el menú Ventana del elemento primario.  
  
### Para crear una lista Ventana de MDI en un MenuStrip  
  
1.  Cree un formulario y establezca su propiedad <xref:System.Windows.Forms.Form.IsMdiContainer%2A> en `true`.  
  
2.  Agregue un <xref:System.Windows.Forms.MenuStrip> al formulario.  
  
3.  Agregue dos elementos de menú de nivel superior a <xref:System.Windows.Forms.MenuStrip> y establezca sus propiedades <xref:System.Windows.Forms.Control.Text%2A> en `&File` y `&Window`.  
  
4.  Agregue un elemento de submenú al elemento de menú `&File` y establezca su propiedad <xref:System.Windows.Forms.ToolStripItem.Text%2A> en `&Open`.  
  
5.  establezca la propiedad de <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> de <xref:System.Windows.Forms.MenuStrip> a `&Window`<xref:System.Windows.Forms.ToolStripMenuItem>.  
  
6.  Agregue un formulario al proyecto y agréguele el control que desee, como otro <xref:System.Windows.Forms.MenuStrip>.  
  
7.  Cree un controlador de eventos para el evento <xref:System.Windows.Forms.Control.Click> de `&New`<xref:System.Windows.Forms.ToolStripMenuItem>.  
  
8.  Dentro del controlador de eventos, inserte el código de ejemplo siguiente para crear y mostrar nuevas instancias de `Form2` como formulario MDI secundario de `Form1`.  
  
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
  
     \[C\#\]  
  
    ```  
    private void newToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
  
    ```  
  
9. Coloque el código siguiente en `&New`<xref:System.Windows.Forms.ToolStripMenuItem> para registrar el controlador de eventos.  
  
    ```vb  
    Private Sub newToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles newToolStripMenuItem.Click  
  
    ```  
  
    ```csharp  
    this.newToolStripMenuItem.Click += new System.EventHandler(this.newToolStripMenuItem_Click);  
  
    ```  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Dos controles <xref:System.Windows.Forms.Form> denominados `Form1` y `Form2`.  
  
-   Un control <xref:System.Windows.Forms.MenuStrip> en `Form1` denominado `menuStrip1` y un control <xref:System.Windows.Forms.MenuStrip> en `Form2` denominado `menuStrip2`.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=fullName> y <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## Vea también  
 [Cómo: Crear formularios principales MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)   
 [Cómo: Crear formularios MDI secundarios](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)   
 [MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)