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
ms.openlocfilehash: 57491faa10c182630d41565ba236d65e393929b3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182544"
---
# <a name="how-to-determine-the-active-mdi-child"></a>Cómo: Determinar el formulario secundario MDI activo
En ocasiones, querrá proporcionar un comando que funcione en el control que se centra en el formulario secundario activo actualmente. Por ejemplo, supongamos que desea copiar el texto seleccionado del cuadro de texto del formulario secundario al Portapapeles. Crearía un procedimiento que copie el texto <xref:System.Windows.Forms.Control.Click> seleccionado en el Portapapeles utilizando el evento del elemento de menú Copiar del menú Edición estándar.  
  
 Dado que una aplicación MDI puede tener muchas instancias del mismo formulario secundario, el procedimiento debe saber qué formulario usar. Para especificar el formulario <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> correcto, utilice la propiedad, que devuelve el formulario secundario que tiene el foco o que se ha activo más recientemente.  
  
 Cuando tiene varios controles en un formulario, también debe especificar qué control está activo. Al <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> igual que <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> la propiedad, la propiedad devuelve el control con el foco en el formulario secundario activo. El procedimiento siguiente ilustra un procedimiento de copia que se puede llamar desde un menú de formulario secundario, un menú en el formulario MDI o un botón de barra de herramientas.  
  
### <a name="to-determine-the-active-mdi-child-to-copy-its-text-to-the-clipboard"></a>Para determinar el elemento secundario MDI activo (para copiar su texto en el Portapapeles)  
  
1. Dentro de un método, copie el texto del control activo del formulario secundario activo en el Portapapeles.  
  
    > [!NOTE]
    > En este ejemplo se supone que`Form1`hay un formulario primario MDI ( <xref:System.Windows.Forms.RichTextBox> ) que tiene una o varias ventanas secundarias MDI que contienen un control. Para obtener más información, consulte Creación de [formularios primarios MDI](how-to-create-mdi-parent-forms.md).  
  
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
  
## <a name="see-also"></a>Consulte también

- [Aplicaciones de interfaz de múltiples documentos (MDI)](multiple-document-interface-mdi-applications.md)
- [Cómo: Crear formularios principales MDI](how-to-create-mdi-parent-forms.md)
- [Cómo: Crear formularios MDI secundarios](how-to-create-mdi-child-forms.md)
- [Cómo: Enviar datos al formulario secundario MDI activo](how-to-send-data-to-the-active-mdi-child.md)
- [Cómo: Organizar formularios MDI secundarios](how-to-arrange-mdi-child-forms.md)
