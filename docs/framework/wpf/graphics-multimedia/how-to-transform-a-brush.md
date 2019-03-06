---
title: Filtrar Transformar un pincel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], rotating contents
- brushes [WPF], Transform property
- rotating contents of brushes [WPF]
ms.assetid: ebada2f9-f01f-4863-9ea2-c2e4e51610f1
ms.openlocfilehash: 990c82b4844ce3ca7f5b553b180280b6b37496ca
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373769"
---
# <a name="how-to-transform-a-brush"></a><span data-ttu-id="50012-102">Procedimiento Transformar un pincel</span><span class="sxs-lookup"><span data-stu-id="50012-102">How to: Transform a Brush</span></span>
<span data-ttu-id="50012-103">En este ejemplo se muestra cómo transformar <xref:System.Windows.Media.Brush> objetos mediante el uso de sus dos propiedades de transformación: <xref:System.Windows.Media.Brush.RelativeTransform%2A> y <xref:System.Windows.Media.Brush.Transform%2A>.</span><span class="sxs-lookup"><span data-stu-id="50012-103">This example shows how to transform <xref:System.Windows.Media.Brush> objects by using their two transformation properties: <xref:System.Windows.Media.Brush.RelativeTransform%2A> and <xref:System.Windows.Media.Brush.Transform%2A>.</span></span>  
  
 <span data-ttu-id="50012-104">Los ejemplos siguientes usan una <xref:System.Windows.Media.RotateTransform> para girar el contenido de un <xref:System.Windows.Media.ImageBrush> 45 grados.</span><span class="sxs-lookup"><span data-stu-id="50012-104">The following examples use a <xref:System.Windows.Media.RotateTransform> to rotate the content of an <xref:System.Windows.Media.ImageBrush> by 45 degrees.</span></span>  
  
 <span data-ttu-id="50012-105">La siguiente ilustración muestra el <xref:System.Windows.Media.ImageBrush> sin un <xref:System.Windows.Media.RotateTransform>, con el <xref:System.Windows.Media.RotateTransform> aplicado a la <xref:System.Windows.Media.Brush.RelativeTransform%2A> propiedad y con el <xref:System.Windows.Media.RotateTransform> aplicado a la <xref:System.Windows.Media.Brush.Transform%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="50012-105">The following illustration shows the <xref:System.Windows.Media.ImageBrush> without a <xref:System.Windows.Media.RotateTransform>, with the <xref:System.Windows.Media.RotateTransform> applied to the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property, and with the <xref:System.Windows.Media.RotateTransform> applied to the <xref:System.Windows.Media.Brush.Transform%2A> property.</span></span>  
  
 <span data-ttu-id="50012-106">![Valores de Brush RelativeTransform y Transform](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")</span><span class="sxs-lookup"><span data-stu-id="50012-106">![Brush RelativeTransform and Transform settings](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")</span></span>  
  
## <a name="example"></a><span data-ttu-id="50012-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="50012-107">Example</span></span>  
 <span data-ttu-id="50012-108">El primer ejemplo se aplica un <xref:System.Windows.Media.RotateTransform> a la <xref:System.Windows.Media.Brush.RelativeTransform%2A> propiedad de un <xref:System.Windows.Media.ImageBrush>.</span><span class="sxs-lookup"><span data-stu-id="50012-108">The first example applies a <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property of an <xref:System.Windows.Media.ImageBrush>.</span></span> <span data-ttu-id="50012-109">El <xref:System.Windows.Media.RotateTransform.CenterX%2A> y <xref:System.Windows.Media.RotateTransform.CenterY%2A> las propiedades de un <xref:System.Windows.Media.RotateTransform> objeto se establecen en 0,5, que es la coordenada relativa del punto central de este contenido.</span><span class="sxs-lookup"><span data-stu-id="50012-109">The <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of a <xref:System.Windows.Media.RotateTransform> object are both set to 0.5, which is the relative coordinate of the center point of this content.</span></span> <span data-ttu-id="50012-110">Como resultado, el <xref:System.Windows.Media.ImageBrush> contenido gira sobre su centro.</span><span class="sxs-lookup"><span data-stu-id="50012-110">As a result, the <xref:System.Windows.Media.ImageBrush> content rotates about its center.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 <span data-ttu-id="50012-111">El segundo ejemplo también se aplica un <xref:System.Windows.Media.RotateTransform> a un <xref:System.Windows.Media.ImageBrush>; sin embargo, este ejemplo se usa el <xref:System.Windows.Media.Brush.Transform%2A> propiedad en lugar de la <xref:System.Windows.Media.Brush.RelativeTransform%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="50012-111">The second example also applies a <xref:System.Windows.Media.RotateTransform> to an <xref:System.Windows.Media.ImageBrush>; however, this example uses the <xref:System.Windows.Media.Brush.Transform%2A> property instead of the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property.</span></span>  
  
 <span data-ttu-id="50012-112">Para girar el pincel sobre su centro, el ejemplo establece la <xref:System.Windows.Media.RotateTransform.CenterX%2A> y <xref:System.Windows.Media.RotateTransform.CenterY%2A> propiedades de la <xref:System.Windows.Media.RotateTransform> objeto en coordenadas absolutas.</span><span class="sxs-lookup"><span data-stu-id="50012-112">To rotate the brush about its center, the example sets the <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of the <xref:System.Windows.Media.RotateTransform> object to absolute coordinates.</span></span> <span data-ttu-id="50012-113">Como el pincel pinta un rectángulo de 175 x 90 píxeles, el punto central del rectángulo es (87,5, 45).</span><span class="sxs-lookup"><span data-stu-id="50012-113">Because the brush paints a rectangle that is 175 by 90 pixels, the center point of the rectangle is (87.5, 45).</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 <span data-ttu-id="50012-114">Para obtener una descripción de cómo el <xref:System.Windows.Media.Brush.RelativeTransform%2A> y <xref:System.Windows.Media.Brush.Transform%2A> propiedades de trabajo, consulte el [información general sobre la transformación de pinceles](brush-transformation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="50012-114">For a description of how the <xref:System.Windows.Media.Brush.RelativeTransform%2A> and <xref:System.Windows.Media.Brush.Transform%2A> properties work, see the [Brush Transformation Overview](brush-transformation-overview.md).</span></span>  
  
 <span data-ttu-id="50012-115">Para ver el ejemplo completo, consulte [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973) (Ejemplo de pinceles).</span><span class="sxs-lookup"><span data-stu-id="50012-115">For the complete sample, see [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="50012-116">Para más información sobre los pinceles, consulte [Información general sobre el dibujo con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="50012-116">For more information about brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50012-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="50012-117">See also</span></span>
- [<span data-ttu-id="50012-118">Información general sobre la transformación de pinceles</span><span class="sxs-lookup"><span data-stu-id="50012-118">Brush Transformation Overview</span></span>](brush-transformation-overview.md)
- [<span data-ttu-id="50012-119">Información general sobre el dibujo con colores sólidos y degradados</span><span class="sxs-lookup"><span data-stu-id="50012-119">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="50012-120">Información general sobre transformaciones</span><span class="sxs-lookup"><span data-stu-id="50012-120">Transforms Overview</span></span>](transforms-overview.md)
