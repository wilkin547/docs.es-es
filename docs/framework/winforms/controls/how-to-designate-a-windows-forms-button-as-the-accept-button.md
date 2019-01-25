---
title: Procedimiento Designar un botón de formularios Windows Forms como botón Aceptar
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: 22cc9da6-b913-4e04-9554-dee443ac5c3a
ms.openlocfilehash: e35dbc2b66f743f5af3c405228439268590e1a5b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660208"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a>Procedimiento Designar un botón de formularios Windows Forms como botón Aceptar
En cualquier formulario de Windows, se puede designar un <xref:System.Windows.Forms.Button> que sea el botón Aceptar, también conocido como el botón predeterminado del control. Cada vez que el usuario presiona la tecla ENTRAR, se hace clic en el botón predeterminado, independientemente de que otro control en el formulario tiene el foco.  
  
> [!NOTE]
>  Las excepciones a esto son cuando el control tiene el foco es otro botón, en ese caso, se hace clic en el botón con el foco, o un cuadro de texto multilínea o un control personalizado que intercepta la tecla ENTRAR.  
  
### <a name="to-designate-the-accept-button"></a>Para designar el botón Aceptar  
  
1.  Establezca el formulario <xref:System.Windows.Forms.Form.AcceptButton%2A> propiedad correspondientes <xref:System.Windows.Forms.Button> control.  
  
    ```vb  
    Private Sub SetDefault(ByVal myDefaultBtn As Button)  
      Me.AcceptButton = myDefaultBtn   
    End Sub  
    ```  
  
    ```csharp  
    private void SetDefault(Button myDefaultBtn)  
    {  
       this.AcceptButton = myDefaultBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetDefault(Button ^ myDefaultBtn)  
       {  
          this->AcceptButton = myDefaultBtn;  
       }  
    ```  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [Información general sobre el control Button](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)
- [Maneras de seleccionar un control Button de formularios Windows Forms](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)
- [Cómo: Responder a clics de botón de Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)
- [Cómo: Designar un botón de formularios Windows Forms como botón para cancelar](../../../../docs/framework/winforms/controls/how-to-designate-a-windows-forms-button-as-the-cancel-button.md)
- [Botón (control)](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
