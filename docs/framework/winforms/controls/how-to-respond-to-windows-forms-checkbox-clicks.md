---
title: Procedimiento Responder a Windows Forms clics en casillas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Click event [Windows Forms], CheckBox control
- CheckBox control [Windows Forms], Click events
- events [Windows Forms], Click events
- double-clicks
- check boxes [Windows Forms], responding to events
ms.assetid: c39f901e-8899-43b6-aa31-939cbf7089fb
ms.openlocfilehash: cf9a7c51c0054c34dbce40f3a2dfa68c62f3a4e2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54726330"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a>Procedimiento Responder a Windows Forms clics en casillas
Cada vez que un usuario hace clic en un formulario Windows Forms <xref:System.Windows.Forms.CheckBox> (control), el <xref:System.Windows.Forms.Control.Click> se produce el evento. Puede programar la aplicación para realizar alguna acción según el estado de la casilla de verificación.  
  
### <a name="to-respond-to-checkbox-clicks"></a>Para responder a clics en casillas  
  
1.  En el <xref:System.Windows.Forms.Control.Click> controlador de eventos, use el <xref:System.Windows.Forms.CheckBox.Checked%2A> propiedad para determinar el estado del control y realizar cualquier acción necesaria.  
  
    ```vb  
    Private Sub CheckBox1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles CheckBox1.Click  
       ' The CheckBox control's Text property is changed each time the   
       ' control is clicked, indicating a checked or unchecked state.  
       If CheckBox1.Checked = True Then  
          CheckBox1.Text = "Checked"  
       Else  
          CheckBox1.Text = "Unchecked"  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_Click(object sender, System.EventArgs e)  
    {  
       // The CheckBox control's Text property is changed each time the   
       // control is clicked, indicating a checked or unchecked state.  
       if (checkBox1.Checked)  
       {  
          checkBox1.Text = "Checked";  
       }  
       else  
       {  
          checkBox1.Text = "Unchecked";  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if (checkBox1->Checked)  
          {  
             checkBox1->Text = "Checked";  
          }  
          else  
          {  
             checkBox1->Text = "Unchecked";  
          }  
       }  
    ```  
  
    > [!NOTE]
    >  Si el usuario intenta hacer doble clic en el <xref:System.Windows.Forms.CheckBox> control, cada clic se procesará por separado; es decir, el <xref:System.Windows.Forms.CheckBox> control no admite el evento de doble clic.  
  
    > [!NOTE]
    >  Cuando el <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> propiedad es `true` (valor predeterminado), el <xref:System.Windows.Forms.CheckBox> se selecciona automáticamente o se borra cuando se hace clic en. En caso contrario, debe establecer manualmente la <xref:System.Windows.Forms.CheckBox.Checked%2A> propiedad cuando la <xref:System.Windows.Forms.Control.Click> se produce el evento.  
  
     También puede usar el <xref:System.Windows.Forms.CheckBox> control para determinar un curso de acción.  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a>Para determinar un curso de acción cuando una casilla de verificación se hace clic en  
  
1.  Utilice una instrucción case para consultar el valor de la <xref:System.Windows.Forms.CheckBox.CheckState%2A> propiedad para determinar un curso de acción. Cuando el <xref:System.Windows.Forms.CheckBox.ThreeState%2A> propiedad está establecida en `true`, el <xref:System.Windows.Forms.CheckBox.CheckState%2A> propiedad puede devolver tres valores posibles, que representan la casilla activada, la casilla desactivada y un tercer estado indeterminado, en el que se muestra el cuadro con un texto atenuado apariencia para indicar que la opción no está disponible.  
  
    ```vb  
    Private Sub CheckBox1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles CheckBox1.Click  
       Select Case CheckBox1.CheckState  
          Case CheckState.Checked  
             ' Code for checked state.  
          Case CheckState.Unchecked  
             ' Code for unchecked state.  
          Case CheckState.Indeterminate  
             ' Code for indeterminate state.  
       End Select   
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_Click(object sender, System.EventArgs e)  
    {  
       switch(checkBox1.CheckState)  
       {  
          case CheckState.Checked:  
             // Code for checked state.  
             break;  
          case CheckState.Unchecked:  
             // Code for unchecked state.  
             break;  
          case CheckState.Indeterminate:  
             // Code for indeterminate state.  
             break;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          switch(checkBox1->CheckState) {  
             case CheckState::Checked:  
                // Code for checked state.  
                break;  
             case CheckState::Unchecked:  
                // Code for unchecked state.  
                break;  
             case CheckState::Indeterminate:  
                // Code for indeterminate state.  
                break;  
          }  
       }  
    ```  
  
    > [!NOTE]
    >  Cuando el <xref:System.Windows.Forms.CheckBox.ThreeState%2A> propiedad está establecida en `true`, <xref:System.Windows.Forms.CheckBox.Checked%2A> propiedad devuelve `true` para ambos <xref:System.Windows.Forms.CheckState.Checked> y <xref:System.Windows.Forms.CheckState.Indeterminate>.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.CheckBox>
- [Información general sobre el control CheckBox](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)
- [Cómo: Establecer opciones con controles CheckBox de formularios de Windows](../../../../docs/framework/winforms/controls/how-to-set-options-with-windows-forms-checkbox-controls.md)
- [CheckBox (control)](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)
