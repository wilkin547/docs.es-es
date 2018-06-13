---
title: 'Cómo: Dibujar una forma cerrada utilizando el elemento Polygon'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], Polygon elements
- closed shapes [WPF], drawing with Polygon elements
- Polygon elements [WPF]
- drawing [WPF], closed shapes with Polygon elements
ms.assetid: 4b0ca008-29ce-48dd-8bc3-f3a20ffca6a6
ms.openlocfilehash: 4105139e159783cf0197f4e56c82001835077cbf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559467"
---
# <a name="how-to-draw-a-closed-shape-by-using-the-polygon-element"></a><span data-ttu-id="9aae0-102">Cómo: Dibujar una forma cerrada utilizando el elemento Polygon</span><span class="sxs-lookup"><span data-stu-id="9aae0-102">How to: Draw a Closed Shape by Using the Polygon Element</span></span>
<span data-ttu-id="9aae0-103">Este ejemplo muestra cómo dibujar una forma cerrada utilizando el <xref:System.Windows.Shapes.Polygon> elemento.</span><span class="sxs-lookup"><span data-stu-id="9aae0-103">This example shows how to draw a closed shape by using the <xref:System.Windows.Shapes.Polygon> element.</span></span> <span data-ttu-id="9aae0-104">Para dibujar una forma cerrada, cree un <xref:System.Windows.Shapes.Polygon> elemento y utilice su <xref:System.Windows.Shapes.Polygon.Points%2A> propiedad para especificar los vértices de una forma.</span><span class="sxs-lookup"><span data-stu-id="9aae0-104">To draw a closed shape, create a <xref:System.Windows.Shapes.Polygon> element and use its <xref:System.Windows.Shapes.Polygon.Points%2A> property to specify the vertices of a shape.</span></span> <span data-ttu-id="9aae0-105">Se dibuja automáticamente una línea que conecta los puntos primero y último.</span><span class="sxs-lookup"><span data-stu-id="9aae0-105">A line is automatically drawn that connects the first and last points.</span></span> <span data-ttu-id="9aae0-106">Por último, especifique un <xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>, o ambos.</span><span class="sxs-lookup"><span data-stu-id="9aae0-106">Finally, specify a <xref:System.Windows.Shapes.Shape.Fill%2A>, a <xref:System.Windows.Shapes.Shape.Stroke%2A>, or both.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9aae0-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9aae0-107">Example</span></span>  
 <span data-ttu-id="9aae0-108">En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], una sintaxis válida para los puntos es una lista delimitada por espacios de pares de coordenadas x e y separados por comas.</span><span class="sxs-lookup"><span data-stu-id="9aae0-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolygonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 <span data-ttu-id="9aae0-109">Aunque el ejemplo se usa un <xref:System.Windows.Controls.Canvas> para contener los polígonos, puede usar elementos de polígono (y todos los demás elementos de formas) con cualquier <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> que admita contenido no son de texto.</span><span class="sxs-lookup"><span data-stu-id="9aae0-109">Although the example uses a <xref:System.Windows.Controls.Canvas> to contain the polygons, you can use polygon elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="9aae0-110">Este ejemplo forma parte de un ejemplo más extenso; Para obtener un ejemplo completo, vea [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="9aae0-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span></span>
