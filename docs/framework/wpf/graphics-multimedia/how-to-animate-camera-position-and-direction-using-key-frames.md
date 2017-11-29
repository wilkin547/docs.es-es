---
title: "Cómo: Animar la posición y la dirección de una cámara mediante fotogramas clave"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], camera direction with key frames
- key frames [WPF], animating camera direction
- animation [WPF], camera position with key frames
- camera position [WPF], animating with key frames
- key frames [WPF], animating camera position
- camera direction [WPF], animating with key frames
ms.assetid: 5753024e-0057-454d-947f-43ea686879c7
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dbac99770b5cbb7dacb0468e1a892956fda6b79c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-camera-position-and-direction-using-key-frames"></a>Cómo: Animar la posición y la dirección de una cámara mediante fotogramas clave
En el ejemplo siguiente, <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> se usa para animar la posición de un <xref:System.Windows.Media.Media3D.PerspectiveCamera> en una escena 3D. Además, <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> se usa para animar la dirección en que apunta la cámara en la escena 3D. En ambas animaciones utilizan varios fotogramas clave que crean una serie de efectos de animación:  
  
1.  <xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame>y <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> se utilizan para crear una interpolación lineal uniforme entre los valores.  
  
2.  <xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame>y <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> se utilizan para crear "saltos" súbitos entre los valores (sin interpolación).  
  
3.  <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame>y <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> se utilizan para crear una transición variable entre los valores según el <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> propiedad. En el ejemplo siguiente, la animación se inicia lentamente, pero hacia el final del segmento de tiempo, acelera exponencialmente.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>Vea también  
 [Animar la posición y la dirección de una cámara en una escena 3D](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-camera-position-and-direction-in-a-3d-scene.md)  
 [Información general sobre gráficos 3D](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
