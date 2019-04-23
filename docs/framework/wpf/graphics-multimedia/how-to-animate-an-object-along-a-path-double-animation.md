---
title: Procedimiento Animación de un objeto a lo largo de un trazado (animación doble)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (double animation)
- double animation [WPF]
ms.assetid: 5a3c4a99-f303-42ad-a52a-e4794bb1798e
ms.openlocfilehash: 54f345bbe6b513e3593cbf45ba190d4a44228424
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59101450"
---
# <a name="how-to-animate-an-object-along-a-path-double-animation"></a><span data-ttu-id="11cf1-102">Procedimiento Animación de un objeto a lo largo de un trazado (animación doble)</span><span class="sxs-lookup"><span data-stu-id="11cf1-102">How to: Animate an Object Along a Path (Double Animation)</span></span>
<span data-ttu-id="11cf1-103">En este ejemplo se muestra cómo usar el <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> clase para mover un objeto a lo largo de un trazado definido por un <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="11cf1-103">This example shows how to use the <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> class to move an object along a path defined by a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11cf1-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="11cf1-104">Example</span></span>  
 <span data-ttu-id="11cf1-105">El ejemplo siguiente utiliza dos <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> objetos que se va a mover un rectángulo a lo largo de un trazado geométrico:</span><span class="sxs-lookup"><span data-stu-id="11cf1-105">The following example uses two <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> objects to move a rectangle along a geometric path:</span></span>  
  
-   <span data-ttu-id="11cf1-106">La primera <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> anima la <xref:System.Windows.Media.TranslateTransform.X%2A> de la <xref:System.Windows.Media.TranslateTransform> aplicada al rectángulo.</span><span class="sxs-lookup"><span data-stu-id="11cf1-106">The first <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates the <xref:System.Windows.Media.TranslateTransform.X%2A> of the <xref:System.Windows.Media.TranslateTransform> applied to the rectangle.</span></span> <span data-ttu-id="11cf1-107">Hace que el rectángulo se mueva horizontalmente a lo largo del trazado.</span><span class="sxs-lookup"><span data-stu-id="11cf1-107">It makes the rectangle move horizontally along the path.</span></span>  
  
-   <span data-ttu-id="11cf1-108">El segundo <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> anima la <xref:System.Windows.Media.TranslateTransform.Y%2A> de la <xref:System.Windows.Media.TranslateTransform> aplicada al rectángulo.</span><span class="sxs-lookup"><span data-stu-id="11cf1-108">The second <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates the <xref:System.Windows.Media.TranslateTransform.Y%2A> of the <xref:System.Windows.Media.TranslateTransform> applied to the rectangle.</span></span> <span data-ttu-id="11cf1-109">Hace que el rectángulo se mueva verticalmente a lo largo del trazado.</span><span class="sxs-lookup"><span data-stu-id="11cf1-109">It makes the rectangle move vertically along the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#DoubleAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/doubleanimationusingpathexample.xaml#doubleanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/DoubleAnimationUsingPathExample.cs#doubleanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/DoubleAnimationUsingPathExample.vb#doubleanimationusingpathwholepage)]  
  
 <span data-ttu-id="11cf1-110">Para obtener un ejemplo completo, vea [ejemplo de animación de trazado](https://go.microsoft.com/fwlink/?LinkID=160028).</span><span class="sxs-lookup"><span data-stu-id="11cf1-110">For the complete sample, see [Path Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160028).</span></span>  
  
 <span data-ttu-id="11cf1-111">Otra manera de mover un objeto utilizando un trazado geométrico es usar un <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> objeto.</span><span class="sxs-lookup"><span data-stu-id="11cf1-111">Another way to move an object using a geometric path is to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object.</span></span> <span data-ttu-id="11cf1-112">Para obtener un ejemplo, vea [animar un objeto a lo largo de un trazado (animación en matriz)](how-to-animate-an-object-along-a-path-matrix-animation.md).</span><span class="sxs-lookup"><span data-stu-id="11cf1-112">For an example, see [Animate an Object Along a Path (Matrix Animation)](how-to-animate-an-object-along-a-path-matrix-animation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11cf1-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="11cf1-113">See also</span></span>

- [<span data-ttu-id="11cf1-114">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="11cf1-114">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="11cf1-115">Temas de procedimientos de animación de trazado</span><span class="sxs-lookup"><span data-stu-id="11cf1-115">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
