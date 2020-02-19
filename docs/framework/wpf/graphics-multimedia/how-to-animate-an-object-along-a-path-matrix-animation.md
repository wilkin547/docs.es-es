---
title: 'Cómo: Animar un objeto a lo largo de una trayectoria (animación de matriz)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (matrix animation)
- matrix animation [WPF]
ms.assetid: 7000e697-1414-468c-b915-cf66062fc49e
ms.openlocfilehash: 7dfc233fe60e1cea293edc44a2bba79dc6962f7c
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452914"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation"></a><span data-ttu-id="7b6ff-102">Cómo: Animar un objeto a lo largo de una trayectoria (animación de matriz)</span><span class="sxs-lookup"><span data-stu-id="7b6ff-102">How to: Animate an Object Along a Path (Matrix Animation)</span></span>
<span data-ttu-id="7b6ff-103">En este ejemplo se muestra cómo usar la clase <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> para animar un objeto a lo largo de un trazado definido por un <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="7b6ff-103">This example shows how to use the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> class to animate an object along a path that is defined by a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b6ff-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7b6ff-104">Example</span></span>  
 <span data-ttu-id="7b6ff-105">En el ejemplo siguiente se anima un objeto a lo largo de un trazado haciendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7b6ff-105">The following example animates an object along a path by doing the following:</span></span>  
  
- <span data-ttu-id="7b6ff-106">Aplica un <xref:System.Windows.Media.MatrixTransform> al objeto para moverlo.</span><span class="sxs-lookup"><span data-stu-id="7b6ff-106">Applies a <xref:System.Windows.Media.MatrixTransform> to the object in order to move it.</span></span>  
  
- <span data-ttu-id="7b6ff-107">Define la ruta de acceso mediante un <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="7b6ff-107">Defines the path by using a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
- <span data-ttu-id="7b6ff-108">Crea un <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> y lo usa para animar la propiedad <xref:System.Windows.Media.Matrix> de la <xref:System.Windows.Media.MatrixTransform>.</span><span class="sxs-lookup"><span data-stu-id="7b6ff-108">Creates a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> and uses it to animate the <xref:System.Windows.Media.Matrix> property of the <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="7b6ff-109">El <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> toma el <xref:System.Windows.Media.PathGeometry> y lo utiliza para generar valores <xref:System.Windows.Media.Matrix>.</span><span class="sxs-lookup"><span data-stu-id="7b6ff-109">The <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> takes the <xref:System.Windows.Media.PathGeometry> and uses it to generate <xref:System.Windows.Media.Matrix> values.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexample.xaml#matrixanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExample.cs#matrixanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExample.vb#matrixanimationusingpathwholepage)]  
  
 <span data-ttu-id="7b6ff-110">Para obtener el ejemplo completo, consulte [ejemplo de animación de trazado](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span><span class="sxs-lookup"><span data-stu-id="7b6ff-110">For the complete sample, see [Path Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span></span> <span data-ttu-id="7b6ff-111">Para obtener más información sobre las rutas de acceso geométricas, vea [información general sobre geometría](geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7b6ff-111">For more information about geometric paths, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b6ff-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7b6ff-112">See also</span></span>

- [<span data-ttu-id="7b6ff-113">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="7b6ff-113">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="7b6ff-114">Ejemplo de animación de trazado</span><span class="sxs-lookup"><span data-stu-id="7b6ff-114">Path Animation Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [<span data-ttu-id="7b6ff-115">Temas de procedimientos de animación de trazado</span><span class="sxs-lookup"><span data-stu-id="7b6ff-115">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
