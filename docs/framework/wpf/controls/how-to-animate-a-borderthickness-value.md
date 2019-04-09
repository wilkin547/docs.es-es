---
title: Filtrar Animar el valor del grosor de un borde
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF], animating changes to
- animation [WPF], changes to border thickness
ms.assetid: fd021978-f74b-4e7b-a7f7-3987dcad9e0f
ms.openlocfilehash: 10e177d1f6d6add4638ce14af900e75d7e363890
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59150740"
---
# <a name="how-to-animate-a-borderthickness-value"></a>Filtrar Animar el valor del grosor de un borde
En este ejemplo se muestra cómo animar los cambios realizados en el grosor de un borde mediante la <xref:System.Windows.Media.Animation.ThicknessAnimation> clase.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se anima el grosor de un borde mediante el uso de <xref:System.Windows.Media.Animation.ThicknessAnimation>. El ejemplo se usa el <xref:System.Windows.Controls.Border.BorderThickness%2A> propiedad de <xref:System.Windows.Controls.Border>.  
  
 [!code-csharp[BasicAnimations_snip#ThicknessAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/ThicknessAnimationExample.cs#thicknessanimationwholepage)]
 [!code-vb[BasicAnimations_snip#ThicknessAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/ThicknessAnimationExample.vb#thicknessanimationwholepage)]  
  
 Para obtener un ejemplo completo, vea [Animation Example Gallery](https://go.microsoft.com/fwlink/?LinkID=159969).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.Animation.ThicknessAnimation>
- <xref:System.Windows.Controls.Border.BorderThickness%2A>
- <xref:System.Windows.Controls.Border>
- [Información general sobre animaciones](../graphics-multimedia/animation-overview.md)
- [Temas "Cómo..." de animación y control de tiempo](../graphics-multimedia/animation-and-timing-how-to-topics.md)
- [Animar el grosor de un borde mediante fotogramas clave](../graphics-multimedia/how-to-animate-the-thickness-of-a-border-by-using-key-frames.md)
