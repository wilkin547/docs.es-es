---
title: 'Cómo: Animar la opacidad de un elemento o pincel'
ms.date: 03/30/2017
helpviewer_keywords:
- opacity [WPF], animating
- animation [WPF], Opacity property
ms.assetid: 572af23b-39dd-48d1-9db5-4bca56a4b3d3
ms.openlocfilehash: 549d3eab0d6d75403e962eeb146be8d7995cc931
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43421807"
---
# <a name="how-to-animate-the-opacity-of-an-element-or-brush"></a>Cómo: Animar la opacidad de un elemento o pincel
Para hacer que un elemento de marco fundido, puede animar su <xref:System.Windows.UIElement.Opacity%2A> puede animar la propiedad o el <xref:System.Windows.Media.Brush.Opacity%2A> propiedad de la <xref:System.Windows.Media.Brush> (o pinceles) utilizado para pintar. Animar la opacidad del elemento facilita y fundido sus elementos secundarios, pero animar el pincel utilizado para pintar el elemento le permite ser más selectivo sobre qué parte del elemento desaparece. Por ejemplo, podría animar la opacidad de un pincel que se usa para pintar el fondo de un botón. Esto provocaría que el fondo del botón para que aparezcan y desaparezcan de la vista, dejando su texto totalmente opaco.  
  
> [!NOTE]
>  Animar el <xref:System.Windows.Media.Brush.Opacity%2A> de un <xref:System.Windows.Media.Brush> ofrece ventajas de rendimiento respecto a animar el <xref:System.Windows.UIElement.Opacity%2A> propiedad de un elemento.  
  
 En el ejemplo siguiente, se animan dos botones para que fundido. La opacidad del primer <xref:System.Windows.Controls.Button> se anima desde `1.0` a `0.0` a través de un <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de cinco segundos. El segundo botón también se anima, pero la opacidad de SolidColorBrush utilizado para pintar su <xref:System.Windows.Controls.Control.Background%2A> se anima en lugar de la opacidad de todo el botón. Cuando se ejecuta el ejemplo, el primer botón completamente desaparece, mientras que sólo el fondo del segundo botón desaparece. Su texto y el borde permanecen completamente opacos.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[timingbehaviors_snip#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/OpacityAnimationExample.xaml#10)]  
  
 Se ha omitido el código en este ejemplo. El ejemplo completo también muestra cómo animar la opacidad de un <xref:System.Windows.Media.Color> dentro de un <xref:System.Windows.Media.LinearGradientBrush>.  Para obtener el ejemplo completo, vea el [animar la opacidad de un ejemplo de elemento](https://go.microsoft.com/fwlink/?LinkID=159968).
