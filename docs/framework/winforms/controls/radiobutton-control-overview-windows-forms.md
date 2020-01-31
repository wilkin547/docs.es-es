---
title: Información general sobre el control RadioButton
ms.date: 03/30/2017
f1_keywords:
- RadioButton
helpviewer_keywords:
- RadioButton control [Windows Forms], about RadioButton control
- RadioButton control [Windows Forms], determining state
- radio buttons [Windows Forms], determining state
- radio buttons [Windows Forms], about radio buttons
ms.assetid: cd11f0c2-d098-4022-adf9-1455bc166a13
ms.openlocfilehash: bbc93046b69d39caadde4986ff56f067fc206a9e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741133"
---
# <a name="radiobutton-control-overview-windows-forms"></a>Información general sobre el control RadioButton (formularios Windows Forms)
Windows Forms los controles de <xref:System.Windows.Forms.RadioButton> presentan un conjunto de dos o más opciones mutuamente excluyentes para el usuario. Aunque puede parecer que los botones de radio y las casillas funcionan de forma similar, hay una diferencia importante: cuando un usuario selecciona un botón de radio, los demás botones de radio del mismo grupo no se pueden seleccionar también. En cambio, se puede seleccionar cualquier número de casillas. Al definir un grupo de botones de radio se indica al usuario "a continuación se muestra un conjunto de opciones entre las que puede elegir una y solo una".  
  
## <a name="using-the-control"></a>Usar el control  
 Cuando se hace clic en un control de <xref:System.Windows.Forms.RadioButton>, su propiedad <xref:System.Windows.Forms.RadioButton.Checked%2A> se establece en `true` y se llama al controlador de eventos <xref:System.Windows.Forms.Control.Click>. El evento <xref:System.Windows.Forms.RadioButton.CheckedChanged> se genera cuando cambia el valor de la propiedad <xref:System.Windows.Forms.RadioButton.Checked%2A>. Si la propiedad <xref:System.Windows.Forms.RadioButton.AutoCheck%2A> está establecida en `true` (el valor predeterminado), cuando se selecciona el botón de radio, se borran automáticamente los demás elementos del grupo. Normalmente, esta propiedad solo se establece en `false` cuando se usa el código de validación para asegurarse de que el botón de radio seleccionado es una opción permitida. El texto que se muestra en el control se establece con la propiedad <xref:System.Windows.Forms.Control.Text%2A>, que puede contener accesos directos a teclas de acceso. Una tecla de acceso permite al usuario "hacer clic" en el control presionando la tecla ALT con la tecla de acceso. Para obtener más información, vea [Cómo: crear claves de acceso para Windows Forms controles](how-to-create-access-keys-for-windows-forms-controls.md) y [Cómo: establecer el texto mostrado por un control Windows Forms](how-to-set-the-text-displayed-by-a-windows-forms-control.md).  
  
 El control <xref:System.Windows.Forms.RadioButton> puede aparecer como un botón de comando, que parece que se ha presionado si se selecciona, si la propiedad <xref:System.Windows.Forms.RadioButton.Appearance%2A> está establecida en <xref:System.Windows.Forms.Appearance.Button>. Los botones de radio también pueden mostrar imágenes mediante las propiedades <xref:System.Windows.Forms.ButtonBase.Image%2A> y <xref:System.Windows.Forms.ButtonBase.ImageList%2A>. Para obtener más información, vea [Cómo: establecer la imagen mostrada por un Control Windows Forms](how-to-set-the-image-displayed-by-a-windows-forms-control.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.RadioButton>
- [Información general del control Panel](panel-control-overview-windows-forms.md)
- [Información general sobre el control GroupBox](groupbox-control-overview-windows-forms.md)
- [Información general sobre el control CheckBox](checkbox-control-overview-windows-forms.md)
- [Crear teclas de acceso para controles de Windows Forms](how-to-create-access-keys-for-windows-forms-controls.md)
- [Establecer el texto mostrado por un control de Windows Forms](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Procedimiento para agrupar controles RadioButton de formularios Windows Forms para que funcionen como un conjunto](how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md)
- [RadioButton (control)](radiobutton-control-windows-forms.md)
