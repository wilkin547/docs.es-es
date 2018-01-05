---
title: "Cómo: Realizar una prueba de posicionamiento usando Geometry como parámetro"
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
helpviewer_keywords:
- hit tests [WPF], on visual objects using Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], hit tests on visual objects [WPF]
ms.assetid: 6c8bdbf2-19e0-4fbb-bf89-c1252b2ebc61
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1b5c5bb47e3f435419bcf3c472f052260adec7c0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-hit-test-using-geometry-as-a-parameter"></a><span data-ttu-id="8ffff-102">Cómo: Realizar una prueba de posicionamiento usando Geometry como parámetro</span><span class="sxs-lookup"><span data-stu-id="8ffff-102">How to: Hit Test Using Geometry as a Parameter</span></span>
<span data-ttu-id="8ffff-103">Este ejemplo muestra cómo realizar una prueba de posicionamiento en un objeto visual mediante un <xref:System.Windows.Media.Geometry> como un impacto en el parámetro de la prueba.</span><span class="sxs-lookup"><span data-stu-id="8ffff-103">This example shows how to perform a hit test on a visual object using a <xref:System.Windows.Media.Geometry> as a hit test parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ffff-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8ffff-104">Example</span></span>  
 <span data-ttu-id="8ffff-105">En el ejemplo siguiente se muestra cómo configurar una prueba de posicionamiento usando <xref:System.Windows.Media.GeometryHitTestParameters> para el <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> método.</span><span class="sxs-lookup"><span data-stu-id="8ffff-105">The following example shows how to set up a hit test using <xref:System.Windows.Media.GeometryHitTestParameters> for the <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> method.</span></span> <span data-ttu-id="8ffff-106">El <xref:System.Windows.Point> valor que se pasa a la `OnMouseDown` método se utiliza para crear un <xref:System.Windows.Media.Geometry> objeto con el fin de ampliar el intervalo de la prueba de posicionamiento.</span><span class="sxs-lookup"><span data-stu-id="8ffff-106">The <xref:System.Windows.Point> value that is passed to the `OnMouseDown` method is used to create a <xref:System.Windows.Media.Geometry> object in order to expand the range of the hit test.</span></span>  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet10)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet10)]  
  
 <span data-ttu-id="8ffff-107">El <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> propiedad de <xref:System.Windows.Media.GeometryHitTestResult> proporciona información acerca de los resultados de una prueba de posicionamiento que utiliza un <xref:System.Windows.Media.Geometry> como un impacto en el parámetro de la prueba.</span><span class="sxs-lookup"><span data-stu-id="8ffff-107">The <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> property of <xref:System.Windows.Media.GeometryHitTestResult> provides information about the results of a hit test that uses a <xref:System.Windows.Media.Geometry> as a hit test parameter.</span></span> <span data-ttu-id="8ffff-108">La siguiente ilustración muestra la relación entre la geometría de la prueba de posicionamiento (círculo azul) y el contenido representado del objeto visual de destino (cuadrado rojo).</span><span class="sxs-lookup"><span data-stu-id="8ffff-108">The following illustration shows the relationship between the hit test geometry (the blue circle) and the rendered content of the target visual object (the red square).</span></span>  
  
 <span data-ttu-id="8ffff-109">![Diagrama de IntersectionDetail usado en la prueba de posicionamiento](../../../../docs/framework/wpf/graphics-multimedia/media/intersectiondetail01.png "IntersectionDetail01")</span><span class="sxs-lookup"><span data-stu-id="8ffff-109">![Diagram of IntersectionDetail used in hit testing](../../../../docs/framework/wpf/graphics-multimedia/media/intersectiondetail01.png "IntersectionDetail01")</span></span>  
<span data-ttu-id="8ffff-110">Intersección entre la geometría de la prueba de posicionamiento y el objeto visual de destino</span><span class="sxs-lookup"><span data-stu-id="8ffff-110">Intersection between hit test geometry and target visual object</span></span>  
  
 <span data-ttu-id="8ffff-111">En el ejemplo siguiente se muestra cómo implementar una devolución de llamada de la prueba de posicionamiento cuando un <xref:System.Windows.Media.Geometry> se utiliza como un parámetro de la prueba de posicionamiento.</span><span class="sxs-lookup"><span data-stu-id="8ffff-111">The following example shows how to implement a hit test callback when a <xref:System.Windows.Media.Geometry> is used as a hit test parameter.</span></span> <span data-ttu-id="8ffff-112">El `result` parámetro se convierte en una <xref:System.Windows.Media.GeometryHitTestResult> con el fin de recuperar el valor de la <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="8ffff-112">The `result` parameter is cast to a <xref:System.Windows.Media.GeometryHitTestResult> in order to retrieve the value of the <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> property.</span></span> <span data-ttu-id="8ffff-113">El valor de propiedad le permite determinar si el <xref:System.Windows.Media.Geometry> parámetro de prueba de posicionamiento está total o parcialmente dentro del contenido representado de la prueba de posicionamiento de destino.</span><span class="sxs-lookup"><span data-stu-id="8ffff-113">The property value allows you to determine if the <xref:System.Windows.Media.Geometry> hit test parameter is fully or partially contained within the rendered content of the hit test target.</span></span> <span data-ttu-id="8ffff-114">En este caso, el código de ejemplo solo está agregando los resultados de la prueba de posicionamiento a la lista para elementos visuales que estén totalmente entro del límite de destino.</span><span class="sxs-lookup"><span data-stu-id="8ffff-114">In this case, the sample code is only adding hit test results to the list for visuals that are fully contained within the target boundary.</span></span>  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet11)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet11)]  
  
> [!NOTE]
>  <span data-ttu-id="8ffff-115">El <xref:System.Windows.Media.HitTestResult> devolución de llamada no debe llamarse una vez el detalle de la intersección <xref:System.Windows.Media.IntersectionDetail.Empty>.</span><span class="sxs-lookup"><span data-stu-id="8ffff-115">The <xref:System.Windows.Media.HitTestResult> callback should not be called when the intersection detail is <xref:System.Windows.Media.IntersectionDetail.Empty>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ffff-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ffff-116">See Also</span></span>  
 [<span data-ttu-id="8ffff-117">Realizar pruebas de posicionamiento en la capa visual</span><span class="sxs-lookup"><span data-stu-id="8ffff-117">Hit Testing in the Visual Layer</span></span>](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)  
 [<span data-ttu-id="8ffff-118">Geometría de una prueba de posicionamiento en un objeto Visual</span><span class="sxs-lookup"><span data-stu-id="8ffff-118">Hit Test Geometry in a Visual</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-hit-test-geometry-in-a-visual.md)
