---
title: Procedimiento Pintar un área con un degradado radial
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with radial gradients
- radial gradients [WPF], painting with
- painting [WPF], with radial gradients
ms.assetid: b5d0fc8a-8986-4796-b003-a75b41a48928
ms.openlocfilehash: c3bcc11dea4b1f223f629415591ab03588881dde
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921840"
---
# <a name="how-to-paint-an-area-with-a-radial-gradient"></a><span data-ttu-id="d8ee6-102">Procedimiento Pintar un área con un degradado radial</span><span class="sxs-lookup"><span data-stu-id="d8ee6-102">How to: Paint an Area with a Radial Gradient</span></span>
<span data-ttu-id="d8ee6-103">En este ejemplo se muestra cómo usar el <xref:System.Windows.Media.RadialGradientBrush> clase para pintar un área con un degradado radial.</span><span class="sxs-lookup"><span data-stu-id="d8ee6-103">This example shows how to use the <xref:System.Windows.Media.RadialGradientBrush> class to paint an area with a radial gradient.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8ee6-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d8ee6-104">Example</span></span>  
 <span data-ttu-id="d8ee6-105">En el ejemplo siguiente se usa un <xref:System.Windows.Media.RadialGradientBrush> para pintar un rectángulo con un degradado radial que realiza la transición de amarillo a rojo a azul para verde lima.</span><span class="sxs-lookup"><span data-stu-id="d8ee6-105">The following example uses a <xref:System.Windows.Media.RadialGradientBrush> to paint a rectangle with a radial gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xaml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 <span data-ttu-id="d8ee6-106">La siguiente ilustración muestra el degradado del ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="d8ee6-106">The following illustration shows the gradient from the preceding example.</span></span> <span data-ttu-id="d8ee6-107">Se resaltan los delimitadores de degradado.</span><span class="sxs-lookup"><span data-stu-id="d8ee6-107">The gradient's stops have been highlighted.</span></span>  
  
 <span data-ttu-id="d8ee6-108">![Delimitadores de degradado en un degradado radial](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span><span class="sxs-lookup"><span data-stu-id="d8ee6-108">![Gradient stops in a radial gradient](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d8ee6-109">Los ejemplos de este tema usan el sistema de coordenadas predeterminado para establecer puntos de control.</span><span class="sxs-lookup"><span data-stu-id="d8ee6-109">The examples in this topic use the default coordinate system for setting control points.</span></span> <span data-ttu-id="d8ee6-110">El sistema de coordenadas predeterminado está relacionado con un rectángulo: 0 indica 0 por ciento del rectángulo, y 1 indica un 100 por cien del rectángulo.</span><span class="sxs-lookup"><span data-stu-id="d8ee6-110">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="d8ee6-111">Puede cambiar este sistema de coordenadas estableciendo el <xref:System.Windows.Media.GradientBrush.MappingMode%2A> valor para la propiedad <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span><span class="sxs-lookup"><span data-stu-id="d8ee6-111">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span> <span data-ttu-id="d8ee6-112">Un sistema de coordenadas absoluto no está relacionado con un rectángulo de selección.</span><span class="sxs-lookup"><span data-stu-id="d8ee6-112">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="d8ee6-113">Los valores se interpretan directamente en el espacio local.</span><span class="sxs-lookup"><span data-stu-id="d8ee6-113">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="d8ee6-114">Para más <xref:System.Windows.Media.RadialGradientBrush> ejemplos, vea el [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="d8ee6-114">For additional <xref:System.Windows.Media.RadialGradientBrush> examples, see the [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="d8ee6-115">Para obtener más información acerca de los degradados y otros tipos de pinceles, vea [el dibujo con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d8ee6-115">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>
