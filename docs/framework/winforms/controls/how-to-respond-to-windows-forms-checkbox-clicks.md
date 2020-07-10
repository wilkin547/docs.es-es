---
title: para responder a clics en casillas
description: Obtenga información sobre cómo programar la aplicación de Windows Forms para realizar alguna acción en función del estado de la casilla.
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
ms.openlocfilehash: 58944bc421f990343b6c58484aaab3d79c8bda5e
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174502"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a><span data-ttu-id="8bd51-103">Cómo: Responder a clics en casillas de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8bd51-103">How to: Respond to Windows Forms CheckBox Clicks</span></span>
<span data-ttu-id="8bd51-104">Cada vez que un usuario hace clic en un control de Windows Forms <xref:System.Windows.Forms.CheckBox> , <xref:System.Windows.Forms.Control.Click> se produce el evento.</span><span class="sxs-lookup"><span data-stu-id="8bd51-104">Whenever a user clicks a Windows Forms <xref:System.Windows.Forms.CheckBox> control, the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span> <span data-ttu-id="8bd51-105">Puede programar la aplicación para realizar alguna acción en función del estado de la casilla.</span><span class="sxs-lookup"><span data-stu-id="8bd51-105">You can program your application to perform some action depending upon the state of the check box.</span></span>  
  
### <a name="to-respond-to-checkbox-clicks"></a><span data-ttu-id="8bd51-106">Para responder a clics en casillas</span><span class="sxs-lookup"><span data-stu-id="8bd51-106">To respond to CheckBox clicks</span></span>  
  
1. <span data-ttu-id="8bd51-107">En el <xref:System.Windows.Forms.Control.Click> controlador de eventos, use la <xref:System.Windows.Forms.CheckBox.Checked%2A> propiedad para determinar el estado del control y realice las acciones necesarias.</span><span class="sxs-lookup"><span data-stu-id="8bd51-107">In the <xref:System.Windows.Forms.Control.Click> event handler, use the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine the control's state, and perform any necessary action.</span></span>  
  
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
    > <span data-ttu-id="8bd51-108">Si el usuario intenta hacer doble clic en el <xref:System.Windows.Forms.CheckBox> control, cada clic se procesará por separado; es decir, el <xref:System.Windows.Forms.CheckBox> control no admite el evento de doble clic.</span><span class="sxs-lookup"><span data-stu-id="8bd51-108">If the user attempts to double-click the <xref:System.Windows.Forms.CheckBox> control, each click will be processed separately; that is, the <xref:System.Windows.Forms.CheckBox> control does not support the double-click event.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="8bd51-109">Cuando la <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> propiedad es `true` (valor predeterminado), <xref:System.Windows.Forms.CheckBox> se selecciona o borra automáticamente al hacer clic en él.</span><span class="sxs-lookup"><span data-stu-id="8bd51-109">When the <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> property is `true` (the default), the <xref:System.Windows.Forms.CheckBox> is automatically selected or cleared when it is clicked.</span></span> <span data-ttu-id="8bd51-110">De lo contrario, debe establecer manualmente la <xref:System.Windows.Forms.CheckBox.Checked%2A> propiedad cuando <xref:System.Windows.Forms.Control.Click> se produce el evento.</span><span class="sxs-lookup"><span data-stu-id="8bd51-110">Otherwise, you must manually set the <xref:System.Windows.Forms.CheckBox.Checked%2A> property when the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span>  
  
     <span data-ttu-id="8bd51-111">También puede usar el <xref:System.Windows.Forms.CheckBox> control para determinar un curso de acción.</span><span class="sxs-lookup"><span data-stu-id="8bd51-111">You can also use the <xref:System.Windows.Forms.CheckBox> control to determine a course of action.</span></span>  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a><span data-ttu-id="8bd51-112">Para determinar una línea de acción al hacer clic en una casilla</span><span class="sxs-lookup"><span data-stu-id="8bd51-112">To determine a course of action when a check box is clicked</span></span>  
  
1. <span data-ttu-id="8bd51-113">Use una instrucción Case para consultar el valor de la <xref:System.Windows.Forms.CheckBox.CheckState%2A> propiedad a fin de determinar un curso de acción.</span><span class="sxs-lookup"><span data-stu-id="8bd51-113">Use a case statement to query the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property to determine a course of action.</span></span> <span data-ttu-id="8bd51-114">Cuando la <xref:System.Windows.Forms.CheckBox.ThreeState%2A> propiedad está establecida en `true` , la <xref:System.Windows.Forms.CheckBox.CheckState%2A> propiedad puede devolver tres valores posibles, que representan el cuadro que se está comprobando, el cuadro desactivado o un tercer estado indeterminado en el que se muestra el cuadro con una apariencia atenuada para indicar que la opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="8bd51-114">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property may return three possible values, which represent the box being checked, the box being unchecked, or a third indeterminate state in which the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
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
    > <span data-ttu-id="8bd51-115">Cuando la <xref:System.Windows.Forms.CheckBox.ThreeState%2A> propiedad se establece en `true` , la <xref:System.Windows.Forms.CheckBox.Checked%2A> propiedad devuelve `true` para <xref:System.Windows.Forms.CheckState.Checked> y <xref:System.Windows.Forms.CheckState.Indeterminate> .</span><span class="sxs-lookup"><span data-stu-id="8bd51-115">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns `true` for both <xref:System.Windows.Forms.CheckState.Checked> and <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bd51-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="8bd51-116">See also</span></span>

- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="8bd51-117">Información general sobre el control CheckBox</span><span class="sxs-lookup"><span data-stu-id="8bd51-117">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="8bd51-118">Cómo: Establecer opciones con los controles CheckBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8bd51-118">How to: Set Options with Windows Forms CheckBox Controls</span></span>](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [<span data-ttu-id="8bd51-119">CheckBox (control)</span><span class="sxs-lookup"><span data-stu-id="8bd51-119">CheckBox Control</span></span>](checkbox-control-windows-forms.md)
