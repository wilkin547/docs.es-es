---
title: 'Cómo: Crear un cuadro de texto de sólo lectura'
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 17ae9524009c687cd62fb315f842e188e120ac68
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731270"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a>Cómo: Crear un cuadro de texto de sólo lectura (formularios Windows Forms)

Puede transformar un cuadro de texto Windows Forms editable en un control de solo lectura. Por ejemplo, el cuadro de texto puede mostrar un valor que normalmente se edita, pero que puede que no sea actualmente, debido al estado de la aplicación.

## <a name="to-create-a-read-only-text-box"></a>Para crear un cuadro de texto de solo lectura

1. Establezca la propiedad <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> del control <xref:System.Windows.Forms.TextBox> en `true`. Con la propiedad establecida en `true`, los usuarios todavía pueden desplazarse y resaltar el texto en un cuadro de texto sin permitir cambios. Un comando de **copia** funciona en un cuadro de texto, pero no los comandos de **cortar** y **pegar** .

    > [!NOTE]
    > La propiedad <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> solo afecta a la interacción del usuario en tiempo de ejecución. Todavía puede cambiar el contenido del cuadro de texto mediante programación en tiempo de ejecución si cambia la propiedad <xref:System.Windows.Forms.TextBox.Text%2A> del cuadro de texto.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.TextBox>
- [Información general sobre el control TextBox](textbox-control-overview-windows-forms.md)
- [Controlar el punto de inserción en un control TextBox de Windows Forms](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Crear un cuadro de texto de contraseña con el control TextBox de Windows Forms](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Insertar comillas en una cadena](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Seleccionar texto en el control TextBox de Windows Forms](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Ver múltiples líneas en el control TextBox de Windows Forms](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Control TextBox](textbox-control-windows-forms.md)
