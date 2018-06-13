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
ms.locfileid: "33557568"
---
# <a name="easing-functions"></a><span data-ttu-id="97890-102">Funciones de aceleración</span><span class="sxs-lookup"><span data-stu-id="97890-102">Easing Functions</span></span>
<span data-ttu-id="97890-103">Las funciones de aceleración le permiten aplicar fórmulas matemáticas personalizadas a las animaciones.</span><span class="sxs-lookup"><span data-stu-id="97890-103">Easing functions allow you to apply custom mathematical formulas to your animations.</span></span> <span data-ttu-id="97890-104">Por ejemplo, puede que quiera que un objeto rebote de forma realista o se comporte como si estuviera sobre un muelle.</span><span class="sxs-lookup"><span data-stu-id="97890-104">For example, you may want an object to realistically bounce or behave as though it were on a spring.</span></span> <span data-ttu-id="97890-105">Podría usar animaciones de fotogramas clave o incluso animaciones From/To/By para aproximarse a estos efectos pero supondría bastante trabajo y la animación sería menos precisa que si usa un fórmula matemática.</span><span class="sxs-lookup"><span data-stu-id="97890-105">You could use Key-Frame or even From/To/By animations to approximate these effects but it would take a significant amount of work and the animation would be less accurate than using a mathematical formula.</span></span>  
  
 <span data-ttu-id="97890-106">Además de crear su propia función de aceleración personalizada mediante la adquisición de <xref:System.Windows.Media.Animation.EasingFunctionBase>, puede usar una de varias funciones de aceleración proporcionadas por el tiempo de ejecución para crear efectos comunes.</span><span class="sxs-lookup"><span data-stu-id="97890-106">Besides creating your own custom easing function by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>, you can use one of several easing functions provided by the runtime to create common effects.</span></span>  
  
-   <span data-ttu-id="97890-107"><xref:System.Windows.Media.Animation.BackEase>: Retira el movimiento de una animación un poco antes de comenzar a animar en la ruta de acceso indicada.</span><span class="sxs-lookup"><span data-stu-id="97890-107"><xref:System.Windows.Media.Animation.BackEase>: Retracts the motion of an animation slightly before it begins to animate in the path indicated.</span></span>  
  
-   <span data-ttu-id="97890-108"><xref:System.Windows.Media.Animation.BounceEase>: Crea un efecto de rebote.</span><span class="sxs-lookup"><span data-stu-id="97890-108"><xref:System.Windows.Media.Animation.BounceEase>: Creates a bouncing effect.</span></span>  
  
-   <span data-ttu-id="97890-109"><xref:System.Windows.Media.Animation.CircleEase>: Crea una animación que aumenta y/o reduce la velocidad mediante una función circular.</span><span class="sxs-lookup"><span data-stu-id="97890-109"><xref:System.Windows.Media.Animation.CircleEase>: Creates an animation that accelerates and/or decelerates using a circular function.</span></span>  
  
-   <span data-ttu-id="97890-110"><xref:System.Windows.Media.Animation.CubicEase>: Crea una animación que aumenta y/o reduce la velocidad mediante la fórmula *f*(*t*) = *t*<sup>3</sup>.</span><span class="sxs-lookup"><span data-stu-id="97890-110"><xref:System.Windows.Media.Animation.CubicEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>3</sup>.</span></span>  
  
-   <span data-ttu-id="97890-111"><xref:System.Windows.Media.Animation.ElasticEase>: Crea una animación que se parezca a un muelle que oscila atrás y adelante hasta que se trata de rest.</span><span class="sxs-lookup"><span data-stu-id="97890-111"><xref:System.Windows.Media.Animation.ElasticEase>: Creates an animation that resembles a spring oscillating back and forth until it comes to rest.</span></span>  
  
-   <span data-ttu-id="97890-112"><xref:System.Windows.Media.Animation.ExponentialEase>: Crea una animación que aumenta y/o reduce la velocidad mediante una fórmula exponencial.</span><span class="sxs-lookup"><span data-stu-id="97890-112"><xref:System.Windows.Media.Animation.ExponentialEase>: Creates an animation that accelerates and/or decelerates using an exponential formula.</span></span>  
  
