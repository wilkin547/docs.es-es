---
title: Procedimiento Girar un objeto utilizando un trazado geométrico (animación en matriz)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
- matrix animation [WPF]
ms.assetid: 877dc9aa-6bdc-4beb-8772-3efaec32c0f0
ms.openlocfilehash: de61e2469e22d077da4b082e18340a837fac2880
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54565896"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation"></a>Procedimiento Girar un objeto utilizando un trazado geométrico (animación en matriz)
En este ejemplo se muestra cómo usar un <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> y un <xref:System.Windows.Media.MatrixTransform> para girar (pivotar) un objeto a lo largo de un trazado geométrico definido por un <xref:System.Windows.Media.PathGeometry> objeto.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> objeto que se va a animar el <xref:System.Windows.Media.MatrixTransform.Matrix%2A> propiedad de un <xref:System.Windows.Media.MatrixTransform>. El <xref:System.Windows.Media.MatrixTransform> se aplica a un botón y hace que se mueva a lo largo de un trazado curvo. Dado que el <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> propiedad está establecida en `true`, el rectángulo gira a lo largo de la tangente de la ruta de acceso.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 Para obtener un ejemplo completo, vea [ejemplo de animación de trazado](https://go.microsoft.com/fwlink/?LinkID=160028).  
  
 La versión del código del ejemplo anterior utiliza un <xref:System.Windows.Media.Animation.Storyboard> para animar el <xref:System.Windows.Media.EllipseGeometry>, aunque se aplique solo a una animación. Una manera más fácil de aplicar una animación única a una propiedad en el código es usar el <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> método. Para obtener un ejemplo, vea [Animar una propiedad sin utilizar un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Vea también
- [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [Temas de procedimientos de animación de trazado](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
- [Ejemplo de animación de trazado](https://go.microsoft.com/fwlink/?LinkID=160028)
