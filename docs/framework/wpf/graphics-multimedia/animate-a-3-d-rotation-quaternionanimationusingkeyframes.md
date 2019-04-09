---
title: Filtrar Animar un giro 3D mediante fotogramas clave (QuaternionAnimationUsingKeyFrames)
ms.date: 03/30/2017
helpviewer_keywords:
- 3-D translations [WPF], animating [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
- key frames [WPF], QuaternionAnimationUsingKeyFrames
- animation [WPF], 3-D translations [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
ms.assetid: 09e5707b-7523-4a08-9aa7-bb13cbedccdf
ms.openlocfilehash: f0b46e488f5f0ff0a918d7766998528fef001794
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59100111"
---
# <a name="how-to-animate-a-3-d-rotation-using-key-frames-quaternionanimationusingkeyframes"></a>Filtrar Animar un giro 3D mediante fotogramas clave (QuaternionAnimationUsingKeyFrames)
En el ejemplo siguiente, <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> se usa para hacer girar un objeto 3D. Esta animación usa los fotogramas clave siguientes:  
  
1.  <xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> se usa para crear una interpolación lineal suave entre valores.  
  
2.  <xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> se usa para crear "saltos" súbitos entre los valores (sin interpolación).  
  
3.  <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> se utiliza para crear una transición variable entre los valores según el <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> propiedad. En el ejemplo siguiente, esta parte de la animación se inicia lentamente, pero hacia el final del segmento temporal, se acelera exponencialmente.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationUsingKeyFramesExample.xaml#quaternionanimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>Vea también

- [Animar un giro 3D mediante Storyboards](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [Animar un giro 3D mediante Rotation3DAnimation](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [Animar un giro 3D mediante cuaterniones](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [Animar un giro 3D mediante fotogramas clave (Rotation3DAnimationUsingKeyFrames)](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [Información general sobre gráficos 3D](3-d-graphics-overview.md)
- [Información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md)
