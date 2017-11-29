---
title: "Cómo: Pintar un área con un degradado lineal"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- linear gradients [WPF], painting with
- brushes [WPF], painting with linear gradients
- painting [WPF], with linear gradients
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dcc37651d6f1f304f15d3244c2504517a2a9fb76
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-paint-an-area-with-a-linear-gradient"></a><span data-ttu-id="34257-102">Cómo: Pintar un área con un degradado lineal</span><span class="sxs-lookup"><span data-stu-id="34257-102">How to: Paint an Area with a Linear Gradient</span></span>
<span data-ttu-id="34257-103">Este ejemplo muestra cómo utilizar la <xref:System.Windows.Media.LinearGradientBrush> clase para pintar un área con un degradado lineal.</span><span class="sxs-lookup"><span data-stu-id="34257-103">This example shows how to use the <xref:System.Windows.Media.LinearGradientBrush> class to paint an area with a linear gradient.</span></span> <span data-ttu-id="34257-104">En el ejemplo siguiente, la <xref:System.Windows.Shapes.Shape.Fill%2A> de un <xref:System.Windows.Shapes.Rectangle> se pinta con un degradado lineal diagonal que realiza la transición de amarillo a rojo a azul para Lima verde.</span><span class="sxs-lookup"><span data-stu-id="34257-104">In the following example, the <xref:System.Windows.Shapes.Shape.Fill%2A> of a <xref:System.Windows.Shapes.Rectangle> is painted with a diagonal linear gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34257-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="34257-105">Example</span></span>  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 <span data-ttu-id="34257-106">En la siguiente ilustración muestra el degradado creado en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="34257-106">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="34257-107">![Degradado lineal diagonal](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span><span class="sxs-lookup"><span data-stu-id="34257-107">![Diagonal linear gradient](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span></span>  
  
 <span data-ttu-id="34257-108">Para crear un degradado lineal horizontal, cambie la <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> y <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> de la <xref:System.Windows.Media.LinearGradientBrush> a (0,0.5) y (1,0.5).</span><span class="sxs-lookup"><span data-stu-id="34257-108">To create a horizontal linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0,0.5) and (1,0.5).</span></span> <span data-ttu-id="34257-109">En el ejemplo siguiente, un <xref:System.Windows.Shapes.Rectangle> se pinta con un degradado lineal horizontal.</span><span class="sxs-lookup"><span data-stu-id="34257-109">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a horizontal linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 <span data-ttu-id="34257-110">En la siguiente ilustración muestra el degradado creado en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="34257-110">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="34257-111">![Un degradado lineal horizontal](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span><span class="sxs-lookup"><span data-stu-id="34257-111">![A horizontal linear gradient](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span></span>  
  
 <span data-ttu-id="34257-112">Para crear un degradado lineal vertical, cambie la <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> y <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> de la <xref:System.Windows.Media.LinearGradientBrush> a (0.5,0) y (0.5,1).</span><span class="sxs-lookup"><span data-stu-id="34257-112">To create a vertical linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0.5,0) and (0.5,1).</span></span> <span data-ttu-id="34257-113">En el ejemplo siguiente, un <xref:System.Windows.Shapes.Rectangle> se pinta con un degradado lineal vertical.</span><span class="sxs-lookup"><span data-stu-id="34257-113">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a vertical linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 <span data-ttu-id="34257-114">En la siguiente ilustración muestra el degradado creado en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="34257-114">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="34257-115">![Degradado lineal vertical](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span><span class="sxs-lookup"><span data-stu-id="34257-115">![Vertical linear gradient](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="34257-116">Los ejemplos en este tema usan el sistema de coordenadas predeterminado para establecer puntos de inicio y finales.</span><span class="sxs-lookup"><span data-stu-id="34257-116">The examples in this topic use the default coordinate system for setting start points and end points.</span></span> <span data-ttu-id="34257-117">El sistema de coordenadas predeterminado es relativo a un cuadro de límite: 0 indica un 0 por ciento del cuadro de límite y 1 indica un 100 por cien del cuadro de límite.</span><span class="sxs-lookup"><span data-stu-id="34257-117">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="34257-118">Puede cambiar este sistema de coordenadas estableciendo la <xref:System.Windows.Media.GradientBrush.MappingMode%2A> valor para la propiedad <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="34257-118">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="34257-119">Un sistema de coordenadas absoluto no está relacionado con un rectángulo de selección.</span><span class="sxs-lookup"><span data-stu-id="34257-119">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="34257-120">Los valores se interpretan directamente en el espacio local.</span><span class="sxs-lookup"><span data-stu-id="34257-120">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="34257-121">Para obtener ejemplos adicionales, vea [ejemplo pinceles](http://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="34257-121">For additional examples, see [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="34257-122">Para obtener más información acerca de los degradados y otros tipos de pinceles, consulte [pintar con colores sólidos y degradados información general sobre](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="34257-122">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span></span>
