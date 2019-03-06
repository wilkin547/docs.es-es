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
ms.openlocfilehash: 456308e37bddc1df86b49085139a3810c4959a58
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354510"
---
# <a name="easing-functions"></a><span data-ttu-id="f27a6-102">Funciones de aceleración</span><span class="sxs-lookup"><span data-stu-id="f27a6-102">Easing Functions</span></span>
<span data-ttu-id="f27a6-103">Las funciones de aceleración le permiten aplicar fórmulas matemáticas personalizadas a las animaciones.</span><span class="sxs-lookup"><span data-stu-id="f27a6-103">Easing functions allow you to apply custom mathematical formulas to your animations.</span></span> <span data-ttu-id="f27a6-104">Por ejemplo, puede que quiera que un objeto rebote de forma realista o se comporte como si estuviera sobre un muelle.</span><span class="sxs-lookup"><span data-stu-id="f27a6-104">For example, you may want an object to realistically bounce or behave as though it were on a spring.</span></span> <span data-ttu-id="f27a6-105">Podría usar animaciones de fotogramas clave o incluso animaciones From/To/By para aproximarse a estos efectos pero supondría bastante trabajo y la animación sería menos precisa que si usa un fórmula matemática.</span><span class="sxs-lookup"><span data-stu-id="f27a6-105">You could use Key-Frame or even From/To/By animations to approximate these effects but it would take a significant amount of work and the animation would be less accurate than using a mathematical formula.</span></span>  
  
 <span data-ttu-id="f27a6-106">Además de crear su propia función de aceleración personalizada heredando de <xref:System.Windows.Media.Animation.EasingFunctionBase>, puede usar una de las funciones de aceleración proporcionadas por el tiempo de ejecución para crear efectos comunes.</span><span class="sxs-lookup"><span data-stu-id="f27a6-106">Besides creating your own custom easing function by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>, you can use one of several easing functions provided by the runtime to create common effects.</span></span>  
  
-   <span data-ttu-id="f27a6-107"><xref:System.Windows.Media.Animation.BackEase>: Retrae ligeramente el movimiento de una animación antes de que comience a animarse en la ruta de acceso indicada.</span><span class="sxs-lookup"><span data-stu-id="f27a6-107"><xref:System.Windows.Media.Animation.BackEase>: Retracts the motion of an animation slightly before it begins to animate in the path indicated.</span></span>  
  
-   <span data-ttu-id="f27a6-108"><xref:System.Windows.Media.Animation.BounceEase>: Crea un efecto de rebote.</span><span class="sxs-lookup"><span data-stu-id="f27a6-108"><xref:System.Windows.Media.Animation.BounceEase>: Creates a bouncing effect.</span></span>  
  
-   <span data-ttu-id="f27a6-109"><xref:System.Windows.Media.Animation.CircleEase>: Crea una animación que acelera y/o desacelera mediante una función circular.</span><span class="sxs-lookup"><span data-stu-id="f27a6-109"><xref:System.Windows.Media.Animation.CircleEase>: Creates an animation that accelerates and/or decelerates using a circular function.</span></span>  
  
-   <span data-ttu-id="f27a6-110"><xref:System.Windows.Media.Animation.CubicEase>: Crea una animación que acelera y/o desacelera mediante la fórmula *f*(*t*) = *t*<sup>3</sup>.</span><span class="sxs-lookup"><span data-stu-id="f27a6-110"><xref:System.Windows.Media.Animation.CubicEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>3</sup>.</span></span>  
  
-   <span data-ttu-id="f27a6-111"><xref:System.Windows.Media.Animation.ElasticEase>: Crea una animación que simula un muelle y hacia atrás hasta llegar a detenerse.</span><span class="sxs-lookup"><span data-stu-id="f27a6-111"><xref:System.Windows.Media.Animation.ElasticEase>: Creates an animation that resembles a spring oscillating back and forth until it comes to rest.</span></span>  
  
