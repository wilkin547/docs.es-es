---
title: Filtrar Usar un elemento almacenado en caché como pincel
ms.date: 03/30/2017
helpviewer_keywords:
- BitmapCache [WPF], using
- cached element [WPF], use as a brush
- BitmapCacheBrush [WPF], using
- CacheMode [WPF], using
ms.assetid: d36e944a-866e-4baf-98c4-fd6a75f6fdd0
ms.openlocfilehash: 008bec87390a807ae2b4797af8b86aaf59c92ef5
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372495"
---
# <a name="how-to-use-a-cached-element-as-a-brush"></a><span data-ttu-id="d1c34-102">Procedimiento Usar un elemento almacenado en caché como pincel</span><span class="sxs-lookup"><span data-stu-id="d1c34-102">How to: Use a Cached Element as a Brush</span></span>
<span data-ttu-id="d1c34-103">Use la <xref:System.Windows.Media.BitmapCacheBrush> clase para reutilizar un elemento almacenado en caché eficazmente.</span><span class="sxs-lookup"><span data-stu-id="d1c34-103">Use the <xref:System.Windows.Media.BitmapCacheBrush> class to reuse a cached element efficiently.</span></span> <span data-ttu-id="d1c34-104">Para almacenar en caché un elemento, crear una nueva instancia de la <xref:System.Windows.Media.BitmapCache> clase y se asigna a la propiedad del elemento <xref:System.Windows.UIElement.CacheMode%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="d1c34-104">To cache an element, create a new instance of the <xref:System.Windows.Media.BitmapCache> class and assign it to the element's <xref:System.Windows.UIElement.CacheMode%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1c34-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d1c34-105">Example</span></span>  
 <span data-ttu-id="d1c34-106">El ejemplo de código siguiente muestra cómo reutilizar un elemento almacenado en caché.</span><span class="sxs-lookup"><span data-stu-id="d1c34-106">The following code example shows how to reuse a cached element.</span></span> <span data-ttu-id="d1c34-107">El elemento almacenado en caché es un <xref:System.Windows.Controls.Image> control que muestra una imagen grande.</span><span class="sxs-lookup"><span data-stu-id="d1c34-107">The cached element is an <xref:System.Windows.Controls.Image> control that displays a large image.</span></span> <span data-ttu-id="d1c34-108">El <xref:System.Windows.Controls.Image> control se almacena en caché como un mapa de bits mediante el uso de la <xref:System.Windows.Media.BitmapCache> clase y la memoria caché se reutiliza mediante la asignación a un <xref:System.Windows.Media.BitmapCacheBrush>.</span><span class="sxs-lookup"><span data-stu-id="d1c34-108">The <xref:System.Windows.Controls.Image> control is cached as a bitmap by using the <xref:System.Windows.Media.BitmapCache> class, and the cache is reused by assigning it to a <xref:System.Windows.Media.BitmapCacheBrush>.</span></span> <span data-ttu-id="d1c34-109">El pincel se asigna al fondo de veinticinco botones para mostrar una reutilización eficiente.</span><span class="sxs-lookup"><span data-stu-id="d1c34-109">The brush is assigned to the background of twenty-five buttons to show efficient reuse.</span></span>  
  
 [!code-xaml[System.Windows.Media.BitmapCacheBrush#_BitmapCacheBrushXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcachebrush/cs/window1.xaml#_bitmapcachebrushxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="d1c34-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1c34-110">See also</span></span>
- <xref:System.Windows.Media.BitmapCache>
- <xref:System.Windows.Media.BitmapCacheBrush>
- <xref:System.Windows.UIElement.CacheMode%2A>
- [<span data-ttu-id="d1c34-111">Cómo: Mejorar el rendimiento al almacenar en caché un elemento de la representación</span><span class="sxs-lookup"><span data-stu-id="d1c34-111">How to: Improve Rendering Performance by Caching an Element</span></span>](how-to-improve-rendering-performance-by-caching-an-element.md)
