---
title: Filtrar Acumular valores de animaciones durante la repetición de ciclos
ms.date: 03/30/2017
helpviewer_keywords:
- accumulating animation values across repeating cycles [WPF]
- animation [WPF], accumulating values across repeating cycles
ms.assetid: 548df369-c7cc-4dab-b569-08b95ced2e7e
ms.openlocfilehash: 4b739883322751e2df86e13bfd07249abdb10a08
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59146021"
---
# <a name="how-to-accumulate-animation-values-during-repeat-cycles"></a>Filtrar Acumular valores de animaciones durante la repetición de ciclos
En este ejemplo se muestra cómo usar el <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> propiedad que se va a acumular valores de animaciones entre ciclos que se repiten.  
  
## <a name="example"></a>Ejemplo  
 Use el <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> propiedad que se va a acumular los valores base de una animación entre ciclos que se repiten. Por ejemplo, si establece una animación se repita 9 veces (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> = "9 x") y establezca la propiedad que se va a animar entre 10 y 15 (From = 10 a = 15), la propiedad se anima de 10 a 15 durante el primer ciclo de 15 a 20 durante el ciclo de segundo , de 20 a 25 durante el ciclo de terceros y así sucesivamente. Por lo tanto, cada ciclo de animación usa el valor final de la animación desde el ciclo de animación anterior como su valor base.  
  
 Puede usar el `IsCumulative` propiedad con animaciones más básicas y la mayoría de las animaciones de fotogramas clave. Para obtener más información, consulte [información general sobre animaciones](animation-overview.md) y [información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md).  
  
 El ejemplo siguiente muestra este comportamiento al animar el ancho de cuatro rectángulos. El ejemplo:  
  
-   Anima el primer rectángulo con <xref:System.Windows.Media.Animation.DoubleAnimation> y establece el <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> propiedad `true`.  
  
-   Anima el segundo rectángulo con <xref:System.Windows.Media.Animation.DoubleAnimation> y establece el <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> propiedad en el valor predeterminado de `false`.  
  
-   Anima el tercer rectángulo con <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> y establece el <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> propiedad `true`.  
  
-   Anima el último rectángulo con <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> y establece el <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> propiedad `false`.  
  
 [!code-xaml[timingbehaviors_snip#IsCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsCumulativeExample.xaml#iscumulativewholepage)]  
  
## <a name="see-also"></a>Vea también

- [Agregar un valor de salida de animación a un valor inicial de animación](how-to-add-an-animation-output-value-to-an-animation-starting-value.md)
- [Repetir una animación](how-to-repeat-an-animation.md)
- [Información general sobre animaciones](animation-overview.md)
- [Información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md)
- [Temas "Cómo..."](animation-and-timing-how-to-topics.md)
