---
title: 'Cómo: Animar un objeto a lo largo de un trazado (animación en punto)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (point animation)
- point animation [WPF]
ms.assetid: 1fa3f817-35bc-41a1-b366-f5a20b70da0c
ms.openlocfilehash: eff0c24a9369ffaa0cfca1cc46af4eff39f58a38
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452901"
---
# <a name="how-to-animate-an-object-along-a-path-point-animation"></a><span data-ttu-id="c7bcf-102">Cómo: Animar un objeto a lo largo de un trazado (animación en punto)</span><span class="sxs-lookup"><span data-stu-id="c7bcf-102">How to: Animate an Object Along a Path (Point Animation)</span></span>
<span data-ttu-id="c7bcf-103">En este ejemplo se muestra cómo utilizar un objeto <xref:System.Windows.Media.Animation.PointAnimationUsingPath> para animar un <xref:System.Windows.Point> a lo largo de un trazado curvo.</span><span class="sxs-lookup"><span data-stu-id="c7bcf-103">This example shows how to use a <xref:System.Windows.Media.Animation.PointAnimationUsingPath> object to animate a <xref:System.Windows.Point> along a curved path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7bcf-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c7bcf-104">Example</span></span>  
 <span data-ttu-id="c7bcf-105">En el ejemplo siguiente se mueve una <xref:System.Windows.Media.EllipseGeometry> a lo largo de un trazado definido por un <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="c7bcf-105">The following example moves an <xref:System.Windows.Media.EllipseGeometry> along a path defined by a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="c7bcf-106">La propiedad <xref:System.Windows.Media.EllipseGeometry.Center%2A> de la geometría de elipse, que toma un valor <xref:System.Windows.Point>, especifica su posición; para desplace la geometría de la elipse, anime su propiedad <xref:System.Windows.Media.EllipseGeometry.Center%2A>.</span><span class="sxs-lookup"><span data-stu-id="c7bcf-106">The ellipse geometry's <xref:System.Windows.Media.EllipseGeometry.Center%2A> property, which takes a <xref:System.Windows.Point> value, specifies its position; to move the ellipse geometry, you animate its <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span> <span data-ttu-id="c7bcf-107">En el ejemplo se usa un <xref:System.Windows.Media.Animation.PointAnimationUsingPath> para animar la propiedad <xref:System.Windows.Media.EllipseGeometry.Center%2A> del objeto <xref:System.Windows.Media.EllipseGeometry>.</span><span class="sxs-lookup"><span data-stu-id="c7bcf-107">The example uses a <xref:System.Windows.Media.Animation.PointAnimationUsingPath> to animate the <xref:System.Windows.Media.EllipseGeometry> object's <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/pointanimationusingpathexample.xaml#pointanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/PointAnimationUsingPathExample.cs#pointanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/PointAnimationUsingPathExample.vb#pointanimationusingpathwholepage)]  
  
 <span data-ttu-id="c7bcf-108">Para obtener el ejemplo completo, consulte [ejemplo de animación de trazado](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span><span class="sxs-lookup"><span data-stu-id="c7bcf-108">For the complete sample, see [Path Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span></span>  
  
 <span data-ttu-id="c7bcf-109">La versión de código del ejemplo anterior usaba un <xref:System.Windows.Media.Animation.Storyboard> para animar el <xref:System.Windows.Media.EllipseGeometry>, aunque solo se aplicó una animación.</span><span class="sxs-lookup"><span data-stu-id="c7bcf-109">The code version of the preceding sample used a <xref:System.Windows.Media.Animation.Storyboard> to animate the <xref:System.Windows.Media.EllipseGeometry>, even though only one animation was applied.</span></span> <span data-ttu-id="c7bcf-110">Una <xref:System.Windows.Media.Animation.Storyboard> suele ser la manera más fácil de aplicar varias animaciones porque estas animaciones pueden controlarse mediante el mismo <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="c7bcf-110">A <xref:System.Windows.Media.Animation.Storyboard> is often the easiest way to apply multiple animations because these animations can be controlled by the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="c7bcf-111">Sin embargo, una manera más fácil de aplicar una animación única a una propiedad cuando se usa código es usar el método <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>.</span><span class="sxs-lookup"><span data-stu-id="c7bcf-111">However, an easier way to apply a single animation to a property when using code is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method.</span></span> <span data-ttu-id="c7bcf-112">Para obtener un ejemplo, vea [Animar una propiedad sin utilizar un guión gráfico](how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="c7bcf-112">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7bcf-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c7bcf-113">See also</span></span>

- [<span data-ttu-id="c7bcf-114">Ejemplo de animación de trazado</span><span class="sxs-lookup"><span data-stu-id="c7bcf-114">Path Animation Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [<span data-ttu-id="c7bcf-115">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="c7bcf-115">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="c7bcf-116">Temas de procedimientos de animación de trazado</span><span class="sxs-lookup"><span data-stu-id="c7bcf-116">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
