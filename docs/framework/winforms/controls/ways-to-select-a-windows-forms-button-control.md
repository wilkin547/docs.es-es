---
title: Maneras de seleccionar un control Button de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Button control [Windows Forms], selecting
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
ms.openlocfilehash: f2881646a05d257044c6461f822a4c35a225f8c8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59223295"
---
# <a name="ways-to-select-a-windows-forms-button-control"></a>Maneras de seleccionar un control Button de formularios Windows Forms
Un botón de Windows Forms se puede seleccionar en las siguientes maneras:  
  
-   Usar un mouse para hacer clic en el botón.  
  
-   Invocar el botón <xref:System.Windows.Forms.Control.Click> evento en el código.  
  
-   Mover el foco al botón presionando la tecla TAB y, a continuación, elija el botón presionando la barra espaciadora o ENTRAR.  
  
-   Presione la tecla de acceso (ALT + la letra subrayada) para el botón. Para obtener más información acerca de las claves de acceso, consulte [Cómo: Crear teclas de acceso para controles de Windows Forms](how-to-create-access-keys-for-windows-forms-controls.md).  
  
-   Si el botón es el botón "accept" del formulario, al presionar ENTRAR, elige el botón, aunque otro control tiene el foco, excepto si ese control es otro botón, un cuadro de texto multilínea o un control personalizado que intercepta la tecla ENTRAR.  
  
-   Si el botón es el botón "Cancelar" del formulario, presione ESC elige el botón, aunque otro control tiene el foco.  
  
-   Llame a la <xref:System.Windows.Forms.Button.PerformClick%2A> método para seleccionar el botón mediante programación.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre el control Button](button-control-overview-windows-forms.md)
- [Filtrar para responder a clics de botones en formularios Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Control Button](button-control-windows-forms.md)
