---
title: Filtrar Establecer el tamaño del mosaico de un TileBrush
ms.date: 03/30/2017
helpviewer_keywords:
- TileBrush [WPF], size of tile properties
- Viewport property of TileBrush [WPF]
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
ms.openlocfilehash: 80b5dfc668464df829db593668bea8a9a4ec09e4
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58839702"
---
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a><span data-ttu-id="9e321-102">Filtrar Establecer el tamaño del mosaico de un TileBrush</span><span class="sxs-lookup"><span data-stu-id="9e321-102">How to: Set the Tile Size for a TileBrush</span></span>

<span data-ttu-id="9e321-103">En este ejemplo se muestra cómo establecer el tamaño del mosaico para un <xref:System.Windows.Media.TileBrush>.</span><span class="sxs-lookup"><span data-stu-id="9e321-103">This example shows how to set the tile size for a <xref:System.Windows.Media.TileBrush>.</span></span> <span data-ttu-id="9e321-104">De forma predeterminada, un <xref:System.Windows.Media.TileBrush> genera un mosaico único que rellena completamente el área que se está pintando.</span><span class="sxs-lookup"><span data-stu-id="9e321-104">By default, a <xref:System.Windows.Media.TileBrush> produces a single tile that completely fills the area that you are painting.</span></span> <span data-ttu-id="9e321-105">Puede invalidar este comportamiento estableciendo el <xref:System.Windows.Media.TileBrush.Viewport%2A> y <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> propiedades.</span><span class="sxs-lookup"><span data-stu-id="9e321-105">You can override this behavior by setting the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> properties.</span></span>

<span data-ttu-id="9e321-106">El <xref:System.Windows.Media.TileBrush.Viewport%2A> propiedad especifica el tamaño del mosaico para un <xref:System.Windows.Media.TileBrush>.</span><span class="sxs-lookup"><span data-stu-id="9e321-106">The <xref:System.Windows.Media.TileBrush.Viewport%2A> property specifies the tile size for a <xref:System.Windows.Media.TileBrush>.</span></span> <span data-ttu-id="9e321-107">De forma predeterminada, el valor de la <xref:System.Windows.Media.TileBrush.Viewport%2A> propiedad es relativo al tamaño del área que se está pintando.</span><span class="sxs-lookup"><span data-stu-id="9e321-107">By default, the value of the <xref:System.Windows.Media.TileBrush.Viewport%2A> property is relative to the size of the area being painted.</span></span> <span data-ttu-id="9e321-108">Para realizar la <xref:System.Windows.Media.TileBrush.Viewport%2A> propiedad especificar un tamaño de mosaico absoluto, establezca el <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> propiedad <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span><span class="sxs-lookup"><span data-stu-id="9e321-108">To make the <xref:System.Windows.Media.TileBrush.Viewport%2A> property specify an absolute tile size, set the <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> property to <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span>

## <a name="example"></a><span data-ttu-id="9e321-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9e321-109">Example</span></span>

<span data-ttu-id="9e321-110">En el ejemplo siguiente se usa un <xref:System.Windows.Media.ImageBrush>, un tipo de <xref:System.Windows.Media.TileBrush>, para pintar un rectángulo con mosaicos.</span><span class="sxs-lookup"><span data-stu-id="9e321-110">The following example uses an <xref:System.Windows.Media.ImageBrush>, a type of <xref:System.Windows.Media.TileBrush>, to paint a rectangle with tiles.</span></span> <span data-ttu-id="9e321-111">El ejemplo establece cada mosaico al 50 por ciento al 50 por ciento del área de salida (rectángulo).</span><span class="sxs-lookup"><span data-stu-id="9e321-111">The example sets each tile to 50 percent by 50 percent of the output area (the rectangle).</span></span> <span data-ttu-id="9e321-112">Como resultado, el rectángulo se pinta con cuatro proyecciones de la imagen.</span><span class="sxs-lookup"><span data-stu-id="9e321-112">As a result, the rectangle is painted with four projections of the image.</span></span>

