---
title: Controlar el punto de inserción en el control de cuadro de texto
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], insertion point
- insertion points [Windows Forms], TextBox controls
- text boxes [Windows Forms], controlling insertion point
ms.assetid: 5bee7d34-5121-429e-ab1f-d8ff67bc74c1
ms.openlocfilehash: fd4803820921f0c922a4ce885f809abee8fd4c6c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742205"
---
# <a name="how-to-control-the-insertion-point-in-a-windows-forms-textbox-control"></a>Cómo: Controlar el punto de inserción en un control TextBox de formularios Windows Forms
Cuando un Windows Forms control de <xref:System.Windows.Forms.TextBox> recibe el foco por primera vez, la inserción predeterminada en el cuadro de texto se encuentra a la izquierda de cualquier texto existente. El usuario puede desplace el punto de inserción con el teclado o el mouse. Si el cuadro de texto pierde y vuelve a obtener el foco, el punto de inserción será donde el usuario lo haya colocado por última vez.  
  
 En algunos casos, este comportamiento puede ser desconcertado para el usuario. En una aplicación de procesamiento de texto, el usuario podría esperar que aparezcan nuevos caracteres después de cualquier texto existente. En una aplicación de entrada de datos, el usuario podría esperar que los nuevos caracteres reemplazaran cualquier entrada existente. Las propiedades <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> y <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> permiten modificar el comportamiento para adaptarlo a su propósito.  
  
### <a name="to-control-the-insertion-point-in-a-textbox-control"></a>Para controlar el punto de inserción en un control TextBox  
  
1. Establezca la propiedad <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> en un valor apropiado. Cero coloca el punto de inserción inmediatamente a la izquierda del primer carácter.  
  
2. Opta Establezca la propiedad <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> en la longitud del texto que desea seleccionar.  
  
     El código siguiente siempre devuelve el punto de inserción a 0. El controlador de eventos `TextBox1_Enter` debe estar enlazado al control; para obtener más información, vea [crear controladores de eventos en Windows Forms](../creating-event-handlers-in-windows-forms.md).  
  
    ```vb  
    Private Sub TextBox1_Enter(ByVal sender As Object, ByVal e As System.EventArgs) Handles TextBox1.Enter  
       TextBox1.SelectionStart = 0  
       TextBox1.SelectionLength = 0  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_Enter(Object sender, System.EventArgs e) {  
       textBox1.SelectionStart = 0;  
       textBox1.SelectionLength = 0;  
    }  
    ```  
  
    ```cpp  
    private:  
       void textBox1_Enter(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          textBox1->SelectionStart = 0;  
          textBox1->SelectionLength = 0;  
       }  
    ```  
  
## <a name="making-the-insertion-point-visible-by-default"></a>Cómo es visible de forma predeterminada el punto de inserción  
 El punto de inserción <xref:System.Windows.Forms.TextBox> es visible de forma predeterminada en un formulario nuevo solo si el control <xref:System.Windows.Forms.TextBox> es el primero en el orden de tabulación. De lo contrario, el punto de inserción solo aparece si se asigna al <xref:System.Windows.Forms.TextBox> el foco con el teclado o con el mouse.  
  
#### <a name="to-make-the-text-box-insertion-point-visible-by-default-on-a-new-form"></a>Para que el punto de inserción del cuadro de texto esté visible de forma predeterminada en un nuevo formulario  
  
- Establezca la propiedad <xref:System.Windows.Forms.Control.TabIndex%2A> del control <xref:System.Windows.Forms.TextBox> en `0`.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.TextBox>
- [Información general sobre el control TextBox](textbox-control-overview-windows-forms.md)
- [Crear un cuadro de texto de contraseña con el control TextBox de Windows Forms](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Crear un cuadro de texto de sólo lectura](how-to-create-a-read-only-text-box-windows-forms.md)
- [Insertar comillas en una cadena](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Seleccionar texto en el control TextBox de Windows Forms](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Ver múltiples líneas en el control TextBox de Windows Forms](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [TextBox (control)](textbox-control-windows-forms.md)
