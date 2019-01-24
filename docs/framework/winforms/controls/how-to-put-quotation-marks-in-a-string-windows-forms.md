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
# <a name="how-to-put-quotation-marks-in-a-string-windows-forms"></a>Procedimiento Insertar comillas en una cadena (formularios Windows Forms)
A veces querrá poner comillas ("") en una cadena de texto. Por ejemplo:  
  
 Me dijo: "¡Te mereces un regalo!"  
  
 Como alternativa, también puede usar el <xref:Microsoft.VisualBasic.ControlChars.Quote> campo como una constante.  
  
### <a name="to-place-quotation-marks-in-a-string-in-your-code"></a>Para colocar comillas en una cadena en el código  
  
1.  En Visual Basic, inserte dos comillas en una fila como una comilla incrustada. En Visual C# y [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)], inserte la secuencia de escape \\"como una comilla incrustada. Por ejemplo, para crear la cadena anterior, utilice el código siguiente.  
  
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
  
     O bien  
  
2.  Inserte el carácter ASCII o Unicode de una comilla. En Visual Basic, utilice el carácter ASCII (34). En Visual C#, use el carácter Unicode (\u0022).  
  
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
    >  En este ejemplo, no puede utilizar \u0022 porque no puede utilizar un nombre de carácter universal que designe un carácter en el juego de caracteres básico. De lo contrario, se produce el error C3851. Para más información, consulte [Error del compilador C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851).  
  
     O bien  
  
3.  También puede definir una constante para el carácter y utilizarla donde sea necesario.  
  
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
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.TextBox>
- <xref:Microsoft.VisualBasic.ControlChars.Quote>
- [Información general sobre el control TextBox](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)
- [Cómo: Controlar el punto de inserción en un Control TextBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Cómo: Crear un cuadro de texto de contraseña con el Control TextBox de Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Cómo: Crear un cuadro de texto de solo lectura](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)
- [Cómo: Seleccionar texto en el Control TextBox de Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Cómo: Ver múltiples líneas en el Control TextBox de Windows Forms](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Control TextBox](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
