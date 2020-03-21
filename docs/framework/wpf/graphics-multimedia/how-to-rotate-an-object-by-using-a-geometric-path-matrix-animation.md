---
title: 'Cómo: Girar un objeto utilizando un trazado geométrico (animación en matriz)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
- matrix animation [WPF]
ms.assetid: 877dc9aa-6bdc-4beb-8772-3efaec32c0f0
ms.openlocfilehash: 63dc873a2b840ea3f870a8c60c5691ab271c1c9f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187410"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation"></a>Cómo: Girar un objeto utilizando un trazado geométrico (animación en matriz)
En este ejemplo se <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> muestra <xref:System.Windows.Media.MatrixTransform> cómo utilizar a y a para girar <xref:System.Windows.Media.PathGeometry> (pivotar) un objeto a lo largo de un trazado geométrico definido por un objeto.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> siguiente se <xref:System.Windows.Media.MatrixTransform.Matrix%2A> utiliza <xref:System.Windows.Media.MatrixTransform>el objeto para animar la propiedad de un archivo . Se <xref:System.Windows.Media.MatrixTransform> aplica a un botón y hace que se mueva a lo largo de un trazado curvo. Dado <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> que la `true`propiedad está establecida en , el rectángulo gira a lo largo de la tangente de la ruta de acceso.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 Para ver el ejemplo completo, consulte Ejemplo de [animación](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)de ruta de acceso .  
  
 La versión de código del <xref:System.Windows.Media.Animation.Storyboard> ejemplo <xref:System.Windows.Media.EllipseGeometry>anterior usaba a para animar el , aunque solo se aplicó una animación. Una manera más fácil de aplicar una sola animación a una propiedad en el código es usar el <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> método. Para obtener un ejemplo, vea [Animar una propiedad sin usar un guión gráfico](how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Consulte también

- [Información general sobre animaciones](animation-overview.md)
- [Temas de procedimientos de animación de trazado](path-animation-how-to-topics.md)
- [Ejemplo de animación de trazado](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
