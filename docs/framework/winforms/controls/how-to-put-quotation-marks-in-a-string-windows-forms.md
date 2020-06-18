---
title: Procedimiento para insertar comillas en una cadena
description: Obtenga información sobre cómo insertar comillas en una cadena de texto. Además, aprenda a usar el campo quote como una constante.
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
ms.openlocfilehash: 08a3e2ab5662cbbf7825890ab430fddcd7b4a9ce
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903628"
---
# <a name="how-to-put-quotation-marks-in-a-string-windows-forms"></a><span data-ttu-id="115b1-104">Cómo: Insertar comillas en una cadena (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="115b1-104">How to: Put Quotation Marks in a String (Windows Forms)</span></span>
<span data-ttu-id="115b1-105">A veces querrá poner comillas ("") en una cadena de texto.</span><span class="sxs-lookup"><span data-stu-id="115b1-105">Sometimes you might want to place quotation marks (" ") in a string of text.</span></span> <span data-ttu-id="115b1-106">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="115b1-106">For example:</span></span>  
  
 <span data-ttu-id="115b1-107">Me dijo: "¡Te mereces un regalo!"</span><span class="sxs-lookup"><span data-stu-id="115b1-107">She said, "You deserve a treat!"</span></span>  
  
 <span data-ttu-id="115b1-108">Como alternativa, también puede usar el <xref:Microsoft.VisualBasic.ControlChars.Quote> campo como una constante.</span><span class="sxs-lookup"><span data-stu-id="115b1-108">As an alternative, you can also use the <xref:Microsoft.VisualBasic.ControlChars.Quote> field as a constant.</span></span>  
  
### <a name="to-place-quotation-marks-in-a-string-in-your-code"></a><span data-ttu-id="115b1-109">Para colocar comillas en una cadena en el código</span><span class="sxs-lookup"><span data-stu-id="115b1-109">To place quotation marks in a string in your code</span></span>  
  
1. <span data-ttu-id="115b1-110">En Visual Basic, inserte dos comillas en una fila como una comilla incrustada.</span><span class="sxs-lookup"><span data-stu-id="115b1-110">In Visual Basic, insert two quotation marks in a row as an embedded quotation mark.</span></span> <span data-ttu-id="115b1-111">En Visual C# y Visual C++, inserte la secuencia de escape \\ "como una comilla incrustada.</span><span class="sxs-lookup"><span data-stu-id="115b1-111">In Visual C# and Visual C++, insert the escape sequence \\" as an embedded quotation mark.</span></span> <span data-ttu-id="115b1-112">Por ejemplo, para crear la cadena anterior, utilice el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="115b1-112">For example, to create the preceding string, use the following code.</span></span>  
  
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
  
     <span data-ttu-id="115b1-113">O bien</span><span class="sxs-lookup"><span data-stu-id="115b1-113">-or-</span></span>  
  
2. <span data-ttu-id="115b1-114">Inserte el carácter ASCII o Unicode de una comilla.</span><span class="sxs-lookup"><span data-stu-id="115b1-114">Insert the ASCII or Unicode character for a quotation mark.</span></span> <span data-ttu-id="115b1-115">En Visual Basic, use el carácter ASCII (34).</span><span class="sxs-lookup"><span data-stu-id="115b1-115">In Visual Basic, use the ASCII character (34).</span></span> <span data-ttu-id="115b1-116">En Visual C#, use el carácter Unicode (\u0022).</span><span class="sxs-lookup"><span data-stu-id="115b1-116">In Visual C#, use the Unicode character (\u0022).</span></span>  
  
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
    > <span data-ttu-id="115b1-117">En este ejemplo, no puede utilizar \u0022 porque no puede utilizar un nombre de carácter universal que designe un carácter en el juego de caracteres básico.</span><span class="sxs-lookup"><span data-stu-id="115b1-117">In this example, you cannot use \u0022 because you cannot use a universal character name that designates a character in the basic character set.</span></span> <span data-ttu-id="115b1-118">De lo contrario, se produce el error C3851.</span><span class="sxs-lookup"><span data-stu-id="115b1-118">Otherwise, you produce C3851.</span></span> <span data-ttu-id="115b1-119">Para más información, consulte [Error del compilador C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851).</span><span class="sxs-lookup"><span data-stu-id="115b1-119">For more information, see [Compiler Error C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851).</span></span>  
  
     <span data-ttu-id="115b1-120">O bien</span><span class="sxs-lookup"><span data-stu-id="115b1-120">-or-</span></span>  
  
3. <span data-ttu-id="115b1-121">También puede definir una constante para el carácter y utilizarla donde sea necesario.</span><span class="sxs-lookup"><span data-stu-id="115b1-121">You can also define a constant for the character, and use it where needed.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="115b1-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="115b1-122">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- <xref:Microsoft.VisualBasic.ControlChars.Quote>
- [<span data-ttu-id="115b1-123">Información general sobre el control TextBox</span><span class="sxs-lookup"><span data-stu-id="115b1-123">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="115b1-124">Procedimiento para controlar el punto de inserción en un control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="115b1-124">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="115b1-125">Procedimiento para crear un cuadro de texto de contraseña con el control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="115b1-125">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="115b1-126">Procedimiento para crear un cuadro de texto de solo lectura</span><span class="sxs-lookup"><span data-stu-id="115b1-126">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="115b1-127">Procedimiento para seleccionar texto en el control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="115b1-127">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="115b1-128">Procedimiento para ver varias líneas en el control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="115b1-128">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="115b1-129">Control TextBox</span><span class="sxs-lookup"><span data-stu-id="115b1-129">TextBox Control</span></span>](textbox-control-windows-forms.md)
