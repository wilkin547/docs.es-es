---
title: 'Cómo: Establecer el tamaño del mosaico de un TileBrush'
ms.date: 03/30/2017
helpviewer_keywords:
- TileBrush [WPF], size of tile properties
- Viewport property of TileBrush [WPF]
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
ms.openlocfilehash: af7bab59a292549b29dad9b6a7417f22b1b84e48
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186835"
---
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a><span data-ttu-id="8897c-102">Cómo: Establecer el tamaño del mosaico de un TileBrush</span><span class="sxs-lookup"><span data-stu-id="8897c-102">How to: Set the Tile Size for a TileBrush</span></span>

<span data-ttu-id="8897c-103">En este ejemplo se muestra cómo <xref:System.Windows.Media.TileBrush>establecer el tamaño de tesela para un archivo .</span><span class="sxs-lookup"><span data-stu-id="8897c-103">This example shows how to set the tile size for a <xref:System.Windows.Media.TileBrush>.</span></span> <span data-ttu-id="8897c-104">De forma <xref:System.Windows.Media.TileBrush> predeterminada, un produce un único mosaico que rellena completamente el área que está pintando.</span><span class="sxs-lookup"><span data-stu-id="8897c-104">By default, a <xref:System.Windows.Media.TileBrush> produces a single tile that completely fills the area that you are painting.</span></span> <span data-ttu-id="8897c-105">Puede invalidar este comportamiento <xref:System.Windows.Media.TileBrush.Viewport%2A> estableciendo las propiedades y. <xref:System.Windows.Media.TileBrush.ViewportUnits%2A></span><span class="sxs-lookup"><span data-stu-id="8897c-105">You can override this behavior by setting the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> properties.</span></span>

<span data-ttu-id="8897c-106">La <xref:System.Windows.Media.TileBrush.Viewport%2A> propiedad especifica el tamaño <xref:System.Windows.Media.TileBrush>de tesela para un archivo .</span><span class="sxs-lookup"><span data-stu-id="8897c-106">The <xref:System.Windows.Media.TileBrush.Viewport%2A> property specifies the tile size for a <xref:System.Windows.Media.TileBrush>.</span></span> <span data-ttu-id="8897c-107">De forma predeterminada, <xref:System.Windows.Media.TileBrush.Viewport%2A> el valor de la propiedad es relativo al tamaño del área que se va a pintar.</span><span class="sxs-lookup"><span data-stu-id="8897c-107">By default, the value of the <xref:System.Windows.Media.TileBrush.Viewport%2A> property is relative to the size of the area being painted.</span></span> <span data-ttu-id="8897c-108">Para que <xref:System.Windows.Media.TileBrush.Viewport%2A> la propiedad especifique un <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> tamaño <xref:System.Windows.Media.BrushMappingMode.Absolute>de tesela absoluto, establezca la propiedad en .</span><span class="sxs-lookup"><span data-stu-id="8897c-108">To make the <xref:System.Windows.Media.TileBrush.Viewport%2A> property specify an absolute tile size, set the <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> property to <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span>

## <a name="example"></a><span data-ttu-id="8897c-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8897c-109">Example</span></span>

<span data-ttu-id="8897c-110">En el ejemplo <xref:System.Windows.Media.ImageBrush>siguiente se <xref:System.Windows.Media.TileBrush>utiliza un , un tipo de , para pintar un rectángulo con mosaicos.</span><span class="sxs-lookup"><span data-stu-id="8897c-110">The following example uses an <xref:System.Windows.Media.ImageBrush>, a type of <xref:System.Windows.Media.TileBrush>, to paint a rectangle with tiles.</span></span> <span data-ttu-id="8897c-111">En el ejemplo se establece cada icono en 50 por ciento por 50 por ciento del área de salida (el rectángulo).</span><span class="sxs-lookup"><span data-stu-id="8897c-111">The example sets each tile to 50 percent by 50 percent of the output area (the rectangle).</span></span> <span data-ttu-id="8897c-112">Como resultado, el rectángulo se pinta con cuatro proyecciones de la imagen.</span><span class="sxs-lookup"><span data-stu-id="8897c-112">As a result, the rectangle is painted with four projections of the image.</span></span>

