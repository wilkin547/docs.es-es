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
ms.openlocfilehash: 69620d81eb77eb76f21f099b30017b142d818457
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559371"
---
# <a name="how-to-draw-an-ellipse-or-a-circle"></a><span data-ttu-id="90e72-102">Cómo: Dibujar una elipse o un círculo</span><span class="sxs-lookup"><span data-stu-id="90e72-102">How to: Draw an Ellipse or a Circle</span></span>
<span data-ttu-id="90e72-103">Este ejemplo muestra cómo dibujar elipses y círculos utilizando el <xref:System.Windows.Shapes.Ellipse> elemento.</span><span class="sxs-lookup"><span data-stu-id="90e72-103">This example shows how to draw ellipses and circles by using the <xref:System.Windows.Shapes.Ellipse> element.</span></span> <span data-ttu-id="90e72-104">Para dibujar una elipse, cree un <xref:System.Windows.Shapes.Ellipse> elemento y especifique su <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="90e72-104">To draw an ellipse, create an <xref:System.Windows.Shapes.Ellipse> element and specify its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="90e72-105">Use su <xref:System.Windows.Shapes.Shape.Fill%2A> propiedad para especificar el <xref:System.Windows.Media.Brush> que se usa para pintar el interior de la elipse.</span><span class="sxs-lookup"><span data-stu-id="90e72-105">Use its <xref:System.Windows.Shapes.Shape.Fill%2A> property to specify the <xref:System.Windows.Media.Brush> that is used to paint the interior of the ellipse.</span></span> <span data-ttu-id="90e72-106">Use su <xref:System.Windows.Shapes.Shape.Stroke%2A> propiedad para especificar el <xref:System.Windows.Media.Brush> que se usa para pintar el esquema de la elipse.</span><span class="sxs-lookup"><span data-stu-id="90e72-106">Use its <xref:System.Windows.Shapes.Shape.Stroke%2A> property to specify the <xref:System.Windows.Media.Brush> that is used to paint the outline of the ellipse.</span></span> <span data-ttu-id="90e72-107">El <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> propiedad especifica el grosor del contorno de elipse.</span><span class="sxs-lookup"><span data-stu-id="90e72-107">The <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> property specifies the thickness of the ellipse outline.</span></span>  
  
 <span data-ttu-id="90e72-108">Para dibujar un círculo, realizar la <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> de la <xref:System.Windows.Shapes.Ellipse> elementos iguales entre sí.</span><span class="sxs-lookup"><span data-stu-id="90e72-108">To draw a circle, make the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> of the <xref:System.Windows.Shapes.Ellipse> element equal to each other.</span></span>  
  
 <span data-ttu-id="90e72-109">En el ejemplo siguiente se dibuja cuatro <xref:System.Windows.Shapes.Ellipse> elementos dentro de un <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="90e72-109">The following example draws four <xref:System.Windows.Shapes.Ellipse> elements within a <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90e72-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="90e72-110">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 <span data-ttu-id="90e72-111">Aunque en este ejemplo se usa un <xref:System.Windows.Controls.Canvas> para que contenga los puntos suspensivos, puede usar elementos de elipse (y todos los demás elementos de formas) con cualquier <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> que admita contenido no son de texto.</span><span class="sxs-lookup"><span data-stu-id="90e72-111">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the ellipses, you can use ellipse elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="90e72-112">Este ejemplo forma parte de un ejemplo más extenso; Para obtener un ejemplo completo, vea [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="90e72-112">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90e72-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="90e72-113">See Also</span></span>  
 <xref:System.Windows.Shapes.Ellipse>  
 <xref:System.Windows.Shapes.Shape>  
 [<span data-ttu-id="90e72-114">Ejemplo de elementos de forma</span><span class="sxs-lookup"><span data-stu-id="90e72-114">Shape Elements Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160037)
