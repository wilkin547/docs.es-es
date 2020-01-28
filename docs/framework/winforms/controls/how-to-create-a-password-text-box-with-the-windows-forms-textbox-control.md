---
title: Crear un cuadro de texto de contraseña con el control TextBox
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
ms.openlocfilehash: ff4706a736d15f14cf437c808219e9088773dc6d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731288"
---
# <a name="how-to-create-a-password-text-box-with-the-windows-forms-textbox-control"></a>Cómo: Crear un cuadro de texto de contraseña con el control TextBox de formularios Windows Forms

Un cuadro de contraseña es un Windows Forms cuadro de texto que muestra los caracteres de marcador de posición mientras un usuario escribe una cadena.

### <a name="to-create-a-password-text-box"></a>Para crear un cuadro de texto de contraseña

1. Establezca la propiedad <xref:System.Windows.Forms.TextBox.PasswordChar%2A> del control <xref:System.Windows.Forms.TextBox> en un carácter específico.

    La propiedad <xref:System.Windows.Forms.TextBox.PasswordChar%2A> especifica el carácter que se muestra en el cuadro de texto. Por ejemplo, si desea que se muestren asteriscos en el cuadro contraseña, especifique * para la propiedad <xref:System.Windows.Forms.TextBox.PasswordChar%2A> en el ventana Propiedades. A continuación, independientemente del carácter que un usuario escribe en el cuadro de texto, se muestra un asterisco.

2. Opta Establezca la propiedad <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A>. La propiedad determina el número de caracteres que se pueden escribir en el cuadro de texto. Si se supera la longitud máxima, el sistema emite un bip y el cuadro de texto no acepta más caracteres. Tenga en cuenta que es posible que no quiera hacer esto, ya que la longitud máxima de una contraseña puede ser de uso para los hackers que intentan adivinar la contraseña.

    En el ejemplo de código siguiente se muestra cómo inicializar un cuadro de texto que aceptará una cadena de hasta 14 caracteres y mostrará asteriscos en lugar de la cadena. El procedimiento `InitializeMyControl` no se ejecutará automáticamente; se debe llamar a.

    > [!IMPORTANT]
    > El uso de la propiedad <xref:System.Windows.Forms.TextBox.PasswordChar%2A> en un cuadro de texto puede ayudarle a garantizar que otras personas no podrán determinar la contraseña de un usuario si observan que el usuario la escribe. Esta medida de seguridad no cubre ningún tipo de almacenamiento o transmisión de la contraseña que puede producirse debido a la lógica de la aplicación. Dado que el texto escrito no está cifrado de ningún modo, debe tratarlo como lo haría con cualquier otra información confidencial. Aunque no aparece como tal, la contraseña todavía se trata como una cadena de texto sin formato (a menos que haya implementado alguna medida de seguridad adicional).

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
- [Controlar el punto de inserción en un control TextBox de Windows Forms](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Crear un cuadro de texto de sólo lectura](how-to-create-a-read-only-text-box-windows-forms.md)
- [Insertar comillas en una cadena](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Seleccionar texto en el control TextBox de Windows Forms](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Ver múltiples líneas en el control TextBox de Windows Forms](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Control TextBox](textbox-control-windows-forms.md)
