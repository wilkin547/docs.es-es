---
title: "C&#243;mo: Animar traslaciones 3D | Microsoft Docs"
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
  - "traslaciones 3D, animar"
  - "animación, traslaciones 3D"
ms.assetid: d4eece1f-0cd2-4a2c-8370-293354c380e4
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Animar traslaciones 3D
En este tema se muestra cómo animar una transformación de traslación establecida en un modelo [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)].  
  
 En el código siguiente se muestra la aplicación de un objeto <xref:System.Windows.Media.Media3D.TranslateTransform3D> a la propiedad <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> de <xref:System.Windows.Media.Media3D.GeometryModel3D>.  
  
 [!code-xml[Animation3DGallery_snip#Translation3DAnimationInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline1)]  
  
 La propiedad <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> de este objeto <xref:System.Windows.Media.Media3D.TranslateTransform3D> se anima mediante el código que aparece a continuación.  
  
 [!code-xml[Animation3DGallery_snip#Translation3DAnimationInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline2)]  
  
## Ejemplo  
 En el siguiente código, se muestra todo el ejemplo.  
  
 [!code-xml[Animation3DGallery_snip#Translation3DAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationexamplewholepage)]  
  
## Vea también  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Crear una escena 3D](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)   
 [Información general sobre gráficos 3D](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)   
 [Información general sobre transformaciones](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)