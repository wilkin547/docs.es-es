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
ms.openlocfilehash: 038d9423ddae6f16165ed0618beab8391c462ac9
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2018
ms.locfileid: "43253216"
---
# <a name="easing-functions"></a>Funciones de aceleración
Las funciones de aceleración le permiten aplicar fórmulas matemáticas personalizadas a las animaciones. Por ejemplo, puede que quiera que un objeto rebote de forma realista o se comporte como si estuviera sobre un muelle. Podría usar animaciones de fotogramas clave o incluso animaciones From/To/By para aproximarse a estos efectos pero supondría bastante trabajo y la animación sería menos precisa que si usa un fórmula matemática.  
  
 Además de crear su propia función de aceleración personalizada heredando de <xref:System.Windows.Media.Animation.EasingFunctionBase>, puede usar una de las funciones de aceleración proporcionadas por el tiempo de ejecución para crear efectos comunes.  
  
-   <xref:System.Windows.Media.Animation.BackEase>: Retira el movimiento de una animación un poco antes de que comience a animarse en la ruta de acceso indicada.  
  
-   <xref:System.Windows.Media.Animation.BounceEase>: Crea un efecto de rebote.  
  
-   <xref:System.Windows.Media.Animation.CircleEase>: Crea una animación que acelera y/o desacelera mediante una función circular.  
  
-   <xref:System.Windows.Media.Animation.CubicEase>: Crea una animación que acelera y/o desacelera mediante la fórmula *f*(*t*) = *t*<sup>3</sup>.  
  
-   <xref:System.Windows.Media.Animation.ElasticEase>: Crea una animación que simula un muelle y hacia atrás hasta llegar a detenerse.  
  
-   <xref:System.Windows.Media.Animation.ExponentialEase>: Crea una animación que acelera y/o desacelera mediante una fórmula exponencial.  
  
-   <xref:System.Windows.Media.Animation.PowerEase>: Crea una animación que acelera y/o desacelera mediante la fórmula *f*(*t*) = *t*<sup>p</sup> donde p es igual a la <xref:System.Windows.Media.Animation.PowerEase.Power%2A>propiedad.  
  
-   <xref:System.Windows.Media.Animation.QuadraticEase>: Crea una animación que acelera y/o desacelera mediante la fórmula *f*(*t*) = *t*<sup>2</sup>.  
  
-   <xref:System.Windows.Media.Animation.QuarticEase>: Crea una animación que acelera y/o desacelera mediante la fórmula *f*(*t*) = *t*<sup>4</sup>.  
  
-   <xref:System.Windows.Media.Animation.QuinticEase>: Crear una animación que acelera y/o desacelera mediante la fórmula *f*(*t*) = *t*<sup>5</sup>.  
  
-   <xref:System.Windows.Media.Animation.SineEase>: Crea una animación que acelera y/o desacelera mediante una fórmula de seno.  
  
 Para aplicar una función de aceleración a una animación, use la `EasingFunction` propiedad de la animación para especificar la función que se aplicará a la animación. El ejemplo siguiente aplica un <xref:System.Windows.Media.Animation.BounceEase> función de aceleración un <xref:System.Windows.Media.Animation.DoubleAnimation> para crear un efecto de rebote.  
  
 [!code-xaml[BounceEase_snippet#BounceEase](../../../../samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 En el ejemplo anterior, la función de aceleración se aplicó a una animación From/To/By. También puede aplicar estas funciones de aceleración a animaciones de fotogramas clave. En el ejemplo siguiente se muestra cómo usar fotogramas clave con funciones de aceleración asociadas a ellos para crear una animación de un rectángulo que se contrae hacia arriba, se ralentiza, se expande hacia abajo (como si cayera) y luego rebota hasta detenerse.  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](../../../../samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 Puede usar el <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> cambio de propiedad para modificar cómo se comporta la función de aceleración, es decir, cómo se interpola la animación. Hay tres valores posibles que puede dar para <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:  
  
-   <xref:System.Windows.Media.Animation.EasingMode.EaseIn>: La interpolación sigue la fórmula matemática asociada con la función de aceleración.  
  
-   <xref:System.Windows.Media.Animation.EasingMode.EaseOut>: La interpolación sigue la interpolación al 100% menos el resultado de la fórmula asociada con la función de aceleración.  
  
-   <xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: La interpolación usa <xref:System.Windows.Media.Animation.EasingMode.EaseIn> durante la primera mitad de la animación y <xref:System.Windows.Media.Animation.EasingMode.EaseOut> para la segunda mitad.  
  
 Los gráficos siguientes muestran los distintos valores de <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> donde *f*(*x*) representa el progreso de la animación y *t* representa el tiempo.  
  
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
  
 Además de utilizar las funciones de aceleración incluidas en el tiempo de ejecución, puede crear sus propias funciones de aceleración personalizadas heredando de <xref:System.Windows.Media.Animation.EasingFunctionBase>. En el ejemplo siguiente se muestra cómo crear una función de aceleración simple personalizada. Puede agregar su propia lógica matemática para cómo se comporta la función de aceleración invalidando el <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> método.   
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
