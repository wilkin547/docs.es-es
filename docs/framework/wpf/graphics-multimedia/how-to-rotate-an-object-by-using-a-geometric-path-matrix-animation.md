---
title: "Cómo: Girar un objeto utilizando un trazado geométrico (animación en matriz)"
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
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
- matrix animation [WPF]
ms.assetid: 877dc9aa-6bdc-4beb-8772-3efaec32c0f0
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c001c0969e42c1eaadad6c029ae86009176b9eb7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation"></a>Cómo: Girar un objeto utilizando un trazado geométrico (animación en matriz)
Este ejemplo muestra cómo utilizar un <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> y un <xref:System.Windows.Media.MatrixTransform> para girar un objeto a lo largo de una ruta de acceso geométrica definida por un <xref:System.Windows.Media.PathGeometry> objeto.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> objeto que se va a animar el <xref:System.Windows.Media.MatrixTransform.Matrix%2A> propiedad de un <xref:System.Windows.Media.MatrixTransform>. El <xref:System.Windows.Media.MatrixTransform> se aplica a un botón y hace que se mueva a lo largo de un trazado curvo. Dado que la <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> propiedad está establecida en `true`, el rectángulo se gira a lo largo de la tangente de la ruta de acceso.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 Para obtener un ejemplo completo, vea [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).  
  
 La versión de código del ejemplo anterior utiliza un <xref:System.Windows.Media.Animation.Storyboard> para animar la <xref:System.Windows.Media.EllipseGeometry>, incluso si se aplica solo una animación. Una manera más fácil de aplicar una sola animación a una propiedad en el código es usar el <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> método. Para obtener un ejemplo, vea [Animar una propiedad sin utilizar un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Temas de procedimientos de animación de trazado](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)  
 [Ejemplo de animación de trazado](http://go.microsoft.com/fwlink/?LinkID=160028)
