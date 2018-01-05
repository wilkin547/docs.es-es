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
# <a name="how-to-animate-the-position-of-an-object-by-using-pointanimation"></a>Cómo: Animar la posición de un objeto mediante PointAnimation
Este ejemplo muestra cómo utilizar el <xref:System.Windows.Media.Animation.PointAnimation> clase para animar un objeto a lo largo de un <xref:System.Windows.Shapes.Path>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se mueve una elipse a lo largo de un <xref:System.Windows.Shapes.Path> desde un punto en la pantalla a otra. En el ejemplo se anima la posición de un <xref:System.Windows.Media.EllipseGeometry> utilizando <xref:System.Windows.Media.Animation.PointAnimation> para animar la <xref:System.Windows.Media.EllipseGeometry.Center%2A> propiedad.  
  
 [!code-csharp[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/PointAnimationExample.cs#pointanimationwholepage)]
 [!code-vb[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/PointAnimationExample.vb#pointanimationwholepage)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.Animation.PointAnimation>  
 <xref:System.Windows.Shapes.Path>  
 <xref:System.Windows.Media.EllipseGeometry>  
 <xref:System.Windows.Media.EllipseGeometry.Center%2A>  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Gráficos y multimedia](../../../../docs/framework/wpf/graphics-multimedia/index.md)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/graphics-how-to-topics.md)  
 [Animación y temporización](http://msdn.microsoft.com/en-us/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
