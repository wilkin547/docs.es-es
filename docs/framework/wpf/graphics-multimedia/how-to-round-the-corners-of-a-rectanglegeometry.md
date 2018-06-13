---
title: 'Cómo: Redondear las esquinas de un RectangleGeometry'
ms.date: 03/30/2017
helpviewer_keywords:
- corners [WPF], rounding
- RectangleGeometry class [WPF], rounding corners
- graphics [WPF], rounding corners of RectangleGeometry objects [WPF]
- rounding corners of RectangleGeometry objects [WPF]
ms.assetid: 926644bc-1357-4c0b-ac81-694bd090ae87
ms.openlocfilehash: e4f1d37e2c0f26967affff14ed6475fc8c0cb28c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561646"
---
# <a name="how-to-round-the-corners-of-a-rectanglegeometry"></a><span data-ttu-id="353bd-102">Cómo: Redondear las esquinas de un RectangleGeometry</span><span class="sxs-lookup"><span data-stu-id="353bd-102">How to: Round the Corners of a RectangleGeometry</span></span>
<span data-ttu-id="353bd-103">Para redondear los vértices de un <xref:System.Windows.Media.RectangleGeometry>, establezca su <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> y <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> propiedades en un valor mayor que cero.</span><span class="sxs-lookup"><span data-stu-id="353bd-103">To round the corners of a <xref:System.Windows.Media.RectangleGeometry>, set its <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> and <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> properties to a value greater than zero.</span></span> <span data-ttu-id="353bd-104">Cuanto mayores sean los valores, más redondeadas serán las esquinas del rectángulo.</span><span class="sxs-lookup"><span data-stu-id="353bd-104">The larger the values, the rounder the rectangle's corners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="353bd-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="353bd-105">Example</span></span>  
 <span data-ttu-id="353bd-106">En el ejemplo siguiente se muestra varias <xref:System.Windows.Media.RectangleGeometry> objetos con diferentes <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> y <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> configuración.</span><span class="sxs-lookup"><span data-stu-id="353bd-106">The following example shows several <xref:System.Windows.Media.RectangleGeometry> objects with different <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> and <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> settings.</span></span> <span data-ttu-id="353bd-107">El <xref:System.Windows.Media.RectangleGeometry> objetos se muestran con <xref:System.Windows.Shapes.Path> elementos.</span><span class="sxs-lookup"><span data-stu-id="353bd-107">The <xref:System.Windows.Media.RectangleGeometry> objects are displayed using <xref:System.Windows.Shapes.Path> elements.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRoundedRectangleGeometryExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/RectangleGeometryRoundedCornerExample.xaml#graphicsmmroundedrectanglegeometryexamplewholepage)]  
  
 <span data-ttu-id="353bd-108">![Rectángulos con diferentes valores de RadiusX&#47;configuración RadiusY](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rounded.png "graphicsmm_rounded")</span><span class="sxs-lookup"><span data-stu-id="353bd-108">![Rectangles with different RadiusX&#47;RadiusY settings](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rounded.png "graphicsmm_rounded")</span></span>  
<span data-ttu-id="353bd-109">Rectángulos con esquinas redondeadas</span><span class="sxs-lookup"><span data-stu-id="353bd-109">Rectangles with Rounded Corners</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="353bd-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="353bd-110">See Also</span></span>  
 [<span data-ttu-id="353bd-111">Información general sobre geometría</span><span class="sxs-lookup"><span data-stu-id="353bd-111">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="353bd-112">Crear una forma compuesta</span><span class="sxs-lookup"><span data-stu-id="353bd-112">Create a Composite Shape</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)  
 [<span data-ttu-id="353bd-113">Crear una forma mediante una clase PathGeometry</span><span class="sxs-lookup"><span data-stu-id="353bd-113">Create a Shape by Using a PathGeometry</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
