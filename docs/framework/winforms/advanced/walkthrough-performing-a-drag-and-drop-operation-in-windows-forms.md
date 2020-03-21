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
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a><span data-ttu-id="b2373-102">Tutorial: Llevar a cabo una operación de arrastrar y colocar en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b2373-102">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>
<span data-ttu-id="b2373-103">Para realizar operaciones de arrastrar y colocar en aplicaciones basadas en Windows, <xref:System.Windows.Forms.Control.DragLeave>debe <xref:System.Windows.Forms.Control.DragDrop> controlar una serie de eventos, en particular los <xref:System.Windows.Forms.Control.DragEnter>eventos , , y .</span><span class="sxs-lookup"><span data-stu-id="b2373-103">To perform drag-and-drop operations within Windows-based applications you must handle a series of events, most notably the <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span> <span data-ttu-id="b2373-104">Trabajando con la información disponible en los argumentos de estos eventos, puede facilitar sin problemas las operaciones de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="b2373-104">By working with the information available in the event arguments of these events, you can easily facilitate drag-and-drop operations.</span></span>  
  
## <a name="dragging-data"></a><span data-ttu-id="b2373-105">Arrastrar datos</span><span class="sxs-lookup"><span data-stu-id="b2373-105">Dragging Data</span></span>  
 <span data-ttu-id="b2373-106">Todas las operaciones de arrastrar y colocar comienzan con arrastrar.</span><span class="sxs-lookup"><span data-stu-id="b2373-106">All drag-and-drop operations begin with dragging.</span></span> <span data-ttu-id="b2373-107">La funcionalidad para permitir que los datos se recopilen <xref:System.Windows.Forms.Control.DoDragDrop%2A> cuando comienza el arrastre se implementa en el método.</span><span class="sxs-lookup"><span data-stu-id="b2373-107">The functionality to enable data to be collected when dragging begins is implemented in the <xref:System.Windows.Forms.Control.DoDragDrop%2A> method.</span></span>  
  
 <span data-ttu-id="b2373-108">En el ejemplo <xref:System.Windows.Forms.Control.MouseDown> siguiente, el evento se utiliza para iniciar la operación de arrastre porque es la más intuitiva (la mayoría de las acciones de arrastrar y colocar comienzan con el botón del mouse presionado).</span><span class="sxs-lookup"><span data-stu-id="b2373-108">In the following example, the <xref:System.Windows.Forms.Control.MouseDown> event is used to start the drag operation because it is the most intuitive (most drag-and-drop actions begin with the mouse button being depressed).</span></span> <span data-ttu-id="b2373-109">Sin embargo, recuerde que podría utilizarse cualquier evento para iniciar un procedimiento de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="b2373-109">However, remember that any event could be used to initiate a drag-and-drop procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b2373-110">Determinados controles tienen eventos personalizados específicos para la acción de arrastrar.</span><span class="sxs-lookup"><span data-stu-id="b2373-110">Certain controls have custom drag-specific events.</span></span> <span data-ttu-id="b2373-111">Los <xref:System.Windows.Forms.ListView> <xref:System.Windows.Forms.TreeView> controles y, por <xref:System.Windows.Forms.TreeView.ItemDrag> ejemplo, tienen un evento.</span><span class="sxs-lookup"><span data-stu-id="b2373-111">The <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls, for example, have an <xref:System.Windows.Forms.TreeView.ItemDrag> event.</span></span>  
  
#### <a name="to-start-a-drag-operation"></a><span data-ttu-id="b2373-112">Para iniciar una operación de arrastrar</span><span class="sxs-lookup"><span data-stu-id="b2373-112">To start a drag operation</span></span>  
  
