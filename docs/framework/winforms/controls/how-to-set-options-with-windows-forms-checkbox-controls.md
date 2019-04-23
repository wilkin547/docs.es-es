---
title: Procedimiento para establecer opciones con los controles CheckBox de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- checked
helpviewer_keywords:
- CheckBox control [Windows Forms], checked state
- check boxes [Windows Forms], using to set options
- CheckBox control [Windows Forms], using to set options
ms.assetid: 2ac70498-7e3e-4e07-8901-ccabaeb5fd3e
ms.openlocfilehash: 881996563acef36a1981ca6236c155b8fc56ef0a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59307327"
---
# <a name="how-to-set-options-with-windows-forms-checkbox-controls"></a>Procedimiento para establecer opciones con los controles CheckBox de formularios Windows Forms
Un formulario Windows Forms <xref:System.Windows.Forms.CheckBox> control se usa para proporcionar a los usuarios True/False o Sí/No (opciones). El control muestra una marca de verificación cuando está seleccionado.  
  
### <a name="to-set-options-with-checkbox-controls"></a>Para establecer las opciones con controles CheckBox  
  
1. Examine el valor de la <xref:System.Windows.Forms.CheckBox.Checked%2A> propiedad para determinar su estado y usar ese valor para establecer una opción.  
  
     En el ejemplo de código siguiente, cuando el <xref:System.Windows.Forms.CheckBox> del control <xref:System.Windows.Forms.CheckBox.CheckedChanged> se provoca el evento, el formulario <xref:System.Windows.Forms.Control.AllowDrop%2A> propiedad está establecida en `false` si está activada la casilla de verificación. Esto es útil en situaciones donde desea restringir la interacción del usuario.  
  
    ```vb  
    Private Sub CheckBox1_CheckedChanged(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles CheckBox1.CheckedChanged  
       ' Determine the CheckState of the check box.  
       If CheckBox1.CheckState = CheckState.Checked Then  
          ' If checked, do not allow items to be dragged onto the form.  
          Me.AllowDrop = False  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_CheckedChanged(object sender, System.EventArgs e)  
    {  
       // Determine the CheckState of the check box.  
       if (checkBox1.CheckState == CheckState.Checked)   
       {  
          // If checked, do not allow items to be dragged onto the form.  
          this.AllowDrop = false;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // Determine the CheckState of the check box.  
          if (checkBox1->CheckState == CheckState::Checked)   
          {  
             // If checked, do not allow items to be dragged onto the form.  
             this->AllowDrop = false;  
          }  
       }  
    ```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.CheckBox>
- [Información general sobre el control CheckBox](checkbox-control-overview-windows-forms.md)
- [Cómo: Responder a Windows Forms clics en casillas](how-to-respond-to-windows-forms-checkbox-clicks.md)
- [CheckBox (control)](checkbox-control-windows-forms.md)
