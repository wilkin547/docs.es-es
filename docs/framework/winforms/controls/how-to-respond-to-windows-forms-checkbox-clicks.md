---
title: para responder a clics en casillas
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
ms.openlocfilehash: 6ff20c443519446d3804b325924cb3c5cbedea97
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141931"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a><span data-ttu-id="681b1-102">Cómo: Responder a clics en casillas de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="681b1-102">How to: Respond to Windows Forms CheckBox Clicks</span></span>
<span data-ttu-id="681b1-103">Cada vez que un <xref:System.Windows.Forms.CheckBox> usuario hace <xref:System.Windows.Forms.Control.Click> clic en un control de formularios Windows Forms, se produce el evento.</span><span class="sxs-lookup"><span data-stu-id="681b1-103">Whenever a user clicks a Windows Forms <xref:System.Windows.Forms.CheckBox> control, the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span> <span data-ttu-id="681b1-104">Puede programar la aplicación para realizar alguna acción en función del estado de la casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="681b1-104">You can program your application to perform some action depending upon the state of the check box.</span></span>  
  
### <a name="to-respond-to-checkbox-clicks"></a><span data-ttu-id="681b1-105">Para responder a los clics de CheckBox</span><span class="sxs-lookup"><span data-stu-id="681b1-105">To respond to CheckBox clicks</span></span>  
  
1. <span data-ttu-id="681b1-106">En <xref:System.Windows.Forms.Control.Click> el controlador de <xref:System.Windows.Forms.CheckBox.Checked%2A> eventos, use la propiedad para determinar el estado del control y realice cualquier acción necesaria.</span><span class="sxs-lookup"><span data-stu-id="681b1-106">In the <xref:System.Windows.Forms.Control.Click> event handler, use the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine the control's state, and perform any necessary action.</span></span>  
  
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
    > <span data-ttu-id="681b1-107">Si el usuario intenta hacer <xref:System.Windows.Forms.CheckBox> doble clic en el control, cada clic se procesará por separado; es decir, <xref:System.Windows.Forms.CheckBox> el control no admite el evento de doble clic.</span><span class="sxs-lookup"><span data-stu-id="681b1-107">If the user attempts to double-click the <xref:System.Windows.Forms.CheckBox> control, each click will be processed separately; that is, the <xref:System.Windows.Forms.CheckBox> control does not support the double-click event.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="681b1-108">Cuando <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> la `true` propiedad es (valor predeterminado), se <xref:System.Windows.Forms.CheckBox> selecciona o borra automáticamente cuando se hace clic en ella.</span><span class="sxs-lookup"><span data-stu-id="681b1-108">When the <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> property is `true` (the default), the <xref:System.Windows.Forms.CheckBox> is automatically selected or cleared when it is clicked.</span></span> <span data-ttu-id="681b1-109">De lo contrario, debe <xref:System.Windows.Forms.CheckBox.Checked%2A> establecer <xref:System.Windows.Forms.Control.Click> manualmente la propiedad cuando se produce el evento.</span><span class="sxs-lookup"><span data-stu-id="681b1-109">Otherwise, you must manually set the <xref:System.Windows.Forms.CheckBox.Checked%2A> property when the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span>  
  
     <span data-ttu-id="681b1-110">También puede utilizar <xref:System.Windows.Forms.CheckBox> el control para determinar un curso de acción.</span><span class="sxs-lookup"><span data-stu-id="681b1-110">You can also use the <xref:System.Windows.Forms.CheckBox> control to determine a course of action.</span></span>  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a><span data-ttu-id="681b1-111">Para determinar un curso de acción cuando se hace clic en una casilla de verificación</span><span class="sxs-lookup"><span data-stu-id="681b1-111">To determine a course of action when a check box is clicked</span></span>  
  
1. <span data-ttu-id="681b1-112">Utilice una instrucción case para <xref:System.Windows.Forms.CheckBox.CheckState%2A> consultar el valor de la propiedad para determinar un curso de acción.</span><span class="sxs-lookup"><span data-stu-id="681b1-112">Use a case statement to query the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property to determine a course of action.</span></span> <span data-ttu-id="681b1-113">Cuando <xref:System.Windows.Forms.CheckBox.ThreeState%2A> la propiedad `true`se <xref:System.Windows.Forms.CheckBox.CheckState%2A> establece en , la propiedad puede devolver tres valores posibles, que representan la casilla que se está marcando, la casilla que está desactivada o un tercer estado indeterminado en el que se muestra la casilla con una apariencia atenuada para indicar que la opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="681b1-113">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property may return three possible values, which represent the box being checked, the box being unchecked, or a third indeterminate state in which the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
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
    > <span data-ttu-id="681b1-114">Cuando <xref:System.Windows.Forms.CheckBox.ThreeState%2A> la propiedad `true`se <xref:System.Windows.Forms.CheckBox.Checked%2A> establece `true` en <xref:System.Windows.Forms.CheckState.Checked> , <xref:System.Windows.Forms.CheckState.Indeterminate>la propiedad devuelve tanto para .</span><span class="sxs-lookup"><span data-stu-id="681b1-114">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns `true` for both <xref:System.Windows.Forms.CheckState.Checked> and <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="681b1-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="681b1-115">See also</span></span>

- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="681b1-116">Información general sobre el control CheckBox</span><span class="sxs-lookup"><span data-stu-id="681b1-116">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="681b1-117">Cómo: Establecer opciones con los controles CheckBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="681b1-117">How to: Set Options with Windows Forms CheckBox Controls</span></span>](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [<span data-ttu-id="681b1-118">CheckBox Control</span><span class="sxs-lookup"><span data-stu-id="681b1-118">CheckBox Control</span></span>](checkbox-control-windows-forms.md)
