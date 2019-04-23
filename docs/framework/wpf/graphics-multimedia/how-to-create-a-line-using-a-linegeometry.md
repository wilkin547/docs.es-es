---
title: Procedimiento Crear una línea mediante la clase LineGeometry
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], lines
ms.assetid: 41231b22-1f74-4c26-a8e7-a55b29f8f6bd
ms.openlocfilehash: f8c334a54f78aec7af91064a447fd18f23dcfbdc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59123063"
---
# <a name="how-to-create-a-line-using-a-linegeometry"></a><span data-ttu-id="b3fab-102">Procedimiento Crear una línea mediante la clase LineGeometry</span><span class="sxs-lookup"><span data-stu-id="b3fab-102">How to: Create a Line Using a LineGeometry</span></span>
<span data-ttu-id="b3fab-103">En este ejemplo se muestra cómo usar el <xref:System.Windows.Media.LineGeometry> clase para describir una línea.</span><span class="sxs-lookup"><span data-stu-id="b3fab-103">This example shows how to use the <xref:System.Windows.Media.LineGeometry> class to describe a line.</span></span> <span data-ttu-id="b3fab-104">Un <xref:System.Windows.Media.LineGeometry> se define por sus puntos inicial y final.</span><span class="sxs-lookup"><span data-stu-id="b3fab-104">A <xref:System.Windows.Media.LineGeometry> is defined by its start and end points.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3fab-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b3fab-105">Example</span></span>  
 <span data-ttu-id="b3fab-106">El ejemplo siguiente muestra cómo crear y representar un <xref:System.Windows.Media.LineGeometry>.</span><span class="sxs-lookup"><span data-stu-id="b3fab-106">The following example shows how to create and render a <xref:System.Windows.Media.LineGeometry>.</span></span>  <span data-ttu-id="b3fab-107">Un <xref:System.Windows.Shapes.Path> elemento se usa para representar la línea.</span><span class="sxs-lookup"><span data-stu-id="b3fab-107">A <xref:System.Windows.Shapes.Path> element is used to render the line.</span></span>  <span data-ttu-id="b3fab-108">Dado que una línea no tiene ninguna área, el <xref:System.Windows.Shapes.Path> del objeto <xref:System.Windows.Shapes.Shape.Fill%2A> no se ha especificado; en su lugar el <xref:System.Windows.Shapes.Shape.Stroke%2A> y <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> se usan las propiedades.</span><span class="sxs-lookup"><span data-stu-id="b3fab-108">Since a line has no area, the <xref:System.Windows.Shapes.Path> object's <xref:System.Windows.Shapes.Shape.Fill%2A> is not specified; instead the <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties are used.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 <span data-ttu-id="b3fab-109">![LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")</span><span class="sxs-lookup"><span data-stu-id="b3fab-109">![A LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")</span></span>  
<span data-ttu-id="b3fab-110">Objeto LineGeometry dibujado desde (10,20) hasta (100,130)</span><span class="sxs-lookup"><span data-stu-id="b3fab-110">A LineGeometry drawn from (10,20) to (100,130)</span></span>  
  
 <span data-ttu-id="b3fab-111">Otras clases de geometría simple incluyen <xref:System.Windows.Media.LineGeometry> y <xref:System.Windows.Media.EllipseGeometry>.</span><span class="sxs-lookup"><span data-stu-id="b3fab-111">Other simple geometry classes include <xref:System.Windows.Media.LineGeometry> and <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="b3fab-112">Estas geometrías, así como otras más complejas, también se pueden crear mediante un <xref:System.Windows.Media.PathGeometry> o <xref:System.Windows.Media.StreamGeometry>.</span><span class="sxs-lookup"><span data-stu-id="b3fab-112">These geometries, as well as more complex ones, can also be created using a <xref:System.Windows.Media.PathGeometry> or <xref:System.Windows.Media.StreamGeometry>.</span></span> <span data-ttu-id="b3fab-113">Para obtener más información, consulte el [información general sobre geometría](geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b3fab-113">For more information, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3fab-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3fab-114">See also</span></span>

- [<span data-ttu-id="b3fab-115">Información general sobre geometría</span><span class="sxs-lookup"><span data-stu-id="b3fab-115">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="b3fab-116">Crear una forma compuesta</span><span class="sxs-lookup"><span data-stu-id="b3fab-116">Create a Composite Shape</span></span>](how-to-create-a-composite-shape.md)
- [<span data-ttu-id="b3fab-117">Crear una forma mediante una clase PathGeometry</span><span class="sxs-lookup"><span data-stu-id="b3fab-117">Create a Shape by Using a PathGeometry</span></span>](how-to-create-a-shape-by-using-a-pathgeometry.md)
