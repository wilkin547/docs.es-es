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
# <a name="easing-functions"></a><span data-ttu-id="68470-102">Funciones de aceleración</span><span class="sxs-lookup"><span data-stu-id="68470-102">Easing Functions</span></span>
<span data-ttu-id="68470-103">Las funciones de aceleración le permiten aplicar fórmulas matemáticas personalizadas a las animaciones.</span><span class="sxs-lookup"><span data-stu-id="68470-103">Easing functions allow you to apply custom mathematical formulas to your animations.</span></span> <span data-ttu-id="68470-104">Por ejemplo, puede que quiera que un objeto rebote de forma realista o se comporte como si estuviera sobre un muelle.</span><span class="sxs-lookup"><span data-stu-id="68470-104">For example, you may want an object to realistically bounce or behave as though it were on a spring.</span></span> <span data-ttu-id="68470-105">Podría usar animaciones de fotogramas clave o incluso animaciones From/To/By para aproximarse a estos efectos pero supondría bastante trabajo y la animación sería menos precisa que si usa un fórmula matemática.</span><span class="sxs-lookup"><span data-stu-id="68470-105">You could use Key-Frame or even From/To/By animations to approximate these effects but it would take a significant amount of work and the animation would be less accurate than using a mathematical formula.</span></span>  
  
 <span data-ttu-id="68470-106">Además de crear su propia función de aceleración personalizada heredando <xref:System.Windows.Media.Animation.EasingFunctionBase>de, puede usar una de las diversas funciones de aceleración proporcionadas por el motor en tiempo de ejecución para crear efectos comunes.</span><span class="sxs-lookup"><span data-stu-id="68470-106">Besides creating your own custom easing function by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>, you can use one of several easing functions provided by the runtime to create common effects.</span></span>  
  
- <span data-ttu-id="68470-107"><xref:System.Windows.Media.Animation.BackEase>: Retira ligeramente el movimiento de una animación antes de que empiece a animarse en la ruta de acceso indicada.</span><span class="sxs-lookup"><span data-stu-id="68470-107"><xref:System.Windows.Media.Animation.BackEase>: Retracts the motion of an animation slightly before it begins to animate in the path indicated.</span></span>  
  
- <span data-ttu-id="68470-108"><xref:System.Windows.Media.Animation.BounceEase>: Crea un efecto de rebote.</span><span class="sxs-lookup"><span data-stu-id="68470-108"><xref:System.Windows.Media.Animation.BounceEase>: Creates a bouncing effect.</span></span>  
  
- <span data-ttu-id="68470-109"><xref:System.Windows.Media.Animation.CircleEase>: Crea una animación que acelera y/o desacelera mediante una función circular.</span><span class="sxs-lookup"><span data-stu-id="68470-109"><xref:System.Windows.Media.Animation.CircleEase>: Creates an animation that accelerates and/or decelerates using a circular function.</span></span>  
  
- <span data-ttu-id="68470-110"><xref:System.Windows.Media.Animation.CubicEase>: Crea una animación que acelera y/o desacelera mediante la fórmula *f*(*t*) = *t*<sup>3</sup>.</span><span class="sxs-lookup"><span data-stu-id="68470-110"><xref:System.Windows.Media.Animation.CubicEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>3</sup>.</span></span>  
  
- <span data-ttu-id="68470-111"><xref:System.Windows.Media.Animation.ElasticEase>: Crea una animación que se parece a un muelle que oscila hacia atrás y hacia delante hasta que llegue al resto.</span><span class="sxs-lookup"><span data-stu-id="68470-111"><xref:System.Windows.Media.Animation.ElasticEase>: Creates an animation that resembles a spring oscillating back and forth until it comes to rest.</span></span>  
  
- <span data-ttu-id="68470-112"><xref:System.Windows.Media.Animation.ExponentialEase>: Crea una animación que acelera y/o desacelera mediante una fórmula exponencial.</span><span class="sxs-lookup"><span data-stu-id="68470-112"><xref:System.Windows.Media.Animation.ExponentialEase>: Creates an animation that accelerates and/or decelerates using an exponential formula.</span></span>  
  
- <span data-ttu-id="68470-113"><xref:System.Windows.Media.Animation.PowerEase>: Crea una animación que acelera y/o desacelera mediante la fórmula *f*(*t*) = *t*<sup>p</sup> , donde p es igual a la <xref:System.Windows.Media.Animation.PowerEase.Power%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="68470-113"><xref:System.Windows.Media.Animation.PowerEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>p</sup> where p is equal to the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span>  
  
- <span data-ttu-id="68470-114"><xref:System.Windows.Media.Animation.QuadraticEase>: Crea una animación que acelera y/o desacelera mediante la fórmula *f*(*t*) = *t*<sup>2</sup>.</span><span class="sxs-lookup"><span data-stu-id="68470-114"><xref:System.Windows.Media.Animation.QuadraticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>2</sup>.</span></span>  
  
