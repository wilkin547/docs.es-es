---
title: "C&#243;mo: Insertar comillas en una cadena (formularios Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "comillas"
  - "comillas, agregar a cadenas en cuadros de texto"
  - "TextBox (control) [Windows Forms], mostrar comillas"
ms.assetid: 68bdc3f3-4177-4eab-99cd-cac17a82b515
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Insertar comillas en una cadena (formularios Windows Forms)
En algunas ocasiones es necesario colocar las comillas \(""\) en una cadena de texto.  Por ejemplo:  
  
 Julia dijo: "¡Te invito a cenar\!"  
  
 Como alternativa, puede utilizar también el campo <xref:Microsoft.VisualBasic.ControlChars.Quote> como una constante.  
  
### Para colocar comillas en una cadena mediante programación  
  
1.  En [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], inserte dos comillas seguidas en una fila para representar una comilla incrustada.  En [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] y [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)], inserte la secuencia de escape \\" como una comilla incrustada.  Por ejemplo, para crear la cadena anterior, utilice el código siguiente:  
  
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
  
2.  Inserte el carácter ASCII o Unicode de las comillas.  En [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], utilice el carácter ASCII \(34\).  En [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], utilice el carácter Unicode \(\\u0022\).  
  
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
    >  En este ejemplo, no se puede utilizar \\u0022 porque no se puede utilizar un nombre de carácter universal que designe un carácter de un juego de caracteres básico.  De lo contrario, se produce el error C3851.  Para obtener más información, vea [Error del compilador C3851](../Topic/Compiler%20Error%20C3851.md).  
  
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
  
## Vea también  
 <xref:System.Windows.Forms.TextBox>   
 <xref:Microsoft.VisualBasic.ControlChars.Quote>   
 [Información general sobre el control TextBox](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)   
 [Cómo: Controlar el punto de inserción en un control TextBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)   
 [Cómo: Crear un cuadro de texto de contraseña con el control TextBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)   
 [Cómo: Crear un cuadro de texto de sólo lectura](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)   
 [Cómo: Seleccionar texto en el control TextBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)   
 [Cómo: Ver múltiples líneas en el control TextBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)   
 [TextBox \(Control\)](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)