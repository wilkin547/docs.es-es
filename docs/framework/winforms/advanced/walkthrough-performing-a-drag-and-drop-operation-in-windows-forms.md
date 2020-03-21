---
title: 'Tutorial: Realice una operación de arrastrar y colocar'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drag and drop operations
- drag and drop [Windows Forms], Windows Forms
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
ms.openlocfilehash: b5e4bf753733cb9bd010672f40e8fbeb0cf036bf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182443"
---
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a>Tutorial: Llevar a cabo una operación de arrastrar y colocar en formularios Windows Forms
Para realizar operaciones de arrastrar y colocar en aplicaciones basadas en Windows, <xref:System.Windows.Forms.Control.DragLeave>debe <xref:System.Windows.Forms.Control.DragDrop> controlar una serie de eventos, en particular los <xref:System.Windows.Forms.Control.DragEnter>eventos , , y . Trabajando con la información disponible en los argumentos de estos eventos, puede facilitar sin problemas las operaciones de arrastrar y colocar.  
  
## <a name="dragging-data"></a>Arrastrar datos  
 Todas las operaciones de arrastrar y colocar comienzan con arrastrar. La funcionalidad para permitir que los datos se recopilen <xref:System.Windows.Forms.Control.DoDragDrop%2A> cuando comienza el arrastre se implementa en el método.  
  
 En el ejemplo <xref:System.Windows.Forms.Control.MouseDown> siguiente, el evento se utiliza para iniciar la operación de arrastre porque es la más intuitiva (la mayoría de las acciones de arrastrar y colocar comienzan con el botón del mouse presionado). Sin embargo, recuerde que podría utilizarse cualquier evento para iniciar un procedimiento de arrastrar y colocar.  
  
> [!NOTE]
> Determinados controles tienen eventos personalizados específicos para la acción de arrastrar. Los <xref:System.Windows.Forms.ListView> <xref:System.Windows.Forms.TreeView> controles y, por <xref:System.Windows.Forms.TreeView.ItemDrag> ejemplo, tienen un evento.  
  
#### <a name="to-start-a-drag-operation"></a>Para iniciar una operación de arrastrar  
  
1. En <xref:System.Windows.Forms.Control.MouseDown> el caso del control donde se `DoDragDrop` iniciará el arrastre, utilice el método para establecer los datos que se van a arrastrar y tendrá el efecto permitido que tendrá el arrastre. Para más información, vea <xref:System.Windows.Forms.DragEventArgs.Data%2A> y <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.  
  
     En el ejemplo siguiente se muestra cómo iniciar una operación de arrastrar. El control donde comienza el <xref:System.Windows.Forms.Button> arrastre es un control, los <xref:System.Windows.Forms.Control.Text%2A> datos que <xref:System.Windows.Forms.Button> se arrastran es la cadena que representa la propiedad del control y los efectos permitidos se copian o se mueven.  
  
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
    > Cualquier dato se puede utilizar `DoDragDrop` como parámetro en el método; en el ejemplo <xref:System.Windows.Forms.Control.Text%2A> anterior, <xref:System.Windows.Forms.Button> se usó la propiedad del control (en lugar de codificar de forma rígida un valor o <xref:System.Windows.Forms.Button> recuperar datos de un conjunto de datos) porque la propiedad estaba relacionada con la ubicación desde la que se arrastraba (el control). Téngalo en cuenta cuando incorpore operaciones de arrastrar y colocar en aplicaciones basadas en Windows.  
  
 Mientras una operación de arrastre <xref:System.Windows.Forms.Control.QueryContinueDrag> está en vigor, puede controlar el evento, que "pide permiso" del sistema para continuar la operación de arrastre. Al controlar este método, también es el punto adecuado para llamar a métodos que tendrán un efecto en la operación de arrastre, como expandir un <xref:System.Windows.Forms.TreeNode> control cuando <xref:System.Windows.Forms.TreeView> el cursor se desplaza sobre él.  
  
## <a name="dropping-data"></a>Colocar datos  
 Una vez que haya empezado a arrastrar datos desde una ubicación a un control o Windows Forms, naturalmente deseará colocarlos en algún lugar. El cursor cambiará cuando cruce una zona de un formulario o control que esté configurada correctamente para la colocación de datos. Cualquier área dentro de un formulario Windows Forms o <xref:System.Windows.Forms.Control.AllowDrop%2A> control se <xref:System.Windows.Forms.Control.DragEnter> puede <xref:System.Windows.Forms.Control.DragDrop> hacer para aceptar datos eliminados estableciendo la propiedad y controlando los eventos y.  
  
#### <a name="to-perform-a-drop"></a>Para llevar a cabo la operación de colocar  
  
1. Establezca <xref:System.Windows.Forms.Control.AllowDrop%2A> la propiedad en true.  
  
2. En `DragEnter` el caso del control donde se producirá la colocación, asegúrese de que los <xref:System.Windows.Forms.Control.Text%2A>datos que se arrastran son de un tipo aceptable (en este caso, ). A continuación, el código establece el efecto que se <xref:System.Windows.Forms.DragDropEffects> producirá cuando se produzca la colocación en un valor de la enumeración. Para más información, consulte <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.  
  
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
    > Puede definir el <xref:System.Windows.Forms.DataFormats> suyo propio especificando <xref:System.Object> su propio <xref:System.Windows.Forms.DataObject.SetData%2A> objeto como parámetro del método. Cuando lo haga, asegúrese de que el objeto especificado sea serializable. Para más información, consulte <xref:System.Runtime.Serialization.ISerializable>.  
  
3. En <xref:System.Windows.Forms.Control.DragDrop> el caso del control donde se <xref:System.Windows.Forms.DataObject.GetData%2A> producirá la colocación, utilice el método para recuperar los datos que se arrastran. Para más información, consulte <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.  
  
     En el ejemplo <xref:System.Windows.Forms.TextBox> siguiente, un control es el control al que se arrastra (donde se producirá la colocación). El código <xref:System.Windows.Forms.Control.Text%2A> establece la <xref:System.Windows.Forms.TextBox> propiedad del control igual a los datos que se arrastran.  
  
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
    > Además, puede trabajar <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> con la propiedad, de modo que, dependiendo de las teclas deprimidas durante la operación de arrastrar y colocar, se producen ciertos efectos (por ejemplo, es estándar copiar los datos arrastrados cuando se presiona la tecla CTRL).  
  
## <a name="see-also"></a>Consulte también

- [Cómo: Agregar datos al Portapapeles](how-to-add-data-to-the-clipboard.md)
- [Cómo: Recuperar datos del Portapapeles](how-to-retrieve-data-from-the-clipboard.md)
- [Compatibilidad con las operaciones de arrastrar y colocar y con el Portapapeles](drag-and-drop-operations-and-clipboard-support.md)
