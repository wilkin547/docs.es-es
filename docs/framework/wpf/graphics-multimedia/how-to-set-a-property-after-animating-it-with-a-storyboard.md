---
title: Filtrar Establecer una propiedad después de animarla con un guión gráfico
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], changing property values after
ms.assetid: 79466556-4dbf-40bd-9c1e-a77613b07077
ms.openlocfilehash: 2e1389392c6465ed56b2c71e53b2e3c1947acbe2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59188323"
---
# <a name="how-to-set-a-property-after-animating-it-with-a-storyboard"></a>Filtrar Establecer una propiedad después de animarla con un guión gráfico
En algunos casos, es posible que parece que no se puede cambiar el valor de una propiedad después de que se ha animado.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, un <xref:System.Windows.Media.Animation.Storyboard> sirve para animar el color de un <xref:System.Windows.Media.SolidColorBrush>. El guión gráfico se desencadena cuando se hace clic en el botón. El <xref:System.Windows.Media.Animation.Timeline.Completed> se controla el evento para que el programa recibe una notificación cuando el <xref:System.Windows.Media.Animation.ColorAnimation> se complete.  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton1Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton1declaration)]  
  
## <a name="example"></a>Ejemplo  
 Después de la <xref:System.Windows.Media.Animation.ColorAnimation> finalice, el programa intenta cambiar el color del pincel a azul.  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton1Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton1handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton1Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton1handler)]  
  
 El código anterior no parece hacer nada: la permanece pincel amarillo, que es el valor proporcionado por el <xref:System.Windows.Media.Animation.ColorAnimation> que anima el pincel. El valor de propiedad subyacente (el valor base) realmente se cambia a azul. Sin embargo, el valor efectivo o actual, sigue siendo amarillo porque la <xref:System.Windows.Media.Animation.ColorAnimation> continúa invalidando el valor base. Si desea que el valor base vuelva a ser el valor efectivo, debe detener la animación de influir en la propiedad. Hay tres maneras de hacer esto con animaciones de guión gráfico:  
  
-   Establecer la animación <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> propiedad <xref:System.Windows.Media.Animation.FillBehavior.Stop>  
  
-   Quitar el guión gráfico.  
  
-   Quitar la animación de la propiedad individual.  
  
## <a name="set-the-animations-fillbehavior-property-to-stop"></a>Establecer FillBehavior (propiedad) de la animación en Stop  
 Estableciendo <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> a <xref:System.Windows.Media.Animation.FillBehavior.Stop>, indica a la animación deje de afectar a su propiedad de destino una vez que llega al final de su período activo.  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton2Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton2declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton2Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton2handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton2Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton2handler)]  
  
## <a name="remove-the-entire-storyboard"></a>Quitar el guión gráfico  
 Mediante el uso de un <xref:System.Windows.Media.Animation.RemoveStoryboard> desencadenador o la <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType> método, indicar a las animaciones de guión gráfico para que dejen de afectar a sus propiedades de destino. La diferencia entre este enfoque y la configuración de la <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> propiedad es que puede quitar el guión gráfico en cualquier momento, mientras el <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> propiedad sólo tiene efecto cuando la animación alcanza el final de su período activo.  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton3Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton3declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton3Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton3handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton3Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton3handler)]  
  
## <a name="remove-an-animation-from-an-individual-property"></a>Quitar una animación de una propiedad individual  
 Otra técnica para detener una animación que afecte a una propiedad es usar el <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> método del objeto que se anima. Especifique la propiedad animada como primer parámetro y `null` como el segundo.  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton4Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton4declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton4Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton4handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton4Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton4handler)]  
  
 Esta técnica también funciona para las animaciones sin guiones gráficos.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType>
- <xref:System.Windows.Media.Animation.RemoveStoryboard>
- [Información general sobre animaciones](animation-overview.md)
- [Información general sobre técnicas de animación de propiedades](property-animation-techniques-overview.md)
