---
title: "C&#243;mo: Animar un giro 3D mediante cuaterniones | Microsoft Docs"
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
  - "traslaciones 3D, animar, con cuaterniones"
  - "animación, traslaciones 3D, con cuaterniones"
  - "cuaterniones"
ms.assetid: adca9cb1-066b-4de8-abbb-6b4007579ee7
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Animar un giro 3D mediante cuaterniones
En este ejemplo se muestra cómo animar un giro de un objeto 3D utilizando cuaterniones.  
  
 En el código siguiente se muestra el objeto <xref:System.Windows.Media.Media3D.QuaternionRotation3D> utilizado como valor de la propiedad <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> de una transformación <xref:System.Windows.Media.Media3D.RotateTransform3D>.  
  
 [!code-xml[Animation3DGallery_snip#QuaternionAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline1)]  
  
 <xref:System.Windows.Media.Media3D.QuaternionRotation3D> se anima con <xref:System.Windows.Media.Animation.QuaternionAnimation> dentro de <xref:System.Windows.Media.Animation.Storyboard> mediante el código mostrado a continuación.  
  
 [!code-xml[Animation3DGallery_snip#QuaternionAnimationExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline2)]  
  
## Ejemplo  
 En el siguiente código, se muestra todo el ejemplo.  
  
 [!code-xml[Animation3DGallery_snip#QuaternionAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexamplewholepage)]  
  
## Vea también  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Crear una escena 3D](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)   
 [Información general sobre gráficos 3D](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)   
 [Información general sobre transformaciones](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)   
 [Animar un giro 3D mediante Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-storyboards.md)   
 [Animar un giro 3D mediante Rotation3DAnimation](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)