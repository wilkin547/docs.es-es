---
title: Funciones de aceleración
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applying mathematical formulas to animations [WPF]
- applying easing functions to animations [WPF]
- mathematical formulas [WPF], applying to animations
- animations [WPF], realistic movement
- easing functions [WPF]
- customizing easing functions [WPF]
- easing functions [WPF], definition
- easing functions [WPF], customizing
- animations [WPF], applying
ms.assetid: 075b9c2b-82c4-43fa-b3cd-de0b6236eb38
ms.openlocfilehash: 3ce7c1824dc53c154ba1091ea62c1b8950b757c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="easing-functions"></a>Funciones de aceleración
Las funciones de aceleración le permiten aplicar fórmulas matemáticas personalizadas a las animaciones. Por ejemplo, puede que quiera que un objeto rebote de forma realista o se comporte como si estuviera sobre un muelle. Podría usar animaciones de fotogramas clave o incluso animaciones From/To/By para aproximarse a estos efectos pero supondría bastante trabajo y la animación sería menos precisa que si usa un fórmula matemática.  
  
 Además de crear su propia función de aceleración personalizada mediante la adquisición de <xref:System.Windows.Media.Animation.EasingFunctionBase>, puede usar una de varias funciones de aceleración proporcionadas por el tiempo de ejecución para crear efectos comunes.  
  
-   <xref:System.Windows.Media.Animation.BackEase>: Retira el movimiento de una animación un poco antes de comenzar a animar en la ruta de acceso indicada.  
  
-   <xref:System.Windows.Media.Animation.BounceEase>: Crea un efecto de rebote.  
  
-   <xref:System.Windows.Media.Animation.CircleEase>: Crea una animación que aumenta y/o reduce la velocidad mediante una función circular.  
  
-   <xref:System.Windows.Media.Animation.CubicEase>: Crea una animación que aumenta y/o reduce la velocidad mediante la fórmula *f*(*t*) = *t*<sup>3</sup>.  
  
-   <xref:System.Windows.Media.Animation.ElasticEase>: Crea una animación que se parezca a un muelle que oscila atrás y adelante hasta que se trata de rest.  
  
-   <xref:System.Windows.Media.Animation.ExponentialEase>: Crea una animación que aumenta y/o reduce la velocidad mediante una fórmula exponencial.  
  
-   <xref:System.Windows.Media.Animation.PowerEase>: Crea una animación que aumenta y/o reduce la velocidad mediante la fórmula *f*(*t*) = *t*<sup>p</sup> donde p es igual a la <xref:System.Windows.Media.Animation.PowerEase.Power%2A>propiedad.  
  
-   <xref:System.Windows.Media.Animation.QuadraticEase>: Crea una animación que aumenta y/o reduce la velocidad mediante la fórmula *f*(*t*) = *t*<sup>2</sup>.  
  
-   <xref:System.Windows.Media.Animation.QuarticEase>: Crea una animación que aumenta y/o reduce la velocidad mediante la fórmula *f*(*t*) = *t*<sup>4</sup>.  
  
-   <xref:System.Windows.Media.Animation.QuinticEase>: Cree una animación que aumenta y/o reduce la velocidad mediante la fórmula *f*(*t*) = *t*<sup>5</sup>.  
  
