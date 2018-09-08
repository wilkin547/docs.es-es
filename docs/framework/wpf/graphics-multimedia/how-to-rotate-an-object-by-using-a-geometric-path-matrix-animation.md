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
ms.openlocfilehash: 3a35f6dda05cfe65811de16d76b288c8fbd618a7
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44199237"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation"></a><span data-ttu-id="51e63-102">Cómo: Girar un objeto utilizando un trazado geométrico (animación en matriz)</span><span class="sxs-lookup"><span data-stu-id="51e63-102">How to: Rotate an Object by Using a Geometric Path (Matrix Animation)</span></span>
<span data-ttu-id="51e63-103">En este ejemplo se muestra cómo usar un <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> y un <xref:System.Windows.Media.MatrixTransform> para girar (pivotar) un objeto a lo largo de un trazado geométrico definido por un <xref:System.Windows.Media.PathGeometry> objeto.</span><span class="sxs-lookup"><span data-stu-id="51e63-103">This example shows how to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> and a <xref:System.Windows.Media.MatrixTransform> to rotate (pivot) an object along a geometric path defined by a <xref:System.Windows.Media.PathGeometry> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51e63-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="51e63-104">Example</span></span>  
 <span data-ttu-id="51e63-105">En el ejemplo siguiente se usa el <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> objeto que se va a animar el <xref:System.Windows.Media.MatrixTransform.Matrix%2A> propiedad de un <xref:System.Windows.Media.MatrixTransform>.</span><span class="sxs-lookup"><span data-stu-id="51e63-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="51e63-106">El <xref:System.Windows.Media.MatrixTransform> se aplica a un botón y hace que se mueva a lo largo de un trazado curvo.</span><span class="sxs-lookup"><span data-stu-id="51e63-106">The <xref:System.Windows.Media.MatrixTransform> is applied to a button and causes it to move along a curved path.</span></span> <span data-ttu-id="51e63-107">Dado que el <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> propiedad está establecida en `true`, el rectángulo gira a lo largo de la tangente de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="51e63-107">Because the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> property is set to `true`, the rectangle rotates along the tangent of the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 <span data-ttu-id="51e63-108">Para obtener un ejemplo completo, vea [ejemplo de animación de trazado](https://go.microsoft.com/fwlink/?LinkID=160028).</span><span class="sxs-lookup"><span data-stu-id="51e63-108">For the complete sample, see [Path Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160028).</span></span>  
  
 <span data-ttu-id="51e63-109">La versión del código del ejemplo anterior utiliza un <xref:System.Windows.Media.Animation.Storyboard> para animar el <xref:System.Windows.Media.EllipseGeometry>, aunque se aplique solo a una animación.</span><span class="sxs-lookup"><span data-stu-id="51e63-109">The code version of the preceding sample used a <xref:System.Windows.Media.Animation.Storyboard> to animate the <xref:System.Windows.Media.EllipseGeometry>, even though only one animation was applied.</span></span> <span data-ttu-id="51e63-110">Una manera más fácil de aplicar una animación única a una propiedad en el código es usar el <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> método.</span><span class="sxs-lookup"><span data-stu-id="51e63-110">An easier way to apply a single animation to a property in code is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method.</span></span> <span data-ttu-id="51e63-111">Para obtener un ejemplo, vea [Animar una propiedad sin utilizar un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="51e63-111">For an example, see [Animate a Property Without Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51e63-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="51e63-112">See Also</span></span>  
 [<span data-ttu-id="51e63-113">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="51e63-113">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="51e63-114">Temas de procedimientos de animación de trazado</span><span class="sxs-lookup"><span data-stu-id="51e63-114">Path Animation How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)  
 [<span data-ttu-id="51e63-115">Ejemplo de animación de trazado</span><span class="sxs-lookup"><span data-stu-id="51e63-115">Path Animation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160028)
