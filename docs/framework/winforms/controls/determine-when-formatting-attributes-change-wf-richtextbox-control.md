---
title: Determinar cuándo cambian los atributos de formato en RichTextBox Control
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], text boxes
- RichTextBox control [Windows Forms], determining font changes
- text boxes [Windows Forms], determining font changes
- SelChange event
ms.assetid: bdfed015-f77a-41e5-b38f-f8629b2fa166
ms.openlocfilehash: a190c3479b58464763e0eefdd32d14e88a1f05e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142269"
---
# <a name="how-to-determine-when-formatting-attributes-change-in-the-windows-forms-richtextbox-control"></a>Cómo: Determinar cuándo cambian los atributos de formato en el control RichTextBox de formularios Windows Forms
Un uso común del <xref:System.Windows.Forms.RichTextBox> control de formularios Windows Forms es dar formato al texto con atributos como opciones de fuente o estilos de párrafo. Es posible que la aplicación deba realizar un seguimiento de cualquier cambio en el formato del texto con el fin de mostrar una barra de herramientas, como en muchas aplicaciones de procesamiento de texto.  
  
### <a name="to-respond-to-changes-in-formatting-attributes"></a>Para responder a los cambios en los atributos de formato  
  
1. Escriba código <xref:System.Windows.Forms.RichTextBox.SelectionChanged> en el controlador de eventos para realizar una acción adecuada en función del valor del atributo. En el ejemplo siguiente se cambia la apariencia de <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> un botón de barra de herramientas en función del valor de la propiedad. El botón de la barra de herramientas solo se actualizará cuando se mueva el punto de inserción en el control.  
  
     En el ejemplo siguiente se <xref:System.Windows.Forms.RichTextBox> supone <xref:System.Windows.Forms.ToolBar> un formulario con un control y un control que contiene un botón de barra de herramientas. Para obtener más información acerca de las barras de herramientas y los botones de la barra de herramientas, vea [Cómo: Agregar botones a un control de barra](how-to-add-buttons-to-a-toolbar-control.md)de herramientas .  
  
    ```vb  
    ' The following code assumes the existence of a toolbar control  
    ' with at least one toolbar button.  
    Private Sub RichTextBox1_SelectionChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles RichTextBox1.SelectionChanged  
       If RichTextBox1.SelectionBullet = True Then  
          ' Bullet button on toolbar should appear pressed  
          ToolBarButton1.Pushed = True  
       Else  
           ' Bullet button on toolbar should appear unpressed  
           ToolBarButton1.Pushed = False  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    // The following code assumes the existence of a toolbar control  
    // with at least one toolbar button.  
    private void richTextBox1_SelectionChanged(object sender,  
    System.EventArgs e)  
    {  
       if (richTextBox1.SelectionBullet == true)
       {  
          // Bullet button on toolbar should appear pressed  
          toolBarButton1.Pushed = true;  
       }  
       else
       {  
          // Bullet button on toolbar should appear unpressed  
          toolBarButton1.Pushed = false;  
       }  
    }  
    ```  
  
    ```cpp  
    // The following code assumes the existence of a toolbar control  
    // with at least one toolbar button.  
    private:  
       System::Void richTextBox1_SelectionChanged(  
          System::Object ^  sender, System::EventArgs ^  e)  
       {  
          if (richTextBox1->SelectionBullet == true)  
          {  
             // Bullet button on toolbar should appear pressed  
             toolBarButton1->Pushed = true;  
          }  
          else  
          {  
             // Bullet button on toolbar should appear unpressed  
             toolBarButton1->Pushed = false;  
          }  
       }  
    ```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.RichTextBox.SelectionChanged>
- <xref:System.Windows.Forms.RichTextBox>
- [Control RichTextBox](richtextbox-control-windows-forms.md)
- [Controles que se utilizan en Windows Forms](controls-to-use-on-windows-forms.md)
