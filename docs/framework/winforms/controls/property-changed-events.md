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
ms.openlocfilehash: 0ff5b3874d9de169f4a9f1040d601173af352c06
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703236"
---
# <a name="property-changed-events"></a>Eventos de cambio de propiedades
Si desea que el control para enviar notificaciones cuando una propiedad denominada *PropertyName* cambios, defina un evento denominado *PropertyName* `Changed` y un método denominado `On` *PropertyName* `Changed` que provoca el evento. La convención de nomenclatura en Windows Forms es anexar la palabra *Changed* en el nombre de la propiedad. El tipo de delegado de evento asociado para los eventos de cambio de propiedad es <xref:System.EventHandler>, y el tipo de datos de evento es <xref:System.EventArgs>. La clase base <xref:System.Windows.Forms.Control> define muchos eventos de cambio de propiedad, como <xref:System.Windows.Forms.Control.BackColorChanged>, <xref:System.Windows.Forms.Control.BackgroundImageChanged>, <xref:System.Windows.Forms.Control.FontChanged>, <xref:System.Windows.Forms.Control.LocationChanged>y otros. Para obtener información general sobre los eventos, vea [eventos](../../../standard/events/index.md) y [eventos en controles de formularios Windows Forms](events-in-windows-forms-controls.md).  
  
 Eventos de cambio de propiedad son útiles porque permiten que los consumidores de un control adjuntar controladores de eventos que responden al cambio. Si el control debe responder a un evento de cambio de propiedad que se inicia, invalidar correspondiente `On` *PropertyName* `Changed` en lugar de asociar un delegado al evento. Un control responde normalmente a un evento de cambio de propiedad mediante la actualización de otras propiedades o volver a dibujar algunos o todos de su superficie de dibujo.  
  
 El ejemplo siguiente se muestra cómo el `FlashTrackBar` que responde el control personalizado a algunos de los eventos de cambio de propiedad que hereda de <xref:System.Windows.Forms.Control>. Para obtener un ejemplo completo, vea [Cómo: Crear un Control de Windows Forms que muestre el progreso](how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#2)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#2)]  
  
## <a name="see-also"></a>Vea también
- [Eventos](../../../standard/events/index.md)
- [Eventos de los controles de Windows Forms](events-in-windows-forms-controls.md)
- [Propiedades de los controles de Windows Forms](properties-in-windows-forms-controls.md)
