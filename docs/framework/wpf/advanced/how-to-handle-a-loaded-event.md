---
title: Filtrar Controlar un evento cargado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XAML [WPF], Loaded events
- events [WPF], Loaded
- Loaded events [WPF]
ms.assetid: 0cf8d003-8441-4df4-807a-6db09347e829
ms.openlocfilehash: a4916d3cfd20d082a8466f61fc74e16db2f0f346
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57353353"
---
# <a name="how-to-handle-a-loaded-event"></a><span data-ttu-id="6b041-102">Filtrar Controlar un evento cargado</span><span class="sxs-lookup"><span data-stu-id="6b041-102">How to: Handle a Loaded Event</span></span>
<span data-ttu-id="6b041-103">En este ejemplo se muestra cómo controlar el <xref:System.Windows.FrameworkElement.Loaded?displayProperty=nameWithType> eventos y un escenario adecuado para controlar ese evento.</span><span class="sxs-lookup"><span data-stu-id="6b041-103">This example shows how to handle the <xref:System.Windows.FrameworkElement.Loaded?displayProperty=nameWithType> event, and an appropriate scenario for handling that event.</span></span> <span data-ttu-id="6b041-104">El controlador crea un <xref:System.Windows.Controls.Button> cuando se cargue la página.</span><span class="sxs-lookup"><span data-stu-id="6b041-104">The handler  creates a <xref:System.Windows.Controls.Button> when the page loads.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b041-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6b041-105">Example</span></span>  
 <span data-ttu-id="6b041-106">En el ejemplo siguiente se usa [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] junto con un archivo de código subyacente.</span><span class="sxs-lookup"><span data-stu-id="6b041-106">The following example uses [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] together with a code-behind file.</span></span>  
  
 [!code-xaml[FELoaded#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FELoaded#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml.cs#handler)]
 [!code-vb[FELoaded#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FELoaded/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a><span data-ttu-id="6b041-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b041-107">See also</span></span>
- <xref:System.Windows.FrameworkElement>
- [<span data-ttu-id="6b041-108">Eventos de duración de objetos</span><span class="sxs-lookup"><span data-stu-id="6b041-108">Object Lifetime Events</span></span>](object-lifetime-events.md)
- [<span data-ttu-id="6b041-109">Información general sobre eventos enrutados</span><span class="sxs-lookup"><span data-stu-id="6b041-109">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="6b041-110">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="6b041-110">How-to Topics</span></span>](base-elements-how-to-topics.md)
