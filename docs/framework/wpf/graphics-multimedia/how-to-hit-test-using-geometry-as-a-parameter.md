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
# <a name="how-to-hit-test-using-geometry-as-a-parameter"></a>Procedimiento Realizar una prueba de posicionamiento mediante el uso de Geometry como parámetro
En este ejemplo se muestra cómo realizar una prueba de posicionamiento en un objeto visual <xref:System.Windows.Media.Geometry> utilizando como parámetro de prueba de posicionamiento.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo configurar una prueba de posicionamiento <xref:System.Windows.Media.GeometryHitTestParameters> mediante para <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> el método. El <xref:System.Windows.Point> valor que se pasa `OnMouseDown` al método se usa para crear un <xref:System.Windows.Media.Geometry> objeto con el fin de expandir el intervalo de la prueba de posicionamiento.  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet10)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet10)]  
  
 La <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> propiedad de <xref:System.Windows.Media.GeometryHitTestResult> proporciona información sobre los resultados de una prueba de <xref:System.Windows.Media.Geometry> posicionamiento que utiliza como parámetro de prueba de posicionamiento. La siguiente ilustración muestra la relación entre la geometría de la prueba de posicionamiento (círculo azul) y el contenido representado del objeto visual de destino (cuadrado rojo).  
  
 ![Diagrama que muestra IntersectionDetail usado en la prueba de posicionamiento.](./media/how-to-hit-test-using-geometry-as-a-parameter/intersectiondetail-hit-test.png)  
  
 En el ejemplo siguiente se muestra cómo implementar una devolución de llamada de <xref:System.Windows.Media.Geometry> la prueba de posicionamiento cuando se usa un parámetro de prueba de posicionamiento. El `result` parámetro se convierte en un <xref:System.Windows.Media.GeometryHitTestResult> objeto para recuperar el valor de la <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> propiedad. El valor de propiedad le permite determinar si el <xref:System.Windows.Media.Geometry> parámetro de la prueba de posicionamiento está incluido total o parcialmente en el contenido representado del destino de la prueba de posicionamiento. En este caso, el código de ejemplo solo está agregando los resultados de la prueba de posicionamiento a la lista para elementos visuales que estén totalmente entro del límite de destino.  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet11)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet11)]  
  
> [!NOTE]
> No <xref:System.Windows.Media.HitTestResult> se debe llamar a la devolución de llamada cuando el <xref:System.Windows.Media.IntersectionDetail.Empty>detalle de la intersección es.  
  
## <a name="see-also"></a>Vea también

- [Realizar pruebas de posicionamiento en la capa visual](hit-testing-in-the-visual-layer.md)
- [Geometría de una prueba de posicionamiento en un objeto Visual](how-to-hit-test-geometry-in-a-visual.md)
