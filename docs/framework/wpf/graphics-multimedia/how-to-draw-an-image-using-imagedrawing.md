---
title: Filtrar Dibujar una imagen mediante un objeto ImageDrawing
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], images
- graphics [WPF], drawing images
- images [WPF], drawing
ms.assetid: df28ab41-25fb-4ab3-b51d-7f695b24f55e
ms.openlocfilehash: f9459185bf81160b45222e7d6821e0f945ada381
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59100163"
---
# <a name="how-to-draw-an-image-using-imagedrawing"></a><span data-ttu-id="d6131-102">Filtrar Dibujar una imagen mediante un objeto ImageDrawing</span><span class="sxs-lookup"><span data-stu-id="d6131-102">How to: Draw an Image Using ImageDrawing</span></span>
<span data-ttu-id="d6131-103">En este ejemplo se muestra cómo usar un <xref:System.Windows.Media.ImageDrawing> para dibujar una imagen.</span><span class="sxs-lookup"><span data-stu-id="d6131-103">This example shows how to use an <xref:System.Windows.Media.ImageDrawing> to draw an image.</span></span> <span data-ttu-id="d6131-104">Un <xref:System.Windows.Media.ImageDrawing> permite mostrar un <xref:System.Windows.Media.ImageSource> con un <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.DrawingImage>, o <xref:System.Windows.Media.Visual>.</span><span class="sxs-lookup"><span data-stu-id="d6131-104">An <xref:System.Windows.Media.ImageDrawing> enables you display an <xref:System.Windows.Media.ImageSource> with a <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.DrawingImage>, or <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="d6131-105">Para dibujar una imagen, se crea un <xref:System.Windows.Media.ImageDrawing> y establezca su <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> y <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> propiedades.</span><span class="sxs-lookup"><span data-stu-id="d6131-105">To draw an image, you create an <xref:System.Windows.Media.ImageDrawing> and set its <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> and <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> properties.</span></span> <span data-ttu-id="d6131-106">El <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> propiedad especifica la imagen para dibujar y la <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> propiedad especifica la posición y tamaño de cada imagen.</span><span class="sxs-lookup"><span data-stu-id="d6131-106">The <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> property specifies the image to draw, and the <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> property specifies the position and size of each image.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6131-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d6131-107">Example</span></span>  
 <span data-ttu-id="d6131-108">En el ejemplo siguiente se crea un dibujo compuesto mediante cuatro <xref:System.Windows.Media.ImageDrawing> objetos.</span><span class="sxs-lookup"><span data-stu-id="d6131-108">The following example creates a composite drawing using four <xref:System.Windows.Media.ImageDrawing> objects.</span></span> <span data-ttu-id="d6131-109">Este ejemplo genera la siguiente imagen:</span><span class="sxs-lookup"><span data-stu-id="d6131-109">This example produces the following image:</span></span>  
  
 <span data-ttu-id="d6131-110">![Varios objetos DrawingImage](./media/graphicsmm-imagedrawingexample.jpg "graphicsmm_ImageDrawingExample")</span><span class="sxs-lookup"><span data-stu-id="d6131-110">![Several DrawingImage objects](./media/graphicsmm-imagedrawingexample.jpg "graphicsmm_ImageDrawingExample")</span></span>  
<span data-ttu-id="d6131-111">Cuatro objetos de un objeto ImageDrawing</span><span class="sxs-lookup"><span data-stu-id="d6131-111">Four ImageDrawing objects</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawingExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawingexample)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawingExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawingexample)]  
  
 <span data-ttu-id="d6131-112">Para obtener un ejemplo que muestra una manera sencilla de mostrar una imagen sin utilizar <xref:System.Windows.Media.ImageDrawing>, consulte [usar el elemento de imagen](../controls/how-to-use-the-image-element.md).</span><span class="sxs-lookup"><span data-stu-id="d6131-112">For an example showing a simple way to display an image without using <xref:System.Windows.Media.ImageDrawing>, see [Use the Image Element](../controls/how-to-use-the-image-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6131-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6131-113">See also</span></span>

- <xref:System.Windows.Freezable.Freeze%2A>
- <xref:System.Windows.Controls.Image>
- [<span data-ttu-id="d6131-114">Información general sobre objetos Drawing</span><span class="sxs-lookup"><span data-stu-id="d6131-114">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="d6131-115">Información general sobre objetos Freezable</span><span class="sxs-lookup"><span data-stu-id="d6131-115">Freezable Objects Overview</span></span>](../advanced/freezable-objects-overview.md)
- [<span data-ttu-id="d6131-116">PresentationOptions:Freeze (Atributo)</span><span class="sxs-lookup"><span data-stu-id="d6131-116">PresentationOptions:Freeze Attribute</span></span>](../advanced/presentationoptions-freeze-attribute.md)
