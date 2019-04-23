---
title: Procedimiento Personalizar el tamaño de un control de posición en un objeto ScrollBar
ms.date: 03/30/2017
helpviewer_keywords:
- ScrollBar control [WPF]
- customizing thumb size [WPF]
- thumb size [WPF]
ms.assetid: fa32b866-5ca1-4e73-85e7-2ac64b80d194
ms.openlocfilehash: 60ae7c4e95801036c5deb0c485645297509b830c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207284"
---
# <a name="how-to-customize-the-thumb-size-on-a-scrollbar"></a><span data-ttu-id="e0b6c-102">Procedimiento Personalizar el tamaño de un control de posición en un objeto ScrollBar</span><span class="sxs-lookup"><span data-stu-id="e0b6c-102">How to: Customize the Thumb Size on a ScrollBar</span></span>
<span data-ttu-id="e0b6c-103">En este tema se explica cómo establecer el <xref:System.Windows.Controls.Primitives.Thumb> de un <xref:System.Windows.Controls.Primitives.ScrollBar> a un tamaño fijo y cómo especificar un tamaño mínimo para el <xref:System.Windows.Controls.Primitives.Thumb> de un <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="e0b6c-103">This topic explains how to set the <xref:System.Windows.Controls.Primitives.Thumb> of a <xref:System.Windows.Controls.Primitives.ScrollBar> to a fixed size and how to specify a minimum size for the <xref:System.Windows.Controls.Primitives.Thumb> of a <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0b6c-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e0b6c-104">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="e0b6c-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="e0b6c-105">Description</span></span>  
 <span data-ttu-id="e0b6c-106">En el ejemplo siguiente se crea un <xref:System.Windows.Controls.Primitives.ScrollBar> que tiene un <xref:System.Windows.Controls.Primitives.Thumb> con un tamaño fijo.</span><span class="sxs-lookup"><span data-stu-id="e0b6c-106">The following example creates a <xref:System.Windows.Controls.Primitives.ScrollBar> that has a <xref:System.Windows.Controls.Primitives.Thumb> with a fixed size.</span></span> <span data-ttu-id="e0b6c-107">El ejemplo se establece la <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> propiedad de la <xref:System.Windows.Controls.Primitives.Thumb> a <xref:System.Double.NaN> y establece el alto de la <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="e0b6c-107">The example sets the <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> property of the <xref:System.Windows.Controls.Primitives.Thumb> to <xref:System.Double.NaN> and sets the height of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  <span data-ttu-id="e0b6c-108">Para crear una horizontal <xref:System.Windows.Controls.Primitives.ScrollBar> con un <xref:System.Windows.Controls.Primitives.Thumb> que tiene un ancho fijo, establezca el ancho de la <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="e0b6c-108">To create a horizontal <xref:System.Windows.Controls.Primitives.ScrollBar> with a <xref:System.Windows.Controls.Primitives.Thumb> that has a fixed width, set the width of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="e0b6c-109">Código</span><span class="sxs-lookup"><span data-stu-id="e0b6c-109">Code</span></span>  
 [!code-xaml[ScrollBarCustomThumbSize#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#1)]  
  
## <a name="description"></a><span data-ttu-id="e0b6c-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="e0b6c-110">Description</span></span>  
 <span data-ttu-id="e0b6c-111">En el ejemplo siguiente se crea un <xref:System.Windows.Controls.Primitives.ScrollBar> que tiene un <xref:System.Windows.Controls.Primitives.Thumb> con un tamaño mínimo.</span><span class="sxs-lookup"><span data-stu-id="e0b6c-111">The following example creates a <xref:System.Windows.Controls.Primitives.ScrollBar> that has a <xref:System.Windows.Controls.Primitives.Thumb> with a minimum size.</span></span> <span data-ttu-id="e0b6c-112">El ejemplo establece el valor de <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="e0b6c-112">The example sets the value of <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>.</span></span> <span data-ttu-id="e0b6c-113">Para crear una horizontal <xref:System.Windows.Controls.Primitives.ScrollBar> con un <xref:System.Windows.Controls.Primitives.Thumb> que tiene un ancho mínimo, establezca el <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="e0b6c-113">To create a horizontal <xref:System.Windows.Controls.Primitives.ScrollBar> with a <xref:System.Windows.Controls.Primitives.Thumb> that has a minimum width, set the <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="e0b6c-114">Código</span><span class="sxs-lookup"><span data-stu-id="e0b6c-114">Code</span></span>  
 [!code-xaml[ScrollBarCustomThumbSize#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#2)]  
  
## <a name="see-also"></a><span data-ttu-id="e0b6c-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0b6c-115">See also</span></span>

- <span data-ttu-id="e0b6c-116">[ScrollBar Styles and Templates](scrollbar-styles-and-templates.md) (Estilos y plantillas de ScrollBar)</span><span class="sxs-lookup"><span data-stu-id="e0b6c-116">[ScrollBar Styles and Templates](scrollbar-styles-and-templates.md)</span></span>
