---
title: Procedimiento para crear un cuadro de texto de contraseña con el control TextBox de formularios Windows Forms
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
ms.openlocfilehash: 56391777c75db288c33d1b2192355be0df50f7ee
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046122"
---
# <a name="how-to-create-a-password-text-box-with-the-windows-forms-textbox-control"></a>Procedimiento para crear un cuadro de texto de contraseña con el control TextBox de formularios Windows Forms

Un cuadro de contraseña es un Windows Forms cuadro de texto que muestra los caracteres de marcador de posición mientras un usuario escribe una cadena.

### <a name="to-create-a-password-text-box"></a>Para crear un cuadro de texto de contraseña

1. Establezca la <xref:System.Windows.Forms.TextBox.PasswordChar%2A> propiedad <xref:System.Windows.Forms.TextBox> del control en un carácter específico.

    La <xref:System.Windows.Forms.TextBox.PasswordChar%2A> propiedad especifica el carácter que se muestra en el cuadro de texto. Por ejemplo, si desea que se muestren asteriscos en el cuadro contraseña, especifique * <xref:System.Windows.Forms.TextBox.PasswordChar%2A> para la propiedad en el ventana Propiedades. A continuación, independientemente del carácter que un usuario escribe en el cuadro de texto, se muestra un asterisco.

2. Opta Establezca la <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> propiedad. La propiedad determina el número de caracteres que se pueden escribir en el cuadro de texto. Si se supera la longitud máxima, el sistema emite un bip y el cuadro de texto no acepta más caracteres. Tenga en cuenta que es posible que no quiera hacer esto, ya que la longitud máxima de una contraseña puede ser de uso para los hackers que intentan adivinar la contraseña.

    En el ejemplo de código siguiente se muestra cómo inicializar un cuadro de texto que aceptará una cadena de hasta 14 caracteres y mostrará asteriscos en lugar de la cadena. El `InitializeMyControl` procedimiento no se ejecutará automáticamente; se debe llamar a.

    > [!IMPORTANT]
    > El uso <xref:System.Windows.Forms.TextBox.PasswordChar%2A> de la propiedad en un cuadro de texto puede ayudarle a garantizar que otras personas no podrán determinar la contraseña de un usuario si observan que el usuario la escribe. Esta medida de seguridad no cubre ningún tipo de almacenamiento o transmisión de la contraseña que puede producirse debido a la lógica de la aplicación. Dado que el texto escrito no está cifrado de ningún modo, debe tratarlo como lo haría con cualquier otra información confidencial. Aunque no aparece como tal, la contraseña todavía se trata como una cadena de texto sin formato (a menos que haya implementado alguna medida de seguridad adicional).

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
- [Procedimientos: Controlar el punto de inserción en un control de cuadro de texto Windows Forms](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Cómo: Crear un cuadro de texto de solo lectura](how-to-create-a-read-only-text-box-windows-forms.md)
- [Cómo: Insertar comillas en una cadena](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Cómo: Seleccionar texto en el control TextBox Windows Forms](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Cómo: Ver varias líneas en el control TextBox Windows Forms](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Control TextBox](textbox-control-windows-forms.md)
