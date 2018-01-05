---
title: "Cómo: Crear un evento enrutado personalizado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], creating
- events [WPF], routing
ms.assetid: b79f459a-1c3f-4045-b2d4-1659cc8eaa3c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ecd335cb08056cb8b7c696555d666f54cad81b87
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-custom-routed-event"></a><span data-ttu-id="10a83-102">Cómo: Crear un evento enrutado personalizado</span><span class="sxs-lookup"><span data-stu-id="10a83-102">How to: Create a Custom Routed Event</span></span>
<span data-ttu-id="10a83-103">Para que el evento personalizado admitir el enrutamiento de eventos, debe registrar un <xref:System.Windows.RoutedEvent> mediante el <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> método.</span><span class="sxs-lookup"><span data-stu-id="10a83-103">For your custom event to support event routing, you need to register a <xref:System.Windows.RoutedEvent> using the <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> method.</span></span> <span data-ttu-id="10a83-104">Este ejemplo muestra los aspectos básicos de la creación de un evento enrutado personalizado.</span><span class="sxs-lookup"><span data-stu-id="10a83-104">This example demonstrates the basics of creating a custom routed event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10a83-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="10a83-105">Example</span></span>  
 <span data-ttu-id="10a83-106">Como se muestra en el ejemplo siguiente, registre primero un <xref:System.Windows.RoutedEvent> mediante el <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> método.</span><span class="sxs-lookup"><span data-stu-id="10a83-106">As shown in the following example, you first register a <xref:System.Windows.RoutedEvent> using the <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> method.</span></span> <span data-ttu-id="10a83-107">Por convención, el <xref:System.Windows.RoutedEvent> nombre de campo estático debe finalizar con el sufijo ***eventos***.</span><span class="sxs-lookup"><span data-stu-id="10a83-107">By convention, the <xref:System.Windows.RoutedEvent> static field name should end with the suffix ***Event***.</span></span> <span data-ttu-id="10a83-108">En este ejemplo, el nombre del evento es `Tap` y la estrategia de enrutamiento del evento es <xref:System.Windows.RoutingStrategy.Bubble>.</span><span class="sxs-lookup"><span data-stu-id="10a83-108">In this example, the name of the event is `Tap` and the routing strategy of the event is <xref:System.Windows.RoutingStrategy.Bubble>.</span></span> <span data-ttu-id="10a83-109">Después de la llamada de registro, puede proporcionar los descriptores de acceso de eventos de [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] add y remove del evento.</span><span class="sxs-lookup"><span data-stu-id="10a83-109">After the registration call, you can provide add-and-remove [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] event accessors for the event.</span></span>  
  
 <span data-ttu-id="10a83-110">Tenga en cuenta que, aunque el evento se genera a través del método virtual `OnTap` en este ejemplo concreto, cómo se genera el evento o cómo este responde a los cambios dependerá de sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="10a83-110">Note that even though the event is raised through the `OnTap` virtual method in this particular example, how you raise your event or how your event responds to changes depends on your needs.</span></span>  
  
 <span data-ttu-id="10a83-111">Tenga en cuenta también que en este ejemplo se implementa básicamente una subclase completa de <xref:System.Windows.Controls.Button>; esa subclase se genera como un ensamblado independiente y, a continuación, crea una instancia como una clase personalizada en otro [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] página.</span><span class="sxs-lookup"><span data-stu-id="10a83-111">Note also that this example basically implements an entire subclass of <xref:System.Windows.Controls.Button>; that subclass is built as a separate assembly and then instantiated as a custom class on a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page.</span></span> <span data-ttu-id="10a83-112">Este ejemplo pretende ilustrar el concepto de que los controles con subclases pueden insertarse en árboles formados por otros controles y que, en esta situación, los eventos personalizados de estos controles tienen las mismas funcionalidades de enrutamiento de eventos que cualquier elemento de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] nativo.</span><span class="sxs-lookup"><span data-stu-id="10a83-112">This is to illustrate the concept that subclassed controls can be inserted into trees composed of other controls, and that in this situation, custom events on these controls have the very same event routing capabilities as any native [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] element does.</span></span>  
  
 [!code-csharp[RoutedEventCustom#CustomClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/SDKSampleLibrary/class1.cs#customclass)]
 [!code-vb[RoutedEventCustom#CustomClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventCustom/VB/SDKSampleLibrary/Class1.vb#customclass)]  
  
 [!code-xaml[RoutedEventCustom#Page](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/RoutedEventCustomApp/default.xaml#page)]  
  
 <span data-ttu-id="10a83-113">Los eventos de tunelización se crean la misma forma, pero con <xref:System.Windows.RoutedEvent.RoutingStrategy%2A> establecido en <xref:System.Windows.RoutingStrategy.Tunnel> en la llamada de registro.</span><span class="sxs-lookup"><span data-stu-id="10a83-113">Tunneling events are created the same way, but with <xref:System.Windows.RoutedEvent.RoutingStrategy%2A> set to <xref:System.Windows.RoutingStrategy.Tunnel> in the registration call.</span></span> <span data-ttu-id="10a83-114">Por convención, a los eventos de tunelización de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se les antepone la palabra "Preview".</span><span class="sxs-lookup"><span data-stu-id="10a83-114">By convention, tunneling events in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] are prefixed with the word "Preview".</span></span>  
  
 <span data-ttu-id="10a83-115">Para ver un ejemplo de cómo funciona la propagación de eventos, consulte [Controlar un evento enrutado](../../../../docs/framework/wpf/advanced/how-to-handle-a-routed-event.md).</span><span class="sxs-lookup"><span data-stu-id="10a83-115">To see an example of how bubbling events work, see [Handle a Routed Event](../../../../docs/framework/wpf/advanced/how-to-handle-a-routed-event.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10a83-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="10a83-116">See Also</span></span>  
 [<span data-ttu-id="10a83-117">Información general sobre eventos enrutados</span><span class="sxs-lookup"><span data-stu-id="10a83-117">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [<span data-ttu-id="10a83-118">Información general sobre acciones del usuario</span><span class="sxs-lookup"><span data-stu-id="10a83-118">Input Overview</span></span>](../../../../docs/framework/wpf/advanced/input-overview.md)  
 [<span data-ttu-id="10a83-119">Información general sobre la creación de controles</span><span class="sxs-lookup"><span data-stu-id="10a83-119">Control Authoring Overview</span></span>](../../../../docs/framework/wpf/controls/control-authoring-overview.md)
