---
title: 'Cómo: Pintar un área con una imagen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], painting with
- painting [WPF], with images
- brushes [WPF], painting with images
ms.assetid: 3432c533-1fc7-492d-94ee-0b13d60125ae
ms.openlocfilehash: 92969778c04c6ac634a2964c402d6c3439b96b49
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186049"
---
# <a name="how-to-paint-an-area-with-an-image"></a><span data-ttu-id="63e3b-102">Cómo: Pintar un área con una imagen</span><span class="sxs-lookup"><span data-stu-id="63e3b-102">How to: Paint an Area with an Image</span></span>
<span data-ttu-id="63e3b-103">En este ejemplo se <xref:System.Windows.Media.ImageBrush> muestra cómo utilizar la clase para pintar un área con una imagen.</span><span class="sxs-lookup"><span data-stu-id="63e3b-103">This example shows how to use the <xref:System.Windows.Media.ImageBrush> class to paint an area with an image.</span></span> <span data-ttu-id="63e3b-104">Un <xref:System.Windows.Media.ImageBrush> muestra una sola imagen, que <xref:System.Windows.Media.ImageBrush.ImageSource%2A> se especifica por su propiedad.</span><span class="sxs-lookup"><span data-stu-id="63e3b-104">An <xref:System.Windows.Media.ImageBrush> displays a single image, which is specified by its <xref:System.Windows.Media.ImageBrush.ImageSource%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63e3b-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="63e3b-105">Example</span></span>  
 <span data-ttu-id="63e3b-106">En el ejemplo <xref:System.Windows.Controls.Control.Background%2A> siguiente se pinta <xref:System.Windows.Media.ImageBrush>el de un botón mediante un archivo .</span><span class="sxs-lookup"><span data-stu-id="63e3b-106">The following example paints the <xref:System.Windows.Controls.Control.Background%2A> of a button by using an <xref:System.Windows.Media.ImageBrush>.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 <span data-ttu-id="63e3b-107">De forma <xref:System.Windows.Media.ImageBrush> predeterminada, un estira su imagen para rellenar completamente el área que está pintando.</span><span class="sxs-lookup"><span data-stu-id="63e3b-107">By default, an <xref:System.Windows.Media.ImageBrush> stretches its image to completely fill the area that you are painting.</span></span> <span data-ttu-id="63e3b-108">En el ejemplo anterior, la imagen se ajusta para rellenar el botón, lo que puede distorsionar la imagen.</span><span class="sxs-lookup"><span data-stu-id="63e3b-108">In the preceding example, the image is stretched to fill the button, possibly distorting the image.</span></span> <span data-ttu-id="63e3b-109">Puede controlar este comportamiento <xref:System.Windows.Media.TileBrush.Stretch%2A> estableciendo <xref:System.Windows.Media.TileBrush> <xref:System.Windows.Media.Stretch.Uniform> la <xref:System.Windows.Media.Stretch.UniformToFill>propiedad de to o , lo que hace que el pincel conserve la relación de aspecto de la imagen.</span><span class="sxs-lookup"><span data-stu-id="63e3b-109">You can control this behavior by setting the <xref:System.Windows.Media.TileBrush.Stretch%2A> property of <xref:System.Windows.Media.TileBrush> to <xref:System.Windows.Media.Stretch.Uniform> or <xref:System.Windows.Media.Stretch.UniformToFill>, which causes the brush to preserve the aspect ratio of the image.</span></span>  
  
 <span data-ttu-id="63e3b-110">Si establece <xref:System.Windows.Media.TileBrush.Viewport%2A> las <xref:System.Windows.Media.TileBrush.TileMode%2A> propiedades <xref:System.Windows.Media.ImageBrush>y de un , puede crear un patrón de repetición.</span><span class="sxs-lookup"><span data-stu-id="63e3b-110">If you set the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.TileMode%2A> properties of an <xref:System.Windows.Media.ImageBrush>, you can create a repeating pattern.</span></span> <span data-ttu-id="63e3b-111">En el ejemplo siguiente se pinta un botón mediante un patrón creado a partir de una imagen.</span><span class="sxs-lookup"><span data-stu-id="63e3b-111">The following example paints a button by using a pattern that is created from an image.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 <span data-ttu-id="63e3b-112">Para obtener más <xref:System.Windows.Media.ImageBrush> información acerca de la clase, vea [Pintar con imágenes, dibujos y objetos visuales](painting-with-images-drawings-and-visuals.md).</span><span class="sxs-lookup"><span data-stu-id="63e3b-112">For more information about the <xref:System.Windows.Media.ImageBrush> class, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span>  
  
 <span data-ttu-id="63e3b-113">Este ejemplo de código forma parte de <xref:System.Windows.Media.ImageBrush> un ejemplo más amplio que se proporciona para la clase.</span><span class="sxs-lookup"><span data-stu-id="63e3b-113">This code example is part of a larger example that is provided for the <xref:System.Windows.Media.ImageBrush> class.</span></span> <span data-ttu-id="63e3b-114">Para obtener el ejemplo completo, vea [ImageBrush Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).</span><span class="sxs-lookup"><span data-stu-id="63e3b-114">For the complete sample, see [ImageBrush Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63e3b-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="63e3b-115">See also</span></span>

- [<span data-ttu-id="63e3b-116">Pintar con imágenes, dibujos y elementos visuales</span><span class="sxs-lookup"><span data-stu-id="63e3b-116">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
