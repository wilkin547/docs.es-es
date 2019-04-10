---
title: Filtrar para usar un elemento almacenado en caché como pincel
ms.date: 03/30/2017
helpviewer_keywords:
- BitmapCache [WPF], using
- cached element [WPF], use as a brush
- BitmapCacheBrush [WPF], using
- CacheMode [WPF], using
ms.assetid: d36e944a-866e-4baf-98c4-fd6a75f6fdd0
ms.openlocfilehash: 78df242c7f00b69e36ea4ab6751f51509d9e2220
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229373"
---
# <a name="how-to-use-a-cached-element-as-a-brush"></a>Filtrar para usar un elemento almacenado en caché como pincel
Use la <xref:System.Windows.Media.BitmapCacheBrush> clase para reutilizar un elemento almacenado en caché eficazmente. Para almacenar en caché un elemento, crear una nueva instancia de la <xref:System.Windows.Media.BitmapCache> clase y se asigna a la propiedad del elemento <xref:System.Windows.UIElement.CacheMode%2A> propiedad.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente muestra cómo reutilizar un elemento almacenado en caché. El elemento almacenado en caché es un <xref:System.Windows.Controls.Image> control que muestra una imagen grande. El <xref:System.Windows.Controls.Image> control se almacena en caché como un mapa de bits mediante el uso de la <xref:System.Windows.Media.BitmapCache> clase y la memoria caché se reutiliza mediante la asignación a un <xref:System.Windows.Media.BitmapCacheBrush>. El pincel se asigna al fondo de veinticinco botones para mostrar una reutilización eficiente.  
  
 [!code-xaml[System.Windows.Media.BitmapCacheBrush#_BitmapCacheBrushXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcachebrush/cs/window1.xaml#_bitmapcachebrushxaml)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.BitmapCache>
- <xref:System.Windows.Media.BitmapCacheBrush>
- <xref:System.Windows.UIElement.CacheMode%2A>
- [Filtrar para mejorar el rendimiento de la representación mediante el almacenamiento en caché de un elemento](how-to-improve-rendering-performance-by-caching-an-element.md)
