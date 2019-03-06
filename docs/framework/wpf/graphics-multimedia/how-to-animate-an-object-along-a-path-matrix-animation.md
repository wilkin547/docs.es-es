---
title: Filtrar Animar un objeto a lo largo de una trayectoria (animación de matriz)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (matrix animation)
- matrix animation [WPF]
ms.assetid: 7000e697-1414-468c-b915-cf66062fc49e
ms.openlocfilehash: c0c4f1fad5ab6b8d30e6809aa866b4629d08af23
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57363740"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation"></a><span data-ttu-id="82a57-102">Procedimiento Animar un objeto a lo largo de una trayectoria (animación de matriz)</span><span class="sxs-lookup"><span data-stu-id="82a57-102">How to: Animate an Object Along a Path (Matrix Animation)</span></span>
<span data-ttu-id="82a57-103">En este ejemplo se muestra cómo usar el <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> clase para animar un objeto a lo largo de una ruta de acceso que se define mediante un <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="82a57-103">This example shows how to use the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> class to animate an object along a path that is defined by a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="82a57-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="82a57-104">Example</span></span>  
 <span data-ttu-id="82a57-105">En el ejemplo siguiente se anima un objeto a lo largo de un trazado haciendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="82a57-105">The following example animates an object along a path by doing the following:</span></span>  
  
-   <span data-ttu-id="82a57-106">Se aplica un <xref:System.Windows.Media.MatrixTransform> al objeto con el fin de moverla.</span><span class="sxs-lookup"><span data-stu-id="82a57-106">Applies a <xref:System.Windows.Media.MatrixTransform> to the object in order to move it.</span></span>  
  
-   <span data-ttu-id="82a57-107">Define la ruta de acceso mediante el uso de un <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="82a57-107">Defines the path by using a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
-   <span data-ttu-id="82a57-108">Crea un <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> y lo usa para animar la <xref:System.Windows.Media.Matrix> propiedad de la <xref:System.Windows.Media.MatrixTransform>.</span><span class="sxs-lookup"><span data-stu-id="82a57-108">Creates a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> and uses it to animate the <xref:System.Windows.Media.Matrix> property of the <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="82a57-109">El <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> toma el <xref:System.Windows.Media.PathGeometry> y lo usa para generar <xref:System.Windows.Media.Matrix> valores.</span><span class="sxs-lookup"><span data-stu-id="82a57-109">The <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> takes the <xref:System.Windows.Media.PathGeometry> and uses it to generate <xref:System.Windows.Media.Matrix> values.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexample.xaml#matrixanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExample.cs#matrixanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExample.vb#matrixanimationusingpathwholepage)]  
  
 <span data-ttu-id="82a57-110">Para obtener un ejemplo completo, vea [ejemplo de animación de trazado](https://go.microsoft.com/fwlink/?LinkID=160028).</span><span class="sxs-lookup"><span data-stu-id="82a57-110">For the complete sample, see [Path Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160028).</span></span> <span data-ttu-id="82a57-111">Para obtener más información sobre los trazados geométricos, vea el [información general sobre geometría](geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="82a57-111">For more information about geometric paths, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82a57-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="82a57-112">See also</span></span>
- [<span data-ttu-id="82a57-113">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="82a57-113">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="82a57-114">Ejemplo de animación de trazado</span><span class="sxs-lookup"><span data-stu-id="82a57-114">Path Animation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160028)
- [<span data-ttu-id="82a57-115">Temas de procedimientos de animación de trazado</span><span class="sxs-lookup"><span data-stu-id="82a57-115">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
