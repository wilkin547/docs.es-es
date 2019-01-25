---
title: Maneras de seleccionar un control Button de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Button control [Windows Forms], selecting
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
ms.openlocfilehash: 908751401d812be0403af5517d9bbf2ad7344f35
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54573808"
---
# <a name="ways-to-select-a-windows-forms-button-control"></a>Maneras de seleccionar un control Button de formularios Windows Forms
Un botón de Windows Forms se puede seleccionar en las siguientes maneras:  
  
-   Usar un mouse para hacer clic en el botón.  
  
-   Invocar el botón <xref:System.Windows.Forms.Control.Click> evento en el código.  
  
-   Mover el foco al botón presionando la tecla TAB y, a continuación, elija el botón presionando la barra espaciadora o ENTRAR.  
  
-   Presione la tecla de acceso (ALT + la letra subrayada) para el botón. Para obtener más información acerca de las claves de acceso, consulte [Cómo: Crear teclas de acceso para controles de Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).  
  
-   Si el botón es el botón "accept" del formulario, al presionar ENTRAR, elige el botón, aunque otro control tiene el foco, excepto si ese control es otro botón, un cuadro de texto multilínea o un control personalizado que intercepta la tecla ENTRAR.  
  
-   Si el botón es el botón "Cancelar" del formulario, presione ESC elige el botón, aunque otro control tiene el foco.  
  
-   Llame a la <xref:System.Windows.Forms.Button.PerformClick%2A> método para seleccionar el botón mediante programación.  
  
## <a name="see-also"></a>Vea también
- [Información general sobre el control Button](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)
- [Cómo: Responder a clics de botón de Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)
- [Botón (control)](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