-   <span data-ttu-id="97890-113"><xref:System.Windows.Media.Animation.PowerEase>: Crea una animación que aumenta y/o reduce la velocidad mediante la fórmula *f*(*t*) = *t*<sup>p</sup> donde p es igual a la <xref:System.Windows.Media.Animation.PowerEase.Power%2A>propiedad.</span><span class="sxs-lookup"><span data-stu-id="97890-113"><xref:System.Windows.Media.Animation.PowerEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>p</sup> where p is equal to the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span>  
  
-   <span data-ttu-id="97890-114"><xref:System.Windows.Media.Animation.QuadraticEase>: Crea una animación que aumenta y/o reduce la velocidad mediante la fórmula *f*(*t*) = *t*<sup>2</sup>.</span><span class="sxs-lookup"><span data-stu-id="97890-114"><xref:System.Windows.Media.Animation.QuadraticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>2</sup>.</span></span>  
  
-   <span data-ttu-id="97890-115"><xref:System.Windows.Media.Animation.QuarticEase>: Crea una animación que aumenta y/o reduce la velocidad mediante la fórmula *f*(*t*) = *t*<sup>4</sup>.</span><span class="sxs-lookup"><span data-stu-id="97890-115"><xref:System.Windows.Media.Animation.QuarticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>4</sup>.</span></span>  
  
-   <span data-ttu-id="97890-116"><xref:System.Windows.Media.Animation.QuinticEase>: Cree una animación que aumenta y/o reduce la velocidad mediante la fórmula *f*(*t*) = *t*<sup>5</sup>.</span><span class="sxs-lookup"><span data-stu-id="97890-116"><xref:System.Windows.Media.Animation.QuinticEase>: Create an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>5</sup>.</span></span>  
  
