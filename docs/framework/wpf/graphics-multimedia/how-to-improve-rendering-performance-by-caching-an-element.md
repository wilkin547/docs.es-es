---
title: Procedimiento Mejorar el rendimiento al almacenar en caché un elemento de la representación
ms.date: 03/30/2017
helpviewer_keywords:
- rendering performance [WPF], caching an element
- BitmapCache [WPF], improving rendering performance
- CacheMode [WPF], improving rendering performance
- performance [WPF], caching an element
- UIElement [WPF], caching
ms.assetid: 4739c1fc-60ba-4c46-aba6-f6c1a2688f19
ms.openlocfilehash: b5e39541fdf031b19e9e74483c0de94295e788d7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375238"
---
# <a name="how-to-improve-rendering-performance-by-caching-an-element"></a>Procedimiento Mejorar el rendimiento al almacenar en caché un elemento de la representación
Use la <xref:System.Windows.Media.BitmapCache> clase para mejorar el rendimiento de la representación de un complejo <xref:System.Windows.UIElement>. Para almacenar en caché un elemento, crear una nueva instancia de la <xref:System.Windows.Media.BitmapCache> clase y se asigna a la propiedad del elemento <xref:System.Windows.UIElement.CacheMode%2A> propiedad. Puede volver a usar un <xref:System.Windows.Media.BitmapCache> eficazmente en un <xref:System.Windows.Media.BitmapCacheBrush>.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente muestra cómo crear un elemento complejo y lo almacena en caché como un mapa de bits, lo que mejora el rendimiento cuando se anima el elemento. El elemento es un lienzo que contiene formas geométricas con muchos vértices. Un <xref:System.Windows.Media.BitmapCache> no tiene valor predeterminado se asigna valores a la <xref:System.Windows.UIElement.CacheMode%2A> del lienzo, y una animación muestra la escala sin problemas del mapa de bits almacenado en caché.  
  
 [!code-xaml[System.Windows.Media.BitmapCache#_BitmapCacheXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcache/cs/window1.xaml#_bitmapcachexaml)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Media.BitmapCache>
- <xref:System.Windows.Media.BitmapCacheBrush>
- <xref:System.Windows.UIElement.CacheMode%2A>
- [Cómo: Usar un elemento almacenado en caché como pincel](how-to-use-a-cached-element-as-a-brush.md)
