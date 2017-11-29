---
title: "Cómo: Girar un objeto utilizando un trazado geométrico"
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
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
ms.assetid: cb31ca4d-f05a-4c6b-9a18-4b6faaf38d45
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 078d1054f9b6a4c2f6172f00aa8c4ad9077e6db2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path"></a><span data-ttu-id="7a0b8-102">Cómo: Girar un objeto utilizando un trazado geométrico</span><span class="sxs-lookup"><span data-stu-id="7a0b8-102">How to: Rotate an Object by Using a Geometric Path</span></span>
<span data-ttu-id="7a0b8-103">Este ejemplo muestra cómo girar un objeto a lo largo de una ruta de acceso geométrica definida por un <xref:System.Windows.Media.PathGeometry> objeto.</span><span class="sxs-lookup"><span data-stu-id="7a0b8-103">This example shows how to rotate (pivot) an object along a geometric path that is defined by a <xref:System.Windows.Media.PathGeometry> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a0b8-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7a0b8-104">Example</span></span>  
 <span data-ttu-id="7a0b8-105">En el ejemplo siguiente se utiliza tres <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> objetos que se va a mover un rectángulo a lo largo de un trazado geométrico.</span><span class="sxs-lookup"><span data-stu-id="7a0b8-105">The following example uses three <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> objects to move a rectangle along a geometric path.</span></span>  
  
-   <span data-ttu-id="7a0b8-106">La primera <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> anima un <xref:System.Windows.Media.RotateTransform> que se aplica al rectángulo.</span><span class="sxs-lookup"><span data-stu-id="7a0b8-106">The first <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates a <xref:System.Windows.Media.RotateTransform> that is applied to the rectangle.</span></span> <span data-ttu-id="7a0b8-107">La animación genera valores de ángulo.</span><span class="sxs-lookup"><span data-stu-id="7a0b8-107">The animation generates angle values.</span></span> <span data-ttu-id="7a0b8-108">Hace que el rectángulo gire (pivote) a lo largo de los contornos del trazado.</span><span class="sxs-lookup"><span data-stu-id="7a0b8-108">It makes the rectangle rotate (pivot) along the contours of the path.</span></span>  
  
-   <span data-ttu-id="7a0b8-109">Los otros dos objetos animan la <xref:System.Windows.Media.TranslateTransform.X%2A> y <xref:System.Windows.Media.TranslateTransform.Y%2A> valores de un <xref:System.Windows.Media.TranslateTransform> que se aplica al rectángulo.</span><span class="sxs-lookup"><span data-stu-id="7a0b8-109">The other two objects animate the <xref:System.Windows.Media.TranslateTransform.X%2A> and <xref:System.Windows.Media.TranslateTransform.Y%2A> values of a <xref:System.Windows.Media.TranslateTransform> that is applied to the rectangle.</span></span> <span data-ttu-id="7a0b8-110">Hacen que el rectángulo se mueva horizontal y verticalmente a lo largo del trazado.</span><span class="sxs-lookup"><span data-stu-id="7a0b8-110">They make the rectangle move horizontally and vertically along the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#RotateAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/rotateanimationusingpathexample.xaml#rotateanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/RotateAnimationUsingPathExample.cs#rotateanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/RotateAnimationUsingPathExample.vb#rotateanimationusingpathwholepage)]  
  
 <span data-ttu-id="7a0b8-111">Otra manera de girar un objeto utilizando un trazado geométrico es usar un <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> de objeto y establecer su <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="7a0b8-111">Another way to rotate an object by using a geometric path is to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object and set its <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> property to `true`.</span></span> <span data-ttu-id="7a0b8-112">Para obtener más información y un ejemplo, vea [girar un objeto utilizando un trazado geométrico (animación de matriz)](../../../../docs/framework/wpf/graphics-multimedia/how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md).</span><span class="sxs-lookup"><span data-stu-id="7a0b8-112">For more information and an example, see [Rotate an Object by Using a Geometric Path (Matrix Animation)](../../../../docs/framework/wpf/graphics-multimedia/how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md).</span></span>  
  
 <span data-ttu-id="7a0b8-113">Para obtener un ejemplo completo, vea [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).</span><span class="sxs-lookup"><span data-stu-id="7a0b8-113">For the complete sample, see [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a0b8-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a0b8-114">See Also</span></span>  
 [<span data-ttu-id="7a0b8-115">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="7a0b8-115">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="7a0b8-116">Ejemplo de animación de trazado</span><span class="sxs-lookup"><span data-stu-id="7a0b8-116">Path Animation Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160028)  
 [<span data-ttu-id="7a0b8-117">Temas de procedimientos de animación de trazado</span><span class="sxs-lookup"><span data-stu-id="7a0b8-117">Path Animation How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
