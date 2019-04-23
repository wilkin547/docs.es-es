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
ms.openlocfilehash: 21592fdd74c43d40310e0fcbc96af6565a42e08b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59336075"
---
# <a name="how-to-disable-tab-pages"></a>Procedimiento para deshabilitar fichas
En algunas ocasiones, deseará restringir el acceso a datos que están disponibles dentro de la aplicación de Windows Forms. Un ejemplo de esto podría ser si tiene datos que se muestran en las páginas de fichas de un control de ficha; los administradores podrían tener información sobre una página de ficha que desee restringir invitados o de los usuarios de nivel inferior.  
  
### <a name="to-disable-tab-pages-programmatically"></a>Para deshabilitar páginas de fichas mediante programación  
  
1. Escribir código para controlar el control de ficha <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> eventos. Este es el evento que se desencadena cuando el usuario cambia de una ficha a la siguiente.  
  
2. Compruebe las credenciales. Dependiendo de la información presentada, es posible que desee comprobar el usuario haya iniciado sesión con el nombre de usuario o alguna otra forma de credenciales antes de permitir al usuario ver la pestaña.  
  
3. Si el usuario tiene las credenciales adecuadas, muestre la ficha que se hizo clic. Si el usuario no tiene las credenciales adecuadas, mostrar un cuadro de mensaje u otra interfaz de usuario que indica que no tiene acceso y vuelva a la pestaña inicial.  
  
    > [!NOTE]
    >  Al implementar esta funcionalidad en sus aplicaciones de producción, puede realizar esta comprobación de credenciales durante el formulario <xref:System.Windows.Forms.Form.Load> eventos. Esto le permitirá ocultar la ficha antes de que se muestra ninguna interfaz de usuario, que es un enfoque mucho más limpio a la programación. La metodología utilizada a continuación (comprobación de credenciales y deshabilitación de la ficha durante el <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> evento) es para fines ilustrativos.  
  
4. Opcionalmente, si tiene más de dos páginas de fichas, muestre una página diferente del original.  
  
     En el ejemplo siguiente, un <xref:System.Windows.Forms.CheckBox> control se usa en lugar de comprobar las credenciales, como los criterios para el acceso a la pestaña variará por aplicación. Cuando el <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> se genera el evento, si la comprobación de credenciales es true (es decir, se activa la casilla de verificación) y la pestaña seleccionada es `TabPage2` (la ficha con la información confidencial, en este ejemplo), a continuación, `TabPage2` se muestra. En caso contrario, `TabPage3` se muestra y se muestra un cuadro de mensaje para el usuario, que indica que no tiene privilegios de acceso adecuados. El código siguiente supone un formulario con un <xref:System.Windows.Forms.CheckBox> control (`CredentialCheck`) y un <xref:System.Windows.Forms.TabControl> control con tres páginas de ficha.  
  
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

- [Información general del control TabControl](tabcontrol-control-overview-windows-forms.md)
- [Cómo: Agregar un Control a una página de ficha](how-to-add-a-control-to-a-tab-page.md)
- [Cómo: Agregar y quitar fichas con el control TabControl de formularios de Windows](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
- [Cómo: Cambiar la apariencia del control TabControl de formularios de Windows](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
