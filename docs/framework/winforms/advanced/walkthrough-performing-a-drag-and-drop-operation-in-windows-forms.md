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
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a><span data-ttu-id="84d34-102">Tutorial: Llevar a cabo una operación de arrastrar y colocar en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="84d34-102">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>
<span data-ttu-id="84d34-103">Para realizar operaciones de arrastrar y colocar en aplicaciones basadas en Windows, debe controlar una serie de eventos, especialmente los eventos <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>y <xref:System.Windows.Forms.Control.DragDrop>.</span><span class="sxs-lookup"><span data-stu-id="84d34-103">To perform drag-and-drop operations within Windows-based applications you must handle a series of events, most notably the <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span> <span data-ttu-id="84d34-104">Trabajando con la información disponible en los argumentos de estos eventos, puede facilitar sin problemas las operaciones de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="84d34-104">By working with the information available in the event arguments of these events, you can easily facilitate drag-and-drop operations.</span></span>  
  
## <a name="dragging-data"></a><span data-ttu-id="84d34-105">Arrastrar datos</span><span class="sxs-lookup"><span data-stu-id="84d34-105">Dragging Data</span></span>  
 <span data-ttu-id="84d34-106">Todas las operaciones de arrastrar y colocar comienzan con arrastrar.</span><span class="sxs-lookup"><span data-stu-id="84d34-106">All drag-and-drop operations begin with dragging.</span></span> <span data-ttu-id="84d34-107">La funcionalidad para habilitar la recopilación de datos al arrastrar comienza se implementa en el método <xref:System.Windows.Forms.Control.DoDragDrop%2A>.</span><span class="sxs-lookup"><span data-stu-id="84d34-107">The functionality to enable data to be collected when dragging begins is implemented in the <xref:System.Windows.Forms.Control.DoDragDrop%2A> method.</span></span>  
  
 <span data-ttu-id="84d34-108">En el ejemplo siguiente, el evento <xref:System.Windows.Forms.Control.MouseDown> se utiliza para iniciar la operación de arrastre porque es el más intuitivo (la mayoría de las acciones de arrastrar y colocar comienzan con el botón del mouse que se presiona).</span><span class="sxs-lookup"><span data-stu-id="84d34-108">In the following example, the <xref:System.Windows.Forms.Control.MouseDown> event is used to start the drag operation because it is the most intuitive (most drag-and-drop actions begin with the mouse button being depressed).</span></span> <span data-ttu-id="84d34-109">Sin embargo, recuerde que podría utilizarse cualquier evento para iniciar un procedimiento de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="84d34-109">However, remember that any event could be used to initiate a drag-and-drop procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="84d34-110">Determinados controles tienen eventos personalizados específicos para la acción de arrastrar.</span><span class="sxs-lookup"><span data-stu-id="84d34-110">Certain controls have custom drag-specific events.</span></span> <span data-ttu-id="84d34-111">Los controles <xref:System.Windows.Forms.ListView> y <xref:System.Windows.Forms.TreeView>, por ejemplo, tienen un evento <xref:System.Windows.Forms.TreeView.ItemDrag>.</span><span class="sxs-lookup"><span data-stu-id="84d34-111">The <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls, for example, have an <xref:System.Windows.Forms.TreeView.ItemDrag> event.</span></span>  
  
#### <a name="to-start-a-drag-operation"></a><span data-ttu-id="84d34-112">Para iniciar una operación de arrastrar</span><span class="sxs-lookup"><span data-stu-id="84d34-112">To start a drag operation</span></span>  
  
