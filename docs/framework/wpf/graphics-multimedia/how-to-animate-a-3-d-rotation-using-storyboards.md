---
title: "C&#243;mo: Animar un giro 3D mediante Storyboards | Microsoft Docs"
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
  - "traslaciones 3D, animar, con guiones gráficos"
  - "animación, traslaciones 3D, con guiones gráficos"
  - "Guiones gráficos"
ms.assetid: 1020e44e-e21e-49a8-be53-53cbc1910e83
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Animar un giro 3D mediante Storyboards
En el ejemplo siguiente se muestra cómo hacer que objeto 3D gire mientras se "tambalea" animando las propiedades <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> y <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> de un objeto <xref:System.Windows.Media.Media3D.AxisAngleRotation3D>.  Este objeto <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> especifica la transformación de giro del objeto 3D y así, animando sus propiedades, crea el efecto de giro deseado.  Dentro del guión gráfico, se utiliza <xref:System.Windows.Media.Animation.DoubleAnimation> para animar la propiedad <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A>, mientras que para animar <xref:System.Windows.Media.Animation.Vector3DAnimation> se utiliza la propiedad <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A>.  
  
## Ejemplo  
 [!code-xml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## Vea también  
 [Animar un giro 3D mediante Rotation3DAnimation](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)   
 [Animar un giro 3D mediante fotogramas clave \(Rotation3DAnimationUsingKeyFrames\)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-key-frames.md)   
 [Información general sobre gráficos 3D](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)   
 [Información general sobre objetos Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)