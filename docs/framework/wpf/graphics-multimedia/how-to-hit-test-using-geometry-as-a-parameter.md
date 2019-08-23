---
title: Procedimiento Realizar una prueba de posicionamiento mediante el uso de Geometry como parámetro
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects using Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], hit tests on visual objects [WPF]
ms.assetid: 6c8bdbf2-19e0-4fbb-bf89-c1252b2ebc61
ms.openlocfilehash: 8bed7784b00f49178c9a87def74b62f7ce620ec7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923408"
---
# <a name="how-to-hit-test-using-geometry-as-a-parameter"></a><span data-ttu-id="34f9a-102">Procedimiento Realizar una prueba de posicionamiento mediante el uso de Geometry como parámetro</span><span class="sxs-lookup"><span data-stu-id="34f9a-102">How to: Hit Test Using Geometry as a Parameter</span></span>
<span data-ttu-id="34f9a-103">En este ejemplo se muestra cómo realizar una prueba de posicionamiento en un objeto visual <xref:System.Windows.Media.Geometry> utilizando como parámetro de prueba de posicionamiento.</span><span class="sxs-lookup"><span data-stu-id="34f9a-103">This example shows how to perform a hit test on a visual object using a <xref:System.Windows.Media.Geometry> as a hit test parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34f9a-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="34f9a-104">Example</span></span>  
 <span data-ttu-id="34f9a-105">En el ejemplo siguiente se muestra cómo configurar una prueba de posicionamiento <xref:System.Windows.Media.GeometryHitTestParameters> mediante para <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> el método.</span><span class="sxs-lookup"><span data-stu-id="34f9a-105">The following example shows how to set up a hit test using <xref:System.Windows.Media.GeometryHitTestParameters> for the <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> method.</span></span> <span data-ttu-id="34f9a-106">El <xref:System.Windows.Point> valor que se pasa `OnMouseDown` al método se usa para crear un <xref:System.Windows.Media.Geometry> objeto con el fin de expandir el intervalo de la prueba de posicionamiento.</span><span class="sxs-lookup"><span data-stu-id="34f9a-106">The <xref:System.Windows.Point> value that is passed to the `OnMouseDown` method is used to create a <xref:System.Windows.Media.Geometry> object in order to expand the range of the hit test.</span></span>  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet10)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet10)]  
  
 <span data-ttu-id="34f9a-107">La <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> propiedad de <xref:System.Windows.Media.GeometryHitTestResult> proporciona información sobre los resultados de una prueba de <xref:System.Windows.Media.Geometry> posicionamiento que utiliza como parámetro de prueba de posicionamiento.</span><span class="sxs-lookup"><span data-stu-id="34f9a-107">The <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> property of <xref:System.Windows.Media.GeometryHitTestResult> provides information about the results of a hit test that uses a <xref:System.Windows.Media.Geometry> as a hit test parameter.</span></span> <span data-ttu-id="34f9a-108">La siguiente ilustración muestra la relación entre la geometría de la prueba de posicionamiento (círculo azul) y el contenido representado del objeto visual de destino (cuadrado rojo).</span><span class="sxs-lookup"><span data-stu-id="34f9a-108">The following illustration shows the relationship between the hit test geometry (the blue circle) and the rendered content of the target visual object (the red square).</span></span>  
  
 ![Diagrama que muestra IntersectionDetail usado en la prueba de posicionamiento.](./media/how-to-hit-test-using-geometry-as-a-parameter/intersectiondetail-hit-test.png)  
  
 <span data-ttu-id="34f9a-110">En el ejemplo siguiente se muestra cómo implementar una devolución de llamada de <xref:System.Windows.Media.Geometry> la prueba de posicionamiento cuando se usa un parámetro de prueba de posicionamiento.</span><span class="sxs-lookup"><span data-stu-id="34f9a-110">The following example shows how to implement a hit test callback when a <xref:System.Windows.Media.Geometry> is used as a hit test parameter.</span></span> <span data-ttu-id="34f9a-111">El `result` parámetro se convierte en un <xref:System.Windows.Media.GeometryHitTestResult> objeto para recuperar el valor de la <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="34f9a-111">The `result` parameter is cast to a <xref:System.Windows.Media.GeometryHitTestResult> in order to retrieve the value of the <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> property.</span></span> <span data-ttu-id="34f9a-112">El valor de propiedad le permite determinar si el <xref:System.Windows.Media.Geometry> parámetro de la prueba de posicionamiento está incluido total o parcialmente en el contenido representado del destino de la prueba de posicionamiento.</span><span class="sxs-lookup"><span data-stu-id="34f9a-112">The property value allows you to determine if the <xref:System.Windows.Media.Geometry> hit test parameter is fully or partially contained within the rendered content of the hit test target.</span></span> <span data-ttu-id="34f9a-113">En este caso, el código de ejemplo solo está agregando los resultados de la prueba de posicionamiento a la lista para elementos visuales que estén totalmente entro del límite de destino.</span><span class="sxs-lookup"><span data-stu-id="34f9a-113">In this case, the sample code is only adding hit test results to the list for visuals that are fully contained within the target boundary.</span></span>  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet11)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet11)]  
  
> [!NOTE]
> <span data-ttu-id="34f9a-114">No <xref:System.Windows.Media.HitTestResult> se debe llamar a la devolución de llamada cuando el <xref:System.Windows.Media.IntersectionDetail.Empty>detalle de la intersección es.</span><span class="sxs-lookup"><span data-stu-id="34f9a-114">The <xref:System.Windows.Media.HitTestResult> callback should not be called when the intersection detail is <xref:System.Windows.Media.IntersectionDetail.Empty>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34f9a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="34f9a-115">See also</span></span>

- [<span data-ttu-id="34f9a-116">Realizar pruebas de posicionamiento en la capa visual</span><span class="sxs-lookup"><span data-stu-id="34f9a-116">Hit Testing in the Visual Layer</span></span>](hit-testing-in-the-visual-layer.md)
- [<span data-ttu-id="34f9a-117">Geometría de una prueba de posicionamiento en un objeto Visual</span><span class="sxs-lookup"><span data-stu-id="34f9a-117">Hit Test Geometry in a Visual</span></span>](how-to-hit-test-geometry-in-a-visual.md)
