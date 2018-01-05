---
title: "Cómo: Animar un objeto a lo largo de un trazado (animación en punto)"
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
- animation [WPF], objects along paths (point animation)
- point animation [WPF]
ms.assetid: 1fa3f817-35bc-41a1-b366-f5a20b70da0c
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 399d6b8028b8715f38335089a723707657df4a98
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-an-object-along-a-path-point-animation"></a>Cómo: Animar un objeto a lo largo de un trazado (animación en punto)
Este ejemplo muestra cómo utilizar un <xref:System.Windows.Media.Animation.PointAnimationUsingPath> objeto que se va a animar un <xref:System.Windows.Point> a lo largo de un trazado curvo.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo mueve un <xref:System.Windows.Media.EllipseGeometry> a lo largo de una ruta de acceso definido por un <xref:System.Windows.Media.PathGeometry>. La geometría de elipse <xref:System.Windows.Media.EllipseGeometry.Center%2A> propiedad, que toma un <xref:System.Windows.Point> valor, especifica su posición; para mover la geometría de elipse, le animar su <xref:System.Windows.Media.EllipseGeometry.Center%2A> propiedad. El ejemplo se usa un <xref:System.Windows.Media.Animation.PointAnimationUsingPath> para animar la <xref:System.Windows.Media.EllipseGeometry> del objeto <xref:System.Windows.Media.EllipseGeometry.Center%2A> propiedad.  
  
 [!code-xaml[PathAnimationGallery_snippet#PointAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/pointanimationusingpathexample.xaml#pointanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/PointAnimationUsingPathExample.cs#pointanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/PointAnimationUsingPathExample.vb#pointanimationusingpathwholepage)]  
  
 Para obtener un ejemplo completo, vea [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).  
  
 La versión de código del ejemplo anterior utiliza un <xref:System.Windows.Media.Animation.Storyboard> para animar la <xref:System.Windows.Media.EllipseGeometry>, incluso si se aplica solo una animación. A <xref:System.Windows.Media.Animation.Storyboard> suele ser la manera más fácil de aplicar varias animaciones, porque estas animaciones pueden controlarse mediante el mismo <xref:System.Windows.Media.Animation.Storyboard>. Sin embargo, una manera más fácil de aplicar una sola animación a una propiedad cuando se usa código es usar el <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> método. Para obtener un ejemplo, vea [Animar una propiedad sin utilizar un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Vea también  
 [Ejemplo de animación de trazado](http://go.microsoft.com/fwlink/?LinkID=160028)  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Temas de procedimientos de animación de trazado](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
