---
title: "C&#243;mo: Aplicar varias transformaciones a un objeto | Microsoft Docs"
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
  - "gráficos, agrupar objetos Transform"
  - "agrupar objetos Transform"
  - "Transform (objetos), agrupar"
  - "TransformGroup"
ms.assetid: 98cd1921-12bc-4bf5-8193-529228fb7402
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Aplicar varias transformaciones a un objeto
En este ejemplo se muestra cómo usar un objeto <xref:System.Windows.Media.TransformGroup> para agrupar dos o más objetos <xref:System.Windows.Media.Transform> en un único objeto <xref:System.Windows.Media.Transform> compuesto.  
  
## Ejemplo  
 En el ejemplo siguiente se usa <xref:System.Windows.Media.TransformGroup> para aplicar <xref:System.Windows.Media.ScaleTransform> y <xref:System.Windows.Media.RotateTransform> a <xref:System.Windows.Controls.Button>.  
  
 [!code-xml[Transforms_snip#MultipleTransformExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MultipleTransformExample.xaml#multipletransformexamplewholepage)]  
  
 [!code-csharp[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/MultipleTransformsExample.cs#multipletransformscodeexamplewholepage)]
 [!code-vb[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/MultipleTransformsExample.vb#multipletransformscodeexamplewholepage)]  
  
## Vea también  
 <xref:System.Windows.UIElement.RenderTransform%2A>   
 <xref:System.Windows.Media.TransformGroup>   
 [Información general sobre transformaciones](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)   
 [Ejemplo 2\-D Transforms](http://go.microsoft.com/fwlink/?LinkID=158252)