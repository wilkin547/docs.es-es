---
title: 'Tutorial: Llevar a cabo una operación de arrastrar y colocar en formularios Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drag and drop operations
- drag and drop [Windows Forms], Windows Forms
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
ms.openlocfilehash: f7551f28d07c9517865f60af99954eb40e57daa2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59340729"
---
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a><span data-ttu-id="921fc-102">Tutorial: Llevar a cabo una operación de arrastrar y colocar en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="921fc-102">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>
<span data-ttu-id="921fc-103">Para realizar operaciones de arrastrar y colocar en aplicaciones basadas en Windows debe controlar una serie de eventos, sobre todo la <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, y <xref:System.Windows.Forms.Control.DragDrop> eventos.</span><span class="sxs-lookup"><span data-stu-id="921fc-103">To perform drag-and-drop operations within Windows-based applications you must handle a series of events, most notably the <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span> <span data-ttu-id="921fc-104">Trabajando con la información disponible en los argumentos de estos eventos, puede facilitar sin problemas las operaciones de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="921fc-104">By working with the information available in the event arguments of these events, you can easily facilitate drag-and-drop operations.</span></span>  
  
## <a name="dragging-data"></a><span data-ttu-id="921fc-105">Arrastrar datos</span><span class="sxs-lookup"><span data-stu-id="921fc-105">Dragging Data</span></span>  
 <span data-ttu-id="921fc-106">Todas las operaciones de arrastrar y colocar comienzan con arrastrar.</span><span class="sxs-lookup"><span data-stu-id="921fc-106">All drag-and-drop operations begin with dragging.</span></span> <span data-ttu-id="921fc-107">La funcionalidad para habilitar los datos se recopilan cuando comienza a arrastrar se implementa en el <xref:System.Windows.Forms.Control.DoDragDrop%2A> método.</span><span class="sxs-lookup"><span data-stu-id="921fc-107">The functionality to enable data to be collected when dragging begins is implemented in the <xref:System.Windows.Forms.Control.DoDragDrop%2A> method.</span></span>  
  
 <span data-ttu-id="921fc-108">En el ejemplo siguiente, la <xref:System.Windows.Forms.Control.MouseDown> eventos se usan para iniciar la operación de arrastre porque es más intuitivo (la mayoría de las acciones de arrastrar y colocar empiezan con el botón del mouse cuando se presiona).</span><span class="sxs-lookup"><span data-stu-id="921fc-108">In the following example, the <xref:System.Windows.Forms.Control.MouseDown> event is used to start the drag operation because it is the most intuitive (most drag-and-drop actions begin with the mouse button being depressed).</span></span> <span data-ttu-id="921fc-109">Sin embargo, recuerde que podría utilizarse cualquier evento para iniciar un procedimiento de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="921fc-109">However, remember that any event could be used to initiate a drag-and-drop procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="921fc-110">Determinados controles tienen eventos personalizados específicos para la acción de arrastrar.</span><span class="sxs-lookup"><span data-stu-id="921fc-110">Certain controls have custom drag-specific events.</span></span> <span data-ttu-id="921fc-111">El <xref:System.Windows.Forms.ListView> y <xref:System.Windows.Forms.TreeView> controles, por ejemplo, tienen un <xref:System.Windows.Forms.TreeView.ItemDrag> eventos.</span><span class="sxs-lookup"><span data-stu-id="921fc-111">The <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls, for example, have an <xref:System.Windows.Forms.TreeView.ItemDrag> event.</span></span>  
  
#### <a name="to-start-a-drag-operation"></a><span data-ttu-id="921fc-112">Para iniciar una operación de arrastrar</span><span class="sxs-lookup"><span data-stu-id="921fc-112">To start a drag operation</span></span>  
  
