---
title: Procedimiento Animar la opacidad de un elemento o pincel
ms.date: 03/30/2017
helpviewer_keywords:
- opacity [WPF], animating
- animation [WPF], Opacity property
ms.assetid: 572af23b-39dd-48d1-9db5-4bca56a4b3d3
ms.openlocfilehash: 2f18861eb18f81b631245d1d933b7acb1b3e0e42
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950512"
---
# <a name="how-to-animate-the-opacity-of-an-element-or-brush"></a>Procedimiento Animar la opacidad de un elemento o pincel
Para hacer que un elemento de marco se desvanezca y salga de la vista, puede <xref:System.Windows.UIElement.Opacity%2A> animar su propiedad o puede <xref:System.Windows.Media.Brush.Opacity%2A> animar la <xref:System.Windows.Media.Brush> propiedad de (o pinceles) que se usa para pintarla. Animar la opacidad del elemento hace que esta y sus elementos secundarios se muestreen y salgan de la vista, pero la animación del pincel que se usa para pintar el elemento le permite ser más selectivo sobre qué parte del elemento se atenúa. Por ejemplo, podría animar la opacidad de un pincel que se usa para pintar el fondo de un botón. Esto haría que el fondo del botón se desvanecera y fuera de la vista, mientras que el texto se quedaba totalmente opaco.  
  
> [!NOTE]
> Animar <xref:System.Windows.Media.Brush>deun proporciona ventajas de rendimiento sobre la <xref:System.Windows.UIElement.Opacity%2A> animación de la propiedad de un elemento. <xref:System.Windows.Media.Brush.Opacity%2A>  
  
 En el ejemplo siguiente, se animan dos botones para que se atenúen y desaparecen de la vista. La opacidad de la primera <xref:System.Windows.Controls.Button> se anima desde `1.0` hasta `0.0` <xref:System.Windows.Media.Animation.Timeline.Duration%2A> cinco segundos. El segundo botón también se anima, pero la opacidad del SolidColorBrush que se usa para pintar <xref:System.Windows.Controls.Control.Background%2A> su está animada en lugar de la opacidad del botón completo. Cuando se ejecuta el ejemplo, el primer botón se atenúa completamente y se aleja de la vista, mientras que solo el fondo del segundo botón se atenúa y sale de la vista. Su texto y borde permanecen totalmente opacos.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[timingbehaviors_snip#10](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/OpacityAnimationExample.xaml#10)]  
  
 El código se ha omitido en este ejemplo. En el ejemplo completo también se muestra cómo animar la opacidad <xref:System.Windows.Media.Color> de un <xref:System.Windows.Media.LinearGradientBrush>dentro de un.  Para obtener el ejemplo completo, vea el [ejemplo de animación de la opacidad de un elemento](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/OpacityAnimation).
