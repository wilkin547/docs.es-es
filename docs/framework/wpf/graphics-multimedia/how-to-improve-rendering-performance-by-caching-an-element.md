---
title: "C&#243;mo: Mejorar el rendimiento de la representaci&#243;n mediante el almacenamiento en cach&#233; de un elemento | Microsoft Docs"
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
  - "BitmapCache [WPF], mejorar el rendimiento de la representación"
  - "CacheMode [WPF], mejorar el rendimiento de la representación"
  - "rendimiento [WPF], almacenar en caché un elemento"
  - "rendimiento de la representación [WPF], almacenar en caché un elemento"
  - "UIElement [WPF], almacenar en caché"
ms.assetid: 4739c1fc-60ba-4c46-aba6-f6c1a2688f19
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Mejorar el rendimiento de la representaci&#243;n mediante el almacenamiento en cach&#233; de un elemento
Use la clase <xref:System.Windows.Media.BitmapCache> para mejorar el rendimiento de la representación de un objeto <xref:System.Windows.UIElement> complejo.  Para almacenar en caché un elemento, cree una nueva instancia de la clase <xref:System.Windows.Media.BitmapCache> y asígnela a la propiedad <xref:System.Windows.UIElement.CacheMode%2A> del elemento.  Puede reutilizar eficazmente una clase <xref:System.Windows.Media.BitmapCache> en <xref:System.Windows.Media.BitmapCacheBrush>.  
  
## Ejemplo  
 En el siguiente ejemplo de código se muestra cómo crear un elemento complejo y almacenarlo en caché como un mapa de bits, que mejora el rendimiento cuando se anima el elemento.  El elemento es un lienzo que contiene formas geométricas con muchos vértices.  Se asigna una clase <xref:System.Windows.Media.BitmapCache> con valores predeterminados a la propiedad <xref:System.Windows.UIElement.CacheMode%2A> del lienzo y una animación muestra el ajuste de escala suavizado del mapa de bits almacenado en caché.  
  
 [!code-xml[System.Windows.Media.BitmapCache#_BitmapCacheXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcache/cs/window1.xaml#_bitmapcachexaml)]  
  
## Vea también  
 <xref:System.Windows.Media.BitmapCache>   
 <xref:System.Windows.Media.BitmapCacheBrush>   
 <xref:System.Windows.UIElement.CacheMode%2A>   
 [Cómo: Usar un elemento almacenado en caché como pincel](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-a-cached-element-as-a-brush.md)