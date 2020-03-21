---
title: para responder a clics en casillas
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
ms.openlocfilehash: 6ff20c443519446d3804b325924cb3c5cbedea97
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141931"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a>Cómo: Responder a clics en casillas de formularios Windows Forms
Cada vez que un <xref:System.Windows.Forms.CheckBox> usuario hace <xref:System.Windows.Forms.Control.Click> clic en un control de formularios Windows Forms, se produce el evento. Puede programar la aplicación para realizar alguna acción en función del estado de la casilla de verificación.  
  
### <a name="to-respond-to-checkbox-clicks"></a>Para responder a los clics de CheckBox  
  
1. En <xref:System.Windows.Forms.Control.Click> el controlador de <xref:System.Windows.Forms.CheckBox.Checked%2A> eventos, use la propiedad para determinar el estado del control y realice cualquier acción necesaria.  
  
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
    > Si el usuario intenta hacer <xref:System.Windows.Forms.CheckBox> doble clic en el control, cada clic se procesará por separado; es decir, <xref:System.Windows.Forms.CheckBox> el control no admite el evento de doble clic.  
  
    > [!NOTE]
    > Cuando <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> la `true` propiedad es (valor predeterminado), se <xref:System.Windows.Forms.CheckBox> selecciona o borra automáticamente cuando se hace clic en ella. De lo contrario, debe <xref:System.Windows.Forms.CheckBox.Checked%2A> establecer <xref:System.Windows.Forms.Control.Click> manualmente la propiedad cuando se produce el evento.  
  
     También puede utilizar <xref:System.Windows.Forms.CheckBox> el control para determinar un curso de acción.  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a>Para determinar un curso de acción cuando se hace clic en una casilla de verificación  
  
1. Utilice una instrucción case para <xref:System.Windows.Forms.CheckBox.CheckState%2A> consultar el valor de la propiedad para determinar un curso de acción. Cuando <xref:System.Windows.Forms.CheckBox.ThreeState%2A> la propiedad `true`se <xref:System.Windows.Forms.CheckBox.CheckState%2A> establece en , la propiedad puede devolver tres valores posibles, que representan la casilla que se está marcando, la casilla que está desactivada o un tercer estado indeterminado en el que se muestra la casilla con una apariencia atenuada para indicar que la opción no está disponible.  
  
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
    > Cuando <xref:System.Windows.Forms.CheckBox.ThreeState%2A> la propiedad `true`se <xref:System.Windows.Forms.CheckBox.Checked%2A> establece `true` en <xref:System.Windows.Forms.CheckState.Checked> , <xref:System.Windows.Forms.CheckState.Indeterminate>la propiedad devuelve tanto para .  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.CheckBox>
- [Información general sobre el control CheckBox](checkbox-control-overview-windows-forms.md)
- [Cómo: Establecer opciones con los controles CheckBox de formularios Windows Forms](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [CheckBox Control](checkbox-control-windows-forms.md)
