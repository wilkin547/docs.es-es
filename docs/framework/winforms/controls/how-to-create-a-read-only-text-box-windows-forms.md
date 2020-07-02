---
title: Procedimiento para crear un cuadro de texto de solo lectura
description: Obtenga información sobre cómo transformar un cuadro de texto Windows Forms editable en un cuadro de texto de Windows Forms de solo lectura.
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 5baa7c66d5f16560a4ea23861d563b099592957f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619369"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a>Cómo: Crear un cuadro de texto de sólo lectura (formularios Windows Forms)

Puede transformar un cuadro de texto Windows Forms editable en un control de solo lectura. Por ejemplo, el cuadro de texto puede mostrar un valor que normalmente se edita, pero que puede que no sea actualmente, debido al estado de la aplicación.

## <a name="to-create-a-read-only-text-box"></a>Para crear un cuadro de texto de solo lectura

1. Establezca la <xref:System.Windows.Forms.TextBox> propiedad del control <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> en `true` . Con la propiedad establecida en `true` , los usuarios todavía pueden desplazarse y resaltar el texto en un cuadro de texto sin permitir cambios. Un comando de **copia** funciona en un cuadro de texto, pero no los comandos de **cortar** y **pegar** .

    > [!NOTE]
    > La <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> propiedad solo afecta a la interacción del usuario en tiempo de ejecución. Todavía puede cambiar el contenido del cuadro de texto mediante programación en tiempo de ejecución cambiando la <xref:System.Windows.Forms.TextBox.Text%2A> propiedad del cuadro de texto.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.TextBox>
- [Información general sobre el control TextBox](textbox-control-overview-windows-forms.md)
- [Procedimiento para controlar el punto de inserción en un control TextBox de formularios Windows Forms](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Procedimiento para crear un cuadro de texto de contraseña con el control TextBox de formularios Windows Forms](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Procedimiento para insertar comillas en una cadena](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Procedimiento para seleccionar texto en el control TextBox de formularios Windows Forms](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Procedimiento para ver varias líneas en el control TextBox de formularios Windows Forms](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Control TextBox](textbox-control-windows-forms.md)
