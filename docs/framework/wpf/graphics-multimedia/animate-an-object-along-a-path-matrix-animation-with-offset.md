---
title: "Cómo: Animar un objeto a lo largo de un trazado (animación en matriz con acumulación de desplazamiento)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- offset accumulation [WPF]
- animation [WPF], objects along paths (matrix animation with offset accumulation)
- matrix animation with offset accumulation [WPF]
ms.assetid: 1bca90ef-9832-4128-8ed6-62908e7ec146
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5259e930060a8ac6118d232f08d02193a6a1b300
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation-with-offset-accumulation"></a><span data-ttu-id="e588f-102">Cómo: Animar un objeto a lo largo de un trazado (animación en matriz con acumulación de desplazamiento)</span><span class="sxs-lookup"><span data-stu-id="e588f-102">How to: Animate an Object Along a Path (Matrix Animation with Offset Accumulation)</span></span>
<span data-ttu-id="e588f-103">Este ejemplo muestra cómo utilizar la <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> clase animar un objeto a lo largo de una ruta de acceso y hacer que esa animación su desplazamiento se acumulan los valores mientras se repite.</span><span class="sxs-lookup"><span data-stu-id="e588f-103">This example shows how to use the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> class to animate an object along a path and have that animation accumulate its offset values as it repeats.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e588f-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e588f-104">Example</span></span>  
 <span data-ttu-id="e588f-105">En el ejemplo siguiente se usa el <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> objeto que se va a animar el <xref:System.Windows.Media.MatrixTransform.Matrix%2A> propiedad de una <xref:System.Windows.Media.MatrixTransform> aplicada a un botón.</span><span class="sxs-lookup"><span data-stu-id="e588f-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> applied to a button.</span></span> <span data-ttu-id="e588f-106">Como resultado, un botón se mueve a lo largo de un trazado curvo.</span><span class="sxs-lookup"><span data-stu-id="e588f-106">As a result, a button moves along a curved path.</span></span>  
  
 <span data-ttu-id="e588f-107">Además, el ejemplo establece la <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> propiedad `true`, lo que hace que el desplazamiento de la matriz animada para acumular a medida que se repite la animación.</span><span class="sxs-lookup"><span data-stu-id="e588f-107">In addition, the example sets the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> property to `true`, which causes the offset of the animated matrix to accumulate as the animation repeats.</span></span> <span data-ttu-id="e588f-108">Dado que el desplazamiento se acumula, el botón se aleja por la pantalla cuando se repite la animación, en lugar de restablecerse a la posición inicial.</span><span class="sxs-lookup"><span data-stu-id="e588f-108">Because the offset accumulates, the button moves farther across the screen when the animation repeats, rather than resetting to the starting position.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexampleoffsetcumulative.xaml#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExampleOffsetCumulative.cs#matrixanimationusingpathoffsetcumulativewholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExampleOffsetCumulative.vb#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 <span data-ttu-id="e588f-109">Tenga en cuenta que, aunque el <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> esta propiedad hace que los valores de desplazamiento acumular en las repeticiones, no hace que se acumulan los valores de rotación.</span><span class="sxs-lookup"><span data-stu-id="e588f-109">Note that, although the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> property causes offset values to accumulate over repetitions, it doesn't cause rotation values to accumulate.</span></span> <span data-ttu-id="e588f-110">Para hacer que se acumulan los valores de rotación, establezca la animación <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> y <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> propiedades para `true`.</span><span class="sxs-lookup"><span data-stu-id="e588f-110">To make rotation values accumulate, set the animation's <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> and <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> properties to `true`.</span></span>  
  
 <span data-ttu-id="e588f-111">Para obtener un ejemplo completo, vea [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).</span><span class="sxs-lookup"><span data-stu-id="e588f-111">For the complete sample, see [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).</span></span> <span data-ttu-id="e588f-112">Para obtener un ejemplo que muestra cómo animar un <xref:System.Windows.Media.Matrix> valor a lo largo de una ruta de acceso sin acumulación de desplazamiento, vea [animar un objeto a lo largo de una ruta de acceso (animación de matriz)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md).</span><span class="sxs-lookup"><span data-stu-id="e588f-112">For an example showing how to animate a <xref:System.Windows.Media.Matrix> value along a path without offset accumulation, see [Animate an Object Along a Path (Matrix Animation)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e588f-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="e588f-113">See Also</span></span>  
 [<span data-ttu-id="e588f-114">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="e588f-114">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="e588f-115">Temas de procedimientos de animación de trazado</span><span class="sxs-lookup"><span data-stu-id="e588f-115">Path Animation How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
