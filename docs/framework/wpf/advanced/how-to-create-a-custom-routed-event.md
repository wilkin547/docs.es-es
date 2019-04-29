---
title: Procedimiento Crear un evento enrutado personalizado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], creating
- events [WPF], routing
ms.assetid: b79f459a-1c3f-4045-b2d4-1659cc8eaa3c
ms.openlocfilehash: a3850875c8ca747f8709b55f8fe721d25be24304
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776693"
---
# <a name="how-to-create-a-custom-routed-event"></a><span data-ttu-id="d1302-102">Procedimiento Crear un evento enrutado personalizado</span><span class="sxs-lookup"><span data-stu-id="d1302-102">How to: Create a Custom Routed Event</span></span>
<span data-ttu-id="d1302-103">Para que el evento personalizado admitir el enrutamiento de eventos, deberá registrar una <xref:System.Windows.RoutedEvent> utilizando el <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> método.</span><span class="sxs-lookup"><span data-stu-id="d1302-103">For your custom event to support event routing, you need to register a <xref:System.Windows.RoutedEvent> using the <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> method.</span></span> <span data-ttu-id="d1302-104">Este ejemplo muestra los aspectos básicos de la creación de un evento enrutado personalizado.</span><span class="sxs-lookup"><span data-stu-id="d1302-104">This example demonstrates the basics of creating a custom routed event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1302-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d1302-105">Example</span></span>  
 <span data-ttu-id="d1302-106">Como se muestra en el ejemplo siguiente, primero se registre un <xref:System.Windows.RoutedEvent> utilizando el <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> método.</span><span class="sxs-lookup"><span data-stu-id="d1302-106">As shown in the following example, you first register a <xref:System.Windows.RoutedEvent> using the <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> method.</span></span> <span data-ttu-id="d1302-107">Por convención, el <xref:System.Windows.RoutedEvent> nombre del campo estático debe terminar con el sufijo ***eventos***.</span><span class="sxs-lookup"><span data-stu-id="d1302-107">By convention, the <xref:System.Windows.RoutedEvent> static field name should end with the suffix ***Event***.</span></span> <span data-ttu-id="d1302-108">En este ejemplo, el nombre del evento es `Tap` y la estrategia de enrutamiento del evento es <xref:System.Windows.RoutingStrategy.Bubble>.</span><span class="sxs-lookup"><span data-stu-id="d1302-108">In this example, the name of the event is `Tap` and the routing strategy of the event is <xref:System.Windows.RoutingStrategy.Bubble>.</span></span> <span data-ttu-id="d1302-109">Después de la llamada de registro, puede proporcionar los descriptores de acceso de eventos de [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] add y remove del evento.</span><span class="sxs-lookup"><span data-stu-id="d1302-109">After the registration call, you can provide add-and-remove [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] event accessors for the event.</span></span>  
  
 <span data-ttu-id="d1302-110">Tenga en cuenta que, aunque el evento se genera a través del método virtual `OnTap` en este ejemplo concreto, cómo se genera el evento o cómo este responde a los cambios dependerá de sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="d1302-110">Note that even though the event is raised through the `OnTap` virtual method in this particular example, how you raise your event or how your event responds to changes depends on your needs.</span></span>  
  
 <span data-ttu-id="d1302-111">Tenga en cuenta también que este ejemplo implementa básicamente una subclase completa de <xref:System.Windows.Controls.Button>; esa subclase se compila como un ensamblado independiente y, a continuación, crea una instancia como una clase personalizada en otro [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] página.</span><span class="sxs-lookup"><span data-stu-id="d1302-111">Note also that this example basically implements an entire subclass of <xref:System.Windows.Controls.Button>; that subclass is built as a separate assembly and then instantiated as a custom class on a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page.</span></span> <span data-ttu-id="d1302-112">Este ejemplo pretende ilustrar el concepto de que los controles con subclases pueden insertarse en árboles formados por otros controles y que, en esta situación, los eventos personalizados de estos controles tienen las mismas funcionalidades de enrutamiento de eventos que cualquier elemento de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] nativo.</span><span class="sxs-lookup"><span data-stu-id="d1302-112">This is to illustrate the concept that subclassed controls can be inserted into trees composed of other controls, and that in this situation, custom events on these controls have the very same event routing capabilities as any native [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] element does.</span></span>  
  
 [!code-csharp[RoutedEventCustom#CustomClass](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/SDKSampleLibrary/class1.cs#customclass)]
 [!code-vb[RoutedEventCustom#CustomClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventCustom/VB/SDKSampleLibrary/Class1.vb#customclass)]  
  
 [!code-xaml[RoutedEventCustom#Page](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/RoutedEventCustomApp/default.xaml#page)]  
  
 <span data-ttu-id="d1302-113">Los eventos de tunelización se crean la misma manera, pero con <xref:System.Windows.RoutedEvent.RoutingStrategy%2A> establecido en <xref:System.Windows.RoutingStrategy.Tunnel> en la llamada de registro.</span><span class="sxs-lookup"><span data-stu-id="d1302-113">Tunneling events are created the same way, but with <xref:System.Windows.RoutedEvent.RoutingStrategy%2A> set to <xref:System.Windows.RoutingStrategy.Tunnel> in the registration call.</span></span> <span data-ttu-id="d1302-114">Por convención, a los eventos de tunelización de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se les antepone la palabra "Preview".</span><span class="sxs-lookup"><span data-stu-id="d1302-114">By convention, tunneling events in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] are prefixed with the word "Preview".</span></span>  
  
 <span data-ttu-id="d1302-115">Para ver un ejemplo de cómo funciona la propagación de eventos, consulte [Controlar un evento enrutado](how-to-handle-a-routed-event.md).</span><span class="sxs-lookup"><span data-stu-id="d1302-115">To see an example of how bubbling events work, see [Handle a Routed Event](how-to-handle-a-routed-event.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1302-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1302-116">See also</span></span>

- [<span data-ttu-id="d1302-117">Información general sobre eventos enrutados</span><span class="sxs-lookup"><span data-stu-id="d1302-117">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="d1302-118">Información general sobre acciones del usuario</span><span class="sxs-lookup"><span data-stu-id="d1302-118">Input Overview</span></span>](input-overview.md)
- [<span data-ttu-id="d1302-119">Información general sobre la creación de controles</span><span class="sxs-lookup"><span data-stu-id="d1302-119">Control Authoring Overview</span></span>](../controls/control-authoring-overview.md)
