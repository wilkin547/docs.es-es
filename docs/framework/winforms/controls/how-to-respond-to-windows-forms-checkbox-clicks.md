---
title: Filtrar Responder a Windows Forms clics en casillas
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
ms.openlocfilehash: fff08bebf4e0eeea7dff8146ed8805e9d71247da
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57724520"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a><span data-ttu-id="f3d6e-102">Filtrar Responder a Windows Forms clics en casillas</span><span class="sxs-lookup"><span data-stu-id="f3d6e-102">How to: Respond to Windows Forms CheckBox Clicks</span></span>
<span data-ttu-id="f3d6e-103">Cada vez que un usuario hace clic en un formulario Windows Forms <xref:System.Windows.Forms.CheckBox> (control), el <xref:System.Windows.Forms.Control.Click> se produce el evento.</span><span class="sxs-lookup"><span data-stu-id="f3d6e-103">Whenever a user clicks a Windows Forms <xref:System.Windows.Forms.CheckBox> control, the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span> <span data-ttu-id="f3d6e-104">Puede programar la aplicación para realizar alguna acción según el estado de la casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="f3d6e-104">You can program your application to perform some action depending upon the state of the check box.</span></span>  
  
### <a name="to-respond-to-checkbox-clicks"></a><span data-ttu-id="f3d6e-105">Para responder a clics en casillas</span><span class="sxs-lookup"><span data-stu-id="f3d6e-105">To respond to CheckBox clicks</span></span>  
  
1.  <span data-ttu-id="f3d6e-106">En el <xref:System.Windows.Forms.Control.Click> controlador de eventos, use el <xref:System.Windows.Forms.CheckBox.Checked%2A> propiedad para determinar el estado del control y realizar cualquier acción necesaria.</span><span class="sxs-lookup"><span data-stu-id="f3d6e-106">In the <xref:System.Windows.Forms.Control.Click> event handler, use the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine the control's state, and perform any necessary action.</span></span>  
  
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
    >  <span data-ttu-id="f3d6e-107">Si el usuario intenta hacer doble clic en el <xref:System.Windows.Forms.CheckBox> control, cada clic se procesará por separado; es decir, el <xref:System.Windows.Forms.CheckBox> control no admite el evento de doble clic.</span><span class="sxs-lookup"><span data-stu-id="f3d6e-107">If the user attempts to double-click the <xref:System.Windows.Forms.CheckBox> control, each click will be processed separately; that is, the <xref:System.Windows.Forms.CheckBox> control does not support the double-click event.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f3d6e-108">Cuando el <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> propiedad es `true` (valor predeterminado), el <xref:System.Windows.Forms.CheckBox> se selecciona automáticamente o se borra cuando se hace clic en.</span><span class="sxs-lookup"><span data-stu-id="f3d6e-108">When the <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> property is `true` (the default), the <xref:System.Windows.Forms.CheckBox> is automatically selected or cleared when it is clicked.</span></span> <span data-ttu-id="f3d6e-109">En caso contrario, debe establecer manualmente la <xref:System.Windows.Forms.CheckBox.Checked%2A> propiedad cuando la <xref:System.Windows.Forms.Control.Click> se produce el evento.</span><span class="sxs-lookup"><span data-stu-id="f3d6e-109">Otherwise, you must manually set the <xref:System.Windows.Forms.CheckBox.Checked%2A> property when the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span>  
  
     <span data-ttu-id="f3d6e-110">También puede usar el <xref:System.Windows.Forms.CheckBox> control para determinar un curso de acción.</span><span class="sxs-lookup"><span data-stu-id="f3d6e-110">You can also use the <xref:System.Windows.Forms.CheckBox> control to determine a course of action.</span></span>  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a><span data-ttu-id="f3d6e-111">Para determinar un curso de acción cuando una casilla de verificación se hace clic en</span><span class="sxs-lookup"><span data-stu-id="f3d6e-111">To determine a course of action when a check box is clicked</span></span>  
  
1.  <span data-ttu-id="f3d6e-112">Utilice una instrucción case para consultar el valor de la <xref:System.Windows.Forms.CheckBox.CheckState%2A> propiedad para determinar un curso de acción.</span><span class="sxs-lookup"><span data-stu-id="f3d6e-112">Use a case statement to query the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property to determine a course of action.</span></span> <span data-ttu-id="f3d6e-113">Cuando el <xref:System.Windows.Forms.CheckBox.ThreeState%2A> propiedad está establecida en `true`, el <xref:System.Windows.Forms.CheckBox.CheckState%2A> propiedad puede devolver tres valores posibles, que representan la casilla activada, la casilla desactivada y un tercer estado indeterminado, en el que se muestra el cuadro con un texto atenuado apariencia para indicar que la opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="f3d6e-113">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property may return three possible values, which represent the box being checked, the box being unchecked, or a third indeterminate state in which the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
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
    >  <span data-ttu-id="f3d6e-114">Cuando el <xref:System.Windows.Forms.CheckBox.ThreeState%2A> propiedad está establecida en `true`, <xref:System.Windows.Forms.CheckBox.Checked%2A> propiedad devuelve `true` para ambos <xref:System.Windows.Forms.CheckState.Checked> y <xref:System.Windows.Forms.CheckState.Indeterminate>.</span><span class="sxs-lookup"><span data-stu-id="f3d6e-114">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns `true` for both <xref:System.Windows.Forms.CheckState.Checked> and <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3d6e-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3d6e-115">See also</span></span>
- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="f3d6e-116">Información general sobre el control CheckBox</span><span class="sxs-lookup"><span data-stu-id="f3d6e-116">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="f3d6e-117">Cómo: Establecer opciones con controles CheckBox de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="f3d6e-117">How to: Set Options with Windows Forms CheckBox Controls</span></span>](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [<span data-ttu-id="f3d6e-118">CheckBox (control)</span><span class="sxs-lookup"><span data-stu-id="f3d6e-118">CheckBox Control</span></span>](checkbox-control-windows-forms.md)
