---
title: "C&#243;mo: Animar la posici&#243;n y la direcci&#243;n de una c&#225;mara en una escena 3D | Microsoft Docs"
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
  - "escenas 3D, animar la dirección de la cámara"
  - "escenas 3D, animar la posición de la cámara"
  - "animación, dirección de la cámara en escenas 3D"
  - "animación, posición de la cámara en escenas 3D"
  - "dirección de la cámara, animar en escenas 3D"
  - "posición de la cámara, animar en escenas 3D"
ms.assetid: 480224b7-a5e5-4165-ba7f-ef760ddff94a
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# C&#243;mo: Animar la posici&#243;n y la direcci&#243;n de una c&#225;mara en una escena 3D
En el ejemplo siguiente se muestra cómo animar la posición de una cámara y animar la dirección en la que apunta en una escena 3D.  Para ello, se utiliza <xref:System.Windows.Media.Animation.Point3DAnimation> y <xref:System.Windows.Media.Animation.Vector3DAnimation> para animar las propiedades <xref:System.Windows.Media.Media3D.ProjectionCamera.Position%2A> y <xref:System.Windows.Media.Media3D.ProjectionCamera.LookDirection%2A>, respectivamente, de <xref:System.Windows.Media.Media3D.PerspectiveCamera>.  Puede utilizar una animación como ésta para cambiar el punto de vista del espectador de una escena en respuesta a un evento.  
  
## Ejemplo  
 [!code-xml[Animation3DGallery_snip#PointVector3DAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationExample.xaml#pointvector3danimationexamplewholepage)]  
  
## Vea también  
 <xref:System.Windows.Media.Animation.Vector3DAnimation>   
 <xref:System.Windows.Media.Animation.Point3DAnimation>   
 [Animar la posición y la dirección de una cámara mediante fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-camera-position-and-direction-using-key-frames.md)   
 [Información general sobre gráficos 3D](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)