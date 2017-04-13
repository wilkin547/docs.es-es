---
title: "C&#243;mo: Animar la posici&#243;n y la direcci&#243;n de una c&#225;mara mediante fotogramas clave | Microsoft Docs"
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
  - "animación, dirección de la cámara con fotogramas clave"
  - "animación, posición de la cámara con fotogramas clave"
  - "dirección de la cámara, animar con fotogramas clave"
  - "posición de la cámara, animar con fotogramas clave"
  - "fotogramas clave, animar la dirección de la cámara"
  - "fotogramas clave, animar la posición de la cámara"
ms.assetid: 5753024e-0057-454d-947f-43ea686879c7
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Animar la posici&#243;n y la direcci&#243;n de una c&#225;mara mediante fotogramas clave
En el ejemplo siguiente, se utiliza <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> para animar la posición de <xref:System.Windows.Media.Media3D.PerspectiveCamera> en una escena 3D.  Además, se utiliza <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> para animar la dirección en que apunta la cámara en la escena 3D.  En ambas animaciones se utilizan varios fotogramas clave que crean una serie de efectos de animación:  
  
1.  <xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame> y <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> se utilizan para crear una interpolación suavizada y lineal entre valores.  
  
2.  <xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame> y <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> se utilizan para crear "saltos" súbitos entre valores \(sin interpolación\).  
  
3.  <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> y <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> se utilizan para crear una transición variable entre valores en función de la propiedad <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame>.  En el ejemplo siguiente, la animación se inicia lentamente, pero se va acelerando de forma exponencial a medida que avanza hacia el final del segmento temporal.  
  
## Ejemplo  
 [!code-xml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## Vea también  
 [Animar la posición y la dirección de una cámara en una escena 3D](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-camera-position-and-direction-in-a-3d-scene.md)   
 [Información general sobre gráficos 3D](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)