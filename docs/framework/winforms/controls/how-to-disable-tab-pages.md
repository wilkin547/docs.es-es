---
title: Filtrar para deshabilitar fichas
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
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59336075"
---
# <a name="how-to-disable-tab-pages"></a><span data-ttu-id="f7bf1-102">Filtrar para deshabilitar fichas</span><span class="sxs-lookup"><span data-stu-id="f7bf1-102">How to: Disable Tab Pages</span></span>
<span data-ttu-id="f7bf1-103">En algunas ocasiones, deseará restringir el acceso a datos que están disponibles dentro de la aplicación de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f7bf1-103">On some occasions, you will want to restrict access to data that is available within your Windows Forms application.</span></span> <span data-ttu-id="f7bf1-104">Un ejemplo de esto podría ser si tiene datos que se muestran en las páginas de fichas de un control de ficha; los administradores podrían tener información sobre una página de ficha que desee restringir invitados o de los usuarios de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="f7bf1-104">One example of this might be when you have data displayed in the tab pages of a tab control; administrators could have information on a tab page that you would want to restrict from guest or lower-level users.</span></span>  
  
### <a name="to-disable-tab-pages-programmatically"></a><span data-ttu-id="f7bf1-105">Para deshabilitar páginas de fichas mediante programación</span><span class="sxs-lookup"><span data-stu-id="f7bf1-105">To disable tab pages programmatically</span></span>  
  
1. <span data-ttu-id="f7bf1-106">Escribir código para controlar el control de ficha <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> eventos.</span><span class="sxs-lookup"><span data-stu-id="f7bf1-106">Write code to handle the tab control's <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event.</span></span> <span data-ttu-id="f7bf1-107">Este es el evento que se desencadena cuando el usuario cambia de una ficha a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="f7bf1-107">This is the event that is raised when the user switches from one tab to the next.</span></span>  
  
2. <span data-ttu-id="f7bf1-108">Compruebe las credenciales.</span><span class="sxs-lookup"><span data-stu-id="f7bf1-108">Check credentials.</span></span> <span data-ttu-id="f7bf1-109">Dependiendo de la información presentada, es posible que desee comprobar el usuario haya iniciado sesión con el nombre de usuario o alguna otra forma de credenciales antes de permitir al usuario ver la pestaña.</span><span class="sxs-lookup"><span data-stu-id="f7bf1-109">Depending upon the information presented, you may want to check the user name the user has logged in with or some other form of credentials before allowing the user to view the tab.</span></span>  
  
3. <span data-ttu-id="f7bf1-110">Si el usuario tiene las credenciales adecuadas, muestre la ficha que se hizo clic.</span><span class="sxs-lookup"><span data-stu-id="f7bf1-110">If the user has appropriate credentials, display the tab that was clicked.</span></span> <span data-ttu-id="f7bf1-111">Si el usuario no tiene las credenciales adecuadas, mostrar un cuadro de mensaje u otra interfaz de usuario que indica que no tiene acceso y vuelva a la pestaña inicial.</span><span class="sxs-lookup"><span data-stu-id="f7bf1-111">If the user does not have appropriate credentials, display a message box or some other user interface indicating that they do not have access, and return to the initial tab.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f7bf1-112">Al implementar esta funcionalidad en sus aplicaciones de producción, puede realizar esta comprobación de credenciales durante el formulario <xref:System.Windows.Forms.Form.Load> eventos.</span><span class="sxs-lookup"><span data-stu-id="f7bf1-112">When you implement this functionality in your production applications, you can perform this credential check during the form's <xref:System.Windows.Forms.Form.Load> event.</span></span> <span data-ttu-id="f7bf1-113">Esto le permitirá ocultar la ficha antes de que se muestra ninguna interfaz de usuario, que es un enfoque mucho más limpio a la programación.</span><span class="sxs-lookup"><span data-stu-id="f7bf1-113">This will allow you to hide the tab before any user interface is shown, which is a much cleaner approach to programming.</span></span> <span data-ttu-id="f7bf1-114">La metodología utilizada a continuación (comprobación de credenciales y deshabilitación de la ficha durante el <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> evento) es para fines ilustrativos.</span><span class="sxs-lookup"><span data-stu-id="f7bf1-114">The methodology used below (checking credentials and disabling the tab during the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event) is for illustrative purposes.</span></span>  
  
4. <span data-ttu-id="f7bf1-115">Opcionalmente, si tiene más de dos páginas de fichas, muestre una página diferente del original.</span><span class="sxs-lookup"><span data-stu-id="f7bf1-115">Optionally, if you have more than two tab pages, display a tab page different from the original.</span></span>  
  
     <span data-ttu-id="f7bf1-116">En el ejemplo siguiente, un <xref:System.Windows.Forms.CheckBox> control se usa en lugar de comprobar las credenciales, como los criterios para el acceso a la pestaña variará por aplicación.</span><span class="sxs-lookup"><span data-stu-id="f7bf1-116">In the example below, a <xref:System.Windows.Forms.CheckBox> control is used in lieu of checking the credentials, as the criteria for access to the tab will vary by application.</span></span> <span data-ttu-id="f7bf1-117">Cuando el <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> se genera el evento, si la comprobación de credenciales es true (es decir, se activa la casilla de verificación) y la pestaña seleccionada es `TabPage2` (la ficha con la información confidencial, en este ejemplo), a continuación, `TabPage2` se muestra.</span><span class="sxs-lookup"><span data-stu-id="f7bf1-117">When the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event is raised, if the credential check is true (that is, the check box is checked) and the selected tab is `TabPage2` (the tab with the confidential information, in this example), then `TabPage2` is displayed.</span></span> <span data-ttu-id="f7bf1-118">En caso contrario, `TabPage3` se muestra y se muestra un cuadro de mensaje para el usuario, que indica que no tiene privilegios de acceso adecuados.</span><span class="sxs-lookup"><span data-stu-id="f7bf1-118">Otherwise, `TabPage3` is displayed and a message box is shown to the user, indicating they did not have appropriate access privileges.</span></span> <span data-ttu-id="f7bf1-119">El código siguiente supone un formulario con un <xref:System.Windows.Forms.CheckBox> control (`CredentialCheck`) y un <xref:System.Windows.Forms.TabControl> control con tres páginas de ficha.</span><span class="sxs-lookup"><span data-stu-id="f7bf1-119">The code below assumes a form with a <xref:System.Windows.Forms.CheckBox> control (`CredentialCheck`) and a <xref:System.Windows.Forms.TabControl> control with three tab pages.</span></span>  
  
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
  
     <span data-ttu-id="f7bf1-120">(Visual C#, Visual C++) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="f7bf1-120">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=   
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f7bf1-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7bf1-121">See also</span></span>

- [<span data-ttu-id="f7bf1-122">Información general sobre el control TabControl</span><span class="sxs-lookup"><span data-stu-id="f7bf1-122">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="f7bf1-123">Filtrar para agregar un control a una ficha</span><span class="sxs-lookup"><span data-stu-id="f7bf1-123">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="f7bf1-124">Filtrar para agregar y quitar fichas con el control TabControl de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f7bf1-124">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
- [<span data-ttu-id="f7bf1-125">Filtrar para cambiar el aspecto apariencia del control TabControl de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f7bf1-125">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
