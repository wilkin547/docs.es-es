---
title: "C&#243;mo: Aplicar un dibujo a un modelo 3D | Microsoft Docs"
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
  - "modelos 3D, aplicar dibujos a"
  - "dibujos, aplicar a modelos 3D"
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Aplicar un dibujo a un modelo 3D
En este ejemplo se muestra cómo utilizar <xref:System.Windows.Media.DrawingBrush> como <xref:System.Windows.Media.Media3D.Material> aplicado a un modelo [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)].  
  
 En el código siguiente se define la propiedad <xref:System.Windows.Media.DrawingGroup> como contenido de <xref:System.Windows.Media.DrawingBrush>.  <xref:System.Windows.Media.DrawingBrush> se establece como la propiedad <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> de <xref:System.Windows.Media.Media3D.DiffuseMaterial> aplicada a un plano [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)].  
  
 **Nota:** con frecuencia, es conveniente definir los objetos y valores complejos, como el dibujo siguiente, como recursos que se pueden reutilizar, a fin de simplificar el código.  Consulte [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md) para obtener más información.  
  
 [!code-xml[3DGallery_snip#ApplyDrawingToMaterialInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]  
  
## Ejemplo  
 En el siguiente código, se muestra todo el ejemplo.  
  
 [!code-xml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]  
  
## Vea también  
 [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [Crear una escena 3D](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)   
 [Información general sobre objetos Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)   
 [Información general sobre gráficos 3D](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)