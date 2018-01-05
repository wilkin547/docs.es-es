---
title: "Cómo: Animar un giro 3D mediante fotogramas clave"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], 3-D translations [WPF], with key frames (Rotation3DAnimation)
- key frames [WPF], Rotation3DAnimation
- 3-D translations [WPF], animating [WPF], with key frames (Rotation3DAnimation)
ms.assetid: 6f671b95-7f30-4836-9a4f-aeb7dc30121f
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ca1b49277792e89f1d0cc7ca213d02978bb4dee3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-3-d-rotation-using-key-frames"></a>Cómo: Animar un giro 3D mediante fotogramas clave
En el ejemplo siguiente, <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> se usa para hacer girar mientras su eje de rotación anima resultante en una "oscilante" un objeto 3D. Esta animación usa los fotogramas clave siguientes:  
  
1.  <xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame>se utiliza para crear una interpolación lineal uniforme entre los valores.  
  
2.  <xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame>se utiliza para crear "saltos" súbitos entre los valores (sin interpolación).  
  
3.  <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame>se utiliza para crear una transición variable entre los valores según el <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> propiedad. En el ejemplo siguiente, esta parte de la animación se inicia lentamente, pero hacia el final del segmento de tiempo, acelera exponencialmente.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[Animation3DGallery_snip#Rotation3DAnimationUsingKeyFramesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotation3DAnimationUsingKeyFramesExample.xaml#rotation3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre gráficos 3D](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Animar un giro 3D mediante Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-storyboards.md)  
 [Animar un giro 3D mediante Rotation3DAnimation](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)  
 [Animar un giro 3D mediante cuaterniones](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-quaternions.md)  
 [Animar un giro 3D mediante fotogramas clave (QuaternionAnimationUsingKeyFrames)](../../../../docs/framework/wpf/graphics-multimedia/animate-a-3-d-rotation-quaternionanimationusingkeyframes.md)