1. <span data-ttu-id="921fc-113">En el <xref:System.Windows.Forms.Control.MouseDown> eventos del control donde se iniciará la operación de arrastrar, utilice el `DoDragDrop` tendrán método para establecer los datos que se arrastran y el efecto permitido.</span><span class="sxs-lookup"><span data-stu-id="921fc-113">In the <xref:System.Windows.Forms.Control.MouseDown> event for the control where the drag will begin, use the `DoDragDrop` method to set the data to be dragged and the allowed effect dragging will have.</span></span> <span data-ttu-id="921fc-114">Para obtener más información, vea <xref:System.Windows.Forms.DragEventArgs.Data%2A> y <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span><span class="sxs-lookup"><span data-stu-id="921fc-114">For more information, see <xref:System.Windows.Forms.DragEventArgs.Data%2A> and <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span></span>  
  
     <span data-ttu-id="921fc-115">En el ejemplo siguiente se muestra cómo iniciar una operación de arrastrar.</span><span class="sxs-lookup"><span data-stu-id="921fc-115">The following example shows how to initiate a drag operation.</span></span> <span data-ttu-id="921fc-116">El control donde comienza la operación de arrastrar es un <xref:System.Windows.Forms.Button> control, los datos que se arrastran es la cadena que representa el <xref:System.Windows.Forms.Control.Text%2A> propiedad de la <xref:System.Windows.Forms.Button> control y los efectos permitidos son copiar o mover.</span><span class="sxs-lookup"><span data-stu-id="921fc-116">The control where the drag begins is a <xref:System.Windows.Forms.Button> control, the data being dragged is the string representing the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control, and the allowed effects are either copying or moving.</span></span>  
  
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
    >  <span data-ttu-id="921fc-117">Se puede usar cualquier dato como parámetro en el `DoDragDrop` método; en el ejemplo anterior, el <xref:System.Windows.Forms.Control.Text%2A> propiedad de la <xref:System.Windows.Forms.Button> se usó el control (en lugar de codificar de forma rígida un valor o recuperar datos de un conjunto de datos) porque la propiedad estaba relacionada con el ubicación que se arrastran desde (el <xref:System.Windows.Forms.Button> control).</span><span class="sxs-lookup"><span data-stu-id="921fc-117">Any data can be used as a parameter in the `DoDragDrop` method; in the example above, the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control was used (rather than hard-coding a value or retrieving data from a dataset) because the property was related to the location being dragged from (the <xref:System.Windows.Forms.Button> control).</span></span> <span data-ttu-id="921fc-118">Téngalo en cuenta cuando incorpore operaciones de arrastrar y colocar en aplicaciones basadas en Windows.</span><span class="sxs-lookup"><span data-stu-id="921fc-118">Keep this in mind as you incorporate drag-and-drop operations into your Windows-based applications.</span></span>  
  
 <span data-ttu-id="921fc-119">Mientras una operación de arrastrar está en vigor, se puede controlar la <xref:System.Windows.Forms.Control.QueryContinueDrag> eventos, que "pide permiso" del sistema para continuar la operación de arrastre.</span><span class="sxs-lookup"><span data-stu-id="921fc-119">While a drag operation is in effect, you can handle the <xref:System.Windows.Forms.Control.QueryContinueDrag> event, which "asks permission" of the system to continue the drag operation.</span></span> <span data-ttu-id="921fc-120">Este método de control, es el punto adecuado para llamar a métodos que tengan un efecto en la operación de arrastrar, como expandir un <xref:System.Windows.Forms.TreeNode> en un <xref:System.Windows.Forms.TreeView> controlar cuando el cursor se desplaza sobre él.</span><span class="sxs-lookup"><span data-stu-id="921fc-120">When handling this method, it is also the appropriate point for you to call methods that will have an effect on the drag operation, such as expanding a <xref:System.Windows.Forms.TreeNode> in a <xref:System.Windows.Forms.TreeView> control when the cursor hovers over it.</span></span>  
  
## <a name="dropping-data"></a><span data-ttu-id="921fc-121">Colocar datos</span><span class="sxs-lookup"><span data-stu-id="921fc-121">Dropping Data</span></span>  
 <span data-ttu-id="921fc-122">Una vez que haya empezado a arrastrar datos desde una ubicación a un control o Windows Forms, naturalmente deseará colocarlos en algún lugar.</span><span class="sxs-lookup"><span data-stu-id="921fc-122">Once you have begun dragging data from a location on a Windows Form or control, you will naturally want to drop it somewhere.</span></span> <span data-ttu-id="921fc-123">El cursor cambiará cuando cruce una zona de un formulario o control que esté configurada correctamente para la colocación de datos.</span><span class="sxs-lookup"><span data-stu-id="921fc-123">The cursor will change when it crosses an area of a form or control that is correctly configured for dropping data.</span></span> <span data-ttu-id="921fc-124">¿Se pueden hacer cualquier zona dentro de un formulario de Windows o un control para aceptar datos colocados estableciendo el <xref:System.Windows.Forms.Control.AllowDrop%2A> propiedad y el control de la <xref:System.Windows.Forms.Control.DragEnter> y <xref:System.Windows.Forms.Control.DragDrop> eventos.</span><span class="sxs-lookup"><span data-stu-id="921fc-124">Any area within a Windows Form or control can be made to accept dropped data by setting the <xref:System.Windows.Forms.Control.AllowDrop%2A> property and handling the <xref:System.Windows.Forms.Control.DragEnter> and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span>  
  
#### <a name="to-perform-a-drop"></a><span data-ttu-id="921fc-125">Para llevar a cabo la operación de colocar</span><span class="sxs-lookup"><span data-stu-id="921fc-125">To perform a drop</span></span>  
  
1. <span data-ttu-id="921fc-126">Establecer el <xref:System.Windows.Forms.Control.AllowDrop%2A> propiedad en true.</span><span class="sxs-lookup"><span data-stu-id="921fc-126">Set the <xref:System.Windows.Forms.Control.AllowDrop%2A> property to true.</span></span>  
  
