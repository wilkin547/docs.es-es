---
title: "Cómo: Conservar la relación de aspecto de una imagen utilizada como fondo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- aspect ratios of background images [WPF], preserving
- brushes [WPF], preserving aspect ratios of background images
- background images [WPF], preserving aspect ratios
ms.assetid: 28c39478-13d7-4011-80a3-8b9cc3e54478
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9716d91a99eb79e38b729424389b2962d1eb6b1c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-preserve-the-aspect-ratio-of-an-image-used-as-a-background"></a><span data-ttu-id="78d54-102">Cómo: Conservar la relación de aspecto de una imagen utilizada como fondo</span><span class="sxs-lookup"><span data-stu-id="78d54-102">How to: Preserve the Aspect Ratio of an Image Used as a Background</span></span>
<span data-ttu-id="78d54-103">Este ejemplo muestra cómo utilizar el <xref:System.Windows.Media.TileBrush.Stretch%2A> propiedad de un <xref:System.Windows.Media.ImageBrush> para conservar la relación de aspecto de la imagen.</span><span class="sxs-lookup"><span data-stu-id="78d54-103">This example shows how to use the <xref:System.Windows.Media.TileBrush.Stretch%2A> property of an <xref:System.Windows.Media.ImageBrush> in order to preserve the aspect ratio of the image.</span></span>  
  
 <span data-ttu-id="78d54-104">De forma predeterminada, cuando se usa un <xref:System.Windows.Media.ImageBrush> para pintar un área, su contenido se expande para rellenar completamente el área de salida.</span><span class="sxs-lookup"><span data-stu-id="78d54-104">By default, when you use an <xref:System.Windows.Media.ImageBrush> to paint an area, its content stretches to completely fill the output area.</span></span> <span data-ttu-id="78d54-105">Cuando el área de salida y la imagen tienen relaciones de aspecto diferentes, la imagen queda distorsionada al ajustarse.</span><span class="sxs-lookup"><span data-stu-id="78d54-105">When the output area and the image have different aspect ratios, the image is distorted by this stretching.</span></span>  
  
 <span data-ttu-id="78d54-106">Para realizar una <xref:System.Windows.Media.ImageBrush> conservar la relación de aspecto de la imagen, establezca la <xref:System.Windows.Media.TileBrush.Stretch%2A> propiedad <xref:System.Windows.Media.Stretch.Uniform> o <xref:System.Windows.Media.Stretch.UniformToFill>.</span><span class="sxs-lookup"><span data-stu-id="78d54-106">To make an <xref:System.Windows.Media.ImageBrush> preserve the aspect ratio of its image, set the <xref:System.Windows.Media.TileBrush.Stretch%2A> property to <xref:System.Windows.Media.Stretch.Uniform> or <xref:System.Windows.Media.Stretch.UniformToFill>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78d54-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="78d54-107">Example</span></span>  
 <span data-ttu-id="78d54-108">El ejemplo siguiente utiliza dos <xref:System.Windows.Media.ImageBrush> objetos que se va a pintar dos rectángulos.</span><span class="sxs-lookup"><span data-stu-id="78d54-108">The following example uses two <xref:System.Windows.Media.ImageBrush> objects to paint two rectangles.</span></span> <span data-ttu-id="78d54-109">Cada rectángulo tiene 300 por 150 píxeles y cada uno contiene una imagen de 300 por 300 píxeles.</span><span class="sxs-lookup"><span data-stu-id="78d54-109">Each rectangle is 300 by 150 pixels and each contains a 300 by 300 pixel image.</span></span> <span data-ttu-id="78d54-110">El <xref:System.Windows.Media.TileBrush.Stretch%2A> propiedad del primer pincel se establece en <xref:System.Windows.Media.Stretch.Uniform>y el <xref:System.Windows.Media.TileBrush.Stretch%2A> propiedad del segundo pincel se establece en <xref:System.Windows.Media.Stretch.UniformToFill>.</span><span class="sxs-lookup"><span data-stu-id="78d54-110">The <xref:System.Windows.Media.TileBrush.Stretch%2A> property of the first brush is set to <xref:System.Windows.Media.Stretch.Uniform>, and the <xref:System.Windows.Media.TileBrush.Stretch%2A> property of the second brush is set to <xref:System.Windows.Media.Stretch.UniformToFill>.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushStretchModesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/StretchModes.cs#imagebrushstretchmodesexamplewholepage)]  
  
 <span data-ttu-id="78d54-111">La ilustración siguiente muestra la salida del pincel de primer, que tiene un <xref:System.Windows.Media.TileBrush.Stretch%2A> de <xref:System.Windows.Media.Stretch.Uniform>.</span><span class="sxs-lookup"><span data-stu-id="78d54-111">The following illustration shows the output of the first brush, which has a <xref:System.Windows.Media.TileBrush.Stretch%2A> setting of <xref:System.Windows.Media.Stretch.Uniform>.</span></span>  
  
 <span data-ttu-id="78d54-112">![ImageBrush con Uniform stretching](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagebrushuniformstretch.jpg "graphicsmm_ImageBrushUniformStretch")</span><span class="sxs-lookup"><span data-stu-id="78d54-112">![ImageBrush with Uniform stretching](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagebrushuniformstretch.jpg "graphicsmm_ImageBrushUniformStretch")</span></span>  
  
 <span data-ttu-id="78d54-113">La ilustración siguiente muestra el resultado del segundo pincel, que tiene un <xref:System.Windows.Media.TileBrush.Stretch%2A> de <xref:System.Windows.Media.Stretch.UniformToFill>.</span><span class="sxs-lookup"><span data-stu-id="78d54-113">The next illustration shows the output of the second brush, which has a <xref:System.Windows.Media.TileBrush.Stretch%2A> setting of <xref:System.Windows.Media.Stretch.UniformToFill>.</span></span>  
  
 <span data-ttu-id="78d54-114">![ImageBrush con UniformToFill stretching](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagebrushuniformtofillstretch.jpg "graphicsmm_ImageBrushUniformToFillStretch")</span><span class="sxs-lookup"><span data-stu-id="78d54-114">![ImageBrush with UniformToFill stretching](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagebrushuniformtofillstretch.jpg "graphicsmm_ImageBrushUniformToFillStretch")</span></span>  
  
 <span data-ttu-id="78d54-115">Tenga en cuenta que la <xref:System.Windows.Media.TileBrush.Stretch%2A> propiedad se comporta exactamente igual para los demás <xref:System.Windows.Media.TileBrush> objetos, es decir, para <xref:System.Windows.Media.DrawingBrush> y <xref:System.Windows.Media.VisualBrush>.</span><span class="sxs-lookup"><span data-stu-id="78d54-115">Note that the <xref:System.Windows.Media.TileBrush.Stretch%2A> property behaves identically for the other <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.DrawingBrush> and <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="78d54-116">Para obtener más información acerca de <xref:System.Windows.Media.ImageBrush> y el otro <xref:System.Windows.Media.TileBrush> los objetos, vea [pintar con imágenes, gráficos y objetos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).</span><span class="sxs-lookup"><span data-stu-id="78d54-116">For more information about <xref:System.Windows.Media.ImageBrush> and the other <xref:System.Windows.Media.TileBrush> objects, see [Painting with Images, Drawings, and Visuals](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).</span></span>  
  
 <span data-ttu-id="78d54-117">Tenga en cuenta también que, aunque la <xref:System.Windows.Media.TileBrush.Stretch%2A> propiedad aparece para especificar cómo el <xref:System.Windows.Media.TileBrush> contenido se ajusta para su área de salida, en realidad especifica cómo el <xref:System.Windows.Media.TileBrush> contenido se expande para rellenar su mosaico base.</span><span class="sxs-lookup"><span data-stu-id="78d54-117">Note also that, although the <xref:System.Windows.Media.TileBrush.Stretch%2A> property appears to specify how the <xref:System.Windows.Media.TileBrush> content stretches to fit its output area, it actually specifies how the <xref:System.Windows.Media.TileBrush> content stretches to fill its base tile.</span></span> <span data-ttu-id="78d54-118">Para obtener más información, consulta <xref:System.Windows.Media.TileBrush>.</span><span class="sxs-lookup"><span data-stu-id="78d54-118">For more information, see <xref:System.Windows.Media.TileBrush>.</span></span>  
  
 <span data-ttu-id="78d54-119">Este ejemplo de código forma parte de un ejemplo mayor proporcionado para el <xref:System.Windows.Media.ImageBrush> clase.</span><span class="sxs-lookup"><span data-stu-id="78d54-119">This code example is part of a larger example that is provided for the <xref:System.Windows.Media.ImageBrush> class.</span></span> <span data-ttu-id="78d54-120">Para obtener un ejemplo completo, vea [ejemplo ImageBrush](http://go.microsoft.com/fwlink/?LinkID=160005).</span><span class="sxs-lookup"><span data-stu-id="78d54-120">For the complete sample, see [ImageBrush Sample](http://go.microsoft.com/fwlink/?LinkID=160005).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78d54-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="78d54-121">See Also</span></span>  
 <xref:System.Windows.Media.TileBrush>  
 [<span data-ttu-id="78d54-122">Pintar con imágenes, dibujos y elementos visuales</span><span class="sxs-lookup"><span data-stu-id="78d54-122">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
