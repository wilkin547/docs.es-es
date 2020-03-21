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
ms.openlocfilehash: a351fdc936f634b7c57ba5a49e51501f7572a3c9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186875"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path"></a>Cómo: Girar un objeto utilizando un trazado geométrico
En este ejemplo se muestra cómo girar (pivotar) un <xref:System.Windows.Media.PathGeometry> objeto a lo largo de un trazado geométrico definido por un objeto.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> siguiente se utilizan tres objetos para mover un rectángulo a lo largo de un trazado geométrico.  
  
- El <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> primero anima <xref:System.Windows.Media.RotateTransform> un que se aplica al rectángulo. La animación genera valores de ángulo. Hace que el rectángulo gire (pivote) a lo largo de los contornos del trazado.  
  
- Los otros dos <xref:System.Windows.Media.TranslateTransform.X%2A> objetos animan los valores y <xref:System.Windows.Media.TranslateTransform.Y%2A> de un <xref:System.Windows.Media.TranslateTransform> que se aplica al rectángulo. Hacen que el rectángulo se mueva horizontal y verticalmente a lo largo del trazado.  
  
 [!code-xaml[PathAnimationGallery_snippet#RotateAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/rotateanimationusingpathexample.xaml#rotateanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/RotateAnimationUsingPathExample.cs#rotateanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/RotateAnimationUsingPathExample.vb#rotateanimationusingpathwholepage)]  
  
 Otra forma de rotar un objeto mediante un <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> trazado geométrico es utilizar un objeto y establecer su <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> propiedad en `true`. Para obtener más información y un ejemplo, vea [Rotar un objeto mediante un trazado geométrico (animación de matriz)](how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md).  
  
 Para ver el ejemplo completo, consulte Ejemplo de [animación](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)de ruta de acceso .  
  
## <a name="see-also"></a>Consulte también

- [Información general sobre animaciones](animation-overview.md)
- [Ejemplo de animación de trazado](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [Temas de procedimientos de animación de trazado](path-animation-how-to-topics.md)
