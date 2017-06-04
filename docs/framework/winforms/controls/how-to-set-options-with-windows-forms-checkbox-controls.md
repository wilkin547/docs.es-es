---
title: "C&#243;mo: Establecer opciones con los controles CheckBox de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "checked"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "casillas, utilizar para establecer opciones"
  - "CheckBox (control) [Windows Forms], estado activado"
  - "CheckBox (control) [Windows Forms], utilizar para establecer opciones"
ms.assetid: 2ac70498-7e3e-4e07-8901-ccabaeb5fd3e
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Establecer opciones con los controles CheckBox de formularios Windows Forms
El control <xref:System.Windows.Forms.CheckBox> de los formularios Windows Forms se utiliza para ofrecer a los usuarios opciones de tipo Verdadero\/Falso o Sí\/No.  El control muestra una marca de verificación cuando está seleccionado.  
  
### Para establecer opciones con controles CheckBox  
  
1.  Examine el valor de la propiedad <xref:System.Windows.Forms.CheckBox.Checked%2A> para determinar su estado y utilice este valor para establecer una opción.  
  
     En el ejemplo de código siguiente, cuando se produce el evento <xref:System.Windows.Forms.CheckBox.CheckedChanged> del control <xref:System.Windows.Forms.CheckBox>, la propiedad <xref:System.Windows.Forms.Control.AllowDrop%2A> del formulario se establece en `false` si se activa la casilla.  Esto es útil en situaciones en las que se desee limitar la interacción del usuario.  
  
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
  
## Vea también  
 <xref:System.Windows.Forms.CheckBox>   
 [Información general sobre el control CheckBox](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)   
 [Cómo: Responder a clics en casillas de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-checkbox-clicks.md)   
 [CheckBox \(Control\)](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)