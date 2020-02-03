---
title: Seleccionar texto en el control TextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], selecting text programmatically
- text boxes [Windows Forms], selecting text programmatically
- text [Windows Forms], selecting in text boxes programmatically
ms.assetid: 8c591546-6a01-45c7-8e03-f78431f903b1
ms.openlocfilehash: 8a32e40f14ddae6f8ddcaa6d62337329df6fde26
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745312"
---
# <a name="how-to-select-text-in-the-windows-forms-textbox-control"></a><span data-ttu-id="4d618-102">Cómo: Seleccionar texto en el control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4d618-102">How to: Select Text in the Windows Forms TextBox Control</span></span>
<span data-ttu-id="4d618-103">Puede seleccionar texto mediante programación en el control Windows Forms <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="4d618-103">You can select text programmatically in the Windows Forms <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="4d618-104">Por ejemplo, si crea una función que busca en el texto una cadena determinada, puede seleccionar el texto para alertar visualmente al lector de la posición de la cadena encontrada.</span><span class="sxs-lookup"><span data-stu-id="4d618-104">For example, if you create a function that searches text for a particular string, you can select the text to visually alert the reader of the found string's position.</span></span>  
  
### <a name="to-select-text-programmatically"></a><span data-ttu-id="4d618-105">Para seleccionar texto mediante programación</span><span class="sxs-lookup"><span data-stu-id="4d618-105">To select text programmatically</span></span>  
  
1. <span data-ttu-id="4d618-106">Establezca la propiedad <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> en el principio del texto que desea seleccionar.</span><span class="sxs-lookup"><span data-stu-id="4d618-106">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property to the beginning of the text you want to select.</span></span>  
  
     <span data-ttu-id="4d618-107">La propiedad <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> es un número que indica el punto de inserción dentro de la cadena de texto, donde 0 es la posición más a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="4d618-107">The <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property is a number that indicates the insertion point within the string of text, with 0 being the left-most position.</span></span> <span data-ttu-id="4d618-108">Si la propiedad <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> está establecida en un valor igual o mayor que el número de caracteres del cuadro de texto, el punto de inserción se coloca después del último carácter.</span><span class="sxs-lookup"><span data-stu-id="4d618-108">If the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property is set to a value equal to or greater than the number of characters in the text box, the insertion point is placed after the last character.</span></span>  
  
2. <span data-ttu-id="4d618-109">Establezca la propiedad <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> en la longitud del texto que desea seleccionar.</span><span class="sxs-lookup"><span data-stu-id="4d618-109">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property to the length of the text you want to select.</span></span>  
  
     <span data-ttu-id="4d618-110">La propiedad <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> es un valor numérico que establece el ancho del punto de inserción.</span><span class="sxs-lookup"><span data-stu-id="4d618-110">The <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property is a numeric value that sets the width of the insertion point.</span></span> <span data-ttu-id="4d618-111">Al establecer el <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> en un número mayor que 0, se selecciona ese número de caracteres, empezando por el punto de inserción actual.</span><span class="sxs-lookup"><span data-stu-id="4d618-111">Setting the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> to a number greater than 0 causes that number of characters to be selected, starting from the current insertion point.</span></span>  
  
3. <span data-ttu-id="4d618-112">Opta Acceder al texto seleccionado a través de la propiedad <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A>.</span><span class="sxs-lookup"><span data-stu-id="4d618-112">(Optional) Access the selected text through the <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> property.</span></span>  
  
     <span data-ttu-id="4d618-113">El código siguiente selecciona el contenido de un cuadro de texto cuando se produce el evento <xref:System.Windows.Forms.Control.Enter> del control.</span><span class="sxs-lookup"><span data-stu-id="4d618-113">The code below selects the contents of a text box when the control's <xref:System.Windows.Forms.Control.Enter> event occurs.</span></span> <span data-ttu-id="4d618-114">En este ejemplo se comprueba si el cuadro de texto tiene un valor para la propiedad <xref:System.Windows.Forms.TextBox.Text%2A> que no es `null` o una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="4d618-114">This example checks if the text box has a value for the <xref:System.Windows.Forms.TextBox.Text%2A> property that is not `null` or an empty string.</span></span> <span data-ttu-id="4d618-115">Cuando el cuadro de texto recibe el foco, se selecciona el texto actual en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="4d618-115">When the text box receives the focus, the current text in the text box is selected.</span></span> <span data-ttu-id="4d618-116">El controlador de eventos `TextBox1_Enter` debe estar enlazado al control; para obtener más información, vea [Cómo: crear controladores de eventos en tiempo de ejecución para Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="4d618-116">The `TextBox1_Enter` event handler must be bound to the control; for more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
     <span data-ttu-id="4d618-117">Para probar este ejemplo, presione la tecla TAB hasta que el cuadro de texto tenga el foco.</span><span class="sxs-lookup"><span data-stu-id="4d618-117">To test this example, press the Tab key until the text box has the focus.</span></span> <span data-ttu-id="4d618-118">Si hace clic en el cuadro de texto, se anula la selección del texto.</span><span class="sxs-lookup"><span data-stu-id="4d618-118">If you click in the text box, the text is unselected.</span></span>  
  
    ```vb  
    Private Sub TextBox1_Enter(ByVal sender As Object, ByVal e As System.EventArgs) Handles TextBox1.Enter  
       If (Not String.IsNullOrEmpty(TextBox1.Text)) Then  
          TextBox1.SelectionStart = 0  
          TextBox1.SelectionLength = TextBox1.Text.Length  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_Enter(object sender, System.EventArgs e){  
       if (!String.IsNullOrEmpty(textBox1.Text))  
       {  
          textBox1.SelectionStart = 0;  
          textBox1.SelectionLength = textBox1.Text.Length;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void textBox1_Enter(System::Object ^ sender,  
          System::EventArgs ^ e) {  
       if (!System::String::IsNullOrEmpty(textBox1->Text))  
       {  
          textBox1->SelectionStart = 0;  
          textBox1->SelectionLength = textBox1->Text->Length;  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4d618-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4d618-119">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="4d618-120">Información general sobre el control TextBox</span><span class="sxs-lookup"><span data-stu-id="4d618-120">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="4d618-121">Controlar el punto de inserción en un control TextBox de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4d618-121">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="4d618-122">Crear un cuadro de texto de contraseña con el control TextBox de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4d618-122">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="4d618-123">Crear un cuadro de texto de sólo lectura</span><span class="sxs-lookup"><span data-stu-id="4d618-123">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="4d618-124">Insertar comillas en una cadena</span><span class="sxs-lookup"><span data-stu-id="4d618-124">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="4d618-125">Ver múltiples líneas en el control TextBox de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4d618-125">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="4d618-126">TextBox (control)</span><span class="sxs-lookup"><span data-stu-id="4d618-126">TextBox Control</span></span>](textbox-control-windows-forms.md)
