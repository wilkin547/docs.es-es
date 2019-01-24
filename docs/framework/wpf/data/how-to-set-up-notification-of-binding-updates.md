---
title: Procedimiento Configurar notificación de actualizaciones de enlaces
ms.date: 03/30/2017
helpviewer_keywords:
- notifications [WPF], binding updates
- data binding [WPF], notification of binding updates
- binding [WPF], updates [WPF], notifications of
ms.assetid: 5673073e-dbe1-49da-980a-484a88f9595a
ms.openlocfilehash: ca6af88d6ba8ba4e242faa5d1443ee95925fbe2c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54511870"
---
# <a name="how-to-set-up-notification-of-binding-updates"></a><span data-ttu-id="d9dad-102">Procedimiento Configurar notificación de actualizaciones de enlaces</span><span class="sxs-lookup"><span data-stu-id="d9dad-102">How to: Set Up Notification of Binding Updates</span></span>
<span data-ttu-id="d9dad-103">En este ejemplo se muestra cómo configurar la notificación cuando se ha actualizado la propiedad de destino del enlace (destino) o el origen del enlace (origen) de un enlace.</span><span class="sxs-lookup"><span data-stu-id="d9dad-103">This example shows how to set up to be notified when the binding target (target) or the binding source (source) property of a binding has been updated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9dad-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d9dad-104">Example</span></span>  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="d9dad-105">genera un evento de actualización de datos cada vez que se actualiza el origen o el destino del enlace.</span><span class="sxs-lookup"><span data-stu-id="d9dad-105">raises a data update event each time that the binding source or target has been updated.</span></span> <span data-ttu-id="d9dad-106">Internamente, este evento se usar para informar a [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] que debe actualizarse porque se han cambiado los datos enlazados.</span><span class="sxs-lookup"><span data-stu-id="d9dad-106">Internally, this event is used to inform the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] that it should update, because the bound data has changed.</span></span> <span data-ttu-id="d9dad-107">Tenga en cuenta que para estos eventos funcionen y también para el enlace unidireccional o bidireccional funcionen correctamente, debe implementar la clase de datos mediante el <xref:System.ComponentModel.INotifyPropertyChanged> interfaz.</span><span class="sxs-lookup"><span data-stu-id="d9dad-107">Note that for these events to work, and also for one-way or two-way binding to work properly, you need to implement your data class using the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="d9dad-108">Para más información, consulte [Cómo: Implementar la notificación de cambio de propiedad](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).</span><span class="sxs-lookup"><span data-stu-id="d9dad-108">For more information, see [Implement Property Change Notification](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).</span></span>  
  
 <span data-ttu-id="d9dad-109">Establecer el <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A> o <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A> propiedad (o ambos) para `true` en el enlace.</span><span class="sxs-lookup"><span data-stu-id="d9dad-109">Set the <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A> or <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A> property (or both) to `true` in the binding.</span></span> <span data-ttu-id="d9dad-110">El controlador que proporcione para la escucha de este evento debe adjuntarse directamente al elemento donde desee que se le informe de los cambios, o en el contexto de datos general si quiere que se le notifiquen los cambios en el contexto.</span><span class="sxs-lookup"><span data-stu-id="d9dad-110">The handler you provide to listen for this event must be attached directly to the element where you want to be informed of changes, or to the overall data context if you want to be aware that anything in the context has changed.</span></span>  
  
 <span data-ttu-id="d9dad-111">Este es un ejemplo que muestra cómo configurar las notificaciones cuando se ha actualizado una propiedad de destino.</span><span class="sxs-lookup"><span data-stu-id="d9dad-111">Here is an example that shows how to set up for notification when a target property has been updated.</span></span>  
  
 [!code-xaml[DirectionalBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#2)]  
  
 <span data-ttu-id="d9dad-112">Después puede asignar un controlador basado en el delegado EventHandler\<T>, *OnTargetUpdated* en este ejemplo, para controlar el evento:</span><span class="sxs-lookup"><span data-stu-id="d9dad-112">You can then assign a handler based on the EventHandler\<T> delegate, *OnTargetUpdated* in this example, to handle the event:</span></span>  
  
 [!code-csharp[DirectionalBinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#3)]  
[!code-csharp[DirectionalBinding#EndEvent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#endevent)]  
  
 <span data-ttu-id="d9dad-113">Los parámetros del evento pueden usarse para determinar los detalles sobre la propiedad que ha cambiado (como el tipo o el elemento específico si el mismo controlador se adjunta a más de un elemento), lo que puede resultar útil si hay varias propiedades enlazadas en un único elemento.</span><span class="sxs-lookup"><span data-stu-id="d9dad-113">Parameters of the event can be used to determine details about the property that changed (such as the type or the specific element if the same handler is attached to more than one element), which can be useful if there are multiple bound properties on a single element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9dad-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9dad-114">See also</span></span>
- [<span data-ttu-id="d9dad-115">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="d9dad-115">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [<span data-ttu-id="d9dad-116">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="d9dad-116">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
