---
title: "Funciones de aceleraci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "aplicar fórmulas matemáticas a las animaciones [WPF]"
  - "aplicar funciones de aceleración a las animaciones [WPF]"
  - "fórmulas matemáticas [WPF], aplicar a las animaciones"
  - "animaciones [WPF], movimiento realista"
  - "funciones de aceleración [WPF]"
  - "personalizar las funciones de aceleración [WPF]"
  - "funciones de aceleración [WPF], definición"
  - "funciones de aceleración [WPF], personalizar"
  - "aplicación de animaciones [WPF]"
ms.assetid: 075b9c2b-82c4-43fa-b3cd-de0b6236eb38
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Funciones de aceleraci&#243;n
Las funciones de aceleración permiten aplicar fórmulas matemáticas personalizadas a las animaciones. Por ejemplo, puede que un objeto rebote realista o se comporte como si fuera un muelle. Puede usar fotogramas clave o incluso animaciones From/To/By para aproximar estos efectos pero que tardaría una cantidad significativa de trabajo y la animación sería menos precisa que el uso de una fórmula matemática.  
  
 Además de crear su propia función de aceleración personalizada heredando de <xref:System.Windows.Media.Animation.EasingFunctionBase>, puede utilizar las funciones de aceleración proporcionadas por el tiempo de ejecución para crear efectos comunes.  
  
-   <xref:System.Windows.Media.Animation.BackEase>: retira el movimiento de una animación un poco antes de que comience a animar en la ruta indicada.  
  
-   <xref:System.Windows.Media.Animation.BounceEase>: crea un efecto de rebote.  
  
-   <xref:System.Windows.Media.Animation.CircleEase>: crea una animación que acelera y/o desacelera mediante una función circular.  
  
-   <xref:System.Windows.Media.Animation.CubicEase>: crea una animación que acelera y/o desacelera mediante la fórmula *f*( *t*) = *t*<sup>3</sup>.  
  
-   <xref:System.Windows.Media.Animation.ElasticEase>: crea una animación que simula un muelle que oscila adelante y atrás hasta que se detenga.  
  
-   <xref:System.Windows.Media.Animation.ExponentialEase>: crea una animación que acelera y/o desacelera mediante una fórmula exponencial.  
  
-   <xref:System.Windows.Media.Animation.PowerEase>: crea una animación que acelera y/o desacelera mediante la fórmula *f*( *t*) = *t*<sup>p</sup> donde p es igual a la <xref:System.Windows.Media.Animation.PowerEase.Power%2A> propiedad.  
  
-   <xref:System.Windows.Media.Animation.QuadraticEase>: crea una animación que acelera y/o desacelera mediante la fórmula *f*( *t*) = *t*<sup>2</sup>.  
  
-   <xref:System.Windows.Media.Animation.QuarticEase>: crea una animación que acelera y/o desacelera mediante la fórmula *f*( *t*) = *t*<sup>4</sup>.  
  
-   <xref:System.Windows.Media.Animation.QuinticEase>: crear una animación que acelera y/o desacelera mediante la fórmula *f*( *t*) = *t*<sup>5</sup>.  
  
