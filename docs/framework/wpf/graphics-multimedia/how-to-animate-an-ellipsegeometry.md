---
title: Procedimiento Animar un objeto EllipseGeometry
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], EllipseGeometry objects [WPF]
- EllipseGeometry objects [WPF], animating
- graphics [WPF], animation
ms.assetid: 767b9b6e-9cb7-482e-b6c2-fee7750c3995
ms.openlocfilehash: 0f8174a2144435c9ad65904ee587355e8b38e935
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760927"
---
# <a name="how-to-animate-an-ellipsegeometry"></a><span data-ttu-id="6e53e-102">Procedimiento Animar un objeto EllipseGeometry</span><span class="sxs-lookup"><span data-stu-id="6e53e-102">How to: Animate an EllipseGeometry</span></span>
<span data-ttu-id="6e53e-103">En este ejemplo se muestra cómo animar una <xref:System.Windows.Media.Geometry> dentro de un <xref:System.Windows.Shapes.Path> elemento.</span><span class="sxs-lookup"><span data-stu-id="6e53e-103">This example shows how to animate a <xref:System.Windows.Media.Geometry> within a <xref:System.Windows.Shapes.Path> element.</span></span> <span data-ttu-id="6e53e-104">En el ejemplo siguiente, un <xref:System.Windows.Media.Animation.PointAnimation> sirve para animar la <xref:System.Windows.Media.EllipseGeometry.Center%2A> de un <xref:System.Windows.Media.EllipseGeometry>.</span><span class="sxs-lookup"><span data-stu-id="6e53e-104">In the following example, a <xref:System.Windows.Media.Animation.PointAnimation> is used to animate the <xref:System.Windows.Media.EllipseGeometry.Center%2A> of an <xref:System.Windows.Media.EllipseGeometry>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e53e-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6e53e-105">Example</span></span>  
 [!code-xaml[animatepath_snip_XAML#1](~/samples/snippets/csharp/VS_Snippets_Wpf/animatepath_snip_XAML/CS/EllipseGeometryExample.xaml#1)]  
  
 [!code-csharp[animatepath_snip#101](~/samples/snippets/csharp/VS_Snippets_Wpf/animatepath_snip/CSharp/EllipseGeometryExample.cs#101)]  
  
 [!code-vb[animatepath_snip#201](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animatepath_snip/VisualBasic/EllipseGeometryExample.vb#201)]  
  
## <a name="see-also"></a><span data-ttu-id="6e53e-106">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e53e-106">See also</span></span>

- [<span data-ttu-id="6e53e-107">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="6e53e-107">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="6e53e-108">Información general sobre geometría</span><span class="sxs-lookup"><span data-stu-id="6e53e-108">Geometry Overview</span></span>](geometry-overview.md)
