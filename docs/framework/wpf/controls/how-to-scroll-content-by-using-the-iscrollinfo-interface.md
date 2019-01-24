---
title: Procedimiento Desplazarse por contenido utilizando la interfaz IScrollInfo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ScrollViewer control [WPF], scrolling content
- scrolling content [WPF]
- IScrollInfo interface [WPF]
ms.assetid: d8700bef-a3f8-4c12-9de2-fc3b79f32cd3
ms.openlocfilehash: 49b3483750582aa51d1de418f745d931604d2786
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54637864"
---
# <a name="how-to-scroll-content-by-using-the-iscrollinfo-interface"></a><span data-ttu-id="91f25-102">Procedimiento Desplazarse por contenido utilizando la interfaz IScrollInfo</span><span class="sxs-lookup"><span data-stu-id="91f25-102">How to: Scroll Content by Using the IScrollInfo Interface</span></span>
<span data-ttu-id="91f25-103">En este ejemplo se muestra cómo desplazarse por contenido utilizando la <xref:System.Windows.Controls.Primitives.IScrollInfo> interfaz.</span><span class="sxs-lookup"><span data-stu-id="91f25-103">This example shows how to scroll content by using the <xref:System.Windows.Controls.Primitives.IScrollInfo> interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91f25-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="91f25-104">Example</span></span>  
 <span data-ttu-id="91f25-105">El ejemplo siguiente muestra las características de la <xref:System.Windows.Controls.Primitives.IScrollInfo> interfaz.</span><span class="sxs-lookup"><span data-stu-id="91f25-105">The following example demonstrates the features of the <xref:System.Windows.Controls.Primitives.IScrollInfo> interface.</span></span> <span data-ttu-id="91f25-106">El ejemplo se crea un <xref:System.Windows.Controls.StackPanel> elemento [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] que está anidado en un elemento primario <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="91f25-106">The example creates a <xref:System.Windows.Controls.StackPanel> element in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that is nested in a parent <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="91f25-107">Los elementos secundarios de la <xref:System.Windows.Controls.StackPanel> se puede desplazar de forma lógica mediante el uso de los métodos definidos por el <xref:System.Windows.Controls.Primitives.IScrollInfo> interfaz y la conversión a la instancia de <xref:System.Windows.Controls.StackPanel> (`sp1`) en el código.</span><span class="sxs-lookup"><span data-stu-id="91f25-107">The child elements of the <xref:System.Windows.Controls.StackPanel> can be scrolled logically by using the methods defined by the <xref:System.Windows.Controls.Primitives.IScrollInfo> interface and cast to the instance of <xref:System.Windows.Controls.StackPanel> (`sp1`) in code.</span></span>  
  
 [!code-xaml[IScrollInfoMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="91f25-108">Cada <xref:System.Windows.Controls.Button> en el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivo desencadena un método personalizado asociado que controla el comportamiento de desplazamiento en <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="91f25-108">Each <xref:System.Windows.Controls.Button> in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file triggers an associated custom method that controls scrolling behavior in <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="91f25-109">El ejemplo siguiente muestra cómo usar el <xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> y <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A> métodos; genéricamente también se muestra cómo usar los métodos de posición que el <xref:System.Windows.Controls.Primitives.IScrollInfo> define la clase.</span><span class="sxs-lookup"><span data-stu-id="91f25-109">The following example shows how to use the <xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> and <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A> methods; it also generically shows how to use all the positioning methods that the <xref:System.Windows.Controls.Primitives.IScrollInfo> class defines.</span></span>  
  
 [!code-csharp[IScrollInfoMethods#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="91f25-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="91f25-110">See also</span></span>
- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.Primitives.IScrollInfo>
- <xref:System.Windows.Controls.StackPanel>
- [<span data-ttu-id="91f25-111">Información general sobre ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="91f25-111">ScrollViewer Overview</span></span>](../../../../docs/framework/wpf/controls/scrollviewer-overview.md)
- [<span data-ttu-id="91f25-112">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="91f25-112">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/scrollviewer-how-to-topics.md)
- [<span data-ttu-id="91f25-113">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="91f25-113">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
