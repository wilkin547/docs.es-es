---
title: 'Cómo: Pintar un área con un degradado lineal'
ms.date: 03/30/2017
helpviewer_keywords:
- linear gradients [WPF], painting with
- brushes [WPF], painting with linear gradients
- painting [WPF], with linear gradients
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
ms.openlocfilehash: 76c491632911c48db34d932ba3895278591378a5
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452771"
---
# <a name="how-to-paint-an-area-with-a-linear-gradient"></a><span data-ttu-id="bde59-102">Cómo: Pintar un área con un degradado lineal</span><span class="sxs-lookup"><span data-stu-id="bde59-102">How to: Paint an Area with a Linear Gradient</span></span>
<span data-ttu-id="bde59-103">En este ejemplo se muestra cómo usar la clase <xref:System.Windows.Media.LinearGradientBrush> para pintar un área con un degradado lineal.</span><span class="sxs-lookup"><span data-stu-id="bde59-103">This example shows how to use the <xref:System.Windows.Media.LinearGradientBrush> class to paint an area with a linear gradient.</span></span> <span data-ttu-id="bde59-104">En el ejemplo siguiente, el <xref:System.Windows.Shapes.Shape.Fill%2A> de una <xref:System.Windows.Shapes.Rectangle> se pinta con un degradado lineal diagonal que realiza la transición de amarillo a rojo a azul a verde lima.</span><span class="sxs-lookup"><span data-stu-id="bde59-104">In the following example, the <xref:System.Windows.Shapes.Shape.Fill%2A> of a <xref:System.Windows.Shapes.Rectangle> is painted with a diagonal linear gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bde59-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bde59-105">Example</span></span>  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 <span data-ttu-id="bde59-106">En la ilustración siguiente se muestra el degradado creado en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="bde59-106">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="bde59-107">![Degradado lineal diagonal](./media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span><span class="sxs-lookup"><span data-stu-id="bde59-107">![Diagonal linear gradient](./media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span></span>  
  
 <span data-ttu-id="bde59-108">Para crear un degradado lineal horizontal, cambie el <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> y <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> de la <xref:System.Windows.Media.LinearGradientBrush> a (0, 0.5) y (1, 0.5).</span><span class="sxs-lookup"><span data-stu-id="bde59-108">To create a horizontal linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0,0.5) and (1,0.5).</span></span> <span data-ttu-id="bde59-109">En el ejemplo siguiente, se pinta un <xref:System.Windows.Shapes.Rectangle> con un degradado lineal horizontal.</span><span class="sxs-lookup"><span data-stu-id="bde59-109">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a horizontal linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 <span data-ttu-id="bde59-110">En la ilustración siguiente se muestra el degradado creado en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="bde59-110">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="bde59-111">![Degradado lineal horizontal](./media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span><span class="sxs-lookup"><span data-stu-id="bde59-111">![A horizontal linear gradient](./media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span></span>  
  
 <span data-ttu-id="bde59-112">Para crear un degradado lineal vertical, cambie los <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> y <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> de la <xref:System.Windows.Media.LinearGradientBrush> a (0.5, 0) y (0.5, 1).</span><span class="sxs-lookup"><span data-stu-id="bde59-112">To create a vertical linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0.5,0) and (0.5,1).</span></span> <span data-ttu-id="bde59-113">En el ejemplo siguiente, se pinta un <xref:System.Windows.Shapes.Rectangle> con un degradado lineal vertical.</span><span class="sxs-lookup"><span data-stu-id="bde59-113">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a vertical linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 <span data-ttu-id="bde59-114">En la ilustración siguiente se muestra el degradado creado en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="bde59-114">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="bde59-115">![Degradado lineal vertical](./media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span><span class="sxs-lookup"><span data-stu-id="bde59-115">![Vertical linear gradient](./media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bde59-116">En los ejemplos de este tema se usa el sistema de coordenadas predeterminado para establecer puntos de inicio y extremos.</span><span class="sxs-lookup"><span data-stu-id="bde59-116">The examples in this topic use the default coordinate system for setting start points and end points.</span></span> <span data-ttu-id="bde59-117">El sistema de coordenadas predeterminado es relativo a un rectángulo de selección: 0 indica 0 por ciento del rectángulo de selección y 1 indica el 100 por ciento del cuadro de límite.</span><span class="sxs-lookup"><span data-stu-id="bde59-117">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="bde59-118">Puede cambiar este sistema de coordenadas estableciendo la propiedad <xref:System.Windows.Media.GradientBrush.MappingMode%2A> en el valor <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bde59-118">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="bde59-119">Un sistema de coordenadas absoluto no está relacionado con un rectángulo de selección.</span><span class="sxs-lookup"><span data-stu-id="bde59-119">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="bde59-120">Los valores se interpretan directamente en el espacio local.</span><span class="sxs-lookup"><span data-stu-id="bde59-120">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="bde59-121">Para obtener más ejemplos, vea [ejemplo de pinceles](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span><span class="sxs-lookup"><span data-stu-id="bde59-121">For additional examples, see [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span> <span data-ttu-id="bde59-122">Para obtener más información sobre los degradados y otros tipos de pinceles, consulte [información general sobre el dibujo con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="bde59-122">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>
