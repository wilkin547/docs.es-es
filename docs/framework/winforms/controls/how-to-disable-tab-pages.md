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
ms.openlocfilehash: 9074aedb81a485267dc4faff92e0fe8d0d3b467f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182173"
---
# <a name="how-to-disable-tab-pages"></a>Cómo: Deshabilitar páginas de ficha
En algunas ocasiones, querrá restringir el acceso a los datos que están disponibles en la aplicación de Windows Forms. Un ejemplo de esto podría ser cuando tiene datos mostrados en las páginas de pestañas de un control de ficha; Los administradores podrían tener información en una etiqueta que desea restringir de los usuarios invitados o de nivel inferior.  
  
### <a name="to-disable-tab-pages-programmatically"></a>Para deshabilitar las páginas de pestañas mediante programación  
  
1. Escriba código para controlar el <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> evento del control de ficha. Este es el evento que se genera cuando el usuario cambia de una pestaña a la siguiente.  
  
2. Compruebe las credenciales. Dependiendo de la información presentada, es posible que desee comprobar el nombre de usuario con el que el usuario ha iniciado sesión o alguna otra forma de credenciales antes de permitir que el usuario vea la pestaña.  
  
3. Si el usuario tiene las credenciales adecuadas, muestre la pestaña en la que se hizo clic. Si el usuario no tiene las credenciales adecuadas, muestre un cuadro de mensaje o alguna otra interfaz de usuario que indique que no tiene acceso y vuelva a la pestaña inicial.  
  
    > [!NOTE]
    > Al implementar esta funcionalidad en las aplicaciones de producción, puede realizar <xref:System.Windows.Forms.Form.Load> esta comprobación de credenciales durante el evento del formulario. Esto le permitirá ocultar la pestaña antes de que se muestre cualquier interfaz de usuario, que es un enfoque mucho más limpio para la programación. La metodología utilizada a continuación (comprobar las credenciales y deshabilitar la pestaña durante el <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> evento) tiene fines ilustrativos.  
  
4. Opcionalmente, si tiene más de dos páginas de pestañas, muestre una etiqueta diferente de la original.  
  
     En el ejemplo <xref:System.Windows.Forms.CheckBox> siguiente, se usa un control en lugar de comprobar las credenciales, ya que los criterios de acceso a la pestaña variarán según la aplicación. Cuando <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> se genera el evento, si la comprobación de credenciales es true (es `TabPage2` decir, la casilla de verificación `TabPage2` está activada) y la pestaña seleccionada es (la pestaña con la información confidencial, en este ejemplo), se muestra. De `TabPage3` lo contrario, se muestra y se muestra un cuadro de mensaje al usuario, que indica que no tenían los privilegios de acceso adecuados. El código siguiente asume un <xref:System.Windows.Forms.CheckBox> formulario`CredentialCheck`con <xref:System.Windows.Forms.TabControl> un control ( ) y un control con tres etiquetas.  
  
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
  
     (Visual C, Visual C++) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a>Consulte también

- [Información general del control TabControl](tabcontrol-control-overview-windows-forms.md)
- [Cómo: Agregar un control a una página de fichas](how-to-add-a-control-to-a-tab-page.md)
- [Agregar y quitar fichas con el control TabControl de Windows Forms](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
- [Cómo: Cambiar la apariencia del control TabControl de formularios Windows Forms](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
