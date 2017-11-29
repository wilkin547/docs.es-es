---
title: "Cómo: Redondear las esquinas de un RectangleGeometry"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- corners [WPF], rounding
- RectangleGeometry class [WPF], rounding corners
- graphics [WPF], rounding corners of RectangleGeometry objects [WPF]
- rounding corners of RectangleGeometry objects [WPF]
ms.assetid: 926644bc-1357-4c0b-ac81-694bd090ae87
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4cd857f7ce886095bcbe92ae57c350ce83bb5c7d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-round-the-corners-of-a-rectanglegeometry"></a><span data-ttu-id="54228-102">Cómo: Redondear las esquinas de un RectangleGeometry</span><span class="sxs-lookup"><span data-stu-id="54228-102">How to: Round the Corners of a RectangleGeometry</span></span>
<span data-ttu-id="54228-103">Para redondear los vértices de un <xref:System.Windows.Media.RectangleGeometry>, establezca su <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> y <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> propiedades en un valor mayor que cero.</span><span class="sxs-lookup"><span data-stu-id="54228-103">To round the corners of a <xref:System.Windows.Media.RectangleGeometry>, set its <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> and <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> properties to a value greater than zero.</span></span> <span data-ttu-id="54228-104">Cuanto mayores sean los valores, más redondeadas serán las esquinas del rectángulo.</span><span class="sxs-lookup"><span data-stu-id="54228-104">The larger the values, the rounder the rectangle's corners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54228-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="54228-105">Example</span></span>  
 <span data-ttu-id="54228-106">En el ejemplo siguiente se muestra varias <xref:System.Windows.Media.RectangleGeometry> objetos con diferentes <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> y <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> configuración.</span><span class="sxs-lookup"><span data-stu-id="54228-106">The following example shows several <xref:System.Windows.Media.RectangleGeometry> objects with different <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> and <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> settings.</span></span> <span data-ttu-id="54228-107">El <xref:System.Windows.Media.RectangleGeometry> objetos se muestran con <xref:System.Windows.Shapes.Path> elementos.</span><span class="sxs-lookup"><span data-stu-id="54228-107">The <xref:System.Windows.Media.RectangleGeometry> objects are displayed using <xref:System.Windows.Shapes.Path> elements.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRoundedRectangleGeometryExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/RectangleGeometryRoundedCornerExample.xaml#graphicsmmroundedrectanglegeometryexamplewholepage)]  
  
 <span data-ttu-id="54228-108">![Rectángulos con diferentes valores de RadiusX &#47; Configuración radiusY](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rounded.png "graphicsmm_rounded")</span><span class="sxs-lookup"><span data-stu-id="54228-108">![Rectangles with different RadiusX&#47;RadiusY settings](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rounded.png "graphicsmm_rounded")</span></span>  
<span data-ttu-id="54228-109">Rectángulos con esquinas redondeadas</span><span class="sxs-lookup"><span data-stu-id="54228-109">Rectangles with Rounded Corners</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54228-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="54228-110">See Also</span></span>  
 [<span data-ttu-id="54228-111">Información general sobre geometría</span><span class="sxs-lookup"><span data-stu-id="54228-111">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="54228-112">Crear una forma compuesta</span><span class="sxs-lookup"><span data-stu-id="54228-112">Create a Composite Shape</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)  
 [<span data-ttu-id="54228-113">Crear una forma mediante una clase PathGeometry</span><span class="sxs-lookup"><span data-stu-id="54228-113">Create a Shape by Using a PathGeometry</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
