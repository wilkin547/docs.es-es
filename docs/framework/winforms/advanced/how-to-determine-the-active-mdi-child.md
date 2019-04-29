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
ms.openlocfilehash: 9b70824670b8f47a2346135cb31ad39bd55694d1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937558"
---
# <a name="how-to-determine-the-active-mdi-child"></a>Procedimiento para determinar el formulario secundario MDI activo
En ocasiones, desee proporcionar un comando que funciona en el control que tiene el foco en el formulario secundario activo actualmente. Por ejemplo, suponga que desea copiar el texto seleccionado del cuadro de texto del formulario secundario en el Portapapeles. Creación de un procedimiento que se copia el texto seleccionado en el Portapapeles usando el <xref:System.Windows.Forms.Control.Click> eventos del elemento de menú Copiar en el menú de edición estándar.  
  
 Dado que una aplicación MDI puede tener muchas instancias del mismo formulario secundario, debe saber qué formulario hay que usar el procedimiento. Para especificar el formato correcto, use el <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> propiedad, que devuelve el formulario secundario que tiene el foco o que estuvo activa más recientemente.  
  
 Cuando haya varios controles en un formulario, también deberá especificar qué control está activo. Al igual que el <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> propiedad, el <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> propiedad devuelve el control con el foco en el formulario secundario activo. El procedimiento siguiente muestra un procedimiento de copia que se puede llamar desde un menú del formulario secundario, un menú en el formulario MDI o un botón de barra de herramientas.  
  
### <a name="to-determine-the-active-mdi-child-to-copy-its-text-to-the-clipboard"></a>Para determinar el formulario secundario MDI activo (para copiar el texto en el Portapapeles)  
  
1. Dentro de un método, copie el texto del control activo del formulario secundario activo en el Portapapeles.  
  
    > [!NOTE]
    >  En este ejemplo se da por supuesto que hay un formulario primario MDI (`Form1`) que tiene una o varias ventanas secundarias MDI que contiene un <xref:System.Windows.Forms.RichTextBox> control. Para obtener más información, consulte [crear los formularios MDI primario](how-to-create-mdi-parent-forms.md).  
  
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
- [Cómo: Crear formularios principales MDI](how-to-create-mdi-parent-forms.md)
- [Cómo: Crear formularios MDI secundarios](how-to-create-mdi-child-forms.md)
- [Cómo: Enviar datos al formulario secundario MDI activo](how-to-send-data-to-the-active-mdi-child.md)
- [Cómo: Organizar formularios MDI secundarios](how-to-arrange-mdi-child-forms.md)