-   <xref:System.Windows.Media.Animation.SineEase>: Crea una animación que aumenta y/o reduce la velocidad mediante una fórmula de seno.  
  
 Puede explorar el comportamiento de estas funciones de aceleración con el ejemplo siguiente.  
  
 [Ejecutar este ejemplo](http://go.microsoft.com/fwlink/?LinkId=139798&sref=easing_functions_gallery)  
  
 Para aplicar una función de aceleración a una animación, utilice el `EasingFunction` la propiedad de la animación especificar la función de aceleración para aplicar a la animación. El ejemplo siguiente aplica un <xref:System.Windows.Media.Animation.BounceEase> función de aceleración una <xref:System.Windows.Media.Animation.DoubleAnimation> para crear un efecto de rebote.  
  
 [Ejecutar este ejemplo](http://go.microsoft.com/fwlink/?LinkId=139798&sref=BounceEase)  
  
 [!code-xaml[BounceEase_snippet#BounceEase](../../../../samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 En el ejemplo anterior, la función de aceleración se aplicó a una animación From/To/By. También puede aplicar estas funciones de aceleración a animaciones de fotogramas clave. En el ejemplo siguiente se muestra cómo usar fotogramas clave con funciones de aceleración asociadas a ellos para crear una animación de un rectángulo que se contrae hacia arriba, se ralentiza, se expande hacia abajo (como si cayera) y luego rebota hasta detenerse.  
  
 [Ejecutar este ejemplo](http://go.microsoft.com/fwlink/?LinkId=139798&sref=EasingFunctionDoubleKeyFrame)  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](../../../../samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 Puede usar el <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> cambio de propiedad para modificar cómo se comporta la función de aceleración, es decir, cómo se interpola la animación. Hay tres valores posibles que puede proporcionar <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:  
  
-   <xref:System.Windows.Media.Animation.EasingMode.EaseIn>: La interpolación sigue la fórmula matemática asociada a la función de aceleración.  
  
-   <xref:System.Windows.Media.Animation.EasingMode.EaseOut>: La interpolación sigue la interpolación al 100% menos el resultado de la fórmula asociada con la función de aceleración.  
  
-   <xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Usa la interpolación <xref:System.Windows.Media.Animation.EasingMode.EaseIn> para la primera mitad de la animación y <xref:System.Windows.Media.Animation.EasingMode.EaseOut> para la segunda mitad.  
  
 En los gráficos siguientes muestran los distintos valores de <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> donde *f*(*x*) representa el progreso de la animación y *t* representa el tiempo.  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 ![Gráficos EasingMode para BackEase.](../../../../docs/framework/wpf/graphics-multimedia/media/backease-graph.png "BackEase_Graph")  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 ![Gráficos EasingMode para BounceEase.](../../../../docs/framework/wpf/graphics-multimedia/media/bounceease-graph.png "BounceEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 ![Gráficos EasingMode para CircleEase.](../../../../docs/framework/wpf/graphics-multimedia/media/circleease-graph.png "CircleEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 ![Gráficos EasingMode para CubicEase.](../../../../docs/framework/wpf/graphics-multimedia/media/cubicease-graph.png "CubicEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 ![ElasticEase con gráficos de diferentes EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/elasticease-graph.png "ElasticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 ![Gráficos ExponentialEase de diferentes EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/exponentialease-graph.png "ExponentialEase_Graph")  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 ![QuarticEase con gráficos de diferentes EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 ![QuadraticEase con gráficos de la diferentes EasingMode](../../../../docs/framework/wpf/graphics-multimedia/media/quadraticease-graph.png "QuadraticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 ![QuarticEase con gráficos de diferentes EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 ![QuinticEase con gráficos de diferentes EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/quinticease-graph.png "QuinticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 ![SineEase para diferentes valores de EasingMode](../../../../docs/framework/wpf/graphics-multimedia/media/sineease-graph.png "SineEase_Graph")  
  
> [!NOTE]
>  Puede usar <xref:System.Windows.Media.Animation.PowerEase> para crear el mismo comportamiento que <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, y <xref:System.Windows.Media.Animation.QuinticEase> utilizando el <xref:System.Windows.Media.Animation.PowerEase.Power%2A> propiedad. Por ejemplo, si desea usar <xref:System.Windows.Media.Animation.PowerEase> para sustituir <xref:System.Windows.Media.Animation.CubicEase>, especifique un <xref:System.Windows.Media.Animation.PowerEase.Power%2A> valor 3.  
  
 Además de utilizar las funciones de aceleración incluidas en el tiempo de ejecución, puede crear sus propias funciones de aceleración personalizadas mediante la adquisición de <xref:System.Windows.Media.Animation.EasingFunctionBase>. En el ejemplo siguiente se muestra cómo crear una función de aceleración simple personalizada. Puede agregar su propia lógica matemática para el funcionamiento de la función de aceleración invalidando el <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> método.  
  
 [Ejecutar este ejemplo](http://go.microsoft.com/fwlink/?LinkId=139798&sref=CustomEasingFunction)  
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
