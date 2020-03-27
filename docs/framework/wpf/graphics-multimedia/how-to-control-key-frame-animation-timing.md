---
title: 'Cómo: Controlar la temporización de animaciones y fotogramas clave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], timing
- timing key-frame animation
ms.assetid: b059216f-7d4b-4ca8-a019-bc287ee7bf16
ms.openlocfilehash: 8cfd2be0bbc526ed92a5fb1b558a5a41dc9c3113
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344735"
---
# <a name="how-to-control-key-frame-animation-timing"></a>Cómo: Controlar la temporización de animaciones y fotogramas clave

En este ejemplo se muestra cómo controlar la sincronización de fotogramas clave dentro de una animación de fotograma clave. Al igual que otras animaciones, <xref:System.Windows.Media.Animation.Timeline.Duration%2A> las animaciones de fotogramas clave tienen una propiedad. Además de especificar la duración de una animación, debe especificar qué parte de esa duración se asigna a cada uno de sus fotogramas clave. Para indicar el tiempo, <xref:System.Windows.Media.Animation.KeyTime> especifique a para cada fotograma clave de la animación.

El <xref:System.Windows.Media.Animation.KeyTime> para cada fotograma clave especifica cuándo finaliza un fotograma clave (no especifica el tiempo que se reproduce un fotograma clave). Puede especificar <xref:System.Windows.Media.Animation.KeyTime> como <xref:System.TimeSpan> un valor, como un <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> porcentaje <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> o como el valor especial.

## <a name="example"></a>Ejemplo

En el ejemplo <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> siguiente se usa a para animar un rectángulo a través de la pantalla. Los tiempos clave de <xref:System.TimeSpan> los fotogramas clave se establecen con valores.

[!code-csharp[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimestimespanexample)]
[!code-vb[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimestimespanexample)]
[!code-xaml[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimestimespanexample)]

La siguiente ilustración muestra cuándo se alcanza el valor de cada fotograma clave.

![Los valores de clave se alcanzan a 3, 4 y 10 segundos](./media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")

En el ejemplo siguiente se muestra una animación idéntica, excepto que los tiempos clave de los fotogramas clave se establecen con valores de porcentaje.

[!code-csharp[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespercentageexample)]
[!code-vb[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespercentageexample)]
[!code-xaml[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespercentageexample)]

La siguiente ilustración muestra cuándo se alcanza el valor de cada fotograma clave.

![Los valores de clave se alcanzan a 3, 4 y 10 segundos](./media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")

En el <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> ejemplo siguiente se utilizan valores de tiempo clave.

[!code-csharp[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimesuniformexample)]
[!code-vb[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimesuniformexample)]
[!code-xaml[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimesuniformexample)]

La siguiente ilustración muestra cuándo se alcanza el valor de cada fotograma clave.

![Los valores de clave se alcanzan a 3.3, 6.6 y 9.9 segundos](./media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")

El ejemplo <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> final utiliza valores de tiempo clave.

[!code-csharp[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespacedexample)]
[!code-vb[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespacedexample)]
[!code-xaml[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespacedexample)]

La siguiente ilustración muestra cuándo se alcanza el valor de cada fotograma clave.

![Los valores de clave se alcanzan a 0, 5 y 10 segundos](./media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")

Para simplificar, las versiones de código de este ejemplo usan animaciones locales, no guiones gráficos, porque solo se aplica una sola animación a una sola propiedad, pero los ejemplos se pueden modificar para usar guiones gráficos en su lugar. Para obtener un ejemplo que muestra cómo declarar un guión gráfico en el código, vea [Animar una propiedad mediante un guión gráfico](how-to-animate-a-property-by-using-a-storyboard.md).

Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation). Para obtener más información acerca de las animaciones de fotogramas clave, vea Información general sobre [animaciones de fotogramas](key-frame-animations-overview.md)clave .

## <a name="see-also"></a>Vea también

- [Información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md)
- [Información general sobre animaciones](animation-overview.md)
- [Temas "Cómo..."](animation-and-timing-how-to-topics.md)
