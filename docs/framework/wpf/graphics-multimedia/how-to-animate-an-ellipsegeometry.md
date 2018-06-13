---
title: 'Cómo: Animar un EllipseGeometry'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], EllipseGeometry objects [WPF]
- EllipseGeometry objects [WPF], animating
- graphics [WPF], animation
ms.assetid: 767b9b6e-9cb7-482e-b6c2-fee7750c3995
ms.openlocfilehash: 223c435e3805fc897f5486f121cb4ffc922fb16d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558965"
---
# <a name="how-to-animate-an-ellipsegeometry"></a>Cómo: Animar un EllipseGeometry
Este ejemplo muestra cómo animar un <xref:System.Windows.Media.Geometry> dentro de un <xref:System.Windows.Shapes.Path> elemento. En el ejemplo siguiente, un <xref:System.Windows.Media.Animation.PointAnimation> se usa para animar la <xref:System.Windows.Media.EllipseGeometry.Center%2A> de un <xref:System.Windows.Media.EllipseGeometry>.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[animatepath_snip_XAML#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animatepath_snip_XAML/CS/EllipseGeometryExample.xaml#1)]  
  
 [!code-csharp[animatepath_snip#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animatepath_snip/CSharp/EllipseGeometryExample.cs#101)]  
  
 [!code-vb[animatepath_snip#201](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animatepath_snip/VisualBasic/EllipseGeometryExample.vb#201)]  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Información general sobre geometría](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
