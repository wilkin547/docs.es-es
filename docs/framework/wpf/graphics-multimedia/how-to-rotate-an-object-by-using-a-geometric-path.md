---
title: 'Cómo: Girar un objeto utilizando un trazado geométrico'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
ms.assetid: cb31ca4d-f05a-4c6b-9a18-4b6faaf38d45
ms.openlocfilehash: a351fdc936f634b7c57ba5a49e51501f7572a3c9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186875"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path"></a><span data-ttu-id="a9d40-102">Cómo: Girar un objeto utilizando un trazado geométrico</span><span class="sxs-lookup"><span data-stu-id="a9d40-102">How to: Rotate an Object by Using a Geometric Path</span></span>
<span data-ttu-id="a9d40-103">En este ejemplo se muestra cómo girar (pivotar) un <xref:System.Windows.Media.PathGeometry> objeto a lo largo de un trazado geométrico definido por un objeto.</span><span class="sxs-lookup"><span data-stu-id="a9d40-103">This example shows how to rotate (pivot) an object along a geometric path that is defined by a <xref:System.Windows.Media.PathGeometry> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9d40-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a9d40-104">Example</span></span>  
 <span data-ttu-id="a9d40-105">En el ejemplo <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> siguiente se utilizan tres objetos para mover un rectángulo a lo largo de un trazado geométrico.</span><span class="sxs-lookup"><span data-stu-id="a9d40-105">The following example uses three <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> objects to move a rectangle along a geometric path.</span></span>  
  
- <span data-ttu-id="a9d40-106">El <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> primero anima <xref:System.Windows.Media.RotateTransform> un que se aplica al rectángulo.</span><span class="sxs-lookup"><span data-stu-id="a9d40-106">The first <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates a <xref:System.Windows.Media.RotateTransform> that is applied to the rectangle.</span></span> <span data-ttu-id="a9d40-107">La animación genera valores de ángulo.</span><span class="sxs-lookup"><span data-stu-id="a9d40-107">The animation generates angle values.</span></span> <span data-ttu-id="a9d40-108">Hace que el rectángulo gire (pivote) a lo largo de los contornos del trazado.</span><span class="sxs-lookup"><span data-stu-id="a9d40-108">It makes the rectangle rotate (pivot) along the contours of the path.</span></span>  
  
- <span data-ttu-id="a9d40-109">Los otros dos <xref:System.Windows.Media.TranslateTransform.X%2A> objetos animan los valores y <xref:System.Windows.Media.TranslateTransform.Y%2A> de un <xref:System.Windows.Media.TranslateTransform> que se aplica al rectángulo.</span><span class="sxs-lookup"><span data-stu-id="a9d40-109">The other two objects animate the <xref:System.Windows.Media.TranslateTransform.X%2A> and <xref:System.Windows.Media.TranslateTransform.Y%2A> values of a <xref:System.Windows.Media.TranslateTransform> that is applied to the rectangle.</span></span> <span data-ttu-id="a9d40-110">Hacen que el rectángulo se mueva horizontal y verticalmente a lo largo del trazado.</span><span class="sxs-lookup"><span data-stu-id="a9d40-110">They make the rectangle move horizontally and vertically along the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#RotateAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/rotateanimationusingpathexample.xaml#rotateanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/RotateAnimationUsingPathExample.cs#rotateanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/RotateAnimationUsingPathExample.vb#rotateanimationusingpathwholepage)]  
  
 <span data-ttu-id="a9d40-111">Otra forma de rotar un objeto mediante un <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> trazado geométrico es utilizar un objeto y establecer su <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> propiedad en `true`.</span><span class="sxs-lookup"><span data-stu-id="a9d40-111">Another way to rotate an object by using a geometric path is to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object and set its <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> property to `true`.</span></span> <span data-ttu-id="a9d40-112">Para obtener más información y un ejemplo, vea [Rotar un objeto mediante un trazado geométrico (animación de matriz)](how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md).</span><span class="sxs-lookup"><span data-stu-id="a9d40-112">For more information and an example, see [Rotate an Object by Using a Geometric Path (Matrix Animation)](how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md).</span></span>  
  
 <span data-ttu-id="a9d40-113">Para ver el ejemplo completo, consulte Ejemplo de [animación](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)de ruta de acceso .</span><span class="sxs-lookup"><span data-stu-id="a9d40-113">For the complete sample, see [Path Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9d40-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a9d40-114">See also</span></span>

- [<span data-ttu-id="a9d40-115">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="a9d40-115">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="a9d40-116">Ejemplo de animación de trazado</span><span class="sxs-lookup"><span data-stu-id="a9d40-116">Path Animation Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [<span data-ttu-id="a9d40-117">Temas de procedimientos de animación de trazado</span><span class="sxs-lookup"><span data-stu-id="a9d40-117">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
