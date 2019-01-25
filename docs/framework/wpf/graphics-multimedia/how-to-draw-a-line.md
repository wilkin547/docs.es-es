---
title: Procedimiento Dibujar una línea
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], lines
- graphics [WPF], lines
- lines [WPF], drawing
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
ms.openlocfilehash: 54152b6b68dd453c565afa2ffb23edfe8132a441
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629025"
---
# <a name="how-to-draw-a-line"></a><span data-ttu-id="fe712-102">Procedimiento Dibujar una línea</span><span class="sxs-lookup"><span data-stu-id="fe712-102">How to: Draw a Line</span></span>
<span data-ttu-id="fe712-103">En este ejemplo se muestra cómo dibujar líneas con el <xref:System.Windows.Shapes.Line> elemento.</span><span class="sxs-lookup"><span data-stu-id="fe712-103">This example shows you how to draw lines by using the <xref:System.Windows.Shapes.Line> element.</span></span>  
  
 <span data-ttu-id="fe712-104">Para dibujar una línea, cree un <xref:System.Windows.Shapes.Line> elemento.</span><span class="sxs-lookup"><span data-stu-id="fe712-104">To draw a line, create a <xref:System.Windows.Shapes.Line> element.</span></span> <span data-ttu-id="fe712-105">Use su <xref:System.Windows.Shapes.Line.X1%2A> y <xref:System.Windows.Shapes.Line.Y1%2A> propiedades para establecer su punto inicial; y utilice su <xref:System.Windows.Shapes.Line.X2%2A> y <xref:System.Windows.Shapes.Line.Y2%2A> propiedades para establecer su punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="fe712-105">Use its <xref:System.Windows.Shapes.Line.X1%2A> and <xref:System.Windows.Shapes.Line.Y1%2A> properties to set its start point; and use its <xref:System.Windows.Shapes.Line.X2%2A> and <xref:System.Windows.Shapes.Line.Y2%2A> properties to set its end point.</span></span> <span data-ttu-id="fe712-106">Por último, establezca su <xref:System.Windows.Shapes.Shape.Stroke%2A> y <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> porque una línea sin un trazo es invisible.</span><span class="sxs-lookup"><span data-stu-id="fe712-106">Finally, set its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> because a line without a stroke is invisible.</span></span>  
  
 <span data-ttu-id="fe712-107">Establecer el <xref:System.Windows.Shapes.Shape.Fill%2A> (elemento) para una línea no tiene ningún efecto, porque una línea no tiene interior.</span><span class="sxs-lookup"><span data-stu-id="fe712-107">Setting the <xref:System.Windows.Shapes.Shape.Fill%2A> element for a line has no effect, because a line has no interior.</span></span>  
  
 <span data-ttu-id="fe712-108">El ejemplo siguiente dibuja tres líneas dentro de un <xref:System.Windows.Controls.Canvas> elemento.</span><span class="sxs-lookup"><span data-stu-id="fe712-108">The following example draws three lines inside a <xref:System.Windows.Controls.Canvas> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe712-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fe712-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#LineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 <span data-ttu-id="fe712-110">Este ejemplo forma parte de un ejemplo más extenso; Para obtener un ejemplo completo, vea [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="fe712-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe712-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe712-111">See also</span></span>
- <xref:System.Windows.Shapes.Line>
- [<span data-ttu-id="fe712-112">Ejemplo de los elementos de forma</span><span class="sxs-lookup"><span data-stu-id="fe712-112">Shape Elements Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160037)
