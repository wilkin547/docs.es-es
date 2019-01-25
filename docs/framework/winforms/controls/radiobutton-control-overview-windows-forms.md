---
title: Información general sobre el control RadioButton (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- RadioButton
helpviewer_keywords:
- RadioButton control [Windows Forms], about RadioButton control
- RadioButton control [Windows Forms], determining state
- radio buttons [Windows Forms], determining state
- radio buttons [Windows Forms], about radio buttons
ms.assetid: cd11f0c2-d098-4022-adf9-1455bc166a13
ms.openlocfilehash: d07fd4028385dac25ae7413a54f72b331ab91eb6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558402"
---
# <a name="radiobutton-control-overview-windows-forms"></a>Información general sobre el control RadioButton (formularios Windows Forms)
Windows Forms <xref:System.Windows.Forms.RadioButton> controles presentan un conjunto de dos o más opciones mutuamente excluyentes para el usuario. Aunque los botones de radio y casillas de verificación puede parecer que funcionan de forma similar, hay una diferencia importante: cuando un usuario selecciona un botón de radio, los otros botones de radio en el mismo grupo no se puede seleccionar también. En cambio, se puede seleccionar cualquier número de casillas de verificación. Definir un grupo de botones de radio indica al usuario, "Aquí se muestra un conjunto de opciones desde el que puede elegir uno y solo uno."  
  
## <a name="using-the-control"></a>Uso del Control  
 Cuando un <xref:System.Windows.Forms.RadioButton> se hace clic en el control, su <xref:System.Windows.Forms.RadioButton.Checked%2A> propiedad está establecida en `true` y <xref:System.Windows.Forms.Control.Click> se llama al controlador de eventos. El <xref:System.Windows.Forms.RadioButton.CheckedChanged> evento se desencadena cuando el valor de la <xref:System.Windows.Forms.RadioButton.Checked%2A> los cambios de propiedad. Si el <xref:System.Windows.Forms.RadioButton.AutoCheck%2A> propiedad está establecida en `true` (valor predeterminado), cuando se selecciona el botón de radio todos los demás miembros del grupo se borran automáticamente. Normalmente, esta propiedad es sólo se establece en `false` cuando se usa el código de validación para asegurarse de que el botón de radio seleccionado es una opción válida. El texto mostrado en el control se establece con el <xref:System.Windows.Forms.Control.Text%2A> propiedad, que puede contener teclas de acceso directo. Una clave de acceso permite que un usuario "haga clic en" el control presionando la tecla ALT y la clave de acceso. Para obtener más información, vea [Cómo: Crear teclas de acceso para controles de Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md) y [Cómo: Establecer el texto mostrado por un Windows Forms Control](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md).  
  
 El <xref:System.Windows.Forms.RadioButton> control puede aparecer como un botón de comando, que parece que se ha presionado cuando está seleccionado, si la <xref:System.Windows.Forms.RadioButton.Appearance%2A> propiedad está establecida en <xref:System.Windows.Forms.Appearance.Button>. Botones de radio también pueden mostrar imágenes usando la <xref:System.Windows.Forms.ButtonBase.Image%2A> y <xref:System.Windows.Forms.ButtonBase.ImageList%2A> propiedades. Para obtener más información, vea [Cómo: Establecer la imagen que muestra un Windows Forms Control](../../../../docs/framework/winforms/controls/how-to-set-the-image-displayed-by-a-windows-forms-control.md).  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.RadioButton>
- [Información general del control Panel](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)
- [Información general sobre el control GroupBox](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md)
- [Información general sobre el control CheckBox](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)
- [Cómo: Crear teclas de acceso para controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)
- [Cómo: Establecer el texto mostrado por un Windows Forms Control](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Cómo: Controles de grupo Windows Forms RadioButton funcione como un conjunto](../../../../docs/framework/winforms/controls/how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md)
- [RadioButton (control)](../../../../docs/framework/winforms/controls/radiobutton-control-windows-forms.md)
