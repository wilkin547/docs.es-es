---
title: Eventos de cambio de propiedades
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- properties [Windows Forms], changes
ms.assetid: 268039ec-5aaa-4d76-b902-acccb036c850
ms.openlocfilehash: f4e6a6267df88cdd33a58093f276c6005209f38d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="property-changed-events"></a>Eventos de cambio de propiedades
Si desea que el control para enviar notificaciones cuando una propiedad denominada *PropertyName* cambios, definir un evento denominado *PropertyName* `Changed` y un método denominado `On` *PropertyName* `Changed` que genera el evento. La convención de nomenclatura en formularios Windows Forms es anexar la palabra *Changed* al nombre de la propiedad. El tipo de delegado de evento asociado para eventos de cambio de propiedad es <xref:System.EventHandler>, y el tipo de datos de evento es <xref:System.EventArgs>. La clase base <xref:System.Windows.Forms.Control> define muchos eventos de cambio de propiedad, como <xref:System.Windows.Forms.Control.BackColorChanged>, <xref:System.Windows.Forms.Control.BackgroundImageChanged>, <xref:System.Windows.Forms.Control.FontChanged>, <xref:System.Windows.Forms.Control.LocationChanged>y otros. Para obtener información general acerca de los eventos, vea [eventos](../../../../docs/standard/events/index.md) y [eventos en controles de Windows Forms](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md).  
  
 Eventos de cambio de propiedad son útiles porque permite que los consumidores de un control adjuntar controladores de eventos que respondan al cambio. Si el control debe responder a un evento de cambio de propiedad que genera, invalidar correspondiente `On` *PropertyName* `Changed` método en lugar de adjuntar un delegado al evento. Normalmente, un control se responde a un evento cambiado por propiedad actualizando otras propiedades o volver a dibujar algunos o todos de su superficie de dibujo.  
  
 El siguiente ejemplo se muestra cómo el `FlashTrackBar` que responde el control personalizado a algunos de los eventos de cambio de propiedad que hereda de <xref:System.Windows.Forms.Control>. Para obtener un ejemplo completo, vea [Cómo: crear un Windows Forms Control That Shows Progress](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#2)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#2)]  
  
## <a name="see-also"></a>Vea también  
 [Eventos](../../../../docs/standard/events/index.md)  
 [Eventos de los controles de Windows Forms](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)  
 [Propiedades de los controles de Windows Forms](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)
