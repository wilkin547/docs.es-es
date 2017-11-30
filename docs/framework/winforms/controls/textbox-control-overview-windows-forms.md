---
title: "Información general sobre el control TextBox (formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
f1_keywords: TextBox
helpviewer_keywords:
- TextBox control [Windows Forms], about TextBox controls
- text boxes [Windows Forms], adding
ms.assetid: d1a9c7f5-fa53-480a-a75c-158f8649ea2f
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e8c75392f12b87c7495b1fcdf5419f2463067161
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="textbox-control-overview-windows-forms"></a>Información general sobre el control TextBox (formularios Windows Forms)
Cuadros de texto de formularios Windows Forms se utilizan para obtener datos proporcionados por el usuario o para mostrar el texto. El <xref:System.Windows.Forms.TextBox> control se utiliza generalmente para el texto editable, aunque también pueden realizarse de solo lectura. Cuadros de texto pueden mostrar varias líneas, ajustar el texto al tamaño del control y agregar formato básico. El <xref:System.Windows.Forms.TextBox> control proporciona un estilo de formato único para el texto mostrado o escrito en el control. Para mostrar varios tipos de texto con formato, use el <xref:System.Windows.Forms.RichTextBox> control. Para obtener más información, consulte [información general del Control RichTextBox](../../../../docs/framework/winforms/controls/richtextbox-control-overview-windows-forms.md).  
  
## <a name="working-with-the-textbox-control"></a>Trabajar con el Control de cuadro de texto  
 El texto mostrado por el control se encuentra en la <xref:System.Windows.Forms.TextBox.Text%2A> propiedad. De forma predeterminada, puede introducir hasta 2048 caracteres en un cuadro de texto. Si establece la <xref:System.Windows.Forms.TextBox.Multiline%2A> propiedad `true`, puede escribir un máximo de 32 KB de texto. El <xref:System.Windows.Forms.TextBox.Text%2A> propiedad puede establecerse en tiempo de diseño con la ventana Propiedades, en tiempo de ejecución en código, o proporcionados por el usuario en tiempo de ejecución. Se puede recuperar el contenido actual de un cuadro de texto en tiempo de ejecución al leer el <xref:System.Windows.Forms.TextBox.Text%2A> propiedad.  
  
 En el ejemplo de código siguiente se establece el texto en el control en tiempo de ejecución. El `InitializeMyControl` procedimiento no se ejecutará automáticamente; debe llamarse.  
  
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
 <xref:System.Windows.Forms.TextBox>  
 [Controlar el punto de inserción en un control TextBox de Windows Forms](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [Crear un cuadro de texto de contraseña con el control TextBox de Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [Crear un cuadro de texto de sólo lectura](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [Insertar comillas en una cadena](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [Seleccionar texto en el control TextBox de Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [Ver múltiples líneas en el control TextBox de Windows Forms](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [Control TextBox](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
