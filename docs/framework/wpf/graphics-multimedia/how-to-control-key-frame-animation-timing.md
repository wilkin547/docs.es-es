---
title: Filtrar Controlar la temporización de animaciones de fotogramas clave
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], timing
- timing key-fram animation
ms.assetid: b059216f-7d4b-4ca8-a019-bc287ee7bf16
ms.openlocfilehash: 02171c4e2bf444d0bd31bc53fab9d451f081a93c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57353730"
---
# <a name="how-to-control-key-frame-animation-timing"></a>Filtrar Controlar la temporización de animaciones de fotogramas clave
En este ejemplo se muestra cómo controlar la temporización de fotogramas clave dentro de una animación de fotogramas clave. Al igual que otras animaciones, animaciones de fotogramas clave tienen una <xref:System.Windows.Media.Animation.Timeline.Duration%2A> propiedad. Además de especificar la duración de una animación, deberá especificar qué parte de esa duración se asigna a cada uno de los fotogramas clave. Para asignar el tiempo, especifica un <xref:System.Windows.Media.Animation.KeyTime> para cada fotograma clave en la animación.  
  
 El <xref:System.Windows.Media.Animation.KeyTime> para cada fotograma clave especifica cuando finaliza (no especificar el período de tiempo se reproduce un fotograma clave). Puede especificar un <xref:System.Windows.Media.Animation.KeyTime> como un <xref:System.TimeSpan> valor, como un porcentaje o como el <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> o <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> valor especial.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> para animar un rectángulo en la pantalla. Los tiempos clave de los fotogramas clave se establecen con <xref:System.TimeSpan> valores.  
  
 [!code-csharp[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimestimespanexample)]
 [!code-vb[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimestimespanexample)]
 [!code-xaml[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimestimespanexample)]  
  
 La siguiente ilustración se muestra cuando se alcanza el valor de cada fotograma clave.  
  
 ![Los valores de clave se alcanzan a 3, 4 y 10 segundos](./media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")  
  
 El ejemplo siguiente muestra una animación que es idéntica, salvo que los tiempos clave de los fotogramas clave se establecen con valores de porcentaje.  
  
 [!code-csharp[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespercentageexample)]
 [!code-vb[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespercentageexample)]
 [!code-xaml[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespercentageexample)]  
  
 La siguiente ilustración se muestra cuando se alcanza el valor de cada fotograma clave.  
  
 ![Los valores de clave se alcanzan a 3, 4 y 10 segundos](./media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")  
  
 El ejemplo siguiente se usa <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> tiempo valores de clave.  
  
 [!code-csharp[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimesuniformexample)]
 [!code-vb[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimesuniformexample)]
 [!code-xaml[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimesuniformexample)]  
  
 La siguiente ilustración se muestra cuando se alcanza el valor de cada fotograma clave.  
  
 ![Los valores de clave se alcanzan en 3.3,6.6, 6.6 y 9.9 segundos](./media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")  
  
 El último ejemplo utiliza <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> tiempo valores de clave.  
  
 [!code-csharp[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespacedexample)]
 [!code-vb[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespacedexample)]
 [!code-xaml[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespacedexample)]  
  
 La siguiente ilustración se muestra cuando se alcanza el valor de cada fotograma clave.  
  
 ![Los valores de clave se alcanzan a 0, 5 y 10 segundos](./media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")  
  
 Por motivos de simplicidad, las versiones de código de este ejemplo usan animaciones locales, no guiones gráficos, porque se aplica solo a una animación única a una sola propiedad, pero se pueden modificar los ejemplos para usar guiones gráficos en su lugar. Para obtener un ejemplo que muestra cómo declarar un guión gráfico en el código, consulte [animar una propiedad utilizando un guión gráfico](how-to-animate-a-property-by-using-a-storyboard.md).  
  
 Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://go.microsoft.com/fwlink/?LinkID=160012). Para obtener más información acerca de las animaciones de fotogramas clave, consulte el [información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md).  
  
## <a name="see-also"></a>Vea también
- [Información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md)
- [Información general sobre animaciones](animation-overview.md)
- [Temas "Cómo..."](animation-and-timing-how-to-topics.md)
