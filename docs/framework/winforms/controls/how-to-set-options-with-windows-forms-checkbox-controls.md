---
title: para establecer opciones con controles de casilla
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
ms.openlocfilehash: 00b467836d8e60aeee51a010a6384abf7dd73c56
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141853"
---
# <a name="how-to-set-options-with-windows-forms-checkbox-controls"></a>Cómo: Establecer opciones con los controles CheckBox de formularios Windows Forms
Un control <xref:System.Windows.Forms.CheckBox> de formularios Windows Forms se usa para proporcionar a los usuarios True/False o Sí/No opciones. El control muestra una marca de verificación cuando se selecciona.  
  
### <a name="to-set-options-with-checkbox-controls"></a>Para configurar opciones con controles CheckBox  
  
1. Examine el valor <xref:System.Windows.Forms.CheckBox.Checked%2A> de la propiedad para determinar su estado y use ese valor para establecer una opción.  
  
     En el ejemplo de <xref:System.Windows.Forms.CheckBox> código siguiente, cuando se genera el evento del <xref:System.Windows.Forms.CheckBox.CheckedChanged> control, la propiedad del <xref:System.Windows.Forms.Control.AllowDrop%2A> formulario se establece `false` en si la casilla de verificación está activada. Esto es útil para situaciones en las que desea restringir la interacción del usuario.  
  
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
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.CheckBox>
- [Información general sobre el control CheckBox](checkbox-control-overview-windows-forms.md)
- [Cómo: Responder a clics en casillas de formularios Windows Forms](how-to-respond-to-windows-forms-checkbox-clicks.md)
- [CheckBox Control](checkbox-control-windows-forms.md)
