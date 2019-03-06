---
title: Filtrar Animar un objeto a lo largo de un trazado (animación en punto)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (point animation)
- point animation [WPF]
ms.assetid: 1fa3f817-35bc-41a1-b366-f5a20b70da0c
ms.openlocfilehash: 13cf583277b4e105da01c5ab56111123cf03038c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351631"
---
# <a name="how-to-animate-an-object-along-a-path-point-animation"></a>Procedimiento Animar un objeto a lo largo de un trazado (animación en punto)
En este ejemplo se muestra cómo usar un <xref:System.Windows.Media.Animation.PointAnimationUsingPath> objeto para animar un <xref:System.Windows.Point> a lo largo de un trazado curvo.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se mueve una <xref:System.Windows.Media.EllipseGeometry> a lo largo de un trazado definido por un <xref:System.Windows.Media.PathGeometry>. La geometría de elipse <xref:System.Windows.Media.EllipseGeometry.Center%2A> propiedad, que toma un <xref:System.Windows.Point> valor, especifica su posición; para mover la geometría de elipse, puede animar su <xref:System.Windows.Media.EllipseGeometry.Center%2A> propiedad. El ejemplo se usa un <xref:System.Windows.Media.Animation.PointAnimationUsingPath> para animar la <xref:System.Windows.Media.EllipseGeometry> del objeto <xref:System.Windows.Media.EllipseGeometry.Center%2A> propiedad.  
  
 [!code-xaml[PathAnimationGallery_snippet#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/pointanimationusingpathexample.xaml#pointanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/PointAnimationUsingPathExample.cs#pointanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/PointAnimationUsingPathExample.vb#pointanimationusingpathwholepage)]  
  
 Para obtener un ejemplo completo, vea [ejemplo de animación de trazado](https://go.microsoft.com/fwlink/?LinkID=160028).  
  
 La versión del código del ejemplo anterior utiliza un <xref:System.Windows.Media.Animation.Storyboard> para animar el <xref:System.Windows.Media.EllipseGeometry>, aunque se aplique solo a una animación. Un <xref:System.Windows.Media.Animation.Storyboard> suele ser la manera más fácil de aplicar varias animaciones, porque estas animaciones pueden controlarse con el mismo <xref:System.Windows.Media.Animation.Storyboard>. Sin embargo, una manera más fácil de aplicar una animación única a una propiedad cuando se usa el código es usar el <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> método. Para obtener un ejemplo, vea [Animar una propiedad sin utilizar un guión gráfico](how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Vea también
- [Ejemplo de animación de trazado](https://go.microsoft.com/fwlink/?LinkID=160028)
- [Información general sobre animaciones](animation-overview.md)
- [Temas de procedimientos de animación de trazado](path-animation-how-to-topics.md)
