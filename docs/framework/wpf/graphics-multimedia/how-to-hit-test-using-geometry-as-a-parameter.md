---
title: Filtrar Realizar una prueba de posicionamiento mediante el uso de Geometry como parámetro
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects using Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], hit tests on visual objects [WPF]
ms.assetid: 6c8bdbf2-19e0-4fbb-bf89-c1252b2ebc61
ms.openlocfilehash: 73420d6ae1386676ed900e91b3951df9e0934db8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59100969"
---
# <a name="how-to-hit-test-using-geometry-as-a-parameter"></a><span data-ttu-id="9ae5c-102">Filtrar Realizar una prueba de posicionamiento mediante el uso de Geometry como parámetro</span><span class="sxs-lookup"><span data-stu-id="9ae5c-102">How to: Hit Test Using Geometry as a Parameter</span></span>
<span data-ttu-id="9ae5c-103">En este ejemplo se muestra cómo realizar una prueba de posicionamiento en un objeto visual mediante un <xref:System.Windows.Media.Geometry> como un impacto en el parámetro de la prueba.</span><span class="sxs-lookup"><span data-stu-id="9ae5c-103">This example shows how to perform a hit test on a visual object using a <xref:System.Windows.Media.Geometry> as a hit test parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ae5c-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9ae5c-104">Example</span></span>  
 <span data-ttu-id="9ae5c-105">El ejemplo siguiente muestra cómo configurar una prueba de posicionamiento usando <xref:System.Windows.Media.GeometryHitTestParameters> para el <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> método.</span><span class="sxs-lookup"><span data-stu-id="9ae5c-105">The following example shows how to set up a hit test using <xref:System.Windows.Media.GeometryHitTestParameters> for the <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> method.</span></span> <span data-ttu-id="9ae5c-106">El <xref:System.Windows.Point> valor que se pasa a la `OnMouseDown` método se usa para crear un <xref:System.Windows.Media.Geometry> objeto con el fin de ampliar el intervalo de la prueba de posicionamiento.</span><span class="sxs-lookup"><span data-stu-id="9ae5c-106">The <xref:System.Windows.Point> value that is passed to the `OnMouseDown` method is used to create a <xref:System.Windows.Media.Geometry> object in order to expand the range of the hit test.</span></span>  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet10)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet10)]  
  
 <span data-ttu-id="9ae5c-107">El <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> propiedad de <xref:System.Windows.Media.GeometryHitTestResult> proporciona información acerca de los resultados de una prueba de posicionamiento que utiliza un <xref:System.Windows.Media.Geometry> como un impacto en el parámetro de la prueba.</span><span class="sxs-lookup"><span data-stu-id="9ae5c-107">The <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> property of <xref:System.Windows.Media.GeometryHitTestResult> provides information about the results of a hit test that uses a <xref:System.Windows.Media.Geometry> as a hit test parameter.</span></span> <span data-ttu-id="9ae5c-108">La siguiente ilustración muestra la relación entre la geometría de la prueba de posicionamiento (círculo azul) y el contenido representado del objeto visual de destino (cuadrado rojo).</span><span class="sxs-lookup"><span data-stu-id="9ae5c-108">The following illustration shows the relationship between the hit test geometry (the blue circle) and the rendered content of the target visual object (the red square).</span></span>  
  
 ![Diagrama que muestra IntersectionDetail utilizado en la prueba de posicionamiento.](./media/how-to-hit-test-using-geometry-as-a-parameter/intersectiondetail-hit-test.png)  
  
 <span data-ttu-id="9ae5c-110">El ejemplo siguiente muestra cómo implementar una devolución de llamada de prueba de posicionamiento cuando un <xref:System.Windows.Media.Geometry> se utiliza como un parámetro de prueba de posicionamiento.</span><span class="sxs-lookup"><span data-stu-id="9ae5c-110">The following example shows how to implement a hit test callback when a <xref:System.Windows.Media.Geometry> is used as a hit test parameter.</span></span> <span data-ttu-id="9ae5c-111">El `result` parámetro se convierte en un <xref:System.Windows.Media.GeometryHitTestResult> con el fin de recuperar el valor de la <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="9ae5c-111">The `result` parameter is cast to a <xref:System.Windows.Media.GeometryHitTestResult> in order to retrieve the value of the <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> property.</span></span> <span data-ttu-id="9ae5c-112">El valor de propiedad le permite determinar si el <xref:System.Windows.Media.Geometry> parámetro de prueba de posicionamiento está total o parcialmente dentro del contenido representado del destino de prueba de posicionamiento.</span><span class="sxs-lookup"><span data-stu-id="9ae5c-112">The property value allows you to determine if the <xref:System.Windows.Media.Geometry> hit test parameter is fully or partially contained within the rendered content of the hit test target.</span></span> <span data-ttu-id="9ae5c-113">En este caso, el código de ejemplo solo está agregando los resultados de la prueba de posicionamiento a la lista para elementos visuales que estén totalmente entro del límite de destino.</span><span class="sxs-lookup"><span data-stu-id="9ae5c-113">In this case, the sample code is only adding hit test results to the list for visuals that are fully contained within the target boundary.</span></span>  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet11)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet11)]  
  
> [!NOTE]
>  <span data-ttu-id="9ae5c-114">El <xref:System.Windows.Media.HitTestResult> devolución de llamada no debe llamarse cuando la información de la intersección es <xref:System.Windows.Media.IntersectionDetail.Empty>.</span><span class="sxs-lookup"><span data-stu-id="9ae5c-114">The <xref:System.Windows.Media.HitTestResult> callback should not be called when the intersection detail is <xref:System.Windows.Media.IntersectionDetail.Empty>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ae5c-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ae5c-115">See also</span></span>

- [<span data-ttu-id="9ae5c-116">Realizar pruebas de posicionamiento en la capa visual</span><span class="sxs-lookup"><span data-stu-id="9ae5c-116">Hit Testing in the Visual Layer</span></span>](hit-testing-in-the-visual-layer.md)
- [<span data-ttu-id="9ae5c-117">Geometría de una prueba de posicionamiento en un objeto visual</span><span class="sxs-lookup"><span data-stu-id="9ae5c-117">Hit Test Geometry in a Visual</span></span>](how-to-hit-test-geometry-in-a-visual.md)
