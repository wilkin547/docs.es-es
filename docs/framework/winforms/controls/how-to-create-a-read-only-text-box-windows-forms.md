---
title: Procedimiento Crear un cuadro de texto de sólo lectura (formularios Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 89d331f6c7fad5880aff031eb808199292e493a6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54670347"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a>Procedimiento Crear un cuadro de texto de sólo lectura (formularios Windows Forms)
Puede transformar un cuadro de texto editable de Windows Forms en un control de solo lectura. Por ejemplo, el cuadro de texto puede mostrar un valor que se puede editar normalmente pero actualmente, no puede ser debido al estado de la aplicación.  
  
### <a name="to-create-a-read-only-text-box"></a>Para crear un cuadro de texto de solo lectura  
  
1.  Establecer el <xref:System.Windows.Forms.TextBox> del control <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> propiedad `true`. Con la propiedad establecida en `true`, los usuarios pueden desplazarse y resaltar texto en un cuadro de texto sin permitir que los cambios. Un **copia** comando es funcional en un cuadro de texto, pero **cortar** y **pegar** no son de comandos.  
  
    > [!NOTE]
    >  El <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> propiedad solo afecta a la interacción del usuario en tiempo de ejecución. Se puede modificar el contenido del cuadro de texto mediante programación en tiempo de ejecución mediante el <xref:System.Windows.Forms.TextBox.Text%2A> propiedad del cuadro de texto.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.TextBox>
- [Información general sobre el control TextBox](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)
- [Cómo: Controlar el punto de inserción en un Control TextBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Cómo: Crear un cuadro de texto de contraseña con el Control TextBox de Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Cómo: Insertar comillas en una cadena](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Cómo: Seleccionar texto en el Control TextBox de Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Cómo: Ver múltiples líneas en el Control TextBox de Windows Forms](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Control TextBox](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
