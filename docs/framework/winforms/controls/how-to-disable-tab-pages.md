---
title: Procedimiento para deshabilitar fichas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tab pages [Windows Forms], hiding in forms
- TabControl control [Windows Forms], disabling pages
ms.assetid: adcc6618-8a34-4ee1-bbe3-47e732de6a59
ms.openlocfilehash: 888228c28dce591b237be16b6a321afee0105208
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967147"
---
# <a name="how-to-disable-tab-pages"></a>Procedimiento para deshabilitar fichas
En algunas ocasiones, deseará restringir el acceso a los datos que están disponibles en la aplicación Windows Forms. Un ejemplo de esto podría ser cuando se muestran datos en las páginas de fichas de un control de ficha. los administradores pueden tener información en una página de ficha que desea restringir a usuarios de nivel inferior o invitado.  
  
### <a name="to-disable-tab-pages-programmatically"></a>Para deshabilitar las páginas de fichas mediante programación  
  
1. Escriba código para controlar el evento del control <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> de pestaña. Este es el evento que se genera cuando el usuario cambia de una pestaña a la siguiente.  
  
2. Compruebe las credenciales. En función de la información presentada, puede que desee comprobar el nombre de usuario con el que ha iniciado sesión el usuario o alguna otra forma de credenciales antes de permitir que el usuario vea la ficha.  
  
3. Si el usuario tiene las credenciales apropiadas, muestre la ficha en la que se hizo clic. Si el usuario no tiene las credenciales adecuadas, muestre un cuadro de mensaje o alguna otra interfaz de usuario que indique que no tienen acceso y vuelva a la pestaña inicial.  
  
    > [!NOTE]
    > Al implementar esta funcionalidad en las aplicaciones de producción, puede realizar esta comprobación de credenciales durante el evento <xref:System.Windows.Forms.Form.Load> del formulario. Esto le permitirá ocultar la pestaña antes de que se muestre cualquier interfaz de usuario, que es un enfoque mucho más limpio para la programación. La metodología que se usa a continuación (comprobar las credenciales y deshabilitar la pestaña durante el <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> evento) es con fines ilustrativos.  
  
4. Opcionalmente, si tiene más de dos páginas de fichas, muestre una página de ficha diferente de la original.  
  
     En el ejemplo siguiente, se <xref:System.Windows.Forms.CheckBox> usa un control en lugar de comprobar las credenciales, ya que los criterios para el acceso a la pestaña variarán en función de la aplicación. Cuando se <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> genera el evento, si la comprobación de credenciales es true (es decir, la casilla está activada) y la pestaña seleccionada `TabPage2` es (en `TabPage2` este ejemplo, la pestaña con la información confidencial), se muestra. De lo `TabPage3` contrario, se muestra y se muestra un cuadro de mensaje al usuario, que indica que no tenía los privilegios de acceso adecuados. En el código siguiente se presupone un formulario <xref:System.Windows.Forms.CheckBox> con un`CredentialCheck`control () <xref:System.Windows.Forms.TabControl> y un control con tres páginas de fichas.  
  
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
  
     (Visual C#, visual C++) Coloque el siguiente código en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=   
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a>Vea también

- [Información general del control TabControl](tabcontrol-control-overview-windows-forms.md)
- [Cómo: Agregar un control a una página de fichas](how-to-add-a-control-to-a-tab-page.md)
- [Cómo: Agregar y quitar pestañas con el Windows Forms TabControl](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
- [Procedimientos: Cambiar la apariencia de la Windows Forms TabControl](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
