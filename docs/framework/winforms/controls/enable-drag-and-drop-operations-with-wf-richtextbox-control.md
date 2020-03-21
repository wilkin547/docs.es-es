---
title: Habilitar operaciones de arrastrar y soltar con RichTextBox Control
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], text boxes
- drag and drop [Windows Forms], richTextBox control
- text boxes [Windows Forms], drag-and-drop operations
- RichTextBox control [Windows Forms], drag-and-drop operations
ms.assetid: ca167d1c-2014-4cf0-96a0-20598470be3b
ms.openlocfilehash: 27e5c18598552c465ef17f5e58069bc10e401c09
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182350"
---
# <a name="how-to-enable-drag-and-drop-operations-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="df4d4-102">Cómo: Habilitar operaciones de arrastrar y colocar con el control RichTextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="df4d4-102">How to: Enable Drag-and-Drop Operations with the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="df4d4-103">Las operaciones de arrastrar y colocar con el control <xref:System.Windows.Forms.RichTextBox> de formularios Windows Forms se realizan mediante el control de los eventos <xref:System.Windows.Forms.RichTextBox.DragEnter> y <xref:System.Windows.Forms.RichTextBox.DragDrop> .</span><span class="sxs-lookup"><span data-stu-id="df4d4-103">Drag-and-drop operations with the Windows Forms <xref:System.Windows.Forms.RichTextBox> control are done by handling the <xref:System.Windows.Forms.RichTextBox.DragEnter> and <xref:System.Windows.Forms.RichTextBox.DragDrop> events.</span></span> <span data-ttu-id="df4d4-104">Por lo tanto, las operaciones de arrastrar y colocar son extremadamente sencillas con el control <xref:System.Windows.Forms.RichTextBox> .</span><span class="sxs-lookup"><span data-stu-id="df4d4-104">Thus, drag-and-drop operations are extremely simple with the <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
### <a name="to-enable-drag-operations-in-a-richtextbox-control"></a><span data-ttu-id="df4d4-105">Para habilitar las operaciones de arrastre en un control RichTextBox</span><span class="sxs-lookup"><span data-stu-id="df4d4-105">To enable drag operations in a RichTextBox control</span></span>  
  
1. <span data-ttu-id="df4d4-106">Establezca la propiedad <xref:System.Windows.Forms.RichTextBox.AllowDrop%2A> del control <xref:System.Windows.Forms.RichTextBox> en `true`.</span><span class="sxs-lookup"><span data-stu-id="df4d4-106">Set the <xref:System.Windows.Forms.RichTextBox.AllowDrop%2A> property of the <xref:System.Windows.Forms.RichTextBox> control to `true`.</span></span>  
  
