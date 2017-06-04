---
title: "C&#243;mo: Animar un giro 3D mediante fotogramas clave (QuaternionAnimationUsingKeyFrames) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "traslaciones 3D, animar, mediante fotogramas clave (QuaternionAnimationUsingKeyFrames)"
  - "animación, traslaciones 3D, mediante fotogramas clave (QuaternionAnimationUsingKeyFrames)"
  - "fotogramas clave, QuaternionAnimationUsingKeyFrames"
ms.assetid: 09e5707b-7523-4a08-9aa7-bb13cbedccdf
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Animar un giro 3D mediante fotogramas clave (QuaternionAnimationUsingKeyFrames)
En el ejemplo siguiente, se utiliza <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> para hacer que gire un objeto 3D.  Esta animación usa los siguiente fotogramas clave:  
  
1.  <xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> se utiliza para crear una interpolación suavizada y lineal entre valores.  
  
2.  <xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> se utiliza para crear "saltos" súbitos entre valores \(sin interpolación\).  
  
3.  <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> se utiliza para crear una transición variable entre valores en función de la propiedad <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A>.  En el ejemplo siguiente, esta parte de la animación se inicia lentamente pero, hacia el final del segmento temporal, se acelera de forma exponencial.  
  
## Ejemplo  
 [!code-xml[Animation3DGallery_snip#QuaternionAnimationUsingKeyFramesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationUsingKeyFramesExample.xaml#quaternionanimationusingkeyframesexamplewholepage)]  
  
## Vea también  
 [Animar un giro 3D mediante Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-storyboards.md)   
 [Animar un giro 3D mediante Rotation3DAnimation](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)   
 [Animar un giro 3D mediante cuaterniones](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-quaternions.md)   
 [Animar un giro 3D mediante fotogramas clave \(Rotation3DAnimationUsingKeyFrames\)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-key-frames.md)   
 [Información general sobre gráficos 3D](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)   
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)