---
title: Procedimiento Pintar un área con un degradado lineal
ms.date: 03/30/2017
helpviewer_keywords:
- linear gradients [WPF], painting with
- brushes [WPF], painting with linear gradients
- painting [WPF], with linear gradients
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
ms.openlocfilehash: c48ff13811d784ecc7042b73b964a9e6f2d42a34
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57367250"
---
# <a name="how-to-paint-an-area-with-a-linear-gradient"></a><span data-ttu-id="fbd06-102">Procedimiento Pintar un área con un degradado lineal</span><span class="sxs-lookup"><span data-stu-id="fbd06-102">How to: Paint an Area with a Linear Gradient</span></span>
<span data-ttu-id="fbd06-103">En este ejemplo se muestra cómo usar el <xref:System.Windows.Media.LinearGradientBrush> clase para pintar un área con un degradado lineal.</span><span class="sxs-lookup"><span data-stu-id="fbd06-103">This example shows how to use the <xref:System.Windows.Media.LinearGradientBrush> class to paint an area with a linear gradient.</span></span> <span data-ttu-id="fbd06-104">En el ejemplo siguiente, la <xref:System.Windows.Shapes.Shape.Fill%2A> de un <xref:System.Windows.Shapes.Rectangle> se pinta con un degradado lineal diagonal que realiza la transición de amarillo a rojo a azul para verde lima.</span><span class="sxs-lookup"><span data-stu-id="fbd06-104">In the following example, the <xref:System.Windows.Shapes.Shape.Fill%2A> of a <xref:System.Windows.Shapes.Rectangle> is painted with a diagonal linear gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbd06-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fbd06-105">Example</span></span>  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 <span data-ttu-id="fbd06-106">La siguiente ilustración muestra el degradado que se creó en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="fbd06-106">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="fbd06-107">![Degradado lineal diagonal](./media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span><span class="sxs-lookup"><span data-stu-id="fbd06-107">![Diagonal linear gradient](./media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span></span>  
  
 <span data-ttu-id="fbd06-108">Para crear un degradado lineal horizontal, cambie el <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> y <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> de la <xref:System.Windows.Media.LinearGradientBrush> a (0,0.5) y (1,0.5).</span><span class="sxs-lookup"><span data-stu-id="fbd06-108">To create a horizontal linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0,0.5) and (1,0.5).</span></span> <span data-ttu-id="fbd06-109">En el ejemplo siguiente, un <xref:System.Windows.Shapes.Rectangle> se pinta con un degradado lineal horizontal.</span><span class="sxs-lookup"><span data-stu-id="fbd06-109">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a horizontal linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 <span data-ttu-id="fbd06-110">La siguiente ilustración muestra el degradado que se creó en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="fbd06-110">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="fbd06-111">![Un degradado lineal horizontal](./media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span><span class="sxs-lookup"><span data-stu-id="fbd06-111">![A horizontal linear gradient](./media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span></span>  
  
 <span data-ttu-id="fbd06-112">Para crear un degradado lineal vertical, cambie el <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> y <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> de la <xref:System.Windows.Media.LinearGradientBrush> a (0.5,0) y (0.5,1).</span><span class="sxs-lookup"><span data-stu-id="fbd06-112">To create a vertical linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0.5,0) and (0.5,1).</span></span> <span data-ttu-id="fbd06-113">En el ejemplo siguiente, un <xref:System.Windows.Shapes.Rectangle> se pinta con un degradado lineal vertical.</span><span class="sxs-lookup"><span data-stu-id="fbd06-113">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a vertical linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 <span data-ttu-id="fbd06-114">La siguiente ilustración muestra el degradado que se creó en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="fbd06-114">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="fbd06-115">![Degradado lineal vertical](./media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span><span class="sxs-lookup"><span data-stu-id="fbd06-115">![Vertical linear gradient](./media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fbd06-116">Los ejemplos de este tema usan el sistema de coordenadas predeterminado para establecer puntos de inicio y finales.</span><span class="sxs-lookup"><span data-stu-id="fbd06-116">The examples in this topic use the default coordinate system for setting start points and end points.</span></span> <span data-ttu-id="fbd06-117">El sistema de coordenadas predeterminado está relacionado con un rectángulo: 0 indica 0 por ciento del rectángulo, y 1 indica un 100 por cien del rectángulo.</span><span class="sxs-lookup"><span data-stu-id="fbd06-117">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="fbd06-118">Puede cambiar este sistema de coordenadas estableciendo el <xref:System.Windows.Media.GradientBrush.MappingMode%2A> valor para la propiedad <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fbd06-118">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="fbd06-119">Un sistema de coordenadas absoluto no está relacionado con un rectángulo de selección.</span><span class="sxs-lookup"><span data-stu-id="fbd06-119">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="fbd06-120">Los valores se interpretan directamente en el espacio local.</span><span class="sxs-lookup"><span data-stu-id="fbd06-120">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="fbd06-121">Para obtener ejemplos adicionales, consulte [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="fbd06-121">For additional examples, see [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="fbd06-122">Para obtener más información acerca de los degradados y otros tipos de pinceles, vea [el dibujo con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fbd06-122">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>