2. <span data-ttu-id="df4d4-107">Escriba código en el controlador de eventos del evento <xref:System.Windows.Forms.RichTextBox.DragEnter> .</span><span class="sxs-lookup"><span data-stu-id="df4d4-107">Write code in the event handler of the <xref:System.Windows.Forms.RichTextBox.DragEnter> event.</span></span> <span data-ttu-id="df4d4-108">Use una declaración `if` para asegurarse de que los datos que se arrastran son de un tipo aceptable (en este caso, texto).</span><span class="sxs-lookup"><span data-stu-id="df4d4-108">Use an `if` statement to ensure that the data being dragged is of an acceptable type (in this case, text).</span></span> <span data-ttu-id="df4d4-109">La propiedad <xref:System.Windows.Forms.DragEventArgs.Effect%2A?displayProperty=nameWithType> se puede establecer en cualquier valor de la enumeración <xref:System.Windows.Forms.DragDropEffects> .</span><span class="sxs-lookup"><span data-stu-id="df4d4-109">The <xref:System.Windows.Forms.DragEventArgs.Effect%2A?displayProperty=nameWithType> property can be set to any value of the <xref:System.Windows.Forms.DragDropEffects> enumeration.</span></span>  
  
    ```vb  
    Private Sub RichTextBox1_DragEnter(ByVal sender As Object, _
       ByVal e As System.Windows.Forms.DragEventArgs) _
       Handles RichTextBox1.DragEnter  
       If (e.Data.GetDataPresent(DataFormats.Text)) Then  
          e.Effect = DragDropEffects.Copy  
       Else  
          e.Effect = DragDropEffects.None  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void richTextBox1_DragEnter(object sender,
    System.Windows.Forms.DragEventArgs e)  
    {  
       if (e.Data.GetDataPresent(DataFormats.Text))
          e.Effect = DragDropEffects.Copy;  
       else  
          e.Effect = DragDropEffects.None;  
    }  
    ```  
  
    ```cpp  
    private:  
       void richTextBox1_DragEnter(System::Object ^  sender,  
          System::Windows::Forms::DragEventArgs ^  e)  
       {  
          if (e->Data->GetDataPresent(DataFormats::Text))  
             e->Effect = DragDropEffects::Copy;  
          else  
             e->Effect = DragDropEffects::None;  
       }  
    ```  
  
     <span data-ttu-id="df4d4-110">(Visual C- y Visual C++) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="df4d4-110">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.richTextBox1.DragEnter += new  
        System.Windows.Forms.DragEventHandler  
        (this.richTextBox1_DragEnter);  
    ```  
  
    ```cpp  
    this->richTextBox1->DragEnter += gcnew  
       System::Windows::Forms::DragEventHandler  
       (this, &Form1::richTextBox1_DragEnter);  
    ```  
  
3. <span data-ttu-id="df4d4-111">Escriba código para controlar el evento <xref:System.Windows.Forms.RichTextBox.DragDrop> .</span><span class="sxs-lookup"><span data-stu-id="df4d4-111">Write code to handle the <xref:System.Windows.Forms.RichTextBox.DragDrop> event.</span></span> <span data-ttu-id="df4d4-112">Utilice el método <xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=nameWithType> para recuperar los datos que se están arrastrando.</span><span class="sxs-lookup"><span data-stu-id="df4d4-112">Use the <xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=nameWithType> method to retrieve the data being dragged.</span></span>  
  
     <span data-ttu-id="df4d4-113">En el ejemplo siguiente, el código establece la propiedad <xref:System.Windows.Forms.RichTextBox.Text%2A> del control <xref:System.Windows.Forms.RichTextBox> igual a los datos que se están arrastrando.</span><span class="sxs-lookup"><span data-stu-id="df4d4-113">In the example below, the code sets the <xref:System.Windows.Forms.RichTextBox.Text%2A> property of the <xref:System.Windows.Forms.RichTextBox> control equal to the data being dragged.</span></span> <span data-ttu-id="df4d4-114">Si ya hay texto en el control <xref:System.Windows.Forms.RichTextBox> , el texto arrastrado se inserta en el punto de inserción.</span><span class="sxs-lookup"><span data-stu-id="df4d4-114">If there is already text in the <xref:System.Windows.Forms.RichTextBox> control, the dragged text is inserted at the insertion point.</span></span>  
  
    ```vb  
    Private Sub RichTextBox1_DragDrop(ByVal sender As Object, _
       ByVal e As System.Windows.Forms.DragEventArgs) _
       Handles RichTextBox1.DragDrop  
       Dim i As Int16
       Dim s As String  
  
       ' Get start position to drop the text.  
       i = RichTextBox1.SelectionStart  
       s = RichTextBox1.Text.Substring(i)  
       RichTextBox1.Text = RichTextBox1.Text.Substring(0, i)  
  
       ' Drop the text on to the RichTextBox.  
       RichTextBox1.Text = RichTextBox1.Text + _  
          e.Data.GetData(DataFormats.Text).ToString()  
       RichTextBox1.Text = RichTextBox1.Text + s  
    End Sub  
    ```  
  
    ```csharp  
    private void richTextBox1_DragDrop(object sender,
    System.Windows.Forms.DragEventArgs e)  
    {  
       int i;  
       String s;  
  
       // Get start position to drop the text.  
       i = richTextBox1.SelectionStart;  
       s = richTextBox1.Text.Substring(i);  
       richTextBox1.Text = richTextBox1.Text.Substring(0,i);  
  
       // Drop the text on to the RichTextBox.  
       richTextBox1.Text = richTextBox1.Text +
          e.Data.GetData(DataFormats.Text).ToString();  
       richTextBox1.Text = richTextBox1.Text + s;  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void richTextBox1_DragDrop(System::Object ^  sender,  
          System::Windows::Forms::DragEventArgs ^  e)  
       {  
          int i;  
          String ^s;  
  
       // Get start position to drop the text.  
       i = richTextBox1->SelectionStart;  
       s = richTextBox1->Text->Substring(i);  
       richTextBox1->Text = richTextBox1->Text->Substring(0,i);  
  
       // Drop the text on to the RichTextBox.  
       String ^str = String::Concat(richTextBox1->Text, e->Data  
       ->GetData(DataFormats->Text)->ToString());
       richTextBox1->Text = String::Concat(str, s);  
       }  
    ```  
  
     <span data-ttu-id="df4d4-115">(Visual C- y Visual C++) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="df4d4-115">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.richTextBox1.DragDrop += new  
        System.Windows.Forms.DragEventHandler  
        (this.richTextBox1_DragDrop);  
    ```  
  
    ```cpp  
    this->richTextBox1->DragDrop += gcnew
       System::Windows::Forms::DragEventHandler  
       (this, &Form1::richTextBox1_DragDrop);  
    ```  
  
### <a name="to-test-the-drag-and-drop-functionality-in-your-application"></a><span data-ttu-id="df4d4-116">Para probar la funcionalidad de arrastrar y colocar en la aplicación</span><span class="sxs-lookup"><span data-stu-id="df4d4-116">To test the drag-and-drop functionality in your application</span></span>  
  
1. <span data-ttu-id="df4d4-117">Guarde y compile la aplicación.</span><span class="sxs-lookup"><span data-stu-id="df4d4-117">Save and build your application.</span></span> <span data-ttu-id="df4d4-118">Mientras se esté ejecutando, ejecute WordPad.</span><span class="sxs-lookup"><span data-stu-id="df4d4-118">While it is running, run WordPad.</span></span>  
  
     <span data-ttu-id="df4d4-119">WordPad es un editor de texto instalado por Windows que permite operaciones de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="df4d4-119">WordPad is a text editor installed by Windows that allows drag-and-drop operations.</span></span> <span data-ttu-id="df4d4-120">Para acceder a este, haga clic en el botón **Inicio** , seleccione **Ejecutar**, escriba `WordPad` en el cuadro de texto del cuadro de diálogo **Ejecutar** y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="df4d4-120">It is accessible by clicking the **Start** button, selecting **Run**, typing `WordPad` in the text box of the **Run** dialog box, and then clicking **OK**.</span></span>  
  
2. <span data-ttu-id="df4d4-121">Una vez abierto WordPad, escriba una cadena de texto en esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="df4d4-121">Once WordPad is open, type a string of text in it.</span></span> <span data-ttu-id="df4d4-122">Use el mouse para seleccionar el texto y, después, arrastre el texto seleccionado al control <xref:System.Windows.Forms.RichTextBox> de la aplicación Windows.</span><span class="sxs-lookup"><span data-stu-id="df4d4-122">Using the mouse, select the text, and then drag the selected text over to the <xref:System.Windows.Forms.RichTextBox> control in your Windows application.</span></span>  
  
     <span data-ttu-id="df4d4-123">Observe que, cuando el mouse señala el control <xref:System.Windows.Forms.RichTextBox> (y, por consiguiente, genera el evento <xref:System.Windows.Forms.RichTextBox.DragEnter> ), el cursor cambia y puede colocar el texto seleccionado en el control <xref:System.Windows.Forms.RichTextBox> .</span><span class="sxs-lookup"><span data-stu-id="df4d4-123">Notice that when you point the mouse at the <xref:System.Windows.Forms.RichTextBox> control (and, consequently, raise the <xref:System.Windows.Forms.RichTextBox.DragEnter> event), the mouse pointer changes and you can drop the selected text into the <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
     <span data-ttu-id="df4d4-124">Al soltar el botón del mouse, se quita el texto seleccionado (es decir, se genera el evento <xref:System.Windows.Forms.RichTextBox.DragDrop> ) y se inserta en el control <xref:System.Windows.Forms.RichTextBox> .</span><span class="sxs-lookup"><span data-stu-id="df4d4-124">When you release the mouse button, the selected text is dropped (that is, the <xref:System.Windows.Forms.RichTextBox.DragDrop> event is raised) and is inserted within the <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df4d4-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="df4d4-125">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="df4d4-126">Cómo: Llevar a cabo operaciones de arrastrar y colocar entre aplicaciones</span><span class="sxs-lookup"><span data-stu-id="df4d4-126">How to: Perform Drag-and-Drop Operations Between Applications</span></span>](../advanced/how-to-perform-drag-and-drop-operations-between-applications.md)
- [<span data-ttu-id="df4d4-127">Control RichTextBox</span><span class="sxs-lookup"><span data-stu-id="df4d4-127">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="df4d4-128">Controles que se utilizan en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="df4d4-128">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
