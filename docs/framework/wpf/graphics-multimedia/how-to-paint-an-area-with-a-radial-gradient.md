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
ms.openlocfilehash: 5762ef1a1526ba6f004917c8a947e35ce731c86d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916098"
---
# <a name="how-to-paint-an-area-with-a-radial-gradient"></a><span data-ttu-id="4256b-102">Procedimiento Pintar un área con un degradado radial</span><span class="sxs-lookup"><span data-stu-id="4256b-102">How to: Paint an Area with a Radial Gradient</span></span>
<span data-ttu-id="4256b-103">En este ejemplo se muestra cómo utilizar <xref:System.Windows.Media.RadialGradientBrush> la clase para pintar un área con un degradado radial.</span><span class="sxs-lookup"><span data-stu-id="4256b-103">This example shows how to use the <xref:System.Windows.Media.RadialGradientBrush> class to paint an area with a radial gradient.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4256b-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4256b-104">Example</span></span>  
 <span data-ttu-id="4256b-105"><xref:System.Windows.Media.RadialGradientBrush> En el ejemplo siguiente se usa para pintar un rectángulo con un degradado radial que realiza la transición de amarillo a rojo a azul a verde lima.</span><span class="sxs-lookup"><span data-stu-id="4256b-105">The following example uses a <xref:System.Windows.Media.RadialGradientBrush> to paint a rectangle with a radial gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xaml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 <span data-ttu-id="4256b-106">En la ilustración siguiente se muestra el degradado del ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="4256b-106">The following illustration shows the gradient from the preceding example.</span></span> <span data-ttu-id="4256b-107">Los topes del degradado se han resaltado.</span><span class="sxs-lookup"><span data-stu-id="4256b-107">The gradient's stops have been highlighted.</span></span>  
  
 <span data-ttu-id="4256b-108">![Delimitadores de degradado en un degradado radial](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span><span class="sxs-lookup"><span data-stu-id="4256b-108">![Gradient stops in a radial gradient](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4256b-109">En los ejemplos de este tema se usa el sistema de coordenadas predeterminado para establecer los puntos de control.</span><span class="sxs-lookup"><span data-stu-id="4256b-109">The examples in this topic use the default coordinate system for setting control points.</span></span> <span data-ttu-id="4256b-110">El sistema de coordenadas predeterminado es relativo a un cuadro de límite: 0 indica un 0 por ciento del rectángulo de selección, mientras que 1 indica un 100 por cien del rectángulo de selección.</span><span class="sxs-lookup"><span data-stu-id="4256b-110">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="4256b-111">Puede cambiar este sistema de coordenadas estableciendo la <xref:System.Windows.Media.GradientBrush.MappingMode%2A> propiedad en el valor. <xref:System.Windows.Media.BrushMappingMode.Absolute></span><span class="sxs-lookup"><span data-stu-id="4256b-111">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span> <span data-ttu-id="4256b-112">Un sistema de coordenadas absoluto no está relacionado con un rectángulo de selección.</span><span class="sxs-lookup"><span data-stu-id="4256b-112">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="4256b-113">Los valores se interpretan directamente en el espacio local.</span><span class="sxs-lookup"><span data-stu-id="4256b-113">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="4256b-114">Para obtener <xref:System.Windows.Media.RadialGradientBrush> más ejemplos, vea el [ejemplo brushes](https://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="4256b-114">For additional <xref:System.Windows.Media.RadialGradientBrush> examples, see the [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="4256b-115">Para obtener más información sobre los degradados y otros tipos de pinceles, consulte [información general sobre el dibujo con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4256b-115">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>
