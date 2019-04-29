---
title: Información general sobre el control TextBox (formularios Windows Forms)
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
ms.openlocfilehash: a91b67df1071c79707bb20a68efb4d5e6f083ae0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61932553"
---
# <a name="textbox-control-overview-windows-forms"></a>Información general sobre el control TextBox (formularios Windows Forms)
Los cuadros de texto de Windows Forms se utilizan para obtener datos proporcionados por el usuario o para mostrar texto. El <xref:System.Windows.Forms.TextBox> control se utiliza generalmente para el texto editable, aunque también se pueden hacer de solo lectura. Los cuadros de texto pueden mostrar varias líneas, ajustar el texto para el tamaño del control y agregar formato básico. El <xref:System.Windows.Forms.TextBox> control proporciona un único estilo de formato para mostrar o escribir en el control de texto. Para mostrar varios tipos de texto con formato, use el <xref:System.Windows.Forms.RichTextBox> control. Para obtener más información, consulte [información general del Control RichTextBox](richtextbox-control-overview-windows-forms.md).  
  
## <a name="working-with-the-textbox-control"></a>Trabajar con el Control de cuadro de texto  
 El texto mostrado por el control está incluido en el <xref:System.Windows.Forms.TextBox.Text%2A> propiedad. De forma predeterminada, puede especificar hasta 2048 caracteres en un cuadro de texto. Si establece la <xref:System.Windows.Forms.TextBox.Multiline%2A> propiedad `true`, puede escribir hasta 32 KB de texto. El <xref:System.Windows.Forms.TextBox.Text%2A> propiedad puede establecerse en tiempo de diseño con la ventana Propiedades, en tiempo de ejecución en el código o mediante la entrada del usuario en tiempo de ejecución. Se puede recuperar el contenido actual de un cuadro de texto en tiempo de ejecución, lea el <xref:System.Windows.Forms.TextBox.Text%2A> propiedad.  
  
 El ejemplo de código siguiente establece el texto en el control en tiempo de ejecución. El `InitializeMyControl` procedimiento no se ejecutará automáticamente; debe llamarse.  
  
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
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.TextBox>
- [Cómo: Controlar el punto de inserción en un Control TextBox de formularios Windows Forms](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Cómo: Crear un cuadro de texto de contraseña con el Control TextBox de Windows Forms](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Cómo: Crear un cuadro de texto de solo lectura](how-to-create-a-read-only-text-box-windows-forms.md)
- [Cómo: Insertar comillas en una cadena](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Cómo: Seleccionar texto en el Control TextBox de Windows Forms](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Cómo: Ver múltiples líneas en el Control TextBox de Windows Forms](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Control TextBox](textbox-control-windows-forms.md)
