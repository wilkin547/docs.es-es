---
title: Información general sobre el control TextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TextBox
helpviewer_keywords:
- TextBox control [Windows Forms], about TextBox controls
- text boxes [Windows Forms], adding
ms.assetid: d1a9c7f5-fa53-480a-a75c-158f8649ea2f
ms.openlocfilehash: 06ab460d720d17331881b5ba653263160eaf3cb3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742805"
---
# <a name="textbox-control-overview-windows-forms"></a>Información general sobre el control TextBox (formularios Windows Forms)
Windows Forms cuadros de texto se utilizan para obtener la entrada del usuario o para mostrar texto. Normalmente, el control <xref:System.Windows.Forms.TextBox> se utiliza para texto editable, aunque también se puede convertir en de solo lectura. Los cuadros de texto pueden mostrar varias líneas, ajustar el texto al tamaño del control y agregar formato básico. El control <xref:System.Windows.Forms.TextBox> proporciona un estilo de formato único para el texto que se muestra o se escribe en el control. Para mostrar varios tipos de texto con formato, utilice el control <xref:System.Windows.Forms.RichTextBox>. Para obtener más información, vea [información general sobre el control RichTextBox](richtextbox-control-overview-windows-forms.md).  
  
## <a name="working-with-the-textbox-control"></a>Trabajar con el control TextBox  
 El texto que muestra el control está contenido en la propiedad <xref:System.Windows.Forms.TextBox.Text%2A>. De forma predeterminada, puede escribir hasta 2048 caracteres en un cuadro de texto. Si establece la propiedad <xref:System.Windows.Forms.TextBox.Multiline%2A> en `true`, puede escribir hasta 32 KB de texto. La propiedad <xref:System.Windows.Forms.TextBox.Text%2A> se puede establecer en tiempo de diseño con la ventana Propiedades, en tiempo de ejecución en el código o mediante la entrada del usuario en tiempo de ejecución. El contenido actual de un cuadro de texto se puede recuperar en tiempo de ejecución mediante la lectura de la propiedad <xref:System.Windows.Forms.TextBox.Text%2A>.  
  
 En el ejemplo de código siguiente se establece el texto del control en tiempo de ejecución. El procedimiento `InitializeMyControl` no se ejecutará automáticamente; se debe llamar a.  
  
```vb  
Private Sub InitializeMyControl()  
   ' Put some text into the control first.  
   TextBox1.Text = "This is a TextBox control."  
End Sub  
```  
  
```csharp  
private void InitializeMyControl() {  
   // Put some text into the control first.  
   textBox1.Text = "This is a TextBox control.";  
}  
```  
  
```cpp  
private:  
   void InitializeMyControl()  
   {  
      // Put some text into the control first.  
      textBox1->Text = "This is a TextBox control.";  
   }  
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.TextBox>
- [Controlar el punto de inserción en un control TextBox de Windows Forms](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Crear un cuadro de texto de contraseña con el control TextBox de Windows Forms](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Crear un cuadro de texto de sólo lectura](how-to-create-a-read-only-text-box-windows-forms.md)
- [Insertar comillas en una cadena](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Seleccionar texto en el control TextBox de Windows Forms](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Ver múltiples líneas en el control TextBox de Windows Forms](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [TextBox (control)](textbox-control-windows-forms.md)
