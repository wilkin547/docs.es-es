---
title: 'Cómo: Pintar un área con un degradado radial'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with radial gradients
- radial gradients [WPF], painting with
- painting [WPF], with radial gradients
ms.assetid: b5d0fc8a-8986-4796-b003-a75b41a48928
ms.openlocfilehash: 8a53d5d7247f82905816265f7c92b22f287591c5
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452758"
---
# <a name="how-to-paint-an-area-with-a-radial-gradient"></a><span data-ttu-id="baa84-102">Cómo: Pintar un área con un degradado radial</span><span class="sxs-lookup"><span data-stu-id="baa84-102">How to: Paint an Area with a Radial Gradient</span></span>
<span data-ttu-id="baa84-103">En este ejemplo se muestra cómo usar la clase <xref:System.Windows.Media.RadialGradientBrush> para pintar un área con un degradado radial.</span><span class="sxs-lookup"><span data-stu-id="baa84-103">This example shows how to use the <xref:System.Windows.Media.RadialGradientBrush> class to paint an area with a radial gradient.</span></span>  
  
## <a name="example"></a><span data-ttu-id="baa84-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="baa84-104">Example</span></span>  
 <span data-ttu-id="baa84-105">En el ejemplo siguiente se usa un <xref:System.Windows.Media.RadialGradientBrush> para pintar un rectángulo con un degradado radial que realiza la transición de amarillo a rojo a azul a verde lima.</span><span class="sxs-lookup"><span data-stu-id="baa84-105">The following example uses a <xref:System.Windows.Media.RadialGradientBrush> to paint a rectangle with a radial gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xaml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 <span data-ttu-id="baa84-106">En la ilustración siguiente se muestra el degradado del ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="baa84-106">The following illustration shows the gradient from the preceding example.</span></span> <span data-ttu-id="baa84-107">Los topes del degradado se han resaltado.</span><span class="sxs-lookup"><span data-stu-id="baa84-107">The gradient's stops have been highlighted.</span></span>  
  
 <span data-ttu-id="baa84-108">![Delimitadores de degradado en un degradado radial](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span><span class="sxs-lookup"><span data-stu-id="baa84-108">![Gradient stops in a radial gradient](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="baa84-109">En los ejemplos de este tema se usa el sistema de coordenadas predeterminado para establecer los puntos de control.</span><span class="sxs-lookup"><span data-stu-id="baa84-109">The examples in this topic use the default coordinate system for setting control points.</span></span> <span data-ttu-id="baa84-110">El sistema de coordenadas predeterminado es relativo a un rectángulo de selección: 0 indica 0 por ciento del rectángulo de selección y 1 indica el 100 por ciento del cuadro de límite.</span><span class="sxs-lookup"><span data-stu-id="baa84-110">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="baa84-111">Puede cambiar este sistema de coordenadas estableciendo la propiedad <xref:System.Windows.Media.GradientBrush.MappingMode%2A> en el valor <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span><span class="sxs-lookup"><span data-stu-id="baa84-111">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span> <span data-ttu-id="baa84-112">Un sistema de coordenadas absoluto no está relacionado con un rectángulo de selección.</span><span class="sxs-lookup"><span data-stu-id="baa84-112">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="baa84-113">Los valores se interpretan directamente en el espacio local.</span><span class="sxs-lookup"><span data-stu-id="baa84-113">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="baa84-114">Para obtener más ejemplos de <xref:System.Windows.Media.RadialGradientBrush>, vea el [ejemplo de pinceles](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span><span class="sxs-lookup"><span data-stu-id="baa84-114">For additional <xref:System.Windows.Media.RadialGradientBrush> examples, see the [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span> <span data-ttu-id="baa84-115">Para obtener más información sobre los degradados y otros tipos de pinceles, consulte [información general sobre el dibujo con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="baa84-115">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>
