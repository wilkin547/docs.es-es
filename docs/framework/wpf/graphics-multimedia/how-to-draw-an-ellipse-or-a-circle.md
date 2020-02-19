---
title: 'Cómo: Dibujar una elipse o un círculo'
ms.date: 03/30/2017
helpviewer_keywords:
- ellipses [WPF], drawing
- circles [WPF], drawing
- drawing circles [WPF]
- drawing ellipses [WPF]
- graphics [WPF], drawing circles
- graphics [WPF], drawing ellipses
ms.assetid: 99763b8c-bfc8-44be-8231-8a70daf5481a
ms.openlocfilehash: 5f17615da4907cba6e25b68f2f934602c2f8a390
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452927"
---
# <a name="how-to-draw-an-ellipse-or-a-circle"></a><span data-ttu-id="f92b2-102">Cómo: Dibujar una elipse o un círculo</span><span class="sxs-lookup"><span data-stu-id="f92b2-102">How to: Draw an Ellipse or a Circle</span></span>
<span data-ttu-id="f92b2-103">En este ejemplo se muestra cómo dibujar elipses y círculos mediante el elemento <xref:System.Windows.Shapes.Ellipse>.</span><span class="sxs-lookup"><span data-stu-id="f92b2-103">This example shows how to draw ellipses and circles by using the <xref:System.Windows.Shapes.Ellipse> element.</span></span> <span data-ttu-id="f92b2-104">Para dibujar una elipse, cree un elemento <xref:System.Windows.Shapes.Ellipse> y especifique su <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="f92b2-104">To draw an ellipse, create an <xref:System.Windows.Shapes.Ellipse> element and specify its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="f92b2-105">Utilice su propiedad <xref:System.Windows.Shapes.Shape.Fill%2A> para especificar el <xref:System.Windows.Media.Brush> que se utiliza para pintar el interior de la elipse.</span><span class="sxs-lookup"><span data-stu-id="f92b2-105">Use its <xref:System.Windows.Shapes.Shape.Fill%2A> property to specify the <xref:System.Windows.Media.Brush> that is used to paint the interior of the ellipse.</span></span> <span data-ttu-id="f92b2-106">Utilice su propiedad <xref:System.Windows.Shapes.Shape.Stroke%2A> para especificar el <xref:System.Windows.Media.Brush> que se usa para pintar el contorno de la elipse.</span><span class="sxs-lookup"><span data-stu-id="f92b2-106">Use its <xref:System.Windows.Shapes.Shape.Stroke%2A> property to specify the <xref:System.Windows.Media.Brush> that is used to paint the outline of the ellipse.</span></span> <span data-ttu-id="f92b2-107">La propiedad <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> especifica el grosor del contorno de la elipse.</span><span class="sxs-lookup"><span data-stu-id="f92b2-107">The <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> property specifies the thickness of the ellipse outline.</span></span>  
  
 <span data-ttu-id="f92b2-108">Para dibujar un círculo, convierta el <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> del elemento <xref:System.Windows.Shapes.Ellipse> igual entre sí.</span><span class="sxs-lookup"><span data-stu-id="f92b2-108">To draw a circle, make the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> of the <xref:System.Windows.Shapes.Ellipse> element equal to each other.</span></span>  
  
 <span data-ttu-id="f92b2-109">En el ejemplo siguiente se dibujan cuatro elementos <xref:System.Windows.Shapes.Ellipse> dentro de un <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="f92b2-109">The following example draws four <xref:System.Windows.Shapes.Ellipse> elements within a <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f92b2-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f92b2-110">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 <span data-ttu-id="f92b2-111">Aunque en este ejemplo se usa una <xref:System.Windows.Controls.Canvas> para contener los puntos suspensivos, se pueden usar elementos Ellipse (y todos los demás elementos Shape) con cualquier <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> que admita contenido que no sea de texto.</span><span class="sxs-lookup"><span data-stu-id="f92b2-111">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the ellipses, you can use ellipse elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="f92b2-112">Este ejemplo forma parte de un ejemplo más grande; para obtener el ejemplo completo, vea [ejemplo de elementos de forma](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span><span class="sxs-lookup"><span data-stu-id="f92b2-112">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f92b2-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f92b2-113">See also</span></span>

- <xref:System.Windows.Shapes.Ellipse>
- <xref:System.Windows.Shapes.Shape>
- [<span data-ttu-id="f92b2-114">Ejemplo de elementos de forma</span><span class="sxs-lookup"><span data-stu-id="f92b2-114">Shape Elements Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
