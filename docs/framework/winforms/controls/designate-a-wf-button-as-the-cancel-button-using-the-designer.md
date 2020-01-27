---
title: Designar un botón como botón para cancelar mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
ms.openlocfilehash: 95d1139b6e339055f944ad0b0967a6d91283d49e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746054"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a>Cómo: Designar un botón de formularios Windows Forms como botón para cancelar mediante el Diseñador
En cualquier Windows Form, puede designar un control <xref:System.Windows.Forms.Button> para que sea el botón Cancelar. Se hace clic en un botón Cancelar cuando el usuario presiona la tecla ESC, independientemente del control del formulario que tenga el foco. Normalmente, este botón se programa para permitir al usuario salir rápidamente de una operación sin confirmar ninguna acción.

## <a name="to-designate-the-cancel-button"></a>Para designar el botón Cancelar

1. Seleccione el formulario en el que reside el botón.

2. En la ventana **propiedades** , establezca la propiedad <xref:System.Windows.Forms.Form.CancelButton%2A> del formulario en el nombre del control <xref:System.Windows.Forms.Button>.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [Información general sobre el control Button](button-control-overview-windows-forms.md)
- [Maneras de seleccionar un control Button de formularios Windows Forms](ways-to-select-a-windows-forms-button-control.md)
- [Responder a clics de botones en Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Procedimiento para designar un botón de formularios Windows Forms como botón para aceptar mediante el diseñador](designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [Botón (control)](button-control-windows-forms.md)
