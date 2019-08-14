---
title: Procedimiento Crear un cuadro de texto de solo lectura (Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 18d2f5ed2530957487ac25c3eb6240f8bc50a938
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "68971940"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a>Procedimiento Crear un cuadro de texto de solo lectura (Windows Forms)

Puede transformar un cuadro de texto Windows Forms editable en un control de solo lectura. Por ejemplo, el cuadro de texto puede mostrar un valor que normalmente se edita, pero que puede que no sea actualmente, debido al estado de la aplicación.

## <a name="to-create-a-read-only-text-box"></a>Para crear un cuadro de texto de solo lectura

1. Establezca la <xref:System.Windows.Forms.TextBox> propiedad del <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> control en `true`. Con la propiedad establecida en `true`, los usuarios todavía pueden desplazarse y resaltar el texto en un cuadro de texto sin permitir cambios. Un comando de **copia** funciona en un cuadro de texto, pero no los comandos de **cortar** y **pegar** .

    > [!NOTE]
    > La <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> propiedad solo afecta a la interacción del usuario en tiempo de ejecución. Todavía puede cambiar el contenido del cuadro de texto mediante programación en tiempo de ejecución <xref:System.Windows.Forms.TextBox.Text%2A> cambiando la propiedad del cuadro de texto.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.TextBox>
- [Información general sobre el control TextBox](textbox-control-overview-windows-forms.md)
- [Cómo: Controlar el punto de inserción en un control de cuadro de texto Windows Forms](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Cómo: Crear un cuadro de texto de contraseña con el control Windows Forms TextBox](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Procedimientos: Insertar comillas en una cadena](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Cómo: Seleccionar texto en el control TextBox Windows Forms](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Cómo: Ver varias líneas en el control TextBox Windows Forms](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Control TextBox](textbox-control-windows-forms.md)
