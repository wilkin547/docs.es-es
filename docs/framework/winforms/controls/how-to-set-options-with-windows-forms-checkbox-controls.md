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
ms.openlocfilehash: 84198eab42aa02b1bb37fa16a3c4247a37f58a10
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746764"
---
# <a name="how-to-set-options-with-windows-forms-checkbox-controls"></a>Cómo: Establecer opciones con los controles CheckBox de formularios Windows Forms
Se usa un control Windows Forms <xref:System.Windows.Forms.CheckBox> para proporcionar a los usuarios opciones true/false o yes/no. El control muestra una marca de verificación cuando está seleccionada.  
  
### <a name="to-set-options-with-checkbox-controls"></a>Para establecer opciones con controles CheckBox  
  
1. Examine el valor de la propiedad <xref:System.Windows.Forms.CheckBox.Checked%2A> para determinar su estado y use ese valor para establecer una opción.  
  
     En el ejemplo de código siguiente, cuando se genera el evento de <xref:System.Windows.Forms.CheckBox.CheckedChanged> del control <xref:System.Windows.Forms.CheckBox>, la propiedad <xref:System.Windows.Forms.Control.AllowDrop%2A> del formulario se establece en `false` si la casilla está activada. Esto resulta útil en situaciones en las que desea restringir la interacción del usuario.  
  
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
- [Responder a clics en casillas de Windows Forms](how-to-respond-to-windows-forms-checkbox-clicks.md)
- [CheckBox (control)](checkbox-control-windows-forms.md)
