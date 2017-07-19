---
title: "C&#243;mo: Aplicar material emisor a un objeto tridimensional | Microsoft Docs"
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
  - "objetos 3D, aplicar EmissiveMaterial"
  - "EmissiveMaterial, aplicar a objetos 3D"
ms.assetid: fd442cc2-5adc-487a-ba70-e45ed54bb3b4
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Aplicar material emisor a un objeto tridimensional
En el ejemplo siguiente se muestra cómo usar <xref:System.Windows.Media.Media3D.EmissiveMaterial> para agregar a un material existente el mismo color que el pincel de EmissiveMaterial.  En el código siguiente se muestra <xref:System.Windows.Media.Media3D.DiffuseMaterial> y <xref:System.Windows.Media.Media3D.EmissiveMaterial> aplicados en combinación para agregar el color azul a la apariencia de DiffuseMaterial.  
  
 [!code-xml[3DGallery_snip#EmmisiveMaterialAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emmisivematerialanimationexampleinline1)]  
  
 En código de procedimientos:  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexampleinline1)]  
  
## Ejemplo  
 El código siguiente muestra el ejemplo completo en XAML.  
  
 [!code-xml[3DGallery_snip#EmissiveMaterialExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emissivematerialexamplewholepage)]  
  
## Ejemplo  
 A continuación se muestra el ejemplo completo en código de procedimientos.  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexamplewholepage)]  
  
## Vea también  
 [Crear una escena 3D](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)   
 [Información general sobre gráficos 3D](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)   
 [Animar propiedades de material en una escena 3D](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-material-properties-in-a-3-d-scene.md)   
 [Aplicar material a la parte anterior y posterior de un objeto 3D](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-material-to-the-front-and-back-of-a-3-d-object.md)