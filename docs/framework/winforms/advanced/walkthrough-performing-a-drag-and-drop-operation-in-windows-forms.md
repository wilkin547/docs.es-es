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
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a><span data-ttu-id="32c51-103">Tutorial: Llevar a cabo una operación de arrastrar y colocar en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="32c51-103">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>
<span data-ttu-id="32c51-104">Para realizar operaciones de arrastrar y colocar en aplicaciones basadas en Windows, debe controlar una serie de eventos, especialmente los <xref:System.Windows.Forms.Control.DragEnter> <xref:System.Windows.Forms.Control.DragLeave> eventos, y <xref:System.Windows.Forms.Control.DragDrop> .</span><span class="sxs-lookup"><span data-stu-id="32c51-104">To perform drag-and-drop operations within Windows-based applications you must handle a series of events, most notably the <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span> <span data-ttu-id="32c51-105">Trabajando con la información disponible en los argumentos de estos eventos, puede facilitar sin problemas las operaciones de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="32c51-105">By working with the information available in the event arguments of these events, you can easily facilitate drag-and-drop operations.</span></span>  
  
## <a name="dragging-data"></a><span data-ttu-id="32c51-106">Arrastrar datos</span><span class="sxs-lookup"><span data-stu-id="32c51-106">Dragging Data</span></span>  
 <span data-ttu-id="32c51-107">Todas las operaciones de arrastrar y colocar comienzan con arrastrar.</span><span class="sxs-lookup"><span data-stu-id="32c51-107">All drag-and-drop operations begin with dragging.</span></span> <span data-ttu-id="32c51-108">La funcionalidad para habilitar la recopilación de datos al arrastrar comienza se implementa en el <xref:System.Windows.Forms.Control.DoDragDrop%2A> método.</span><span class="sxs-lookup"><span data-stu-id="32c51-108">The functionality to enable data to be collected when dragging begins is implemented in the <xref:System.Windows.Forms.Control.DoDragDrop%2A> method.</span></span>  
  
 <span data-ttu-id="32c51-109">En el ejemplo siguiente, el <xref:System.Windows.Forms.Control.MouseDown> evento se utiliza para iniciar la operación de arrastre porque es la más intuitiva (la mayoría de las acciones de arrastrar y colocar comienzan con el botón del mouse que se presiona).</span><span class="sxs-lookup"><span data-stu-id="32c51-109">In the following example, the <xref:System.Windows.Forms.Control.MouseDown> event is used to start the drag operation because it is the most intuitive (most drag-and-drop actions begin with the mouse button being depressed).</span></span> <span data-ttu-id="32c51-110">Sin embargo, recuerde que podría utilizarse cualquier evento para iniciar un procedimiento de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="32c51-110">However, remember that any event could be used to initiate a drag-and-drop procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="32c51-111">Determinados controles tienen eventos personalizados específicos para la acción de arrastrar.</span><span class="sxs-lookup"><span data-stu-id="32c51-111">Certain controls have custom drag-specific events.</span></span> <span data-ttu-id="32c51-112">Los <xref:System.Windows.Forms.ListView> <xref:System.Windows.Forms.TreeView> controles y, por ejemplo, tienen un <xref:System.Windows.Forms.TreeView.ItemDrag> evento.</span><span class="sxs-lookup"><span data-stu-id="32c51-112">The <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls, for example, have an <xref:System.Windows.Forms.TreeView.ItemDrag> event.</span></span>  
  
#### <a name="to-start-a-drag-operation"></a><span data-ttu-id="32c51-113">Para iniciar una operación de arrastrar</span><span class="sxs-lookup"><span data-stu-id="32c51-113">To start a drag operation</span></span>  
  
