---
title: Procedimiento Dibujar texto en un elemento visual
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], drawing text to visuals
- visuals [WPF], drawing text to
- text [WPF], drawing to visuals
- drawing [WPF], text to visuals
ms.assetid: fee4003c-e8a6-46ec-babd-2c7f4231a101
ms.openlocfilehash: bd760a06150098d0fff17dbdce95b55a0e5fe713
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963841"
---
# <a name="how-to-draw-text-to-a-visual"></a><span data-ttu-id="c3d5c-102">Procedimiento Dibujar texto en un elemento visual</span><span class="sxs-lookup"><span data-stu-id="c3d5c-102">How to: Draw Text to a Visual</span></span>
<span data-ttu-id="c3d5c-103">En el ejemplo siguiente se muestra cómo dibujar texto en <xref:System.Windows.Media.DrawingVisual> mediante un <xref:System.Windows.Media.DrawingContext> objeto.</span><span class="sxs-lookup"><span data-stu-id="c3d5c-103">The following example shows how to draw text to a <xref:System.Windows.Media.DrawingVisual> using a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="c3d5c-104">Un contexto de dibujo se devuelve mediante una <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> llamada al método <xref:System.Windows.Media.DrawingVisual> de un objeto.</span><span class="sxs-lookup"><span data-stu-id="c3d5c-104">A drawing context is returned by calling the <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> method of a <xref:System.Windows.Media.DrawingVisual> object.</span></span> <span data-ttu-id="c3d5c-105">Puede dibujar gráficos y texto en un contexto de dibujo.</span><span class="sxs-lookup"><span data-stu-id="c3d5c-105">You can draw graphics and text into a drawing context.</span></span>  
  
 <span data-ttu-id="c3d5c-106">Para dibujar texto en el contexto del dibujo, use <xref:System.Windows.Media.DrawingContext.DrawText%2A> el método de <xref:System.Windows.Media.DrawingContext> un objeto.</span><span class="sxs-lookup"><span data-stu-id="c3d5c-106">To draw text into the drawing context, use the <xref:System.Windows.Media.DrawingContext.DrawText%2A> method of a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="c3d5c-107">Cuando haya terminado de dibujar el contenido en el contexto del dibujo, <xref:System.Windows.Media.DrawingContext.Close%2A> llame al método para cerrar el contexto del dibujo y conservar el contenido.</span><span class="sxs-lookup"><span data-stu-id="c3d5c-107">When you are finished drawing content into the drawing context, call the <xref:System.Windows.Media.DrawingContext.Close%2A> method to close the drawing context and persist the content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3d5c-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c3d5c-108">Example</span></span>  
 [!code-csharp[DrawingVisualSample#110](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
> <span data-ttu-id="c3d5c-109">Para obtener el código completo del que se ha extraído el ejemplo de código anterior, vea [Ejemplo Hit Test Using DrawingVisuals](https://go.microsoft.com/fwlink/?LinkID=159994).</span><span class="sxs-lookup"><span data-stu-id="c3d5c-109">For the complete code sample from which the preceding code example was extracted, see [Hit Test Using DrawingVisuals Sample](https://go.microsoft.com/fwlink/?LinkID=159994).</span></span>
