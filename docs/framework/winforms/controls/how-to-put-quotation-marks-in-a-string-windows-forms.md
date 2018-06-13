---
title: 'Cómo: Insertar comillas en una cadena (formularios Windows Forms)'
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
ms.openlocfilehash: 7fcc2e8692880f1e5c2b8df807cf7943a5575c56
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534838"
---
# <a name="how-to-put-quotation-marks-in-a-string-windows-forms"></a><span data-ttu-id="91264-102">Cómo: Insertar comillas en una cadena (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="91264-102">How to: Put Quotation Marks in a String (Windows Forms)</span></span>
<span data-ttu-id="91264-103">A veces querrá poner comillas ("") en una cadena de texto.</span><span class="sxs-lookup"><span data-stu-id="91264-103">Sometimes you might want to place quotation marks (" ") in a string of text.</span></span> <span data-ttu-id="91264-104">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="91264-104">For example:</span></span>  
  
 <span data-ttu-id="91264-105">Me dijo: "¡Te mereces un regalo!"</span><span class="sxs-lookup"><span data-stu-id="91264-105">She said, "You deserve a treat!"</span></span>  
  
 <span data-ttu-id="91264-106">Como alternativa, también puede utilizar el <xref:Microsoft.VisualBasic.ControlChars.Quote> campo como una constante.</span><span class="sxs-lookup"><span data-stu-id="91264-106">As an alternative, you can also use the <xref:Microsoft.VisualBasic.ControlChars.Quote> field as a constant.</span></span>  
  
### <a name="to-place-quotation-marks-in-a-string-in-your-code"></a><span data-ttu-id="91264-107">Para colocar comillas en una cadena en el código</span><span class="sxs-lookup"><span data-stu-id="91264-107">To place quotation marks in a string in your code</span></span>  
  
1.  <span data-ttu-id="91264-108">En Visual Basic, inserte dos comillas seguidas en una fila como una comilla incrustada.</span><span class="sxs-lookup"><span data-stu-id="91264-108">In Visual Basic, insert two quotation marks in a row as an embedded quotation mark.</span></span> <span data-ttu-id="91264-109">En Visual C# y [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)], inserte la secuencia de escape \\"como una comilla incrustada.</span><span class="sxs-lookup"><span data-stu-id="91264-109">In Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)], insert the escape sequence \\" as an embedded quotation mark.</span></span> <span data-ttu-id="91264-110">Por ejemplo, para crear la cadena anterior, utilice el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="91264-110">For example, to create the preceding string, use the following code.</span></span>  
  
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
  
     <span data-ttu-id="91264-111">-o bien-</span><span class="sxs-lookup"><span data-stu-id="91264-111">-or-</span></span>  
  
2.  <span data-ttu-id="91264-112">Inserte el carácter ASCII o Unicode de una comilla.</span><span class="sxs-lookup"><span data-stu-id="91264-112">Insert the ASCII or Unicode character for a quotation mark.</span></span> <span data-ttu-id="91264-113">En Visual Basic, utilice el carácter ASCII (34).</span><span class="sxs-lookup"><span data-stu-id="91264-113">In Visual Basic, use the ASCII character (34).</span></span> <span data-ttu-id="91264-114">En Visual C#, utilice el carácter Unicode (\u0022).</span><span class="sxs-lookup"><span data-stu-id="91264-114">In Visual C#, use the Unicode character (\u0022).</span></span>  
  
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
    >  <span data-ttu-id="91264-115">En este ejemplo, no puede utilizar \u0022 porque no puede utilizar un nombre de carácter universal que designe un carácter en el juego de caracteres básico.</span><span class="sxs-lookup"><span data-stu-id="91264-115">In this example, you cannot use \u0022 because you cannot use a universal character name that designates a character in the basic character set.</span></span> <span data-ttu-id="91264-116">De lo contrario, se produce el error C3851.</span><span class="sxs-lookup"><span data-stu-id="91264-116">Otherwise, you produce C3851.</span></span> <span data-ttu-id="91264-117">Para más información, consulte [Error del compilador C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851).</span><span class="sxs-lookup"><span data-stu-id="91264-117">For more information, see [Compiler Error C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851).</span></span>  
  
     <span data-ttu-id="91264-118">-o bien-</span><span class="sxs-lookup"><span data-stu-id="91264-118">-or-</span></span>  
  
3.  <span data-ttu-id="91264-119">También puede definir una constante para el carácter y utilizarla donde sea necesario.</span><span class="sxs-lookup"><span data-stu-id="91264-119">You can also define a constant for the character, and use it where needed.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="91264-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="91264-120">See Also</span></span>  
 <xref:System.Windows.Forms.TextBox>  
 <xref:Microsoft.VisualBasic.ControlChars.Quote>  
 [<span data-ttu-id="91264-121">Información general sobre el control TextBox</span><span class="sxs-lookup"><span data-stu-id="91264-121">TextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="91264-122">Controlar el punto de inserción en un control TextBox de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="91264-122">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [<span data-ttu-id="91264-123">Crear un cuadro de texto de contraseña con el control TextBox de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="91264-123">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="91264-124">Crear un cuadro de texto de sólo lectura</span><span class="sxs-lookup"><span data-stu-id="91264-124">How to: Create a Read-Only Text Box</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [<span data-ttu-id="91264-125">Seleccionar texto en el control TextBox de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="91264-125">How to: Select Text in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="91264-126">Ver múltiples líneas en el control TextBox de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="91264-126">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="91264-127">Control TextBox</span><span class="sxs-lookup"><span data-stu-id="91264-127">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
