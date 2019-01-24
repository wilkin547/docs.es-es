---
title: Procedimiento Insertar comillas en una cadena (formularios Windows Forms)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- quotation marks
- TextBox control [Windows Forms], displaying quotation marks
- quotation marks [Windows Forms], adding to strings in text boxes
ms.assetid: 68bdc3f3-4177-4eab-99cd-cac17a82b515
ms.openlocfilehash: 24d7ea17384a912fda454bfb1136696ab18d9843
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54651648"
---
# <a name="how-to-put-quotation-marks-in-a-string-windows-forms"></a><span data-ttu-id="d5dfc-102">Procedimiento Insertar comillas en una cadena (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="d5dfc-102">How to: Put Quotation Marks in a String (Windows Forms)</span></span>
<span data-ttu-id="d5dfc-103">A veces querrá poner comillas ("") en una cadena de texto.</span><span class="sxs-lookup"><span data-stu-id="d5dfc-103">Sometimes you might want to place quotation marks (" ") in a string of text.</span></span> <span data-ttu-id="d5dfc-104">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d5dfc-104">For example:</span></span>  
  
 <span data-ttu-id="d5dfc-105">Me dijo: "¡Te mereces un regalo!"</span><span class="sxs-lookup"><span data-stu-id="d5dfc-105">She said, "You deserve a treat!"</span></span>  
  
 <span data-ttu-id="d5dfc-106">Como alternativa, también puede usar el <xref:Microsoft.VisualBasic.ControlChars.Quote> campo como una constante.</span><span class="sxs-lookup"><span data-stu-id="d5dfc-106">As an alternative, you can also use the <xref:Microsoft.VisualBasic.ControlChars.Quote> field as a constant.</span></span>  
  
### <a name="to-place-quotation-marks-in-a-string-in-your-code"></a><span data-ttu-id="d5dfc-107">Para colocar comillas en una cadena en el código</span><span class="sxs-lookup"><span data-stu-id="d5dfc-107">To place quotation marks in a string in your code</span></span>  
  
1.  <span data-ttu-id="d5dfc-108">En Visual Basic, inserte dos comillas en una fila como una comilla incrustada.</span><span class="sxs-lookup"><span data-stu-id="d5dfc-108">In Visual Basic, insert two quotation marks in a row as an embedded quotation mark.</span></span> <span data-ttu-id="d5dfc-109">En Visual C# y [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)], inserte la secuencia de escape \\"como una comilla incrustada.</span><span class="sxs-lookup"><span data-stu-id="d5dfc-109">In Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)], insert the escape sequence \\" as an embedded quotation mark.</span></span> <span data-ttu-id="d5dfc-110">Por ejemplo, para crear la cadena anterior, utilice el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="d5dfc-110">For example, to create the preceding string, use the following code.</span></span>  
  
    ```vb  
    Private Sub InsertQuote()  
       TextBox1.Text = "She said, ""You deserve a treat!"" "  
    End Sub  
    ```  
  
    ```csharp  
    private void InsertQuote(){  
       textBox1.Text = "She said, \"You deserve a treat!\" ";  
    }  
    ```  
  
    ```cpp  
    private:  
       void InsertQuote()  
       {  
          textBox1->Text = "She said, \"You deserve a treat!\" ";  
       }  
    ```  
  
     <span data-ttu-id="d5dfc-111">O bien</span><span class="sxs-lookup"><span data-stu-id="d5dfc-111">-or-</span></span>  
  
2.  <span data-ttu-id="d5dfc-112">Inserte el carácter ASCII o Unicode de una comilla.</span><span class="sxs-lookup"><span data-stu-id="d5dfc-112">Insert the ASCII or Unicode character for a quotation mark.</span></span> <span data-ttu-id="d5dfc-113">En Visual Basic, utilice el carácter ASCII (34).</span><span class="sxs-lookup"><span data-stu-id="d5dfc-113">In Visual Basic, use the ASCII character (34).</span></span> <span data-ttu-id="d5dfc-114">En Visual C#, use el carácter Unicode (\u0022).</span><span class="sxs-lookup"><span data-stu-id="d5dfc-114">In Visual C#, use the Unicode character (\u0022).</span></span>  
  
    ```vb  
    Private Sub InsertAscii()  
       TextBox1.Text = "She said, " & Chr(34) & "You deserve a treat!" & Chr(34)  
    End Sub  
    ```  
  
    ```csharp  
    private void InsertAscii(){  
       textBox1.Text = "She said, " + '\u0022' + "You deserve a treat!" + '\u0022';  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="d5dfc-115">En este ejemplo, no puede utilizar \u0022 porque no puede utilizar un nombre de carácter universal que designe un carácter en el juego de caracteres básico.</span><span class="sxs-lookup"><span data-stu-id="d5dfc-115">In this example, you cannot use \u0022 because you cannot use a universal character name that designates a character in the basic character set.</span></span> <span data-ttu-id="d5dfc-116">De lo contrario, se produce el error C3851.</span><span class="sxs-lookup"><span data-stu-id="d5dfc-116">Otherwise, you produce C3851.</span></span> <span data-ttu-id="d5dfc-117">Para más información, consulte [Error del compilador C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851).</span><span class="sxs-lookup"><span data-stu-id="d5dfc-117">For more information, see [Compiler Error C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851).</span></span>  
  
     <span data-ttu-id="d5dfc-118">O bien</span><span class="sxs-lookup"><span data-stu-id="d5dfc-118">-or-</span></span>  
  
3.  <span data-ttu-id="d5dfc-119">También puede definir una constante para el carácter y utilizarla donde sea necesario.</span><span class="sxs-lookup"><span data-stu-id="d5dfc-119">You can also define a constant for the character, and use it where needed.</span></span>  
  
    ```vb  
    Const quote As String = """"  
    TextBox1.Text = "She said, " & quote & "You deserve a treat!" & quote  
    ```  
  
    ```csharp  
    const string quote = "\"";  
    textBox1.Text = "She said, " + quote +  "You deserve a treat!"+ quote ;  
    ```  
  
    ```cpp  
    const String^ quote = "\"";  
    textBox1->Text = String::Concat("She said, ",  
       const_cast<String^>(quote), "You deserve a treat!",  
       const_cast<String^>(quote));  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d5dfc-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5dfc-120">See also</span></span>
- <xref:System.Windows.Forms.TextBox>
- <xref:Microsoft.VisualBasic.ControlChars.Quote>
- [<span data-ttu-id="d5dfc-121">Información general sobre el control TextBox</span><span class="sxs-lookup"><span data-stu-id="d5dfc-121">TextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="d5dfc-122">Cómo: Controlar el punto de inserción en un Control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d5dfc-122">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="d5dfc-123">Cómo: Crear un cuadro de texto de contraseña con el Control TextBox de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d5dfc-123">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="d5dfc-124">Cómo: Crear un cuadro de texto de solo lectura</span><span class="sxs-lookup"><span data-stu-id="d5dfc-124">How to: Create a Read-Only Text Box</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="d5dfc-125">Cómo: Seleccionar texto en el Control TextBox de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d5dfc-125">How to: Select Text in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="d5dfc-126">Cómo: Ver múltiples líneas en el Control TextBox de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d5dfc-126">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="d5dfc-127">Control TextBox</span><span class="sxs-lookup"><span data-stu-id="d5dfc-127">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
