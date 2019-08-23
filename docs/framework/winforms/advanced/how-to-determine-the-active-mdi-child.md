---
title: Procedimiento para determinar el formulario secundario MDI activo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Clipboard [Windows Forms], copying data to
- MDI [Windows Forms], child windows
- child forms
- MDI [Windows Forms], activating forms
- MDI [Windows Forms], locating focus
ms.assetid: 33880ec3-0207-4c2b-a616-ff140443cc0f
ms.openlocfilehash: 91100b37e4cae9041479b209e40034efe376df5b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946221"
---
# <a name="how-to-determine-the-active-mdi-child"></a>Procedimiento para determinar el formulario secundario MDI activo
En ocasiones, querrá proporcionar un comando que opere en el control que tenga el foco en el formulario de elemento secundario activo actualmente. Por ejemplo, supongamos que desea copiar el texto seleccionado del cuadro de texto del formulario secundario en el portapapeles. Debe crear un procedimiento que copie el texto seleccionado en el portapapeles <xref:System.Windows.Forms.Control.Click> mediante el evento del elemento de menú copiar en el menú edición estándar.  
  
 Dado que una aplicación MDI puede tener muchas instancias del mismo formulario secundario, el procedimiento debe saber qué formulario usar. Para especificar el formato correcto, use la <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> propiedad, que devuelve el formulario secundario que tiene el foco o que estuvo activo más recientemente.  
  
 Si tiene varios controles en un formulario, también debe especificar qué control está activo. Al igual <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> que la propiedad <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> , la propiedad devuelve el control con el foco en el formulario secundario activo. En el procedimiento siguiente se muestra un procedimiento de copia al que se puede llamar desde un menú de formulario secundario, un menú del formulario MDI o un botón de la barra de herramientas.  
  
### <a name="to-determine-the-active-mdi-child-to-copy-its-text-to-the-clipboard"></a>Para determinar el elemento secundario MDI activo (para copiar su texto en el portapapeles)  
  
1. Dentro de un método, copie el texto del control activo del formulario secundario activo en el portapapeles.  
  
    > [!NOTE]
    > En este ejemplo se da por supuesto que hay un`Form1`formulario MDI principal () que tiene una o varias ventanas <xref:System.Windows.Forms.RichTextBox> secundarias MDI que contienen un control. Para obtener más información, vea [crear formularios MDI principales](how-to-create-mdi-parent-forms.md).  
  
    ```vb  
    Public Sub mniCopy_Click(ByVal sender As Object, _  
       ByVal e As System.EventArgs) Handles mniCopy.Click  
  
       ' Determine the active child form.  
       Dim activeChild As Form = Me.ActiveMDIChild  
  
       ' If there is an active child form, find the active control, which  
       ' in this example should be a RichTextBox.  
       If (Not activeChild Is Nothing) Then  
          Dim theBox As RichTextBox = _  
            TryCast(activeChild.ActiveControl, RichTextBox)  
  
          If (Not theBox Is Nothing) Then  
             'Put selected text on Clipboard.  
             Clipboard.SetDataObject(theBox.SelectedText)  
          Else  
             MessageBox.Show("You need to select a RichTextBox.")  
          End If  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void mniCopy_Click (object sender, System.EventArgs e)  
    {  
       // Determine the active child form.  
       Form activeChild = this.ActiveMdiChild;  
  
       // If there is an active child form, find the active control, which  
       // in this example should be a RichTextBox.  
       if (activeChild != null)  
       {    
          try  
          {  
             RichTextBox theBox = (RichTextBox)activeChild.ActiveControl;  
             if (theBox != null)  
             {  
                // Put the selected text on the Clipboard.  
                Clipboard.SetDataObject(theBox.SelectedText);  
  
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
- [Cómo: Crear formularios MDI primarios](how-to-create-mdi-parent-forms.md)
- [Cómo: Crear formularios MDI secundarios](how-to-create-mdi-child-forms.md)
- [Cómo: Enviar datos al elemento secundario MDI activo](how-to-send-data-to-the-active-mdi-child.md)
- [Cómo: Organizar formularios MDI secundarios](how-to-arrange-mdi-child-forms.md)
