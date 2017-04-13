---
title: "C&#243;mo: Animar un giro 3D mediante fotogramas clave | Microsoft Docs"
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
  - "traslaciones 3D, animar, con fotogramas clave (Rotation3DAnimation)"
  - "animación, traslaciones 3D, con fotogramas clave (Rotation3DAnimation)"
  - "fotogramas clave, Rotation3DAnimation"
ms.assetid: 6f671b95-7f30-4836-9a4f-aeb7dc30121f
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Animar un giro 3D mediante fotogramas clave
En el ejemplo siguiente, se utiliza <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> para hacer girar un objeto 3D con un eje de giro animado de modo que se "tambalea".  Esta animación usa los siguiente fotogramas clave:  
  
1.  <xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> se utiliza para crear una interpolación suavizada y lineal entre valores.  
  
2.  <xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> se utiliza para crear "saltos" súbitos entre valores \(sin interpolación\).  
  
3.  <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> se utiliza para crear una transición variable entre valores en función de la propiedad <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A>.  En el ejemplo siguiente, esta parte de la animación se inicia lentamente pero, hacia el final del segmento temporal, se acelera de forma exponencial.  
  
## Ejemplo  
 [!code-xml[Animation3DGallery_snip#Rotation3DAnimationUsingKeyFramesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotation3DAnimationUsingKeyFramesExample.xaml#rotation3danimationusingkeyframesexamplewholepage)]  
  
## Vea también  
 [Información general sobre gráficos 3D](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)   
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Animar un giro 3D mediante Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-storyboards.md)   
 [Animar un giro 3D mediante Rotation3DAnimation](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)   
 [Animar un giro 3D mediante cuaterniones](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-quaternions.md)   
 [Animar un giro 3D mediante fotogramas clave \(QuaternionAnimationUsingKeyFrames\)](../../../../docs/framework/wpf/graphics-multimedia/animate-a-3-d-rotation-quaternionanimationusingkeyframes.md)