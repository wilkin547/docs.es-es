---
title: "Cómo: Animar un giro 3D mediante fotogramas clave (QuaternionAnimationUsingKeyFrames)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 3-D translations [WPF], animating [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
- key frames [WPF], QuaternionAnimationUsingKeyFrames
- animation [WPF], 3-D translations [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
ms.assetid: 09e5707b-7523-4a08-9aa7-bb13cbedccdf
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 89719cbcb72c5c24654962e9eb17a540224fd588
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-3-d-rotation-using-key-frames-quaternionanimationusingkeyframes"></a>Cómo: Animar un giro 3D mediante fotogramas clave (QuaternionAnimationUsingKeyFrames)
En el ejemplo siguiente, <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> se usa para hacer girar un objeto 3D. Esta animación usa los fotogramas clave siguientes:  
  
1.  <xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame>se utiliza para crear una interpolación lineal uniforme entre los valores.  
  
2.  <xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame>se utiliza para crear "saltos" súbitos entre los valores (sin interpolación).  
  
3.  <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame>se utiliza para crear una transición variable entre los valores según el <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> propiedad. En el ejemplo siguiente, esta parte de la animación se inicia lentamente, pero hacia el final del segmento de tiempo, acelera exponencialmente.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationUsingKeyFramesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationUsingKeyFramesExample.xaml#quaternionanimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>Vea también  
 [Animar un giro 3D mediante Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-storyboards.md)  
 [Animar un giro 3D mediante Rotation3DAnimation](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)  
 [Animar un giro 3D mediante cuaterniones](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-quaternions.md)  
 [Animar un giro 3D mediante fotogramas clave (Rotation3DAnimationUsingKeyFrames)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-key-frames.md)  
 [Información general sobre gráficos 3D](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)
