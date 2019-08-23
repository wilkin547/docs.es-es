---
title: Procedimiento Enumerar el contenido de un dibujo de un objeto visual
ms.date: 03/30/2017
helpviewer_keywords:
- retrieving the DrawingGroup value of a Visual [WPF]
- enumerating the contents of a Visual [WPF]
ms.assetid: 2974ddb3-2997-4713-8fd2-e93d549c58a8
ms.openlocfilehash: 25aa0c3706005c1e16cedd7e06914db764545ebb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930069"
---
# <a name="how-to-enumerate-drawing-content-of-a-visual"></a><span data-ttu-id="277e4-102">Procedimiento Enumerar el contenido de un dibujo de un objeto visual</span><span class="sxs-lookup"><span data-stu-id="277e4-102">How to: Enumerate Drawing Content of a Visual</span></span>
<span data-ttu-id="277e4-103">El <xref:System.Windows.Media.Drawing> objeto proporciona un modelo de objetos para enumerar el contenido de <xref:System.Windows.Media.Visual>un objeto.</span><span class="sxs-lookup"><span data-stu-id="277e4-103">The <xref:System.Windows.Media.Drawing> object provide an object model for enumerating the contents of a <xref:System.Windows.Media.Visual>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="277e4-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="277e4-104">Example</span></span>  
 <span data-ttu-id="277e4-105">En el ejemplo siguiente se <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> usa el método para <xref:System.Windows.Media.DrawingGroup> recuperar el valor <xref:System.Windows.Media.Visual> de un y enumerarlo.</span><span class="sxs-lookup"><span data-stu-id="277e4-105">The following example uses the <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> method to retrieve the <xref:System.Windows.Media.DrawingGroup> value of a <xref:System.Windows.Media.Visual> and enumerate it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="277e4-106">Cuando se enumera el contenido del objeto visual, se recuperan <xref:System.Windows.Media.Drawing> los objetos y no la representación subyacente de los datos de representación como una lista de instrucciones de gráficos vectoriales.</span><span class="sxs-lookup"><span data-stu-id="277e4-106">When you are enumerating the contents of the visual, you are retrieving <xref:System.Windows.Media.Drawing> objects, and not the underlying representation of the render data as a vector graphics instruction list.</span></span> <span data-ttu-id="277e4-107">Para más información, consulte [Información general sobre la representación de gráficos en WPF](wpf-graphics-rendering-overview.md).</span><span class="sxs-lookup"><span data-stu-id="277e4-107">For more information, see [WPF Graphics Rendering Overview](wpf-graphics-rendering-overview.md).</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a><span data-ttu-id="277e4-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="277e4-108">See also</span></span>

- <xref:System.Windows.Media.Drawing>
- <xref:System.Windows.Media.DrawingGroup>
- <xref:System.Windows.Media.VisualTreeHelper>
- [<span data-ttu-id="277e4-109">Información general sobre objetos Drawing</span><span class="sxs-lookup"><span data-stu-id="277e4-109">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="277e4-110">Información general sobre la representación de gráficos en WPF</span><span class="sxs-lookup"><span data-stu-id="277e4-110">WPF Graphics Rendering Overview</span></span>](wpf-graphics-rendering-overview.md)
