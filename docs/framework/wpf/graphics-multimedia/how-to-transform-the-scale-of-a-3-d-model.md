---
title: "C&#243;mo: Transformar la escala de un modelo 3D | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "objetos 3D, ajustar la escala"
  - "ajustar la escala, objetos 3D"
ms.assetid: f3fdfe33-f7dc-44b0-84a5-e43b89947f35
caps.latest.revision: 3
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 3
---
# C&#243;mo: Transformar la escala de un modelo 3D
En este ejemplo se muestra cómo ajustar la escala de un objeto 3D.  Para ajustar la escala de un objeto 3D, se utiliza una transformación <xref:System.Windows.Media.Media3D.ScaleTransform3D>.  Las propiedades <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> y <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> cambian el tamaño del elemento según el factor especificado.  Por ejemplo, un valor de <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> de 1,5 expande un objeto al 150 por ciento de su ancho original.  Un valor de <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> de 0,5 reduce el alto de un objeto a la mitad.  En el código siguiente se muestra cómo utilizar <xref:System.Windows.Media.Media3D.ScaleTransform3D> como transformación para un objeto <xref:System.Windows.Media.Media3D.GeometryModel3D>.  
  
 [!code-xml[3DGallery_snip#ScaleTransform3DExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexampleinline1)]  
  
## Ejemplo  
 En el siguiente código, se muestra todo el ejemplo.  
  
 [!code-xml[3DGallery_snip#ScaleTransform3DExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexamplewholepage)]  
  
## Vea también  
 [Animar traslaciones 3D](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-3-d-translations.md)   
 [Crear una escena 3D](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)   
 [Información general sobre gráficos 3D](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)