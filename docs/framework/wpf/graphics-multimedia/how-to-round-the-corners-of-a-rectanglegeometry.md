---
title: Filtrar Redondear las esquinas de un RectangleGeometry
ms.date: 03/30/2017
helpviewer_keywords:
- corners [WPF], rounding
- RectangleGeometry class [WPF], rounding corners
- graphics [WPF], rounding corners of RectangleGeometry objects [WPF]
- rounding corners of RectangleGeometry objects [WPF]
ms.assetid: 926644bc-1357-4c0b-ac81-694bd090ae87
ms.openlocfilehash: eb2f173bedb903e12b2795264c684524cfa09825
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089138"
---
# <a name="how-to-round-the-corners-of-a-rectanglegeometry"></a><span data-ttu-id="28301-102">Filtrar Redondear las esquinas de un RectangleGeometry</span><span class="sxs-lookup"><span data-stu-id="28301-102">How to: Round the Corners of a RectangleGeometry</span></span>
<span data-ttu-id="28301-103">Para redondear los vértices de un <xref:System.Windows.Media.RectangleGeometry>, establezca su <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> y <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> propiedades en un valor mayor que cero.</span><span class="sxs-lookup"><span data-stu-id="28301-103">To round the corners of a <xref:System.Windows.Media.RectangleGeometry>, set its <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> and <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> properties to a value greater than zero.</span></span> <span data-ttu-id="28301-104">Cuanto mayor sea el valores, más redondeadas serán las esquinas del rectángulo.</span><span class="sxs-lookup"><span data-stu-id="28301-104">The larger the values, the rounder the rectangle's corners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28301-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="28301-105">Example</span></span>  
 <span data-ttu-id="28301-106">El ejemplo siguiente se muestra varias <xref:System.Windows.Media.RectangleGeometry> objetos con diferentes <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> y <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> configuración.</span><span class="sxs-lookup"><span data-stu-id="28301-106">The following example shows several <xref:System.Windows.Media.RectangleGeometry> objects with different <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> and <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> settings.</span></span> <span data-ttu-id="28301-107">El <xref:System.Windows.Media.RectangleGeometry> objetos se muestran mediante <xref:System.Windows.Shapes.Path> elementos.</span><span class="sxs-lookup"><span data-stu-id="28301-107">The <xref:System.Windows.Media.RectangleGeometry> objects are displayed using <xref:System.Windows.Shapes.Path> elements.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRoundedRectangleGeometryExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/RectangleGeometryRoundedCornerExample.xaml#graphicsmmroundedrectanglegeometryexamplewholepage)]  
  
 <span data-ttu-id="28301-108">![Rectángulos con diferentes RadiusX&#47;configuración RadiusY](./media/graphicsmm-rounded.png "graphicsmm_rounded")</span><span class="sxs-lookup"><span data-stu-id="28301-108">![Rectangles with different RadiusX&#47;RadiusY settings](./media/graphicsmm-rounded.png "graphicsmm_rounded")</span></span>  
<span data-ttu-id="28301-109">Rectángulos con esquinas redondeadas</span><span class="sxs-lookup"><span data-stu-id="28301-109">Rectangles with Rounded Corners</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28301-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="28301-110">See also</span></span>

- [<span data-ttu-id="28301-111">Información general sobre geometría</span><span class="sxs-lookup"><span data-stu-id="28301-111">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="28301-112">Crear una forma compuesta</span><span class="sxs-lookup"><span data-stu-id="28301-112">Create a Composite Shape</span></span>](how-to-create-a-composite-shape.md)
- [<span data-ttu-id="28301-113">Crear una forma mediante una clase PathGeometry</span><span class="sxs-lookup"><span data-stu-id="28301-113">Create a Shape by Using a PathGeometry</span></span>](how-to-create-a-shape-by-using-a-pathgeometry.md)
