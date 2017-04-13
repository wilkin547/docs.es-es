---
title: "C&#243;mo: Usar un elemento almacenado en cach&#233; como pincel | Microsoft Docs"
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
  - "BitmapCache [WPF], utilizar"
  - "BitmapCacheBrush [WPF], utilizar"
  - "elemento en caché [WPF], usar como pincel"
  - "CacheMode [WPF], utilizar"
ms.assetid: d36e944a-866e-4baf-98c4-fd6a75f6fdd0
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Usar un elemento almacenado en cach&#233; como pincel
Use la clase <xref:System.Windows.Media.BitmapCacheBrush> para reutilizar eficazmente un elemento almacenado en caché.  Para almacenar en caché un elemento, cree una nueva instancia de la clase <xref:System.Windows.Media.BitmapCache> y asígnela a la propiedad <xref:System.Windows.UIElement.CacheMode%2A> del elemento.  
  
## Ejemplo  
 En el siguiente ejemplo de código se muestra cómo reutilizar un elemento almacenado en caché.  El elemento almacenado en caché es un control <xref:System.Windows.Controls.Image> que muestra una imagen grande.  El control <xref:System.Windows.Controls.Image> se almacena en caché como un mapa de bits mediante la clase <xref:System.Windows.Media.BitmapCache>, y la memoria caché se reutiliza mediante su asignación a <xref:System.Windows.Media.BitmapCacheBrush>.  El pincel se asigna al fondo de veinticinco botones para mostrar una reutilización eficaz.  
  
 [!code-xml[System.Windows.Media.BitmapCacheBrush#_BitmapCacheBrushXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcachebrush/cs/window1.xaml#_bitmapcachebrushxaml)]  
  
## Vea también  
 <xref:System.Windows.Media.BitmapCache>   
 <xref:System.Windows.Media.BitmapCacheBrush>   
 <xref:System.Windows.UIElement.CacheMode%2A>   
 [Cómo: Mejorar el rendimiento de la representación mediante el almacenamiento en caché de un elemento](../../../../docs/framework/wpf/graphics-multimedia/how-to-improve-rendering-performance-by-caching-an-element.md)