---
title: "Cómo: Mejorar el rendimiento de la representación mediante el almacenamiento en caché de un elemento"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- rendering performance [WPF], caching an element
- BitmapCache [WPF], improving rendering performance
- CacheMode [WPF], improving rendering performance
- performance [WPF], caching an element
- UIElement [WPF], caching
ms.assetid: 4739c1fc-60ba-4c46-aba6-f6c1a2688f19
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9cd12b811ae4dd89c645ada1f4f70b06f73b9b13
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-improve-rendering-performance-by-caching-an-element"></a><span data-ttu-id="78792-102">Cómo: Mejorar el rendimiento de la representación mediante el almacenamiento en caché de un elemento</span><span class="sxs-lookup"><span data-stu-id="78792-102">How to: Improve Rendering Performance by Caching an Element</span></span>
<span data-ttu-id="78792-103">Use la <xref:System.Windows.Media.BitmapCache> clase para mejorar el rendimiento de la representación de un complejo <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="78792-103">Use the <xref:System.Windows.Media.BitmapCache> class to improve rendering performance of a complex <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="78792-104">Para almacenar en caché un elemento, crear una nueva instancia de la <xref:System.Windows.Media.BitmapCache> clase y asígnelo al elemento <xref:System.Windows.UIElement.CacheMode%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="78792-104">To cache an element, create a new instance of the <xref:System.Windows.Media.BitmapCache> class and assign it to the element's <xref:System.Windows.UIElement.CacheMode%2A> property.</span></span> <span data-ttu-id="78792-105">Puede volver a usar un <xref:System.Windows.Media.BitmapCache> eficazmente en un <xref:System.Windows.Media.BitmapCacheBrush>.</span><span class="sxs-lookup"><span data-stu-id="78792-105">You can reuse a <xref:System.Windows.Media.BitmapCache> efficiently in a <xref:System.Windows.Media.BitmapCacheBrush>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78792-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="78792-106">Example</span></span>  
 <span data-ttu-id="78792-107">En el ejemplo de código siguiente se muestra cómo crear un elemento complejo y almacenarlo en caché como un mapa de bits, lo que mejora el rendimiento cuando se anima el elemento.</span><span class="sxs-lookup"><span data-stu-id="78792-107">The following code example shows how to create a complex element and cache it as a bitmap, which improves performance when the element is animated.</span></span> <span data-ttu-id="78792-108">El elemento es un lienzo que contiene formas geométricas con muchos vértices.</span><span class="sxs-lookup"><span data-stu-id="78792-108">The element is a canvas that holds shape geometries with many vertices.</span></span> <span data-ttu-id="78792-109">A <xref:System.Windows.Media.BitmapCache> no tiene valor predeterminado se asigna valores a las <xref:System.Windows.UIElement.CacheMode%2A> del lienzo, y una animación muestra el ajuste de escala suavizado del mapa de bits almacenado en caché.</span><span class="sxs-lookup"><span data-stu-id="78792-109">A <xref:System.Windows.Media.BitmapCache> with default values is assigned to the <xref:System.Windows.UIElement.CacheMode%2A> of the canvas, and an animation shows the smooth scaling of the cached bitmap.</span></span>  
  
 [!code-xaml[System.Windows.Media.BitmapCache#_BitmapCacheXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcache/cs/window1.xaml#_bitmapcachexaml)]  
  
## <a name="see-also"></a><span data-ttu-id="78792-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="78792-110">See Also</span></span>  
 <xref:System.Windows.Media.BitmapCache>  
 <xref:System.Windows.Media.BitmapCacheBrush>  
 <xref:System.Windows.UIElement.CacheMode%2A>  
 [<span data-ttu-id="78792-111">Usar un elemento almacenado en caché como pincel</span><span class="sxs-lookup"><span data-stu-id="78792-111">How to: Use a Cached Element as a Brush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-a-cached-element-as-a-brush.md)