1. <span data-ttu-id="b2373-113">En <xref:System.Windows.Forms.Control.MouseDown> el caso del control donde se `DoDragDrop` iniciará el arrastre, utilice el método para establecer los datos que se van a arrastrar y tendrá el efecto permitido que tendrá el arrastre.</span><span class="sxs-lookup"><span data-stu-id="b2373-113">In the <xref:System.Windows.Forms.Control.MouseDown> event for the control where the drag will begin, use the `DoDragDrop` method to set the data to be dragged and the allowed effect dragging will have.</span></span> <span data-ttu-id="b2373-114">Para más información, vea <xref:System.Windows.Forms.DragEventArgs.Data%2A> y <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span><span class="sxs-lookup"><span data-stu-id="b2373-114">For more information, see <xref:System.Windows.Forms.DragEventArgs.Data%2A> and <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span></span>  
  
     <span data-ttu-id="b2373-115">En el ejemplo siguiente se muestra cómo iniciar una operación de arrastrar.</span><span class="sxs-lookup"><span data-stu-id="b2373-115">The following example shows how to initiate a drag operation.</span></span> <span data-ttu-id="b2373-116">El control donde comienza el <xref:System.Windows.Forms.Button> arrastre es un control, los <xref:System.Windows.Forms.Control.Text%2A> datos que <xref:System.Windows.Forms.Button> se arrastran es la cadena que representa la propiedad del control y los efectos permitidos se copian o se mueven.</span><span class="sxs-lookup"><span data-stu-id="b2373-116">The control where the drag begins is a <xref:System.Windows.Forms.Button> control, the data being dragged is the string representing the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control, and the allowed effects are either copying or moving.</span></span>  
  
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
    > <span data-ttu-id="b2373-117">Cualquier dato se puede utilizar `DoDragDrop` como parámetro en el método; en el ejemplo <xref:System.Windows.Forms.Control.Text%2A> anterior, <xref:System.Windows.Forms.Button> se usó la propiedad del control (en lugar de codificar de forma rígida un valor o <xref:System.Windows.Forms.Button> recuperar datos de un conjunto de datos) porque la propiedad estaba relacionada con la ubicación desde la que se arrastraba (el control).</span><span class="sxs-lookup"><span data-stu-id="b2373-117">Any data can be used as a parameter in the `DoDragDrop` method; in the example above, the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control was used (rather than hard-coding a value or retrieving data from a dataset) because the property was related to the location being dragged from (the <xref:System.Windows.Forms.Button> control).</span></span> <span data-ttu-id="b2373-118">Téngalo en cuenta cuando incorpore operaciones de arrastrar y colocar en aplicaciones basadas en Windows.</span><span class="sxs-lookup"><span data-stu-id="b2373-118">Keep this in mind as you incorporate drag-and-drop operations into your Windows-based applications.</span></span>  
  
 <span data-ttu-id="b2373-119">Mientras una operación de arrastre <xref:System.Windows.Forms.Control.QueryContinueDrag> está en vigor, puede controlar el evento, que "pide permiso" del sistema para continuar la operación de arrastre.</span><span class="sxs-lookup"><span data-stu-id="b2373-119">While a drag operation is in effect, you can handle the <xref:System.Windows.Forms.Control.QueryContinueDrag> event, which "asks permission" of the system to continue the drag operation.</span></span> <span data-ttu-id="b2373-120">Al controlar este método, también es el punto adecuado para llamar a métodos que tendrán un efecto en la operación de arrastre, como expandir un <xref:System.Windows.Forms.TreeNode> control cuando <xref:System.Windows.Forms.TreeView> el cursor se desplaza sobre él.</span><span class="sxs-lookup"><span data-stu-id="b2373-120">When handling this method, it is also the appropriate point for you to call methods that will have an effect on the drag operation, such as expanding a <xref:System.Windows.Forms.TreeNode> in a <xref:System.Windows.Forms.TreeView> control when the cursor hovers over it.</span></span>  
  
## <a name="dropping-data"></a><span data-ttu-id="b2373-121">Colocar datos</span><span class="sxs-lookup"><span data-stu-id="b2373-121">Dropping Data</span></span>  
 <span data-ttu-id="b2373-122">Una vez que haya empezado a arrastrar datos desde una ubicación a un control o Windows Forms, naturalmente deseará colocarlos en algún lugar.</span><span class="sxs-lookup"><span data-stu-id="b2373-122">Once you have begun dragging data from a location on a Windows Form or control, you will naturally want to drop it somewhere.</span></span> <span data-ttu-id="b2373-123">El cursor cambiará cuando cruce una zona de un formulario o control que esté configurada correctamente para la colocación de datos.</span><span class="sxs-lookup"><span data-stu-id="b2373-123">The cursor will change when it crosses an area of a form or control that is correctly configured for dropping data.</span></span> <span data-ttu-id="b2373-124">Cualquier área dentro de un formulario Windows Forms o <xref:System.Windows.Forms.Control.AllowDrop%2A> control se <xref:System.Windows.Forms.Control.DragEnter> puede <xref:System.Windows.Forms.Control.DragDrop> hacer para aceptar datos eliminados estableciendo la propiedad y controlando los eventos y.</span><span class="sxs-lookup"><span data-stu-id="b2373-124">Any area within a Windows Form or control can be made to accept dropped data by setting the <xref:System.Windows.Forms.Control.AllowDrop%2A> property and handling the <xref:System.Windows.Forms.Control.DragEnter> and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span>  
  
#### <a name="to-perform-a-drop"></a><span data-ttu-id="b2373-125">Para llevar a cabo la operación de colocar</span><span class="sxs-lookup"><span data-stu-id="b2373-125">To perform a drop</span></span>  
  
1. <span data-ttu-id="b2373-126">Establezca <xref:System.Windows.Forms.Control.AllowDrop%2A> la propiedad en true.</span><span class="sxs-lookup"><span data-stu-id="b2373-126">Set the <xref:System.Windows.Forms.Control.AllowDrop%2A> property to true.</span></span>  
  
