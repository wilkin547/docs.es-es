---
title: 'Cómo: Girar un objeto utilizando un trazado geométrico'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
ms.assetid: cb31ca4d-f05a-4c6b-9a18-4b6faaf38d45
ms.openlocfilehash: 5a73ee967be0aae7dc3f1ef82229c2bcb2f9ade2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560721"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path"></a>Cómo: Girar un objeto utilizando un trazado geométrico
Este ejemplo muestra cómo girar un objeto a lo largo de una ruta de acceso geométrica definida por un <xref:System.Windows.Media.PathGeometry> objeto.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza tres <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> objetos que se va a mover un rectángulo a lo largo de un trazado geométrico.  
  
-   La primera <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> anima un <xref:System.Windows.Media.RotateTransform> que se aplica al rectángulo. La animación genera valores de ángulo. Hace que el rectángulo gire (pivote) a lo largo de los contornos del trazado.  
  
-   Los otros dos objetos animan la <xref:System.Windows.Media.TranslateTransform.X%2A> y <xref:System.Windows.Media.TranslateTransform.Y%2A> valores de un <xref:System.Windows.Media.TranslateTransform> que se aplica al rectángulo. Hacen que el rectángulo se mueva horizontal y verticalmente a lo largo del trazado.  
  
 [!code-xaml[PathAnimationGallery_snippet#RotateAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/rotateanimationusingpathexample.xaml#rotateanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/RotateAnimationUsingPathExample.cs#rotateanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/RotateAnimationUsingPathExample.vb#rotateanimationusingpathwholepage)]  
  
 Otra manera de girar un objeto utilizando un trazado geométrico es usar un <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> de objeto y establecer su <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> propiedad `true`. Para obtener más información y un ejemplo, vea [girar un objeto utilizando un trazado geométrico (animación de matriz)](../../../../docs/framework/wpf/graphics-multimedia/how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md).  
  
 Para obtener un ejemplo completo, vea [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Ejemplo de animación de trazado](http://go.microsoft.com/fwlink/?LinkID=160028)  
 [Temas de procedimientos de animación de trazado](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
