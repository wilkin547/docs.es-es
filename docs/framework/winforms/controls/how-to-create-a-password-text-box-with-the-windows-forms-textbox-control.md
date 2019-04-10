---
title: Filtrar para crear un cuadro de texto de contraseña con el control TextBox de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], entering passwords
- password boxes [Windows Forms], creating
- PasswordChar property in text boxes
- passwords [Windows Forms], input mask
- passwords [Windows Forms], password text box
ms.assetid: d105d6b9-3d50-44cd-80d8-2c0e2f486727
ms.openlocfilehash: ab5df1233c16a7ce076efa817fb14808b588ebcd
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59300988"
---
# <a name="how-to-create-a-password-text-box-with-the-windows-forms-textbox-control"></a>Filtrar para crear un cuadro de texto de contraseña con el control TextBox de formularios Windows Forms
Un cuadro de contraseña es un cuadro de texto de Windows Forms que muestra los caracteres de marcador de posición mientras un usuario escribe una cadena.  
  
### <a name="to-create-a-password-text-box"></a>Para crear un cuadro de texto de contraseña  
  
1. Establecer el <xref:System.Windows.Forms.TextBox.PasswordChar%2A> propiedad de la <xref:System.Windows.Forms.TextBox> control a un carácter específico.  
  
     El <xref:System.Windows.Forms.TextBox.PasswordChar%2A> propiedad especifica el carácter que se muestra en el cuadro de texto. Por ejemplo, si desea que se muestren asteriscos en el cuadro de contraseña, especifique * para la <xref:System.Windows.Forms.TextBox.PasswordChar%2A> propiedad en la ventana Propiedades. A continuación, independientemente del carácter que un usuario escribe en el cuadro de texto, se muestra un asterisco.  
  
2. (Opcional) Establecer el <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> propiedad. La propiedad determina cuántos caracteres se pueden escribir en el cuadro de texto. Si se supera la longitud máxima, el sistema emite un bip y el cuadro de texto no acepta caracteres más. Tenga en cuenta que es posible que no desea hacer esto como la longitud máxima de una contraseña puede resultar útil para los hackers que intentan adivinar la contraseña.  
  
     El ejemplo de código siguiente muestra cómo inicializar un cuadro de texto que se aceptan una cadena de hasta 14 caracteres y se muestran asteriscos en lugar de la cadena. El `InitializeMyControl` procedimiento no se ejecutará automáticamente; debe llamarse.  
  
    > [!IMPORTANT]
    >  Mediante el <xref:System.Windows.Forms.TextBox.PasswordChar%2A> propiedad en un cuadro de texto puede ayudar a garantizar que otras personas no podrán determinar la contraseña de un usuario si ven cuando el usuario escribe. Esta medida de seguridad no cubre a cualquier tipo de almacenamiento o transmisión de la contraseña que se puede producir debido a la lógica de aplicación. Dado que no se cifra el texto escrito en cualquier forma, debe tratar como lo haría con cualquier otro dato confidencial. Aunque no aparezcan como tal, la contraseña es todavía se tratan como una cadena de texto sin formato (a menos que haya implementado alguna medida de seguridad adicional).  
  
    ```vb  
    Private Sub InitializeMyControl()  
       ' Set to no text.  
       TextBox1.Text = ""  
       ' The password character is an asterisk.  
       TextBox1.PasswordChar = "*"  
       ' The control will allow no more than 14 characters.  
       TextBox1.MaxLength = 14  
    End Sub  
    ```  
  
    ```csharp  
    private void InitializeMyControl()  
    {  
       // Set to no text.  
       textBox1.Text = "";  
       // The password character is an asterisk.  
       textBox1.PasswordChar = '*';  
       // The control will allow no more than 14 characters.  
       textBox1.MaxLength = 14;  
    }  
    ```  
  
    ```cpp  
    private:  
       void InitializeMyControl()  
       {  
          // Set to no text.  
          textBox1->Text = "";  
          // The password character is an asterisk.  
          textBox1->PasswordChar = '*';  
          // The control will allow no more than 14 characters.  
          textBox1->MaxLength = 14;  
       }  
    ```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.TextBox>
- [Información general sobre el control TextBox](textbox-control-overview-windows-forms.md)
- [Filtrar para controlar el punto de inserción en un control TextBox de formularios Windows Forms](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Filtrar para crear un cuadro de texto de solo lectura](how-to-create-a-read-only-text-box-windows-forms.md)
- [Filtrar para insertar comillas en una cadena](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Filtrar para seleccionar texto en el control TextBox de formularios Windows Forms](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Filtrar para ver varias líneas en el control TextBox de formularios Windows Forms](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Control TextBox](textbox-control-windows-forms.md)
