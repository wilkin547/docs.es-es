---
title: Designar un botón como el botón Aceptar
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
ms.openlocfilehash: ca5f691fb26db5c4adcb48405c9600b54827104c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142152"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a>Cómo: Designar un botón de formularios Windows Forms como botón para aceptar
En cualquier formulario Windows Forms, puede designar un <xref:System.Windows.Forms.Button> control para que sea el botón Aceptar, también conocido como el botón predeterminado. Cada vez que el usuario presiona la tecla ENTRAR, se hace clic en el botón predeterminado independientemente del otro control del formulario que tenga el foco.  
  
> [!NOTE]
> Las excepciones a esto son cuando el control con foco es otro botón (en ese caso, se hará clic en el botón con el foco) o un cuadro de texto de varias líneas, o un control personalizado que captura la tecla ENTRAR.  
  
### <a name="to-designate-the-accept-button"></a>Para designar el botón Aceptar  
  
1. Establezca la propiedad <xref:System.Windows.Forms.Form.AcceptButton%2A> del formulario <xref:System.Windows.Forms.Button> en el control adecuado.  
  
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
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [Información general sobre el control Button](button-control-overview-windows-forms.md)
- [Maneras de seleccionar un control Button de formularios Windows Forms](ways-to-select-a-windows-forms-button-control.md)
- [Cómo: Responder a clics de botones en formularios Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Cómo: Definir un botón de formularios Windows Forms como el botón Cancelar](how-to-designate-a-windows-forms-button-as-the-cancel-button.md)
- [Control Button](button-control-windows-forms.md)
