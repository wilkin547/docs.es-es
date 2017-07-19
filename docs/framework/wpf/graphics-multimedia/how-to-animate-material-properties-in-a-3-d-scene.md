---
title: "C&#243;mo: Animar propiedades de material en una escena 3D | Microsoft Docs"
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
  - "escenas 3D, animar propiedades de material"
  - "animación, propiedades de material en escenas 3D"
  - "propiedades de material, animar en escenas 3D"
ms.assetid: 229fd6eb-7401-4992-b0c9-8b28de230c0f
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Animar propiedades de material en una escena 3D
En este ejemplo se muestra cómo animar la propiedad <xref:System.Windows.Media.Brush.Opacity%2A> de <xref:System.Windows.Media.Media3D.Material> aplicada a un modelo [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)].  
  
 En el ejemplo de código siguiente se define <xref:System.Windows.Media.LinearGradientBrush> utilizado como el objeto <xref:System.Windows.Media.Media3D.Material> aplicado al objeto 3D.  
  
 [!code-xml[Animation3DGallery_snip#AnimateMaterialExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline1)]  
  
 La propiedad <xref:System.Windows.Media.Brush.Opacity%2A> de este <xref:System.Windows.Media.LinearGradientBrush> se anima mediante el ejemplo de código mostrado a continuación.  
  
 [!code-xml[Animation3DGallery_snip#AnimateMaterialExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline2)]  
  
## Ejemplo  
 En el siguiente código, se muestra todo el ejemplo.  
  
 [!code-xml[Animation3DGallery_snip#AnimateMaterialExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexamplewholepage)]  
  
## Vea también  
 [Crear una escena 3D](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)   
 [Información general sobre gráficos 3D](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)