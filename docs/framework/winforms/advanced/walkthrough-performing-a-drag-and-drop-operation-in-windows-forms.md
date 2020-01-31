---
title: 'Tutorial: realizar una operación de arrastrar y colocar'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drag and drop operations
- drag and drop [Windows Forms], Windows Forms
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
ms.openlocfilehash: 265e6d4f9e3370d28a18b86dea983bb0b556be41
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746795"
---
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a>Tutorial: Llevar a cabo una operación de arrastrar y colocar en Windows Forms
Para realizar operaciones de arrastrar y colocar en aplicaciones basadas en Windows, debe controlar una serie de eventos, especialmente los eventos <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>y <xref:System.Windows.Forms.Control.DragDrop>. Trabajando con la información disponible en los argumentos de estos eventos, puede facilitar sin problemas las operaciones de arrastrar y colocar.  
  
## <a name="dragging-data"></a>Arrastrar datos  
 Todas las operaciones de arrastrar y colocar comienzan con arrastrar. La funcionalidad para habilitar la recopilación de datos al arrastrar comienza se implementa en el método <xref:System.Windows.Forms.Control.DoDragDrop%2A>.  
  
 En el ejemplo siguiente, el evento <xref:System.Windows.Forms.Control.MouseDown> se utiliza para iniciar la operación de arrastre porque es el más intuitivo (la mayoría de las acciones de arrastrar y colocar comienzan con el botón del mouse que se presiona). Sin embargo, recuerde que podría utilizarse cualquier evento para iniciar un procedimiento de arrastrar y colocar.  
  
> [!NOTE]
> Determinados controles tienen eventos personalizados específicos para la acción de arrastrar. Los controles <xref:System.Windows.Forms.ListView> y <xref:System.Windows.Forms.TreeView>, por ejemplo, tienen un evento <xref:System.Windows.Forms.TreeView.ItemDrag>.  
  
#### <a name="to-start-a-drag-operation"></a>Para iniciar una operación de arrastrar  
  
1. En el evento <xref:System.Windows.Forms.Control.MouseDown> del control en el que se iniciará el arrastre, use el método `DoDragDrop` para establecer los datos que se van a arrastrar y el efecto permitido que se va a arrastrar tendrá. Para obtener más información, vea <xref:System.Windows.Forms.DragEventArgs.Data%2A> y <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.  
  
     En el ejemplo siguiente se muestra cómo iniciar una operación de arrastrar. El control donde comienza el arrastre es un control <xref:System.Windows.Forms.Button>, los datos que se arrastran son la cadena que representa la propiedad <xref:System.Windows.Forms.Control.Text%2A> del control <xref:System.Windows.Forms.Button> y los efectos permitidos son copiar o mover.  
  
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
    > Los datos se pueden usar como parámetros en el método `DoDragDrop`; en el ejemplo anterior, se usó la propiedad <xref:System.Windows.Forms.Control.Text%2A> del control <xref:System.Windows.Forms.Button> (en lugar de codificar de forma rígida un valor o recuperar datos de un conjunto de datos) porque la propiedad estaba relacionada con la ubicación de la que se está arrastrando (el control <xref:System.Windows.Forms.Button>). Téngalo en cuenta cuando incorpore operaciones de arrastrar y colocar en aplicaciones basadas en Windows.  
  
 Mientras haya una operación de arrastrar en vigor, puede controlar el evento <xref:System.Windows.Forms.Control.QueryContinueDrag>, que "pide permiso" del sistema para continuar con la operación de arrastre. Al controlar este método, también es el momento adecuado para llamar a métodos que afectarán a la operación de arrastre, como expandir un <xref:System.Windows.Forms.TreeNode> en un control de <xref:System.Windows.Forms.TreeView> cuando el cursor se mantiene sobre él.  
  
## <a name="dropping-data"></a>Colocar datos  
 Una vez que haya empezado a arrastrar datos desde una ubicación a un control o Windows Forms, naturalmente deseará colocarlos en algún lugar. El cursor cambiará cuando cruce una zona de un formulario o control que esté configurada correctamente para la colocación de datos. Cualquier área dentro de un formulario o control de Windows puede realizarse para aceptar los datos colocados estableciendo la propiedad <xref:System.Windows.Forms.Control.AllowDrop%2A> y controlando los eventos <xref:System.Windows.Forms.Control.DragEnter> y <xref:System.Windows.Forms.Control.DragDrop>.  
  
#### <a name="to-perform-a-drop"></a>Para llevar a cabo la operación de colocar  
  
1. Establezca la propiedad <xref:System.Windows.Forms.Control.AllowDrop%2A> en true.  
  
2. En el evento `DragEnter` del control donde se producirá la colocación, asegúrese de que los datos que se arrastran son de un tipo aceptable (en este caso, <xref:System.Windows.Forms.Control.Text%2A>). A continuación, el código establece el efecto que tendrá lugar cuando se produzca la colocación en un valor de la enumeración <xref:System.Windows.Forms.DragDropEffects>. Para obtener más información, vea <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.  
  
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
    > Puede definir su propio <xref:System.Windows.Forms.DataFormats> especificando su propio objeto como <xref:System.Object> parámetro del método <xref:System.Windows.Forms.DataObject.SetData%2A>. Cuando lo haga, asegúrese de que el objeto especificado sea serializable. Para obtener más información, vea <xref:System.Runtime.Serialization.ISerializable>.  
  
3. En el evento <xref:System.Windows.Forms.Control.DragDrop> del control donde se producirá la eliminación, use el método <xref:System.Windows.Forms.DataObject.GetData%2A> para recuperar los datos que se arrastran. Para obtener más información, vea <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.  
  
     En el ejemplo siguiente, un control <xref:System.Windows.Forms.TextBox> es el control al que se está arrastrando (donde se producirá la colocación). El código establece la propiedad <xref:System.Windows.Forms.Control.Text%2A> del control <xref:System.Windows.Forms.TextBox> igual a los datos que se arrastran.  
  
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
    > Además, puede trabajar con la propiedad <xref:System.Windows.Forms.DragEventArgs.KeyState%2A>, de modo que, en función de las teclas presionadas durante la operación de arrastrar y colocar, se produzcan ciertos efectos (por ejemplo, es estándar copiar los datos arrastrados cuando se presiona la tecla CTRL).  
  
## <a name="see-also"></a>Vea también

- [Agregar datos al Portapapeles](how-to-add-data-to-the-clipboard.md)
- [Recuperar datos del Portapapeles](how-to-retrieve-data-from-the-clipboard.md)
- [Compatibilidad con las operaciones de arrastrar y colocar y con el Portapapeles](drag-and-drop-operations-and-clipboard-support.md)
