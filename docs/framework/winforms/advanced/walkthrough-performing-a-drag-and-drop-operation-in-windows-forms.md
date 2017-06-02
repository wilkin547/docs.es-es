---
title: "Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Windows Forms, drag and drop operations"
  - "drag and drop, Windows Forms"
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms
Para realizar las operaciones de arrastrar y colocar en las aplicaciones basadas en Windows, debe controlar una serie de eventos, sobre todo <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave> y <xref:System.Windows.Forms.Control.DragDrop>.  La información disponible en los argumentos de estos eventos facilita, de forma muy sencilla, las operaciones de arrastrar y colocar.  
  
## Arrastrar datos  
 Todas las opciones de arrastrar y colocar empiezan por arrastrar.  La función de habilitar la posibilidad de recopilar los datos cuando se inicia la operación de arrastrar se implementa en el método <xref:System.Windows.Forms.Control.DoDragDrop%2A>.  
  
 En el ejemplo siguiente, se usa el evento <xref:System.Windows.Forms.Control.MouseDown> para iniciar la operación de arrastrar, ya que es más intuitivo \(la mayor parte de acciones de arrastrar y colocar se inician cuando se presiona el botón del mouse\).  No obstante, recuerde que puede utilizarse cualquier evento para iniciar un procedimiento de arrastrar y colocar.  
  
> [!NOTE]
>  Algunos controles disponen de eventos de arrastrar personalizados.  Los controles <xref:System.Windows.Forms.ListView> y <xref:System.Windows.Forms.TreeView>, por ejemplo, tienen un evento <xref:System.Windows.Forms.TreeView.ItemDrag>.  
  
#### Para iniciar una operación de arrastre  
  
1.  En el eventode <xref:System.Windows.Forms.Control.MouseDown>para el control donde iniciar la operación, utilice el método de `DoDragDrop` para establecer los datos que se arrastrarán y el efecto que tendrá.  Para obtener más información, vea <xref:System.Windows.Forms.DragEventArgs.Data%2A> y <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.  
  
     En el ejemplo siguiente se muestra cómo iniciar una operación de arrastre:  Si el control donde se va a iniciar la operación es un control <xref:System.Windows.Forms.Button>, los datos que se arrastran corresponden a la cadena que representa la propiedad <xref:System.Windows.Forms.Control.Text%2A> del control <xref:System.Windows.Forms.Button>, y los efectos permitidos son copiar o mover.  
  
    ```vb  
    Private Sub Button1_MouseDown(ByVal sender As Object, ByVal e As System.Windows.Forms.MouseEventArgs) Handles Button1.MouseDown  
       Button1.DoDragDrop(Button1.Text, DragDropEffects.Copy Or DragDropEffects.Move)  
    End Sub  
  
    ```  
  
    ```csharp  
    private void button1_MouseDown(object sender,   
    System.Windows.Forms.MouseEventArgs e)  
    {  
       button1.DoDragDrop(button1.Text, DragDropEffects.Copy |   
          DragDropEffects.Move);  
    }  
  
    ```  
  
    > [!NOTE]
    >  Se puede usar cualquier dato como parámetro en el método `DoDragDrop`; en el ejemplo anterior, se usó la propiedad <xref:System.Windows.Forms.Control.Text%2A> del control  <xref:System.Windows.Forms.Button> \(en lugar de incluir un valor incluido en el código o recuperar datos desde un conjunto de datos\) porque la propiedad estaba relacionada con la ubicación desde la que se realizó la operación de arrastrar \(el control <xref:System.Windows.Forms.Button>\).  No lo olvide cuando incorpore operaciones de arrastrar y colocar a aplicaciones para Windows.  
  
 Mientras esté vigente una operación de arrastrar, se puede controlar el evento <xref:System.Windows.Forms.Control.QueryContinueDrag>, que "pide permiso" al sistema para continuar la operación de arrastrar.  Cuando se realice este método, también conviene recordar llamar a métodos que tengan un efecto sobre la operación de arrastrar, como expandir un <xref:System.Windows.Forms.TreeNode> en un control <xref:System.Windows.Forms.TreeView> cuando el cursor se mantiene sobre él.  
  
