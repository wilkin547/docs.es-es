---
title: "C&#243;mo: Hacer que un elemento gire en su posici&#243;n | Microsoft Docs"
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
  - "clases, DoubleAnimation"
  - "clases, RotateTransform"
  - "DoubleAnimation (clase)"
  - "gráficos, girar elementos"
  - "RotateTransform (clase)"
  - "girar elementos"
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Hacer que un elemento gire en su posici&#243;n
En este ejemplo se muestra cómo hacer girar un elemento mediante una clase <xref:System.Windows.Media.RotateTransform> y una clase <xref:System.Windows.Media.Animation.DoubleAnimation>.  
  
 En el ejemplo siguiente se aplica <xref:System.Windows.Media.RotateTransform> a la propiedad <xref:System.Windows.UIElement.RenderTransform%2A> del elemento.  En el ejemplo se utiliza <xref:System.Windows.Media.Animation.DoubleAnimation> para animar la propiedad <xref:System.Windows.Media.RotateTransform.Angle%2A> de <xref:System.Windows.Media.RotateTransform>.  Para hacer que el elemento gire en su posición, en el ejemplo se establece la propiedad <xref:System.Windows.UIElement.RenderTransformOrigin%2A> del elemento en el punto \(0,5, 0,5\).  
  
## Ejemplo  
 [!code-xml[transformanimations_snip#11](../../../../samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 Para obtener el ejemplo completo, que incluye más ejemplos de transformaciones, vea [2\-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).  
  
## Vea también  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Información general sobre transformaciones](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)