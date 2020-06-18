---
title: Crear un cuadro de texto de contraseña con el control TextBox
description: Obtenga información sobre cómo cerate un texto Windows Forms que muestra caracteres de marcador de posición mientras un usuario escribe una cadena.
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
ms.openlocfilehash: 6d7e61eefa44ce3152aa77e3922bde471a4aeaf3
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904317"
---
# <a name="how-to-create-a-password-text-box-with-the-windows-forms-textbox-control"></a>Procedimiento para crear un cuadro de texto de contraseña con el control TextBox de formularios Windows Forms

Un cuadro de contraseña es un Windows Forms cuadro de texto que muestra los caracteres de marcador de posición mientras un usuario escribe una cadena.

### <a name="to-create-a-password-text-box"></a>Para crear un cuadro de texto de contraseña

1. Establezca la <xref:System.Windows.Forms.TextBox.PasswordChar%2A> propiedad del <xref:System.Windows.Forms.TextBox> control en un carácter específico.

    La <xref:System.Windows.Forms.TextBox.PasswordChar%2A> propiedad especifica el carácter que se muestra en el cuadro de texto. Por ejemplo, si desea que se muestren asteriscos en el cuadro contraseña, especifique * para la <xref:System.Windows.Forms.TextBox.PasswordChar%2A> propiedad en el ventana Propiedades. A continuación, independientemente del carácter que un usuario escribe en el cuadro de texto, se muestra un asterisco.

2. Opta Establezca la <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> propiedad. La propiedad determina el número de caracteres que se pueden escribir en el cuadro de texto. Si se supera la longitud máxima, el sistema emite un bip y el cuadro de texto no acepta más caracteres. Tenga en cuenta que es posible que no quiera hacer esto, ya que la longitud máxima de una contraseña puede ser de uso para los hackers que intentan adivinar la contraseña.

    En el ejemplo de código siguiente se muestra cómo inicializar un cuadro de texto que aceptará una cadena de hasta 14 caracteres y mostrará asteriscos en lugar de la cadena. El `InitializeMyControl` procedimiento no se ejecutará automáticamente; se debe llamar a.

    > [!IMPORTANT]
    > El uso de la <xref:System.Windows.Forms.TextBox.PasswordChar%2A> propiedad en un cuadro de texto puede ayudarle a garantizar que otras personas no podrán determinar la contraseña de un usuario si observan que el usuario la escribe. Esta medida de seguridad no cubre ningún tipo de almacenamiento o transmisión de la contraseña que puede producirse debido a la lógica de la aplicación. Dado que el texto escrito no está cifrado de ningún modo, debe tratarlo como lo haría con cualquier otra información confidencial. Aunque no aparece como tal, la contraseña todavía se trata como una cadena de texto sin formato (a menos que haya implementado alguna medida de seguridad adicional).

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

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.TextBox>
- [Información general sobre el control TextBox](textbox-control-overview-windows-forms.md)
- [Procedimiento para controlar el punto de inserción en un control TextBox de formularios Windows Forms](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Procedimiento para crear un cuadro de texto de solo lectura](how-to-create-a-read-only-text-box-windows-forms.md)
- [Procedimiento para insertar comillas en una cadena](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Procedimiento para seleccionar texto en el control TextBox de formularios Windows Forms](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Procedimiento para ver varias líneas en el control TextBox de formularios Windows Forms](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Control TextBox](textbox-control-windows-forms.md)
