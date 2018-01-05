---
title: "Cómo: Definir un rectángulo usando una clase RectangleGeometry"
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
- graphics [WPF], rectangles
- rectangles [WPF], creating with RectangleGeometry class
ms.assetid: e40b8a8e-54b8-416b-a9f2-be6dca9fdf0b
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3a8254bd60da379d006bc50ab3a935cd83b83d0a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-a-rectangle-using-a-rectanglegeometry"></a><span data-ttu-id="0ac6b-102">Cómo: Definir un rectángulo usando una clase RectangleGeometry</span><span class="sxs-lookup"><span data-stu-id="0ac6b-102">How to: Define a Rectangle Using a RectangleGeometry</span></span>
<span data-ttu-id="0ac6b-103">En este ejemplo se describe cómo utilizar el <xref:System.Windows.Media.RectangleGeometry> clase para describir un rectángulo.</span><span class="sxs-lookup"><span data-stu-id="0ac6b-103">This example describes how to use the <xref:System.Windows.Media.RectangleGeometry> class to describe a rectangle.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ac6b-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0ac6b-104">Example</span></span>  
 <span data-ttu-id="0ac6b-105">En el ejemplo siguiente se muestra cómo crear y representar una <xref:System.Windows.Media.RectangleGeometry>.</span><span class="sxs-lookup"><span data-stu-id="0ac6b-105">The following example shows how to create and render a <xref:System.Windows.Media.RectangleGeometry>.</span></span>  <span data-ttu-id="0ac6b-106">La posición relativa y las dimensiones del rectángulo se definen mediante un <xref:System.Windows.Rect> estructura.</span><span class="sxs-lookup"><span data-stu-id="0ac6b-106">The relative position and the dimensions of the rectangle are defined by a <xref:System.Windows.Rect> structure.</span></span> <span data-ttu-id="0ac6b-107">La posición relativa es `50,50` y el alto y el ancho son ambos `25` crear un cuadrado.</span><span class="sxs-lookup"><span data-stu-id="0ac6b-107">The relative position is `50,50` and the height and the width are both `25` creating a square.</span></span> <span data-ttu-id="0ac6b-108">Se pinta el interior del rectángulo con un <xref:System.Windows.Media.Brushes.LemonChiffon%2A> pincel y su contorno se pinta con un <xref:System.Windows.Media.Brushes.Black%2A> trazo con un grosor de `1`.</span><span class="sxs-lookup"><span data-stu-id="0ac6b-108">The rectangle's interior is painted with a <xref:System.Windows.Media.Brushes.LemonChiffon%2A> brush and its outline is painted with a <xref:System.Windows.Media.Brushes.Black%2A> stroke with a thickness of `1`.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 <span data-ttu-id="0ac6b-109">![RectangleGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.gif "graphicsmm_rectangle")</span><span class="sxs-lookup"><span data-stu-id="0ac6b-109">![A RectangleGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.gif "graphicsmm_rectangle")</span></span>  
<span data-ttu-id="0ac6b-110">RectangleGeometry</span><span class="sxs-lookup"><span data-stu-id="0ac6b-110">RectangleGeometry</span></span>  
  
 <span data-ttu-id="0ac6b-111">Aunque este ejemplo usa un <xref:System.Windows.Shapes.Path> elemento que se va a representar el <xref:System.Windows.Media.RectangleGeometry>, hay muchas otras formas de usar <xref:System.Windows.Media.RectangleGeometry> objetos.</span><span class="sxs-lookup"><span data-stu-id="0ac6b-111">Although this example used a <xref:System.Windows.Shapes.Path> element to render the <xref:System.Windows.Media.RectangleGeometry>, there are many other ways to use <xref:System.Windows.Media.RectangleGeometry> objects.</span></span> <span data-ttu-id="0ac6b-112">Por ejemplo, un <xref:System.Windows.Media.RectangleGeometry> puede utilizarse para especificar el <xref:System.Windows.UIElement.Clip%2A> de un <xref:System.Windows.UIElement> o <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> de un <xref:System.Windows.Media.GeometryDrawing>.</span><span class="sxs-lookup"><span data-stu-id="0ac6b-112">For example, a <xref:System.Windows.Media.RectangleGeometry> can be used to specify the <xref:System.Windows.UIElement.Clip%2A> of a <xref:System.Windows.UIElement> or the <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> of a <xref:System.Windows.Media.GeometryDrawing>.</span></span>  
  
 <span data-ttu-id="0ac6b-113">Otras clases de geometrías simples incluyen <xref:System.Windows.Media.LineGeometry> y <xref:System.Windows.Media.EllipseGeometry>.</span><span class="sxs-lookup"><span data-stu-id="0ac6b-113">Other simple geometry classes include <xref:System.Windows.Media.LineGeometry> and <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="0ac6b-114">Estos objetos Geometry, así como las más complejas, también pueden crearse mediante un <xref:System.Windows.Media.PathGeometry> o <xref:System.Windows.Media.StreamGeometry>.</span><span class="sxs-lookup"><span data-stu-id="0ac6b-114">These geometries, as well as more complex ones, can also be created using a <xref:System.Windows.Media.PathGeometry> or <xref:System.Windows.Media.StreamGeometry>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ac6b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ac6b-115">See Also</span></span>  
 [<span data-ttu-id="0ac6b-116">Información general sobre geometría</span><span class="sxs-lookup"><span data-stu-id="0ac6b-116">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="0ac6b-117">Crear una forma compuesta</span><span class="sxs-lookup"><span data-stu-id="0ac6b-117">Create a Composite Shape</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)  
 [<span data-ttu-id="0ac6b-118">Crear una forma mediante una clase PathGeometry</span><span class="sxs-lookup"><span data-stu-id="0ac6b-118">Create a Shape by Using a PathGeometry</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
