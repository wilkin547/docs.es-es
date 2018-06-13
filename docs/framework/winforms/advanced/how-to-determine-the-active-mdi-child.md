---
title: 'Cómo: Determinar el formulario secundario MDI activo'
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
ms.openlocfilehash: 0b084d204361764af1b36b154acfc5b360fc977e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521723"
---
# <a name="how-to-determine-the-active-mdi-child"></a>Cómo: Determinar el formulario secundario MDI activo
En algunas ocasiones, deseará proporcionar un comando que funciona en el control que tiene el foco en el formulario secundario actualmente activo. Por ejemplo, suponga que desea copiar el texto seleccionado en el cuadro de texto del formulario secundario en el Portapapeles. Debe crear un procedimiento que copie el texto seleccionado en el Portapapeles usando el <xref:System.Windows.Forms.Control.Click> evento del elemento de menú Copiar en el menú de edición estándar.  
  
 Dado que una aplicación MDI puede tener muchas instancias del mismo formulario secundario, el procedimiento necesita saber qué formulario hay que usar. Para especificar el formato correcto, use la <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> propiedad, que devuelve el formulario secundario que tiene el foco o el que estuvo activa más recientemente.  
  
 Cuando haya varios controles en un formulario, debe especificar qué control está activo. Al igual que el <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> propiedad, el <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> propiedad devuelve el control con el foco en el formulario secundario activo. El procedimiento siguiente muestra un procedimiento de copia que se pueda llamar desde un menú de formulario secundario, un menú en el formulario MDI o un botón de barra de herramientas.  
  
### <a name="to-determine-the-active-mdi-child-to-copy-its-text-to-the-clipboard"></a>Para determinar el formulario secundario MDI activo (para copiar el texto en el Portapapeles)  
  
1.  Dentro de un método, copie el texto del control activo del formulario secundario activo en el Portapapeles.  
  
    > [!NOTE]
    >  En este ejemplo se da por supuesto que hay un formulario primario MDI (`Form1`) que tiene una o varias ventanas secundarias MDI que contiene un <xref:System.Windows.Forms.RichTextBox> control. Para obtener más información, consulte [crear formularios primarios MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md).  
  
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
 [Aplicaciones de interfaz de múltiples documentos (MDI)](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)  
 [Crear formularios principales MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [Crear formularios MDI secundarios](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [Enviar datos al formulario secundario MDI activo](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)  
 [Cómo: Organizar formularios MDI secundarios](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)
