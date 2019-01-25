---
title: Procedimiento Controlar un evento cargado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XAML [WPF], Loaded events
- events [WPF], Loaded
- Loaded events [WPF]
ms.assetid: 0cf8d003-8441-4df4-807a-6db09347e829
ms.openlocfilehash: 187d75c436913140855f4d860eb3b6ad4656f309
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54682948"
---
# <a name="how-to-handle-a-loaded-event"></a><span data-ttu-id="dc1af-102">Procedimiento Controlar un evento cargado</span><span class="sxs-lookup"><span data-stu-id="dc1af-102">How to: Handle a Loaded Event</span></span>
<span data-ttu-id="dc1af-103">En este ejemplo se muestra cómo controlar el <xref:System.Windows.FrameworkElement.Loaded?displayProperty=nameWithType> eventos y un escenario adecuado para controlar ese evento.</span><span class="sxs-lookup"><span data-stu-id="dc1af-103">This example shows how to handle the <xref:System.Windows.FrameworkElement.Loaded?displayProperty=nameWithType> event, and an appropriate scenario for handling that event.</span></span> <span data-ttu-id="dc1af-104">El controlador crea un <xref:System.Windows.Controls.Button> cuando se cargue la página.</span><span class="sxs-lookup"><span data-stu-id="dc1af-104">The handler  creates a <xref:System.Windows.Controls.Button> when the page loads.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc1af-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dc1af-105">Example</span></span>  
 <span data-ttu-id="dc1af-106">En el ejemplo siguiente se usa [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] junto con un archivo de código subyacente.</span><span class="sxs-lookup"><span data-stu-id="dc1af-106">The following example uses [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] together with a code-behind file.</span></span>  
  
 [!code-xaml[FELoaded#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FELoaded#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml.cs#handler)]
 [!code-vb[FELoaded#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FELoaded/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a><span data-ttu-id="dc1af-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc1af-107">See also</span></span>
- <xref:System.Windows.FrameworkElement>
- [<span data-ttu-id="dc1af-108">Eventos de duración de objetos</span><span class="sxs-lookup"><span data-stu-id="dc1af-108">Object Lifetime Events</span></span>](../../../../docs/framework/wpf/advanced/object-lifetime-events.md)
- [<span data-ttu-id="dc1af-109">Información general sobre eventos enrutados</span><span class="sxs-lookup"><span data-stu-id="dc1af-109">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
- [<span data-ttu-id="dc1af-110">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="dc1af-110">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
