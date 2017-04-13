---
title: "Informaci&#243;n general sobre animaciones de fotogramas clave | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "animación, fotogramas clave"
  - "fotogramas clave [WPF], acerca de animaciones de fotogramas clave"
  - "valores de destino de animación múltiples"
ms.assetid: 10028f97-bb63-41fc-b8ad-663dac7ea203
caps.latest.revision: 29
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# Informaci&#243;n general sobre animaciones de fotogramas clave
En este tema se presenta la animación de fotogramas clave.  La animación de fotogramas clave permite animar utilizando más de dos valores objetivo y controlar el método de interpolación de una animación.  
  
 Este tema contiene las secciones siguientes.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
-   [Requisitos previos](#prerequisites)  
  
-   [Utilizar animaciones de fotogramas clave](#keyframeanimations)  
  
-   [Temas relacionados](#seeAlsoToggle)  
  
<a name="prerequisites"></a>   
## Requisitos previos  
 Para comprender esta información general, debe conocer las animaciones y las escalas de tiempo de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  Para obtener una introducción a las animaciones, vea [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md). También ayuda a conocer las animaciones From\/To\/By.  Para obtener más información, vea [Información general sobre animaciones From\/To\/By](../../../../docs/framework/wpf/graphics-multimedia/from-to-by-animations-overview.md).  
  
<a name="whatisakeyframeanimation"></a>   
## ¿Qué es una animación de fotograma clave?  
 Igual que una animación From\/To\/By, una animación de fotograma clave anima el valor de una propiedad de destino.  Crea una transición entre sus valores de destino a lo largo de su valor de <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.  Sin embargo, mientras una animación From\/To\/By crea una transición entre dos valores, una animación de fotograma clave única puede crear transiciones entre cualquier número de valores de destino.  A diferencia de una animación From\/To\/By, una animación de fotograma clave no tiene propiedades From, To o By que permitan establecer sus valores de destino.  Los valores de destino de una animación de fotograma clave se describen utilizando objetos de fotograma \(de ahí el término "animación de fotograma clave"\).  Para especificar los valores de destino de la animación, cree objetos de fotograma clave y agréguelos a la colección <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.KeyFrames%2A> de la animación.  Cuando se ejecute la animación, realizará transiciones entre los fotogramas especificados.  
  
 Además de admitir varios valores de destino, algunos métodos de fotograma clave admiten incluso varios métodos de interpolación.  Un método de interpolación de animación define cómo se realizan las transiciones de un valor al siguiente.  Hay tres tipos de interpolaciones: [discretas](GTMT), [lineales](GTMT) y [spline](GTMT).  
  
 Para animar con una animación de fotograma clave, complete los pasos siguientes.  
  
-   Declare la animación y especifique su propiedad <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, igual que haría para una animación From\/To\/By.  
  
-   Para cada valor de destino, cree un fotograma clave del tipo adecuado, establezca su valor y su propiedad <xref:System.Windows.Media.Animation.KeyTime>y agréguelo a la colección <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.KeyFrames%2A> de la animación.  
  
-   Asocie la animación a una propiedad, igual que haría con una animación From\/To\/By.  Para obtener más información sobre cómo aplicar una animación a una propiedad utilizando un guión gráfico, vea [Información general sobre objetos Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
 El ejemplo siguiente utiliza <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> para animar un elemento <xref:System.Windows.Shapes.Rectangle> en cuatro ubicaciones diferentes.  
  
 [!code-xml[keyframes_ovw_snip#BasicKeyFrameExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/KeyFramesIntroduction.xaml#basickeyframeexamplewholepage)]
 [!code-xml[keyframes_ovw_snip#BasicKeyFrameExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/KeyFramesIntroduction.xaml#basickeyframeexamplewholepage)]  
  
 Como una animación From\/To\/By, una animación de fotograma clave puede aplicarse a una propiedad usando un objeto <xref:System.Windows.Media.Animation.Storyboard> en el marcado y en el código o utilizando el método <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> en el código.  También puede usar una animación de fotograma clave para crear una clase <xref:System.Windows.Media.Animation.AnimationClock> y aplicarla a una o más propiedades.  Para obtener más información sobre los distintos métodos para aplicar animaciones, vea [Información general sobre técnicas de animación de propiedades](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
<a name="animation_types"></a>   
## Tipos de animación de fotograma clave  
 Dado que las animaciones generan valores de propiedades, hay distintos tipos de animaciones para los diversos tipos de propiedades.  Para animar una propiedad que acepta una estructura <xref:System.Double> \(tal como la propiedad <xref:System.Windows.FrameworkElement.Width%2A> de un elemento\), se usa una animación que genera valores <xref:System.Double>.  Para animar una propiedad que acepta una estructura <xref:System.Windows.Point>, se usa una animación que genera valores <xref:System.Windows.Point>, y así sucesivamente.  
  
 Las clases de animaciones de fotograma clave pertenecen al espacio de nombres <xref:System.Windows.Media.Animation> y se adhieren a la convención de nomenclatura siguiente:  
  
 *\<Tipo\>* `AnimationUsingKeyFrames`  
  
 Donde *\<Tipo\>* es el tipo de valor que la clase anima.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona las clases de animación de fotograma clave siguientes.  
  
|Tipo de propiedad|Clase de animaciones From\/To\/By correspondiente|Los métodos de interpolación admitidos|  
|-----------------------|-------------------------------------------------------|--------------------------------------------|  
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
## Valores de destino \(fotogramas clave\) y tiempos clave  
 Así como hay diferentes tipos de animaciones de fotograma clave para animar diferentes tipos de propiedad, hay también diferentes tipos de objetos de fotograma clave: uno para cada tipo de valor animado y de método de interpolación admitido.  Los tipos de fotograma clave se adhieren a la convención de nomenclatura siguiente:  
  
 *\<MétodoDeInterpolación\>\<Tipo\>* `KeyFrame`  
  
 Donde *\<MétodoDeInterpolación\>* es el método de interpolación que utiliza el fotograma clave y *\<Tipo\>* es el tipo de valor que anima la clase.  Una animación de fotograma clave que admita los tres métodos de interpolación tendrá tres tipos de fotograma clave que puede utilizar.  Por ejemplo, puede utilizar tres tipos de fotograma clave con un objeto <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>: <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>, <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> y <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>.  \(Los métodos de interpolación se describen con detalle en una sección posterior.\)  
  
 El propósito principal de un fotograma clave es especificar un valor de <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> y <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A>.  Cada tipo de fotograma clave proporciona estas dos propiedades.  
  
-   La propiedad <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> especifica el valor de destino para ese fotograma clave.  
  
-   La propiedad <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> especifica cuándo se alcanza \(dentro del valor de <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de la animación\) el valor de <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> de un fotograma clave.  
  
 Cuando se inicia la animación de un fotograma clave, recorre en iteración sus fotogramas clave en el orden definido por sus propiedades <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A>.  
  
-   Si no hay ningún fotograma clave en el tiempo 0, la animación crea una transición entre el valor actual de la propiedad de destino y el valor <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> del primer fotograma clave; de lo contrario, el valor de salida de animación es el valor del primer fotograma clave.  
  
-   La animación crea una transición entre el valor <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> del primer y el segundo fotograma clave utilizando el método de interpolación especificado por el segundo fotograma clave.  La transición se inicia en el valor  <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> del primer fotograma clave y termina cuando se alcanza el valor <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> del segundo fotograma clave.  
  
-   La animación continúa, creando transiciones entre cada fotograma clave subsiguiente y su fotograma clave anterior.  
  
-   Finalmente, a animación realiza una transición al valor del fotograma clave con el mayor tiempo clave igual o menor que el valor de <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de la animación.  
  
 Si el valor de <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de la animación es <xref:System.Windows.Duration.Automatic%2A> o su valor de <xref:System.Windows.Media.Animation.Timeline.Duration%2A> es igual al tiempo del último fotograma clave, la animación finaliza.  De lo contrario, si el valor <xref:System.Windows.Duration> de la animación es mayor que el tiempo clave del último fotograma clave, la animación retiene el valor del fotograma clave hasta que alcanza el final de su valor de <xref:System.Windows.Duration>.  Como todas las animaciones, una animación de fotograma clave utiliza su propiedad <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> para determinar si retiene el valor final cuando llega al fin de su período activo.  Para obtener más información, vea [Información general sobre comportamientos de control de tiempo](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md).  
  
 El ejemplo siguiente utiliza el objeto <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> definido en el ejemplo anterior para mostrar cómo funcionan las propiedades <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> y <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A>.  
  
-   El primer fotograma clave establece inmediatamente el valor de salida de la animación en 0.  
  
-   El segundo fotograma clave se anima desde 0 a 350.  Se inicia una vez que termina el primer fotograma clave \(en el tiempo \= 0 segundos\), se reproduce durante 2 segundos y finaliza en el tiempo \= 0:0:2.  
  
-   El tercer fotograma clave se anima desde 350 a 50.  Se inicia cuando finaliza el segundo fotograma clave \(en el tiempo \= 2 segundos\), se reproduce durante 5 segundos y finaliza en el tiempo \= 0:0:7.  
  
-   El cuarto fotograma clave se anima desde 50 a 200.  Se inicia cuando finaliza el tercer fotograma clave \(en el tiempo \= 7 segundos\), se reproduce durante 1 segundo y finaliza en el tiempo \= 0:0:8.  
  
-   Dado que la propiedad <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de la animación se estableció en 10 segundos, la animación retiene su valor final durante dos segundos antes de finalizar en el tiempo \= 0:0:10.  
  
 [!code-xml[keyframes_ovw_snip#BasicKeyFrameExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/KeyFramesIntroduction.xaml#basickeyframeexamplewholepage)]
 [!code-xml[keyframes_ovw_snip#BasicKeyFrameExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/KeyFramesIntroduction.xaml#basickeyframeexamplewholepage)]  
  
<a name="interpolationmethods"></a>   
## Métodos de interpolación  
 Las secciones anteriores mencionaban que algunas animaciones de fotograma clave admiten varios métodos de interpolación.  La interpolación de una animación describe cómo una animación realiza transiciones entre valores a lo largo de su duración.  Seleccionando qué tipo de fotograma clave se utiliza con la animación, puede definir el método de interpolación para ese segmento del fotograma clave.  Hay tres tipos diferentes de métodos de interpolación: lineal, discreto y spline.  
  
### Interpolación lineal  
 Con la [interpolación lineal](GTMT), la animación progresa en una velocidad constante en la duración del segmento.  Por ejemplo, si un segmento de fotograma clave pasa de 0 a 10 en una duración de 5 segundos, la animación generará los valores siguientes en los tiempos especificados:  
  
|Hora|Valor de salida.|  
|----------|----------------------|  
|0|0|  
|1|2|  
|2|4|  
|3|6|  
|4|8|  
|4.25|8.5|  
|4.5|9|  
|5|10|  
  
### Interpolación discreta  
 Con la [interpolación discreta](GTMT), la función de animación salta de un valor al siguiente sin interpolación.  Si un segmento de fotograma clave pasa de 0 a 10 en una duración de 5 segundos, la animación generará los valores siguientes en los tiempos especificados:  
  
|Hora|Valor de salida.|  
|----------|----------------------|  
|0|0|  
|1|0|  
|2|0|  
|3|0|  
|4|0|  
|4.25|0|  
|4.5|0|  
|5|10|  
  
 Observe cómo la animación no cambia su valor de salida hasta el mismo fin de la duración del segmento.  
  
 [La interpolación spline](GTMT) es más compleja.  Se describe en la siguiente sección.  
  
<a name="anim_spline"></a>   
### Interpolación spline  
 La interpolación spline se puede utilizar para lograr efectos del control de tiempo más realistas.  Dado que las animaciones se utilizan muy frecuentemente para imitar efectos que se producen en el mundo real, los programadores pueden necesitar un control preciso de la aceleración y la desaceleración de los objetos, así como una manipulación estrecha de los segmentos de tiempo.  Los fotogramas clave de spline permiten animar con interpolación spline.  Con otros fotogramas clave, se debe especificar valores <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> y <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A>.  Con un fotograma clave de spline, también se especifica un valor <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A>.  En el ejemplo siguiente se muestra un fotograma clave de spline único para un objeto <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.  Observe la propiedad <xref:System.Windows.Media.Animation.KeySpline>; es lo que hace que un fotograma clave de spline sea diferente de los demás tipos de fotograma clave.  
  
 [!code-xml[keyframes_ovw_snip#SingleSplineKeyFrameExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/InterpolationMethodsExample.xaml#singlesplinekeyframeexample)]
 [!code-xml[keyframes_ovw_snip#SingleSplineKeyFrameExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/InterpolationMethodsExample.xaml#singlesplinekeyframeexample)]  
  
 Una [curva de Bézier cúbica](GTMT) se define mediante un punto inicial, un punto final y dos puntos de control.  La propiedad <xref:System.Windows.Media.Animation.KeySpline> de un fotograma clave de spline define los dos puntos de control de una curva de Bézier que se extiende de \(0,0\) a \(1,1\).  El primer punto de control controla el factor de curvatura de la primera mitad de la curva de Bézier, y el segundo punto de control controla el factor de curvatura de la segunda mitad del segmento de Bézier.  La curva resultante describe la tasa de cambio para ese fotograma clave de spline.  Cuanto más inclinada sea la curva, más rápidamente cambia de valor el fotograma clave.  Cuando la curva se hace más plana, el fotograma clave cambia de valor más lentamente.  
  
 Podría utilizar <xref:System.Windows.Media.Animation.KeySpline> para simular trayectorias físicas como las del agua al caer o de bolas que rebotan, o aplicar otros efectos de amortiguación de entrada y salida a animaciones de movimiento.  Para efectos de interacción con el usuario tales como fundidos de fondo o rebote de botones de control, quizá deba aplicar la interpolación spline para acelerar o ralentizar la velocidad de cambio de la animación de una manera concreta.  
  
 El ejemplo siguiente especifica un valor <xref:System.Windows.Media.Animation.KeySpline> de 0,1 1,0, que crea la curva Bézier siguiente.  
  
 ![Curva Bézier](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyspline-0-1-1-0.png "graphicsmm\_keyspline\_0\_1\_1\_0")  
Un spline clave con puntos de control \(0,0; 1,0\) y \(1,0; 0,0\)  
  
 [!code-xml[keyframes_ovw_snip#SingleSplineKeyFrameExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/InterpolationMethodsExample.xaml#singlesplinekeyframeexample)]
 [!code-xml[keyframes_ovw_snip#SingleSplineKeyFrameExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/InterpolationMethodsExample.xaml#singlesplinekeyframeexample)]  
  
 Este fotograma clave se anima rápidamente al principio, reduce la velocidad y, a continuación, se acelera de nuevo antes de finalizar.  
  
 El ejemplo siguiente especifica un valor <xref:System.Windows.Media.Animation.KeySpline> de 0.5,0.25 0.75,1.0, que crea la curva Bézier siguiente.  
  
 ![Curva Bézier](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyspline-025-050-075-10.png "graphicsmm\_keyspline\_025\_050\_075\_10")  
Un spline clave con puntos de control \(0,25; 0,5\) y \(0,75; 1,0\)  
  
 [!code-xml[keyframes_ovw_snip#SingleSplineKeyFrameExampleInline3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/InterpolationMethodsExample.xaml#singlesplinekeyframeexampleinline3)]
 [!code-xml[keyframes_ovw_snip#SingleSplineKeyFrameExampleInline3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/InterpolationMethodsExample.xaml#singlesplinekeyframeexampleinline3)]  
  
 Dado que la curvatura de la curva Bézier cambia muy poco, este fotograma clave se anima a una velocidad casi constante; reduce la velocidad un poco hacia su fin.  
  
 En el ejemplo siguiente se usa un objeto <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> para animar la posición de un rectángulo.  Dado que <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> utiliza objetos <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>, la transición entre los valores del fotograma clave utiliza la interpolación spline.  
  
 [!code-xml[keyframes_ovw_snip#SplinedInterpolationExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/InterpolationMethodsExample.xaml#splinedinterpolationexample)]
 [!code-xml[keyframes_ovw_snip#SplinedInterpolationExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/InterpolationMethodsExample.xaml#splinedinterpolationexample)]  
  
 La interpolación spline puede ser difícil entender; puede ser útil experimentar con diferentes valores.  [Key Spline Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160011) permite cambiar valores de spline clave y ver el resultado que tienen sobre una animación.  
  
<a name="combininginterpolationmethods"></a>   
### Combinar métodos de interpolación  
 Puede utilizar fotogramas clave con diferentes tipos de interpolación en una única animación de fotograma de clave.  Cuando dos animaciones de fotograma clave con diferentes interpolaciones se siguen entre sí, el método de interpolación del segundo fotograma clave se utiliza para crear la transición desde el primer valor al segundo.  
  
 En el ejemplo siguiente, se crea un objeto <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> que utiliza interpolación lineal, spline y discreta.  
  
 [!code-xml[keyframes_ovw_snip#ComboInterpolationExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/InterpolationMethodsExample.xaml#combointerpolationexample)]
 [!code-xml[keyframes_ovw_snip#ComboInterpolationExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/InterpolationMethodsExample.xaml#combointerpolationexample)]  
  
<a name="keytimes"></a>   
## Más sobre la duración y los tiempos clave  
 Como sucede con las demás animaciones, las animaciones de fotogramas clave tienen una propiedad <xref:System.Windows.Duration>.  Además de especificar el valor de <xref:System.Windows.Duration> de la animación, debe especificar qué parte de esa duración se asigna a cada fotograma clave.  Para hacerlo, describa un valor <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> para cada uno de los fotogramas clave de la animación.  El valor de <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> de cada fotograma clave especifica cuándo finaliza ese fotograma.  
  
 La propiedad <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> no especifica cuánto tiempo se reproduce el tiempo clave.  La duración de la reproducción del fotograma clave la determinan el momento de finalización del fotograma, el momento de finalización del fotograma anterior y la duración de la animación.  Es posible especificar tiempos clave en forma de un valor de tiempo, un porcentaje o como los valores especiales <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> o <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>.  
  
 La lista siguiente describe las diferentes maneras de especificar tiempos clave.  
  
### Valores TimeSpan  
 Puede utilizar valores <xref:System.TimeSpan> para especificar un valor de <xref:System.Windows.Media.Animation.KeyTime>.  El valor debe ser mayor o igual a 0, y menor o igual a la duración de la animación.  El ejemplo siguiente muestra una animación con una duración de 10 segundos y cuatro fotogramas clave cuyos tiempos clave se especifican como valores de tiempo.  
  
-   El primer fotograma clave se anima desde el valor base hasta 100 durante los primeros 3 segundos, finalizando en el tiempo \= 0:0:03.  
  
-   El segundo fotograma clave se anima desde 100 a 200.  Se inicia una vez que termina el primer fotograma clave \(en el tiempo \= 3 segundos\), se reproduce durante 5 segundos y finaliza en el tiempo \= 0:0:8.  
  
-   El tercer fotograma clave se anima desde 200 a 500.  Se inicia cuando finaliza el segundo fotograma clave \(en el tiempo \= 8 segundos\), se reproduce durante 1 segundo y finaliza en el tiempo \= 0:0:9.  
  
-   El cuarto fotograma clave se anima desde 500 a 600.  Se inicia cuando finaliza el tercer fotograma clave \(en el tiempo \= 9 segundos\), se reproduce durante 1 segundo y finaliza en el tiempo \= 0:0:10.  
  
 [!code-xml[keyframes_ovw_snip#TimeSpanKeyTimeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/KeyTimesExample.xaml#timespankeytimeexample)]
 [!code-xml[keyframes_ovw_snip#TimeSpanKeyTimeExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/KeyTimesExample.xaml#timespankeytimeexample)]  
  
### Valores de porcentaje  
 Un valor de porcentaje especifica que el fotograma clave finaliza en algún porcentaje del valor de <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de la animación.  En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], debe especificar el porcentaje como un número seguido por el símbolo `%`.  En código, utilice el método <xref:System.Windows.Media.Animation.KeyTime.FromPercent%2A> y pásele un valor <xref:System.Double> que indique el porcentaje.  El valor debe ser igual o mayor que 0 e igual o menor que el 100 por ciento.  El ejemplo siguiente muestra una animación con una duración de 10 segundos y cuatro fotogramas clave cuyos tiempos clave se especifican como porcentajes.  
  
-   El primer fotograma clave se anima desde el valor base hasta 100 durante los primeros 3 segundos, finalizando en el tiempo \= 0:0:3.  
  
-   El segundo fotograma clave se anima desde 100 a 200.  Se inicia una vez que termina el primer fotograma clave \(en el tiempo \= 3 segundos\), se reproduce durante 5 segundos y finaliza en el tiempo \= 0:0:8 \(0,8 \* 10 \= 8\).  
  
-   El tercer fotograma clave se anima desde 200 a 500.  Se inicia cuando finaliza el segundo fotograma clave \(en el tiempo \= 8 segundos\), se reproduce durante 1 segundo y finaliza en el tiempo \= 0:0:9 \(0,9 \* 10 \= 9\).  
  
-   El cuarto fotograma clave se anima desde 500 a 600.  Se inicia cuando finaliza el tercer fotograma clave \(en el tiempo \= 9 segundos\), se reproduce durante 1 segundo y finaliza en el tiempo \= 0:0:10 \(1 \* 10 \= 10\).  
  
 [!code-xml[keyframes_ovw_snip#PercentageKeyTimeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/KeyTimesExample.xaml#percentagekeytimeexample)]
 [!code-xml[keyframes_ovw_snip#PercentageKeyTimeExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/KeyTimesExample.xaml#percentagekeytimeexample)]  
  
### Valor especial, Uniform  
 Utilice el control de tiempo <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> cuando desee que cada fotograma clave tome la misma cantidad de tiempo.  
  
 Un tiempo clave <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> divide el tiempo disponible por igual entre el número de fotogramas clave para determinar la hora de finalización de cada fotograma clave.  El ejemplo siguiente muestra una animación con una duración de 10 segundos y cuatro fotogramas clave cuyos tiempos clave se especifican como <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A>.  
  
-   El primer fotograma clave se anima desde el valor base hasta 100 durante los primeros 2,5 segundos, finalizando en el tiempo \= 0:0:2,5.  
  
-   El segundo fotograma clave se anima desde 100 a 200.  Se inicia una vez que termina el primer fotograma clave \(en el tiempo \= 2.5 segundos\), se reproduce durante aproximadamente 2,5 segundos y finaliza en el tiempo \= 0:0:5.  
  
-   El tercer fotograma clave se anima desde 200 a 500.  Se inicia cuando finaliza el segundo fotograma clave \(en el tiempo \= 5 segundos\), se reproduce durante 2,5 segundos y finaliza en el tiempo \= 0:0:7,5.  
  
-   El cuarto fotograma clave se anima desde 500 a 600.  Se inicia cuando finaliza el segundo fotograma clave \(en el tiempo \= 7,5 segundos\), se reproduce durante 2,5 segundos y finaliza en el tiempo \= 0:0:1.  
  
 [!code-xml[keyframes_ovw_snip#UniformKeyTimeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/KeyTimesExample.xaml#uniformkeytimeexample)]
 [!code-xml[keyframes_ovw_snip#UniformKeyTimeExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/KeyTimesExample.xaml#uniformkeytimeexample)]  
  
### Valor especial, Paced  
 Utilice el control de tiempo <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> cuando desee animar a una velocidad constante.  
  
 Un tiempo clave <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> asigna el tiempo disponible en función de la longitud de los fotogramas clave para determinar la duración de cada fotograma.  De esta forma, se proporciona el comportamiento para que la "velocidad" o la reproducción de la animación se mantengan constantes.  El ejemplo siguiente muestra una animación con una duración de 10 segundos y tres fotogramas clave cuyos tiempos clave se especifican como <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>.  
  
 [!code-xml[keyframes_ovw_snip#PacedKeyTimeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/KeyTimesExample.xaml#pacedkeytimeexample)]
 [!code-xml[keyframes_ovw_snip#PacedKeyTimeExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/KeyTimesExample.xaml#pacedkeytimeexample)]  
  
 Tenga en cuenta que, si el tiempo clave del último fotograma clave es <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> o <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A>, su tiempo de clave resuelto se establecerá en el 100 por cien.  Si el primer fotograma clave de una animación de varios fotogramas es paced, su tiempo clave resuelto se establecerá en 0.  \(Si la colección de fotogramas clave contiene solamente un fotograma de clave única y es un fotograma de clave paced, su tiempo clave resuelto se establecerá en el 100 por ciento.\)  
  
 Diferentes fotogramas dentro de una única animación de fotograma clave pueden utilizar diferentes tipos de tiempo clave.  
  
<a name="combiningkeytimes"></a>   
## Combinar tiempos clave y fotogramas clave fuera de secuencia  
 Puede utilizar fotogramas clave con diferentes tipos de valor <xref:System.Windows.Media.Animation.KeyTime> en la misma animación.  Y, aunque se recomienda agregar los fotogramas clave en el orden en el que se deben reproducir, no es necesario.  El sistema de animación y control de tiempo es capaz de resolver fotogramas clave fuera de secuencia.  Los fotogramas clave con tiempos clave no válidos se omiten.  
  
 La lista siguiente describe el procedimiento por el que se resuelven los tiempos clave para los fotogramas clave de una animación de fotogramas clave.  
  
1.  Resuelva los valores <xref:System.TimeSpan><xref:System.Windows.Media.Animation.KeyTime>.  
  
2.  Determine el *tiempo de interpolación total* de la animación, el tiempo total que tarda la animación de fotogramas clave en completar una iteración hacia adelante.  
  
    1.  Si el valor de <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de la animación no es <xref:System.Windows.Duration.Automatic%2A> o <xref:System.Windows.Duration.Forever%2A>, el tiempo de interpolación total es el valor de la propiedad <xref:System.Windows.Media.Animation.Timeline.Duration%2A> de la animación.  
  
    2.  De lo contrario, el tiempo de interpolación total es el valor <xref:System.TimeSpan><xref:System.Windows.Media.Animation.KeyTime> mayor especificado entre sus fotogramas clave, si existe alguno.  
  
    3.  De lo contrario, el tiempo de interpolación total es 1 segundo.  
  
3.  Utilice el valor de tiempo de interpolación total para resolver valores <xref:System.Windows.Media.Animation.KeyTimeType><xref:System.Windows.Media.Animation.KeyTime>.  
  
4.  Resuelva el último fotograma clave, si no se resolvió ya en los pasos anteriores.  Si el valor <xref:System.Windows.Media.Animation.KeyTime> del último fotograma clave es <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> o <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>, su tiempo resuelto será igual al tiempo de interpolación total.  
  
     Si el valor <xref:System.Windows.Media.Animation.KeyTime> del primer fotograma clave es <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> y esta animación tiene más de un fotograma clave, resuelva su valor <xref:System.Windows.Media.Animation.KeyTime> en cero; si solamente hay un fotograma clave y su valor <xref:System.Windows.Media.Animation.KeyTime> es <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>, se resuelve en el tiempo de interpolación total, como se describe en el paso anterior.  
  
5.  Resuelva los restantes valores <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A><xref:System.Windows.Media.Animation.KeyTime>: cada uno recibe una cuota igual del tiempo disponible.  Durante este proceso, los valores <xref:System.Windows.Media.Animation.KeyTime.Paced%2A><xref:System.Windows.Media.Animation.KeyTime> no resueltos se tratan temporalmente como valores <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A><xref:System.Windows.Media.Animation.KeyTime>y obtienen un tiempo resuelto temporal.  
  
6.  Resuelva los valores <xref:System.Windows.Media.Animation.KeyTime> de los fotogramas clave con tiempo clave no especificados utilizando los fotogramas clave declarados más cercanos que tengan valores <xref:System.Windows.Media.Animation.KeyTime> resueltos.  
  
7.  Resuelva los restantes valores <xref:System.Windows.Media.Animation.KeyTime.Paced%2A><xref:System.Windows.Media.Animation.KeyTime>.  <xref:System.Windows.Media.Animation.KeyTime.Paced%2A><xref:System.Windows.Media.Animation.KeyTime> utilizan los valores <xref:System.Windows.Media.Animation.KeyTime> de los fotogramas clave vecinos para determinar su tiempo resuelto.  El objetivo es asegurarse de que la velocidad de la animación sea constante alrededor del tiempo resuelto de este fotograma clave.  
  
8.  Ordene los fotogramas clave por tiempo resuelto \(clave principal\) y orden de declaración \(clave secundaria\), es decir, utilice un orden estable basado en los valores <xref:System.Windows.Media.Animation.KeyTime> resueltos de los fotogramas clave.  
  
## Vea también  
 <xref:System.Windows.Media.Animation.KeyTime>   
 <xref:System.Windows.Media.Animation.KeySpline>   
 <xref:System.Windows.Media.Animation.Timeline>   
 [Ejemplo Key Spline Animation](http://go.microsoft.com/fwlink/?LinkID=160011)   
 [Ejemplo KeyFrame Animation](http://go.microsoft.com/fwlink/?LinkID=160012)   
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Información general sobre objetos Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)   
 [Temas "Cómo..." de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)   
 [Información general sobre comportamientos de control de tiempo](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)