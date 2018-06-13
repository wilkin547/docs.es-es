---
title: 'Cómo: Crear un cuadro de texto de sólo lectura (formularios Windows Forms)'
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 06e03f67bd1f084b30bce85c3d81ad7b8c97a1b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530151"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a>Cómo: Crear un cuadro de texto de sólo lectura (formularios Windows Forms)
Puede transformar un cuadro de texto editable de formularios Windows Forms en un control de solo lectura. Por ejemplo, el cuadro de texto puede mostrar un valor que normalmente se edita pero no puede estar en la actualidad, debido al estado de la aplicación.  
  
### <a name="to-create-a-read-only-text-box"></a>Para crear un cuadro de texto de solo lectura  
  
1.  Establecer el <xref:System.Windows.Forms.TextBox> del control <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> propiedad `true`. Con la propiedad establecida en `true`, los usuarios todavía pueden desplazarse y resaltar texto en un cuadro de texto sin permitir que los cambios. A **copia** comando es funcional en un cuadro de texto, pero **cortar** y **pegar** comandos no están.  
  
    > [!NOTE]
    >  El <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> propiedad solo afecta a la interacción del usuario en tiempo de ejecución. Se puede cambiar el contenido del cuadro de texto mediante programación en tiempo de ejecución cambiando el <xref:System.Windows.Forms.TextBox.Text%2A> propiedad del cuadro de texto.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.TextBox>  
 [Información general sobre el control TextBox](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [Controlar el punto de inserción en un control TextBox de Windows Forms](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [Crear un cuadro de texto de contraseña con el control TextBox de Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [Insertar comillas en una cadena](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [Seleccionar texto en el control TextBox de Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [Ver múltiples líneas en el control TextBox de Windows Forms](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [Control TextBox](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
