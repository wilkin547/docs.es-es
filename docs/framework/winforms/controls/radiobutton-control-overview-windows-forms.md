---
title: "Información general sobre el control RadioButton (formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: RadioButton
helpviewer_keywords:
- RadioButton control [Windows Forms], about RadioButton control
- RadioButton control [Windows Forms], determining state
- radio buttons [Windows Forms], determining state
- radio buttons [Windows Forms], about radio buttons
ms.assetid: cd11f0c2-d098-4022-adf9-1455bc166a13
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ac0a04c506919ef807a3f8c5ed5aa75ee998f64a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="radiobutton-control-overview-windows-forms"></a>Información general sobre el control RadioButton (formularios Windows Forms)
Formularios Windows Forms <xref:System.Windows.Forms.RadioButton> controles presentan un conjunto de dos o más opciones mutuamente excluyentes para el usuario. Aunque puede parecer que los botones de radio y casillas de verificación funcionan de forma similar, hay una diferencia importante: cuando un usuario selecciona un botón de opción, los otros botones de radio en el mismo grupo no se puede seleccionar también. En cambio, puede seleccionar cualquier número de casillas de verificación. Definir un grupo de botones de radio, indica al usuario, "Aquí es un conjunto de opciones desde el que puede elegir una y solamente una".  
  
## <a name="using-the-control"></a>Usar el Control  
 Cuando un <xref:System.Windows.Forms.RadioButton> se hace clic en el control, su <xref:System.Windows.Forms.RadioButton.Checked%2A> propiedad está establecida en `true` y <xref:System.Windows.Forms.Control.Click> se llama al controlador de eventos. El <xref:System.Windows.Forms.RadioButton.CheckedChanged> evento se desencadena cuando el valor de la <xref:System.Windows.Forms.RadioButton.Checked%2A> cambios de propiedad. Si el <xref:System.Windows.Forms.RadioButton.AutoCheck%2A> propiedad está establecida en `true` (valor predeterminado), cuando se selecciona el botón de radio automáticamente se borran todos los demás en el grupo. Normalmente, esta propiedad es solo se establece en `false` cuando se utiliza el código de validación para asegurarse de que el botón de radio seleccionado corresponde a una opción válida. El texto mostrado en el control se establece con el <xref:System.Windows.Forms.Control.Text%2A> propiedad, que puede contener teclas de acceso directo. Una tecla de acceso permite a un usuario para "hacer clic" en el control presionando la tecla ALT y la tecla de acceso. Para obtener más información, consulte [Cómo: crear teclas de acceso para controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md) y [Cómo: establecer el texto que se muestra en un Control de Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md).  
  
 El <xref:System.Windows.Forms.RadioButton> control puede aparecer como un botón de comando, que parece que ha presionado cuando está seleccionado, si la <xref:System.Windows.Forms.RadioButton.Appearance%2A> propiedad está establecida en <xref:System.Windows.Forms.Appearance.Button>. Botones de radio también pueden mostrar imágenes con la <xref:System.Windows.Forms.ButtonBase.Image%2A> y <xref:System.Windows.Forms.ButtonBase.ImageList%2A> propiedades. Para obtener más información, consulte [Cómo: establecer la imagen muestra un Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-image-displayed-by-a-windows-forms-control.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.RadioButton>  
 [Información general del control Panel](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [Información general sobre el control GroupBox](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md)  
 [Información general sobre el control CheckBox](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)  
 [Crear teclas de acceso para controles de Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)  
 [Establecer el texto mostrado por un control de Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [Procedimiento para agrupar controles RadioButton de formularios Windows Forms para que funcionen como un conjunto](../../../../docs/framework/winforms/controls/how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md)  
 [RadioButton (control)](../../../../docs/framework/winforms/controls/radiobutton-control-windows-forms.md)