1. <span data-ttu-id="84d34-113">En el evento <xref:System.Windows.Forms.Control.MouseDown> del control en el que se iniciará el arrastre, use el método `DoDragDrop` para establecer los datos que se van a arrastrar y el efecto permitido que se va a arrastrar tendrá.</span><span class="sxs-lookup"><span data-stu-id="84d34-113">In the <xref:System.Windows.Forms.Control.MouseDown> event for the control where the drag will begin, use the `DoDragDrop` method to set the data to be dragged and the allowed effect dragging will have.</span></span> <span data-ttu-id="84d34-114">Para más información, vea <xref:System.Windows.Forms.DragEventArgs.Data%2A> y <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span><span class="sxs-lookup"><span data-stu-id="84d34-114">For more information, see <xref:System.Windows.Forms.DragEventArgs.Data%2A> and <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span></span>  
  
     <span data-ttu-id="84d34-115">En el ejemplo siguiente se muestra cómo iniciar una operación de arrastrar.</span><span class="sxs-lookup"><span data-stu-id="84d34-115">The following example shows how to initiate a drag operation.</span></span> <span data-ttu-id="84d34-116">El control donde comienza el arrastre es un control <xref:System.Windows.Forms.Button>, los datos que se arrastran son la cadena que representa la propiedad <xref:System.Windows.Forms.Control.Text%2A> del control <xref:System.Windows.Forms.Button> y los efectos permitidos son copiar o mover.</span><span class="sxs-lookup"><span data-stu-id="84d34-116">The control where the drag begins is a <xref:System.Windows.Forms.Button> control, the data being dragged is the string representing the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control, and the allowed effects are either copying or moving.</span></span>  
  
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
    > <span data-ttu-id="84d34-117">Los datos se pueden usar como parámetros en el método `DoDragDrop`; en el ejemplo anterior, se usó la propiedad <xref:System.Windows.Forms.Control.Text%2A> del control <xref:System.Windows.Forms.Button> (en lugar de codificar de forma rígida un valor o recuperar datos de un conjunto de datos) porque la propiedad estaba relacionada con la ubicación de la que se está arrastrando (el control <xref:System.Windows.Forms.Button>).</span><span class="sxs-lookup"><span data-stu-id="84d34-117">Any data can be used as a parameter in the `DoDragDrop` method; in the example above, the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control was used (rather than hard-coding a value or retrieving data from a dataset) because the property was related to the location being dragged from (the <xref:System.Windows.Forms.Button> control).</span></span> <span data-ttu-id="84d34-118">Téngalo en cuenta cuando incorpore operaciones de arrastrar y colocar en aplicaciones basadas en Windows.</span><span class="sxs-lookup"><span data-stu-id="84d34-118">Keep this in mind as you incorporate drag-and-drop operations into your Windows-based applications.</span></span>  
  
 <span data-ttu-id="84d34-119">Mientras haya una operación de arrastrar en vigor, puede controlar el evento <xref:System.Windows.Forms.Control.QueryContinueDrag>, que "pide permiso" del sistema para continuar con la operación de arrastre.</span><span class="sxs-lookup"><span data-stu-id="84d34-119">While a drag operation is in effect, you can handle the <xref:System.Windows.Forms.Control.QueryContinueDrag> event, which "asks permission" of the system to continue the drag operation.</span></span> <span data-ttu-id="84d34-120">Al controlar este método, también es el momento adecuado para llamar a métodos que afectarán a la operación de arrastre, como expandir un <xref:System.Windows.Forms.TreeNode> en un control de <xref:System.Windows.Forms.TreeView> cuando el cursor se mantiene sobre él.</span><span class="sxs-lookup"><span data-stu-id="84d34-120">When handling this method, it is also the appropriate point for you to call methods that will have an effect on the drag operation, such as expanding a <xref:System.Windows.Forms.TreeNode> in a <xref:System.Windows.Forms.TreeView> control when the cursor hovers over it.</span></span>  
  
## <a name="dropping-data"></a><span data-ttu-id="84d34-121">Colocar datos</span><span class="sxs-lookup"><span data-stu-id="84d34-121">Dropping Data</span></span>  
 <span data-ttu-id="84d34-122">Una vez que haya empezado a arrastrar datos desde una ubicación a un control o Windows Forms, naturalmente deseará colocarlos en algún lugar.</span><span class="sxs-lookup"><span data-stu-id="84d34-122">Once you have begun dragging data from a location on a Windows Form or control, you will naturally want to drop it somewhere.</span></span> <span data-ttu-id="84d34-123">El cursor cambiará cuando cruce una zona de un formulario o control que esté configurada correctamente para la colocación de datos.</span><span class="sxs-lookup"><span data-stu-id="84d34-123">The cursor will change when it crosses an area of a form or control that is correctly configured for dropping data.</span></span> <span data-ttu-id="84d34-124">Cualquier área dentro de un formulario o control de Windows puede realizarse para aceptar los datos colocados estableciendo la propiedad <xref:System.Windows.Forms.Control.AllowDrop%2A> y controlando los eventos <xref:System.Windows.Forms.Control.DragEnter> y <xref:System.Windows.Forms.Control.DragDrop>.</span><span class="sxs-lookup"><span data-stu-id="84d34-124">Any area within a Windows Form or control can be made to accept dropped data by setting the <xref:System.Windows.Forms.Control.AllowDrop%2A> property and handling the <xref:System.Windows.Forms.Control.DragEnter> and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span>  
  
#### <a name="to-perform-a-drop"></a><span data-ttu-id="84d34-125">Para llevar a cabo la operación de colocar</span><span class="sxs-lookup"><span data-stu-id="84d34-125">To perform a drop</span></span>  
  
1. <span data-ttu-id="84d34-126">Establezca la propiedad <xref:System.Windows.Forms.Control.AllowDrop%2A> en true.</span><span class="sxs-lookup"><span data-stu-id="84d34-126">Set the <xref:System.Windows.Forms.Control.AllowDrop%2A> property to true.</span></span>  
  
