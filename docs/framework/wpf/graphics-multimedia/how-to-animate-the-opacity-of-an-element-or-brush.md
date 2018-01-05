---
title: "Cómo: Animar la opacidad de un elemento o pincel"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- opacity [WPF], animating
- animation [WPF], Opacity property
ms.assetid: 572af23b-39dd-48d1-9db5-4bca56a4b3d3
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c3b750e6ee21c8347d3896ec290f0ff564cc0a2c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-the-opacity-of-an-element-or-brush"></a>Cómo: Animar la opacidad de un elemento o pincel
Para hacer que un elemento de marco fundido, puede animar su <xref:System.Windows.UIElement.Opacity%2A> propiedad o se puede animar la <xref:System.Windows.Media.Brush.Opacity%2A> propiedad de la <xref:System.Windows.Media.Brush> (o pinceles) utilizado para pintar. Animar la opacidad del elemento facilita y fundido sus elementos secundarios, pero animar el pincel que se usa para pintar el elemento permite que sea más selectivo con respecto a qué parte del elemento fundido. Por ejemplo, podría animar la opacidad de un pincel utilizado para pintar el fondo del botón. Esto provocaría que el fondo del botón fundido de entrada y salida de la vista, dejando su texto completamente opaco.  
  
> [!NOTE]
>  Animar el <xref:System.Windows.Media.Brush.Opacity%2A> de un <xref:System.Windows.Media.Brush> ofrece ventajas de rendimiento respecto a animar la <xref:System.Windows.UIElement.Opacity%2A> propiedad de un elemento.  
  
 En el ejemplo siguiente, se animan dos botones para que atenuación u ocultar. La opacidad del primer <xref:System.Windows.Controls.Button> se anima desde `1.0` a `0.0` sobre un <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de cinco segundos. El segundo botón también se anima, pero la opacidad del objeto SolidColorBrush utilizado para pintar su <xref:System.Windows.Controls.Control.Background%2A> se anima en lugar de la opacidad de todo el botón. Cuando se ejecuta el ejemplo, el primer botón completamente desaparece, mientras que sólo el fondo del segundo botón desaparece de la vista. Su texto y borde permanecen totalmente opacos.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[timingbehaviors_snip#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/OpacityAnimationExample.xaml#10)]  
  
 Se ha omitido el código de este ejemplo. El ejemplo completo también muestra cómo animar la opacidad de un <xref:System.Windows.Media.Color> dentro de un <xref:System.Windows.Media.LinearGradientBrush>.  Para obtener el ejemplo completo, vea el [animar la opacidad de un ejemplo de elemento](http://go.microsoft.com/fwlink/?LinkID=159968).
