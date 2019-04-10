---
title: Filtrar para enviar datos al formulario secundario MDI activo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- child forms
- MDI [Windows Forms], sending data to forms
- Clipboard [Windows Forms], pasting
- Clipboard [Windows Forms], getting data from
ms.assetid: 1047d2fe-1235-46db-aad9-563aea1d743b
ms.openlocfilehash: f4399d8548eff76aaa4effae6da7239cd3b0284b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59343719"
---
# <a name="how-to-send-data-to-the-active-mdi-child"></a>Filtrar para enviar datos al formulario secundario MDI activo
A menudo, en el contexto de [aplicaciones de interfaz de múltiples documentos (MDI)](multiple-document-interface-mdi-applications.md), deberá enviar datos a la ventana secundaria activa, por ejemplo, cuando el usuario pega datos desde el Portapapeles en una aplicación MDI.  
  
> [!NOTE]
>  Para obtener información sobre cómo comprobar qué ventana secundaria tiene el foco y enviar su contenido en el Portapapeles, consulte [determinar el formulario secundario MDI activo](how-to-determine-the-active-mdi-child.md).  
  
### <a name="to-send-data-to-the-active-mdi-child-window-from-the-clipboard"></a>Para enviar datos a la ventana secundaria MDI activa desde el Portapapeles  
  
1. Dentro de un método, copie el texto del Portapapeles en el control activo del formulario secundario activo.  
  
    > [!NOTE]
    >  En este ejemplo se da por supuesto que hay un formulario primario MDI (`Form1`) que tiene una o varias ventanas secundarias MDI que contiene un <xref:System.Windows.Forms.RichTextBox> control. Para obtener más información, consulte [crear los formularios MDI primario](how-to-create-mdi-parent-forms.md).  
  
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
  
## <a name="see-also"></a>Vea también

- [Aplicaciones de interfaz de múltiples documentos (MDI)](multiple-document-interface-mdi-applications.md)
- [Filtrar para crear formularios principales MDI](how-to-create-mdi-parent-forms.md)
- [Filtrar para crear formularios secundarios MDI](how-to-create-mdi-child-forms.md)
- [Filtrar para determinar el formulario secundario MDI activo](how-to-determine-the-active-mdi-child.md)
- [Filtrar para organizar formularios secundarios MDI](how-to-arrange-mdi-child-forms.md)
