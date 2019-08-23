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
ms.openlocfilehash: 72118711dfd40ad8c665157e09f01c60085db903
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965731"
---
# <a name="easing-functions"></a>Funciones de aceleración
Las funciones de aceleración le permiten aplicar fórmulas matemáticas personalizadas a las animaciones. Por ejemplo, puede que quiera que un objeto rebote de forma realista o se comporte como si estuviera sobre un muelle. Podría usar animaciones de fotogramas clave o incluso animaciones From/To/By para aproximarse a estos efectos pero supondría bastante trabajo y la animación sería menos precisa que si usa un fórmula matemática.  
  
 Además de crear su propia función de aceleración personalizada heredando <xref:System.Windows.Media.Animation.EasingFunctionBase>de, puede usar una de las diversas funciones de aceleración proporcionadas por el motor en tiempo de ejecución para crear efectos comunes.  
  
- <xref:System.Windows.Media.Animation.BackEase>: Retira ligeramente el movimiento de una animación antes de que empiece a animarse en la ruta de acceso indicada.  
  
- <xref:System.Windows.Media.Animation.BounceEase>: Crea un efecto de rebote.  
  
- <xref:System.Windows.Media.Animation.CircleEase>: Crea una animación que acelera y/o desacelera mediante una función circular.  
  
- <xref:System.Windows.Media.Animation.CubicEase>: Crea una animación que acelera y/o desacelera mediante la fórmula *f*(*t*) = *t*<sup>3</sup>.  
  
- <xref:System.Windows.Media.Animation.ElasticEase>: Crea una animación que se parece a un muelle que oscila hacia atrás y hacia delante hasta que llegue al resto.  
  
- <xref:System.Windows.Media.Animation.ExponentialEase>: Crea una animación que acelera y/o desacelera mediante una fórmula exponencial.  
  
- <xref:System.Windows.Media.Animation.PowerEase>: Crea una animación que acelera y/o desacelera mediante la fórmula *f*(*t*) = *t*<sup>p</sup> , donde p es igual a la <xref:System.Windows.Media.Animation.PowerEase.Power%2A> propiedad.  
  
- <xref:System.Windows.Media.Animation.QuadraticEase>: Crea una animación que acelera y/o desacelera mediante la fórmula *f*(*t*) = *t*<sup>2</sup>.  
  
- <xref:System.Windows.Media.Animation.QuarticEase>: Crea una animación que acelera y/o desacelera mediante la fórmula *f*(*t*) = *t*<sup>4</sup>.  
  
- <xref:System.Windows.Media.Animation.QuinticEase>: Cree una animación que acelere y/o desacelera mediante la fórmula *f*(*t*) = *t*<sup>5</sup>.  
  
- <xref:System.Windows.Media.Animation.SineEase>: Crea una animación que acelera y/o desacelera mediante una fórmula de seno.  
  
 Para aplicar una función de aceleración a una animación, use `EasingFunction` la propiedad de la animación especifique la función de aceleración que se va a aplicar a la animación. En el ejemplo siguiente se <xref:System.Windows.Media.Animation.BounceEase> aplica una función de <xref:System.Windows.Media.Animation.DoubleAnimation> aceleración a un para crear un efecto de rebote.  
  
 [!code-xaml[BounceEase_snippet#BounceEase](~/samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 En el ejemplo anterior, la función de aceleración se aplicó a una animación From/To/By. También puede aplicar estas funciones de aceleración a animaciones de fotogramas clave. En el ejemplo siguiente se muestra cómo usar fotogramas clave con funciones de aceleración asociadas a ellos para crear una animación de un rectángulo que se contrae hacia arriba, se ralentiza, se expande hacia abajo (como si cayera) y luego rebota hasta detenerse.  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](~/samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 Puede usar la <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> propiedad para modificar el comportamiento de la función de aceleración, es decir, cambiar el modo en que se interpola la animación. Hay tres posibles valores que puede proporcionar para <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:  
  
- <xref:System.Windows.Media.Animation.EasingMode.EaseIn>: La interpolación sigue la fórmula matemática asociada a la función de aceleración.  
  
- <xref:System.Windows.Media.Animation.EasingMode.EaseOut>: La interpolación sigue la interpolación del 100% menos el resultado de la fórmula asociada con la función de aceleración.  
  
- <xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: La interpolación <xref:System.Windows.Media.Animation.EasingMode.EaseIn> utiliza para la primera mitad de la animación <xref:System.Windows.Media.Animation.EasingMode.EaseOut> y para la segunda mitad.  
  
 Los gráficos siguientes muestran los distintos valores de donde <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> *f*(*x*) representa el progreso de la animación y *t* representa el tiempo.  
  
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
> Puede usar <xref:System.Windows.Media.Animation.PowerEase> para crear el mismo comportamiento que <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>y <xref:System.Windows.Media.Animation.QuinticEase> mediante la <xref:System.Windows.Media.Animation.PowerEase.Power%2A> propiedad. Por ejemplo, si desea usar <xref:System.Windows.Media.Animation.PowerEase> para sustituir por <xref:System.Windows.Media.Animation.CubicEase>, especifique un <xref:System.Windows.Media.Animation.PowerEase.Power%2A> valor de 3.  
  
 Además de usar las funciones de aceleración que se incluyen en el tiempo de ejecución, puede crear sus propias funciones personalizadas de aceleración heredando <xref:System.Windows.Media.Animation.EasingFunctionBase>de. En el ejemplo siguiente se muestra cómo crear una función de aceleración simple personalizada. Puede agregar su propia lógica matemática para el comportamiento de la función de aceleración invalidando el <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> método.   
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
