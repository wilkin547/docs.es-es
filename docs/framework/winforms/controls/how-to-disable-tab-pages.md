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
ms.locfileid: "33534272"
---
# <a name="how-to-disable-tab-pages"></a><span data-ttu-id="492f0-102">Cómo: Deshabilitar páginas de ficha</span><span class="sxs-lookup"><span data-stu-id="492f0-102">How to: Disable Tab Pages</span></span>
<span data-ttu-id="492f0-103">En algunas ocasiones, deseará restringir el acceso a datos que están disponibles dentro de la aplicación de formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="492f0-103">On some occasions, you will want to restrict access to data that is available within your Windows Forms application.</span></span> <span data-ttu-id="492f0-104">Un ejemplo de esto podría ser cuando tiene datos que se muestran en las fichas de un control de pestaña; los administradores podrían tener información sobre una página de ficha que desee para impedir que invitados o los usuarios de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="492f0-104">One example of this might be when you have data displayed in the tab pages of a tab control; administrators could have information on a tab page that you would want to restrict from guest or lower-level users.</span></span>  
  
### <a name="to-disable-tab-pages-programmatically"></a><span data-ttu-id="492f0-105">Para deshabilitar páginas de fichas mediante programación</span><span class="sxs-lookup"><span data-stu-id="492f0-105">To disable tab pages programmatically</span></span>  
  
1.  <span data-ttu-id="492f0-106">Escribir código para controlar el control de ficha <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> eventos.</span><span class="sxs-lookup"><span data-stu-id="492f0-106">Write code to handle the tab control's <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event.</span></span> <span data-ttu-id="492f0-107">Éste es el evento que se desencadena cuando el usuario cambia de una pestaña a otra.</span><span class="sxs-lookup"><span data-stu-id="492f0-107">This is the event that is raised when the user switches from one tab to the next.</span></span>  
  
2.  <span data-ttu-id="492f0-108">Compruebe las credenciales.</span><span class="sxs-lookup"><span data-stu-id="492f0-108">Check credentials.</span></span> <span data-ttu-id="492f0-109">Dependiendo de la información presentada, puede comprobar el usuario ha iniciado sesión con el nombre de usuario o alguna otra forma de credenciales antes de permitir al usuario ver la pestaña.</span><span class="sxs-lookup"><span data-stu-id="492f0-109">Depending upon the information presented, you may want to check the user name the user has logged in with or some other form of credentials before allowing the user to view the tab.</span></span>  
  
3.  <span data-ttu-id="492f0-110">Si el usuario tiene las credenciales apropiadas, muestre la ficha que se hizo clic.</span><span class="sxs-lookup"><span data-stu-id="492f0-110">If the user has appropriate credentials, display the tab that was clicked.</span></span> <span data-ttu-id="492f0-111">Si el usuario no tiene las credenciales adecuadas, mostrar un cuadro de mensaje u otra interfaz de usuario que indica no tendrá acceso y vuelva a la pestaña inicial.</span><span class="sxs-lookup"><span data-stu-id="492f0-111">If the user does not have appropriate credentials, display a message box or some other user interface indicating that they do not have access, and return to the initial tab.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="492f0-112">Al implementar esta funcionalidad en las aplicaciones de producción, puede realizar esta comprobación de credenciales durante el formulario <xref:System.Windows.Forms.Form.Load> eventos.</span><span class="sxs-lookup"><span data-stu-id="492f0-112">When you implement this functionality in your production applications, you can perform this credential check during the form's <xref:System.Windows.Forms.Form.Load> event.</span></span> <span data-ttu-id="492f0-113">Esto le permitirá ocultar la ficha antes de que se muestra ninguna interfaz de usuario, que es un método más apropiado para la programación.</span><span class="sxs-lookup"><span data-stu-id="492f0-113">This will allow you to hide the tab before any user interface is shown, which is a much cleaner approach to programming.</span></span> <span data-ttu-id="492f0-114">La metodología utilizada a continuación (comprobación de credenciales y deshabilitación de la ficha durante el <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> evento) es para fines ilustrativos.</span><span class="sxs-lookup"><span data-stu-id="492f0-114">The methodology used below (checking credentials and disabling the tab during the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event) is for illustrative purposes.</span></span>  
  
4.  <span data-ttu-id="492f0-115">Opcionalmente, si tiene más de dos páginas de fichas, mostrar una página de fichas diferente del original.</span><span class="sxs-lookup"><span data-stu-id="492f0-115">Optionally, if you have more than two tab pages, display a tab page different from the original.</span></span>  
  
     <span data-ttu-id="492f0-116">En el ejemplo siguiente, un <xref:System.Windows.Forms.CheckBox> control se utiliza en lugar de comprobar las credenciales, como los criterios para el acceso a la ficha varían por aplicación.</span><span class="sxs-lookup"><span data-stu-id="492f0-116">In the example below, a <xref:System.Windows.Forms.CheckBox> control is used in lieu of checking the credentials, as the criteria for access to the tab will vary by application.</span></span> <span data-ttu-id="492f0-117">Cuando el <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> se genera el evento, si la comprobación de credenciales es true (es decir, se activa la casilla de verificación) y la ficha seleccionada es `TabPage2` (la pestaña con la información confidencial, en este ejemplo), a continuación, `TabPage2` se muestra.</span><span class="sxs-lookup"><span data-stu-id="492f0-117">When the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event is raised, if the credential check is true (that is, the check box is checked) and the selected tab is `TabPage2` (the tab with the confidential information, in this example), then `TabPage2` is displayed.</span></span> <span data-ttu-id="492f0-118">En caso contrario, `TabPage3` se muestra y se muestra un cuadro de mensaje para el usuario, que indica que no tenía privilegios de acceso necesarios.</span><span class="sxs-lookup"><span data-stu-id="492f0-118">Otherwise, `TabPage3` is displayed and a message box is shown to the user, indicating they did not have appropriate access privileges.</span></span> <span data-ttu-id="492f0-119">El código siguiente supone un formulario con un <xref:System.Windows.Forms.CheckBox> control (`CredentialCheck`) y un <xref:System.Windows.Forms.TabControl> control con tres páginas de fichas.</span><span class="sxs-lookup"><span data-stu-id="492f0-119">The code below assumes a form with a <xref:System.Windows.Forms.CheckBox> control (`CredentialCheck`) and a <xref:System.Windows.Forms.TabControl> control with three tab pages.</span></span>  
  
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
  
     <span data-ttu-id="492f0-120">(Visual C#, Visual C++) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="492f0-120">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=   
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="492f0-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="492f0-121">See Also</span></span>  
 [<span data-ttu-id="492f0-122">Información general del control TabControl</span><span class="sxs-lookup"><span data-stu-id="492f0-122">TabControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [<span data-ttu-id="492f0-123">Agregar un control a una página de fichas</span><span class="sxs-lookup"><span data-stu-id="492f0-123">How to: Add a Control to a Tab Page</span></span>](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 [<span data-ttu-id="492f0-124">Agregar y quitar fichas con el control TabControl de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="492f0-124">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)  
 [<span data-ttu-id="492f0-125">Cambiar la apariencia del control TabControl de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="492f0-125">How to: Change the Appearance of the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
