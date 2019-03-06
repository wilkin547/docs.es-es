---
title: Filtrar Pintar un área con una imagen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], painting with
- painting [WPF], with images
- brushes [WPF], painting with images
ms.assetid: 3432c533-1fc7-492d-94ee-0b13d60125ae
ms.openlocfilehash: c1db803aacad85ce90fec519b5eabdd8df7bb584
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369128"
---
# <a name="how-to-paint-an-area-with-an-image"></a><span data-ttu-id="35d7a-102">Filtrar Pintar un área con una imagen</span><span class="sxs-lookup"><span data-stu-id="35d7a-102">How to: Paint an Area with an Image</span></span>
<span data-ttu-id="35d7a-103">En este ejemplo se muestra cómo usar el <xref:System.Windows.Media.ImageBrush> clase para pintar un área con una imagen.</span><span class="sxs-lookup"><span data-stu-id="35d7a-103">This example shows how to use the <xref:System.Windows.Media.ImageBrush> class to paint an area with an image.</span></span> <span data-ttu-id="35d7a-104">Un <xref:System.Windows.Media.ImageBrush> muestra una sola imagen, que se especifica mediante su <xref:System.Windows.Media.ImageBrush.ImageSource%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="35d7a-104">An <xref:System.Windows.Media.ImageBrush> displays a single image, which is specified by its <xref:System.Windows.Media.ImageBrush.ImageSource%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35d7a-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="35d7a-105">Example</span></span>  
 <span data-ttu-id="35d7a-106">Las operaciones de pintura de ejemplo siguiente la <xref:System.Windows.Controls.Control.Background%2A> de un botón mediante el uso de un <xref:System.Windows.Media.ImageBrush>.</span><span class="sxs-lookup"><span data-stu-id="35d7a-106">The following example paints the <xref:System.Windows.Controls.Control.Background%2A> of a button by using an <xref:System.Windows.Media.ImageBrush>.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 <span data-ttu-id="35d7a-107">De forma predeterminada, un <xref:System.Windows.Media.ImageBrush> ajusta su imagen hasta rellenar completamente el área que se está pintando.</span><span class="sxs-lookup"><span data-stu-id="35d7a-107">By default, an <xref:System.Windows.Media.ImageBrush> stretches its image to completely fill the area that you are painting.</span></span> <span data-ttu-id="35d7a-108">En el ejemplo anterior, la imagen se ajusta para rellenar el botón, lo que puede distorsionar la imagen.</span><span class="sxs-lookup"><span data-stu-id="35d7a-108">In the preceding example, the image is stretched to fill the button, possibly distorting the image.</span></span> <span data-ttu-id="35d7a-109">Puede controlar este comportamiento estableciendo el <xref:System.Windows.Media.TileBrush.Stretch%2A> propiedad de <xref:System.Windows.Media.TileBrush> a <xref:System.Windows.Media.Stretch.Uniform> o <xref:System.Windows.Media.Stretch.UniformToFill>, lo que hace que el pincel conserve la relación de aspecto de la imagen.</span><span class="sxs-lookup"><span data-stu-id="35d7a-109">You can control this behavior by setting the <xref:System.Windows.Media.TileBrush.Stretch%2A> property of <xref:System.Windows.Media.TileBrush> to <xref:System.Windows.Media.Stretch.Uniform> or <xref:System.Windows.Media.Stretch.UniformToFill>, which causes the brush to preserve the aspect ratio of the image.</span></span>  
  
 <span data-ttu-id="35d7a-110">Si establece la <xref:System.Windows.Media.TileBrush.Viewport%2A> y <xref:System.Windows.Media.TileBrush.TileMode%2A> las propiedades de un <xref:System.Windows.Media.ImageBrush>, puede crear un patrón de repetición.</span><span class="sxs-lookup"><span data-stu-id="35d7a-110">If you set the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.TileMode%2A> properties of an <xref:System.Windows.Media.ImageBrush>, you can create a repeating pattern.</span></span> <span data-ttu-id="35d7a-111">En el ejemplo siguiente se pinta un botón mediante un patrón creado a partir de una imagen.</span><span class="sxs-lookup"><span data-stu-id="35d7a-111">The following example paints a button by using a pattern that is created from an image.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 <span data-ttu-id="35d7a-112">Para obtener más información sobre la <xref:System.Windows.Media.ImageBrush> de clases, vea [pintar con imágenes, dibujos y elementos visuales](painting-with-images-drawings-and-visuals.md).</span><span class="sxs-lookup"><span data-stu-id="35d7a-112">For more information about the <xref:System.Windows.Media.ImageBrush> class, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span>  
  
 <span data-ttu-id="35d7a-113">Este ejemplo de código forma parte de un ejemplo más extenso proporcionado para el <xref:System.Windows.Media.ImageBrush> clase.</span><span class="sxs-lookup"><span data-stu-id="35d7a-113">This code example is part of a larger example that is provided for the <xref:System.Windows.Media.ImageBrush> class.</span></span> <span data-ttu-id="35d7a-114">Para obtener un ejemplo completo, vea [ejemplo de ImageBrush](https://go.microsoft.com/fwlink/?LinkID=160005).</span><span class="sxs-lookup"><span data-stu-id="35d7a-114">For the complete sample, see [ImageBrush Sample](https://go.microsoft.com/fwlink/?LinkID=160005).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35d7a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="35d7a-115">See also</span></span>
- [<span data-ttu-id="35d7a-116">Pintar con imágenes, dibujos y elementos visuales</span><span class="sxs-lookup"><span data-stu-id="35d7a-116">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
