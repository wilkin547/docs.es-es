---
title: "Cómo: Animar la posición de un objeto mediante PointAnimation"
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
- graphics [WPF], animation
- animation [WPF], PointAnimation
ms.assetid: 42310977-cc90-438a-8a47-0345898e01be
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: baa412a889ee82c9bf20ff1d6420d8a86f339ca6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-the-position-of-an-object-by-using-pointanimation"></a><span data-ttu-id="bebbe-102">Cómo: Animar la posición de un objeto mediante PointAnimation</span><span class="sxs-lookup"><span data-stu-id="bebbe-102">How to: Animate the Position of an Object by Using PointAnimation</span></span>
<span data-ttu-id="bebbe-103">Este ejemplo muestra cómo utilizar el <xref:System.Windows.Media.Animation.PointAnimation> clase para animar un objeto a lo largo de un <xref:System.Windows.Shapes.Path>.</span><span class="sxs-lookup"><span data-stu-id="bebbe-103">This example shows how to use the <xref:System.Windows.Media.Animation.PointAnimation> class to animate an object along a <xref:System.Windows.Shapes.Path>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bebbe-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bebbe-104">Example</span></span>  
 <span data-ttu-id="bebbe-105">En el ejemplo siguiente se mueve una elipse a lo largo de un <xref:System.Windows.Shapes.Path> desde un punto en la pantalla a otra.</span><span class="sxs-lookup"><span data-stu-id="bebbe-105">The following example moves an ellipse along a <xref:System.Windows.Shapes.Path> from one point on the screen to another.</span></span> <span data-ttu-id="bebbe-106">En el ejemplo se anima la posición de un <xref:System.Windows.Media.EllipseGeometry> utilizando <xref:System.Windows.Media.Animation.PointAnimation> para animar la <xref:System.Windows.Media.EllipseGeometry.Center%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="bebbe-106">The example animates the position of an <xref:System.Windows.Media.EllipseGeometry> by using <xref:System.Windows.Media.Animation.PointAnimation> to animate the <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span>  
  
 [!code-csharp[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/PointAnimationExample.cs#pointanimationwholepage)]
 [!code-vb[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/PointAnimationExample.vb#pointanimationwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="bebbe-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="bebbe-107">See Also</span></span>  
 <xref:System.Windows.Media.Animation.PointAnimation>  
 <xref:System.Windows.Shapes.Path>  
 <xref:System.Windows.Media.EllipseGeometry>  
 <xref:System.Windows.Media.EllipseGeometry.Center%2A>  
 [<span data-ttu-id="bebbe-108">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="bebbe-108">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="bebbe-109">Gráficos y multimedia</span><span class="sxs-lookup"><span data-stu-id="bebbe-109">Graphics and Multimedia</span></span>](../../../../docs/framework/wpf/graphics-multimedia/index.md)  
 [<span data-ttu-id="bebbe-110">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="bebbe-110">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/graphics-how-to-topics.md)  
 [<span data-ttu-id="bebbe-111">Animación y temporización</span><span class="sxs-lookup"><span data-stu-id="bebbe-111">Animation and Timing</span></span>](http://msdn.microsoft.com/en-us/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [<span data-ttu-id="bebbe-112">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="bebbe-112">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
