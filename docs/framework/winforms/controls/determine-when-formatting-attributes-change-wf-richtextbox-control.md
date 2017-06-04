---
title: "C&#243;mo: Determinar cu&#225;ndo cambian los atributos de formato en el control RichTextBox de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ejemplos [Windows Forms], cuadros de texto"
  - "RichTextBox (control) [Windows Forms], determinar cambios de fuente"
  - "SelBold (propiedad)"
  - "SelChange (evento)"
  - "cuadros de texto, determinar cambios de fuente"
ms.assetid: bdfed015-f77a-41e5-b38f-f8629b2fa166
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Determinar cu&#225;ndo cambian los atributos de formato en el control RichTextBox de formularios Windows Forms
Un uso común del control <xref:System.Windows.Forms.RichTextBox> de formularios Windows Forms consiste en dar formato a texto con atributos tales como opciones de fuente o estilos de párrafo.  Es posible que la aplicación necesite hacer un seguimiento de los cambios de formato del texto para mostrar una barra de herramientas, como ocurre en muchas aplicaciones de procesamiento de textos.  
  
### Para responder a los cambios en los atributos de formato  
  
1.  Escriba código en el controlador del evento <xref:System.Windows.Forms.RichTextBox.SelectionChanged> para ejecutar la acción adecuada según el valor del atributo.  El ejemplo siguiente cambia la apariencia de un botón de la barra de herramientas según el valor de la propiedad <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A>.  El botón de la barra de herramientas se actualizará sólo cuando el punto de inserción se desplace al control.  
  
     El ejemplo siguiente supone un formulario con un control <xref:System.Windows.Forms.RichTextBox> y un control <xref:System.Windows.Forms.ToolBar> que contiene un botón de barra de herramientas.  Para obtener más información sobre las barras de herramientas y los botones de barra de herramientas, vea [Cómo: Agregar botones a un control ToolBar](../../../../docs/framework/winforms/controls/how-to-add-buttons-to-a-toolbar-control.md).  
  
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
  
## Vea también  
 <xref:System.Windows.Forms.RichTextBox.SelectionChanged>   
 <xref:System.Windows.Forms.RichTextBox>   
 [RichTextBox \(Control\)](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)   
 [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)