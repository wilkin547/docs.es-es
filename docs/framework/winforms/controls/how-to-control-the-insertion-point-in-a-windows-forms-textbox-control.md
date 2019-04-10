---
title: Filtrar para controlar el punto de inserción en un control TextBox de formularios Windows Forms
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
ms.openlocfilehash: 43fdb023f19aa988dfef3dcd68443d6f59808472
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59341327"
---
# <a name="how-to-control-the-insertion-point-in-a-windows-forms-textbox-control"></a>Filtrar para controlar el punto de inserción en un control TextBox de formularios Windows Forms
Cuando un formulario Windows Forms <xref:System.Windows.Forms.TextBox> control recibe el foco por primera vez, es el punto de inserción predeterminado del cuadro de texto a la izquierda del texto existente. El usuario puede mover el punto de inserción con el teclado o el mouse. Si el cuadro de texto pierde y, a continuación, vuelva a obtener el foco, el punto de inserción será siempre que el usuario dejó.  
  
 En algunos casos, este comportamiento puede resultar desconcertante para el usuario. Aplicación de procesamiento de una palabra, el usuario podría esperar que los caracteres aparecen después del texto existente. En una aplicación de entrada de datos, el usuario podría esperar que los caracteres para reemplazar cualquier entrada existente. El <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> y <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> propiedades le permiten modificar el comportamiento para adaptarlo a su propósito.  
  
### <a name="to-control-the-insertion-point-in-a-textbox-control"></a>Para controlar el punto de inserción en un control TextBox  
  
1. Establezca la propiedad <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> en un valor apropiado. Cero, coloca el punto de inserción inmediatamente a la izquierda del primer carácter.  
  
2. (Opcional) Establecer el <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> propiedad a la longitud del texto que desea seleccionar.  
  
     El código siguiente siempre devuelve el punto de inserción a 0. El `TextBox1_Enter` controlador de eventos debe enlazarse al control; para obtener más información, consulte [crear controladores de eventos en Windows Forms](../creating-event-handlers-in-windows-forms.md).  
  
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
  
## <a name="making-the-insertion-point-visible-by-default"></a>Hacer Visible de forma predeterminada el punto de inserción  
 El <xref:System.Windows.Forms.TextBox> es visible de forma predeterminada en un solo si formulario nuevo punto de inserción del <xref:System.Windows.Forms.TextBox> control es el primero en el orden de tabulación. En caso contrario, el punto de inserción aparece sólo si da el <xref:System.Windows.Forms.TextBox> el foco con el teclado o el mouse.  
  
#### <a name="to-make-the-text-box-insertion-point-visible-by-default-on-a-new-form"></a>Para realizar la inserción del cuadro de texto punto visible de forma predeterminada en un formulario nuevo  
  
-   Establecer el <xref:System.Windows.Forms.TextBox> del control <xref:System.Windows.Forms.Control.TabIndex%2A> propiedad `0`.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.TextBox>
- [Información general sobre el control TextBox](textbox-control-overview-windows-forms.md)
- [Filtrar para crear un cuadro de texto de contraseña con el control TextBox de formularios Windows Forms](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Filtrar para crear un cuadro de texto de solo lectura](how-to-create-a-read-only-text-box-windows-forms.md)
- [Filtrar para insertar comillas en una cadena](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Filtrar para seleccionar texto en el control TextBox de formularios Windows Forms](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Filtrar para ver varias líneas en el control TextBox de formularios Windows Forms](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Control TextBox](textbox-control-windows-forms.md)