<span data-ttu-id="8897c-113">La ilustración siguiente muestra la salida que produce el ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8897c-113">The following illustration shows the output that the example produces:</span></span>

![Un rectángulo con cuatro cerezas que demuestran mosaicos con un pincel de imagen.](./media/how-to-set-the-tile-size-for-a-tilebrush/rectangle-tile-image-brush.png)

[!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]

<span data-ttu-id="8897c-115">En el ejemplo <xref:System.Windows.Media.ImageBrush>siguiente <xref:System.Windows.Media.TileBrush.Viewport%2A> se `0,0,25,25` crea <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> <xref:System.Windows.Media.BrushMappingMode.Absolute>un , establece su en y su en , y se utiliza para pintar otro rectángulo.</span><span class="sxs-lookup"><span data-stu-id="8897c-115">The next example creates an <xref:System.Windows.Media.ImageBrush>, sets its <xref:System.Windows.Media.TileBrush.Viewport%2A> to `0,0,25,25` and its <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> to <xref:System.Windows.Media.BrushMappingMode.Absolute>, and uses it to paint another rectangle.</span></span> <span data-ttu-id="8897c-116">Como resultado, el pincel genera iconos que tienen un ancho de 25 píxeles y un alto de 25 píxeles.</span><span class="sxs-lookup"><span data-stu-id="8897c-116">As a result, the brush produces tiles that have a width of 25  pixels and a height of 25 pixels .</span></span>

<span data-ttu-id="8897c-117">La ilustración siguiente muestra la salida que produce el ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8897c-117">The following illustration shows the output that the example produces:</span></span>

![Un rectángulo con cuarenta y ocho cerezas que demuestran un TileBrush en mosaico con una ventana gráfica.](./media/how-to-set-the-tile-size-for-a-tilebrush/25-x-25-viewport-tilebrush.png)

[!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]

<span data-ttu-id="8897c-119">Los ejemplos anteriores forman parte de un ejemplo mayor.</span><span class="sxs-lookup"><span data-stu-id="8897c-119">The preceding examples are part of a larger sample.</span></span> <span data-ttu-id="8897c-120">Para obtener el ejemplo completo, vea [ImageBrush Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).</span><span class="sxs-lookup"><span data-stu-id="8897c-120">For the complete sample, see [ImageBrush Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).</span></span>

<span data-ttu-id="8897c-121">Aunque en este <xref:System.Windows.Media.ImageBrush> ejemplo <xref:System.Windows.Media.TileBrush.Viewport%2A> se <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> utiliza la clase, <xref:System.Windows.Media.TileBrush> las propiedades y <xref:System.Windows.Media.DrawingBrush> se <xref:System.Windows.Media.VisualBrush>comportan de forma idéntica para los demás objetos, es decir, for y .</span><span class="sxs-lookup"><span data-stu-id="8897c-121">Although this example uses the <xref:System.Windows.Media.ImageBrush> class, the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> properties behave identically for the other <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.DrawingBrush> and <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="8897c-122">Para obtener <xref:System.Windows.Media.ImageBrush> más información <xref:System.Windows.Media.TileBrush> sobre y los demás objetos, vea [Pintar con imágenes, dibujos y objetos visuales](painting-with-images-drawings-and-visuals.md).</span><span class="sxs-lookup"><span data-stu-id="8897c-122">For more information about <xref:System.Windows.Media.ImageBrush> and the other <xref:System.Windows.Media.TileBrush> objects, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8897c-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8897c-123">See also</span></span>

- <xref:System.Windows.Media.TileBrush>
- [<span data-ttu-id="8897c-124">Pintar con imágenes, dibujos y elementos visuales</span><span class="sxs-lookup"><span data-stu-id="8897c-124">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="8897c-125">Crear patrones de mosaico diferentes con un objeto TileBrush</span><span class="sxs-lookup"><span data-stu-id="8897c-125">Create Different Tile Patterns with a TileBrush</span></span>](how-to-create-different-tile-patterns-with-a-tilebrush.md)
