---
title: Procedimiento Animar un objeto Matrix mediante fotogramas clave
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: ff5320fa5b4441ae3e0f414b274ab9118b77ec50
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59336803"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a>Procedimiento Animar un objeto Matrix mediante fotogramas clave
En este ejemplo se muestra cómo animar la <xref:System.Windows.Media.MatrixTransform.Matrix%2A> propiedad de un <xref:System.Windows.Media.MatrixTransform> mediante fotogramas clave.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> clase se va a animar el <xref:System.Windows.Media.MatrixTransform.Matrix%2A> propiedad de un <xref:System.Windows.Media.MatrixTransform>. El ejemplo se usa el <xref:System.Windows.Media.MatrixTransform> objeto para transformar la apariencia y la posición de un <xref:System.Windows.Controls.Button>.  
  
 Esta animación usa el <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> de clases para crear dos fotogramas clave y realiza las siguientes acciones con ellos:  
  
1. Anima el primer <xref:System.Windows.Media.Matrix> durante los primeros 0,2 segundos. El ejemplo se cambia el <xref:System.Windows.Media.Matrix.M11%2A> y <xref:System.Windows.Media.Matrix.M12%2A> propiedades de la <xref:System.Windows.Media.Matrix>. Este cambio hace que el botón Ajustar y se convierten en sesgado. El ejemplo también se cambia el <xref:System.Windows.Media.Matrix.OffsetX%2A> y <xref:System.Windows.Media.Matrix.OffsetY%2A> propiedades para que el botón cambia de posición.  
  
2. Anima el segundo <xref:System.Windows.Media.Matrix> en 1,0 segundo. El botón se mueve a otra posición mientras el botón ya no está sesgado ni ajustado.  
  
3. Se repite la animación indefinidamente.  
  
> [!NOTE]
>  Marcos que se derivan de la clave del <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> objeto crean saltos súbitos entre los valores, es decir, el movimiento de la animación es brusco.  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [Información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md)
- [Temas de procedimientos de fotogramas clave](key-frame-animation-how-to-topics.md)
