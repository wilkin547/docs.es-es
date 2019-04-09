---
title: Filtrar para seleccionar texto en el control TextBox de formularios Windows Forms
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
ms.openlocfilehash: f96ac69f16eefb5bf4a0625ff83e207c289a105b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59111441"
---
# <a name="how-to-select-text-in-the-windows-forms-textbox-control"></a><span data-ttu-id="4c6fa-102">Filtrar para seleccionar texto en el control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4c6fa-102">How to: Select Text in the Windows Forms TextBox Control</span></span>
<span data-ttu-id="4c6fa-103">Puede seleccionar texto mediante programación en los formularios de Windows <xref:System.Windows.Forms.TextBox> control.</span><span class="sxs-lookup"><span data-stu-id="4c6fa-103">You can select text programmatically in the Windows Forms <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="4c6fa-104">Por ejemplo, si crea una función que se busca el texto de una cadena concreta, puede seleccionar el texto para alertar visualmente al usuario de la posición de la cadena encontrada.</span><span class="sxs-lookup"><span data-stu-id="4c6fa-104">For example, if you create a function that searches text for a particular string, you can select the text to visually alert the reader of the found string's position.</span></span>  
  
### <a name="to-select-text-programmatically"></a><span data-ttu-id="4c6fa-105">Para seleccionar texto mediante programación</span><span class="sxs-lookup"><span data-stu-id="4c6fa-105">To select text programmatically</span></span>  
  
1.  <span data-ttu-id="4c6fa-106">Establecer el <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> propiedad al principio del texto que desea seleccionar.</span><span class="sxs-lookup"><span data-stu-id="4c6fa-106">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property to the beginning of the text you want to select.</span></span>  
  
     <span data-ttu-id="4c6fa-107">El <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> propiedad es un número que indica el punto de inserción en la cadena de texto, siendo 0 la posición más a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="4c6fa-107">The <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property is a number that indicates the insertion point within the string of text, with 0 being the left-most position.</span></span> <span data-ttu-id="4c6fa-108">Si el <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> propiedad se establece en un valor igual o mayor que el número de caracteres en el cuadro de texto, el punto de inserción se coloca después del último carácter.</span><span class="sxs-lookup"><span data-stu-id="4c6fa-108">If the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property is set to a value equal to or greater than the number of characters in the text box, the insertion point is placed after the last character.</span></span>  
  
2.  <span data-ttu-id="4c6fa-109">Establecer el <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> propiedad a la longitud del texto que desea seleccionar.</span><span class="sxs-lookup"><span data-stu-id="4c6fa-109">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property to the length of the text you want to select.</span></span>  
  
     <span data-ttu-id="4c6fa-110">El <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> propiedad es un valor numérico que establece el ancho del punto de inserción.</span><span class="sxs-lookup"><span data-stu-id="4c6fa-110">The <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property is a numeric value that sets the width of the insertion point.</span></span> <span data-ttu-id="4c6fa-111">Establecer el <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> en un número mayor que 0, ese número de caracteres que se seleccionarán, comenzando desde el punto de inserción actual.</span><span class="sxs-lookup"><span data-stu-id="4c6fa-111">Setting the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> to a number greater than 0 causes that number of characters to be selected, starting from the current insertion point.</span></span>  
  
3.  <span data-ttu-id="4c6fa-112">(Opcional) Tener acceso al texto seleccionado a través de la <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="4c6fa-112">(Optional) Access the selected text through the <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> property.</span></span>  
  
     <span data-ttu-id="4c6fa-113">El código siguiente selecciona el contenido de texto de un cuadro cuando el control <xref:System.Windows.Forms.Control.Enter> se produce el evento.</span><span class="sxs-lookup"><span data-stu-id="4c6fa-113">The code below selects the contents of a text box when the control's <xref:System.Windows.Forms.Control.Enter> event occurs.</span></span> <span data-ttu-id="4c6fa-114">Este ejemplo se comprueba si el cuadro de texto tiene un valor para el <xref:System.Windows.Forms.TextBox.Text%2A> propiedad que no es `null` o una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="4c6fa-114">This example checks if the text box has a value for the <xref:System.Windows.Forms.TextBox.Text%2A> property that is not `null` or an empty string.</span></span> <span data-ttu-id="4c6fa-115">Cuando el cuadro de texto recibe el foco, se selecciona el texto actual en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="4c6fa-115">When the text box receives the focus, the current text in the text box is selected.</span></span> <span data-ttu-id="4c6fa-116">El `TextBox1_Enter` controlador de eventos debe enlazarse al control; para obtener más información, consulte [Cómo: Crear controladores de eventos en tiempo de ejecución para Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="4c6fa-116">The `TextBox1_Enter` event handler must be bound to the control; for more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
     <span data-ttu-id="4c6fa-117">Para probar este ejemplo, presione la tecla Tab hasta que el cuadro de texto tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="4c6fa-117">To test this example, press the Tab key until the text box has the focus.</span></span> <span data-ttu-id="4c6fa-118">Si hace clic en el cuadro de texto, el texto está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="4c6fa-118">If you click in the text box, the text is unselected.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4c6fa-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c6fa-119">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="4c6fa-120">Información general sobre el control TextBox</span><span class="sxs-lookup"><span data-stu-id="4c6fa-120">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="4c6fa-121">Filtrar para controlar el punto de inserción en un control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4c6fa-121">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="4c6fa-122">Filtrar para crear un cuadro de texto de contraseña con el control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4c6fa-122">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="4c6fa-123">Filtrar para crear un cuadro de texto de solo lectura</span><span class="sxs-lookup"><span data-stu-id="4c6fa-123">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="4c6fa-124">Filtrar para insertar comillas en una cadena</span><span class="sxs-lookup"><span data-stu-id="4c6fa-124">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="4c6fa-125">Filtrar para ver varias líneas en el control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4c6fa-125">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="4c6fa-126">Control TextBox</span><span class="sxs-lookup"><span data-stu-id="4c6fa-126">TextBox Control</span></span>](textbox-control-windows-forms.md)