-   <span data-ttu-id="97890-117"><xref:System.Windows.Media.Animation.SineEase>: Crea una animación que aumenta y/o reduce la velocidad mediante una fórmula de seno.</span><span class="sxs-lookup"><span data-stu-id="97890-117"><xref:System.Windows.Media.Animation.SineEase>: Creates an animation that accelerates and/or decelerates using a sine formula.</span></span>  
  
 <span data-ttu-id="97890-118">Puede explorar el comportamiento de estas funciones de aceleración con el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="97890-118">You can explore the behavior of these easing functions with the following sample.</span></span>  
  
 [<span data-ttu-id="97890-119">Ejecutar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="97890-119">Run this sample</span></span>](http://go.microsoft.com/fwlink/?LinkId=139798&sref=easing_functions_gallery)  
  
 <span data-ttu-id="97890-120">Para aplicar una función de aceleración a una animación, utilice el `EasingFunction` la propiedad de la animación especificar la función de aceleración para aplicar a la animación.</span><span class="sxs-lookup"><span data-stu-id="97890-120">To apply an easing function to an animation, use the `EasingFunction` property of the animation specify the easing function to apply to the animation.</span></span> <span data-ttu-id="97890-121">El ejemplo siguiente aplica un <xref:System.Windows.Media.Animation.BounceEase> función de aceleración una <xref:System.Windows.Media.Animation.DoubleAnimation> para crear un efecto de rebote.</span><span class="sxs-lookup"><span data-stu-id="97890-121">The following example applies a <xref:System.Windows.Media.Animation.BounceEase> easing function to a <xref:System.Windows.Media.Animation.DoubleAnimation> to create a bouncing effect.</span></span>  
  
 [<span data-ttu-id="97890-122">Ejecutar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="97890-122">Run this sample</span></span>](http://go.microsoft.com/fwlink/?LinkId=139798&sref=BounceEase)  
  
 [!code-xaml[BounceEase_snippet#BounceEase](../../../../samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 <span data-ttu-id="97890-123">En el ejemplo anterior, la función de aceleración se aplicó a una animación From/To/By.</span><span class="sxs-lookup"><span data-stu-id="97890-123">In the previous example, the easing function was applied to a From/To/By animation.</span></span> <span data-ttu-id="97890-124">También puede aplicar estas funciones de aceleración a animaciones de fotogramas clave.</span><span class="sxs-lookup"><span data-stu-id="97890-124">You can also apply these easing functions to Key-Frame animations.</span></span> <span data-ttu-id="97890-125">En el ejemplo siguiente se muestra cómo usar fotogramas clave con funciones de aceleración asociadas a ellos para crear una animación de un rectángulo que se contrae hacia arriba, se ralentiza, se expande hacia abajo (como si cayera) y luego rebota hasta detenerse.</span><span class="sxs-lookup"><span data-stu-id="97890-125">The following example shows how to use key frames with easing functions associated with them to create an animation of a rectangle that contracts upward, slows down, then expands downward (as though falling) and then bounces to a stop.</span></span>  
  
 [<span data-ttu-id="97890-126">Ejecutar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="97890-126">Run this sample</span></span>](http://go.microsoft.com/fwlink/?LinkId=139798&sref=EasingFunctionDoubleKeyFrame)  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](../../../../samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 <span data-ttu-id="97890-127">Puede usar el <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> cambio de propiedad para modificar cómo se comporta la función de aceleración, es decir, cómo se interpola la animación.</span><span class="sxs-lookup"><span data-stu-id="97890-127">You can use the <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> property to alter how the easing function behaves, that is, change how the animation interpolates.</span></span> <span data-ttu-id="97890-128">Hay tres valores posibles que puede proporcionar <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:</span><span class="sxs-lookup"><span data-stu-id="97890-128">There are three possible values you can give for <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:</span></span>  
  
-   <span data-ttu-id="97890-129"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: La interpolación sigue la fórmula matemática asociada a la función de aceleración.</span><span class="sxs-lookup"><span data-stu-id="97890-129"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: Interpolation follows the mathematical formula associated with the easing function.</span></span>  
  
-   <span data-ttu-id="97890-130"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: La interpolación sigue la interpolación al 100% menos el resultado de la fórmula asociada con la función de aceleración.</span><span class="sxs-lookup"><span data-stu-id="97890-130"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: Interpolation follows 100% interpolation minus the output of the formula associated with the easing function.</span></span>  
  
-   <span data-ttu-id="97890-131"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Usa la interpolación <xref:System.Windows.Media.Animation.EasingMode.EaseIn> para la primera mitad de la animación y <xref:System.Windows.Media.Animation.EasingMode.EaseOut> para la segunda mitad.</span><span class="sxs-lookup"><span data-stu-id="97890-131"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Interpolation uses <xref:System.Windows.Media.Animation.EasingMode.EaseIn> for the first half of the animation and <xref:System.Windows.Media.Animation.EasingMode.EaseOut> for the second half.</span></span>  
  
 <span data-ttu-id="97890-132">En los gráficos siguientes muestran los distintos valores de <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> donde *f*(*x*) representa el progreso de la animación y *t* representa el tiempo.</span><span class="sxs-lookup"><span data-stu-id="97890-132">The graphs below demonstrate the different values of <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> where *f*(*x*) represents the animation progress and *t* represents time.</span></span>  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 <span data-ttu-id="97890-133">![Gráficos EasingMode para BackEase.](../../../../docs/framework/wpf/graphics-multimedia/media/backease-graph.png "BackEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="97890-133">![BackEase EasingMode graphs.](../../../../docs/framework/wpf/graphics-multimedia/media/backease-graph.png "BackEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 <span data-ttu-id="97890-134">![Gráficos EasingMode para BounceEase.](../../../../docs/framework/wpf/graphics-multimedia/media/bounceease-graph.png "BounceEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="97890-134">![BounceEase EasingMode graphs.](../../../../docs/framework/wpf/graphics-multimedia/media/bounceease-graph.png "BounceEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 <span data-ttu-id="97890-135">![Gráficos EasingMode para CircleEase.](../../../../docs/framework/wpf/graphics-multimedia/media/circleease-graph.png "CircleEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="97890-135">![CircleEase EasingMode graphs.](../../../../docs/framework/wpf/graphics-multimedia/media/circleease-graph.png "CircleEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 <span data-ttu-id="97890-136">![Gráficos EasingMode para CubicEase.](../../../../docs/framework/wpf/graphics-multimedia/media/cubicease-graph.png "CubicEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="97890-136">![CubicEase EasingMode graphs.](../../../../docs/framework/wpf/graphics-multimedia/media/cubicease-graph.png "CubicEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 <span data-ttu-id="97890-137">![ElasticEase con gráficos de diferentes EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/elasticease-graph.png "ElasticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="97890-137">![ElasticEase with graphs of different easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/elasticease-graph.png "ElasticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 <span data-ttu-id="97890-138">![Gráficos ExponentialEase de diferentes EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/exponentialease-graph.png "ExponentialEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="97890-138">![ExponentialEase graphs of different easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/exponentialease-graph.png "ExponentialEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 <span data-ttu-id="97890-139">![QuarticEase con gráficos de diferentes EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="97890-139">![QuarticEase with graphs of different easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 <span data-ttu-id="97890-140">![QuadraticEase con gráficos de la diferentes EasingMode](../../../../docs/framework/wpf/graphics-multimedia/media/quadraticease-graph.png "QuadraticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="97890-140">![QuadraticEase with graphs of different easingmodes](../../../../docs/framework/wpf/graphics-multimedia/media/quadraticease-graph.png "QuadraticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 <span data-ttu-id="97890-141">![QuarticEase con gráficos de diferentes EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="97890-141">![QuarticEase with graphs of different easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 <span data-ttu-id="97890-142">![QuinticEase con gráficos de diferentes EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/quinticease-graph.png "QuinticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="97890-142">![QuinticEase with graphs of different easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/quinticease-graph.png "QuinticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 <span data-ttu-id="97890-143">![SineEase para diferentes valores de EasingMode](../../../../docs/framework/wpf/graphics-multimedia/media/sineease-graph.png "SineEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="97890-143">![SineEase for different EasingMode values](../../../../docs/framework/wpf/graphics-multimedia/media/sineease-graph.png "SineEase_Graph")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="97890-144">Puede usar <xref:System.Windows.Media.Animation.PowerEase> para crear el mismo comportamiento que <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, y <xref:System.Windows.Media.Animation.QuinticEase> utilizando el <xref:System.Windows.Media.Animation.PowerEase.Power%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="97890-144">You can use <xref:System.Windows.Media.Animation.PowerEase> to create the same behavior as <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, and <xref:System.Windows.Media.Animation.QuinticEase> by using the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span> <span data-ttu-id="97890-145">Por ejemplo, si desea usar <xref:System.Windows.Media.Animation.PowerEase> para sustituir <xref:System.Windows.Media.Animation.CubicEase>, especifique un <xref:System.Windows.Media.Animation.PowerEase.Power%2A> valor 3.</span><span class="sxs-lookup"><span data-stu-id="97890-145">For example, if you want to use <xref:System.Windows.Media.Animation.PowerEase> to substitute for <xref:System.Windows.Media.Animation.CubicEase>, specify a <xref:System.Windows.Media.Animation.PowerEase.Power%2A> value of 3.</span></span>  
  
 <span data-ttu-id="97890-146">Además de utilizar las funciones de aceleración incluidas en el tiempo de ejecución, puede crear sus propias funciones de aceleración personalizadas mediante la adquisición de <xref:System.Windows.Media.Animation.EasingFunctionBase>.</span><span class="sxs-lookup"><span data-stu-id="97890-146">In addition to using the easing functions included in the run-time, you can create your own custom easing functions by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>.</span></span> <span data-ttu-id="97890-147">En el ejemplo siguiente se muestra cómo crear una función de aceleración simple personalizada.</span><span class="sxs-lookup"><span data-stu-id="97890-147">The following example demonstrates how to create a simple custom easing function.</span></span> <span data-ttu-id="97890-148">Puede agregar su propia lógica matemática para el funcionamiento de la función de aceleración invalidando el <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> método.</span><span class="sxs-lookup"><span data-stu-id="97890-148">You can add your own mathematical logic for how the easing function behaves by overriding the <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> method.</span></span>  
  
 [<span data-ttu-id="97890-149">Ejecutar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="97890-149">Run this sample</span></span>](http://go.microsoft.com/fwlink/?LinkId=139798&sref=CustomEasingFunction)  
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
