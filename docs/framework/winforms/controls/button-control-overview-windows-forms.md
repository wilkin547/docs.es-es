---
title: "Información general sobre el control Button (formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Button
helpviewer_keywords:
- Button control [Windows Forms], about Button control
- buttons [Windows Forms], about buttons
ms.assetid: 255b291b-51a9-4a92-a1a4-2400cd82443f
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ff98eb39113a2fa8117d091645ac04526e2983c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="button-control-overview-windows-forms"></a>Información general sobre el control Button (formularios Windows Forms)
El control <xref:System.Windows.Forms.Button> de Windows Forms permite al usuario hacer clic en él para llevar a cabo una acción. Al hacer clic en el botón, parece como si se hubiera presionado y soltado. Cada vez que el usuario hace clic en un botón, el <xref:System.Windows.Forms.Control.Click> se invoca el controlador de eventos. Colocar código en el <xref:System.Windows.Forms.Control.Click> controlador de eventos para realizar cualquier acción que elija.  
  
 El texto mostrado en el botón se encuentra en la <xref:System.Windows.Forms.Control.Text%2A> propiedad. Si el texto excede el ancho del botón, se ajustará a la línea siguiente. Sin embargo, se recortará si el control no puede contener su altura general. Para obtener más información, consulte [Cómo: establecer el texto que se muestra en un Control de Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md). El <xref:System.Windows.Forms.Control.Text%2A> propiedad puede contener una clave de acceso, que permite a un usuario para "hacer clic" en el control presionando la tecla ALT y la tecla de acceso. Para obtener más información, consulte [Cómo: crear teclas de acceso para controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md). La apariencia del texto está controlada por el <xref:System.Windows.Forms.Control.Font%2A> propiedad y el <xref:System.Windows.Forms.ButtonBase.TextAlign%2A> propiedad.  
  
 El <xref:System.Windows.Forms.Button> control también puede mostrar imágenes con la <xref:System.Windows.Forms.ButtonBase.Image%2A> y <xref:System.Windows.Forms.ButtonBase.ImageList%2A> propiedades. Para obtener más información, consulte [Cómo: establecer la imagen muestra un Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-image-displayed-by-a-windows-forms-control.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.Button>  
 [Responder a clics de botones en Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [Maneras de seleccionar un control Button de formularios Windows Forms](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [Procedimiento para designar un botón de formularios Windows Forms como botón para aceptar mediante el diseñador](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-accept-button-using-the-designer.md)  
 [Procedimiento para designar un botón de formularios Windows Forms como botón para cancelar mediante el diseñador](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-cancel-button-using-the-designer.md)  
 [Botón (control)](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
