---
title: 'Cómo: Dibujar una línea'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], lines
- graphics [WPF], lines
- lines [WPF], drawing
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
ms.openlocfilehash: a803c1be01086ca8911ef4cc33bd67697239e2c0
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452953"
---
# <a name="how-to-draw-a-line"></a><span data-ttu-id="8128f-102">Cómo: Dibujar una línea</span><span class="sxs-lookup"><span data-stu-id="8128f-102">How to: Draw a Line</span></span>
<span data-ttu-id="8128f-103">En este ejemplo se muestra cómo dibujar líneas mediante el elemento <xref:System.Windows.Shapes.Line>.</span><span class="sxs-lookup"><span data-stu-id="8128f-103">This example shows you how to draw lines by using the <xref:System.Windows.Shapes.Line> element.</span></span>  
  
 <span data-ttu-id="8128f-104">Para dibujar una línea, cree un elemento <xref:System.Windows.Shapes.Line>.</span><span class="sxs-lookup"><span data-stu-id="8128f-104">To draw a line, create a <xref:System.Windows.Shapes.Line> element.</span></span> <span data-ttu-id="8128f-105">Use sus propiedades <xref:System.Windows.Shapes.Line.X1%2A> y <xref:System.Windows.Shapes.Line.Y1%2A> para establecer su punto inicial; y usan sus propiedades <xref:System.Windows.Shapes.Line.X2%2A> y <xref:System.Windows.Shapes.Line.Y2%2A> para establecer su punto final.</span><span class="sxs-lookup"><span data-stu-id="8128f-105">Use its <xref:System.Windows.Shapes.Line.X1%2A> and <xref:System.Windows.Shapes.Line.Y1%2A> properties to set its start point; and use its <xref:System.Windows.Shapes.Line.X2%2A> and <xref:System.Windows.Shapes.Line.Y2%2A> properties to set its end point.</span></span> <span data-ttu-id="8128f-106">Por último, establezca su <xref:System.Windows.Shapes.Shape.Stroke%2A> y <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> porque una línea sin trazo es invisible.</span><span class="sxs-lookup"><span data-stu-id="8128f-106">Finally, set its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> because a line without a stroke is invisible.</span></span>  
  
 <span data-ttu-id="8128f-107">Establecer el elemento <xref:System.Windows.Shapes.Shape.Fill%2A> para una línea no tiene ningún efecto, ya que una línea no tiene ningún interior.</span><span class="sxs-lookup"><span data-stu-id="8128f-107">Setting the <xref:System.Windows.Shapes.Shape.Fill%2A> element for a line has no effect, because a line has no interior.</span></span>  
  
 <span data-ttu-id="8128f-108">En el ejemplo siguiente se dibujan tres líneas dentro de un elemento <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="8128f-108">The following example draws three lines inside a <xref:System.Windows.Controls.Canvas> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8128f-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8128f-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 <span data-ttu-id="8128f-110">Este ejemplo forma parte de un ejemplo más grande; para obtener el ejemplo completo, vea [ejemplo de elementos de forma](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span><span class="sxs-lookup"><span data-stu-id="8128f-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8128f-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8128f-111">See also</span></span>

- <xref:System.Windows.Shapes.Line>
- [<span data-ttu-id="8128f-112">Ejemplo de elementos de forma</span><span class="sxs-lookup"><span data-stu-id="8128f-112">Shape Elements Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
