---
title: "C&#243;mo: Animar una propiedad sin utilizar un gui&#243;n gr&#225;fico | Microsoft Docs"
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
  - "animación, sin guiones gráficos (local)"
  - "animación local"
  - "animación sin guiones gráficos"
ms.assetid: d411db70-4df7-487d-82bc-95a7c1b2e7f8
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Animar una propiedad sin utilizar un gui&#243;n gr&#225;fico
En este ejemplo se muestra una manera de aplicar una animación a una propiedad sin utilizar un objeto <xref:System.Windows.Media.Animation.Storyboard>.  
  
> [!NOTE]
>  Esta funcionalidad no está disponible en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  Para obtener información sobre cómo animar una propiedad en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], vea [Animar una propiedad utilizando un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).  
  
 Para aplicar una animación local a una propiedad, utilice el método <xref:System.Windows.UIElement.BeginAnimation%2A>.  Este método toma dos parámetros: un objeto <xref:System.Windows.DependencyProperty> que especifica la propiedad para animar, y la animación que se aplicará a esa propiedad.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo animar el ancho y el color de fondo de un objeto <xref:System.Windows.Controls.Button>.  
  
 [!code-cpp[animateproperty#11](../../../../samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
 Existen diversas clases de animación en el espacio de nombres <xref:System.Windows.Media.Animation> para animar diferentes tipos de propiedades.  Para obtener más información sobre la animación de propiedades, vea [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  Para obtener más información sobre las [propiedades de dependencia](GTMT) \(el tipo de propiedades que se muestran en estos ejemplos\) y sus características, vea [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
 Hay otras maneras de animar sin utilizar objetos <xref:System.Windows.Media.Animation.Storyboard>; para obtener más información, vea [Información general sobre técnicas de animación de propiedades](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
## Vea también  
 <xref:System.Windows.Media.Animation.AnimationTimeline>   
 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>   
 <xref:System.Windows.Media.Animation>   
 <xref:System.Windows.Media.Animation.Storyboard>   
 [Información general sobre técnicas de animación de propiedades](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)   
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)