---
title: Filtrar Girar un objeto utilizando un trazado geométrico
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
ms.assetid: cb31ca4d-f05a-4c6b-9a18-4b6faaf38d45
ms.openlocfilehash: 2a027e11b910650044996c7ca7bdb822a1de513f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57350766"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path"></a><span data-ttu-id="a6ee9-102">Filtrar Girar un objeto utilizando un trazado geométrico</span><span class="sxs-lookup"><span data-stu-id="a6ee9-102">How to: Rotate an Object by Using a Geometric Path</span></span>
<span data-ttu-id="a6ee9-103">En este ejemplo se muestra cómo girar (pivotar) un objeto a lo largo de un trazado geométrico definido por un <xref:System.Windows.Media.PathGeometry> objeto.</span><span class="sxs-lookup"><span data-stu-id="a6ee9-103">This example shows how to rotate (pivot) an object along a geometric path that is defined by a <xref:System.Windows.Media.PathGeometry> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6ee9-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a6ee9-104">Example</span></span>  
 <span data-ttu-id="a6ee9-105">El ejemplo siguiente utiliza tres <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> objetos que se va a mover un rectángulo a lo largo de un trazado geométrico.</span><span class="sxs-lookup"><span data-stu-id="a6ee9-105">The following example uses three <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> objects to move a rectangle along a geometric path.</span></span>  
  
-   <span data-ttu-id="a6ee9-106">La primera <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> anima un <xref:System.Windows.Media.RotateTransform> que se aplica al rectángulo.</span><span class="sxs-lookup"><span data-stu-id="a6ee9-106">The first <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates a <xref:System.Windows.Media.RotateTransform> that is applied to the rectangle.</span></span> <span data-ttu-id="a6ee9-107">La animación genera valores de ángulo.</span><span class="sxs-lookup"><span data-stu-id="a6ee9-107">The animation generates angle values.</span></span> <span data-ttu-id="a6ee9-108">Hace que el rectángulo gire (pivote) a lo largo de los contornos del trazado.</span><span class="sxs-lookup"><span data-stu-id="a6ee9-108">It makes the rectangle rotate (pivot) along the contours of the path.</span></span>  
  
-   <span data-ttu-id="a6ee9-109">Los otros dos objetos animan la <xref:System.Windows.Media.TranslateTransform.X%2A> y <xref:System.Windows.Media.TranslateTransform.Y%2A> valores de un <xref:System.Windows.Media.TranslateTransform> que se aplica al rectángulo.</span><span class="sxs-lookup"><span data-stu-id="a6ee9-109">The other two objects animate the <xref:System.Windows.Media.TranslateTransform.X%2A> and <xref:System.Windows.Media.TranslateTransform.Y%2A> values of a <xref:System.Windows.Media.TranslateTransform> that is applied to the rectangle.</span></span> <span data-ttu-id="a6ee9-110">Hacen que el rectángulo se mueva horizontal y verticalmente a lo largo del trazado.</span><span class="sxs-lookup"><span data-stu-id="a6ee9-110">They make the rectangle move horizontally and vertically along the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#RotateAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/rotateanimationusingpathexample.xaml#rotateanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/RotateAnimationUsingPathExample.cs#rotateanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/RotateAnimationUsingPathExample.vb#rotateanimationusingpathwholepage)]  
  
 <span data-ttu-id="a6ee9-111">Otra manera de girar un objeto utilizando un trazado geométrico es usar un <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> de objeto y establecer su <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="a6ee9-111">Another way to rotate an object by using a geometric path is to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object and set its <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> property to `true`.</span></span> <span data-ttu-id="a6ee9-112">Para obtener más información y un ejemplo, vea [girar un objeto utilizando un trazado geométrico (animación en matriz)](how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md).</span><span class="sxs-lookup"><span data-stu-id="a6ee9-112">For more information and an example, see [Rotate an Object by Using a Geometric Path (Matrix Animation)](how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md).</span></span>  
  
 <span data-ttu-id="a6ee9-113">Para obtener un ejemplo completo, vea [ejemplo de animación de trazado](https://go.microsoft.com/fwlink/?LinkID=160028).</span><span class="sxs-lookup"><span data-stu-id="a6ee9-113">For the complete sample, see [Path Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160028).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6ee9-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6ee9-114">See also</span></span>
- [<span data-ttu-id="a6ee9-115">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="a6ee9-115">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="a6ee9-116">Ejemplo de animación de trazado</span><span class="sxs-lookup"><span data-stu-id="a6ee9-116">Path Animation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160028)
- [<span data-ttu-id="a6ee9-117">Temas de procedimientos de animación de trazado</span><span class="sxs-lookup"><span data-stu-id="a6ee9-117">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
