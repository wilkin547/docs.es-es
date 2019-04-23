---
title: Procedimiento Sesgar un elemento
ms.date: 03/30/2017
helpviewer_keywords:
- skewing elements [WPF]
- graphics [WPF], skewing elements
- classes [WPF], SkewTransform
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
ms.openlocfilehash: 47f671f493e7b379c36f9bf4b50ec9d185d10b8a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59144968"
---
# <a name="how-to-skew-an-element"></a><span data-ttu-id="3ff01-102">Procedimiento Sesgar un elemento</span><span class="sxs-lookup"><span data-stu-id="3ff01-102">How to: Skew an Element</span></span>
<span data-ttu-id="3ff01-103">En este ejemplo se muestra cómo usar un <xref:System.Windows.Media.SkewTransform> para sesgar un elemento.</span><span class="sxs-lookup"><span data-stu-id="3ff01-103">This example shows how to use a <xref:System.Windows.Media.SkewTransform> to skew an element.</span></span> <span data-ttu-id="3ff01-104">Un sesgo, también conocido como distorsión, es una transformación que expande el espacio de coordenadas de una manera no uniforme.</span><span class="sxs-lookup"><span data-stu-id="3ff01-104">A skew, which is also known as a shear, is a transformation that stretches the coordinate space in a non-uniform manner.</span></span> <span data-ttu-id="3ff01-105">Un uso típico de un <xref:System.Windows.Media.SkewTransform> para simular [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] profundidad en [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] objetos.</span><span class="sxs-lookup"><span data-stu-id="3ff01-105">One typical use of a <xref:System.Windows.Media.SkewTransform> is for simulating [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] depth in [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] objects.</span></span>  
  
 <span data-ttu-id="3ff01-106">Use la <xref:System.Windows.Media.SkewTransform.CenterX%2A> y <xref:System.Windows.Media.SkewTransform.CenterY%2A> propiedades para especificar el centro de punto de la <xref:System.Windows.Media.SkewTransform>.</span><span class="sxs-lookup"><span data-stu-id="3ff01-106">Use the <xref:System.Windows.Media.SkewTransform.CenterX%2A> and <xref:System.Windows.Media.SkewTransform.CenterY%2A> properties to specify the center point of the <xref:System.Windows.Media.SkewTransform>.</span></span>  
  
 <span data-ttu-id="3ff01-107">Use la <xref:System.Windows.Media.SkewTransform.AngleX%2A> y <xref:System.Windows.Media.SkewTransform.AngleY%2A> propiedades para especificar el ángulo de sesgado de los ejes x y y y para sesgar el sistema de coordenadas actual a lo largo de estos ejes.</span><span class="sxs-lookup"><span data-stu-id="3ff01-107">Use the <xref:System.Windows.Media.SkewTransform.AngleX%2A> and <xref:System.Windows.Media.SkewTransform.AngleY%2A> properties to specify the skew angle of the x-axis and y-axis, and to skew the current coordinate system along these axes.</span></span>  
  
 <span data-ttu-id="3ff01-108">Para predecir el efecto de una transformación de sesgo, considere la posibilidad de que <xref:System.Windows.Media.SkewTransform.AngleX%2A> sesga los valores del eje x en relación con el sistema de coordenadas original.</span><span class="sxs-lookup"><span data-stu-id="3ff01-108">To predict the effect of a skew transformation, consider that <xref:System.Windows.Media.SkewTransform.AngleX%2A> skews x-axis values relative to the original coordinate system.</span></span> <span data-ttu-id="3ff01-109">Por lo tanto, para un <xref:System.Windows.Media.SkewTransform.AngleX%2A> de 30, el eje y gira 30 grados a través del origen y sesga los valores de x-30 grados desde ese origen.</span><span class="sxs-lookup"><span data-stu-id="3ff01-109">Therefore, for an <xref:System.Windows.Media.SkewTransform.AngleX%2A> of 30, the y-axis rotates 30 degrees through the origin and skews the values in x- by 30 degrees from that origin.</span></span> <span data-ttu-id="3ff01-110">Del mismo modo, un <xref:System.Windows.Media.SkewTransform.AngleY%2A> de 30 sesga los valores y de la forma 30 grados desde el origen.</span><span class="sxs-lookup"><span data-stu-id="3ff01-110">Likewise, an <xref:System.Windows.Media.SkewTransform.AngleY%2A> of 30 skews the y- values of the shape by 30 degrees from the origin.</span></span> <span data-ttu-id="3ff01-111">Tenga en cuenta que esto no tiene el mismo efecto que trasladar (mover) el sistema de coordenadas 30 grados en x o y.</span><span class="sxs-lookup"><span data-stu-id="3ff01-111">Note that this is not the same effect as translating (moving) the coordinate system by 30 degrees in x- or y-.</span></span>  
  
 <span data-ttu-id="3ff01-112">El ejemplo siguiente aplica un sesgo horizontal de 45 grados a un <xref:System.Windows.Shapes.Rectangle> desde un punto central de (0,0).</span><span class="sxs-lookup"><span data-stu-id="3ff01-112">The following example applies a horizontal skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (0,0).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ff01-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3ff01-113">Example</span></span>  
 [!code-xaml[transformsSample#41](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 <span data-ttu-id="3ff01-114">El ejemplo siguiente aplica un sesgo horizontal de 45 grados a un <xref:System.Windows.Shapes.Rectangle> desde un punto central de (25,25).</span><span class="sxs-lookup"><span data-stu-id="3ff01-114">The following example applies a horizontal skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (25,25).</span></span>  
  
 [!code-xaml[transformsSample#42](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 <span data-ttu-id="3ff01-115">El ejemplo siguiente aplica un sesgo vertical de 45 grados a un <xref:System.Windows.Shapes.Rectangle> desde un punto central de (25,25).</span><span class="sxs-lookup"><span data-stu-id="3ff01-115">The following example applies a vertical skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (25,25).</span></span>  
  
 [!code-xaml[transformsSample#43](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 <span data-ttu-id="3ff01-116">La ilustración siguiente muestra los diferentes sesgos que se usan en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="3ff01-116">The following illustration shows the different skews that are used in this example.</span></span>  
  
 <span data-ttu-id="3ff01-117">![Ejemplos de SkewTransform](./media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")</span><span class="sxs-lookup"><span data-stu-id="3ff01-117">![SkewTransform examples](./media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")</span></span>  
<span data-ttu-id="3ff01-118">Los tres ejemplos de SkewTransform ilustrados</span><span class="sxs-lookup"><span data-stu-id="3ff01-118">The three SkewTransform examples illustrated</span></span>  
  
 <span data-ttu-id="3ff01-119">Para ver el ejemplo completo, consulte [Ejemplo de transformaciones 2D](https://go.microsoft.com/fwlink/?LinkID=158252).</span><span class="sxs-lookup"><span data-stu-id="3ff01-119">For the complete sample, see [2-D Transforms Sample](https://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ff01-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ff01-120">See also</span></span>

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.SkewTransform>
- [<span data-ttu-id="3ff01-121">Información general sobre transformaciones</span><span class="sxs-lookup"><span data-stu-id="3ff01-121">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="3ff01-122">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="3ff01-122">How-to Topics</span></span>](transformations-how-to-topics.md)
