---
title: "C&#243;mo: Crear una interfaz de usuario de varios paneles con formularios Windows Forms | Microsoft Docs"
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
  - "ListView (control) [Windows Forms], ejemplos"
  - "Panel (control) [Windows Forms], ejemplos"
  - "RichTextBox (control) [Windows Forms], ejemplos"
  - "SplitContainer (control) [Windows Forms], ejemplos"
  - "Splitter (control) [Windows Forms], ejemplos"
  - "TreeView (control) [Windows Forms], ejemplos"
ms.assetid: e79f6bcc-3740-4d1e-b46a-c5594d9b7327
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# C&#243;mo: Crear una interfaz de usuario de varios paneles con formularios Windows Forms
El procedimiento siguiente permite crear una interfaz de usuario de varios paneles parecida a la utilizada en Microsoft Outlook, con una lista de **Carpetas**, un panel de **Mensajes** y un panel de **Vista previa**.  Esta organización se logra principalmente mediante el acoplamiento de los controles con el formulario.  
  
 Al acoplar un control se determina a cuál de los bordes del contenedor principal deberá fijarse.  Por consiguiente, si establece la propiedad <xref:System.Windows.Forms.SplitContainer.Dock%2A> en <xref:System.Windows.Forms.DockStyle>, el borde derecho del control se acoplará al borde derecho de su control primario.  Además, el tamaño del borde acoplado del control se ajusta al tamaño del control contenedor.  Para obtener más información sobre cómo funciona la propiedad <xref:System.Windows.Forms.SplitContainer.Dock%2A>, vea [Cómo: Acoplar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md).  
  
 Este procedimiento se centra en organizar el contenedor <xref:System.Windows.Forms.SplitContainer> y los demás controles del formulario, no se trata de agregar funcionalidades para obtener una aplicación que imite a Microsoft Outlook.  
  
 Para crear esta interfaz de usuario, se colocan todos los controles dentro de un control <xref:System.Windows.Forms.SplitContainer> que, a su vez, contiene un control <xref:System.Windows.Forms.TreeView> en el panel izquierdo.  El panel derecho del control <xref:System.Windows.Forms.SplitContainer> contiene un segundo control <xref:System.Windows.Forms.SplitContainer>, que a su vez tiene un control <xref:System.Windows.Forms.ListView> por encima de un control <xref:System.Windows.Forms.RichTextBox>.  Estos controles <xref:System.Windows.Forms.SplitContainer> permiten realizar el ajuste del tamaño de los demás controles del formulario de manera independiente.  Puede adaptar las técnicas de este procedimiento para crear interfaces de usuario personalizadas propias.  
  
### Para crear una interfaz de usuario de estilo Outlook mediante programación  
  
1.  En un formulario, declare cada uno de los controles que constituyen la interfaz de usuario.  Para este ejemplo, utilice los controles <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.SplitContainer> y <xref:System.Windows.Forms.RichTextBox> para imitar la interfaz de usuario de Microsoft Outlook.  
  
    ```vb  
    Private WithEvents treeView1 As System.Windows.Forms.TreeView  
    Private WithEvents listView1 As System.Windows.Forms.ListView  
    Private WithEvents richTextBox1 As System.Windows.Forms.RichTextBox  
    Private WithEvents splitContainer1 As _  
        System.Windows.Forms.SplitContainer  
    Private WithEvents splitContainer2 As _  
        System.Windows.Forms.SplitContainer  
  
    ```  
  
    ```csharp  
    private System.Windows.Forms.TreeView treeView1;  
    private System.Windows.Forms.ListView listView1;  
    private System.Windows.Forms.RichTextBox richTextBox1;  
    private System.Windows.Forms. SplitContainer splitContainer2;  
    private System.Windows.Forms. SplitContainer splitContainer1;  
  
    ```  
  
