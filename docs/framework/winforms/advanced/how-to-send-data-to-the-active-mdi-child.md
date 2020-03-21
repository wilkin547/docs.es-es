---
title: 'Cómo: Enviar datos al formulario secundario MDI activo'
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
ms.openlocfilehash: 563be8494cb84dc74b45985d3ba74e4b6a07eb8a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182495"
---
# <a name="how-to-send-data-to-the-active-mdi-child"></a>Cómo: Enviar datos al formulario secundario MDI activo
A menudo, en el contexto de las aplicaciones de interfaz de varios [documentos (MDI),](multiple-document-interface-mdi-applications.md)deberá enviar datos a la ventana secundaria activa, como cuando el usuario pega datos desde el Portapapeles en una aplicación MDI.  
  
> [!NOTE]
> Para obtener información sobre cómo comprobar qué ventana secundaria tiene el foco y enviar su contenido al Portapapeles, consulte [Determinación del elemento secundario MDI activo](how-to-determine-the-active-mdi-child.md).  
  
### <a name="to-send-data-to-the-active-mdi-child-window-from-the-clipboard"></a>Para enviar datos a la ventana secundaria MDI activa desde el Portapapeles  
  
1. Dentro de un método, copie el texto del Portapapeles en el control activo del formulario secundario activo.  
  
    > [!NOTE]
    > En este ejemplo se supone que`Form1`hay un formulario primario MDI ( <xref:System.Windows.Forms.RichTextBox> ) que tiene una o varias ventanas secundarias MDI que contienen un control. Para obtener más información, consulte Creación de [formularios primarios MDI](how-to-create-mdi-parent-forms.md).  
  
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
  
## <a name="see-also"></a>Consulte también

- [Aplicaciones de interfaz de múltiples documentos (MDI)](multiple-document-interface-mdi-applications.md)
- [Cómo: Crear formularios principales MDI](how-to-create-mdi-parent-forms.md)
- [Cómo: Crear formularios MDI secundarios](how-to-create-mdi-child-forms.md)
- [Cómo: Determinar el formulario secundario MDI activo](how-to-determine-the-active-mdi-child.md)
- [Cómo: Organizar formularios MDI secundarios](how-to-arrange-mdi-child-forms.md)
