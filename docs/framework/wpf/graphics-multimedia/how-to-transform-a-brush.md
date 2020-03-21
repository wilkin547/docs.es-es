---
title: 'Cómo: Transformar un pincel'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], rotating contents
- brushes [WPF], Transform property
- rotating contents of brushes [WPF]
ms.assetid: ebada2f9-f01f-4863-9ea2-c2e4e51610f1
ms.openlocfilehash: b4484e2fc1ae3e969b02b1d8f3ae4ab2a035558e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187335"
---
# <a name="how-to-transform-a-brush"></a><span data-ttu-id="44a02-102">Cómo: Transformar un pincel</span><span class="sxs-lookup"><span data-stu-id="44a02-102">How to: Transform a Brush</span></span>
<span data-ttu-id="44a02-103">En este ejemplo <xref:System.Windows.Media.Brush> se muestra cómo transformar <xref:System.Windows.Media.Brush.RelativeTransform%2A> objetos mediante sus dos propiedades de transformación: y <xref:System.Windows.Media.Brush.Transform%2A>.</span><span class="sxs-lookup"><span data-stu-id="44a02-103">This example shows how to transform <xref:System.Windows.Media.Brush> objects by using their two transformation properties: <xref:System.Windows.Media.Brush.RelativeTransform%2A> and <xref:System.Windows.Media.Brush.Transform%2A>.</span></span>  
  
 <span data-ttu-id="44a02-104">En los ejemplos <xref:System.Windows.Media.RotateTransform> siguientes se usa <xref:System.Windows.Media.ImageBrush> a para rotar el contenido de un 45 grados.</span><span class="sxs-lookup"><span data-stu-id="44a02-104">The following examples use a <xref:System.Windows.Media.RotateTransform> to rotate the content of an <xref:System.Windows.Media.ImageBrush> by 45 degrees.</span></span>  
  
 <span data-ttu-id="44a02-105">En la ilustración <xref:System.Windows.Media.RotateTransform>siguiente se <xref:System.Windows.Media.RotateTransform> muestra <xref:System.Windows.Media.Brush.RelativeTransform%2A> el <xref:System.Windows.Media.ImageBrush> sin <xref:System.Windows.Media.RotateTransform> un , <xref:System.Windows.Media.Brush.Transform%2A> con el aplicado a la propiedad y con el aplicado a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="44a02-105">The following illustration shows the <xref:System.Windows.Media.ImageBrush> without a <xref:System.Windows.Media.RotateTransform>, with the <xref:System.Windows.Media.RotateTransform> applied to the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property, and with the <xref:System.Windows.Media.RotateTransform> applied to the <xref:System.Windows.Media.Brush.Transform%2A> property.</span></span>  
  
 <span data-ttu-id="44a02-106">![Valores de Brush RelativeTransform y Transform](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")</span><span class="sxs-lookup"><span data-stu-id="44a02-106">![Brush RelativeTransform and Transform settings](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")</span></span>  
  
## <a name="example"></a><span data-ttu-id="44a02-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="44a02-107">Example</span></span>  
 <span data-ttu-id="44a02-108">El primer ejemplo <xref:System.Windows.Media.RotateTransform> aplica <xref:System.Windows.Media.Brush.RelativeTransform%2A> a <xref:System.Windows.Media.ImageBrush>la propiedad de un archivo .</span><span class="sxs-lookup"><span data-stu-id="44a02-108">The first example applies a <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property of an <xref:System.Windows.Media.ImageBrush>.</span></span> <span data-ttu-id="44a02-109">Las <xref:System.Windows.Media.RotateTransform.CenterX%2A> <xref:System.Windows.Media.RotateTransform.CenterY%2A> propiedades y <xref:System.Windows.Media.RotateTransform> propiedades de un objeto se establecen en 0,5, que es la coordenada relativa del punto central de este contenido.</span><span class="sxs-lookup"><span data-stu-id="44a02-109">The <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of a <xref:System.Windows.Media.RotateTransform> object are both set to 0.5, which is the relative coordinate of the center point of this content.</span></span> <span data-ttu-id="44a02-110">Como resultado, <xref:System.Windows.Media.ImageBrush> el contenido gira alrededor de su centro.</span><span class="sxs-lookup"><span data-stu-id="44a02-110">As a result, the <xref:System.Windows.Media.ImageBrush> content rotates about its center.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 <span data-ttu-id="44a02-111">El segundo ejemplo <xref:System.Windows.Media.RotateTransform> también <xref:System.Windows.Media.ImageBrush>aplica a a un ; sin embargo, <xref:System.Windows.Media.Brush.Transform%2A> en este <xref:System.Windows.Media.Brush.RelativeTransform%2A> ejemplo se utiliza la propiedad en lugar de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="44a02-111">The second example also applies a <xref:System.Windows.Media.RotateTransform> to an <xref:System.Windows.Media.ImageBrush>; however, this example uses the <xref:System.Windows.Media.Brush.Transform%2A> property instead of the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property.</span></span>  
  
 <span data-ttu-id="44a02-112">Para girar el pincel alrededor de <xref:System.Windows.Media.RotateTransform.CenterX%2A> su <xref:System.Windows.Media.RotateTransform.CenterY%2A> centro, <xref:System.Windows.Media.RotateTransform> el ejemplo establece las propiedades y las propiedades del objeto en coordenadas absolutas.</span><span class="sxs-lookup"><span data-stu-id="44a02-112">To rotate the brush about its center, the example sets the <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of the <xref:System.Windows.Media.RotateTransform> object to absolute coordinates.</span></span> <span data-ttu-id="44a02-113">Como el pincel pinta un rectángulo de 175 x 90 píxeles, el punto central del rectángulo es (87,5, 45).</span><span class="sxs-lookup"><span data-stu-id="44a02-113">Because the brush paints a rectangle that is 175 by 90 pixels, the center point of the rectangle is (87.5, 45).</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 <span data-ttu-id="44a02-114">Para obtener una <xref:System.Windows.Media.Brush.RelativeTransform%2A> descripción de cómo funcionan las <xref:System.Windows.Media.Brush.Transform%2A> propiedades, vea Información general sobre la transformación de [pinceles](brush-transformation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="44a02-114">For a description of how the <xref:System.Windows.Media.Brush.RelativeTransform%2A> and <xref:System.Windows.Media.Brush.Transform%2A> properties work, see the [Brush Transformation Overview](brush-transformation-overview.md).</span></span>  
  
 <span data-ttu-id="44a02-115">Para ver el ejemplo completo, consulte [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes) (Ejemplo de pinceles).</span><span class="sxs-lookup"><span data-stu-id="44a02-115">For the complete sample, see [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span> <span data-ttu-id="44a02-116">Para más información sobre los pinceles, consulte [Información general sobre el dibujo con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="44a02-116">For more information about brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44a02-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="44a02-117">See also</span></span>

- [<span data-ttu-id="44a02-118">Información general sobre la transformación de pinceles</span><span class="sxs-lookup"><span data-stu-id="44a02-118">Brush Transformation Overview</span></span>](brush-transformation-overview.md)
- [<span data-ttu-id="44a02-119">Información general sobre el dibujo con colores sólidos y degradados</span><span class="sxs-lookup"><span data-stu-id="44a02-119">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="44a02-120">Información general sobre transformaciones</span><span class="sxs-lookup"><span data-stu-id="44a02-120">Transforms Overview</span></span>](transforms-overview.md)
