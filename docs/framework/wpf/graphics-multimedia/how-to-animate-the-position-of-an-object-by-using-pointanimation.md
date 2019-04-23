---
title: Procedimiento Animar la posición de un objeto mediante PointAnimation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], animation
- animation [WPF], PointAnimation
ms.assetid: 42310977-cc90-438a-8a47-0345898e01be
ms.openlocfilehash: 1ef3f77e551affaa7e61d2aabf95f10c29275417
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59111311"
---
# <a name="how-to-animate-the-position-of-an-object-by-using-pointanimation"></a><span data-ttu-id="da6c0-102">Procedimiento Animar la posición de un objeto mediante PointAnimation</span><span class="sxs-lookup"><span data-stu-id="da6c0-102">How to: Animate the Position of an Object by Using PointAnimation</span></span>
<span data-ttu-id="da6c0-103">En este ejemplo se muestra cómo usar el <xref:System.Windows.Media.Animation.PointAnimation> clase para animar un objeto a lo largo de un <xref:System.Windows.Shapes.Path>.</span><span class="sxs-lookup"><span data-stu-id="da6c0-103">This example shows how to use the <xref:System.Windows.Media.Animation.PointAnimation> class to animate an object along a <xref:System.Windows.Shapes.Path>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da6c0-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="da6c0-104">Example</span></span>  
 <span data-ttu-id="da6c0-105">En el ejemplo siguiente se mueve una elipse a lo largo de un <xref:System.Windows.Shapes.Path> desde un punto en la pantalla a otra.</span><span class="sxs-lookup"><span data-stu-id="da6c0-105">The following example moves an ellipse along a <xref:System.Windows.Shapes.Path> from one point on the screen to another.</span></span> <span data-ttu-id="da6c0-106">En el ejemplo se anima la posición de un <xref:System.Windows.Media.EllipseGeometry> utilizando <xref:System.Windows.Media.Animation.PointAnimation> para animar el <xref:System.Windows.Media.EllipseGeometry.Center%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="da6c0-106">The example animates the position of an <xref:System.Windows.Media.EllipseGeometry> by using <xref:System.Windows.Media.Animation.PointAnimation> to animate the <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span>  
  
 [!code-csharp[BasicAnimations_snip#PointAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/PointAnimationExample.cs#pointanimationwholepage)]
 [!code-vb[BasicAnimations_snip#PointAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/PointAnimationExample.vb#pointanimationwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="da6c0-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="da6c0-107">See also</span></span>

- <xref:System.Windows.Media.Animation.PointAnimation>
- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.EllipseGeometry>
- <xref:System.Windows.Media.EllipseGeometry.Center%2A>
- [<span data-ttu-id="da6c0-108">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="da6c0-108">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="da6c0-109">Gráficos y multimedia</span><span class="sxs-lookup"><span data-stu-id="da6c0-109">Graphics and Multimedia</span></span>](index.md)
- [<span data-ttu-id="da6c0-110">Temas de procedimientos de gráficos</span><span class="sxs-lookup"><span data-stu-id="da6c0-110">Graphics How-to Topics</span></span>](graphics-how-to-topics.md)
- [<span data-ttu-id="da6c0-111">Temas de procedimientos de temporización y animación</span><span class="sxs-lookup"><span data-stu-id="da6c0-111">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
