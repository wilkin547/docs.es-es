---
title: Designar un botón como botón para cancelar
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 252f0834-e54b-44d9-96f7-ee5f50e94f2c
ms.openlocfilehash: 123b3e275065efadd24815320ea7d855808e60b9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743263"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button"></a>Cómo: Designar un botón de Windows Forms como botón para cancelar
En cualquier Windows Form, puede designar un control <xref:System.Windows.Forms.Button> para que sea el botón Cancelar. Se hace clic en un botón Cancelar cuando el usuario presiona la tecla ESC, independientemente del control del formulario que tenga el foco. Normalmente, este botón se programa para permitir al usuario salir rápidamente de una operación sin confirmar ninguna acción.  
  
### <a name="to-designate-the-cancel-button"></a>Para designar el botón Cancelar  
  
1. Establezca la propiedad <xref:System.Windows.Forms.Form.CancelButton%2A> del formulario en el control <xref:System.Windows.Forms.Button> adecuado.  
  
    ```vb  
    Private Sub SetCancelButton(ByVal myCancelBtn As Button)  
       Me.CancelButton = myCancelBtn  
    End Sub  
    ```  
  
    ```csharp  
    private void SetCancelButton(Button myCancelBtn)  
    {  
       this.CancelButton = myCancelBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetCancelButton(Button ^ myCancelBtn)  
       {  
          this->CancelButton = myCancelBtn;  
       }  
    ```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [Información general sobre el control Button](button-control-overview-windows-forms.md)
- [Maneras de seleccionar un control Button de formularios Windows Forms](ways-to-select-a-windows-forms-button-control.md)
- [Responder a clics de botones en Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Designar un botón de Windows Forms como botón para aceptar](how-to-designate-a-windows-forms-button-as-the-accept-button.md)
- [Botón (control)](button-control-windows-forms.md)
