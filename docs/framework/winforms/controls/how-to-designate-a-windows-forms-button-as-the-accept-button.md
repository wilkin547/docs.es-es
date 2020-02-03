---
title: Designar un botón como botón para aceptar
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
ms.openlocfilehash: 1063f649768cac2c866390718b261a21e18ec4d3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743271"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a>Cómo: Designar un botón de Windows Forms como botón para aceptar
En cualquier Windows Form, puede designar un control <xref:System.Windows.Forms.Button> para que sea el botón Aceptar, también conocido como el botón predeterminado. Cada vez que el usuario presiona la tecla entrar, se hace clic en el botón predeterminado, independientemente del control del formulario que tenga el foco.  
  
> [!NOTE]
> Las excepciones a esto se produce cuando el control con el foco es otro botón; en ese caso, se hará clic en el botón con el foco, o en un cuadro de texto multilínea, o en un control personalizado que capture la tecla entrar.  
  
### <a name="to-designate-the-accept-button"></a>Para designar el botón Aceptar  
  
1. Establezca la propiedad <xref:System.Windows.Forms.Form.AcceptButton%2A> del formulario en el control <xref:System.Windows.Forms.Button> adecuado.  
  
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
- [Responder a clics de botones en Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Designar un botón de Windows Forms como botón para cancelar](how-to-designate-a-windows-forms-button-as-the-cancel-button.md)
- [Botón (control)](button-control-windows-forms.md)
