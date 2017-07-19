---
title: "C&#243;mo: Deshabilitar p&#225;ginas de ficha | Microsoft Docs"
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
  - "páginas de fichas, ocultar en formularios"
  - "TabControl (control) [Windows Forms], deshabilitar páginas"
ms.assetid: adcc6618-8a34-4ee1-bbe3-47e732de6a59
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Deshabilitar p&#225;ginas de ficha
En algunas ocasiones, deseará restringir el acceso a datos que estén disponibles en la aplicación de Windows Forms.  Un ejemplo de esto sería cuando se visualizan datos en las páginas de ficha de un control de ficha; los administradores podrían tener información sobre una página de ficha a la que desea restringir el acceso a usuarios invitados o de un nivel inferior.  
  
### Para deshabilitar páginas de ficha mediante programación  
  
1.  Escriba código que controle el evento <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> del control de ficha.  Éste es el evento iniciado cuando el usuario cambia de una ficha a la siguiente.  
  
2.  Compruebe las credenciales.  Dependiendo de la información presentada, puede comprobar el nombre del usuario que ha iniciado la sesión u otra forma de credenciales antes de permitir al usuario que vea la ficha.  
  
3.  Si el usuario tiene las credenciales apropiadas, muestre la ficha en la que hizo clic.  Si el usuario no tiene las credenciales apropiadas, muestra un cuadro de mensaje u otra interfaz de usuario para indicar que no tiene acceso y vuelve a la pestaña inicial.  
  
    > [!NOTE]
    >  Cuando implemente esta funcionalidad en sus aplicaciones de producción, puede realizar esta comprobación de credenciales durante el evento <xref:System.Windows.Forms.Form.Load> del formulario.  Esto permitirá ocultar la pestaña antes de que se muestre otra la interfaz de usuario, que es un método mucho más apropiado en programación.  La metodología utilizada a continuación \(comprobación de credenciales y deshabilitación de la ficha durante el evento <xref:System.Windows.Forms.TabControl.SelectedIndexChanged>\) es para fines ilustrativos.  
  
4.  De manera optativa, si tiene más de dos páginas de ficha, muestre una página diferente de la original.  
  
     En el ejemplo siguiente se utiliza un control <xref:System.Windows.Forms.CheckBox> en lugar de comprobar las credenciales, puesto que los criterios de acceso a la ficha variarán según la aplicación.  Cuando se produzca el evento <xref:System.Windows.Forms.TabControl.SelectedIndexChanged>, si la comprobación de credenciales es true \(es decir, se activa la casilla\) y la ficha seleccionada es `TabPage2` \(la ficha con la información confidencial en este ejemplo\), se mostrará `TabPage2`.  De lo contrario, se mostrará `TabPage3` y un cuadro de mensaje para el usuario, indicando que no tiene permisos de acceso suficientes.  El código siguiente supone un formulario con un control <xref:System.Windows.Forms.CheckBox> \(`CredentialCheck`\) y un control <xref:System.Windows.Forms.TabControl> con tres páginas de ficha.  
  
    ```vb  
    Private Sub TabControl1_SelectedIndexChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles TabControl1.SelectedIndexChanged  
       ' Check Credentials Here  
  
       If CredentialCheck.Checked = True And _   
       TabControl1.SelectedTab Is TabPage2 Then  
          TabControl1.SelectedTab = TabPage2  
       ElseIf CredentialCheck.Checked = False _   
       And TabControl1.SelectedTab Is TabPage2 Then  
          MessageBox.Show _   
         ("Unable to load tab. You have insufficient access privileges.")  
          TabControl1.SelectedTab = TabPage3  
       End If  
    End Sub  
  
    ```  
  
    ```csharp  
    private void tabControl1_SelectedIndexChanged(object sender, System.EventArgs e)  
    {  
        // Check Credentials Here  
  
        if ((CredentialCheck.Checked == true) && (tabControl1.SelectedTab == tabPage2))   
        {  
            tabControl1.SelectedTab = tabPage2;  
        }  
        else if ((CredentialCheck.Checked == false) && (tabControl1.SelectedTab == tabPage2))  
        {  
            MessageBox.Show("Unable to load tab. You have insufficient access privileges.");  
            tabControl1.SelectedTab = tabPage3;  
        }  
    }  
  
    ```  
  
    ```cpp  
    private:  
       System::Void tabControl1_SelectedIndexChanged(  
          System::Object ^ sender,  
          System::EventArgs ^  e)  
       {  
          // Check Credentials Here  
          if ((CredentialCheck->Checked == true) &&  
              (tabControl1->SelectedTab == tabPage2))  
          {  
             tabControl1->SelectedTab = tabPage2;  
          }  
          else if ((CredentialCheck->Checked == false) &&  
                   (tabControl1->SelectedTab == tabPage2))  
          {  
             MessageBox::Show(String::Concat("Unable to load tab. ",  
                "You have insufficient access privileges."));  
             tabControl1->SelectedTab = tabPage3;  
          }  
       }  
    ```  
  
     \(Visual C\#, Visual C\+\+\) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=   
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## Vea también  
 [Información general del control TabControl](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)   
 [Cómo: Agregar un control a una página de fichas](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)   
 [Cómo: Agregar y quitar fichas con el control TabControl de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)   
 [Cómo: Cambiar la apariencia del control TabControl de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)