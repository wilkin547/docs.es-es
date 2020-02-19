---
title: 'Cómo: Animar un objeto a lo largo de un trazado (animación en matriz con acumulación de desplazamiento)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- offset accumulation [WPF]
- animation [WPF], objects along paths (matrix animation with offset accumulation)
- matrix animation with offset accumulation [WPF]
ms.assetid: 1bca90ef-9832-4128-8ed6-62908e7ec146
ms.openlocfilehash: 8b3975ef5031b50381dfa9baf7f34a58fc05ab4e
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453109"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation-with-offset-accumulation"></a><span data-ttu-id="27896-102">Cómo: Animar un objeto a lo largo de un trazado (animación en matriz con acumulación de desplazamiento)</span><span class="sxs-lookup"><span data-stu-id="27896-102">How to: Animate an Object Along a Path (Matrix Animation with Offset Accumulation)</span></span>
<span data-ttu-id="27896-103">En este ejemplo se muestra cómo usar la clase <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> para animar un objeto a lo largo de un trazado y hacer que la animación acumule sus valores de desplazamiento a medida que se repite.</span><span class="sxs-lookup"><span data-stu-id="27896-103">This example shows how to use the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> class to animate an object along a path and have that animation accumulate its offset values as it repeats.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27896-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="27896-104">Example</span></span>  
 <span data-ttu-id="27896-105">En el ejemplo siguiente se usa el objeto <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> para animar la propiedad <xref:System.Windows.Media.MatrixTransform.Matrix%2A> de un <xref:System.Windows.Media.MatrixTransform> aplicado a un botón.</span><span class="sxs-lookup"><span data-stu-id="27896-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> applied to a button.</span></span> <span data-ttu-id="27896-106">Como resultado, un botón se mueve a lo largo de un trazado curvo.</span><span class="sxs-lookup"><span data-stu-id="27896-106">As a result, a button moves along a curved path.</span></span>  
  
 <span data-ttu-id="27896-107">Además, en el ejemplo se establece la propiedad <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> en `true`, lo que hace que el desplazamiento de la matriz animada se acumule a medida que se repite la animación.</span><span class="sxs-lookup"><span data-stu-id="27896-107">In addition, the example sets the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> property to `true`, which causes the offset of the animated matrix to accumulate as the animation repeats.</span></span> <span data-ttu-id="27896-108">Dado que el desplazamiento se acumula, el botón se aleja por la pantalla cuando se repite la animación, en lugar de restablecerse a la posición inicial.</span><span class="sxs-lookup"><span data-stu-id="27896-108">Because the offset accumulates, the button moves farther across the screen when the animation repeats, rather than resetting to the starting position.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexampleoffsetcumulative.xaml#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExampleOffsetCumulative.cs#matrixanimationusingpathoffsetcumulativewholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExampleOffsetCumulative.vb#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 <span data-ttu-id="27896-109">Tenga en cuenta que, aunque la propiedad <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> hace que los valores de desplazamiento se acumulen en las repeticiones, no hace que se acumulen los valores de rotación.</span><span class="sxs-lookup"><span data-stu-id="27896-109">Note that, although the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> property causes offset values to accumulate over repetitions, it doesn't cause rotation values to accumulate.</span></span> <span data-ttu-id="27896-110">Para que se acumulen los valores de rotación, establezca las propiedades <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> y <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> de la animación en `true`.</span><span class="sxs-lookup"><span data-stu-id="27896-110">To make rotation values accumulate, set the animation's <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> and <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> properties to `true`.</span></span>  
  
 <span data-ttu-id="27896-111">Para obtener el ejemplo completo, consulte [ejemplo de animación de trazado](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span><span class="sxs-lookup"><span data-stu-id="27896-111">For the complete sample, see [Path Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span></span> <span data-ttu-id="27896-112">Para ver un ejemplo en el que se muestra cómo animar un valor <xref:System.Windows.Media.Matrix> a lo largo de un trazado sin acumulación de desplazamiento, vea [animar un objeto a lo largo de un trazado (animación en matriz)](how-to-animate-an-object-along-a-path-matrix-animation.md).</span><span class="sxs-lookup"><span data-stu-id="27896-112">For an example showing how to animate a <xref:System.Windows.Media.Matrix> value along a path without offset accumulation, see [Animate an Object Along a Path (Matrix Animation)](how-to-animate-an-object-along-a-path-matrix-animation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27896-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="27896-113">See also</span></span>

- [<span data-ttu-id="27896-114">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="27896-114">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="27896-115">Temas de procedimientos de animación de trazado</span><span class="sxs-lookup"><span data-stu-id="27896-115">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
