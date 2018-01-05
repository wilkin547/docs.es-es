---
title: "Cómo: Controlar un evento enrutado"
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
- routed events [WPF], handling
- bubbling events [WPF]
ms.assetid: 157787b4-f469-4047-8777-5b034145f32e
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c491ff4e231d932b3714d2d059b52bad2502368c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-handle-a-routed-event"></a><span data-ttu-id="3bb30-102">Cómo: Controlar un evento enrutado</span><span class="sxs-lookup"><span data-stu-id="3bb30-102">How to: Handle a Routed Event</span></span>
<span data-ttu-id="3bb30-103">En este ejemplo se muestra cómo funciona la propagación de eventos y cómo se escribe un controlador capaz de procesar los datos de eventos enrutados.</span><span class="sxs-lookup"><span data-stu-id="3bb30-103">This example shows how bubbling events work and how to write a handler that can process the routed event data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3bb30-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3bb30-104">Example</span></span>  
 <span data-ttu-id="3bb30-105">En [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], los elementos se organizan en una estructura de árbol de elementos.</span><span class="sxs-lookup"><span data-stu-id="3bb30-105">In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], elements are arranged in an element tree structure.</span></span> <span data-ttu-id="3bb30-106">El elemento primario puede participar en el control de eventos generados inicialmente por elementos secundarios en el árbol de elementos.</span><span class="sxs-lookup"><span data-stu-id="3bb30-106">The parent element can participate in the handling of events that are initially raised by child elements in the element tree.</span></span> <span data-ttu-id="3bb30-107">Esto es posible gracias al enrutamiento de eventos.</span><span class="sxs-lookup"><span data-stu-id="3bb30-107">This is possible because of event routing.</span></span>  
  
 <span data-ttu-id="3bb30-108">Normalmente, los eventos enrutados siguen una de las dos estrategias de enrutamiento posibles: propagación o tunelización.</span><span class="sxs-lookup"><span data-stu-id="3bb30-108">Routed events typically follow one of two routing strategies, bubbling or tunneling.</span></span> <span data-ttu-id="3bb30-109">En este ejemplo se centra en el evento de propagación y usa el <xref:System.Windows.Controls.Primitives.ButtonBase.Click?displayProperty=nameWithType> eventos para mostrar cómo funciona el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="3bb30-109">This example focuses on the bubbling event and uses the <xref:System.Windows.Controls.Primitives.ButtonBase.Click?displayProperty=nameWithType> event to show how routing works.</span></span>  
  
 <span data-ttu-id="3bb30-110">En el ejemplo siguiente se crea dos <xref:System.Windows.Controls.Button> controla y usa [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] atributo sintaxis para adjuntar un controlador de eventos a un elemento primario común, que en este ejemplo es <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="3bb30-110">The following example creates two <xref:System.Windows.Controls.Button> controls and uses [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attribute syntax to attach an event handler to a common parent element, which in this example is <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="3bb30-111">En lugar de adjuntar controladores de eventos individuales para cada <xref:System.Windows.Controls.Button> elemento secundario, el ejemplo usa la sintaxis de atributo para asociar el controlador de eventos para el <xref:System.Windows.Controls.StackPanel> elemento primario.</span><span class="sxs-lookup"><span data-stu-id="3bb30-111">Instead of attaching individual event handlers for each <xref:System.Windows.Controls.Button> child element, the example uses attribute syntax to attach the event handler to the <xref:System.Windows.Controls.StackPanel> parent element.</span></span> <span data-ttu-id="3bb30-112">Este patrón de control de eventos muestra cómo usar el enrutamiento de eventos como técnica para reducir el número de elementos en los que se adjunta un controlador.</span><span class="sxs-lookup"><span data-stu-id="3bb30-112">This event-handling pattern shows how to use event routing as a technique for reducing the number of elements where a handler is attached.</span></span> <span data-ttu-id="3bb30-113">Todos los eventos de propagación para cada <xref:System.Windows.Controls.Button> ruta a través del elemento primario.</span><span class="sxs-lookup"><span data-stu-id="3bb30-113">All the bubbling events for each <xref:System.Windows.Controls.Button> route through the parent element.</span></span>  
  
 <span data-ttu-id="3bb30-114">Tenga en cuenta que en el registro primario <xref:System.Windows.Controls.StackPanel> elemento, el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> nombre de evento especificado como el atributo se certifica parcialmente nombrando la <xref:System.Windows.Controls.Button> clase.</span><span class="sxs-lookup"><span data-stu-id="3bb30-114">Note that on the parent <xref:System.Windows.Controls.StackPanel> element, the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event name specified as the attribute is partially qualified by naming the <xref:System.Windows.Controls.Button> class.</span></span> <span data-ttu-id="3bb30-115">El <xref:System.Windows.Controls.Button> clase es un <xref:System.Windows.Controls.Primitives.ButtonBase> clase derivada que tiene el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento en su lista de miembros.</span><span class="sxs-lookup"><span data-stu-id="3bb30-115">The <xref:System.Windows.Controls.Button> class is a <xref:System.Windows.Controls.Primitives.ButtonBase> derived class that has the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event in its members listing.</span></span> <span data-ttu-id="3bb30-116">Esta técnica de calificación parcial para adjuntar un controlador de eventos es necesaria si el evento que se controla no existe en la lista de miembros del elemento donde está adjunto el controlador de eventos enrutados.</span><span class="sxs-lookup"><span data-stu-id="3bb30-116">This partial qualification technique for attaching an event handler is necessary if the event that is being handled does not exist in the members listing of the element where the routed event handler is attached.</span></span>  
  
 [!code-xaml[RoutedEventHandle#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventHandle/CSharp/default.xaml#xaml)]  
  
 <span data-ttu-id="3bb30-117">El siguiente ejemplo se controla el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventos.</span><span class="sxs-lookup"><span data-stu-id="3bb30-117">The following example handles the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event.</span></span>  <span data-ttu-id="3bb30-118">En el ejemplo se notifican el elemento que controla el evento y el elemento que lo genera.</span><span class="sxs-lookup"><span data-stu-id="3bb30-118">The example reports which element handles the event and which element raises the event.</span></span> <span data-ttu-id="3bb30-119">El controlador de eventos se ejecuta cuando el usuario hace clic en cualquiera de los botones.</span><span class="sxs-lookup"><span data-stu-id="3bb30-119">The event handler is executed when the user clicks either button.</span></span>  
  
 [!code-csharp[RoutedEventHandle#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventHandle/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventHandle#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventHandle/VisualBasic/MainWindow.xaml.vb#handler)]  
  
## <a name="see-also"></a><span data-ttu-id="3bb30-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="3bb30-120">See Also</span></span>  
 <xref:System.Windows.RoutedEvent>  
 [<span data-ttu-id="3bb30-121">Información general sobre acciones del usuario</span><span class="sxs-lookup"><span data-stu-id="3bb30-121">Input Overview</span></span>](../../../../docs/framework/wpf/advanced/input-overview.md)  
 [<span data-ttu-id="3bb30-122">Información general sobre eventos enrutados</span><span class="sxs-lookup"><span data-stu-id="3bb30-122">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [<span data-ttu-id="3bb30-123">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="3bb30-123">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)  
 [<span data-ttu-id="3bb30-124">Detalles de la sintaxis XAML</span><span class="sxs-lookup"><span data-stu-id="3bb30-124">XAML Syntax In Detail</span></span>](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)
