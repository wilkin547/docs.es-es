---
title: Procedimiento Crear un objeto GeometryDrawing
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], renderable
- renderable shapes [WPF]
- graphics [WPF], GeometryDrawing class
- classes [WPF], GeometryDrawing
ms.assetid: 11d3c096-91ba-4d41-9bba-aeac0db70f97
ms.openlocfilehash: f5cdcfdb68ad8030bcbd6c689f45a8baddd000e1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904961"
---
# <a name="how-to-create-a-geometrydrawing"></a><span data-ttu-id="0168b-102">Procedimiento Crear un objeto GeometryDrawing</span><span class="sxs-lookup"><span data-stu-id="0168b-102">How to: Create a GeometryDrawing</span></span>
<span data-ttu-id="0168b-103">En este ejemplo se muestra cómo crear y mostrar un <xref:System.Windows.Media.GeometryDrawing>.</span><span class="sxs-lookup"><span data-stu-id="0168b-103">This example shows how to create and display a <xref:System.Windows.Media.GeometryDrawing>.</span></span> <span data-ttu-id="0168b-104">Un <xref:System.Windows.Media.GeometryDrawing> le permite crear de forma con un relleno y el contorno asociando un <xref:System.Windows.Media.Pen> y un <xref:System.Windows.Media.Brush> con un <xref:System.Windows.Media.Geometry>.</span><span class="sxs-lookup"><span data-stu-id="0168b-104">A <xref:System.Windows.Media.GeometryDrawing> enables you to create shape with a fill and an outline by associating a <xref:System.Windows.Media.Pen> and a <xref:System.Windows.Media.Brush> with a <xref:System.Windows.Media.Geometry>.</span></span> <span data-ttu-id="0168b-105">El <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> describe la estructura de la forma, el <xref:System.Windows.Media.GeometryDrawing.Brush%2A> describe el relleno de la forma y el <xref:System.Windows.Media.GeometryDrawing.Pen%2A> describe el contorno de la forma.</span><span class="sxs-lookup"><span data-stu-id="0168b-105">The <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> describes the shape's structure, the <xref:System.Windows.Media.GeometryDrawing.Brush%2A> describes the shape's fill, and the <xref:System.Windows.Media.GeometryDrawing.Pen%2A> describes the shape's outline.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0168b-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0168b-106">Example</span></span>  
 <span data-ttu-id="0168b-107">En el ejemplo siguiente se usa un <xref:System.Windows.Media.GeometryDrawing> para representar una forma.</span><span class="sxs-lookup"><span data-stu-id="0168b-107">The following example uses a <xref:System.Windows.Media.GeometryDrawing> to render a shape.</span></span> <span data-ttu-id="0168b-108">Se describe la forma mediante una <xref:System.Windows.Media.GeometryGroup> y dos <xref:System.Windows.Media.EllipseGeometry> objetos.</span><span class="sxs-lookup"><span data-stu-id="0168b-108">The shape is described by a <xref:System.Windows.Media.GeometryGroup> and two <xref:System.Windows.Media.EllipseGeometry> objects.</span></span> <span data-ttu-id="0168b-109">Se pinta el interior de la forma con un <xref:System.Windows.Media.LinearGradientBrush> y el contorno se dibuja con un <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>.</span><span class="sxs-lookup"><span data-stu-id="0168b-109">The shape's interior is painted with a <xref:System.Windows.Media.LinearGradientBrush> and its outline is drawn with a <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>.</span></span> <span data-ttu-id="0168b-110">El <xref:System.Windows.Media.GeometryDrawing> se muestra mediante un <xref:System.Windows.Media.ImageDrawing> y un <xref:System.Windows.Controls.Image> elemento.</span><span class="sxs-lookup"><span data-stu-id="0168b-110">The <xref:System.Windows.Media.GeometryDrawing> is displayed using an <xref:System.Windows.Media.ImageDrawing> and an <xref:System.Windows.Controls.Image> element.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexamplewholepage)]  
  
 <span data-ttu-id="0168b-111">La siguiente ilustración muestra resultante <xref:System.Windows.Media.GeometryDrawing>.</span><span class="sxs-lookup"><span data-stu-id="0168b-111">The following illustration shows the resulting <xref:System.Windows.Media.GeometryDrawing>.</span></span>  
  
 <span data-ttu-id="0168b-112">![GeometryDrawing de dos elipses](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span><span class="sxs-lookup"><span data-stu-id="0168b-112">![A GeometryDrawing of two ellipses](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span></span>  
  
 <span data-ttu-id="0168b-113">Para crear dibujos más complejos, puede combinar varios objetos de dibujo en un elemento compuesto de dibujo utilizando un <xref:System.Windows.Media.DrawingGroup>.</span><span class="sxs-lookup"><span data-stu-id="0168b-113">To create more complex drawings, you can combine multiple drawing objects into a single composite drawing using a <xref:System.Windows.Media.DrawingGroup>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0168b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="0168b-114">See also</span></span>

- <xref:System.Windows.Media.DrawingGroup>
- [<span data-ttu-id="0168b-115">Información general sobre objetos Drawing</span><span class="sxs-lookup"><span data-stu-id="0168b-115">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="0168b-116">Información general sobre geometría</span><span class="sxs-lookup"><span data-stu-id="0168b-116">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="0168b-117">Crear un dibujo compuesto</span><span class="sxs-lookup"><span data-stu-id="0168b-117">Create a Composite Drawing</span></span>](how-to-create-a-composite-drawing.md)