-   <span data-ttu-id="f27a6-112"><xref:System.Windows.Media.Animation.ExponentialEase>: Crea una animación que acelera y/o desacelera mediante una fórmula exponencial.</span><span class="sxs-lookup"><span data-stu-id="f27a6-112"><xref:System.Windows.Media.Animation.ExponentialEase>: Creates an animation that accelerates and/or decelerates using an exponential formula.</span></span>  
  
-   <span data-ttu-id="f27a6-113"><xref:System.Windows.Media.Animation.PowerEase>: Crea una animación que acelera y/o desacelera mediante la fórmula *f*(*t*) = *t*<sup>p</sup> donde p es igual a la <xref:System.Windows.Media.Animation.PowerEase.Power%2A>propiedad.</span><span class="sxs-lookup"><span data-stu-id="f27a6-113"><xref:System.Windows.Media.Animation.PowerEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>p</sup> where p is equal to the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span>  
  
-   <span data-ttu-id="f27a6-114"><xref:System.Windows.Media.Animation.QuadraticEase>: Crea una animación que acelera y/o desacelera mediante la fórmula *f*(*t*) = *t*<sup>2</sup>.</span><span class="sxs-lookup"><span data-stu-id="f27a6-114"><xref:System.Windows.Media.Animation.QuadraticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>2</sup>.</span></span>  
  
-   <span data-ttu-id="f27a6-115"><xref:System.Windows.Media.Animation.QuarticEase>: Crea una animación que acelera y/o desacelera mediante la fórmula *f*(*t*) = *t*<sup>4</sup>.</span><span class="sxs-lookup"><span data-stu-id="f27a6-115"><xref:System.Windows.Media.Animation.QuarticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>4</sup>.</span></span>  
  
-   <span data-ttu-id="f27a6-116"><xref:System.Windows.Media.Animation.QuinticEase>: Crear una animación que acelera y/o desacelera mediante la fórmula *f*(*t*) = *t*<sup>5</sup>.</span><span class="sxs-lookup"><span data-stu-id="f27a6-116"><xref:System.Windows.Media.Animation.QuinticEase>: Create an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>5</sup>.</span></span>  
  
