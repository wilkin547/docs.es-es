---
title: Procedimiento Establecer opciones con controles CheckBox de formularios de Windows
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
ms.openlocfilehash: a8159e9e9a2484b95399aba67b1a10b1252a4357
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54525565"
---
# <a name="how-to-set-options-with-windows-forms-checkbox-controls"></a>Procedimiento Establecer opciones con controles CheckBox de formularios de Windows
Un formulario Windows Forms <xref:System.Windows.Forms.CheckBox> control se usa para proporcionar a los usuarios True/False o Sí/No (opciones). El control muestra una marca de verificación cuando está seleccionado.  
  
### <a name="to-set-options-with-checkbox-controls"></a>Para establecer las opciones con controles CheckBox  
  
1.  Examine el valor de la <xref:System.Windows.Forms.CheckBox.Checked%2A> propiedad para determinar su estado y usar ese valor para establecer una opción.  
  
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
- [Información general sobre el control CheckBox](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)
- [Cómo: Responder a Windows Forms clics en casillas](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-checkbox-clicks.md)
- [CheckBox (control)](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)
