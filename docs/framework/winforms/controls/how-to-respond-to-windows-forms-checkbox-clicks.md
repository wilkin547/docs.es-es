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
ms.openlocfilehash: ba2afb52939a6274978ce725dac19b5622419b99
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735666"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a>Cómo: Responder a clics en casillas de Windows Forms
Cada vez que un usuario hace clic en un control de <xref:System.Windows.Forms.CheckBox> de Windows Forms, se produce el evento <xref:System.Windows.Forms.Control.Click>. Puede programar la aplicación para realizar alguna acción en función del estado de la casilla.  
  
### <a name="to-respond-to-checkbox-clicks"></a>Para responder a clics en casillas  
  
1. En el controlador de eventos <xref:System.Windows.Forms.Control.Click>, utilice la propiedad <xref:System.Windows.Forms.CheckBox.Checked%2A> para determinar el estado del control y realizar las acciones necesarias.  
  
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
    > Si el usuario intenta hacer doble clic en el control <xref:System.Windows.Forms.CheckBox>, cada clic se procesará por separado. es decir, el control <xref:System.Windows.Forms.CheckBox> no admite el evento de doble clic.  
  
    > [!NOTE]
    > Cuando se `true` la propiedad <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> (valor predeterminado), el <xref:System.Windows.Forms.CheckBox> se selecciona o borra automáticamente al hacer clic en él. De lo contrario, debe establecer manualmente la propiedad <xref:System.Windows.Forms.CheckBox.Checked%2A> cuando se produce el evento <xref:System.Windows.Forms.Control.Click>.  
  
     También puede usar el control <xref:System.Windows.Forms.CheckBox> para determinar una línea de acción.  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a>Para determinar una línea de acción al hacer clic en una casilla  
  
1. Use una instrucción Case para consultar el valor de la propiedad <xref:System.Windows.Forms.CheckBox.CheckState%2A> para determinar un curso de acción. Cuando la propiedad <xref:System.Windows.Forms.CheckBox.ThreeState%2A> está establecida en `true`, la propiedad <xref:System.Windows.Forms.CheckBox.CheckState%2A> puede devolver tres valores posibles, que representan el cuadro que se está comprobando, el cuadro desactivado o un tercer estado indeterminado en el que se muestra el cuadro con una apariencia atenuada para indicar que la opción no está disponible.  
  
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
    > Cuando la propiedad <xref:System.Windows.Forms.CheckBox.ThreeState%2A> está establecida en `true`, la propiedad <xref:System.Windows.Forms.CheckBox.Checked%2A> devuelve `true` para <xref:System.Windows.Forms.CheckState.Checked> y <xref:System.Windows.Forms.CheckState.Indeterminate>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.CheckBox>
- [Información general sobre el control CheckBox](checkbox-control-overview-windows-forms.md)
- [Establecer opciones con los controles CheckBox de formularios Windows Forms](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [CheckBox (control)](checkbox-control-windows-forms.md)