-   <span data-ttu-id="f27a6-117"><xref:System.Windows.Media.Animation.SineEase>: Crea una animación que acelera y/o desacelera mediante una fórmula de seno.</span><span class="sxs-lookup"><span data-stu-id="f27a6-117"><xref:System.Windows.Media.Animation.SineEase>: Creates an animation that accelerates and/or decelerates using a sine formula.</span></span>  
  
 <span data-ttu-id="f27a6-118">Para aplicar una función de aceleración a una animación, use la `EasingFunction` propiedad de la animación para especificar la función que se aplicará a la animación.</span><span class="sxs-lookup"><span data-stu-id="f27a6-118">To apply an easing function to an animation, use the `EasingFunction` property of the animation specify the easing function to apply to the animation.</span></span> <span data-ttu-id="f27a6-119">El ejemplo siguiente aplica un <xref:System.Windows.Media.Animation.BounceEase> función de aceleración un <xref:System.Windows.Media.Animation.DoubleAnimation> para crear un efecto de rebote.</span><span class="sxs-lookup"><span data-stu-id="f27a6-119">The following example applies a <xref:System.Windows.Media.Animation.BounceEase> easing function to a <xref:System.Windows.Media.Animation.DoubleAnimation> to create a bouncing effect.</span></span>  
  
 [!code-xaml[BounceEase_snippet#BounceEase](~/samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 <span data-ttu-id="f27a6-120">En el ejemplo anterior, la función de aceleración se aplicó a una animación From/To/By.</span><span class="sxs-lookup"><span data-stu-id="f27a6-120">In the previous example, the easing function was applied to a From/To/By animation.</span></span> <span data-ttu-id="f27a6-121">También puede aplicar estas funciones de aceleración a animaciones de fotogramas clave.</span><span class="sxs-lookup"><span data-stu-id="f27a6-121">You can also apply these easing functions to Key-Frame animations.</span></span> <span data-ttu-id="f27a6-122">En el ejemplo siguiente se muestra cómo usar fotogramas clave con funciones de aceleración asociadas a ellos para crear una animación de un rectángulo que se contrae hacia arriba, se ralentiza, se expande hacia abajo (como si cayera) y luego rebota hasta detenerse.</span><span class="sxs-lookup"><span data-stu-id="f27a6-122">The following example shows how to use key frames with easing functions associated with them to create an animation of a rectangle that contracts upward, slows down, then expands downward (as though falling) and then bounces to a stop.</span></span>  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](~/samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 <span data-ttu-id="f27a6-123">Puede usar el <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> cambio de propiedad para modificar cómo se comporta la función de aceleración, es decir, cómo se interpola la animación.</span><span class="sxs-lookup"><span data-stu-id="f27a6-123">You can use the <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> property to alter how the easing function behaves, that is, change how the animation interpolates.</span></span> <span data-ttu-id="f27a6-124">Hay tres valores posibles que puede dar para <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:</span><span class="sxs-lookup"><span data-stu-id="f27a6-124">There are three possible values you can give for <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:</span></span>  
  
-   <span data-ttu-id="f27a6-125"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: La interpolación sigue la fórmula matemática asociada con la función de aceleración.</span><span class="sxs-lookup"><span data-stu-id="f27a6-125"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: Interpolation follows the mathematical formula associated with the easing function.</span></span>  
  
-   <span data-ttu-id="f27a6-126"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: La interpolación sigue la interpolación al 100% menos el resultado de la fórmula asociada con la función de aceleración.</span><span class="sxs-lookup"><span data-stu-id="f27a6-126"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: Interpolation follows 100% interpolation minus the output of the formula associated with the easing function.</span></span>  
  
-   <span data-ttu-id="f27a6-127"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Interpolación utiliza <xref:System.Windows.Media.Animation.EasingMode.EaseIn> durante la primera mitad de la animación y <xref:System.Windows.Media.Animation.EasingMode.EaseOut> para la segunda mitad.</span><span class="sxs-lookup"><span data-stu-id="f27a6-127"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Interpolation uses <xref:System.Windows.Media.Animation.EasingMode.EaseIn> for the first half of the animation and <xref:System.Windows.Media.Animation.EasingMode.EaseOut> for the second half.</span></span>  
  
 <span data-ttu-id="f27a6-128">Los gráficos siguientes muestran los distintos valores de <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> donde *f*(*x*) representa el progreso de la animación y *t* representa el tiempo.</span><span class="sxs-lookup"><span data-stu-id="f27a6-128">The graphs below demonstrate the different values of <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> where *f*(*x*) represents the animation progress and *t* represents time.</span></span>  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 <span data-ttu-id="f27a6-129">![Gráficos EasingMode para BackEase.](./media/backease-graph.png "BackEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="f27a6-129">![BackEase EasingMode graphs.](./media/backease-graph.png "BackEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 <span data-ttu-id="f27a6-130">![Gráficos EasingMode para BounceEase.](./media/bounceease-graph.png "BounceEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="f27a6-130">![BounceEase EasingMode graphs.](./media/bounceease-graph.png "BounceEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 <span data-ttu-id="f27a6-131">![Gráficos EasingMode para CircleEase.](./media/circleease-graph.png "CircleEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="f27a6-131">![CircleEase EasingMode graphs.](./media/circleease-graph.png "CircleEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 <span data-ttu-id="f27a6-132">![Gráficos EasingMode para CubicEase.](./media/cubicease-graph.png "CubicEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="f27a6-132">![CubicEase EasingMode graphs.](./media/cubicease-graph.png "CubicEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 <span data-ttu-id="f27a6-133">![ElasticEase con gráficos de diferentes EasingMode.](./media/elasticease-graph.png "ElasticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="f27a6-133">![ElasticEase with graphs of different easingmodes.](./media/elasticease-graph.png "ElasticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 <span data-ttu-id="f27a6-134">![Gráficos ExponentialEase de diferentes EasingMode.](./media/exponentialease-graph.png "ExponentialEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="f27a6-134">![ExponentialEase graphs of different easingmodes.](./media/exponentialease-graph.png "ExponentialEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 <span data-ttu-id="f27a6-135">![QuarticEase con gráficos de diferentes EasingMode.](./media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="f27a6-135">![QuarticEase with graphs of different easingmodes.](./media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 <span data-ttu-id="f27a6-136">![QuadraticEase con gráficos de la diferentes EasingMode](./media/quadraticease-graph.png "QuadraticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="f27a6-136">![QuadraticEase with graphs of different easingmodes](./media/quadraticease-graph.png "QuadraticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 <span data-ttu-id="f27a6-137">![QuarticEase con gráficos de diferentes EasingMode.](./media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="f27a6-137">![QuarticEase with graphs of different easingmodes.](./media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 <span data-ttu-id="f27a6-138">![QuinticEase con gráficos de diferentes EasingMode.](./media/quinticease-graph.png "QuinticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="f27a6-138">![QuinticEase with graphs of different easingmodes.](./media/quinticease-graph.png "QuinticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 <span data-ttu-id="f27a6-139">![SineEase para diferentes valores de EasingMode](./media/sineease-graph.png "SineEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="f27a6-139">![SineEase for different EasingMode values](./media/sineease-graph.png "SineEase_Graph")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f27a6-140">Puede usar <xref:System.Windows.Media.Animation.PowerEase> para crear el mismo comportamiento que <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, y <xref:System.Windows.Media.Animation.QuinticEase> utilizando el <xref:System.Windows.Media.Animation.PowerEase.Power%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="f27a6-140">You can use <xref:System.Windows.Media.Animation.PowerEase> to create the same behavior as <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, and <xref:System.Windows.Media.Animation.QuinticEase> by using the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span> <span data-ttu-id="f27a6-141">Por ejemplo, si desea usar <xref:System.Windows.Media.Animation.PowerEase> para sustituir <xref:System.Windows.Media.Animation.CubicEase>, especifique un <xref:System.Windows.Media.Animation.PowerEase.Power%2A> valor 3.</span><span class="sxs-lookup"><span data-stu-id="f27a6-141">For example, if you want to use <xref:System.Windows.Media.Animation.PowerEase> to substitute for <xref:System.Windows.Media.Animation.CubicEase>, specify a <xref:System.Windows.Media.Animation.PowerEase.Power%2A> value of 3.</span></span>  
  
 <span data-ttu-id="f27a6-142">Además de utilizar las funciones de aceleración incluidas en el tiempo de ejecución, puede crear sus propias funciones de aceleración personalizadas heredando de <xref:System.Windows.Media.Animation.EasingFunctionBase>.</span><span class="sxs-lookup"><span data-stu-id="f27a6-142">In addition to using the easing functions included in the run-time, you can create your own custom easing functions by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>.</span></span> <span data-ttu-id="f27a6-143">En el ejemplo siguiente se muestra cómo crear una función de aceleración simple personalizada.</span><span class="sxs-lookup"><span data-stu-id="f27a6-143">The following example demonstrates how to create a simple custom easing function.</span></span> <span data-ttu-id="f27a6-144">Puede agregar su propia lógica matemática para cómo se comporta la función de aceleración invalidando el <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> método.</span><span class="sxs-lookup"><span data-stu-id="f27a6-144">You can add your own mathematical logic for how the easing function behaves by overriding the <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> method.</span></span>   
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
