---
title: Maneras de seleccionar un control de botón
ms.date: 03/30/2017
helpviewer_keywords:
- Button control [Windows Forms], selecting
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
ms.openlocfilehash: 145166d182f1ec51068ab3e0c23c12b471b69231
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740002"
---
# <a name="ways-to-select-a-windows-forms-button-control"></a>Maneras de seleccionar un control Button de Windows Forms
Se puede seleccionar un botón Windows Forms de las siguientes maneras:  
  
- Use un mouse para hacer clic en el botón.  
  
- Invocar el evento <xref:System.Windows.Forms.Control.Click> del botón en el código.  
  
- Mueva el foco al botón presionando la tecla TAB y, a continuación, elija el botón presionando la barra ESPACIAdora o entrar.  
  
- Presione la tecla de acceso (ALT + la letra subrayada) para el botón. Para obtener más información acerca de las claves de acceso, consulte [Cómo: crear claves de acceso para controles de Windows Forms](how-to-create-access-keys-for-windows-forms-controls.md).  
  
- Si el botón es el botón "Aceptar" del formulario, al presionar entrar, se elige el botón, aunque otro control tenga el foco, excepto si ese control es otro botón, un cuadro de texto de varias líneas o un control personalizado que intercepta la tecla entrar.  
  
- Si el botón es el botón "Cancelar" del formulario, al presionar ESC se elige el botón, aunque otro control tenga el foco.  
  
- Llame al método <xref:System.Windows.Forms.Button.PerformClick%2A> para seleccionar el botón mediante programación.  
  
## <a name="see-also"></a>Consulte también

- [Información general sobre el control Button](button-control-overview-windows-forms.md)
- [Responder a clics de botones en Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Botón (control)](button-control-windows-forms.md)