## Colocar datos  
 Una vez que haya empezado a arrastrar datos desde un Windows Form o desde un control, lo natural será que desee colocarlos en algún lugar.  El cursor cambiará cuando cruce un área de un formulario o control que esté correctamente configurada para colocar datos.  Se puede hacer que cualquier área dentro de un Windows Form o un control acepte datos colocados si se establece la propiedad <xref:System.Windows.Forms.Control.AllowDrop%2A> y se controlan los eventos <xref:System.Windows.Forms.Control.DragEnter> y <xref:System.Windows.Forms.Control.DragDrop>.  
  
#### Para colocar  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.Control.AllowDrop%2A> en true.  
  
2.  En el evento `DragEnter` del control donde tiene lugar la operación de colocar, asegúrese de que los datos que se están arrastrando tienen un tipo aceptable \(en este caso, <xref:System.Windows.Forms.Control.Text%2A>\).  A continuación, el código establece el efecto que tendrá lugar al colocar como un valor de la enumeración <xref:System.Windows.Forms.DragDropEffects>.  Para obtener más información, vea <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.  
  
    ```vb  
    Private Sub TextBox1_DragEnter(ByVal sender As Object, ByVal e As System.Windows.Forms.DragEventArgs) Handles TextBox1.DragEnter  
       If (e.Data.GetDataPresent(DataFormats.Text)) Then  
         e.Effect = DragDropEffects.Copy  
       Else  
         e.Effect = DragDropEffects.None  
       End If  
    End Sub  
  
    ```  
  
    ```csharp  
    private void textBox1_DragEnter(object sender,   
    System.Windows.Forms.DragEventArgs e)  
    {  
       if (e.Data.GetDataPresent(DataFormats.Text))   
          e.Effect = DragDropEffects.Copy;  
       else  
          e.Effect = DragDropEffects.None;  
    }  
  
    ```  
  
    > [!NOTE]
    >  Puede definir sus propios <xref:System.Windows.Forms.DataFormats> especificando su propio objeto como el parámetro <xref:System.Object> del método <xref:System.Windows.Forms.DataObject.SetData%2A>.  Cuando lo haga, asegúrese de que el objeto especificado sea serializable.  Para obtener más información, vea [Iserializable \(interfaz\)](frlrfSystemRuntimeSerializationISerializableClassTopic).  
  
3.  En el evento <xref:System.Windows.Forms.Control.DragDrop> del control donde tiene lugar la operación de colocar, utilice el método <xref:System.Windows.Forms.DataObject.GetData%2A> para recuperar los datos que se arrastran.  Para obtener más información, vea [DtaObject.Data Property](frlrfSystemSecurityCryptographyXmlDataObjectClassDataTopic).  
  
     En el ejemplo siguiente, el control <xref:System.Windows.Forms.TextBox> es el control que se está arrastrando \(donde tendrá lugar la operación de colocar\).  El código establece la propiedad <xref:System.Windows.Forms.Control.Text%2A> del control <xref:System.Windows.Forms.TextBox> igual a los datos que se están arrastrando.  
  
    ```vb  
    Private Sub TextBox1_DragDrop(ByVal sender As Object, ByVal e As System.Windows.Forms.DragEventArgs) Handles TextBox1.DragDrop  
       TextBox1.Text = e.Data.GetData(DataFormats.Text).ToString  
    End Sub  
  
    ```  
  
    ```csharp  
    private void textBox1_DragDrop(object sender,   
    System.Windows.Forms.DragEventArgs e)  
    {  
       textBox1.Text = e.Data.GetData(DataFormats.Text).ToString();  
    }  
  
    ```  
  
    > [!NOTE]
    >  Se puede también trabajar con la propiedad <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> para que, en función de las teclas presionadas durante la operación de arrastrar y colocar, tengan lugar ciertos efectos \(por ejemplo, un efecto estándar es copiar los datos arrastrados cuando se presiona la tecla CTRL\).  
  
## Vea también  
 [How to: Add Data to the Clipboard](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)   
 [How to: Retrieve Data from the Clipboard](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)   
 [Drag\-and\-Drop Operations and Clipboard Support](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)