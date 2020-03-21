---
title: 'Cómo: Girar un objeto utilizando un trazado geométrico (animación en matriz)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
- matrix animation [WPF]
ms.assetid: 877dc9aa-6bdc-4beb-8772-3efaec32c0f0
ms.openlocfilehash: 63dc873a2b840ea3f870a8c60c5691ab271c1c9f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187410"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation"></a><span data-ttu-id="9619e-102">Cómo: Girar un objeto utilizando un trazado geométrico (animación en matriz)</span><span class="sxs-lookup"><span data-stu-id="9619e-102">How to: Rotate an Object by Using a Geometric Path (Matrix Animation)</span></span>
<span data-ttu-id="9619e-103">En este ejemplo se <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> muestra <xref:System.Windows.Media.MatrixTransform> cómo utilizar a y a para girar <xref:System.Windows.Media.PathGeometry> (pivotar) un objeto a lo largo de un trazado geométrico definido por un objeto.</span><span class="sxs-lookup"><span data-stu-id="9619e-103">This example shows how to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> and a <xref:System.Windows.Media.MatrixTransform> to rotate (pivot) an object along a geometric path defined by a <xref:System.Windows.Media.PathGeometry> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9619e-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9619e-104">Example</span></span>  
 <span data-ttu-id="9619e-105">En el ejemplo <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> siguiente se <xref:System.Windows.Media.MatrixTransform.Matrix%2A> utiliza <xref:System.Windows.Media.MatrixTransform>el objeto para animar la propiedad de un archivo .</span><span class="sxs-lookup"><span data-stu-id="9619e-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="9619e-106">Se <xref:System.Windows.Media.MatrixTransform> aplica a un botón y hace que se mueva a lo largo de un trazado curvo.</span><span class="sxs-lookup"><span data-stu-id="9619e-106">The <xref:System.Windows.Media.MatrixTransform> is applied to a button and causes it to move along a curved path.</span></span> <span data-ttu-id="9619e-107">Dado <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> que la `true`propiedad está establecida en , el rectángulo gira a lo largo de la tangente de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="9619e-107">Because the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> property is set to `true`, the rectangle rotates along the tangent of the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 <span data-ttu-id="9619e-108">Para ver el ejemplo completo, consulte Ejemplo de [animación](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)de ruta de acceso .</span><span class="sxs-lookup"><span data-stu-id="9619e-108">For the complete sample, see [Path Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span></span>  
  
 <span data-ttu-id="9619e-109">La versión de código del <xref:System.Windows.Media.Animation.Storyboard> ejemplo <xref:System.Windows.Media.EllipseGeometry>anterior usaba a para animar el , aunque solo se aplicó una animación.</span><span class="sxs-lookup"><span data-stu-id="9619e-109">The code version of the preceding sample used a <xref:System.Windows.Media.Animation.Storyboard> to animate the <xref:System.Windows.Media.EllipseGeometry>, even though only one animation was applied.</span></span> <span data-ttu-id="9619e-110">Una manera más fácil de aplicar una sola animación a una propiedad en el código es usar el <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> método.</span><span class="sxs-lookup"><span data-stu-id="9619e-110">An easier way to apply a single animation to a property in code is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method.</span></span> <span data-ttu-id="9619e-111">Para obtener un ejemplo, vea [Animar una propiedad sin usar un guión gráfico](how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="9619e-111">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9619e-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9619e-112">See also</span></span>

- [<span data-ttu-id="9619e-113">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="9619e-113">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="9619e-114">Temas de procedimientos de animación de trazado</span><span class="sxs-lookup"><span data-stu-id="9619e-114">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
- [<span data-ttu-id="9619e-115">Ejemplo de animación de trazado</span><span class="sxs-lookup"><span data-stu-id="9619e-115">Path Animation Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
