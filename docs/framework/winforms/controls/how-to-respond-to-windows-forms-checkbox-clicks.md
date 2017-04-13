---
title: "C&#243;mo: Responder a clics en casillas de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "casillas, responder a eventos"
  - "CheckBox (control) [Windows Forms], Click (eventos)"
  - "Click (evento), CheckBox (control)"
  - "hacer doble clic"
  - "eventos [Windows Forms], Click (eventos)"
ms.assetid: c39f901e-8899-43b6-aa31-939cbf7089fb
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Responder a clics en casillas de formularios Windows Forms
Cada vez que un usuario hace clic en un control <xref:System.Windows.Forms.CheckBox> de formularios Windows Forms, se produce el evento <xref:System.Windows.Forms.Control.Click>.  Puede programar la aplicación para que ejecute una acción determinada, dependiendo del estado de la casilla.  
  
### Para responder a eventos de clic en controles CheckBox  
  
1.  En el controlador de eventos <xref:System.Windows.Forms.Control.Click>, utilice la propiedad <xref:System.Windows.Forms.CheckBox.Checked%2A> para determinar el estado del control y realizar las acciones necesarias.  
  
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
    >  Si el usuario intenta hacer doble clic en el control <xref:System.Windows.Forms.CheckBox>, cada clic se procesará por separado; es decir, el control <xref:System.Windows.Forms.CheckBox> no admite el evento doble clic.  
  
    > [!NOTE]
    >  Cuando la propiedad <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> es `true` \(el valor predeterminado\), se selecciona <xref:System.Windows.Forms.CheckBox> automáticamente o se borra cuando se hace clic en ella.  En caso contrario, será necesario establecer manualmente la propiedad <xref:System.Windows.Forms.CheckBox.Checked%2A> cuando se produzca el evento <xref:System.Windows.Forms.Control.Click>.  
  
     También puede utilizar el control <xref:System.Windows.Forms.CheckBox> para determinar una línea de acción.  
  
### Para determinar una línea de acción cuando se hace clic en una casilla  
  
1.  Utilice una instrucción case para consultar el valor de la propiedad <xref:System.Windows.Forms.CheckBox.CheckState%2A> y establecer una línea de acción.  Cuando la propiedad <xref:System.Windows.Forms.CheckBox.ThreeState%2A> se establece en `true`, la propiedad <xref:System.Windows.Forms.CheckBox.CheckState%2A> puede devolver tres posibles valores, que corresponden a la casilla activada, la casilla desactivada y un tercer estado indeterminado, en el que la casilla se muestra atenuada para indicar que la opción no está disponible.  
  
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
    >  Cuando la propiedad <xref:System.Windows.Forms.CheckBox.ThreeState%2A> se establece en `true`, la propiedad <xref:System.Windows.Forms.CheckBox.Checked%2A> devuelve `true` tanto para <xref:System.Windows.Forms.CheckState> como para <xref:System.Windows.Forms.CheckState>.  
  
## Vea también  
 <xref:System.Windows.Forms.CheckBox>   
 [Información general sobre el control CheckBox](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)   
 [Cómo: Establecer opciones con los controles CheckBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-options-with-windows-forms-checkbox-controls.md)   
 [CheckBox \(Control\)](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)