1. <span data-ttu-id="32c51-114">En el <xref:System.Windows.Forms.Control.MouseDown> caso del control donde se iniciará el arrastre, use el `DoDragDrop` método para establecer los datos que se van a arrastrar y el efecto permitido que se arrastra tendrá.</span><span class="sxs-lookup"><span data-stu-id="32c51-114">In the <xref:System.Windows.Forms.Control.MouseDown> event for the control where the drag will begin, use the `DoDragDrop` method to set the data to be dragged and the allowed effect dragging will have.</span></span> <span data-ttu-id="32c51-115">Para obtener más información, vea <xref:System.Windows.Forms.DragEventArgs.Data%2A> y <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span><span class="sxs-lookup"><span data-stu-id="32c51-115">For more information, see <xref:System.Windows.Forms.DragEventArgs.Data%2A> and <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span></span>  
  
     <span data-ttu-id="32c51-116">En el ejemplo siguiente se muestra cómo iniciar una operación de arrastrar.</span><span class="sxs-lookup"><span data-stu-id="32c51-116">The following example shows how to initiate a drag operation.</span></span> <span data-ttu-id="32c51-117">El control donde comienza el arrastre es un <xref:System.Windows.Forms.Button> control, los datos que se arrastran son la cadena que representa la <xref:System.Windows.Forms.Control.Text%2A> propiedad del <xref:System.Windows.Forms.Button> control y los efectos permitidos son copiar o mover.</span><span class="sxs-lookup"><span data-stu-id="32c51-117">The control where the drag begins is a <xref:System.Windows.Forms.Button> control, the data being dragged is the string representing the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control, and the allowed effects are either copying or moving.</span></span>  
  
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
    > <span data-ttu-id="32c51-118">Los datos se pueden usar como parámetros en el `DoDragDrop` método; en el ejemplo anterior, <xref:System.Windows.Forms.Control.Text%2A> se usó la propiedad del <xref:System.Windows.Forms.Button> control (en lugar de codificar de forma rígida un valor o recuperar datos de un conjunto de datos) porque la propiedad estaba relacionada con la ubicación desde la que se arrastró (el <xref:System.Windows.Forms.Button> control).</span><span class="sxs-lookup"><span data-stu-id="32c51-118">Any data can be used as a parameter in the `DoDragDrop` method; in the example above, the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control was used (rather than hard-coding a value or retrieving data from a dataset) because the property was related to the location being dragged from (the <xref:System.Windows.Forms.Button> control).</span></span> <span data-ttu-id="32c51-119">Téngalo en cuenta cuando incorpore operaciones de arrastrar y colocar en aplicaciones basadas en Windows.</span><span class="sxs-lookup"><span data-stu-id="32c51-119">Keep this in mind as you incorporate drag-and-drop operations into your Windows-based applications.</span></span>  
  
 <span data-ttu-id="32c51-120">Mientras haya una operación de arrastrar en vigor, puede controlar el <xref:System.Windows.Forms.Control.QueryContinueDrag> evento, que "pide permiso" del sistema para continuar con la operación de arrastre.</span><span class="sxs-lookup"><span data-stu-id="32c51-120">While a drag operation is in effect, you can handle the <xref:System.Windows.Forms.Control.QueryContinueDrag> event, which "asks permission" of the system to continue the drag operation.</span></span> <span data-ttu-id="32c51-121">Al controlar este método, también es el momento adecuado para llamar a métodos que afectarán a la operación de arrastre, como expandir un <xref:System.Windows.Forms.TreeNode> control en un <xref:System.Windows.Forms.TreeView> control cuando el cursor se mantiene sobre él.</span><span class="sxs-lookup"><span data-stu-id="32c51-121">When handling this method, it is also the appropriate point for you to call methods that will have an effect on the drag operation, such as expanding a <xref:System.Windows.Forms.TreeNode> in a <xref:System.Windows.Forms.TreeView> control when the cursor hovers over it.</span></span>  
  
## <a name="dropping-data"></a><span data-ttu-id="32c51-122">Colocar datos</span><span class="sxs-lookup"><span data-stu-id="32c51-122">Dropping Data</span></span>  
 <span data-ttu-id="32c51-123">Una vez que haya empezado a arrastrar datos desde una ubicación a un control o Windows Forms, naturalmente deseará colocarlos en algún lugar.</span><span class="sxs-lookup"><span data-stu-id="32c51-123">Once you have begun dragging data from a location on a Windows Form or control, you will naturally want to drop it somewhere.</span></span> <span data-ttu-id="32c51-124">El cursor cambiará cuando cruce una zona de un formulario o control que esté configurada correctamente para la colocación de datos.</span><span class="sxs-lookup"><span data-stu-id="32c51-124">The cursor will change when it crosses an area of a form or control that is correctly configured for dropping data.</span></span> <span data-ttu-id="32c51-125">Cualquier área dentro de un formulario o un control de Windows puede realizarse para aceptar los datos colocados estableciendo la <xref:System.Windows.Forms.Control.AllowDrop%2A> propiedad y controlando los <xref:System.Windows.Forms.Control.DragEnter> <xref:System.Windows.Forms.Control.DragDrop> eventos y.</span><span class="sxs-lookup"><span data-stu-id="32c51-125">Any area within a Windows Form or control can be made to accept dropped data by setting the <xref:System.Windows.Forms.Control.AllowDrop%2A> property and handling the <xref:System.Windows.Forms.Control.DragEnter> and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span>  
  
#### <a name="to-perform-a-drop"></a><span data-ttu-id="32c51-126">Para llevar a cabo la operación de colocar</span><span class="sxs-lookup"><span data-stu-id="32c51-126">To perform a drop</span></span>  
  
1. <span data-ttu-id="32c51-127">Establezca la <xref:System.Windows.Forms.Control.AllowDrop%2A> propiedad en true.</span><span class="sxs-lookup"><span data-stu-id="32c51-127">Set the <xref:System.Windows.Forms.Control.AllowDrop%2A> property to true.</span></span>  
  
