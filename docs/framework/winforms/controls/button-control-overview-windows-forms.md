---
title: Información general sobre el control Button (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- Button
helpviewer_keywords:
- Button control [Windows Forms], about Button control
- buttons [Windows Forms], about buttons
ms.assetid: 255b291b-51a9-4a92-a1a4-2400cd82443f
ms.openlocfilehash: 1ded871fdfab83407d8022ca0c4ce6b2c8a6c67c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938988"
---
# <a name="button-control-overview-windows-forms"></a>Información general sobre el control Button (formularios Windows Forms)
El control <xref:System.Windows.Forms.Button> de Windows Forms permite al usuario hacer clic en él para llevar a cabo una acción. Al hacer clic en el botón, parece como si se hubiera presionado y soltado. Cada vez que el usuario hace clic en un botón, el <xref:System.Windows.Forms.Control.Click> se invoca el controlador de eventos. Colocar código en el <xref:System.Windows.Forms.Control.Click> controlador de eventos para realizar cualquier acción que elija.  
  
 El texto mostrado en el botón se encuentra en la <xref:System.Windows.Forms.Control.Text%2A> propiedad. Si el texto supera el ancho del botón, ajustará a la línea siguiente. Sin embargo, se recortará si el control no puede contener su altura total. Para obtener más información, vea [Cómo: Establecer el texto mostrado por un Windows Forms Control](how-to-set-the-text-displayed-by-a-windows-forms-control.md). El <xref:System.Windows.Forms.Control.Text%2A> propiedad puede contener una clave de acceso, que permite que un usuario "haga clic en" el control presionando la tecla ALT y la clave de acceso. Para obtener más detalles, vea [Cómo: Crear teclas de acceso para controles de Windows Forms](how-to-create-access-keys-for-windows-forms-controls.md). La apariencia del texto se controla mediante el <xref:System.Windows.Forms.Control.Font%2A> propiedad y el <xref:System.Windows.Forms.ButtonBase.TextAlign%2A> propiedad.  
  
 El <xref:System.Windows.Forms.Button> control también puede mostrar imágenes usando la <xref:System.Windows.Forms.ButtonBase.Image%2A> y <xref:System.Windows.Forms.ButtonBase.ImageList%2A> propiedades. Para obtener más información, vea [Cómo: Establecer la imagen que muestra un Windows Forms Control](how-to-set-the-image-displayed-by-a-windows-forms-control.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Button>
- [Cómo: Responder a clics de botón de Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Maneras de seleccionar un control Button de formularios Windows Forms](ways-to-select-a-windows-forms-button-control.md)
- [Cómo: Designar un botón de formularios Windows Forms como botón para aceptar mediante el diseñador](designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [Cómo: Designar un botón de formularios Windows Forms como botón para cancelar mediante el diseñador](designate-a-wf-button-as-the-cancel-button-using-the-designer.md)
- [Botón (control)](button-control-windows-forms.md)
