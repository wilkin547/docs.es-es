---
title: 'Tutorial: realizar una operación de arrastrar y colocar'
description: Obtenga información sobre cómo realizar una operación de arrastrar y colocar en Windows Forms controlando una serie de eventos, especialmente los eventos DragEnter, DragLeave y DragDrop.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drag and drop operations
- drag and drop [Windows Forms], Windows Forms
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
ms.openlocfilehash: 83bfda875e2fdec3981bbcb8f8f7be00db342440
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325818"
---
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a>Tutorial: Llevar a cabo una operación de arrastrar y colocar en formularios Windows Forms
Para realizar operaciones de arrastrar y colocar en aplicaciones basadas en Windows, debe controlar una serie de eventos, especialmente los <xref:System.Windows.Forms.Control.DragEnter> <xref:System.Windows.Forms.Control.DragLeave> eventos, y <xref:System.Windows.Forms.Control.DragDrop> . Trabajando con la información disponible en los argumentos de estos eventos, puede facilitar sin problemas las operaciones de arrastrar y colocar.  
  
## <a name="dragging-data"></a>Arrastrar datos  
 Todas las operaciones de arrastrar y colocar comienzan con arrastrar. La funcionalidad para habilitar la recopilación de datos al arrastrar comienza se implementa en el <xref:System.Windows.Forms.Control.DoDragDrop%2A> método.  
  
 En el ejemplo siguiente, el <xref:System.Windows.Forms.Control.MouseDown> evento se utiliza para iniciar la operación de arrastre porque es la más intuitiva (la mayoría de las acciones de arrastrar y colocar comienzan con el botón del mouse que se presiona). Sin embargo, recuerde que podría utilizarse cualquier evento para iniciar un procedimiento de arrastrar y colocar.  
  
> [!NOTE]
> Determinados controles tienen eventos personalizados específicos para la acción de arrastrar. Los <xref:System.Windows.Forms.ListView> <xref:System.Windows.Forms.TreeView> controles y, por ejemplo, tienen un <xref:System.Windows.Forms.TreeView.ItemDrag> evento.  
  
#### <a name="to-start-a-drag-operation"></a>Para iniciar una operación de arrastrar  
  
1. En el <xref:System.Windows.Forms.Control.MouseDown> caso del control donde se iniciará el arrastre, use el `DoDragDrop` método para establecer los datos que se van a arrastrar y el efecto permitido que se arrastra tendrá. Para obtener más información, vea <xref:System.Windows.Forms.DragEventArgs.Data%2A> y <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.  
  
     En el ejemplo siguiente se muestra cómo iniciar una operación de arrastrar. El control donde comienza el arrastre es un <xref:System.Windows.Forms.Button> control, los datos que se arrastran son la cadena que representa la <xref:System.Windows.Forms.Control.Text%2A> propiedad del <xref:System.Windows.Forms.Button> control y los efectos permitidos son copiar o mover.  
  
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
    > Los datos se pueden usar como parámetros en el `DoDragDrop` método; en el ejemplo anterior, <xref:System.Windows.Forms.Control.Text%2A> se usó la propiedad del <xref:System.Windows.Forms.Button> control (en lugar de codificar de forma rígida un valor o recuperar datos de un conjunto de datos) porque la propiedad estaba relacionada con la ubicación desde la que se arrastró (el <xref:System.Windows.Forms.Button> control). Téngalo en cuenta cuando incorpore operaciones de arrastrar y colocar en aplicaciones basadas en Windows.  
  
 Mientras haya una operación de arrastrar en vigor, puede controlar el <xref:System.Windows.Forms.Control.QueryContinueDrag> evento, que "pide permiso" del sistema para continuar con la operación de arrastre. Al controlar este método, también es el momento adecuado para llamar a métodos que afectarán a la operación de arrastre, como expandir un <xref:System.Windows.Forms.TreeNode> control en un <xref:System.Windows.Forms.TreeView> control cuando el cursor se mantiene sobre él.  
  
## <a name="dropping-data"></a>Colocar datos  
 Una vez que haya empezado a arrastrar datos desde una ubicación a un control o Windows Forms, naturalmente deseará colocarlos en algún lugar. El cursor cambiará cuando cruce una zona de un formulario o control que esté configurada correctamente para la colocación de datos. Cualquier área dentro de un formulario o un control de Windows puede realizarse para aceptar los datos colocados estableciendo la <xref:System.Windows.Forms.Control.AllowDrop%2A> propiedad y controlando los <xref:System.Windows.Forms.Control.DragEnter> <xref:System.Windows.Forms.Control.DragDrop> eventos y.  
  
#### <a name="to-perform-a-drop"></a>Para llevar a cabo la operación de colocar  
  
1. Establezca la <xref:System.Windows.Forms.Control.AllowDrop%2A> propiedad en true.  
  
2. En el `DragEnter` caso del control donde se producirá la colocación, asegúrese de que los datos que se arrastran son de un tipo aceptable (en este caso, <xref:System.Windows.Forms.Control.Text%2A> ). A continuación, el código establece el efecto que tendrá lugar cuando se produzca la colocación en un valor de la <xref:System.Windows.Forms.DragDropEffects> enumeración. Para más información, consulte <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.  
  
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
    > Puede definir su propia <xref:System.Windows.Forms.DataFormats> especificando su propio objeto como el <xref:System.Object> parámetro del <xref:System.Windows.Forms.DataObject.SetData%2A> método. Cuando lo haga, asegúrese de que el objeto especificado sea serializable. Para más información, consulte <xref:System.Runtime.Serialization.ISerializable>.  
  
3. En el <xref:System.Windows.Forms.Control.DragDrop> caso del control donde se producirá la colocación, use el <xref:System.Windows.Forms.DataObject.GetData%2A> método para recuperar los datos que se arrastran. Para más información, consulte <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.  
  
     En el ejemplo siguiente, un <xref:System.Windows.Forms.TextBox> control es el control al que se está arrastrando (donde se producirá la colocación). El código establece la <xref:System.Windows.Forms.Control.Text%2A> propiedad del <xref:System.Windows.Forms.TextBox> control igual a los datos que se arrastran.  
  
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
    > Además, puede trabajar con la <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> propiedad, de modo que, en función de las teclas presionadas durante la operación de arrastrar y colocar, se produzcan ciertos efectos (por ejemplo, es estándar copiar los datos arrastrados cuando se presiona la tecla Ctrl).  
  
## <a name="see-also"></a>Vea también

- [Procedimiento para agregar datos al Portapapeles](how-to-add-data-to-the-clipboard.md)
- [Procedimiento para recuperar datos del Portapapeles](how-to-retrieve-data-from-the-clipboard.md)
- [Compatibilidad con las operaciones de arrastrar y colocar y con el Portapapeles](drag-and-drop-operations-and-clipboard-support.md)
