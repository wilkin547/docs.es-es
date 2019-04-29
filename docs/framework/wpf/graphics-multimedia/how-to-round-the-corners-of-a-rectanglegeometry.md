---
title: Procedimiento Redondear las esquinas de un RectangleGeometry
ms.date: 03/30/2017
helpviewer_keywords:
- corners [WPF], rounding
- RectangleGeometry class [WPF], rounding corners
- graphics [WPF], rounding corners of RectangleGeometry objects [WPF]
- rounding corners of RectangleGeometry objects [WPF]
ms.assetid: 926644bc-1357-4c0b-ac81-694bd090ae87
ms.openlocfilehash: eb2f173bedb903e12b2795264c684524cfa09825
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651406"
---
# <a name="how-to-round-the-corners-of-a-rectanglegeometry"></a><span data-ttu-id="b291b-102">Procedimiento Redondear las esquinas de un RectangleGeometry</span><span class="sxs-lookup"><span data-stu-id="b291b-102">How to: Round the Corners of a RectangleGeometry</span></span>
<span data-ttu-id="b291b-103">Para redondear los vértices de un <xref:System.Windows.Media.RectangleGeometry>, establezca su <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> y <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> propiedades en un valor mayor que cero.</span><span class="sxs-lookup"><span data-stu-id="b291b-103">To round the corners of a <xref:System.Windows.Media.RectangleGeometry>, set its <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> and <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> properties to a value greater than zero.</span></span> <span data-ttu-id="b291b-104">Cuanto mayor sea el valores, más redondeadas serán las esquinas del rectángulo.</span><span class="sxs-lookup"><span data-stu-id="b291b-104">The larger the values, the rounder the rectangle's corners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b291b-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b291b-105">Example</span></span>  
 <span data-ttu-id="b291b-106">El ejemplo siguiente se muestra varias <xref:System.Windows.Media.RectangleGeometry> objetos con diferentes <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> y <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> configuración.</span><span class="sxs-lookup"><span data-stu-id="b291b-106">The following example shows several <xref:System.Windows.Media.RectangleGeometry> objects with different <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> and <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> settings.</span></span> <span data-ttu-id="b291b-107">El <xref:System.Windows.Media.RectangleGeometry> objetos se muestran mediante <xref:System.Windows.Shapes.Path> elementos.</span><span class="sxs-lookup"><span data-stu-id="b291b-107">The <xref:System.Windows.Media.RectangleGeometry> objects are displayed using <xref:System.Windows.Shapes.Path> elements.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRoundedRectangleGeometryExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/RectangleGeometryRoundedCornerExample.xaml#graphicsmmroundedrectanglegeometryexamplewholepage)]  
  
 <span data-ttu-id="b291b-108">![Rectángulos con diferentes RadiusX&#47;configuración RadiusY](./media/graphicsmm-rounded.png "graphicsmm_rounded")</span><span class="sxs-lookup"><span data-stu-id="b291b-108">![Rectangles with different RadiusX&#47;RadiusY settings](./media/graphicsmm-rounded.png "graphicsmm_rounded")</span></span>  
<span data-ttu-id="b291b-109">Rectángulos con esquinas redondeadas</span><span class="sxs-lookup"><span data-stu-id="b291b-109">Rectangles with Rounded Corners</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b291b-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="b291b-110">See also</span></span>

- [<span data-ttu-id="b291b-111">Información general sobre geometría</span><span class="sxs-lookup"><span data-stu-id="b291b-111">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="b291b-112">Crear una forma compuesta</span><span class="sxs-lookup"><span data-stu-id="b291b-112">Create a Composite Shape</span></span>](how-to-create-a-composite-shape.md)
- [<span data-ttu-id="b291b-113">Crear una forma mediante una clase PathGeometry</span><span class="sxs-lookup"><span data-stu-id="b291b-113">Create a Shape by Using a PathGeometry</span></span>](how-to-create-a-shape-by-using-a-pathgeometry.md)
