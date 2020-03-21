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
ms.openlocfilehash: a25bde5098af853c3906a174a189fc35f33f0525
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186496"
---
# <a name="easing-functions"></a>Funciones de aceleración
Las funciones de aceleración le permiten aplicar fórmulas matemáticas personalizadas a las animaciones. Por ejemplo, puede que quiera que un objeto rebote de forma realista o se comporte como si estuviera sobre un muelle. Podría usar animaciones de fotogramas clave o incluso animaciones From/To/By para aproximarse a estos efectos pero supondría bastante trabajo y la animación sería menos precisa que si usa un fórmula matemática.  
  
 Además de crear su propia función <xref:System.Windows.Media.Animation.EasingFunctionBase>de facilitación personalizada heredando de , puede utilizar una de las varias funciones de facilitación proporcionadas por el tiempo de ejecución para crear efectos comunes.  
  
- <xref:System.Windows.Media.Animation.BackEase>: Retrae el movimiento de una animación ligeramente antes de que comience a animarse en el trazado indicado.  
  
- <xref:System.Windows.Media.Animation.BounceEase>: Crea un efecto de rebote.  
  
- <xref:System.Windows.Media.Animation.CircleEase>: crea una animación que acelera y/o desacelera mediante una función circular.  
  
- <xref:System.Windows.Media.Animation.CubicEase>: Crea una animación que acelera y/o desacelera utilizando la fórmula *f*(*t*) a *t*<sup>3</sup>.  
  
- <xref:System.Windows.Media.Animation.ElasticEase>: Crea una animación que se asemeja a un resorte que oscila de un lado a otro hasta que llega al descanso.  
  
- <xref:System.Windows.Media.Animation.ExponentialEase>: crea una animación que acelera y/o desacelera mediante una fórmula exponencial.  
  
- <xref:System.Windows.Media.Animation.PowerEase>: crea una animación que acelera o desacelera utilizando la fórmula *f*(*t*) á *t*<sup>p</sup> donde p es igual a la <xref:System.Windows.Media.Animation.PowerEase.Power%2A> propiedad.  
  
- <xref:System.Windows.Media.Animation.QuadraticEase>: Crea una animación que acelera y/o desacelera utilizando la fórmula *f*(*t*) á *t*<sup>2</sup>.  
  
- <xref:System.Windows.Media.Animation.QuarticEase>: Crea una animación que acelera y/o desacelera utilizando la fórmula *f*(*t*) á *t*<sup>4</sup>.  
  
- <xref:System.Windows.Media.Animation.QuinticEase>: Cree una animación que se acelere y/o desacelere utilizando la fórmula *f*(*t*) a *t*<sup>5</sup>.  
  
- <xref:System.Windows.Media.Animation.SineEase>: crea una animación que acelera y/o desacelera mediante una fórmula sinusoida.  
  
 Para aplicar una función de conexión `EasingFunction` a una animación, utilice la propiedad de la animación para especificar la función de asaparación que se aplicará a la animación. En el ejemplo <xref:System.Windows.Media.Animation.BounceEase> siguiente se aplica <xref:System.Windows.Media.Animation.DoubleAnimation> una función de asaing a a para crear un efecto de rebote.  
  
 [!code-xaml[BounceEase_snippet#BounceEase](~/samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 En el ejemplo anterior, la función de aceleración se aplicó a una animación From/To/By. También puede aplicar estas funciones de aceleración a animaciones de fotogramas clave. En el ejemplo siguiente se muestra cómo usar fotogramas clave con funciones de aceleración asociadas a ellos para crear una animación de un rectángulo que se contrae hacia arriba, se ralentiza, se expande hacia abajo (como si cayera) y luego rebota hasta detenerse.  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](~/samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 Puede utilizar <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> la propiedad para modificar el modo en que se comporta la función de atenuación, es decir, cambiar el modo en que se interpola la animación. Hay tres valores posibles que <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>puede dar para:  
  
- <xref:System.Windows.Media.Animation.EasingMode.EaseIn>: La interpolación sigue la fórmula matemática asociada con la función de easing.  
  
- <xref:System.Windows.Media.Animation.EasingMode.EaseOut>: La interpolación sigue la interpolación del 100% menos la salida de la fórmula asociada con la función de easing.  
  
- <xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: La <xref:System.Windows.Media.Animation.EasingMode.EaseIn> interpolación se utiliza para <xref:System.Windows.Media.Animation.EasingMode.EaseOut> la primera mitad de la animación y para la segunda mitad.  
  
 Los gráficos siguientes muestran <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> los diferentes valores de donde *f*(*x*) representa el progreso de la animación y *t* representa el tiempo.  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 ![Gráficos EasingMode para BackEase.](./media/backease-graph.png "BackEase_Graph")  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 ![Gráficos EasingMode para BounceEase.](./media/bounceease-graph.png "BounceEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 ![Gráficos EasingMode para CircleEase.](./media/circleease-graph.png "CircleEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 ![Gráficos EasingMode para CubicEase.](./media/cubicease-graph.png "CubicEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 ![ElasticEase con gráficos de diferentes EasingMode.](./media/elasticease-graph.png "ElasticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 ![Gráficos ExponentialEase de diferentes EasingMode.](./media/exponentialease-graph.png "ExponentialEase_Graph")  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 ![QuarticEase con gráficos de diferentes EasingMode.](./media/quarticease-graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 ![QuadraticEase con gráficos de la diferentes EasingMode](./media/quadraticease-graph.png "QuadraticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 ![QuarticEase con gráficos de diferentes EasingMode.](./media/quarticease-graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 ![QuinticEase con gráficos de diferentes EasingMode.](./media/quinticease-graph.png "QuinticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 ![SineEase para diferentes valores de EasingMode](./media/sineease-graph.png "SineEase_Graph")  
  
> [!NOTE]
> Puede usar <xref:System.Windows.Media.Animation.PowerEase> para crear el <xref:System.Windows.Media.Animation.CubicEase> <xref:System.Windows.Media.Animation.QuadraticEase>mismo <xref:System.Windows.Media.Animation.QuarticEase>comportamiento <xref:System.Windows.Media.Animation.QuinticEase> que <xref:System.Windows.Media.Animation.PowerEase.Power%2A> , , , y mediante la propiedad. Por ejemplo, si desea <xref:System.Windows.Media.Animation.PowerEase> utilizar <xref:System.Windows.Media.Animation.CubicEase>para sustituir <xref:System.Windows.Media.Animation.PowerEase.Power%2A> , especifique un valor de 3.  
  
 Además de utilizar las funciones de facilitación incluidas en el tiempo de ejecución, puede crear sus propias funciones de facilitación personalizadas heredando de <xref:System.Windows.Media.Animation.EasingFunctionBase>. En el ejemplo siguiente se muestra cómo crear una función de aceleración simple personalizada. Puede agregar su propia lógica matemática para cómo se comporta la <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> función de easing reemplazando el método.
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