<span data-ttu-id="9e321-113">La siguiente ilustración muestra la salida que genera el ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9e321-113">The following illustration shows the output that the example produces:</span></span>

![Un rectángulo con cuatro cerezas demostrar la disposición en mosaico con un pincel de imagen.](./media/how-to-set-the-tile-size-for-a-tilebrush/rectangle-tile-image-brush.png)

[!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]

<span data-ttu-id="9e321-115">El ejemplo siguiente se crea un <xref:System.Windows.Media.ImageBrush>, establece su <xref:System.Windows.Media.TileBrush.Viewport%2A> a `0,0,25,25` y su <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> a <xref:System.Windows.Media.BrushMappingMode.Absolute>y lo usa para pintar otro rectángulo.</span><span class="sxs-lookup"><span data-stu-id="9e321-115">The next example creates an <xref:System.Windows.Media.ImageBrush>, sets its <xref:System.Windows.Media.TileBrush.Viewport%2A> to `0,0,25,25` and its <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> to <xref:System.Windows.Media.BrushMappingMode.Absolute>, and uses it to paint another rectangle.</span></span> <span data-ttu-id="9e321-116">Como resultado, el pincel genera iconos que tienen un ancho de 25 píxeles y un alto de 25 píxeles.</span><span class="sxs-lookup"><span data-stu-id="9e321-116">As a result, the brush produces tiles that have a width of 25  pixels and a height of 25 pixels .</span></span>

<span data-ttu-id="9e321-117">La siguiente ilustración muestra la salida que genera el ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9e321-117">The following illustration shows the output that the example produces:</span></span>

![Un rectángulo con cerezas cuarenta y ocho demostrar un TileBrush en mosaico con una ventanilla.](./media/how-to-set-the-tile-size-for-a-tilebrush/25-x-25-viewport-tilebrush.png)

[!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]

<span data-ttu-id="9e321-119">Los ejemplos anteriores forman parte de un ejemplo mayor.</span><span class="sxs-lookup"><span data-stu-id="9e321-119">The preceding examples are part of a larger sample.</span></span> <span data-ttu-id="9e321-120">Para obtener un ejemplo completo, vea [ejemplo de ImageBrush](https://go.microsoft.com/fwlink/?LinkID=160005).</span><span class="sxs-lookup"><span data-stu-id="9e321-120">For the complete sample, see [ImageBrush Sample](https://go.microsoft.com/fwlink/?LinkID=160005).</span></span>

<span data-ttu-id="9e321-121">Aunque este ejemplo usa el <xref:System.Windows.Media.ImageBrush> (clase), el <xref:System.Windows.Media.TileBrush.Viewport%2A> y <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> propiedades se comportan exactamente igual para los demás <xref:System.Windows.Media.TileBrush> objetos, es decir, para <xref:System.Windows.Media.DrawingBrush> y <xref:System.Windows.Media.VisualBrush>.</span><span class="sxs-lookup"><span data-stu-id="9e321-121">Although this example uses the <xref:System.Windows.Media.ImageBrush> class, the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> properties behave identically for the other <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.DrawingBrush> and <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="9e321-122">Para obtener más información acerca de <xref:System.Windows.Media.ImageBrush> y el otro <xref:System.Windows.Media.TileBrush> objetos, vea [pintar con imágenes, dibujos y elementos visuales](painting-with-images-drawings-and-visuals.md).</span><span class="sxs-lookup"><span data-stu-id="9e321-122">For more information about <xref:System.Windows.Media.ImageBrush> and the other <xref:System.Windows.Media.TileBrush> objects, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9e321-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e321-123">See also</span></span>

- <xref:System.Windows.Media.TileBrush>
- [<span data-ttu-id="9e321-124">Pintar con imágenes, dibujos y elementos visuales</span><span class="sxs-lookup"><span data-stu-id="9e321-124">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="9e321-125">Crear patrones de mosaico diferentes con un objeto TileBrush</span><span class="sxs-lookup"><span data-stu-id="9e321-125">Create Different Tile Patterns with a TileBrush</span></span>](how-to-create-different-tile-patterns-with-a-tilebrush.md)