2. <span data-ttu-id="32c51-128">En el `DragEnter` caso del control donde se producirá la colocación, asegúrese de que los datos que se arrastran son de un tipo aceptable (en este caso, <xref:System.Windows.Forms.Control.Text%2A> ).</span><span class="sxs-lookup"><span data-stu-id="32c51-128">In the `DragEnter` event for the control where the drop will occur, ensure that the data being dragged is of an acceptable type (in this case, <xref:System.Windows.Forms.Control.Text%2A>).</span></span> <span data-ttu-id="32c51-129">A continuación, el código establece el efecto que tendrá lugar cuando se produzca la colocación en un valor de la <xref:System.Windows.Forms.DragDropEffects> enumeración.</span><span class="sxs-lookup"><span data-stu-id="32c51-129">The code then sets the effect that will happen when the drop occurs to a value in the <xref:System.Windows.Forms.DragDropEffects> enumeration.</span></span> <span data-ttu-id="32c51-130">Para más información, consulte <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span><span class="sxs-lookup"><span data-stu-id="32c51-130">For more information, see <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span></span>  
  
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
    > <span data-ttu-id="32c51-131">Puede definir su propia <xref:System.Windows.Forms.DataFormats> especificando su propio objeto como el <xref:System.Object> parámetro del <xref:System.Windows.Forms.DataObject.SetData%2A> método.</span><span class="sxs-lookup"><span data-stu-id="32c51-131">You can define your own <xref:System.Windows.Forms.DataFormats> by specifying your own object as the <xref:System.Object> parameter of the <xref:System.Windows.Forms.DataObject.SetData%2A> method.</span></span> <span data-ttu-id="32c51-132">Cuando lo haga, asegúrese de que el objeto especificado sea serializable.</span><span class="sxs-lookup"><span data-stu-id="32c51-132">Be sure, when doing this, that the object specified is serializable.</span></span> <span data-ttu-id="32c51-133">Para más información, consulte <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="32c51-133">For more information, see <xref:System.Runtime.Serialization.ISerializable>.</span></span>  
  
3. <span data-ttu-id="32c51-134">En el <xref:System.Windows.Forms.Control.DragDrop> caso del control donde se producirá la colocación, use el <xref:System.Windows.Forms.DataObject.GetData%2A> método para recuperar los datos que se arrastran.</span><span class="sxs-lookup"><span data-stu-id="32c51-134">In the <xref:System.Windows.Forms.Control.DragDrop> event for the control where the drop will occur, use the <xref:System.Windows.Forms.DataObject.GetData%2A> method to retrieve the data being dragged.</span></span> <span data-ttu-id="32c51-135">Para más información, consulte <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.</span><span class="sxs-lookup"><span data-stu-id="32c51-135">For more information, see <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.</span></span>  
  
     <span data-ttu-id="32c51-136">En el ejemplo siguiente, un <xref:System.Windows.Forms.TextBox> control es el control al que se está arrastrando (donde se producirá la colocación).</span><span class="sxs-lookup"><span data-stu-id="32c51-136">In the example below, a <xref:System.Windows.Forms.TextBox> control is the control being dragged to (where the drop will occur).</span></span> <span data-ttu-id="32c51-137">El código establece la <xref:System.Windows.Forms.Control.Text%2A> propiedad del <xref:System.Windows.Forms.TextBox> control igual a los datos que se arrastran.</span><span class="sxs-lookup"><span data-stu-id="32c51-137">The code sets the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.TextBox> control equal to the data being dragged.</span></span>  
  
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
    > <span data-ttu-id="32c51-138">Además, puede trabajar con la <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> propiedad, de modo que, en función de las teclas presionadas durante la operación de arrastrar y colocar, se produzcan ciertos efectos (por ejemplo, es estándar copiar los datos arrastrados cuando se presiona la tecla Ctrl).</span><span class="sxs-lookup"><span data-stu-id="32c51-138">Additionally, you can work with the <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> property, so that, depending on keys depressed during the drag-and-drop operation, certain effects occur (for example, it is standard to copy the dragged data when the CTRL key is pressed).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32c51-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="32c51-139">See also</span></span>

- [<span data-ttu-id="32c51-140">Procedimiento para agregar datos al Portapapeles</span><span class="sxs-lookup"><span data-stu-id="32c51-140">How to: Add Data to the Clipboard</span></span>](how-to-add-data-to-the-clipboard.md)
- [<span data-ttu-id="32c51-141">Procedimiento para recuperar datos del Portapapeles</span><span class="sxs-lookup"><span data-stu-id="32c51-141">How to: Retrieve Data from the Clipboard</span></span>](how-to-retrieve-data-from-the-clipboard.md)
- [<span data-ttu-id="32c51-142">Compatibilidad con las operaciones de arrastrar y colocar y con el Portapapeles</span><span class="sxs-lookup"><span data-stu-id="32c51-142">Drag-and-Drop Operations and Clipboard Support</span></span>](drag-and-drop-operations-and-clipboard-support.md)
