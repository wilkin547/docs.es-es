---
title: 'Cómo: Animar un objeto a lo largo de una trayectoria (animación doble)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (double animation)
- double animation [WPF]
ms.assetid: 5a3c4a99-f303-42ad-a52a-e4794bb1798e
ms.openlocfilehash: 084caac26fd68b6914ec3858652ec44557a0dbd7
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452862"
---
# <a name="how-to-animate-an-object-along-a-path-double-animation"></a>Cómo: Animar un objeto a lo largo de una trayectoria (animación doble)
En este ejemplo se muestra cómo usar la clase <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> para trasladar un objeto a lo largo de un trazado definido por un <xref:System.Windows.Media.PathGeometry>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usan dos objetos <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> para desplace un rectángulo a lo largo de un trazado geométrico:  
  
- La primera <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> anima el <xref:System.Windows.Media.TranslateTransform.X%2A> de la <xref:System.Windows.Media.TranslateTransform> aplicada al rectángulo. Hace que el rectángulo se mueva horizontalmente a lo largo del trazado.  
  
- El segundo <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> anima el <xref:System.Windows.Media.TranslateTransform.Y%2A> de la <xref:System.Windows.Media.TranslateTransform> aplicada al rectángulo. Hace que el rectángulo se mueva verticalmente a lo largo del trazado.  
  
 [!code-xaml[PathAnimationGallery_snippet#DoubleAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/doubleanimationusingpathexample.xaml#doubleanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/DoubleAnimationUsingPathExample.cs#doubleanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/DoubleAnimationUsingPathExample.vb#doubleanimationusingpathwholepage)]  
  
 Para obtener el ejemplo completo, consulte [ejemplo de animación de trazado](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).  
  
 Otra manera de trasladar un objeto mediante una ruta de acceso geométrica es usar un objeto de <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>. Para obtener un ejemplo, vea [animar un objeto a lo largo de un trazado (animación en matriz)](how-to-animate-an-object-along-a-path-matrix-animation.md).  
  
## <a name="see-also"></a>Consulte también

- [Información general sobre animaciones](animation-overview.md)
- [Temas de procedimientos de animación de trazado](path-animation-how-to-topics.md)
