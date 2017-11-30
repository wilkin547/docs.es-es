---
title: "Cómo: Determinar cuándo cambian los atributos de formato en el control RichTextBox de formularios Windows Forms"
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
helpviewer_keywords:
- examples [Windows Forms], text boxes
- RichTextBox control [Windows Forms], determining font changes
- text boxes [Windows Forms], determining font changes
- SelChange event
ms.assetid: bdfed015-f77a-41e5-b38f-f8629b2fa166
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0dc272e26124acf5c6bd5cf3030941c26c021c49
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-when-formatting-attributes-change-in-the-windows-forms-richtextbox-control"></a>Cómo: Determinar cuándo cambian los atributos de formato en el control RichTextBox de formularios Windows Forms
Un uso común de Windows Forms <xref:System.Windows.Forms.RichTextBox> control es aplicar formato a texto con atributos tales como opciones de fuente o estilos de párrafo. La aplicación que necesite realizar un seguimiento de los cambios en el formato del texto para mostrar una barra de herramientas, como en muchas aplicaciones de procesamiento de texto.  
  
### <a name="to-respond-to-changes-in-formatting-attributes"></a>Para responder a cambios en atributos de formato  
  
1.  Escribir código en el <xref:System.Windows.Forms.RichTextBox.SelectionChanged> controlador de eventos para realizar las acciones adecuadas según el valor del atributo. En el ejemplo siguiente se cambia la apariencia de un botón de barra de herramientas, dependiendo del valor de la <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> propiedad. El botón de barra de herramientas solo se actualizará cuando se mueve el punto de inserción en el control.  
  
     El ejemplo siguiente supone un formulario con un <xref:System.Windows.Forms.RichTextBox> control y un <xref:System.Windows.Forms.ToolBar> control que contiene un botón de barra de herramientas. Para obtener más información acerca de las barras de herramientas y botones de barra de herramientas, consulte [Cómo: agregar botones a un Control de barra de herramientas](../../../../docs/framework/winforms/controls/how-to-add-buttons-to-a-toolbar-control.md).  
  
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
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.RichTextBox.SelectionChanged>  
 <xref:System.Windows.Forms.RichTextBox>  
 [RichTextBox (control)](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