2. <span data-ttu-id="921fc-127">En el `DragEnter` eventos para el control donde tendrá lugar la operación de colocar, asegúrese de que los datos que se arrastran son de un tipo aceptable (en este caso, <xref:System.Windows.Forms.Control.Text%2A>).</span><span class="sxs-lookup"><span data-stu-id="921fc-127">In the `DragEnter` event for the control where the drop will occur, ensure that the data being dragged is of an acceptable type (in this case, <xref:System.Windows.Forms.Control.Text%2A>).</span></span> <span data-ttu-id="921fc-128">El código, a continuación, Establece el efecto que tendrá lugar cuando se produce la entrega a un valor en el <xref:System.Windows.Forms.DragDropEffects> enumeración.</span><span class="sxs-lookup"><span data-stu-id="921fc-128">The code then sets the effect that will happen when the drop occurs to a value in the <xref:System.Windows.Forms.DragDropEffects> enumeration.</span></span> <span data-ttu-id="921fc-129">Para obtener más información, consulta <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span><span class="sxs-lookup"><span data-stu-id="921fc-129">For more information, see <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span></span>  
  
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
    >  <span data-ttu-id="921fc-130">Puede definir sus propios <xref:System.Windows.Forms.DataFormats> especificando su propio objeto como el <xref:System.Object> parámetro de la <xref:System.Windows.Forms.DataObject.SetData%2A> método.</span><span class="sxs-lookup"><span data-stu-id="921fc-130">You can define your own <xref:System.Windows.Forms.DataFormats> by specifying your own object as the <xref:System.Object> parameter of the <xref:System.Windows.Forms.DataObject.SetData%2A> method.</span></span> <span data-ttu-id="921fc-131">Cuando lo haga, asegúrese de que el objeto especificado sea serializable.</span><span class="sxs-lookup"><span data-stu-id="921fc-131">Be sure, when doing this, that the object specified is serializable.</span></span> <span data-ttu-id="921fc-132">Para obtener más información, consulta <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="921fc-132">For more information, see <xref:System.Runtime.Serialization.ISerializable>.</span></span>  
  
3. <span data-ttu-id="921fc-133">En el <xref:System.Windows.Forms.Control.DragDrop> eventos del control donde tendrá lugar la operación de colocar, utilice el <xref:System.Windows.Forms.DataObject.GetData%2A> método para recuperar los datos que se está arrastrando.</span><span class="sxs-lookup"><span data-stu-id="921fc-133">In the <xref:System.Windows.Forms.Control.DragDrop> event for the control where the drop will occur, use the <xref:System.Windows.Forms.DataObject.GetData%2A> method to retrieve the data being dragged.</span></span> <span data-ttu-id="921fc-134">Para obtener más información, consulta <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.</span><span class="sxs-lookup"><span data-stu-id="921fc-134">For more information, see <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.</span></span>  
  
     <span data-ttu-id="921fc-135">En el ejemplo siguiente, un <xref:System.Windows.Forms.TextBox> control es el control que se está arrastrando (donde tendrá lugar la operación de colocar).</span><span class="sxs-lookup"><span data-stu-id="921fc-135">In the example below, a <xref:System.Windows.Forms.TextBox> control is the control being dragged to (where the drop will occur).</span></span> <span data-ttu-id="921fc-136">El código establece la <xref:System.Windows.Forms.Control.Text%2A> propiedad de la <xref:System.Windows.Forms.TextBox> controlar igual a los datos que se está arrastrando.</span><span class="sxs-lookup"><span data-stu-id="921fc-136">The code sets the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.TextBox> control equal to the data being dragged.</span></span>  
  
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
    >  <span data-ttu-id="921fc-137">Además, puede trabajar con el <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> propiedad, por lo que, en función de las teclas presionadas durante la operación de arrastrar y colocar, tengan lugar ciertos efectos (por ejemplo, es estándar copiar los datos arrastrados cuando se presiona la tecla CTRL).</span><span class="sxs-lookup"><span data-stu-id="921fc-137">Additionally, you can work with the <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> property, so that, depending on keys depressed during the drag-and-drop operation, certain effects occur (for example, it is standard to copy the dragged data when the CTRL key is pressed).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="921fc-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="921fc-138">See also</span></span>

- [<span data-ttu-id="921fc-139">Cómo: Agregar datos al Portapapeles</span><span class="sxs-lookup"><span data-stu-id="921fc-139">How to: Add Data to the Clipboard</span></span>](how-to-add-data-to-the-clipboard.md)
- [<span data-ttu-id="921fc-140">Cómo: Recuperar datos del Portapapeles</span><span class="sxs-lookup"><span data-stu-id="921fc-140">How to: Retrieve Data from the Clipboard</span></span>](how-to-retrieve-data-from-the-clipboard.md)
- [<span data-ttu-id="921fc-141">Compatibilidad con las operaciones de arrastrar y colocar y con el Portapapeles</span><span class="sxs-lookup"><span data-stu-id="921fc-141">Drag-and-Drop Operations and Clipboard Support</span></span>](drag-and-drop-operations-and-clipboard-support.md)
