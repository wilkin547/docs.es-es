---
title: 'Cómo: Deshabilitar páginas de ficha'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tab pages [Windows Forms], hiding in forms
- TabControl control [Windows Forms], disabling pages
ms.assetid: adcc6618-8a34-4ee1-bbe3-47e732de6a59
ms.openlocfilehash: 94d8522a71fcd565ae8f994d73ffe4c46fcf7ce3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-disable-tab-pages"></a>Cómo: Deshabilitar páginas de ficha
En algunas ocasiones, deseará restringir el acceso a datos que están disponibles dentro de la aplicación de formularios Windows Forms. Un ejemplo de esto podría ser cuando tiene datos que se muestran en las fichas de un control de pestaña; los administradores podrían tener información sobre una página de ficha que desee para impedir que invitados o los usuarios de nivel inferior.  
  
### <a name="to-disable-tab-pages-programmatically"></a>Para deshabilitar páginas de fichas mediante programación  
  
1.  Escribir código para controlar el control de ficha <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> eventos. Éste es el evento que se desencadena cuando el usuario cambia de una pestaña a otra.  
  
2.  Compruebe las credenciales. Dependiendo de la información presentada, puede comprobar el usuario ha iniciado sesión con el nombre de usuario o alguna otra forma de credenciales antes de permitir al usuario ver la pestaña.  
  
3.  Si el usuario tiene las credenciales apropiadas, muestre la ficha que se hizo clic. Si el usuario no tiene las credenciales adecuadas, mostrar un cuadro de mensaje u otra interfaz de usuario que indica no tendrá acceso y vuelva a la pestaña inicial.  
  
    > [!NOTE]
    >  Al implementar esta funcionalidad en las aplicaciones de producción, puede realizar esta comprobación de credenciales durante el formulario <xref:System.Windows.Forms.Form.Load> eventos. Esto le permitirá ocultar la ficha antes de que se muestra ninguna interfaz de usuario, que es un método más apropiado para la programación. La metodología utilizada a continuación (comprobación de credenciales y deshabilitación de la ficha durante el <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> evento) es para fines ilustrativos.  
  
4.  Opcionalmente, si tiene más de dos páginas de fichas, mostrar una página de fichas diferente del original.  
  
     En el ejemplo siguiente, un <xref:System.Windows.Forms.CheckBox> control se utiliza en lugar de comprobar las credenciales, como los criterios para el acceso a la ficha varían por aplicación. Cuando el <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> se genera el evento, si la comprobación de credenciales es true (es decir, se activa la casilla de verificación) y la ficha seleccionada es `TabPage2` (la pestaña con la información confidencial, en este ejemplo), a continuación, `TabPage2` se muestra. En caso contrario, `TabPage3` se muestra y se muestra un cuadro de mensaje para el usuario, que indica que no tenía privilegios de acceso necesarios. El código siguiente supone un formulario con un <xref:System.Windows.Forms.CheckBox> control (`CredentialCheck`) y un <xref:System.Windows.Forms.TabControl> control con tres páginas de fichas.  
  
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
  
     (Visual C#, Visual C++) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=   
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Información general del control TabControl](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [Agregar un control a una página de fichas](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 [Agregar y quitar fichas con el control TabControl de Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)  
 [Cambiar la apariencia del control TabControl de Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
