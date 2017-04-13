---
title: "C&#243;mo: Enviar datos al formulario secundario MDI activo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "formularios secundarios"
  - "Portapapeles, obtener datos"
  - "Portapapeles, pegar"
  - "MDI, enviar datos a formularios"
ms.assetid: 1047d2fe-1235-46db-aad9-563aea1d743b
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Enviar datos al formulario secundario MDI activo
A menudo, en el contexto de las [Aplicaciones de interfaz de múltiples documentos \(MDI\)](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md), necesitará enviar datos a la ventana secundaria activa, como sucede cuando el usuario pega datos procedentes del Portapapeles en una aplicación MDI.  
  
> [!NOTE]
>  Para obtener información sobre cómo comprobar qué ventana secundaria tiene el foco y enviar su contenido al Portapapeles, vea [Determinar la ventana secundaria de MDI activa](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md).  
  
### Para enviar datos a la ventana secundaria MDI activa desde el Portapapeles  
  
1.  Dentro de un método, copie el texto del Portapapeles en el control activo del formulario secundario activo.  
  
    > [!NOTE]
    >  En este ejemplo se supone que hay un formulario primario MDI \(`Form1`\) que tiene una o varias ventanas secundarias MDI que, a su vez, contienen un control <xref:System.Windows.Forms.RichTextBox>.  Para obtener más información, vea [Crear formularios primarios MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md).  
  
    ```vb  
    Public Sub mniPaste_Click(ByVal sender As Object, _  
       ByVal e As System.EventArgs) Handles mniPaste.Click  
  
       ' Determine the active child form.  
       Dim activeChild As Form = Me.ParentForm.ActiveMDIChild  
  
       ' If there is an active child form, find the active control, which  
       ' in this example should be a RichTextBox.  
       If (Not activeChild Is Nothing) Then  
          Try  
             Dim theBox As RichTextBox = Ctype(activeChild.ActiveControl, RichTextBox)  
             If (Not theBox Is Nothing) Then  
                ' Create a new instance of the DataObject interface.  
                Dim data As IDataObject = Clipboard.GetDataObject()  
                ' If the data is text, then set the text of the   
                ' RichTextBox to the text in the clipboard.  
                If (data.GetDataPresent(DataFormats.Text)) Then  
                   theBox.SelectedText = data.GetData(DataFormats.Text).ToString()  
                End If  
             End If  
          Catch  
             MessageBox.Show("You need to select a RichTextBox.")  
          End Try  
       End If  
    End Sub  
  
    ```  
  
    ```csharp  
    protected void mniPaste_Click (object sender, System.EventArgs e)  
    {  
      // Determine the active child form.  
       Form activeChild = this.ParentForm.ActiveMdiChild;  
  
       // If there is an active child form, find the active control, which  
       // in this example should be a RichTextBox.  
       if (activeChild != null)  
       {  
          try   
          {  
             RichTextBox theBox = (RichTextBox)activeChild.ActiveControl;  
             if (theBox != null)  
             {  
                // Create a new instance of the DataObject interface.  
                IDataObject data = Clipboard.GetDataObject();  
                // If the data is text, then set the text of the   
                // RichTextBox to the text in the clipboard.  
                if (data.GetDataPresent(DataFormats.Text))  
                {  
                   theBox.SelectedText = data.GetData(DataFormats.Text).ToString();                 
                }  
             }  
          }  
          catch   
          {  
             MessageBox.Show("You need to select a RichTextBox.");  
          }  
       }  
    }  
  
    ```  
  
## Vea también  
 [Aplicaciones de interfaz de múltiples documentos \(MDI\)](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)   
 [Cómo: Crear formularios principales MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)   
 [Cómo: Crear formularios MDI secundarios](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)   
 [Cómo: Determinar el formulario secundario MDI activo](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)   
 [Cómo: Organizar formularios MDI secundarios](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)