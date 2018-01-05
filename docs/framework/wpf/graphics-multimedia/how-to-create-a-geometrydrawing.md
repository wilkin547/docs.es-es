---
title: "Cómo: Crear un objeto GeometryDrawing"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- shapes [WPF], renderable
- renderable shapes [WPF]
- graphics [WPF], GeometryDrawing class
- classes [WPF], GeometryDrawing
ms.assetid: 11d3c096-91ba-4d41-9bba-aeac0db70f97
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 31417a3eeee2c1e61674c43558c2799705797c35
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-geometrydrawing"></a><span data-ttu-id="3e674-102">Cómo: Crear un objeto GeometryDrawing</span><span class="sxs-lookup"><span data-stu-id="3e674-102">How to: Create a GeometryDrawing</span></span>
<span data-ttu-id="3e674-103">Este ejemplo muestra cómo crear y mostrar un <xref:System.Windows.Media.GeometryDrawing>.</span><span class="sxs-lookup"><span data-stu-id="3e674-103">This example shows how to create and display a <xref:System.Windows.Media.GeometryDrawing>.</span></span> <span data-ttu-id="3e674-104">A <xref:System.Windows.Media.GeometryDrawing> le permite crear forma con un relleno y un contorno asociando un <xref:System.Windows.Media.Pen> y un <xref:System.Windows.Media.Brush> con un <xref:System.Windows.Media.Geometry>.</span><span class="sxs-lookup"><span data-stu-id="3e674-104">A <xref:System.Windows.Media.GeometryDrawing> enables you to create shape with a fill and an outline by associating a <xref:System.Windows.Media.Pen> and a <xref:System.Windows.Media.Brush> with a <xref:System.Windows.Media.Geometry>.</span></span> <span data-ttu-id="3e674-105">El <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> describe la estructura de la forma, el <xref:System.Windows.Media.GeometryDrawing.Brush%2A> describe el relleno de la forma y el <xref:System.Windows.Media.GeometryDrawing.Pen%2A> describe el contorno de la forma.</span><span class="sxs-lookup"><span data-stu-id="3e674-105">The <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> describes the shape's structure, the <xref:System.Windows.Media.GeometryDrawing.Brush%2A> describes the shape's fill, and the <xref:System.Windows.Media.GeometryDrawing.Pen%2A> describes the shape's outline.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e674-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3e674-106">Example</span></span>  
 <span data-ttu-id="3e674-107">En el ejemplo siguiente se usa un <xref:System.Windows.Media.GeometryDrawing> para representar una forma.</span><span class="sxs-lookup"><span data-stu-id="3e674-107">The following example uses a <xref:System.Windows.Media.GeometryDrawing> to render a shape.</span></span> <span data-ttu-id="3e674-108">Describe la forma un <xref:System.Windows.Media.GeometryGroup> y dos <xref:System.Windows.Media.EllipseGeometry> objetos.</span><span class="sxs-lookup"><span data-stu-id="3e674-108">The shape is described by a <xref:System.Windows.Media.GeometryGroup> and two <xref:System.Windows.Media.EllipseGeometry> objects.</span></span> <span data-ttu-id="3e674-109">Se pinta el interior de la forma con un <xref:System.Windows.Media.LinearGradientBrush> y su contorno se dibuja con un <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>.</span><span class="sxs-lookup"><span data-stu-id="3e674-109">The shape's interior is painted with a <xref:System.Windows.Media.LinearGradientBrush> and its outline is drawn with a <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>.</span></span> <span data-ttu-id="3e674-110">El <xref:System.Windows.Media.GeometryDrawing> se muestra con un <xref:System.Windows.Media.ImageDrawing> y un <xref:System.Windows.Controls.Image> elemento.</span><span class="sxs-lookup"><span data-stu-id="3e674-110">The <xref:System.Windows.Media.GeometryDrawing> is displayed using an <xref:System.Windows.Media.ImageDrawing> and an <xref:System.Windows.Controls.Image> element.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexamplewholepage)]  
  
 <span data-ttu-id="3e674-111">La ilustración siguiente muestra los resultantes <xref:System.Windows.Media.GeometryDrawing>.</span><span class="sxs-lookup"><span data-stu-id="3e674-111">The following illustration shows the resulting <xref:System.Windows.Media.GeometryDrawing>.</span></span>  
  
 <span data-ttu-id="3e674-112">![GeometryDrawing de dos elipses](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span><span class="sxs-lookup"><span data-stu-id="3e674-112">![A GeometryDrawing of two ellipses](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span></span>  
  
 <span data-ttu-id="3e674-113">Para crear dibujos más complejos, puede combinar varios objetos de dibujo en un compuesto único dibujo utilizando un <xref:System.Windows.Media.DrawingGroup>.</span><span class="sxs-lookup"><span data-stu-id="3e674-113">To create more complex drawings, you can combine multiple drawing objects into a single composite drawing using a <xref:System.Windows.Media.DrawingGroup>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e674-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e674-114">See Also</span></span>  
 <xref:System.Windows.Media.DrawingGroup>  
 [<span data-ttu-id="3e674-115">Información general sobre objetos Drawing</span><span class="sxs-lookup"><span data-stu-id="3e674-115">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="3e674-116">Información general sobre geometría</span><span class="sxs-lookup"><span data-stu-id="3e674-116">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="3e674-117">Crear un dibujo compuesto</span><span class="sxs-lookup"><span data-stu-id="3e674-117">Create a Composite Drawing</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-drawing.md)
