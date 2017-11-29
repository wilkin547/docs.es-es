---
title: "Cómo: Animar un objeto a lo largo de una trayectoria (animación doble)"
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
- animation [WPF], objects along paths (double animation)
- double animation [WPF]
ms.assetid: 5a3c4a99-f303-42ad-a52a-e4794bb1798e
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6a461b741675a18ac1e3544b17a9bbe9a8d18547
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-an-object-along-a-path-double-animation"></a>Cómo: Animar un objeto a lo largo de una trayectoria (animación doble)
Este ejemplo muestra cómo utilizar el <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> clase para mover un objeto a lo largo de una ruta de acceso definido por un <xref:System.Windows.Media.PathGeometry>.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente utiliza dos <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> objetos que se va a mover un rectángulo a lo largo de un trazado geométrico:  
  
-   La primera <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> anima la <xref:System.Windows.Media.TranslateTransform.X%2A> de la <xref:System.Windows.Media.TranslateTransform> aplicado al rectángulo. Hace que el rectángulo se mueva horizontalmente a lo largo del trazado.  
  
-   El segundo <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> anima la <xref:System.Windows.Media.TranslateTransform.Y%2A> de la <xref:System.Windows.Media.TranslateTransform> aplicado al rectángulo. Hace que el rectángulo se mueva verticalmente a lo largo del trazado.  
  
 [!code-xaml[PathAnimationGallery_snippet#DoubleAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/doubleanimationusingpathexample.xaml#doubleanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/DoubleAnimationUsingPathExample.cs#doubleanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/DoubleAnimationUsingPathExample.vb#doubleanimationusingpathwholepage)]  
  
 Para obtener un ejemplo completo, vea [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).  
  
 Otra manera de mover un objeto utilizando un trazado geométrico es usar un <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> objeto. Para obtener un ejemplo, vea [animar un objeto a lo largo de una ruta de acceso (animación de matriz)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md).  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Temas de procedimientos de animación de trazado](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
