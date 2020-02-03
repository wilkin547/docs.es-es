---
title: Designar un botón como botón para aceptar mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: a1da0590-755f-49f2-aca7-609fac6351bf
ms.openlocfilehash: 27a5de51f8c5b2c84cc205e09ac1a2179c315752
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746066"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button-using-the-designer"></a>Cómo: Designar un botón de formularios Windows Forms como botón para aceptar mediante el Diseñador
En cualquier Windows Form, puede designar un control <xref:System.Windows.Forms.Button> para que sea el botón Aceptar, también conocido como el botón predeterminado. Cada vez que el usuario presiona la tecla entrar, se hace clic en el botón predeterminado, independientemente del control del formulario que tenga el foco. Las excepciones a esto se produce cuando el control con el foco es otro botón; en ese caso, se hará clic en el botón con el foco, o en un cuadro de texto multilínea, o en un control personalizado que capture la tecla entrar.

## <a name="to-designate-the-accept-button"></a>Para designar el botón Aceptar

1. Seleccione el formulario en el que reside el botón.

2. En la ventana **propiedades** , establezca la propiedad <xref:System.Windows.Forms.Form.AcceptButton%2A> del formulario en el nombre del control <xref:System.Windows.Forms.Button>.

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [Información general sobre el control Button](button-control-overview-windows-forms.md)
- [Maneras de seleccionar un control Button de formularios Windows Forms](ways-to-select-a-windows-forms-button-control.md)
- [Responder a clics de botones en Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Procedimiento para designar un botón de formularios Windows Forms como botón para cancelar mediante el diseñador](designate-a-wf-button-as-the-cancel-button-using-the-designer.md)
- [Botón (control)](button-control-windows-forms.md)
