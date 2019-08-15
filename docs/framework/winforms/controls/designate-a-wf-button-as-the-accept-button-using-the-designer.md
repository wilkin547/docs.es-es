---
title: Procedimiento para designar un botón de formularios Windows Forms como botón para aceptar mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: a1da0590-755f-49f2-aca7-609fac6351bf
ms.openlocfilehash: 27ecb26c493232bcfb996d012f9760b7ef91e5b2
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039656"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button-using-the-designer"></a>Procedimiento para designar un botón de formularios Windows Forms como botón para aceptar mediante el diseñador
En cualquier Windows Form, puede designar un <xref:System.Windows.Forms.Button> control para que sea el botón Aceptar, también conocido como el botón predeterminado. Cada vez que el usuario presiona la tecla entrar, se hace clic en el botón predeterminado, independientemente del control del formulario que tenga el foco. Las excepciones a esto se produce cuando el control con el foco es otro botón; en ese caso, se hará clic en el botón con el foco, o en un cuadro de texto multilínea, o en un control personalizado que capture la tecla entrar.

## <a name="to-designate-the-accept-button"></a>Para designar el botón Aceptar

1. Seleccione el formulario en el que reside el botón.

2. En la ventana **propiedades** , establezca la propiedad del <xref:System.Windows.Forms.Form.AcceptButton%2A> formulario en el <xref:System.Windows.Forms.Button> nombre del control.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [Información general sobre el control Button](button-control-overview-windows-forms.md)
- [Maneras de seleccionar un control Button de formularios Windows Forms](ways-to-select-a-windows-forms-button-control.md)
- [Cómo: Responder a clics de botón de Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Cómo: Designar un botón de Windows Forms como botón para cancelar mediante el diseñador](designate-a-wf-button-as-the-cancel-button-using-the-designer.md)
- [Botón (control)](button-control-windows-forms.md)