2.  Cree un procedimiento que defina la interfaz de usuario.  El código siguiente establece las propiedades de modo que el formulario se asemeje a la interfaz de usuario de Microsoft Outlook.  Sin embargo, si utiliza otros controles o los acopla de forma diferente, es igual de fácil crear otras interfaces de usuario que tengan la misma flexibilidad.  
  
    ```vb  
    Public Sub CreateOutlookUI()  
        ' Create an instance of each control being used.  
        Me.components = New System.ComponentModel.Container()  
        Me.treeView1 = New System.Windows.Forms.TreeView()  
        Me.listView1 = New System.Windows.Forms.ListView()  
        Me.richTextBox1 = New System.Windows.Forms.RichTextBox()  
        Me.splitContainer1 = New System.Windows.Forms.SplitContainer()  
        Me.splitContainer2= New System.Windows.Forms. SplitContainer()  
  
        ' Should you develop this into a working application,  
        ' use the AddHandler method to hook up event procedures here.  
  
        ' Set properties of TreeView control.  
        ' Use the With statement to avoid repetitive code.  
        With Me.treeView1  
            .Dock = System.Windows.Forms.DockStyle.Fill  
            .TabIndex = 0  
            .Nodes.Add("treeView")  
        End With  
  
    ' Set properties of ListView control.  
       With Me.listView1  
          .Dock = System.Windows.Forms.DockStyle.Top  
          .TabIndex = 2  
          .Items.Add("listView")  
       End With  
  
    ' Set properties of RichTextBox control.  
       With Me.richTextBox1  
          .Dock = System.Windows.Forms.DockStyle.Fill  
          .TabIndex = 3  
          .Text = "richTextBox1"  
       End With  
  
        ' Set properties of the first SplitContainer control.  
        With Me.splitContainer1  
            .Dock = System.Windows.Forms.DockStyle.Fill  
            .TabIndex = 1  
            .SplitterWidth = 4  
            .SplitterDistance = 150  
            .Orientation = Orientation.Horizontal  
            .Panel1.Controls.Add(Me.listView1)  
            .Panel2.Controls.Add(Me.richTextBox1)  
    End With  
  
        ' Set properties of the second SplitContainer control.  
        With Me.splitContainer2  
            .Dock = System.Windows.Forms.DockStyle.Fill  
            .TabIndex = 4  
            .SplitterWidth = 4  
            .SplitterDistance = 100  
            .Panel1.Controls.Add(Me.treeView1)  
            .Panel2.Controls.Add(Me.SplitContainer1)  
    End With  
  
    ' Add the main SplitContainer control to the form.  
        Me.Controls.Add(Me.splitContainer2)  
        Me.Text = "Intricate UI Example"  
    End Sub  
  
    ```  
  
    ```csharp  
    public void createOutlookUI()  
    {  
        // Create an instance of each control being used.  
        treeView1 = new System.Windows.Forms.TreeView();  
        listView1 = new System.Windows.Forms.ListView();  
        richTextBox1 = new System.Windows.Forms.RichTextBox();  
        splitContainer2 = new System.Windows.Forms.SplitContainer();  
        splitContainer1 = new System.Windows.Forms.SplitContainer();  
  
        // Insert code here to hook up event methods.  
  
        // Set properties of TreeView control.  
        treeView1.Dock = System.Windows.Forms.DockStyle.Fill;  
        treeView1.TabIndex = 0;  
        treeView1.Nodes.Add("treeView");  
  
        // Set properties of ListView control.  
        listView1.Dock = System.Windows.Forms.DockStyle.Top;  
        listView1.TabIndex = 2;  
        listView1.Items.Add("listView");  
  
        // Set properties of RichTextBox control.  
        richTextBox1.Dock = System.Windows.Forms.DockStyle.Fill;  
        richTextBox1.TabIndex = 3;  
        richTextBox1.Text = "richTextBox1";  
  
        // Set properties of first SplitContainer control.  
        splitContainer1.Dock = System.Windows.Forms.DockStyle.Fill;  
        splitContainer2.TabIndex = 1;  
        splitContainer2.SplitterWidth = 4;  
        splitContainer2.SplitterDistance = 150;  
        splitContainer2.Orientation = Orientation.Horizontal;  
        splitContainer2.Panel1.Controls.Add(this.listView1);  
        splitContainer2.Panel1.Controls.Add(this.richTextBox1);  
  
        // Set properties of second SplitContainer control.  
        splitContainer2.Dock = System.Windows.Forms.DockStyle.Fill;  
        splitContainer2.TabIndex = 4;  
        splitContainer2.SplitterWidth = 4;  
        splitContainer2.SplitterDistance = 100;  
        splitContainer2.Panel1.Controls.Add(this.treeView1);  
        splitContainer2.Panel1.Controls.Add(this.splitContainer1);  
  
        // Add the main SplitContainer control to the form.  
        this.Controls.Add(this.splitContainer2);  
        this.Text = "Intricate UI Example";  
    }  
  
    ```  
  
3.  En [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], agregue una llamada al procedimiento que acaba de crear en el procedimiento `New()`.  En [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], agregue esta línea de código al constructor de la clase de formulario.  
  
    ```vb  
    ' Add this to the New procedure.  
    CreateOutlookUI()  
  
    ```  
  
    ```csharp  
    // Add this to the form class's constructor.  
    createOutlookUI();  
  
    ```  
  
## Vea también  
 <xref:System.Windows.Forms.SplitContainer>   
 [SplitContainer \(Control\)](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)   
 [Cómo: Crear una interfaz de usuario de varios paneles con formularios Windows Forms mediante el Diseñador](../../../../docs/framework/winforms/controls/create-a-multipane-user-interface-with-wf-using-the-designer.md)