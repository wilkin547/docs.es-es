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
ms.openlocfilehash: ba2afb52939a6274978ce725dac19b5622419b99
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735666"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a><span data-ttu-id="c465d-102">Cómo: Responder a clics en casillas de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c465d-102">How to: Respond to Windows Forms CheckBox Clicks</span></span>
<span data-ttu-id="c465d-103">Cada vez que un usuario hace clic en un control de <xref:System.Windows.Forms.CheckBox> de Windows Forms, se produce el evento <xref:System.Windows.Forms.Control.Click>.</span><span class="sxs-lookup"><span data-stu-id="c465d-103">Whenever a user clicks a Windows Forms <xref:System.Windows.Forms.CheckBox> control, the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span> <span data-ttu-id="c465d-104">Puede programar la aplicación para realizar alguna acción en función del estado de la casilla.</span><span class="sxs-lookup"><span data-stu-id="c465d-104">You can program your application to perform some action depending upon the state of the check box.</span></span>  
  
### <a name="to-respond-to-checkbox-clicks"></a><span data-ttu-id="c465d-105">Para responder a clics en casillas</span><span class="sxs-lookup"><span data-stu-id="c465d-105">To respond to CheckBox clicks</span></span>  
  
1. <span data-ttu-id="c465d-106">En el controlador de eventos <xref:System.Windows.Forms.Control.Click>, utilice la propiedad <xref:System.Windows.Forms.CheckBox.Checked%2A> para determinar el estado del control y realizar las acciones necesarias.</span><span class="sxs-lookup"><span data-stu-id="c465d-106">In the <xref:System.Windows.Forms.Control.Click> event handler, use the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine the control's state, and perform any necessary action.</span></span>  
  
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
    > <span data-ttu-id="c465d-107">Si el usuario intenta hacer doble clic en el control <xref:System.Windows.Forms.CheckBox>, cada clic se procesará por separado. es decir, el control <xref:System.Windows.Forms.CheckBox> no admite el evento de doble clic.</span><span class="sxs-lookup"><span data-stu-id="c465d-107">If the user attempts to double-click the <xref:System.Windows.Forms.CheckBox> control, each click will be processed separately; that is, the <xref:System.Windows.Forms.CheckBox> control does not support the double-click event.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="c465d-108">Cuando se `true` la propiedad <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> (valor predeterminado), el <xref:System.Windows.Forms.CheckBox> se selecciona o borra automáticamente al hacer clic en él.</span><span class="sxs-lookup"><span data-stu-id="c465d-108">When the <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> property is `true` (the default), the <xref:System.Windows.Forms.CheckBox> is automatically selected or cleared when it is clicked.</span></span> <span data-ttu-id="c465d-109">De lo contrario, debe establecer manualmente la propiedad <xref:System.Windows.Forms.CheckBox.Checked%2A> cuando se produce el evento <xref:System.Windows.Forms.Control.Click>.</span><span class="sxs-lookup"><span data-stu-id="c465d-109">Otherwise, you must manually set the <xref:System.Windows.Forms.CheckBox.Checked%2A> property when the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span>  
  
     <span data-ttu-id="c465d-110">También puede usar el control <xref:System.Windows.Forms.CheckBox> para determinar una línea de acción.</span><span class="sxs-lookup"><span data-stu-id="c465d-110">You can also use the <xref:System.Windows.Forms.CheckBox> control to determine a course of action.</span></span>  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a><span data-ttu-id="c465d-111">Para determinar una línea de acción al hacer clic en una casilla</span><span class="sxs-lookup"><span data-stu-id="c465d-111">To determine a course of action when a check box is clicked</span></span>  
  
1. <span data-ttu-id="c465d-112">Use una instrucción Case para consultar el valor de la propiedad <xref:System.Windows.Forms.CheckBox.CheckState%2A> para determinar un curso de acción.</span><span class="sxs-lookup"><span data-stu-id="c465d-112">Use a case statement to query the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property to determine a course of action.</span></span> <span data-ttu-id="c465d-113">Cuando la propiedad <xref:System.Windows.Forms.CheckBox.ThreeState%2A> está establecida en `true`, la propiedad <xref:System.Windows.Forms.CheckBox.CheckState%2A> puede devolver tres valores posibles, que representan el cuadro que se está comprobando, el cuadro desactivado o un tercer estado indeterminado en el que se muestra el cuadro con una apariencia atenuada para indicar que la opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="c465d-113">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property may return three possible values, which represent the box being checked, the box being unchecked, or a third indeterminate state in which the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
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
    > <span data-ttu-id="c465d-114">Cuando la propiedad <xref:System.Windows.Forms.CheckBox.ThreeState%2A> está establecida en `true`, la propiedad <xref:System.Windows.Forms.CheckBox.Checked%2A> devuelve `true` para <xref:System.Windows.Forms.CheckState.Checked> y <xref:System.Windows.Forms.CheckState.Indeterminate>.</span><span class="sxs-lookup"><span data-stu-id="c465d-114">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns `true` for both <xref:System.Windows.Forms.CheckState.Checked> and <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c465d-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c465d-115">See also</span></span>

- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="c465d-116">Información general sobre el control CheckBox</span><span class="sxs-lookup"><span data-stu-id="c465d-116">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="c465d-117">Establecer opciones con los controles CheckBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c465d-117">How to: Set Options with Windows Forms CheckBox Controls</span></span>](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [<span data-ttu-id="c465d-118">CheckBox (control)</span><span class="sxs-lookup"><span data-stu-id="c465d-118">CheckBox Control</span></span>](checkbox-control-windows-forms.md)
