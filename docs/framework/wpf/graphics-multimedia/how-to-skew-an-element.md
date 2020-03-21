---
title: 'Cómo: Sesgar un elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- skewing elements [WPF]
- graphics [WPF], skewing elements
- classes [WPF], SkewTransform
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
ms.openlocfilehash: 10b00044c1c518641281e2e72cdb5a68474b5170
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112029"
---
# <a name="how-to-skew-an-element"></a><span data-ttu-id="534ac-102">Cómo: Sesgar un elemento</span><span class="sxs-lookup"><span data-stu-id="534ac-102">How to: Skew an Element</span></span>
<span data-ttu-id="534ac-103">En este ejemplo se <xref:System.Windows.Media.SkewTransform> muestra cómo utilizar a para sesgar un elemento.</span><span class="sxs-lookup"><span data-stu-id="534ac-103">This example shows how to use a <xref:System.Windows.Media.SkewTransform> to skew an element.</span></span> <span data-ttu-id="534ac-104">Un sesgo, también conocido como distorsión, es una transformación que expande el espacio de coordenadas de una manera no uniforme.</span><span class="sxs-lookup"><span data-stu-id="534ac-104">A skew, which is also known as a shear, is a transformation that stretches the coordinate space in a non-uniform manner.</span></span> <span data-ttu-id="534ac-105">Un uso típico <xref:System.Windows.Media.SkewTransform> de a es para simular la profundidad 3D en objetos 2D.</span><span class="sxs-lookup"><span data-stu-id="534ac-105">One typical use of a <xref:System.Windows.Media.SkewTransform> is for simulating 3D depth in 2D objects.</span></span>  
  
 <span data-ttu-id="534ac-106">Utilice <xref:System.Windows.Media.SkewTransform.CenterX%2A> las <xref:System.Windows.Media.SkewTransform.CenterY%2A> propiedades y para especificar <xref:System.Windows.Media.SkewTransform>el punto central del archivo .</span><span class="sxs-lookup"><span data-stu-id="534ac-106">Use the <xref:System.Windows.Media.SkewTransform.CenterX%2A> and <xref:System.Windows.Media.SkewTransform.CenterY%2A> properties to specify the center point of the <xref:System.Windows.Media.SkewTransform>.</span></span>  
  
 <span data-ttu-id="534ac-107">Utilice <xref:System.Windows.Media.SkewTransform.AngleX%2A> las <xref:System.Windows.Media.SkewTransform.AngleY%2A> propiedades y para especificar el ángulo de sesgo del eje X y el eje Y, y para sesgar el sistema de coordenadas actual a lo largo de estos ejes.</span><span class="sxs-lookup"><span data-stu-id="534ac-107">Use the <xref:System.Windows.Media.SkewTransform.AngleX%2A> and <xref:System.Windows.Media.SkewTransform.AngleY%2A> properties to specify the skew angle of the x-axis and y-axis, and to skew the current coordinate system along these axes.</span></span>  
  
 <span data-ttu-id="534ac-108">Para predecir el efecto de una <xref:System.Windows.Media.SkewTransform.AngleX%2A> transformación de sesgo, tenga en cuenta que sesga los valores del eje X en relación con el sistema de coordenadas original.</span><span class="sxs-lookup"><span data-stu-id="534ac-108">To predict the effect of a skew transformation, consider that <xref:System.Windows.Media.SkewTransform.AngleX%2A> skews x-axis values relative to the original coordinate system.</span></span> <span data-ttu-id="534ac-109">Por lo <xref:System.Windows.Media.SkewTransform.AngleX%2A> tanto, para un de 30, el eje Y gira 30 grados a través del origen y sesga los valores en x- por 30 grados desde ese origen.</span><span class="sxs-lookup"><span data-stu-id="534ac-109">Therefore, for an <xref:System.Windows.Media.SkewTransform.AngleX%2A> of 30, the y-axis rotates 30 degrees through the origin and skews the values in x- by 30 degrees from that origin.</span></span> <span data-ttu-id="534ac-110">Del mismo <xref:System.Windows.Media.SkewTransform.AngleY%2A> modo, un de 30 sesga los valores y de la forma en 30 grados desde el origen.</span><span class="sxs-lookup"><span data-stu-id="534ac-110">Likewise, an <xref:System.Windows.Media.SkewTransform.AngleY%2A> of 30 skews the y- values of the shape by 30 degrees from the origin.</span></span> <span data-ttu-id="534ac-111">Tenga en cuenta que esto no tiene el mismo efecto que trasladar (mover) el sistema de coordenadas 30 grados en x o y.</span><span class="sxs-lookup"><span data-stu-id="534ac-111">Note that this is not the same effect as translating (moving) the coordinate system by 30 degrees in x- or y-.</span></span>  
  
 <span data-ttu-id="534ac-112">En el ejemplo siguiente se aplica un <xref:System.Windows.Shapes.Rectangle> sesgo horizontal de 45 grados a un punto central de (0,0).</span><span class="sxs-lookup"><span data-stu-id="534ac-112">The following example applies a horizontal skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (0,0).</span></span>  
  
## <a name="example"></a><span data-ttu-id="534ac-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="534ac-113">Example</span></span>  
 [!code-xaml[transformsSample#41](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 <span data-ttu-id="534ac-114">En el ejemplo siguiente se aplica un <xref:System.Windows.Shapes.Rectangle> sesgo horizontal de 45 grados a un punto central de (25,25).</span><span class="sxs-lookup"><span data-stu-id="534ac-114">The following example applies a horizontal skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (25,25).</span></span>  
  
 [!code-xaml[transformsSample#42](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 <span data-ttu-id="534ac-115">En el ejemplo siguiente se aplica un <xref:System.Windows.Shapes.Rectangle> sesgo vertical de 45 grados a un punto central de (25,25).</span><span class="sxs-lookup"><span data-stu-id="534ac-115">The following example applies a vertical skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (25,25).</span></span>  
  
 [!code-xaml[transformsSample#43](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 <span data-ttu-id="534ac-116">La ilustración siguiente muestra los diferentes sesgos que se usan en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="534ac-116">The following illustration shows the different skews that are used in this example.</span></span>  
  
 <span data-ttu-id="534ac-117">![Ejemplos de SkewTransform](./media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")</span><span class="sxs-lookup"><span data-stu-id="534ac-117">![SkewTransform examples](./media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")</span></span>  
<span data-ttu-id="534ac-118">Los tres ejemplos de SkewTransform ilustrados</span><span class="sxs-lookup"><span data-stu-id="534ac-118">The three SkewTransform examples illustrated</span></span>  
  
 <span data-ttu-id="534ac-119">Para ver el ejemplo completo, consulte Ejemplo de [transformaciones 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span><span class="sxs-lookup"><span data-stu-id="534ac-119">For the complete sample, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="534ac-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="534ac-120">See also</span></span>

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.SkewTransform>
- [<span data-ttu-id="534ac-121">Información general sobre transformaciones</span><span class="sxs-lookup"><span data-stu-id="534ac-121">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="534ac-122">Temas de información</span><span class="sxs-lookup"><span data-stu-id="534ac-122">How-to Topics</span></span>](transformations-how-to-topics.md)
