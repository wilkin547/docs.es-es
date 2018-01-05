---
title: "Cómo: Dibujar texto en un elemento visual"
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
- typography [WPF], drawing text to visuals
- visuals [WPF], drawing text to
- text [WPF], drawing to visuals
- drawing [WPF], text to visuals
ms.assetid: fee4003c-e8a6-46ec-babd-2c7f4231a101
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 765d2102bc4466c2b194e03c9688212e04005ca2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-text-to-a-visual"></a><span data-ttu-id="7a60f-102">Cómo: Dibujar texto en un elemento visual</span><span class="sxs-lookup"><span data-stu-id="7a60f-102">How to: Draw Text to a Visual</span></span>
<span data-ttu-id="7a60f-103">En el ejemplo siguiente se muestra cómo dibujar texto en un <xref:System.Windows.Media.DrawingVisual> mediante un <xref:System.Windows.Media.DrawingContext> objeto.</span><span class="sxs-lookup"><span data-stu-id="7a60f-103">The following example shows how to draw text to a <xref:System.Windows.Media.DrawingVisual> using a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="7a60f-104">Se devuelve un contexto de dibujo mediante una llamada a la <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> método de una <xref:System.Windows.Media.DrawingVisual> objeto.</span><span class="sxs-lookup"><span data-stu-id="7a60f-104">A drawing context is returned by calling the <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> method of a <xref:System.Windows.Media.DrawingVisual> object.</span></span> <span data-ttu-id="7a60f-105">Puede dibujar gráficos y texto en un contexto de dibujo.</span><span class="sxs-lookup"><span data-stu-id="7a60f-105">You can draw graphics and text into a drawing context.</span></span>  
  
 <span data-ttu-id="7a60f-106">Para dibujar texto en el contexto de dibujo, utilice la <xref:System.Windows.Media.DrawingContext.DrawText%2A> método de una <xref:System.Windows.Media.DrawingContext> objeto.</span><span class="sxs-lookup"><span data-stu-id="7a60f-106">To draw text into the drawing context, use the <xref:System.Windows.Media.DrawingContext.DrawText%2A> method of a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="7a60f-107">Cuando haya terminado de dibujar contenido en el contexto de dibujo, llame a la <xref:System.Windows.Media.DrawingContext.Close%2A> método para cerrar el contexto de dibujo y conservar el contenido.</span><span class="sxs-lookup"><span data-stu-id="7a60f-107">When you are finished drawing content into the drawing context, call the <xref:System.Windows.Media.DrawingContext.Close%2A> method to close the drawing context and persist the content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a60f-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7a60f-108">Example</span></span>  
 [!code-csharp[DrawingVisualSample#110](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
>  <span data-ttu-id="7a60f-109">Para obtener el código completo del que se ha extraído el ejemplo de código anterior, vea [Ejemplo Hit Test Using DrawingVisuals](http://go.microsoft.com/fwlink/?LinkID=159994).</span><span class="sxs-lookup"><span data-stu-id="7a60f-109">For the complete code sample from which the preceding code example was extracted, see [Hit Test Using DrawingVisuals Sample](http://go.microsoft.com/fwlink/?LinkID=159994).</span></span>
