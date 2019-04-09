---
title: Filtrar Enumerar el contenido de un dibujo de un objeto visual
ms.date: 03/30/2017
helpviewer_keywords:
- retrieving the DrawingGroup value of a Visual [WPF]
- enumerating the contents of a Visual [WPF]
ms.assetid: 2974ddb3-2997-4713-8fd2-e93d549c58a8
ms.openlocfilehash: 4f0afc1075fe66c7f154fcef3cd883709db55316
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108009"
---
# <a name="how-to-enumerate-drawing-content-of-a-visual"></a><span data-ttu-id="5db97-102">Filtrar Enumerar el contenido de un dibujo de un objeto visual</span><span class="sxs-lookup"><span data-stu-id="5db97-102">How to: Enumerate Drawing Content of a Visual</span></span>
<span data-ttu-id="5db97-103">El <xref:System.Windows.Media.Drawing> objeto proporcionar un modelo de objetos para enumerar el contenido de un <xref:System.Windows.Media.Visual>.</span><span class="sxs-lookup"><span data-stu-id="5db97-103">The <xref:System.Windows.Media.Drawing> object provide an object model for enumerating the contents of a <xref:System.Windows.Media.Visual>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5db97-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5db97-104">Example</span></span>  
 <span data-ttu-id="5db97-105">En el ejemplo siguiente se usa el <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> método para recuperar el <xref:System.Windows.Media.DrawingGroup> valor de un <xref:System.Windows.Media.Visual> y enumerarlo.</span><span class="sxs-lookup"><span data-stu-id="5db97-105">The following example uses the <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> method to retrieve the <xref:System.Windows.Media.DrawingGroup> value of a <xref:System.Windows.Media.Visual> and enumerate it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5db97-106">Cuando se enumera el contenido del objeto visual, que se están recuperando <xref:System.Windows.Media.Drawing> objetos y no la representación subyacente de los datos de representación como una lista de instrucciones de gráficos vectoriales.</span><span class="sxs-lookup"><span data-stu-id="5db97-106">When you are enumerating the contents of the visual, you are retrieving <xref:System.Windows.Media.Drawing> objects, and not the underlying representation of the render data as a vector graphics instruction list.</span></span> <span data-ttu-id="5db97-107">Para más información, consulte [Información general sobre la representación de gráficos en WPF](wpf-graphics-rendering-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5db97-107">For more information, see [WPF Graphics Rendering Overview](wpf-graphics-rendering-overview.md).</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a><span data-ttu-id="5db97-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="5db97-108">See also</span></span>

- <xref:System.Windows.Media.Drawing>
- <xref:System.Windows.Media.DrawingGroup>
- <xref:System.Windows.Media.VisualTreeHelper>
- [<span data-ttu-id="5db97-109">Información general sobre objetos Drawing</span><span class="sxs-lookup"><span data-stu-id="5db97-109">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="5db97-110">Información general sobre la representación de gráficos en WPF</span><span class="sxs-lookup"><span data-stu-id="5db97-110">WPF Graphics Rendering Overview</span></span>](wpf-graphics-rendering-overview.md)