2. <span data-ttu-id="84d34-127">En el evento `DragEnter` del control donde se producirá la colocación, asegúrese de que los datos que se arrastran son de un tipo aceptable (en este caso, <xref:System.Windows.Forms.Control.Text%2A>).</span><span class="sxs-lookup"><span data-stu-id="84d34-127">In the `DragEnter` event for the control where the drop will occur, ensure that the data being dragged is of an acceptable type (in this case, <xref:System.Windows.Forms.Control.Text%2A>).</span></span> <span data-ttu-id="84d34-128">A continuación, el código establece el efecto que tendrá lugar cuando se produzca la colocación en un valor de la enumeración <xref:System.Windows.Forms.DragDropEffects>.</span><span class="sxs-lookup"><span data-stu-id="84d34-128">The code then sets the effect that will happen when the drop occurs to a value in the <xref:System.Windows.Forms.DragDropEffects> enumeration.</span></span> <span data-ttu-id="84d34-129">Para más información, consulte <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span><span class="sxs-lookup"><span data-stu-id="84d34-129">For more information, see <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span></span>  
  
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
    > <span data-ttu-id="84d34-130">Puede definir su propio <xref:System.Windows.Forms.DataFormats> especificando su propio objeto como <xref:System.Object> parámetro del método <xref:System.Windows.Forms.DataObject.SetData%2A>.</span><span class="sxs-lookup"><span data-stu-id="84d34-130">You can define your own <xref:System.Windows.Forms.DataFormats> by specifying your own object as the <xref:System.Object> parameter of the <xref:System.Windows.Forms.DataObject.SetData%2A> method.</span></span> <span data-ttu-id="84d34-131">Cuando lo haga, asegúrese de que el objeto especificado sea serializable.</span><span class="sxs-lookup"><span data-stu-id="84d34-131">Be sure, when doing this, that the object specified is serializable.</span></span> <span data-ttu-id="84d34-132">Para más información, consulte <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="84d34-132">For more information, see <xref:System.Runtime.Serialization.ISerializable>.</span></span>  
  
3. <span data-ttu-id="84d34-133">En el evento <xref:System.Windows.Forms.Control.DragDrop> del control donde se producirá la eliminación, use el método <xref:System.Windows.Forms.DataObject.GetData%2A> para recuperar los datos que se arrastran.</span><span class="sxs-lookup"><span data-stu-id="84d34-133">In the <xref:System.Windows.Forms.Control.DragDrop> event for the control where the drop will occur, use the <xref:System.Windows.Forms.DataObject.GetData%2A> method to retrieve the data being dragged.</span></span> <span data-ttu-id="84d34-134">Para más información, consulte <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.</span><span class="sxs-lookup"><span data-stu-id="84d34-134">For more information, see <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.</span></span>  
  
     <span data-ttu-id="84d34-135">En el ejemplo siguiente, un control <xref:System.Windows.Forms.TextBox> es el control al que se está arrastrando (donde se producirá la colocación).</span><span class="sxs-lookup"><span data-stu-id="84d34-135">In the example below, a <xref:System.Windows.Forms.TextBox> control is the control being dragged to (where the drop will occur).</span></span> <span data-ttu-id="84d34-136">El código establece la propiedad <xref:System.Windows.Forms.Control.Text%2A> del control <xref:System.Windows.Forms.TextBox> igual a los datos que se arrastran.</span><span class="sxs-lookup"><span data-stu-id="84d34-136">The code sets the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.TextBox> control equal to the data being dragged.</span></span>  
  
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
    > <span data-ttu-id="84d34-137">Además, puede trabajar con la propiedad <xref:System.Windows.Forms.DragEventArgs.KeyState%2A>, de modo que, en función de las teclas presionadas durante la operación de arrastrar y colocar, se produzcan ciertos efectos (por ejemplo, es estándar copiar los datos arrastrados cuando se presiona la tecla CTRL).</span><span class="sxs-lookup"><span data-stu-id="84d34-137">Additionally, you can work with the <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> property, so that, depending on keys depressed during the drag-and-drop operation, certain effects occur (for example, it is standard to copy the dragged data when the CTRL key is pressed).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84d34-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="84d34-138">See also</span></span>

- [<span data-ttu-id="84d34-139">Agregar datos al Portapapeles</span><span class="sxs-lookup"><span data-stu-id="84d34-139">How to: Add Data to the Clipboard</span></span>](how-to-add-data-to-the-clipboard.md)
- [<span data-ttu-id="84d34-140">Recuperar datos del Portapapeles</span><span class="sxs-lookup"><span data-stu-id="84d34-140">How to: Retrieve Data from the Clipboard</span></span>](how-to-retrieve-data-from-the-clipboard.md)
- [<span data-ttu-id="84d34-141">Compatibilidad con las operaciones de arrastrar y colocar y con el Portapapeles</span><span class="sxs-lookup"><span data-stu-id="84d34-141">Drag-and-Drop Operations and Clipboard Support</span></span>](drag-and-drop-operations-and-clipboard-support.md)
