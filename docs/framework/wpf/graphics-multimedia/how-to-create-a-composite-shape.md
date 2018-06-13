---
title: 'Cómo: Crear una forma compuesta'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- shapes [WPF], composite
- composite shapes [WPF]
- graphics [WPF], composite shapes
ms.assetid: 8e5c7ef4-d7ed-4c43-afc9-ca01325c300b
ms.openlocfilehash: 6bb2a8a32938682af52343b971b840dbed16bcef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559979"
---
# <a name="how-to-create-a-composite-shape"></a><span data-ttu-id="5681b-102">Cómo: Crear una forma compuesta</span><span class="sxs-lookup"><span data-stu-id="5681b-102">How to: Create a Composite Shape</span></span>
<span data-ttu-id="5681b-103">Este ejemplo muestra cómo crear formas compuestas mediante <xref:System.Windows.Media.Geometry> objetos y mostrarlos mediante un <xref:System.Windows.Shapes.Path> elemento.</span><span class="sxs-lookup"><span data-stu-id="5681b-103">This example shows how to create composite shapes using <xref:System.Windows.Media.Geometry> objects and display them using a <xref:System.Windows.Shapes.Path> element.</span></span> <span data-ttu-id="5681b-104">En el ejemplo siguiente, un <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry>y un <xref:System.Windows.Media.RectangleGeometry> se usan con una <xref:System.Windows.Media.GeometryGroup> para crear una forma compuesta.</span><span class="sxs-lookup"><span data-stu-id="5681b-104">In the following example, a <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry>, and a <xref:System.Windows.Media.RectangleGeometry> are used with a <xref:System.Windows.Media.GeometryGroup> to create a composite shape.</span></span> <span data-ttu-id="5681b-105">A continuación, se dibujan las geometrías mediante un <xref:System.Windows.Shapes.Path> elemento.</span><span class="sxs-lookup"><span data-stu-id="5681b-105">The geometries are then drawn using a <xref:System.Windows.Shapes.Path> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5681b-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5681b-106">Example</span></span>  
 [!code-xaml[GeometrySample#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#19)]  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/CompositeShapeExample.cs#compositeshapecodeexampleinline1)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/compositeshapeexample.vb#compositeshapecodeexampleinline1)]  
  
 <span data-ttu-id="5681b-107">La siguiente ilustración muestra la forma creada en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="5681b-107">The following illustration shows the shape created in the previous example.</span></span>  
  
 <span data-ttu-id="5681b-108">![Una geometría compuesta creada mediante GeometryGroup](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")</span><span class="sxs-lookup"><span data-stu-id="5681b-108">![A composite geometry created using a GeometryGroup](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")</span></span>  
<span data-ttu-id="5681b-109">Geometría compuesta</span><span class="sxs-lookup"><span data-stu-id="5681b-109">Composite Geometry</span></span>  
  
 <span data-ttu-id="5681b-110">Formas más complejas, como polígonos y formas con segmentos de curvados, pueden crearse mediante un <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="5681b-110">More complex shapes, such as polygons and shapes with curved segments, may be created using a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="5681b-111">Para obtener un ejemplo que muestra cómo crear una forma mediante una <xref:System.Windows.Media.PathGeometry>, consulte [crear una forma mediante una clase PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md).</span><span class="sxs-lookup"><span data-stu-id="5681b-111">For an example showing how to create a shape using a <xref:System.Windows.Media.PathGeometry>, see [Create a Shape by Using a PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md).</span></span>  <span data-ttu-id="5681b-112">Aunque en este ejemplo se representa una forma en la pantalla mediante una <xref:System.Windows.Shapes.Path> elemento, <xref:System.Windows.Media.Geometry> objetos también pueden utilizarse para describir el contenido de un <xref:System.Windows.Media.GeometryDrawing> o <xref:System.Windows.Media.DrawingContext>.</span><span class="sxs-lookup"><span data-stu-id="5681b-112">Although this example renders a shape to the screen using a <xref:System.Windows.Shapes.Path> element, <xref:System.Windows.Media.Geometry> objects may also be used to describe the contents of a <xref:System.Windows.Media.GeometryDrawing> or a <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="5681b-113">Se puede usar también para el recorte y la prueba de posicionamiento.</span><span class="sxs-lookup"><span data-stu-id="5681b-113">They may also be used for clipping and hit-testing.</span></span>  
  
 <span data-ttu-id="5681b-114">Este ejemplo forma parte de un ejemplo más extenso; para obtener el ejemplo completo, vea [Ejemplo de geometrías](http://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="5681b-114">This example is part of larger sample; for the complete sample, see the [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).</span></span>
