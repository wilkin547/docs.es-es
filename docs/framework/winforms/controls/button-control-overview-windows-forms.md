---
title: Información general sobre el control Button
ms.date: 03/30/2017
f1_keywords:
- Button
helpviewer_keywords:
- Button control [Windows Forms], about Button control
- buttons [Windows Forms], about buttons
ms.assetid: 255b291b-51a9-4a92-a1a4-2400cd82443f
ms.openlocfilehash: 4ba7b333e5414efb4814d64ce50c55e08b27f859
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747079"
---
# <a name="button-control-overview-windows-forms"></a>Información general sobre el control Button (Windows Forms)
El control <xref:System.Windows.Forms.Button> de Windows Forms permite al usuario hacer clic en él para llevar a cabo una acción. Al hacer clic en el botón, parece como si se hubiera presionado y soltado. Siempre que el usuario hace clic en un botón, se invoca el controlador de eventos <xref:System.Windows.Forms.Control.Click>. Coloque el código en el controlador de eventos <xref:System.Windows.Forms.Control.Click> para realizar cualquier acción que elija.  
  
 El texto que se muestra en el botón está contenido en la propiedad <xref:System.Windows.Forms.Control.Text%2A>. Si el texto supera el ancho del botón, se ajustará a la línea siguiente. Sin embargo, se recortará si el control no puede dar cabida a su alto total. Para obtener más información, vea [Cómo: establecer el texto mostrado por un control de Windows Forms](how-to-set-the-text-displayed-by-a-windows-forms-control.md). La propiedad <xref:System.Windows.Forms.Control.Text%2A> puede contener una tecla de acceso, que permite al usuario "hacer clic" en el control presionando la tecla ALT con la tecla de acceso. Para obtener más información, consulte [Cómo: crear claves de acceso para controles de Windows Forms](how-to-create-access-keys-for-windows-forms-controls.md). La apariencia del texto se controla mediante la propiedad <xref:System.Windows.Forms.Control.Font%2A> y la propiedad <xref:System.Windows.Forms.ButtonBase.TextAlign%2A>.  
  
 El control <xref:System.Windows.Forms.Button> también puede mostrar imágenes mediante las propiedades <xref:System.Windows.Forms.ButtonBase.Image%2A> y <xref:System.Windows.Forms.ButtonBase.ImageList%2A>. Para obtener más información, vea [Cómo: establecer la imagen mostrada por un Control Windows Forms](how-to-set-the-image-displayed-by-a-windows-forms-control.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Button>
- [Responder a clics de botones en Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Maneras de seleccionar un control Button de formularios Windows Forms](ways-to-select-a-windows-forms-button-control.md)
- [Procedimiento para designar un botón de formularios Windows Forms como botón para aceptar mediante el diseñador](designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [Procedimiento para designar un botón de formularios Windows Forms como botón para cancelar mediante el diseñador](designate-a-wf-button-as-the-cancel-button-using-the-designer.md)
- [Botón (control)](button-control-windows-forms.md)
