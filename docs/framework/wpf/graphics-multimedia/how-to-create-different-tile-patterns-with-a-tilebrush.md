---
title: Filtrar Crear patrones de mosaico diferentes con un objeto TileBrush
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TileBrush [WPF], creating tile patterns
- tile patterns [WPF], creating
- creating [WPF], tile patterns with TileBrush
ms.assetid: 5aa46632-3527-4668-9d8d-0375c8af28aa
ms.openlocfilehash: 2efd070ac9ad502f2539d100fa450f95bcdddced
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57367783"
---
# <a name="how-to-create-different-tile-patterns-with-a-tilebrush"></a><span data-ttu-id="4d09d-102">Filtrar Crear patrones de mosaico diferentes con un objeto TileBrush</span><span class="sxs-lookup"><span data-stu-id="4d09d-102">How to: Create Different Tile Patterns with a TileBrush</span></span>
<span data-ttu-id="4d09d-103">En este ejemplo se muestra cómo usar el <xref:System.Windows.Media.TileBrush.TileMode%2A> propiedad de un <xref:System.Windows.Media.TileBrush> para crear un patrón.</span><span class="sxs-lookup"><span data-stu-id="4d09d-103">This example shows how to use the <xref:System.Windows.Media.TileBrush.TileMode%2A> property of a <xref:System.Windows.Media.TileBrush> to create a pattern.</span></span>  
  
 <span data-ttu-id="4d09d-104">El <xref:System.Windows.Media.TileBrush.TileMode%2A> propiedad le permite especificar cómo el contenido de un <xref:System.Windows.Media.TileBrush> se repite, es decir, en mosaico para rellenar un área de salida.</span><span class="sxs-lookup"><span data-stu-id="4d09d-104">The <xref:System.Windows.Media.TileBrush.TileMode%2A> property enables you to specify how the content of a <xref:System.Windows.Media.TileBrush> is repeated, that is, tiled to fill an output area.</span></span> <span data-ttu-id="4d09d-105">Para crear un modelo, puede establecer el <xref:System.Windows.Media.TileBrush.TileMode%2A> a <xref:System.Windows.Media.TileMode.Tile>, <xref:System.Windows.Media.TileMode.FlipX>, <xref:System.Windows.Media.TileMode.FlipY>, o <xref:System.Windows.Media.TileMode.FlipXY>.</span><span class="sxs-lookup"><span data-stu-id="4d09d-105">To create a pattern, you set the <xref:System.Windows.Media.TileBrush.TileMode%2A> to <xref:System.Windows.Media.TileMode.Tile>, <xref:System.Windows.Media.TileMode.FlipX>, <xref:System.Windows.Media.TileMode.FlipY>, or <xref:System.Windows.Media.TileMode.FlipXY>.</span></span> <span data-ttu-id="4d09d-106">También debe establecer el <xref:System.Windows.Media.TileBrush.Viewport%2A> de la <xref:System.Windows.Media.TileBrush> para que sea menor que el área que se está pintando; en caso contrario, solo un único mosaico está generado, independientemente que <xref:System.Windows.Media.TileBrush.TileMode%2A> configuración utilizada.</span><span class="sxs-lookup"><span data-stu-id="4d09d-106">You must also set the <xref:System.Windows.Media.TileBrush.Viewport%2A> of the <xref:System.Windows.Media.TileBrush> so that it is smaller than the area that you are painting; otherwise, only a single tile is produced, regardless which <xref:System.Windows.Media.TileBrush.TileMode%2A> setting you use.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d09d-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4d09d-107">Example</span></span>  
 <span data-ttu-id="4d09d-108">En el ejemplo siguiente se crea cinco <xref:System.Windows.Media.DrawingBrush> los objetos, proporciona a cada uno un diferentes <xref:System.Windows.Media.TileBrush.TileMode%2A> configuración y los usa para dibujar cinco rectángulos.</span><span class="sxs-lookup"><span data-stu-id="4d09d-108">The following example creates five <xref:System.Windows.Media.DrawingBrush> objects, gives them each a different <xref:System.Windows.Media.TileBrush.TileMode%2A> setting, and uses them to paint five rectangles.</span></span> <span data-ttu-id="4d09d-109">Aunque este ejemplo usa el <xref:System.Windows.Media.DrawingBrush> clase para demostrar <xref:System.Windows.Media.TileBrush.TileMode%2A> comportamiento, el <xref:System.Windows.Media.TileBrush.TileMode%2A> propiedad funciona de forma idéntica para todas la <xref:System.Windows.Media.TileBrush> objetos, es decir, para <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.VisualBrush>, y <xref:System.Windows.Media.DrawingBrush>.</span><span class="sxs-lookup"><span data-stu-id="4d09d-109">Although this example uses the <xref:System.Windows.Media.DrawingBrush> class to demonstrate <xref:System.Windows.Media.TileBrush.TileMode%2A> behavior, the <xref:System.Windows.Media.TileBrush.TileMode%2A> property works identically for all the <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.VisualBrush>, and <xref:System.Windows.Media.DrawingBrush>.</span></span>  
  
 <span data-ttu-id="4d09d-110">En la ilustración siguiente se muestra el resultado que genera el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4d09d-110">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="4d09d-111">![TileBrush en mosaico de salida de ejemplo](./media/graphicsmm-drawingbrushtilemodeexample.png "graphicsmm_DrawingBrushTileModeExample")</span><span class="sxs-lookup"><span data-stu-id="4d09d-111">![TileBrush tiling example output](./media/graphicsmm-drawingbrushtilemodeexample.png "graphicsmm_DrawingBrushTileModeExample")</span></span>  
<span data-ttu-id="4d09d-112">Patrones de mosaico creados con la propiedad TileMode</span><span class="sxs-lookup"><span data-stu-id="4d09d-112">Tile patterns created with the TileMode property</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/TileModeExample.cs#graphicsmmdrawingbrushtilemodeexample)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/tilemodeexample.vb#graphicsmmdrawingbrushtilemodeexample)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/TileModeExample.xaml#graphicsmmdrawingbrushtilemodeexample)]  
  
## <a name="see-also"></a><span data-ttu-id="4d09d-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d09d-113">See also</span></span>
- [<span data-ttu-id="4d09d-114">Establecer el tamaño del mosaico de un TileBrush</span><span class="sxs-lookup"><span data-stu-id="4d09d-114">Set the Tile Size for a TileBrush</span></span>](how-to-set-the-tile-size-for-a-tilebrush.md)
- [<span data-ttu-id="4d09d-115">Pintar con imágenes, dibujos y elementos visuales</span><span class="sxs-lookup"><span data-stu-id="4d09d-115">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
