---
title: "Cómo: Responder a clics en casillas de formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8f15adb84f92c9434d6835e80f08bf1d9bd500ad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a><span data-ttu-id="adb76-102">Cómo: Responder a clics en casillas de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="adb76-102">How to: Respond to Windows Forms CheckBox Clicks</span></span>
<span data-ttu-id="adb76-103">Cada vez que un usuario hace clic en un formulario Windows Forms <xref:System.Windows.Forms.CheckBox> (control), el <xref:System.Windows.Forms.Control.Click> se produce el evento.</span><span class="sxs-lookup"><span data-stu-id="adb76-103">Whenever a user clicks a Windows Forms <xref:System.Windows.Forms.CheckBox> control, the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span> <span data-ttu-id="adb76-104">Puede programar la aplicación para realizar alguna acción según el estado de la casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="adb76-104">You can program your application to perform some action depending upon the state of the check box.</span></span>  
  
### <a name="to-respond-to-checkbox-clicks"></a><span data-ttu-id="adb76-105">Para responder a clics en casillas</span><span class="sxs-lookup"><span data-stu-id="adb76-105">To respond to CheckBox clicks</span></span>  
  
1.  <span data-ttu-id="adb76-106">En el <xref:System.Windows.Forms.Control.Click> controlador de eventos, use la <xref:System.Windows.Forms.CheckBox.Checked%2A> propiedad para determinar el estado del control y realizar cualquier acción necesaria.</span><span class="sxs-lookup"><span data-stu-id="adb76-106">In the <xref:System.Windows.Forms.Control.Click> event handler, use the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine the control's state, and perform any necessary action.</span></span>  
  
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
    >  <span data-ttu-id="adb76-107">Si el usuario intenta hacer doble clic en el <xref:System.Windows.Forms.CheckBox> control, cada clic se procesará por separado; es decir, el <xref:System.Windows.Forms.CheckBox> control no admite el evento doble clic.</span><span class="sxs-lookup"><span data-stu-id="adb76-107">If the user attempts to double-click the <xref:System.Windows.Forms.CheckBox> control, each click will be processed separately; that is, the <xref:System.Windows.Forms.CheckBox> control does not support the double-click event.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="adb76-108">Cuando el <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> propiedad es `true` (valor predeterminado), el <xref:System.Windows.Forms.CheckBox> automáticamente se selecciona o se borra cuando se hace clic en.</span><span class="sxs-lookup"><span data-stu-id="adb76-108">When the <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> property is `true` (the default), the <xref:System.Windows.Forms.CheckBox> is automatically selected or cleared when it is clicked.</span></span> <span data-ttu-id="adb76-109">En caso contrario, debe establecer manualmente el <xref:System.Windows.Forms.CheckBox.Checked%2A> propiedad cuando la <xref:System.Windows.Forms.Control.Click> se produce el evento.</span><span class="sxs-lookup"><span data-stu-id="adb76-109">Otherwise, you must manually set the <xref:System.Windows.Forms.CheckBox.Checked%2A> property when the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span>  
  
     <span data-ttu-id="adb76-110">También puede usar el <xref:System.Windows.Forms.CheckBox> control para determinar las acciones posibles.</span><span class="sxs-lookup"><span data-stu-id="adb76-110">You can also use the <xref:System.Windows.Forms.CheckBox> control to determine a course of action.</span></span>  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a><span data-ttu-id="adb76-111">Para determinar un curso de acción cuando una casilla de verificación se hace clic en</span><span class="sxs-lookup"><span data-stu-id="adb76-111">To determine a course of action when a check box is clicked</span></span>  
  
1.  <span data-ttu-id="adb76-112">Utilice una instrucción case para consultar el valor de la <xref:System.Windows.Forms.CheckBox.CheckState%2A> propiedad para determinar las acciones posibles.</span><span class="sxs-lookup"><span data-stu-id="adb76-112">Use a case statement to query the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property to determine a course of action.</span></span> <span data-ttu-id="adb76-113">Cuando el <xref:System.Windows.Forms.CheckBox.ThreeState%2A> propiedad está establecida en `true`, el <xref:System.Windows.Forms.CheckBox.CheckState%2A> propiedad puede devolver tres posibles valores, que corresponden a la casilla activada, la casilla desactivada y un tercer estado indeterminado, en el que se muestra el cuadro con un atenuada apariencia para indicar que la opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="adb76-113">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property may return three possible values, which represent the box being checked, the box being unchecked, or a third indeterminate state in which the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
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
    >  <span data-ttu-id="adb76-114">Cuando el <xref:System.Windows.Forms.CheckBox.ThreeState%2A> propiedad está establecida en `true`, <xref:System.Windows.Forms.CheckBox.Checked%2A> propiedad devuelve `true` para ambos <xref:System.Windows.Forms.CheckState.Checked> y <xref:System.Windows.Forms.CheckState.Indeterminate>.</span><span class="sxs-lookup"><span data-stu-id="adb76-114">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns `true` for both <xref:System.Windows.Forms.CheckState.Checked> and <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adb76-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="adb76-115">See Also</span></span>  
 <xref:System.Windows.Forms.CheckBox>  
 [<span data-ttu-id="adb76-116">Información general sobre el control CheckBox</span><span class="sxs-lookup"><span data-stu-id="adb76-116">CheckBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="adb76-117">Establecer opciones con los controles CheckBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="adb76-117">How to: Set Options with Windows Forms CheckBox Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-set-options-with-windows-forms-checkbox-controls.md)  
 [<span data-ttu-id="adb76-118">CheckBox (control)</span><span class="sxs-lookup"><span data-stu-id="adb76-118">CheckBox Control</span></span>](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)
