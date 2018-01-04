---
title: "Cómo: Establecer opciones con los controles CheckBox de formularios Windows Forms"
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
f1_keywords: checked
helpviewer_keywords:
- CheckBox control [Windows Forms], checked state
- check boxes [Windows Forms], using to set options
- CheckBox control [Windows Forms], using to set options
ms.assetid: 2ac70498-7e3e-4e07-8901-ccabaeb5fd3e
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4059e3b4ad4c687234f2bc0c66c680b2c857cfe7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-options-with-windows-forms-checkbox-controls"></a>Cómo: Establecer opciones con los controles CheckBox de formularios Windows Forms
Un formulario Windows Forms <xref:System.Windows.Forms.CheckBox> control se utiliza para proporcionar a los usuarios True/False o Sí/No (opciones). El control muestra una marca de verificación cuando se selecciona.  
  
### <a name="to-set-options-with-checkbox-controls"></a>Para establecer opciones con controles CheckBox  
  
1.  Examine el valor de la <xref:System.Windows.Forms.CheckBox.Checked%2A> propiedad para determinar su estado y usar ese valor para establecer una opción.  
  
     En el ejemplo de código siguiente, cuando la <xref:System.Windows.Forms.CheckBox> del control <xref:System.Windows.Forms.CheckBox.CheckedChanged> se genera el evento, el formulario <xref:System.Windows.Forms.Control.AllowDrop%2A> propiedad está establecida en `false` si está activada la casilla de verificación. Esto es útil en situaciones donde desea restringir la interacción del usuario.  
  
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
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.CheckBox>  
 [Información general sobre el control CheckBox](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)  
 [Responder a clics en casillas de Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-checkbox-clicks.md)  
 [CheckBox (control)](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)
