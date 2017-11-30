---
title: "Cómo: Usar un elemento almacenado en caché como pincel"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BitmapCache [WPF], using
- cached element [WPF], use as a brush
- BitmapCacheBrush [WPF], using
- CacheMode [WPF], using
ms.assetid: d36e944a-866e-4baf-98c4-fd6a75f6fdd0
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4d0f0c60e9df6a1ec816b1f9cf5769c93b382ae5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-cached-element-as-a-brush"></a>Cómo: Usar un elemento almacenado en caché como pincel
Use la <xref:System.Windows.Media.BitmapCacheBrush> clase para reutilizar un elemento almacenado en caché de forma eficaz. Para almacenar en caché un elemento, crear una nueva instancia de la <xref:System.Windows.Media.BitmapCache> clase y asígnelo al elemento <xref:System.Windows.UIElement.CacheMode%2A> propiedad.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se muestra cómo reutilizar un elemento almacenado en caché. El elemento almacenado en caché es una <xref:System.Windows.Controls.Image> control que muestra una imagen grande. El <xref:System.Windows.Controls.Image> control se almacena en caché como un mapa de bits mediante el uso de la <xref:System.Windows.Media.BitmapCache> clase y la memoria caché se reutiliza asignándolo a una <xref:System.Windows.Media.BitmapCacheBrush>. El pincel se asigna al fondo de veinticinco botones para mostrar una reutilización eficaz.  
  
 [!code-xaml[System.Windows.Media.BitmapCacheBrush#_BitmapCacheBrushXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcachebrush/cs/window1.xaml#_bitmapcachebrushxaml)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.BitmapCache>  
 <xref:System.Windows.Media.BitmapCacheBrush>  
 <xref:System.Windows.UIElement.CacheMode%2A>  
 [Mejorar el rendimiento de la representación mediante el almacenamiento en caché de un elemento](../../../../docs/framework/wpf/graphics-multimedia/how-to-improve-rendering-performance-by-caching-an-element.md)
