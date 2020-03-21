---
title: 'Cómo: Animar una rotación 3D mediante fotogramas clave (QuaternionAnimationUsingKeyFrames)'
ms.date: 03/30/2017
helpviewer_keywords:
- 3D translations [WPF], animating [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
- key frames [WPF], QuaternionAnimationUsingKeyFrames
- animation [WPF], 3D translations [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
ms.assetid: 09e5707b-7523-4a08-9aa7-bb13cbedccdf
ms.openlocfilehash: 5273183aaa49a743cc401dec0b4b16bae09e3129
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112302"
---
# <a name="how-to-animate-a-3d-rotation-using-key-frames-quaternionanimationusingkeyframes"></a>Cómo: Animar una rotación 3D mediante fotogramas clave (QuaternionAnimationUsingKeyFrames)
En el ejemplo <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> siguiente, se utiliza para hacer que un objeto 3D gire. Esta animación utiliza los siguientes fotogramas clave:  
  
1. <xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame>se utiliza para crear una interpolación lineal suave entre los valores.  
  
2. <xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame>se utiliza para crear "saltos" repentinos entre los valores (sin interpolación).  
  
3. <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame>se utiliza para crear una transición <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> variable entre valores dependiendo de la propiedad. En el ejemplo siguiente, esta parte de la animación comienza lentamente, pero hacia el final del segmento de tiempo, se acelera exponencialmente.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationUsingKeyFramesExample.xaml#quaternionanimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>Consulte también

- [Animar una rotación 3D mediante guiones gráficos](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [Animar una rotación 3D mediante Rotation3DAnimation](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [Animar una rotación 3D con cuaterniones](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [Animar una rotación 3D mediante fotogramas clave (Rotation3DAnimationUsingKeyFrames)](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [Descripción general de los gráficos 3D](3-d-graphics-overview.md)
- [Información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md)
