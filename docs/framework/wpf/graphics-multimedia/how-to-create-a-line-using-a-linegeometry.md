---
title: 'Cómo: Crear una línea mediante la clase LineGeometry'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], lines
ms.assetid: 41231b22-1f74-4c26-a8e7-a55b29f8f6bd
ms.openlocfilehash: 8db33fc5c611dcbcae50c71ada1c6b6f9fd9bd29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560474"
---
# <a name="how-to-create-a-line-using-a-linegeometry"></a><span data-ttu-id="03e29-102">Cómo: Crear una línea mediante la clase LineGeometry</span><span class="sxs-lookup"><span data-stu-id="03e29-102">How to: Create a Line Using a LineGeometry</span></span>
<span data-ttu-id="03e29-103">Este ejemplo muestra cómo utilizar la <xref:System.Windows.Media.LineGeometry> clase para describir una línea.</span><span class="sxs-lookup"><span data-stu-id="03e29-103">This example shows how to use the <xref:System.Windows.Media.LineGeometry> class to describe a line.</span></span> <span data-ttu-id="03e29-104">Un <xref:System.Windows.Media.LineGeometry> se define por sus puntos inicial y final.</span><span class="sxs-lookup"><span data-stu-id="03e29-104">A <xref:System.Windows.Media.LineGeometry> is defined by its start and end points.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03e29-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="03e29-105">Example</span></span>  
 <span data-ttu-id="03e29-106">En el ejemplo siguiente se muestra cómo crear y representar una <xref:System.Windows.Media.LineGeometry>.</span><span class="sxs-lookup"><span data-stu-id="03e29-106">The following example shows how to create and render a <xref:System.Windows.Media.LineGeometry>.</span></span>  <span data-ttu-id="03e29-107">Un <xref:System.Windows.Shapes.Path> elemento se usa para representar la línea.</span><span class="sxs-lookup"><span data-stu-id="03e29-107">A <xref:System.Windows.Shapes.Path> element is used to render the line.</span></span>  <span data-ttu-id="03e29-108">Puesto que una línea no tiene área, el <xref:System.Windows.Shapes.Path> del objeto <xref:System.Windows.Shapes.Shape.Fill%2A> no se ha especificado; en su lugar el <xref:System.Windows.Shapes.Shape.Stroke%2A> y <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> se usan propiedades.</span><span class="sxs-lookup"><span data-stu-id="03e29-108">Since a line has no area, the <xref:System.Windows.Shapes.Path> object's <xref:System.Windows.Shapes.Shape.Fill%2A> is not specified; instead the <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties are used.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 <span data-ttu-id="03e29-109">![LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.gif "graphicsmm_line")</span><span class="sxs-lookup"><span data-stu-id="03e29-109">![A LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.gif "graphicsmm_line")</span></span>  
<span data-ttu-id="03e29-110">Objeto LineGeometry dibujado desde (10,20) hasta (100,130)</span><span class="sxs-lookup"><span data-stu-id="03e29-110">A LineGeometry drawn from (10,20) to (100,130)</span></span>  
  
 <span data-ttu-id="03e29-111">Otras clases de geometrías simples incluyen <xref:System.Windows.Media.LineGeometry> y <xref:System.Windows.Media.EllipseGeometry>.</span><span class="sxs-lookup"><span data-stu-id="03e29-111">Other simple geometry classes include <xref:System.Windows.Media.LineGeometry> and <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="03e29-112">Estos objetos Geometry, así como las más complejas, también pueden crearse mediante un <xref:System.Windows.Media.PathGeometry> o <xref:System.Windows.Media.StreamGeometry>.</span><span class="sxs-lookup"><span data-stu-id="03e29-112">These geometries, as well as more complex ones, can also be created using a <xref:System.Windows.Media.PathGeometry> or <xref:System.Windows.Media.StreamGeometry>.</span></span> <span data-ttu-id="03e29-113">Para obtener más información, consulte el [información general sobre geometría](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="03e29-113">For more information, see the [Geometry Overview](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03e29-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="03e29-114">See Also</span></span>  
 [<span data-ttu-id="03e29-115">Información general sobre geometría</span><span class="sxs-lookup"><span data-stu-id="03e29-115">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="03e29-116">Crear una forma compuesta</span><span class="sxs-lookup"><span data-stu-id="03e29-116">Create a Composite Shape</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)  
 [<span data-ttu-id="03e29-117">Crear una forma mediante una clase PathGeometry</span><span class="sxs-lookup"><span data-stu-id="03e29-117">Create a Shape by Using a PathGeometry</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
