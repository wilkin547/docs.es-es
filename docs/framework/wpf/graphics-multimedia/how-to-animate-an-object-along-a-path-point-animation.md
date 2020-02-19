---
title: 'Cómo: Animar un objeto a lo largo de un trazado (animación en punto)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (point animation)
- point animation [WPF]
ms.assetid: 1fa3f817-35bc-41a1-b366-f5a20b70da0c
ms.openlocfilehash: eff0c24a9369ffaa0cfca1cc46af4eff39f58a38
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452901"
---
# <a name="how-to-animate-an-object-along-a-path-point-animation"></a>Cómo: Animar un objeto a lo largo de un trazado (animación en punto)
En este ejemplo se muestra cómo utilizar un objeto <xref:System.Windows.Media.Animation.PointAnimationUsingPath> para animar un <xref:System.Windows.Point> a lo largo de un trazado curvo.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se mueve una <xref:System.Windows.Media.EllipseGeometry> a lo largo de un trazado definido por un <xref:System.Windows.Media.PathGeometry>. La propiedad <xref:System.Windows.Media.EllipseGeometry.Center%2A> de la geometría de elipse, que toma un valor <xref:System.Windows.Point>, especifica su posición; para desplace la geometría de la elipse, anime su propiedad <xref:System.Windows.Media.EllipseGeometry.Center%2A>. En el ejemplo se usa un <xref:System.Windows.Media.Animation.PointAnimationUsingPath> para animar la propiedad <xref:System.Windows.Media.EllipseGeometry.Center%2A> del objeto <xref:System.Windows.Media.EllipseGeometry>.  
  
 [!code-xaml[PathAnimationGallery_snippet#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/pointanimationusingpathexample.xaml#pointanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/PointAnimationUsingPathExample.cs#pointanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/PointAnimationUsingPathExample.vb#pointanimationusingpathwholepage)]  
  
 Para obtener el ejemplo completo, consulte [ejemplo de animación de trazado](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).  
  
 La versión de código del ejemplo anterior usaba un <xref:System.Windows.Media.Animation.Storyboard> para animar el <xref:System.Windows.Media.EllipseGeometry>, aunque solo se aplicó una animación. Una <xref:System.Windows.Media.Animation.Storyboard> suele ser la manera más fácil de aplicar varias animaciones porque estas animaciones pueden controlarse mediante el mismo <xref:System.Windows.Media.Animation.Storyboard>. Sin embargo, una manera más fácil de aplicar una animación única a una propiedad cuando se usa código es usar el método <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>. Para obtener un ejemplo, vea [Animar una propiedad sin utilizar un guión gráfico](how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Consulte también

- [Ejemplo de animación de trazado](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [Información general sobre animaciones](animation-overview.md)
- [Temas de procedimientos de animación de trazado](path-animation-how-to-topics.md)
