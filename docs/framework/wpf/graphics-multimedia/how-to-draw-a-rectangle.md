---
title: "Cómo: Dibujar un rectángulo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drawing [WPF], rectangles
- graphics [WPF], rectangles
- rectangles [WPF], drawing
ms.assetid: beeb57ef-fab5-4446-a38a-1588f97b4c2f
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 58f29783e48aa7173010ffec6a65f9ac1d8a2b62
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-rectangle"></a><span data-ttu-id="5e495-102">Cómo: Dibujar un rectángulo</span><span class="sxs-lookup"><span data-stu-id="5e495-102">How to: Draw a Rectangle</span></span>
<span data-ttu-id="5e495-103">Este ejemplo muestra cómo dibujar un rectángulo con el <xref:System.Windows.Shapes.Rectangle> elemento.</span><span class="sxs-lookup"><span data-stu-id="5e495-103">This example shows how to draw a rectangle by using the <xref:System.Windows.Shapes.Rectangle> element.</span></span>  
  
 <span data-ttu-id="5e495-104">Para dibujar un rectángulo, cree un <xref:System.Windows.Shapes.Rectangle> elemento y especifique su <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="5e495-104">To draw a rectangle, create a <xref:System.Windows.Shapes.Rectangle> element and specify its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="5e495-105">Para pintar el interior del rectángulo, establezca su <xref:System.Windows.Shapes.Shape.Fill%2A>.</span><span class="sxs-lookup"><span data-stu-id="5e495-105">To paint the inside of the rectangle, set its <xref:System.Windows.Shapes.Shape.Fill%2A>.</span></span> <span data-ttu-id="5e495-106">Para conceder a un esquema de rectángulo, utilice su <xref:System.Windows.Shapes.Shape.Stroke%2A> y <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> propiedades.</span><span class="sxs-lookup"><span data-stu-id="5e495-106">To give the rectangle an outline, use its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties.</span></span>  
  
 <span data-ttu-id="5e495-107">Para dar el rectángulo esquinas redondeadas, especifique el valor opcional <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> y <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> propiedades.</span><span class="sxs-lookup"><span data-stu-id="5e495-107">To give the rectangle rounded corners, specify the optional <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties.</span></span> <span data-ttu-id="5e495-108">El <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> y <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> propiedades establecen los radios de ejes x y y de la elipse que se utiliza para redondear los vértices del rectángulo.</span><span class="sxs-lookup"><span data-stu-id="5e495-108">The <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties set the x-axis and y-axis radii of the ellipse that is used to round the corners of the rectangle.</span></span>  
  
 <span data-ttu-id="5e495-109">En el ejemplo siguiente, dos <xref:System.Windows.Shapes.Rectangle> se dibujan un <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="5e495-109">In the following example, two <xref:System.Windows.Shapes.Rectangle> elements are drawn in a <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="5e495-110">El primer rectángulo tiene una <xref:System.Windows.Media.Brushes.Blue%2A> interiores.</span><span class="sxs-lookup"><span data-stu-id="5e495-110">The first rectangle has a <xref:System.Windows.Media.Brushes.Blue%2A> interior.</span></span> <span data-ttu-id="5e495-111">El segundo rectángulo tiene una <xref:System.Windows.Media.Brushes.Blue%2A> interiores, un <xref:System.Windows.Media.Brushes.Black%2A> contorno y esquinas redondeadas.</span><span class="sxs-lookup"><span data-stu-id="5e495-111">The second rectangle has a <xref:System.Windows.Media.Brushes.Blue%2A> interior, a <xref:System.Windows.Media.Brushes.Black%2A> outline, and rounded corners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e495-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5e495-112">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#Rectangle1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/rectangleexample.xaml#rectangle1)]  
  
 <span data-ttu-id="5e495-113">Aunque en este ejemplo se usa un <xref:System.Windows.Controls.Canvas> para que contenga los rectángulos, puede usar elementos de rectángulo (y todos los demás elementos de formas) con cualquier <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> que admita contenido no son de texto.</span><span class="sxs-lookup"><span data-stu-id="5e495-113">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the rectangles, you can use rectangle elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span> <span data-ttu-id="5e495-114">De hecho, los rectángulos son particularmente útiles para proporcionar fondos para partes de <xref:System.Windows.Controls.Grid> paneles.</span><span class="sxs-lookup"><span data-stu-id="5e495-114">In fact, rectangles are particularly useful for providing backgrounds for portions of <xref:System.Windows.Controls.Grid> panels.</span></span> <span data-ttu-id="5e495-115">Para obtener un ejemplo, vea el [información general de la tabla](../../../../docs/framework/wpf/advanced/table-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5e495-115">For an example, see the [Table Overview](../../../../docs/framework/wpf/advanced/table-overview.md).</span></span>  
  
 <span data-ttu-id="5e495-116">Este ejemplo forma parte de un ejemplo más extenso; Para obtener un ejemplo completo, vea [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="5e495-116">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e495-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e495-117">See Also</span></span>  
 <xref:System.Windows.Shapes.Rectangle>  
 [<span data-ttu-id="5e495-118">Ejemplo de elementos de forma</span><span class="sxs-lookup"><span data-stu-id="5e495-118">Shape Elements Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160037)  
 [<span data-ttu-id="5e495-119">Información general sobre formas y dibujo básico en WPF</span><span class="sxs-lookup"><span data-stu-id="5e495-119">Shapes and Basic Drawing in WPF Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [<span data-ttu-id="5e495-120">Información general sobre tablas</span><span class="sxs-lookup"><span data-stu-id="5e495-120">Table Overview</span></span>](../../../../docs/framework/wpf/advanced/table-overview.md)
