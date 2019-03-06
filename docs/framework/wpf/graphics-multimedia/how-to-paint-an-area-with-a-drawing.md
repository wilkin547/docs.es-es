---
title: Filtrar Pintar un área con un dibujo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with drawings
- painting [WPF], with drawings
- drawings [WPF], painting with
ms.assetid: c10dc4b1-09b1-41e8-ad14-456b5fb377df
ms.openlocfilehash: 6b204ae631912181333e2559ebadcdc37e7693b7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57371568"
---
# <a name="how-to-paint-an-area-with-a-drawing"></a><span data-ttu-id="b0f09-102">Filtrar Pintar un área con un dibujo</span><span class="sxs-lookup"><span data-stu-id="b0f09-102">How to: Paint an Area with a Drawing</span></span>
<span data-ttu-id="b0f09-103">En este ejemplo se muestra cómo pintar un área con un dibujo.</span><span class="sxs-lookup"><span data-stu-id="b0f09-103">This example shows how to paint an area with a drawing.</span></span> <span data-ttu-id="b0f09-104">Para pintar un área con un dibujo, usa un <xref:System.Windows.Media.DrawingBrush> y uno o varios <xref:System.Windows.Media.Drawing> objetos.</span><span class="sxs-lookup"><span data-stu-id="b0f09-104">To paint an area with a drawing, you use a <xref:System.Windows.Media.DrawingBrush> and one or more <xref:System.Windows.Media.Drawing> objects.</span></span>   <span data-ttu-id="b0f09-105">En el ejemplo siguiente se usa un <xref:System.Windows.Media.DrawingBrush> para pintar un objeto con un dibujo de dos elipses.</span><span class="sxs-lookup"><span data-stu-id="b0f09-105">The following example uses a <xref:System.Windows.Media.DrawingBrush> to paint an object with a drawing of two ellipses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0f09-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b0f09-106">Example</span></span>  
 [!code-xaml[drawingbrush_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/DrawingBrushExample.vb#drawingbrushexamplewholepage)]  
  
 <span data-ttu-id="b0f09-107">En la siguiente ilustración se muestra el resultado del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b0f09-107">The following illustration shows the example's output.</span></span>  
  
 <span data-ttu-id="b0f09-108">![Resultado de DrawingBrush](./media/graphicsmm-drawingbrush-simple.png "graphicsmm_drawingbrush_simple")</span><span class="sxs-lookup"><span data-stu-id="b0f09-108">![Output from a DrawingBrush](./media/graphicsmm-drawingbrush-simple.png "graphicsmm_drawingbrush_simple")</span></span>  
  
 <span data-ttu-id="b0f09-109">(El centro de la forma es blanco por las razones descritas en [controlar el relleno de una forma compuesta](how-to-control-the-fill-of-a-composite-shape.md).)</span><span class="sxs-lookup"><span data-stu-id="b0f09-109">(The center of the shape is white for reasons described in     [Control the Fill of a Composite Shape](how-to-control-the-fill-of-a-composite-shape.md).)</span></span>  
  
 <span data-ttu-id="b0f09-110">Estableciendo un <xref:System.Windows.Media.DrawingBrush> del objeto <xref:System.Windows.Media.TileBrush.Viewport%2A> y <xref:System.Windows.Media.TileBrush.TileMode%2A> propiedades, puede crear un patrón de repetición.</span><span class="sxs-lookup"><span data-stu-id="b0f09-110">By setting a <xref:System.Windows.Media.DrawingBrush> object's <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.TileMode%2A> properties, you can create a repeating pattern.</span></span> <span data-ttu-id="b0f09-111">En el ejemplo siguiente se pinta un objeto con un patrón creado a partir de un dibujo de dos elipses.</span><span class="sxs-lookup"><span data-stu-id="b0f09-111">The following example paints an object with a pattern created from a drawing of two ellipses.</span></span>  
  
 [!code-xaml[drawingbrush_snip#TiledDrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/TiledDrawingBrushExample.xaml#tileddrawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/TiledDrawingBrushExample.cs#tileddrawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/TiledDrawingBrushExample.vb#tileddrawingbrushexamplewholepage)]  
  
 <span data-ttu-id="b0f09-112">La siguiente ilustración muestra el mosaico <xref:System.Windows.Media.DrawingBrush> salida.</span><span class="sxs-lookup"><span data-stu-id="b0f09-112">The following illustration shows the tiled <xref:System.Windows.Media.DrawingBrush> output.</span></span>  
  
 <span data-ttu-id="b0f09-113">![Resultado en mosaico de DrawingBrush](./media/graphicsmm-drawingbrush-tiled.png "graphicsmm_drawingbrush_tiled")</span><span class="sxs-lookup"><span data-stu-id="b0f09-113">![Tiled output from a DrawingBrush](./media/graphicsmm-drawingbrush-tiled.png "graphicsmm_drawingbrush_tiled")</span></span>  
  
 <span data-ttu-id="b0f09-114">Para obtener más información acerca de los pinceles de dibujo, consulte [pintar con imágenes, dibujos y elementos visuales](painting-with-images-drawings-and-visuals.md).</span><span class="sxs-lookup"><span data-stu-id="b0f09-114">For more information about drawing brushes, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span> <span data-ttu-id="b0f09-115">Para obtener más información acerca de <xref:System.Windows.Media.Drawing> objetos, vea el [información general sobre objetos de dibujo](drawing-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b0f09-115">For more information about <xref:System.Windows.Media.Drawing> objects, see the [Drawing Objects Overview](drawing-objects-overview.md).</span></span>
