---
title: "C&#243;mo: Aplicar material a la parte anterior y posterior de un objeto 3D | Microsoft Docs"
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
  - "objetos 3D, aplicar la clase Material"
  - "clases, Material"
  - "Material (clase), aplicar a ambas caras de un objeto 3D"
ms.assetid: d93c8ad6-4939-4d29-9544-4d16d98093c1
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Aplicar material a la parte anterior y posterior de un objeto 3D
En el ejemplo siguiente se muestra cómo aplicar un objeto <xref:System.Windows.Media.Media3D.Material> a la parte anterior y posterior de un objeto 3D y animar el objeto para mostrar ambos lados del mismo.  Se utiliza la propiedad <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> de un objeto <xref:System.Windows.Media.Media3D.GeometryModel3D> para aplicar un objeto <xref:System.Windows.Media.Brush> rojo a la parte anterior del objeto, y la propiedad <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> del objeto <xref:System.Windows.Media.Media3D.GeometryModel3D> para aplicar un objeto <xref:System.Windows.Media.Brush> azul a la parte posterior del objeto.  En el código siguiente se muestra la aplicación de los materiales al objeto:  
  
 [!code-xml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## Ejemplo  
 En el siguiente código, se muestra todo el ejemplo.  
  
 [!code-xml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## Vea también  
 [Crear una escena 3D](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)   
 [Información general sobre gráficos 3D](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)   
 [Animar propiedades de material en una escena 3D](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-material-properties-in-a-3-d-scene.md)   
 [Aplicar material emisor a un objeto tridimensional](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-emissive-material-to-a-3-d-object.md)