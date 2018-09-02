---
title: 'Cómo: Dibujar una línea'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], lines
- graphics [WPF], lines
- lines [WPF], drawing
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
ms.openlocfilehash: bee343676175098493df347823a3bdbdf17b205f
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43398450"
---
# <a name="how-to-draw-a-line"></a><span data-ttu-id="0c143-102">Cómo: Dibujar una línea</span><span class="sxs-lookup"><span data-stu-id="0c143-102">How to: Draw a Line</span></span>
<span data-ttu-id="0c143-103">En este ejemplo se muestra cómo dibujar líneas con el <xref:System.Windows.Shapes.Line> elemento.</span><span class="sxs-lookup"><span data-stu-id="0c143-103">This example shows you how to draw lines by using the <xref:System.Windows.Shapes.Line> element.</span></span>  
  
 <span data-ttu-id="0c143-104">Para dibujar una línea, cree un <xref:System.Windows.Shapes.Line> elemento.</span><span class="sxs-lookup"><span data-stu-id="0c143-104">To draw a line, create a <xref:System.Windows.Shapes.Line> element.</span></span> <span data-ttu-id="0c143-105">Use su <xref:System.Windows.Shapes.Line.X1%2A> y <xref:System.Windows.Shapes.Line.Y1%2A> propiedades para establecer su punto inicial; y utilice su <xref:System.Windows.Shapes.Line.X2%2A> y <xref:System.Windows.Shapes.Line.Y2%2A> propiedades para establecer su punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="0c143-105">Use its <xref:System.Windows.Shapes.Line.X1%2A> and <xref:System.Windows.Shapes.Line.Y1%2A> properties to set its start point; and use its <xref:System.Windows.Shapes.Line.X2%2A> and <xref:System.Windows.Shapes.Line.Y2%2A> properties to set its end point.</span></span> <span data-ttu-id="0c143-106">Por último, establezca su <xref:System.Windows.Shapes.Shape.Stroke%2A> y <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> porque una línea sin un trazo es invisible.</span><span class="sxs-lookup"><span data-stu-id="0c143-106">Finally, set its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> because a line without a stroke is invisible.</span></span>  
  
 <span data-ttu-id="0c143-107">Establecer el <xref:System.Windows.Shapes.Shape.Fill%2A> (elemento) para una línea no tiene ningún efecto, porque una línea no tiene interior.</span><span class="sxs-lookup"><span data-stu-id="0c143-107">Setting the <xref:System.Windows.Shapes.Shape.Fill%2A> element for a line has no effect, because a line has no interior.</span></span>  
  
 <span data-ttu-id="0c143-108">El ejemplo siguiente dibuja tres líneas dentro de un <xref:System.Windows.Controls.Canvas> elemento.</span><span class="sxs-lookup"><span data-stu-id="0c143-108">The following example draws three lines inside a <xref:System.Windows.Controls.Canvas> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c143-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0c143-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#LineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 <span data-ttu-id="0c143-110">Este ejemplo forma parte de un ejemplo más extenso; Para obtener un ejemplo completo, vea [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="0c143-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c143-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c143-111">See Also</span></span>  
 <xref:System.Windows.Shapes.Line>  
 [<span data-ttu-id="0c143-112">Ejemplo de los elementos de forma</span><span class="sxs-lookup"><span data-stu-id="0c143-112">Shape Elements Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160037)
