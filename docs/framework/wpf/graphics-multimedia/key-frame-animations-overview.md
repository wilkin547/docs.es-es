---
title: Información general sobre animaciones de fotogramas clave
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], key-frame
- key frames [WPF], about key-frame animations
- multiple animation target values [WPF]
ms.assetid: 10028f97-bb63-41fc-b8ad-663dac7ea203
ms.openlocfilehash: f163b71d7a33aa115a2a4600cac08b7e4b2e80e7
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43517411"
---
# <a name="key-frame-animations-overview"></a>Información general sobre animaciones de fotogramas clave
Este tema es una introducción a las animaciones de fotogramas clave. Las animaciones de fotogramas clave le permiten realizar animaciones con más de dos valores de destino y controlan el método de interpolación de una animación.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 Para entender esta introducción, debe conocer las animaciones y escalas de tiempo de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Consulte [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) para ver una introducción a las animaciones. También resulta útil conocer las animaciones From/To/By. Para más información, consulte la información general sobre animaciones From/To/By.  
  
<a name="whatisakeyframeanimation"></a>   
## <a name="what-is-a-key-frame-animation"></a>¿Qué es una animación de fotogramas clave?  
 Al igual que una animación From/To/By, una animación de fotogramas clave anima el valor de una propiedad de destino. Crea una transición entre sus valores de destino a través de su <xref:System.Windows.Media.Animation.Timeline.Duration%2A>. Sin embargo, mientras que una animación From/To/By crea una transición entre dos valores, una animación de fotogramas clave única puede crear transiciones entre cualquier número de valores de destino. A diferencia de una animación From/To/By, una animación de fotogramas clave no tiene propiedades From, To o By con las cuales establecer sus valores de destino. Los valores de destino de una animación de fotogramas clave se describen con objetos de fotogramas clave (de ahí surge el término "animación de fotogramas clave"). Para especificar los valores de destino de la animación, puede crear objetos de fotograma clave y agregarlos a la animación <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.KeyFrames%2A> colección. Cuando se ejecuta la animación, transiciona entre los fotogramas que especificó.  
  
 Además de admitir varios valores de destino, algunos métodos de fotogramas clave incluso admiten varios métodos de interpolación. El método de interpolación de una animación define cómo transiciona de un valor al siguiente. Hay tres tipos de interpolaciones: discreta, lineal y spline.  
  
 Para animar con una animación de fotogramas clave, debe completar los pasos siguientes.  
  
-   Declare la animación y especifique su <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, tal como lo haría para una animación from/to/by.  
  
-   Para cada valor de destino, cree un fotograma clave del tipo adecuado, establezca su valor y <xref:System.Windows.Media.Animation.KeyTime>y su incorporación a la animación <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.KeyFrames%2A> colección.  
  