-   <xref:System.Windows.Media.Animation.SineEase>: crea una animación que acelera y/o desacelera mediante una fórmula de seno.  
  
 Puede explorar el comportamiento de estas funciones de aceleración con el ejemplo siguiente.  
  
 [Ejecutar este ejemplo](http://go.microsoft.com/fwlink/?LinkId=139798&sref=easing_functions_gallery)  
  
 Para aplicar una función de aceleración a una animación, use la `EasingFunction` propiedad de la animación para especificar la función para aplicar a la animación. El ejemplo siguiente aplica un <xref:System.Windows.Media.Animation.BounceEase> función de aceleración un <xref:System.Windows.Media.Animation.DoubleAnimation> para crear un efecto de rebote.  
  
 [Ejecutar este ejemplo](http://go.microsoft.com/fwlink/?LinkId=139798&sref=BounceEase)  
  
 [!code-xml[BounceEase_snippet#BounceEase](../../../../samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 En el ejemplo anterior, la función de aceleración se aplicó a un From/To/By animación. También puede aplicar estas funciones de aceleración a las animaciones de fotogramas clave. En el ejemplo siguiente se muestra cómo usar fotogramas clave con funciones de aceleración asociadas a ellos para crear una animación de un rectángulo que contratos hacia arriba, se ralentiza, a continuación, se expande hacia abajo (como si cayera) y, a continuación, rebota hasta detenerse.  
  
 [Ejecutar este ejemplo](http://go.microsoft.com/fwlink/?LinkId=139798&sref=EasingFunctionDoubleKeyFrame)  
  
 [!code-xml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](../../../../samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 Puede usar el <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> cambio de propiedad para modificar cómo se comporta la función de aceleración, es decir, cómo la animación interpola. Hay tres valores posibles que puede dar para <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:  
  
-   <xref:System.Windows.Media.Animation.EasingMode>: la interpolación sigue la fórmula matemática asociada con la función de aceleración.  
  
-   <xref:System.Windows.Media.Animation.EasingMode>: la interpolación sigue la interpolación al 100% menos el resultado de la fórmula asociada a la función de aceleración.  
  
-   <xref:System.Windows.Media.Animation.EasingMode>: usa interpolación <xref:System.Windows.Media.Animation.EasingMode> para la primera mitad de la animación y <xref:System.Windows.Media.Animation.EasingMode> para la segunda mitad.  
  
 En los gráficos siguientes muestran los distintos valores de <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> donde *f*( *x*) representa el progreso de la animación y *t* representa el tiempo.  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 ![Gráficos BackEase EasingMode. ] (../Image/BackEase_Graph.png "BackEase_Graph")  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 ![Gráficos BounceEase EasingMode. ] (../Image/BounceEase_Graph.png "BounceEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 ![Gráficos CircleEase EasingMode. ] (../Image/CircleEase_Graph.png "CircleEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 ![Gráficos CubicEase EasingMode. ] (../Image/CubicEase_Graph.png "CubicEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 ![ElasticEase con gráficos de diferentes EasingMode. ] (../Image/ElasticEase_Graph.png "ElasticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 ![Gráficos ExponentialEase de diferentes EasingMode. ] (../Image/ExponentialEase_Graph.png "ExponentialEase_Graph")  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 ![QuarticEase con gráficos de diferentes EasingMode. ] (../Image/QuarticEase_Graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 ![QuadraticEase con gráficos de diferentes EasingMode](../../../../docs/framework/wpf/graphics-multimedia/media/quadraticease-graph.png "QuadraticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 ![QuarticEase con gráficos de diferentes EasingMode. ] (../Image/QuarticEase_Graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 ![QuinticEase con gráficos de diferentes EasingMode. ] (../Image/QuinticEase_Graph.png "QuinticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 ![SineEase para diferentes valores de EasingMode](../../../../docs/framework/wpf/graphics-multimedia/media/sineease-graph.png "SineEase_Graph")  
  
> [!NOTE]
>  Puede usar <xref:System.Windows.Media.Animation.PowerEase> para crear el mismo comportamiento que <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, y <xref:System.Windows.Media.Animation.QuinticEase> utilizando la <xref:System.Windows.Media.Animation.PowerEase.Power%2A> propiedad. Por ejemplo, si desea usar <xref:System.Windows.Media.Animation.PowerEase> para sustituir <xref:System.Windows.Media.Animation.CubicEase>, especifique un <xref:System.Windows.Media.Animation.PowerEase.Power%2A> valor de 3.  
  
 Además de utilizar las funciones de aceleración incluidas en el tiempo de ejecución, puede crear sus propias funciones de entradas y salidas lentas personalizadas heredando de <xref:System.Windows.Media.Animation.EasingFunctionBase>. En el ejemplo siguiente se muestra cómo crear una función simple de aceleración personalizada. Puede agregar su propia lógica matemática para el comportamiento de la función de aceleración invalidando el <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> método.  
  
 [Ejecutar este ejemplo](http://go.microsoft.com/fwlink/?LinkId=139798&sref=CustomEasingFunction)  
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xml[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]