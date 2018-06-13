---
title: 'Cómo: Dibujar una imagen usando un objeto ImageDrawing'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], images
- graphics [WPF], drawing images
- images [WPF], drawing
ms.assetid: df28ab41-25fb-4ab3-b51d-7f695b24f55e
ms.openlocfilehash: 2c7771f841fb3b600d4790eb4d484b0a09c45dd5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559884"
---
# <a name="how-to-draw-an-image-using-imagedrawing"></a><span data-ttu-id="1e7d1-102">Cómo: Dibujar una imagen usando un objeto ImageDrawing</span><span class="sxs-lookup"><span data-stu-id="1e7d1-102">How to: Draw an Image Using ImageDrawing</span></span>
<span data-ttu-id="1e7d1-103">Este ejemplo muestra cómo utilizar un <xref:System.Windows.Media.ImageDrawing> para dibujar una imagen.</span><span class="sxs-lookup"><span data-stu-id="1e7d1-103">This example shows how to use an <xref:System.Windows.Media.ImageDrawing> to draw an image.</span></span> <span data-ttu-id="1e7d1-104">Un <xref:System.Windows.Media.ImageDrawing> permite mostrar un <xref:System.Windows.Media.ImageSource> con un <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.DrawingImage>, o <xref:System.Windows.Media.Visual>.</span><span class="sxs-lookup"><span data-stu-id="1e7d1-104">An <xref:System.Windows.Media.ImageDrawing> enables you display an <xref:System.Windows.Media.ImageSource> with a <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.DrawingImage>, or <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="1e7d1-105">Para dibujar una imagen, se crea un <xref:System.Windows.Media.ImageDrawing> y establecer su <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> y <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> propiedades.</span><span class="sxs-lookup"><span data-stu-id="1e7d1-105">To draw an image, you create an <xref:System.Windows.Media.ImageDrawing> and set its <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> and <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> properties.</span></span> <span data-ttu-id="1e7d1-106">El <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> propiedad especifica la imagen para dibujar y la <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> propiedad especifica la posición y el tamaño de cada imagen.</span><span class="sxs-lookup"><span data-stu-id="1e7d1-106">The <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> property specifies the image to draw, and the <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> property specifies the position and size of each image.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e7d1-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1e7d1-107">Example</span></span>  
 <span data-ttu-id="1e7d1-108">En el ejemplo siguiente se crea un dibujo compuesto mediante cuatro <xref:System.Windows.Media.ImageDrawing> objetos.</span><span class="sxs-lookup"><span data-stu-id="1e7d1-108">The following example creates a composite drawing using four <xref:System.Windows.Media.ImageDrawing> objects.</span></span> <span data-ttu-id="1e7d1-109">Este ejemplo produce la siguiente imagen:</span><span class="sxs-lookup"><span data-stu-id="1e7d1-109">This example produces the following image:</span></span>  
  
 <span data-ttu-id="1e7d1-110">![Varios objetos DrawingImage](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagedrawingexample.jpg "graphicsmm_ImageDrawingExample")</span><span class="sxs-lookup"><span data-stu-id="1e7d1-110">![Several DrawingImage objects](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagedrawingexample.jpg "graphicsmm_ImageDrawingExample")</span></span>  
<span data-ttu-id="1e7d1-111">Cuatro objetos ImageDrawing</span><span class="sxs-lookup"><span data-stu-id="1e7d1-111">Four ImageDrawing objects</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawingExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawingexample)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawingExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawingexample)]  
  
 <span data-ttu-id="1e7d1-112">Para obtener un ejemplo que muestra una manera sencilla para mostrar una imagen sin usar <xref:System.Windows.Media.ImageDrawing>, consulte [usar el elemento de imagen](../../../../docs/framework/wpf/controls/how-to-use-the-image-element.md).</span><span class="sxs-lookup"><span data-stu-id="1e7d1-112">For an example showing a simple way to display an image without using <xref:System.Windows.Media.ImageDrawing>, see [Use the Image Element](../../../../docs/framework/wpf/controls/how-to-use-the-image-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e7d1-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e7d1-113">See Also</span></span>  
 <xref:System.Windows.Freezable.Freeze%2A>  
 <xref:System.Windows.Controls.Image>  
 [<span data-ttu-id="1e7d1-114">Información general sobre objetos Drawing</span><span class="sxs-lookup"><span data-stu-id="1e7d1-114">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="1e7d1-115">Información general sobre objetos Freezable</span><span class="sxs-lookup"><span data-stu-id="1e7d1-115">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="1e7d1-116">PresentationOptions:Freeze (Atributo)</span><span class="sxs-lookup"><span data-stu-id="1e7d1-116">PresentationOptions:Freeze Attribute</span></span>](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)
