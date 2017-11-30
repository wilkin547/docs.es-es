---
title: Eventos de cambio de propiedades
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- properties [Windows Forms], changes
ms.assetid: 268039ec-5aaa-4d76-b902-acccb036c850
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7685891e99f1dcb2ca9e515c7dc6d7730ff0b2e5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="property-changed-events"></a><span data-ttu-id="cf646-102">Eventos de cambio de propiedades</span><span class="sxs-lookup"><span data-stu-id="cf646-102">Property-Changed Events</span></span>
<span data-ttu-id="cf646-103">Si desea que el control para enviar notificaciones cuando una propiedad denominada *PropertyName* cambios, definir un evento denominado *PropertyName* `Changed` y un método denominado `On` *PropertyName* `Changed` que genera el evento.</span><span class="sxs-lookup"><span data-stu-id="cf646-103">If you want your control to send notifications when a property named *PropertyName* changes, define an event named *PropertyName*`Changed` and a method named `On`*PropertyName*`Changed` that raises the event.</span></span> <span data-ttu-id="cf646-104">La convención de nomenclatura en formularios Windows Forms es anexar la palabra *Changed* al nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="cf646-104">The naming convention in Windows Forms is to append the word *Changed* to the name of the property.</span></span> <span data-ttu-id="cf646-105">El tipo de delegado de evento asociado para eventos de cambio de propiedad es <xref:System.EventHandler>, y el tipo de datos de evento es <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="cf646-105">The associated event delegate type for property-changed events is <xref:System.EventHandler>, and the event data type is <xref:System.EventArgs>.</span></span> <span data-ttu-id="cf646-106">La clase base <xref:System.Windows.Forms.Control> define muchos eventos de cambio de propiedad, como <xref:System.Windows.Forms.Control.BackColorChanged>, <xref:System.Windows.Forms.Control.BackgroundImageChanged>, <xref:System.Windows.Forms.Control.FontChanged>, <xref:System.Windows.Forms.Control.LocationChanged>y otros.</span><span class="sxs-lookup"><span data-stu-id="cf646-106">The base class <xref:System.Windows.Forms.Control> defines many property-changed events, such as <xref:System.Windows.Forms.Control.BackColorChanged>, <xref:System.Windows.Forms.Control.BackgroundImageChanged>, <xref:System.Windows.Forms.Control.FontChanged>, <xref:System.Windows.Forms.Control.LocationChanged>, and others.</span></span> <span data-ttu-id="cf646-107">Para obtener información general acerca de los eventos, vea [eventos](../../../../docs/standard/events/index.md) y [eventos en controles de Windows Forms](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="cf646-107">For background information about events, see [Events](../../../../docs/standard/events/index.md) and [Events in Windows Forms Controls](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md).</span></span>  
  
 <span data-ttu-id="cf646-108">Eventos de cambio de propiedad son útiles porque permite que los consumidores de un control adjuntar controladores de eventos que respondan al cambio.</span><span class="sxs-lookup"><span data-stu-id="cf646-108">Property-changed events are useful because they allow consumers of a control to attach event handlers that respond to the change.</span></span> <span data-ttu-id="cf646-109">Si el control debe responder a un evento de cambio de propiedad que genera, invalidar correspondiente `On` *PropertyName* `Changed` método en lugar de adjuntar un delegado al evento.</span><span class="sxs-lookup"><span data-stu-id="cf646-109">If your control needs to respond to a property-changed event that it raises, override the corresponding `On`*PropertyName*`Changed` method instead of attaching a delegate to the event.</span></span> <span data-ttu-id="cf646-110">Normalmente, un control se responde a un evento cambiado por propiedad actualizando otras propiedades o volver a dibujar algunos o todos de su superficie de dibujo.</span><span class="sxs-lookup"><span data-stu-id="cf646-110">A control typically responds to a property-changed event by updating other properties or by redrawing some or all of its drawing surface.</span></span>  
  
 <span data-ttu-id="cf646-111">El siguiente ejemplo se muestra cómo el `FlashTrackBar` que responde el control personalizado a algunos de los eventos de cambio de propiedad que hereda de <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="cf646-111">The following example shows how the `FlashTrackBar` custom control responds to some of the property-changed events that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="cf646-112">Para obtener un ejemplo completo, vea [Cómo: crear un Windows Forms Control That Shows Progress](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).</span><span class="sxs-lookup"><span data-stu-id="cf646-112">For the complete sample, see [How to: Create a Windows Forms Control That Shows Progress](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#2)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="cf646-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf646-113">See Also</span></span>  
 [<span data-ttu-id="cf646-114">Eventos</span><span class="sxs-lookup"><span data-stu-id="cf646-114">Events</span></span>](../../../../docs/standard/events/index.md)  
 [<span data-ttu-id="cf646-115">Eventos de los controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cf646-115">Events in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)  
 [<span data-ttu-id="cf646-116">Propiedades de los controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cf646-116">Properties in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)
