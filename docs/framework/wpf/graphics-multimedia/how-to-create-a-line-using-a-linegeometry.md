---
title: "Cómo: Crear una línea mediante la clase LineGeometry"
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
helpviewer_keywords: graphics [WPF], lines
ms.assetid: 41231b22-1f74-4c26-a8e7-a55b29f8f6bd
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: acb2c3db2027f8a4e9594212d1f5af9ea1c8a43b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-line-using-a-linegeometry"></a><span data-ttu-id="d82bc-102">Cómo: Crear una línea mediante la clase LineGeometry</span><span class="sxs-lookup"><span data-stu-id="d82bc-102">How to: Create a Line Using a LineGeometry</span></span>
<span data-ttu-id="d82bc-103">Este ejemplo muestra cómo utilizar la <xref:System.Windows.Media.LineGeometry> clase para describir una línea.</span><span class="sxs-lookup"><span data-stu-id="d82bc-103">This example shows how to use the <xref:System.Windows.Media.LineGeometry> class to describe a line.</span></span> <span data-ttu-id="d82bc-104">Un <xref:System.Windows.Media.LineGeometry> se define por sus puntos inicial y final.</span><span class="sxs-lookup"><span data-stu-id="d82bc-104">A <xref:System.Windows.Media.LineGeometry> is defined by its start and end points.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d82bc-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d82bc-105">Example</span></span>  
 <span data-ttu-id="d82bc-106">En el ejemplo siguiente se muestra cómo crear y representar una <xref:System.Windows.Media.LineGeometry>.</span><span class="sxs-lookup"><span data-stu-id="d82bc-106">The following example shows how to create and render a <xref:System.Windows.Media.LineGeometry>.</span></span>  <span data-ttu-id="d82bc-107">Un <xref:System.Windows.Shapes.Path> elemento se usa para representar la línea.</span><span class="sxs-lookup"><span data-stu-id="d82bc-107">A <xref:System.Windows.Shapes.Path> element is used to render the line.</span></span>  <span data-ttu-id="d82bc-108">Puesto que una línea no tiene área, el <xref:System.Windows.Shapes.Path> del objeto <xref:System.Windows.Shapes.Shape.Fill%2A> no se ha especificado; en su lugar el <xref:System.Windows.Shapes.Shape.Stroke%2A> y <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> se usan propiedades.</span><span class="sxs-lookup"><span data-stu-id="d82bc-108">Since a line has no area, the <xref:System.Windows.Shapes.Path> object's <xref:System.Windows.Shapes.Shape.Fill%2A> is not specified; instead the <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties are used.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 <span data-ttu-id="d82bc-109">![LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.gif "graphicsmm_line")</span><span class="sxs-lookup"><span data-stu-id="d82bc-109">![A LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.gif "graphicsmm_line")</span></span>  
<span data-ttu-id="d82bc-110">Objeto LineGeometry dibujado desde (10,20) hasta (100,130)</span><span class="sxs-lookup"><span data-stu-id="d82bc-110">A LineGeometry drawn from (10,20) to (100,130)</span></span>  
  
 <span data-ttu-id="d82bc-111">Otras clases de geometrías simples incluyen <xref:System.Windows.Media.LineGeometry> y <xref:System.Windows.Media.EllipseGeometry>.</span><span class="sxs-lookup"><span data-stu-id="d82bc-111">Other simple geometry classes include <xref:System.Windows.Media.LineGeometry> and <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="d82bc-112">Estos objetos Geometry, así como las más complejas, también pueden crearse mediante un <xref:System.Windows.Media.PathGeometry> o <xref:System.Windows.Media.StreamGeometry>.</span><span class="sxs-lookup"><span data-stu-id="d82bc-112">These geometries, as well as more complex ones, can also be created using a <xref:System.Windows.Media.PathGeometry> or <xref:System.Windows.Media.StreamGeometry>.</span></span> <span data-ttu-id="d82bc-113">Para obtener más información, consulte el [información general sobre geometría](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d82bc-113">For more information, see the [Geometry Overview](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d82bc-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="d82bc-114">See Also</span></span>  
 [<span data-ttu-id="d82bc-115">Información general sobre geometría</span><span class="sxs-lookup"><span data-stu-id="d82bc-115">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="d82bc-116">Crear una forma compuesta</span><span class="sxs-lookup"><span data-stu-id="d82bc-116">Create a Composite Shape</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)  
 [<span data-ttu-id="d82bc-117">Crear una forma mediante una clase PathGeometry</span><span class="sxs-lookup"><span data-stu-id="d82bc-117">Create a Shape by Using a PathGeometry</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
