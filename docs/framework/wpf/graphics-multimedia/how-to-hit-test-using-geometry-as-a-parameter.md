---
title: Filtrar Realizar una prueba de posicionamiento usando Geometry como parámetro
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects using Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], hit tests on visual objects [WPF]
ms.assetid: 6c8bdbf2-19e0-4fbb-bf89-c1252b2ebc61
ms.openlocfilehash: 15a33d05cb3ca4fd40f04170bd1756e466631275
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57366366"
---
# <a name="how-to-hit-test-using-geometry-as-a-parameter"></a>Filtrar Realizar una prueba de posicionamiento usando Geometry como parámetro
En este ejemplo se muestra cómo realizar una prueba de posicionamiento en un objeto visual mediante un <xref:System.Windows.Media.Geometry> como un impacto en el parámetro de la prueba.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo configurar una prueba de posicionamiento usando <xref:System.Windows.Media.GeometryHitTestParameters> para el <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> método. El <xref:System.Windows.Point> valor que se pasa a la `OnMouseDown` método se usa para crear un <xref:System.Windows.Media.Geometry> objeto con el fin de ampliar el intervalo de la prueba de posicionamiento.  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet10)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet10)]  
  
 El <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> propiedad de <xref:System.Windows.Media.GeometryHitTestResult> proporciona información acerca de los resultados de una prueba de posicionamiento que utiliza un <xref:System.Windows.Media.Geometry> como un impacto en el parámetro de la prueba. La siguiente ilustración muestra la relación entre la geometría de la prueba de posicionamiento (círculo azul) y el contenido representado del objeto visual de destino (cuadrado rojo).  
  
 ![Diagrama de IntersectionDetail utilizado en la prueba de posicionamiento](./media/intersectiondetail01.png "IntersectionDetail01")  
Intersección entre la geometría de la prueba de posicionamiento y el objeto visual de destino  
  
 El ejemplo siguiente muestra cómo implementar una devolución de llamada de prueba de posicionamiento cuando un <xref:System.Windows.Media.Geometry> se utiliza como un parámetro de prueba de posicionamiento. El `result` parámetro se convierte en un <xref:System.Windows.Media.GeometryHitTestResult> con el fin de recuperar el valor de la <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> propiedad. El valor de propiedad le permite determinar si el <xref:System.Windows.Media.Geometry> parámetro de prueba de posicionamiento está total o parcialmente dentro del contenido representado del destino de prueba de posicionamiento. En este caso, el código de ejemplo solo está agregando los resultados de la prueba de posicionamiento a la lista para elementos visuales que estén totalmente entro del límite de destino.  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet11)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet11)]  
  
> [!NOTE]
>  El <xref:System.Windows.Media.HitTestResult> devolución de llamada no debe llamarse cuando la información de la intersección es <xref:System.Windows.Media.IntersectionDetail.Empty>.  
  
## <a name="see-also"></a>Vea también
- [Realizar pruebas de posicionamiento en la capa visual](hit-testing-in-the-visual-layer.md)
- [Geometría de una prueba de posicionamiento en un objeto Visual](how-to-hit-test-geometry-in-a-visual.md)
