---
title: 'Cómo: Animar un objeto Matrix mediante fotogramas clave'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: eb596cf728f8a7cc1964963b8509f42bdd7a392a
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344914"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a>Cómo: Animar un objeto Matrix mediante fotogramas clave
En este ejemplo se <xref:System.Windows.Media.MatrixTransform.Matrix%2A> muestra <xref:System.Windows.Media.MatrixTransform> cómo animar la propiedad de a mediante fotogramas clave.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> siguiente se <xref:System.Windows.Media.MatrixTransform.Matrix%2A> utiliza <xref:System.Windows.Media.MatrixTransform>la clase para animar la propiedad de un archivo . En el <xref:System.Windows.Media.MatrixTransform> ejemplo se utiliza el objeto <xref:System.Windows.Controls.Button>para transformar la apariencia y la posición de un archivo .  
  
 Esta animación <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> utiliza la clase para crear dos fotogramas clave y hace lo siguiente con ellos:  
  
1. Anima el <xref:System.Windows.Media.Matrix> primero durante los primeros 0,2 segundos. En el <xref:System.Windows.Media.Matrix.M11%2A> ejemplo <xref:System.Windows.Media.Matrix.M12%2A> se <xref:System.Windows.Media.Matrix>cambia el y las propiedades del archivo . Este cambio hace que el botón se estire y se vuelva sesgado. El ejemplo también <xref:System.Windows.Media.Matrix.OffsetX%2A> <xref:System.Windows.Media.Matrix.OffsetY%2A> cambia las propiedades y para que el botón cambie de posición.  
  
2. Anima el <xref:System.Windows.Media.Matrix> segundo a 1,0 segundos. El botón se mueve a otra posición mientras el botón ya no está sesgado o estirado.  
  
3. Repite la animación indefinidamente.  
  
> [!NOTE]
> Los fotogramas clave <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> que derivan del objeto crean saltos repentinos entre los valores, es decir, el movimiento de la animación es brusco.  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [Información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md)
- [Temas de procedimientos de fotogramas clave](key-frame-animation-how-to-topics.md)
