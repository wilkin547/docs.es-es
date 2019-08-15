---
title: Procedimiento para designar un botón de formularios Windows Forms como botón para cancelar mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
ms.openlocfilehash: cc352f15fb1e8b531cd0f9b298b2db4ce649d3cf
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039647"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a>Procedimiento para designar un botón de formularios Windows Forms como botón para cancelar mediante el diseñador
En cualquier Windows Form, puede designar un <xref:System.Windows.Forms.Button> control para que sea el botón Cancelar. Se hace clic en un botón Cancelar cuando el usuario presiona la tecla ESC, independientemente del control del formulario que tenga el foco. Normalmente, este botón se programa para permitir al usuario salir rápidamente de una operación sin confirmar ninguna acción.

## <a name="to-designate-the-cancel-button"></a>Para designar el botón Cancelar

1. Seleccione el formulario en el que reside el botón.

2. En la ventana **propiedades** , establezca la propiedad del <xref:System.Windows.Forms.Form.CancelButton%2A> formulario en el <xref:System.Windows.Forms.Button> nombre del control.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [Información general sobre el control Button](button-control-overview-windows-forms.md)
- [Maneras de seleccionar un control Button de formularios Windows Forms](ways-to-select-a-windows-forms-button-control.md)
- [Procedimientos: Responder a clics de botón de Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Cómo: Designar un botón de Windows Forms como botón para aceptar mediante el diseñador](designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [Botón (control)](button-control-windows-forms.md)
