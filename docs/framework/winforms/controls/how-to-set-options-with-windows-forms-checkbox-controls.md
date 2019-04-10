---
title: Filtrar para establecer opciones con los controles CheckBox de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- checked
helpviewer_keywords:
- CheckBox control [Windows Forms], checked state
- check boxes [Windows Forms], using to set options
- CheckBox control [Windows Forms], using to set options
ms.assetid: 2ac70498-7e3e-4e07-8901-ccabaeb5fd3e
ms.openlocfilehash: 881996563acef36a1981ca6236c155b8fc56ef0a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59307327"
---
# <a name="how-to-set-options-with-windows-forms-checkbox-controls"></a><span data-ttu-id="192d4-102">Filtrar para establecer opciones con los controles CheckBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="192d4-102">How to: Set Options with Windows Forms CheckBox Controls</span></span>
<span data-ttu-id="192d4-103">Un formulario Windows Forms <xref:System.Windows.Forms.CheckBox> control se usa para proporcionar a los usuarios True/False o Sí/No (opciones).</span><span class="sxs-lookup"><span data-stu-id="192d4-103">A Windows Forms <xref:System.Windows.Forms.CheckBox> control is used to give users True/False or Yes/No options.</span></span> <span data-ttu-id="192d4-104">El control muestra una marca de verificación cuando está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="192d4-104">The control displays a check mark when it is selected.</span></span>  
  
### <a name="to-set-options-with-checkbox-controls"></a><span data-ttu-id="192d4-105">Para establecer las opciones con controles CheckBox</span><span class="sxs-lookup"><span data-stu-id="192d4-105">To set options with CheckBox controls</span></span>  
  
1. <span data-ttu-id="192d4-106">Examine el valor de la <xref:System.Windows.Forms.CheckBox.Checked%2A> propiedad para determinar su estado y usar ese valor para establecer una opción.</span><span class="sxs-lookup"><span data-stu-id="192d4-106">Examine the value of the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine its state, and use that value to set an option.</span></span>  
  
     <span data-ttu-id="192d4-107">En el ejemplo de código siguiente, cuando el <xref:System.Windows.Forms.CheckBox> del control <xref:System.Windows.Forms.CheckBox.CheckedChanged> se provoca el evento, el formulario <xref:System.Windows.Forms.Control.AllowDrop%2A> propiedad está establecida en `false` si está activada la casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="192d4-107">In the code sample below, when the <xref:System.Windows.Forms.CheckBox> control's <xref:System.Windows.Forms.CheckBox.CheckedChanged> event is raised, the form's <xref:System.Windows.Forms.Control.AllowDrop%2A> property is set to `false` if the check box is checked.</span></span> <span data-ttu-id="192d4-108">Esto es útil en situaciones donde desea restringir la interacción del usuario.</span><span class="sxs-lookup"><span data-stu-id="192d4-108">This is useful for situations where you want to restrict user interaction.</span></span>  
  
    ```vb  
    Private Sub CheckBox1_CheckedChanged(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles CheckBox1.CheckedChanged  
       ' Determine the CheckState of the check box.  
       If CheckBox1.CheckState = CheckState.Checked Then  
          ' If checked, do not allow items to be dragged onto the form.  
          Me.AllowDrop = False  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_CheckedChanged(object sender, System.EventArgs e)  
    {  
       // Determine the CheckState of the check box.  
       if (checkBox1.CheckState == CheckState.Checked)   
       {  
          // If checked, do not allow items to be dragged onto the form.  
          this.AllowDrop = false;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // Determine the CheckState of the check box.  
          if (checkBox1->CheckState == CheckState::Checked)   
          {  
             // If checked, do not allow items to be dragged onto the form.  
             this->AllowDrop = false;  
          }  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="192d4-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="192d4-109">See also</span></span>

- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="192d4-110">Información general sobre el control CheckBox</span><span class="sxs-lookup"><span data-stu-id="192d4-110">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="192d4-111">Filtrar para responder a clics en casillas de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="192d4-111">How to: Respond to Windows Forms CheckBox Clicks</span></span>](how-to-respond-to-windows-forms-checkbox-clicks.md)
- [<span data-ttu-id="192d4-112">Control CheckBox</span><span class="sxs-lookup"><span data-stu-id="192d4-112">CheckBox Control</span></span>](checkbox-control-windows-forms.md)
