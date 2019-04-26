---
title: Procedimiento Crear un dibujo compuesto
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], composite
- composite drawings [WPF]
- graphics [WPF], composite drawings
ms.assetid: 066eb0ab-5f0e-439d-85c6-dca60af269fc
ms.openlocfilehash: 0af7fbca593627ebe8cd102a02617a27eac50aa5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910005"
---
# <a name="how-to-create-a-composite-drawing"></a><span data-ttu-id="09237-102">Procedimiento Crear un dibujo compuesto</span><span class="sxs-lookup"><span data-stu-id="09237-102">How to: Create a Composite Drawing</span></span>
<span data-ttu-id="09237-103">En este ejemplo se muestra cómo usar un <xref:System.Windows.Media.DrawingGroup> para crear dibujos complejos combinando varias <xref:System.Windows.Media.Drawing> objetos en un solo dibujo compuesto.</span><span class="sxs-lookup"><span data-stu-id="09237-103">This example shows how to use a <xref:System.Windows.Media.DrawingGroup> to create complex drawings by combining multiple <xref:System.Windows.Media.Drawing> objects into a single composite drawing.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09237-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="09237-104">Example</span></span>  
 <span data-ttu-id="09237-105">En el ejemplo siguiente se usa un <xref:System.Windows.Media.DrawingGroup> para crear un dibujo compuesto a partir del <xref:System.Windows.Media.GeometryDrawing> y <xref:System.Windows.Media.ImageDrawing> objetos.</span><span class="sxs-lookup"><span data-stu-id="09237-105">The following example uses a <xref:System.Windows.Media.DrawingGroup> to create a composite drawing from the <xref:System.Windows.Media.GeometryDrawing> and <xref:System.Windows.Media.ImageDrawing> objects.</span></span> <span data-ttu-id="09237-106">En la ilustración siguiente se muestra el resultado que genera el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="09237-106">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="09237-107">![DrawingGroup con varios dibujos](./media/graphicsmm-simple.jpg "graphicsmm_simple")</span><span class="sxs-lookup"><span data-stu-id="09237-107">![A DrawingGroup with multiple drawings](./media/graphicsmm-simple.jpg "graphicsmm_simple")</span></span>  
<span data-ttu-id="09237-108">Un dibujo compuesto que se crea mediante el uso de DrawingGroup</span><span class="sxs-lookup"><span data-stu-id="09237-108">A composite drawing that is created by using DrawingGroup</span></span>  
  
 <span data-ttu-id="09237-109">Tenga en cuenta el borde gris, que muestra los límites del dibujo.</span><span class="sxs-lookup"><span data-stu-id="09237-109">Note the gray border, which shows the bounds of the drawing.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 <span data-ttu-id="09237-110">Puede usar un <xref:System.Windows.Media.DrawingGroup> para aplicar un <xref:System.Windows.Media.DrawingGroup.Transform%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A> establecer, <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, o <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> a la contiene los dibujos.</span><span class="sxs-lookup"><span data-stu-id="09237-110">You can use a <xref:System.Windows.Media.DrawingGroup> to apply a <xref:System.Windows.Media.DrawingGroup.Transform%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A> setting, <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, or <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> to the drawings it contains.</span></span> <span data-ttu-id="09237-111">Dado que un <xref:System.Windows.Media.DrawingGroup> es también un <xref:System.Windows.Media.Drawing>, pueden contener otros <xref:System.Windows.Media.DrawingGroup> objetos.</span><span class="sxs-lookup"><span data-stu-id="09237-111">Because a <xref:System.Windows.Media.DrawingGroup> is also a <xref:System.Windows.Media.Drawing>, it can contain other <xref:System.Windows.Media.DrawingGroup> objects.</span></span>  
  
 <span data-ttu-id="09237-112">El ejemplo siguiente es similar al ejemplo anterior, salvo que usa adicionales <xref:System.Windows.Media.DrawingGroup> objetos que se va a aplicar efectos de imagen y una máscara de opacidad a algunos de sus planos.</span><span class="sxs-lookup"><span data-stu-id="09237-112">The following example is similar to the preceding example, except that it uses additional <xref:System.Windows.Media.DrawingGroup> objects to apply bitmap effects and an opacity mask to some of its drawings.</span></span> <span data-ttu-id="09237-113">En la ilustración siguiente se muestra el resultado que genera el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="09237-113">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="09237-114">![DrawingGroup con varios dibujos](./media/graphicsmm-multiple.jpg "graphicsmm_multiple")</span><span class="sxs-lookup"><span data-stu-id="09237-114">![A DrawingGroup with multiple drawings](./media/graphicsmm-multiple.jpg "graphicsmm_multiple")</span></span>  
<span data-ttu-id="09237-115">Dibujo compuesto que tiene varios objetos de DrawingGroup</span><span class="sxs-lookup"><span data-stu-id="09237-115">Composite drawing that has multiple DrawingGroup objects</span></span>  
  
 <span data-ttu-id="09237-116">Tenga en cuenta el borde gris, que muestra los límites del dibujo.</span><span class="sxs-lookup"><span data-stu-id="09237-116">Note the gray border, which shows the bounds of the drawing.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmmultipledrawinggroupsexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmmultipledrawinggroupsexample)]  
  
 <span data-ttu-id="09237-117">Para obtener más información acerca de <xref:System.Windows.Media.Drawing> objetos, vea [información general sobre objetos de dibujo](drawing-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="09237-117">For more information about <xref:System.Windows.Media.Drawing> objects, see [Drawing Objects Overview](drawing-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09237-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="09237-118">See also</span></span>

- <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>
- <xref:System.Windows.Media.DrawingGroup.Transform%2A>
- <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>
- <xref:System.Windows.Media.DrawingGroup.Opacity%2A>
- <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>
- <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>
- [<span data-ttu-id="09237-119">Información general sobre objetos Drawing</span><span class="sxs-lookup"><span data-stu-id="09237-119">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
