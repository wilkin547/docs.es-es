---
title: 'Cómo: Animar el valor del grosor de un borde'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF], animating changes to
- animation [WPF], changes to border thickness
ms.assetid: fd021978-f74b-4e7b-a7f7-3987dcad9e0f
ms.openlocfilehash: 4533ce6f2a1fe7243267ee8d638e2ad0a4f9cf3a
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124668"
---
# <a name="how-to-animate-a-borderthickness-value"></a>Cómo: Animar el valor del grosor de un borde
En este ejemplo se muestra cómo animar los cambios al grosor de un borde mediante la clase <xref:System.Windows.Media.Animation.ThicknessAnimation>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se anima el grosor de un borde mediante <xref:System.Windows.Media.Animation.ThicknessAnimation>. En el ejemplo se usa la propiedad <xref:System.Windows.Controls.Border.BorderThickness%2A> de <xref:System.Windows.Controls.Border>.  
  
 [!code-csharp[BasicAnimations_snip#ThicknessAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/ThicknessAnimationExample.cs#thicknessanimationwholepage)]
 [!code-vb[BasicAnimations_snip#ThicknessAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/ThicknessAnimationExample.vb#thicknessanimationwholepage)]  
  
 Para obtener el ejemplo completo, consulte [Galería de ejemplo de animación](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Media.Animation.ThicknessAnimation>
- <xref:System.Windows.Controls.Border.BorderThickness%2A>
- <xref:System.Windows.Controls.Border>
- [Información general sobre animaciones](../graphics-multimedia/animation-overview.md)
- [Temas de procedimientos de animación y control de tiempo](../graphics-multimedia/animation-and-timing-how-to-topics.md)
- [Animar el grosor de un borde mediante fotogramas clave](../graphics-multimedia/how-to-animate-the-thickness-of-a-border-by-using-key-frames.md)
