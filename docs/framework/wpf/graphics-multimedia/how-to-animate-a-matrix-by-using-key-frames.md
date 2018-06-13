---
title: 'Cómo: Animar un objeto Matrix mediante fotogramas clave'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: edb7074dffab23810872f4347f5339270af86bd1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557022"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a>Cómo: Animar un objeto Matrix mediante fotogramas clave
Este ejemplo muestra cómo animar la <xref:System.Windows.Media.MatrixTransform.Matrix%2A> propiedad de un <xref:System.Windows.Media.MatrixTransform> mediante el uso de fotogramas clave.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> clase para animar la <xref:System.Windows.Media.MatrixTransform.Matrix%2A> propiedad de un <xref:System.Windows.Media.MatrixTransform>. El ejemplo se utiliza la <xref:System.Windows.Media.MatrixTransform> objeto que se va a transformar el aspecto y la posición de un <xref:System.Windows.Controls.Button>.  
  
 Esta animación usa la <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> clase para crear dos fotogramas clave y realiza las siguientes acciones con ellos:  
  
1.  Anima el primer <xref:System.Windows.Media.Matrix> durante los primeros 0,2 segundos. El ejemplo se cambia el <xref:System.Windows.Media.Matrix.M11%2A> y <xref:System.Windows.Media.Matrix.M12%2A> propiedades de la <xref:System.Windows.Media.Matrix>. Este cambio hace que el botón Ajustar y se convierten en sesgado. El ejemplo también se cambia el <xref:System.Windows.Media.Matrix.OffsetX%2A> y <xref:System.Windows.Media.Matrix.OffsetY%2A> propiedades para que el botón cambia de posición.  
  
2.  Anima el segundo <xref:System.Windows.Media.Matrix> en 1,0 segundo. El botón se mueve a otra posición mientras el botón ya no está sesgado ni ajustado.  
  
3.  Repite indefinidamente la animación.  
  
> [!NOTE]
>  Marcos que se derivan de la clave del <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> objeto crean saltos súbitos entre valores, es decir, el movimiento de la animación es irregular.  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.MatrixTransform.Matrix%2A>  
 <xref:System.Windows.Media.MatrixTransform>  
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Temas de procedimientos de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
