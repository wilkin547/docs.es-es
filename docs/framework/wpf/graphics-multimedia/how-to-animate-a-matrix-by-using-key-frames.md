---
title: Procedimiento Animar un objeto Matrix mediante fotogramas clave
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: 6aa3e27cdfda7597c9b6acbf2980a2774f2b667b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963023"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a>Procedimiento Animar un objeto Matrix mediante fotogramas clave
En este ejemplo se muestra cómo animar la <xref:System.Windows.Media.MatrixTransform.Matrix%2A> propiedad de una <xref:System.Windows.Media.MatrixTransform> mediante fotogramas clave.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> usa la clase para <xref:System.Windows.Media.MatrixTransform.Matrix%2A> animar la <xref:System.Windows.Media.MatrixTransform>propiedad de un. En el ejemplo se <xref:System.Windows.Media.MatrixTransform> usa el objeto para transformar la apariencia y la <xref:System.Windows.Controls.Button>posición de.  
  
 Esta animación usa la <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> clase para crear dos fotogramas clave y hace lo siguiente con ellos:  
  
1. Anima la primera <xref:System.Windows.Media.Matrix> durante los primeros 0,2 segundos. En el ejemplo se <xref:System.Windows.Media.Matrix.M11%2A> cambian <xref:System.Windows.Media.Matrix.M12%2A> las propiedades y <xref:System.Windows.Media.Matrix>de. Este cambio hace que el botón se estire y se convierta en sesgado. En el ejemplo también se <xref:System.Windows.Media.Matrix.OffsetX%2A> cambian <xref:System.Windows.Media.Matrix.OffsetY%2A> las propiedades y para que el botón cambie de posición.  
  
2. Anima el segundo <xref:System.Windows.Media.Matrix> a 1,0 segundos. El botón se mueve a otra posición mientras el botón deja de sesgarse o ajustarse.  
  
3. Repite la animación indefinidamente.  
  
> [!NOTE]
> Los fotogramas clave que <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> se derivan del objeto crean saltos súbitos entre los valores, es decir, el movimiento de la animación es entrecortado.  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [Información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md)
- [Temas de procedimientos de fotogramas clave](key-frame-animation-how-to-topics.md)
