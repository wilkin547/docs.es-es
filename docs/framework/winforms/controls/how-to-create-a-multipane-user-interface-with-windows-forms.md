---
title: Filtrar Crear una interfaz de usuario de varios paneles con formularios de Windows
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SplitContainer control [Windows Forms], examples
- ListView control [Windows Forms], examples
- RichTextBox control [Windows Forms], examples
- Panel control [Windows Forms], examples
- TreeView control [Windows Forms], examples
- Splitter control [Windows Forms], examples
ms.assetid: e79f6bcc-3740-4d1e-b46a-c5594d9b7327
ms.openlocfilehash: 4db424b27af09dcb7def0051fba070fe9ccf0491
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57721975"
---
# <a name="how-to-create-a-multipane-user-interface-with-windows-forms"></a>Procedimiento Crear una interfaz de usuario de varios paneles con formularios de Windows
En el siguiente procedimiento, creará una interfaz de usuario de varios paneles similar al usado en Microsoft Outlook, con un **carpeta** lista, un **mensajes** panel y un **devistaprevia** panel. Esta disposición se logra principalmente mediante el acoplamiento de controles con el formulario.  
  
 Al acoplar un control, es necesario determinar cuál de los bordes del contenedor primario de un control está enchufado al. Por lo tanto, si establece la <xref:System.Windows.Forms.SplitContainer.Dock%2A> propiedad <xref:System.Windows.Forms.DockStyle.Right>, el borde derecho del control estará acoplado al borde derecho de su control principal. Además, el borde del control acoplado cambia para coincidir con el de su control contenedor. Para obtener más información acerca de cómo los <xref:System.Windows.Forms.SplitContainer.Dock%2A> propiedad, consulte [Cómo: Acoplar controles en Windows Forms](how-to-dock-controls-on-windows-forms.md).  
  
 Este procedimiento se centra en organizar el <xref:System.Windows.Forms.SplitContainer> y los controles del formulario, no en Agregar funcionalidad para que la aplicación que imite a Microsoft Outlook.  
  
 Para crear esta interfaz de usuario, coloque todos los controles dentro de un <xref:System.Windows.Forms.SplitContainer> control, que contiene un <xref:System.Windows.Forms.TreeView> control en el panel izquierdo. El panel derecho de la <xref:System.Windows.Forms.SplitContainer> control contiene un segundo <xref:System.Windows.Forms.SplitContainer> controlar con un <xref:System.Windows.Forms.ListView> control anterior un <xref:System.Windows.Forms.RichTextBox> control. Estos <xref:System.Windows.Forms.SplitContainer> controles permiten el cambio de tamaño independiente de los otros controles del formulario. Puede adaptar las técnicas de este procedimiento para interfaces de usuario personalizadas de elaborar su propio.  
  
### <a name="to-create-an-outlook-style-user-interface-programmatically"></a>Para crear una interfaz de usuario de estilo de Outlook mediante programación  
  
1.  Dentro de un formulario, declare cada control que compone la interfaz de usuario. En este ejemplo, utilice el <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.SplitContainer>, y <xref:System.Windows.Forms.RichTextBox> controles para imitar la interfaz de usuario de Microsoft Outlook.  
  
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
  
2.  Crear un procedimiento que define la interfaz de usuario. El código siguiente establece las propiedades para que el formulario será similar a la interfaz de usuario en Microsoft Outlook. Sin embargo, mediante otros controles o acopla de forma diferente, es fácil crear otras interfaces de usuario que son igualmente flexibles.  
  
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
  
3.  En Visual Basic, agregue una llamada al procedimiento que acaba de crear el `New()` procedimiento. En Visual C#, agregue esta línea de código al constructor para la clase de formulario.  
  
    ```vb  
    ' Add this to the New procedure.  
    CreateOutlookUI()  
    ```  
  
    ```csharp  
    // Add this to the form class's constructor.  
    createOutlookUI();  
    ```  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.SplitContainer>
- [SplitContainer (control)](splitcontainer-control-windows-forms.md)
- [Cómo: Crear una interfaz de usuario de varios paneles con formularios de Windows mediante el diseñador](create-a-multipane-user-interface-with-wf-using-the-designer.md)
