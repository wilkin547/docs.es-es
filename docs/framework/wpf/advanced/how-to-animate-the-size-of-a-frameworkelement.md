---
title: "C&#243;mo: Animar el tama&#241;o de un elemento FrameworkElement | Microsoft Docs"
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
  - "animación, tamaño de FrameworkElement"
  - "FrameworkElement, animar el tamaño de"
ms.assetid: d4cd5a13-c20d-4a6f-a2ba-14f2c9ce4cef
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Animar el tama&#241;o de un elemento FrameworkElement
Para animar el tamaño de un elemento <xref:System.Windows.FrameworkElement>, puede animar sus propiedades <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> o bien utilizar un objeto <xref:System.Windows.Media.ScaleTransform> animado.  
  
 En el ejemplo siguiente se anima el tamaño de dos botones utilizando estos dos enfoques.  El tamaño de un botón se cambia animando su propiedad <xref:System.Windows.FrameworkElement.Width%2A> y el tamaño del otro se cambia animando un objeto <xref:System.Windows.Media.ScaleTransform> aplicado a su propiedad <xref:System.Windows.UIElement.RenderTransform%2A>.  Cada botón contiene texto.  Inicialmente, el texto tiene el mismo aspecto en ambos botones, pero al cambiar el tamaño de los botones, el texto del segundo botón se distorsiona.  
  
## Ejemplo  
 [!code-xml[transformanimations_snip#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/AnimatingSizeExample.xaml#1)]  
  
 Al transformar un elemento, se transforma el elemento completo y su contenido.  Al modificar directamente el tamaño de un elemento, como en el caso del primer botón, el contenido del elemento no cambia de tamaño a no ser que su tamaño y posición dependan del tamaño de su elemento primario.  
  
 Al animar el tamaño de un elemento aplicando una transformación animada a su propiedad <xref:System.Windows.UIElement.RenderTransform%2A> se obtiene un rendimiento mejor que al animar sus propiedades <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> directamente, porque la propiedad <xref:System.Windows.UIElement.RenderTransform%2A> no activa un paso de diseño.  
  
 Para obtener más información sobre la animación de propiedades, vea [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  Para obtener más información acerca de las transformaciones, vea [Información general sobre transformaciones](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).