2. <span data-ttu-id="b2373-127">En `DragEnter` el caso del control donde se producirá la colocación, asegúrese de que los <xref:System.Windows.Forms.Control.Text%2A>datos que se arrastran son de un tipo aceptable (en este caso, ).</span><span class="sxs-lookup"><span data-stu-id="b2373-127">In the `DragEnter` event for the control where the drop will occur, ensure that the data being dragged is of an acceptable type (in this case, <xref:System.Windows.Forms.Control.Text%2A>).</span></span> <span data-ttu-id="b2373-128">A continuación, el código establece el efecto que se <xref:System.Windows.Forms.DragDropEffects> producirá cuando se produzca la colocación en un valor de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="b2373-128">The code then sets the effect that will happen when the drop occurs to a value in the <xref:System.Windows.Forms.DragDropEffects> enumeration.</span></span> <span data-ttu-id="b2373-129">Para más información, consulte <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span><span class="sxs-lookup"><span data-stu-id="b2373-129">For more information, see <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span></span>  
  
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
    > <span data-ttu-id="b2373-130">Puede definir el <xref:System.Windows.Forms.DataFormats> suyo propio especificando <xref:System.Object> su propio <xref:System.Windows.Forms.DataObject.SetData%2A> objeto como parámetro del método.</span><span class="sxs-lookup"><span data-stu-id="b2373-130">You can define your own <xref:System.Windows.Forms.DataFormats> by specifying your own object as the <xref:System.Object> parameter of the <xref:System.Windows.Forms.DataObject.SetData%2A> method.</span></span> <span data-ttu-id="b2373-131">Cuando lo haga, asegúrese de que el objeto especificado sea serializable.</span><span class="sxs-lookup"><span data-stu-id="b2373-131">Be sure, when doing this, that the object specified is serializable.</span></span> <span data-ttu-id="b2373-132">Para más información, consulte <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="b2373-132">For more information, see <xref:System.Runtime.Serialization.ISerializable>.</span></span>  
  
3. <span data-ttu-id="b2373-133">En <xref:System.Windows.Forms.Control.DragDrop> el caso del control donde se <xref:System.Windows.Forms.DataObject.GetData%2A> producirá la colocación, utilice el método para recuperar los datos que se arrastran.</span><span class="sxs-lookup"><span data-stu-id="b2373-133">In the <xref:System.Windows.Forms.Control.DragDrop> event for the control where the drop will occur, use the <xref:System.Windows.Forms.DataObject.GetData%2A> method to retrieve the data being dragged.</span></span> <span data-ttu-id="b2373-134">Para más información, consulte <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.</span><span class="sxs-lookup"><span data-stu-id="b2373-134">For more information, see <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.</span></span>  
  
     <span data-ttu-id="b2373-135">En el ejemplo <xref:System.Windows.Forms.TextBox> siguiente, un control es el control al que se arrastra (donde se producirá la colocación).</span><span class="sxs-lookup"><span data-stu-id="b2373-135">In the example below, a <xref:System.Windows.Forms.TextBox> control is the control being dragged to (where the drop will occur).</span></span> <span data-ttu-id="b2373-136">El código <xref:System.Windows.Forms.Control.Text%2A> establece la <xref:System.Windows.Forms.TextBox> propiedad del control igual a los datos que se arrastran.</span><span class="sxs-lookup"><span data-stu-id="b2373-136">The code sets the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.TextBox> control equal to the data being dragged.</span></span>  
  
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
    > <span data-ttu-id="b2373-137">Además, puede trabajar <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> con la propiedad, de modo que, dependiendo de las teclas deprimidas durante la operación de arrastrar y colocar, se producen ciertos efectos (por ejemplo, es estándar copiar los datos arrastrados cuando se presiona la tecla CTRL).</span><span class="sxs-lookup"><span data-stu-id="b2373-137">Additionally, you can work with the <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> property, so that, depending on keys depressed during the drag-and-drop operation, certain effects occur (for example, it is standard to copy the dragged data when the CTRL key is pressed).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2373-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b2373-138">See also</span></span>

- [<span data-ttu-id="b2373-139">Cómo: Agregar datos al Portapapeles</span><span class="sxs-lookup"><span data-stu-id="b2373-139">How to: Add Data to the Clipboard</span></span>](how-to-add-data-to-the-clipboard.md)
- [<span data-ttu-id="b2373-140">Cómo: Recuperar datos del Portapapeles</span><span class="sxs-lookup"><span data-stu-id="b2373-140">How to: Retrieve Data from the Clipboard</span></span>](how-to-retrieve-data-from-the-clipboard.md)
- [<span data-ttu-id="b2373-141">Compatibilidad con las operaciones de arrastrar y colocar y con el Portapapeles</span><span class="sxs-lookup"><span data-stu-id="b2373-141">Drag-and-Drop Operations and Clipboard Support</span></span>](drag-and-drop-operations-and-clipboard-support.md)