-   Asocie la animación a una propiedad, tal como lo haría con una animación From/To/By. Para más información sobre cómo aplicar una animación a una propiedad a través de un guión gráfico, consulte [Información sobre objetos Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> para animar un <xref:System.Windows.Shapes.Rectangle> elemento a cuatro ubicaciones diferentes.  
  
 [!code-xaml[keyframes_ovw_snippet#BasicKeyFrameExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyFramesIntroduction.xaml#basickeyframeexamplewholepage)]  
  
 Al igual que un From/To/By animación, una animación de fotogramas clave se puede aplicar a una propiedad mediante el uso de un <xref:System.Windows.Media.Animation.Storyboard> en marcado y código o mediante el <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> método en el código. También puede usar una animación de fotogramas clave para crear un <xref:System.Windows.Media.Animation.AnimationClock> y aplicarla a una o varias propiedades. Para más información sobre los distintos métodos para aplicar animaciones, consulte la [Información general sobre técnicas de animación de propiedades](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
<a name="animation_types"></a>   
## <a name="key-frame-animation-types"></a>Tipos de animación de fotogramas clave  
 Dado que las animaciones generan valores de propiedad, existen distintos tipos de animaciones para los diversos tipos de propiedades. Para animar una propiedad que acepta un <xref:System.Double> (por ejemplo, un elemento <xref:System.Windows.FrameworkElement.Width%2A> propiedad), se usa una animación que genera <xref:System.Double> valores. Para animar una propiedad que acepta un <xref:System.Windows.Point>, use una animación que genera <xref:System.Windows.Point> valores y así sucesivamente.  
  
 Las clases de animación de fotogramas clave pertenecen a la <xref:System.Windows.Media.Animation> espacio de nombres y cumplen con la convención de nomenclatura siguiente:  
  
 *\<Tipo>* `AnimationUsingKeyFrames`  
  
 Donde *\<Tipo>* es el tipo de valor que la clase anima.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona las siguientes clases de animación de fotogramas clave.  
  
|Tipo de propiedad|Clase de animación From/To/By correspondiente|Métodos de interpolación admitidos|  
|-------------------|------------------------------------------------|-------------------------------------|  
|<xref:System.Boolean>|<xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>|Discreta|  
|<xref:System.Byte>|<xref:System.Windows.Media.Animation.ByteAnimationUsingKeyFrames>|Discreta, lineal, spline|  
|<xref:System.Windows.Media.Color>|<xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>|Discreta, lineal, spline|  
|<xref:System.Decimal>|<xref:System.Windows.Media.Animation.DecimalAnimationUsingKeyFrames>|Discreta, lineal, spline|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>|Discreta, lineal, spline|  
|<xref:System.Int16>|<xref:System.Windows.Media.Animation.Int16AnimationUsingKeyFrames>|Discreta, lineal, spline|  
|<xref:System.Int32>|<xref:System.Windows.Media.Animation.Int32AnimationUsingKeyFrames>|Discreta, lineal, spline|  
|<xref:System.Int64>|<xref:System.Windows.Media.Animation.Int64AnimationUsingKeyFrames>|Discreta, lineal, spline|  
|<xref:System.Windows.Media.Matrix>|<xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames>|Discreta|  
|<xref:System.Object>|<xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>|Discreta|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>|Discreta, lineal, spline|  
|<xref:System.Windows.Media.Media3D.Quaternion>|<xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames>|Discreta, lineal, spline|  
|<xref:System.Windows.Rect>|<xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>|Discreta, lineal, spline|  
|<xref:System.Windows.Media.Media3D.Rotation3D>|<xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames>|Discreta, lineal, spline|  
|<xref:System.Single>|<xref:System.Windows.Media.Animation.SingleAnimationUsingKeyFrames>|Discreta, lineal, spline|  
|<xref:System.String>|<xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>|Discreta|  
|<xref:System.Windows.Size>|<xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>|Discreta, lineal, spline|  
|<xref:System.Windows.Thickness>|<xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames>|Discreta, lineal, spline|  
|<xref:System.Windows.Media.Media3D.Vector3D>|<xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames>|Discreta, lineal, spline|  
|<xref:System.Windows.Vector>|<xref:System.Windows.Media.Animation.VectorAnimationUsingKeyFrames>|Discreta, lineal, spline|  
  
<a name="animation_target_values"></a>   
## <a name="target-values-key-frames-and-key-times"></a>Valores de destino (fotogramas clave) y valores KeyTime  
 Del mismo modo que hay distintos tipos de animaciones de fotogramas clave para animar diferentes tipos de propiedades, también hay distintos tipos de objetos de fotogramas clave: uno para cada tipo de valor animado y método de interpolación admitido. Los tipos de fotogramas clave cumplen con la convención de nomenclatura siguiente:  
  
 *\<MétodoInterpolación>\<Tipo>* `KeyFrame`  
  
 Donde *\<MétodoInterpolación>* es el método de interpolación que el fotograma clave usa y *\<Tipo>* es el tipo de valor que la clase anima. Una animación de fotogramas clave que admite los tres métodos de interpolación tendrá tres tipos de fotogramas clave que se pueden usar. Por ejemplo, puede usar tres tipos de fotogramas clave con un <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>: <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>, <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>, y <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>. (Los métodos de interpolación se describen detalladamente en una sección posterior).  
  
 El propósito principal de un fotograma clave es especificar un <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> y un <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A>. Cada tipo de fotograma clave proporciona estas dos propiedades.  
  
-   El <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> propiedad especifica el valor de destino para ese fotograma clave.  
  
-   El <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> propiedad especifica cuándo (dentro de la animación <xref:System.Windows.Media.Animation.Timeline.Duration%2A>) un fotograma clave <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> se alcanza.  
  
 Cuando se inicia una animación de fotogramas clave, itera a través de los fotogramas clave en el orden definido por sus <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> propiedades.  
  
-   Si no hay ningún fotograma clave en tiempo de 0, la animación crea una transición entre el valor actual de la propiedad de destino y el <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> del primer fotograma clave; en caso contrario, la animación de salida de valor se convierte en el valor del primer fotograma clave.  
  
-   La animación crea una transición entre el <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> de los fotogramas clave de primeros y segundo mediante el método de interpolación especificado por el segundo fotograma clave. La transición comienza en el primer fotograma clave <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> y cuando finaliza el segundo fotograma clave <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> se alcanza.  
  
-   La animación continúa y crea transiciones entre cada fotograma clave subsiguiente y el fotograma clave precedente.  
  
-   Por último, las transiciones de animación en el valor del fotograma clave con el mayor tiempo clave que es igual o menor que la animación <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.  
  
 Si la animación <xref:System.Windows.Media.Animation.Timeline.Duration%2A> es <xref:System.Windows.Duration.Automatic%2A> o su <xref:System.Windows.Media.Animation.Timeline.Duration%2A> es igual a la hora del último fotograma clave, los extremos de la animación. De lo contrario, si la animación <xref:System.Windows.Duration> es mayor que el tiempo clave del último fotograma clave, las suspensiones de animación, el valor del fotograma clave hasta que llega al final de su <xref:System.Windows.Duration>. Al igual que todas las animaciones, se usa una animación de fotogramas clave su <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> propiedad para determinar si retiene el valor final cuando llega al final de su período activo. Para más información, consulte [Información general sobre comportamientos de control de tiempo](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md).  
  
 En el ejemplo siguiente se usa el <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> objeto definido en el ejemplo anterior para demostrar cómo el <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> y <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> las propiedades.  
  
-   El primer fotograma clave establece inmediatamente el valor de salida de la animación en 0.  
  
-   El segundo fotograma clave anima desde 0 a 350. Se inicia cuando finaliza el primer fotograma clave (a los 0 segundos) y se reproduce durante 2 segundos, finalizando en 0:0:2.  
  
-   El tercer fotograma clave anima desde 350 a 50. Se inicia cuando finaliza el segundo fotograma clave (a los 2 segundos) y se reproduce durante 5 segundos, finalizando en 0:0:7.  
  
-   El cuarto fotograma clave anima desde 50 a 200. Se inicia cuando finaliza el tercer fotograma clave (a los 7 segundos) y se reproduce durante 1 segundo, finalizando en 0:0:8.  
  
-   Dado que el <xref:System.Windows.Media.Animation.Timeline.Duration%2A> propiedad de la animación se estableció en 10 segundos, la animación retiene su valor final durante dos segundos antes de finalizar en el tiempo = 0:0:10.  
  
 [!code-xaml[keyframes_ovw_snippet#BasicKeyFrameExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyFramesIntroduction.xaml#basickeyframeexamplewholepage)]  
  
<a name="interpolationmethods"></a>   
## <a name="interpolation-methods"></a>Métodos de interpolación  
 En las secciones anteriores se mencionó que algunas animaciones de fotogramas clave admiten varios métodos de interpolación. La interpolación de una animación describe cómo una animación transiciona entre los valores a lo largo de su duración. Si selecciona el tipo de fotograma clave usar con la animación, puede definir el método de interpolación para ese segmento de fotogramas clave. Hay tres tipos de métodos de interpolación distintos: lineal, discreta y spline.  
  
### <a name="linear-interpolation"></a>Interpolación lineal  
 Con la interpolación lineal, la animación avanza a una velocidad constante de la duración del segmento. Por ejemplo, si un segmento de fotogramas clave transiciona desde 0 a 10 durante 5 segundos, la animación generará los valores siguientes en los momentos especificados:  
  
|Tiempo|Valor de salida|  
|----------|------------------|  
|0|0|  
|1|2|  
|2|4|  
|3|6|  
|4|8|  
|4.25|8.5|  
|4.5|9|  
|5|10|  
  
### <a name="discrete-interpolation"></a>Interpolación discreta  
 Con la interpolación discreta, la función de animación pasa de un valor al siguiente sin interpolación. Si un segmento de fotogramas clave transiciona desde 0 a 10 durante 5 segundos, la animación generará los valores siguientes en los momentos especificados:  
  
|Hora|Valor de salida|  
|----------|------------------|  
|0|0|  
|1|0|  
|2|0|  
|3|0|  
|4|0|  
|4.25|0|  
|4.5|0|  
|5|10|  
  
 Tenga en cuenta que la animación no cambia su valor de salida hasta el final mismo de la duración del segmento.  
  
 La interpolación spline es más compleja. Esta interpolación se describe en la sección siguiente.  
  
<a name="anim_spline"></a>   
### <a name="splined-interpolation"></a>Interpolación spline  
 La interpolación spline se puede usar para lograr efectos de control de tiempo más realistas. Debido a que las animaciones se usan a menudo para imitar los efectos que ocurren en el mundo real, es posible que los desarrolladores necesiten un control detallado de la aceleración y la desaceleración de objetos y una manipulación cercana de los segmentos de tiempo. Los fotogramas clave de spline le permiten animar con la interpolación spline. Con otros fotogramas clave, especifica un <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> y <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A>. Con un fotograma clave spline, también se especifica un <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A>. El ejemplo siguiente muestra un fotograma clave de spline único para un <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>. Tenga en cuenta el <xref:System.Windows.Media.Animation.KeySpline> propiedad; que es lo que hace un fotograma clave spline difieren de los otros tipos de fotogramas clave.  
  
 [!code-xaml[keyframes_ovw_snippet#SingleSplineKeyFrameExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/InterpolationMethodsExample.xaml#singlesplinekeyframeexample)]  
  
 Un punto inicial, un punto final y dos puntos de control definen una curva Bézier cúbica. El <xref:System.Windows.Media.Animation.KeySpline> propiedad de un fotograma clave de spline define los dos puntos de control de una curva de Bézier que se extiende desde (0,0) a (1,1). El primer punto de control controla el factor de curva de la primera mitad de la curva Bézier, mientras que el segundo punto de control, el factor de curva de la segunda mitad. La curva resultante describe la tasa de cambio de ese fotograma clave de spline. Cuanto más inclinada sea la curva, el fotograma clave cambia sus valores más rápidamente. A medida que la curva es cada vez más plana, el fotograma clave cambia sus valores más lentamente.  
  
 Puede usar <xref:System.Windows.Media.Animation.KeySpline> para simular trayectorias físicas como pertenecientes a agua o que las bolas que o aplique otros efectos de "salida lenta" y "lenta" a las animaciones de movimiento. Para obtener efectos de interacción con el usuario, como el fundido en el fondo o el rebote del botón de control, podría aplicar la interpolación spline para acelerar o ralentizar la tasa de cambio de una animación de una forma específica.  
  
 En el ejemplo siguiente se especifica un <xref:System.Windows.Media.Animation.KeySpline> de 0,1 1,0, lo que crea la siguiente curva Bézier.  
  
 ![Una curva de Bézier](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyspline-0-1-1-0.png "graphicsmm_keyspline_0_1_1_0")  
Una curva spline clave con los puntos de control (0.0, 1.0) y (1.0, 0.0)  
  
 [!code-xaml[keyframes_ovw_snippet#SingleSplineKeyFrameExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/InterpolationMethodsExample.xaml#singlesplinekeyframeexample)]  
  
 Este fotograma clave se anima rápidamente cuando comienza, disminuye la velocidad y vuelve a acelerarla antes de finalizar.  
  
 En el ejemplo siguiente se especifica un <xref:System.Windows.Media.Animation.KeySpline> de 0.5,0.25 0.75,1.0, que crea la siguiente curva Bézier.  
  
 ![Una curva de Bézier](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyspline-025-050-075-10.png "graphicsmm_keyspline_025_050_075_10")  
Una curva spline clave con los puntos de control (0.25, 0.5) y (0.75, 1.0)  
  
 [!code-xaml[keyframes_ovw_snippet#SingleSplineKeyFrameExampleInline3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/InterpolationMethodsExample.xaml#singlesplinekeyframeexampleinline3)]  
  
 Debido a que la curvatura de la curva Bézier cambia muy poco, este fotograma clave se anima a una velocidad casi constante; disminuye la velocidad cerca del final.  
  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> para animar la posición del rectángulo. Dado que el <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> usa <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> objetos, la transición entre cada valor del fotograma clave usa la interpolación spline.  
  
 [!code-xaml[keyframes_ovw_snippet#SplinedInterpolationExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/InterpolationMethodsExample.xaml#splinedinterpolationexample)]  
  
 La interpolación spline puede ser difícil de entender, por lo que puede resultar útil experimentar distintas configuraciones. El [ejemplo de animación de curva spline clave](https://go.microsoft.com/fwlink/?LinkID=160011) le permite cambiar los valores de curva spline clave y ver el resultado que esto tiene en una animación.  
  
<a name="combininginterpolationmethods"></a>   
### <a name="combining-interpolation-methods"></a>Combinación de métodos de interpolación  
 Puede usar fotogramas clave con distintos tipos de interpolación en una animación de fotogramas clave única. Cuando se encuentran dos animaciones de fotogramas clave con distintas interpolaciones, el método de interpolación del segundo fotograma clave se usa para crear la transición desde el primer valor al segundo.  
  
 En el ejemplo siguiente, un <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> se crea que usa la interpolación lineal, spline y discreta.  
  
 [!code-xaml[keyframes_ovw_snippet#ComboInterpolationExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/InterpolationMethodsExample.xaml#combointerpolationexample)]  
  
<a name="keytimes"></a>   
## <a name="more-about-duration-and-key-times"></a>Más información sobre Duration y KeyTimes  
 Al igual que otras animaciones, animaciones de fotogramas clave tienen una <xref:System.Windows.Duration> propiedad. Además de especificar la animación <xref:System.Windows.Duration>, deberá especificar qué parte de esa duración se asigna a cada fotograma clave. Para ello, que describe un <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> para cada uno de fotogramas clave la animación de. Cada fotograma clave <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> especifica cuándo finaliza ese fotograma clave.  
  
 El <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> propiedad no especifica cuánto tiempo se reproduce el tiempo clave. La cantidad de tiempo durante el cual se reproduce un fotograma clave se determina en virtud del momento en que finaliza el fotograma clave, cuándo finaliza el fotograma clave anterior y la duración de la animación. Se pueden especificar tiempos clave como un valor de tiempo, un porcentaje, o como los valores especiales <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> o <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>.  
  
 En la lista siguiente se describen las distintas formas de especificar los tiempos clave.  
  
### <a name="timespan-values"></a>Valores TimeSpan  
 Puede usar <xref:System.TimeSpan> valores para especificar un <xref:System.Windows.Media.Animation.KeyTime>. El valor debe ser mayor o igual que 0 y menor o igual que la duración de la animación. En el ejemplo siguiente se muestra una animación con una duración de 10 segundos y 4 fotogramas clave cuyos tiempos clave están especificados como valores de tiempo.  
  
-   El primer fotograma clave anima desde el valor base a 100 durante los primeros 3 segundos y finaliza en 0:0:03.  
  
-   El segundo fotograma clave anima desde 100 a 200. Se inicia cuando finaliza el primer fotograma clave (a los 3 segundos) y se reproduce durante 5 segundos, finalizando en 0:0:8.  
  
-   El tercer fotograma clave anima desde 200 a 500. Se inicia cuando finaliza el segundo fotograma clave (a los 8 segundos) y se reproduce durante 1 segundo, finalizando en 0:0:9.  
  
-   El cuarto fotograma clave anima desde 500 a 600. Se inicia cuando finaliza el tercer fotograma clave (a los 9 segundos) y se reproduce durante 1 segundo, finalizando en 0:0:10.  
  
 [!code-xaml[keyframes_ovw_snippet#TimeSpanKeyTimeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyTimesExample.xaml#timespankeytimeexample)]  
  
### <a name="percentage-values"></a>Valores de porcentaje  
 Un valor de porcentaje especifica que el fotograma clave finaliza en algún porcentaje de la animación <xref:System.Windows.Media.Animation.Timeline.Duration%2A>. En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], especifica el porcentaje como un número, seguido del símbolo `%`. En el código, usa el <xref:System.Windows.Media.Animation.KeyTime.FromPercent%2A> método y pásele un <xref:System.Double> que indica el porcentaje. El valor debe ser mayor o igual que 0 y menor o igual que 100 por ciento. En el ejemplo siguiente se muestra una animación con una duración de 10 segundos y 4 fotogramas clave cuyos tiempos clave están especificados como porcentajes.  
  
-   El primer fotograma clave anima desde el valor base a 100 durante los primeros 3 segundos y finaliza en 0:0:3.  
  
-   El segundo fotograma clave anima desde 100 a 200. Se inicia cuando finaliza el primer fotograma clave (a los 3 segundos) y se reproduce durante 5 segundos, finalizando en 0:0:8 (0.8 * 10 = 8).  
  
-   El tercer fotograma clave anima desde 200 a 500. Se inicia cuando finaliza el segundo fotograma clave (a los 8 segundos) y se reproduce durante 1 segundo, finalizando en 0:0:9 (0.9 * 10 = 9).  
  
-   El cuarto fotograma clave anima desde 500 a 600. Se inicia cuando finaliza el tercer fotograma clave (a los 9 segundos) y se reproduce durante 1 segundo, finalizando en 0:0:10 (1 * 10 = 10).  
  
 [!code-xaml[keyframes_ovw_snippet#PercentageKeyTimeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyTimesExample.xaml#percentagekeytimeexample)]  
  
### <a name="special-value-uniform"></a>Valor especial, Uniform  
 Use <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> cuando desee que cada fotograma clave a la misma cantidad de tiempo de control de tiempo.  
  
 Un <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> tiempo clave divide el tiempo disponible por igual por el número de fotogramas clave para determinar la hora de finalización de cada fotograma clave. El ejemplo siguiente muestra una animación con una duración de 10 segundos y fotogramas clave cuatro veces cuya clave se especifican como <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A>.  
  
-   El primer fotograma clave anima desde el valor base a 100 durante los primeros 2.5 segundos y finaliza en 0:0:2.5.  
  
-   El segundo fotograma clave anima desde 100 a 200. Se inicia cuando finaliza el primer fotograma clave (a los 2.5 segundos) y se reproduce aproximadamente durante 2.5 segundos, finalizando en 0:0:5.  
  
-   El tercer fotograma clave anima desde 200 a 500. Se inicia cuando finaliza el segundo fotograma clave (a los 5 segundos) y se reproduce durante 2.5 segundos, finalizando en 0:0:7.5.  
  
-   El cuarto fotograma clave anima desde 500 a 600. Se inicia cuando finaliza el segundo fotograma clave (a los 7.5 segundos) y se reproduce durante 2.5 segundos, finalizando en 0:0:1.  
  
 [!code-xaml[keyframes_ovw_snippet#UniformKeyTimeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyTimesExample.xaml#uniformkeytimeexample)]  
  
### <a name="special-value-paced"></a>Valor especial, Paced  
 Use <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> agota el tiempo cuando desea animar a una velocidad constante.  
  
 Un <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> tiempo clave asigna el tiempo disponible según la longitud de cada uno de los fotogramas clave para determinar la duración de cada fotograma.  Esto proporcionará el comportamiento de que la velocidad o el ritmo de la animación siga constante.  El ejemplo siguiente muestra una animación con una duración de 10 segundos y fotogramas clave tres veces cuya clave se especifican como <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>.  
  
 [!code-xaml[keyframes_ovw_snippet#PacedKeyTimeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyTimesExample.xaml#pacedkeytimeexample)]  
  
 Tenga en cuenta que, si el tiempo clave del último fotograma clave es <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> o <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A>, el tiempo clave resuelto se establecerá en 100 por ciento. Si el primer fotograma clave de una animación de varios fotogramas es Paced, el tiempo clave resuelto se establecerá en 0. (Si la colección de fotogramas clave solo contiene un fotograma clave y es un fotograma clave Paced, el tiempo clave resuelto se establecerá en 100 por ciento).  
  
 Los distintos fotogramas clave dentro de una animación de fotogramas clave pueden usar distintos tipos de tiempo clave.  
  
<a name="combiningkeytimes"></a>   
## <a name="combining-key-times-out-of-order-key-frames"></a>Combinación de tiempos clave y fotogramas clave desordenados  
 Puede usar fotogramas clave con diferentes <xref:System.Windows.Media.Animation.KeyTime> tipos en la misma animación de valor. Además, si bien se recomienda agregar fotogramas clave en el orden en que se deben reproducir, no es necesario hacerlo. El sistema de control de tiempo y animación es capaz de resolver los fotogramas clave desordenados. Se omiten los fotogramas con tiempos clave no válidos.  
  
 En la lista siguiente se describe el procedimiento mediante el cual se resuelven los tiempos clave para los fotogramas clave de una animación de fotogramas clave.  
  
1.  Resolver <xref:System.TimeSpan> <xref:System.Windows.Media.Animation.KeyTime> valores.  
  
2.  Determine el *tiempo de interpolación total*, que es el tiempo total que la animación de fotogramas clave tarda en completar una iteración de avance.  
  
    1.  Si la animación <xref:System.Windows.Media.Animation.Timeline.Duration%2A> no <xref:System.Windows.Duration.Automatic%2A> o <xref:System.Windows.Duration.Forever%2A>, el tiempo de interpolación total es el valor de la animación <xref:System.Windows.Media.Animation.Timeline.Duration%2A> propiedad.  
  
    2.  En caso contrario, es el mayor tiempo de interpolación total <xref:System.TimeSpan> <xref:System.Windows.Media.Animation.KeyTime> valor especificado entre sus fotogramas clave, si existe alguno.  
  
    3.  De lo contrario, el tiempo de interpolación total es de 1 segundo.  
  
3.  Utilice el valor de tiempo de interpolación total para resolver <xref:System.Windows.Media.Animation.KeyTimeType.Percent> <xref:System.Windows.Media.Animation.KeyTime> valores.  
  
4.  Resuelva el último fotograma clave, si no se resolvió ya en los pasos anteriores. Si el <xref:System.Windows.Media.Animation.KeyTime> del último fotograma clave es <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> o <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>, su tiempo de resolución será igual que el tiempo de interpolación total.  
  
     Si el <xref:System.Windows.Media.Animation.KeyTime> del primer fotograma clave es <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> y esta animación con más de en fotogramas clave, resuelva su <xref:System.Windows.Media.Animation.KeyTime> valor en cero; si hay solo un fotograma clave y sus <xref:System.Windows.Media.Animation.KeyTime> valor es <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>, se resuelve como el total tiempo de interpolación, tal como se describe en el paso anterior.  
  
5.  Resolver restantes <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> <xref:System.Windows.Media.Animation.KeyTime> valores: cada una tiene una cuota similar del tiempo disponible.  Durante este proceso, sin resolver <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> <xref:System.Windows.Media.Animation.KeyTime> los valores se tratan temporalmente <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> <xref:System.Windows.Media.Animation.KeyTime> valores y get hora de resolución de un archivo temporal.  
  
6.  Resolver la <xref:System.Windows.Media.Animation.KeyTime> valores de fotogramas clave con tiempos clave no especificados mediante el uso de los fotogramas clave declarados más cercanos que se han resuelto <xref:System.Windows.Media.Animation.KeyTime> valores.  
  
7.  Resolver restantes <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> <xref:System.Windows.Media.Animation.KeyTime> valores. <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> <xref:System.Windows.Media.Animation.KeyTime> Utilice el <xref:System.Windows.Media.Animation.KeyTime> fotogramas para determinar el tiempo de resolución de clave de los valores de los vecinos.  El objetivo es garantizar que la velocidad de la animación sea constante alrededor del tiempo de resolución de este fotograma clave.  
  
8.  Ordene los fotogramas clave en tiempo de resolución (clave principal) y el orden de declaración (clave secundaria), es decir, utilice un orden estable basado en el fotograma clave resueltos <xref:System.Windows.Media.Animation.KeyTime> valores.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.Animation.KeyTime>  
 <xref:System.Windows.Media.Animation.KeySpline>  
 <xref:System.Windows.Media.Animation.Timeline>  
 [Ejemplo de animación de curva Spline clave](https://go.microsoft.com/fwlink/?LinkID=160011)  
 [Ejemplo de animación de fotogramas clave](https://go.microsoft.com/fwlink/?LinkID=160012)  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Información general sobre objetos Storyboard ](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [Temas de procedimientos de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)  
 [Información general sobre comportamientos de control de tiempo](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)