- <span data-ttu-id="68470-115"><xref:System.Windows.Media.Animation.QuarticEase>: Crea una animación que acelera y/o desacelera mediante la fórmula *f*(*t*) = *t*<sup>4</sup>.</span><span class="sxs-lookup"><span data-stu-id="68470-115"><xref:System.Windows.Media.Animation.QuarticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>4</sup>.</span></span>  
  
- <span data-ttu-id="68470-116"><xref:System.Windows.Media.Animation.QuinticEase>: Cree una animación que acelere y/o desacelera mediante la fórmula *f*(*t*) = *t*<sup>5</sup>.</span><span class="sxs-lookup"><span data-stu-id="68470-116"><xref:System.Windows.Media.Animation.QuinticEase>: Create an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>5</sup>.</span></span>  
  
- <span data-ttu-id="68470-117"><xref:System.Windows.Media.Animation.SineEase>: Crea una animación que acelera y/o desacelera mediante una fórmula de seno.</span><span class="sxs-lookup"><span data-stu-id="68470-117"><xref:System.Windows.Media.Animation.SineEase>: Creates an animation that accelerates and/or decelerates using a sine formula.</span></span>  
  
 <span data-ttu-id="68470-118">Para aplicar una función de aceleración a una animación, use `EasingFunction` la propiedad de la animación especifique la función de aceleración que se va a aplicar a la animación.</span><span class="sxs-lookup"><span data-stu-id="68470-118">To apply an easing function to an animation, use the `EasingFunction` property of the animation specify the easing function to apply to the animation.</span></span> <span data-ttu-id="68470-119">En el ejemplo siguiente se <xref:System.Windows.Media.Animation.BounceEase> aplica una función de <xref:System.Windows.Media.Animation.DoubleAnimation> aceleración a un para crear un efecto de rebote.</span><span class="sxs-lookup"><span data-stu-id="68470-119">The following example applies a <xref:System.Windows.Media.Animation.BounceEase> easing function to a <xref:System.Windows.Media.Animation.DoubleAnimation> to create a bouncing effect.</span></span>  
  
 [!code-xaml[BounceEase_snippet#BounceEase](~/samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 <span data-ttu-id="68470-120">En el ejemplo anterior, la función de aceleración se aplicó a una animación From/To/By.</span><span class="sxs-lookup"><span data-stu-id="68470-120">In the previous example, the easing function was applied to a From/To/By animation.</span></span> <span data-ttu-id="68470-121">También puede aplicar estas funciones de aceleración a animaciones de fotogramas clave.</span><span class="sxs-lookup"><span data-stu-id="68470-121">You can also apply these easing functions to Key-Frame animations.</span></span> <span data-ttu-id="68470-122">En el ejemplo siguiente se muestra cómo usar fotogramas clave con funciones de aceleración asociadas a ellos para crear una animación de un rectángulo que se contrae hacia arriba, se ralentiza, se expande hacia abajo (como si cayera) y luego rebota hasta detenerse.</span><span class="sxs-lookup"><span data-stu-id="68470-122">The following example shows how to use key frames with easing functions associated with them to create an animation of a rectangle that contracts upward, slows down, then expands downward (as though falling) and then bounces to a stop.</span></span>  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](~/samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 <span data-ttu-id="68470-123">Puede usar la <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> propiedad para modificar el comportamiento de la función de aceleración, es decir, cambiar el modo en que se interpola la animación.</span><span class="sxs-lookup"><span data-stu-id="68470-123">You can use the <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> property to alter how the easing function behaves, that is, change how the animation interpolates.</span></span> <span data-ttu-id="68470-124">Hay tres posibles valores que puede proporcionar para <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:</span><span class="sxs-lookup"><span data-stu-id="68470-124">There are three possible values you can give for <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:</span></span>  
  
- <span data-ttu-id="68470-125"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: La interpolación sigue la fórmula matemática asociada a la función de aceleración.</span><span class="sxs-lookup"><span data-stu-id="68470-125"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: Interpolation follows the mathematical formula associated with the easing function.</span></span>  
  
- <span data-ttu-id="68470-126"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: La interpolación sigue la interpolación del 100% menos el resultado de la fórmula asociada con la función de aceleración.</span><span class="sxs-lookup"><span data-stu-id="68470-126"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: Interpolation follows 100% interpolation minus the output of the formula associated with the easing function.</span></span>  
  
- <span data-ttu-id="68470-127"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: La interpolación <xref:System.Windows.Media.Animation.EasingMode.EaseIn> utiliza para la primera mitad de la animación <xref:System.Windows.Media.Animation.EasingMode.EaseOut> y para la segunda mitad.</span><span class="sxs-lookup"><span data-stu-id="68470-127"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Interpolation uses <xref:System.Windows.Media.Animation.EasingMode.EaseIn> for the first half of the animation and <xref:System.Windows.Media.Animation.EasingMode.EaseOut> for the second half.</span></span>  
  
 <span data-ttu-id="68470-128">Los gráficos siguientes muestran los distintos valores de donde <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> *f*(*x*) representa el progreso de la animación y *t* representa el tiempo.</span><span class="sxs-lookup"><span data-stu-id="68470-128">The graphs below demonstrate the different values of <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> where *f*(*x*) represents the animation progress and *t* represents time.</span></span>  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 <span data-ttu-id="68470-129">![Gráficos EasingMode para BackEase.](./media/backease-graph.png "BackEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="68470-129">![BackEase EasingMode graphs.](./media/backease-graph.png "BackEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 <span data-ttu-id="68470-130">![Gráficos EasingMode para BounceEase.](./media/bounceease-graph.png "BounceEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="68470-130">![BounceEase EasingMode graphs.](./media/bounceease-graph.png "BounceEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 <span data-ttu-id="68470-131">![Gráficos EasingMode para CircleEase.](./media/circleease-graph.png "CircleEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="68470-131">![CircleEase EasingMode graphs.](./media/circleease-graph.png "CircleEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 <span data-ttu-id="68470-132">![Gráficos EasingMode para CubicEase.](./media/cubicease-graph.png "CubicEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="68470-132">![CubicEase EasingMode graphs.](./media/cubicease-graph.png "CubicEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 <span data-ttu-id="68470-133">![ElasticEase con gráficos de diferentes EasingMode.](./media/elasticease-graph.png "ElasticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="68470-133">![ElasticEase with graphs of different easingmodes.](./media/elasticease-graph.png "ElasticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 <span data-ttu-id="68470-134">![Gráficos ExponentialEase de diferentes EasingMode.](./media/exponentialease-graph.png "ExponentialEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="68470-134">![ExponentialEase graphs of different easingmodes.](./media/exponentialease-graph.png "ExponentialEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 <span data-ttu-id="68470-135">![QuarticEase con gráficos de diferentes EasingMode.](./media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="68470-135">![QuarticEase with graphs of different easingmodes.](./media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 <span data-ttu-id="68470-136">![QuadraticEase con gráficos de la diferentes EasingMode](./media/quadraticease-graph.png "QuadraticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="68470-136">![QuadraticEase with graphs of different easingmodes](./media/quadraticease-graph.png "QuadraticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 <span data-ttu-id="68470-137">![QuarticEase con gráficos de diferentes EasingMode.](./media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="68470-137">![QuarticEase with graphs of different easingmodes.](./media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 <span data-ttu-id="68470-138">![QuinticEase con gráficos de diferentes EasingMode.](./media/quinticease-graph.png "QuinticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="68470-138">![QuinticEase with graphs of different easingmodes.](./media/quinticease-graph.png "QuinticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 <span data-ttu-id="68470-139">![SineEase para diferentes valores de EasingMode](./media/sineease-graph.png "SineEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="68470-139">![SineEase for different EasingMode values](./media/sineease-graph.png "SineEase_Graph")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="68470-140">Puede usar <xref:System.Windows.Media.Animation.PowerEase> para crear el mismo comportamiento que <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>y <xref:System.Windows.Media.Animation.QuinticEase> mediante la <xref:System.Windows.Media.Animation.PowerEase.Power%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="68470-140">You can use <xref:System.Windows.Media.Animation.PowerEase> to create the same behavior as <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, and <xref:System.Windows.Media.Animation.QuinticEase> by using the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span> <span data-ttu-id="68470-141">Por ejemplo, si desea usar <xref:System.Windows.Media.Animation.PowerEase> para sustituir por <xref:System.Windows.Media.Animation.CubicEase>, especifique un <xref:System.Windows.Media.Animation.PowerEase.Power%2A> valor de 3.</span><span class="sxs-lookup"><span data-stu-id="68470-141">For example, if you want to use <xref:System.Windows.Media.Animation.PowerEase> to substitute for <xref:System.Windows.Media.Animation.CubicEase>, specify a <xref:System.Windows.Media.Animation.PowerEase.Power%2A> value of 3.</span></span>  
  
 <span data-ttu-id="68470-142">Además de usar las funciones de aceleración que se incluyen en el tiempo de ejecución, puede crear sus propias funciones personalizadas de aceleración heredando <xref:System.Windows.Media.Animation.EasingFunctionBase>de.</span><span class="sxs-lookup"><span data-stu-id="68470-142">In addition to using the easing functions included in the run-time, you can create your own custom easing functions by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>.</span></span> <span data-ttu-id="68470-143">En el ejemplo siguiente se muestra cómo crear una función de aceleración simple personalizada.</span><span class="sxs-lookup"><span data-stu-id="68470-143">The following example demonstrates how to create a simple custom easing function.</span></span> <span data-ttu-id="68470-144">Puede agregar su propia lógica matemática para el comportamiento de la función de aceleración invalidando el <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> método.</span><span class="sxs-lookup"><span data-stu-id="68470-144">You can add your own mathematical logic for how the easing function behaves by overriding the <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> method.</span></span>   
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
