---
title: 'Cómo: Enumerar el contenido de un dibujo de un objeto Visual'
ms.date: 03/30/2017
helpviewer_keywords:
- retrieving the DrawingGroup value of a Visual [WPF]
- enumerating the contents of a Visual [WPF]
ms.assetid: 2974ddb3-2997-4713-8fd2-e93d549c58a8
ms.openlocfilehash: 19c37ec7df3542eb46b182f4790059eb16fef90b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559407"
---
# <a name="how-to-enumerate-drawing-content-of-a-visual"></a><span data-ttu-id="c0c58-102">Cómo: Enumerar el contenido de un dibujo de un objeto Visual</span><span class="sxs-lookup"><span data-stu-id="c0c58-102">How to: Enumerate Drawing Content of a Visual</span></span>
<span data-ttu-id="c0c58-103">El <xref:System.Windows.Media.Drawing> objeto proporcionar un modelo de objetos para enumerar el contenido de un <xref:System.Windows.Media.Visual>.</span><span class="sxs-lookup"><span data-stu-id="c0c58-103">The <xref:System.Windows.Media.Drawing> object provide an object model for enumerating the contents of a <xref:System.Windows.Media.Visual>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0c58-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c0c58-104">Example</span></span>  
 <span data-ttu-id="c0c58-105">En el ejemplo siguiente se utiliza el <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> método para recuperar el <xref:System.Windows.Media.DrawingGroup> valor de un <xref:System.Windows.Media.Visual> y enumerar.</span><span class="sxs-lookup"><span data-stu-id="c0c58-105">The following example uses the <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> method to retrieve the <xref:System.Windows.Media.DrawingGroup> value of a <xref:System.Windows.Media.Visual> and enumerate it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0c58-106">Cuando se enumera el contenido del objeto visual, que se están recuperando <xref:System.Windows.Media.Drawing> objetos y no la representación subyacente de los datos de representación como una lista de instrucciones de gráficos vectoriales.</span><span class="sxs-lookup"><span data-stu-id="c0c58-106">When you are enumerating the contents of the visual, you are retrieving <xref:System.Windows.Media.Drawing> objects, and not the underlying representation of the render data as a vector graphics instruction list.</span></span> <span data-ttu-id="c0c58-107">Para más información, consulte [Información general sobre la representación de gráficos en WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c0c58-107">For more information, see [WPF Graphics Rendering Overview](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a><span data-ttu-id="c0c58-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0c58-108">See Also</span></span>  
 <xref:System.Windows.Media.Drawing>  
 <xref:System.Windows.Media.DrawingGroup>  
 <xref:System.Windows.Media.VisualTreeHelper>  
 [<span data-ttu-id="c0c58-109">Información general sobre objetos Drawing</span><span class="sxs-lookup"><span data-stu-id="c0c58-109">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="c0c58-110">Información general sobre la representación de gráficos en WPF</span><span class="sxs-lookup"><span data-stu-id="c0c58-110">WPF Graphics Rendering Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)
