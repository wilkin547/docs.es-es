---
title: 'Cómo: Controlar la temporización de animaciones y fotogramas clave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], timing
- timing key-frame animation
ms.assetid: b059216f-7d4b-4ca8-a019-bc287ee7bf16
ms.openlocfilehash: 8cfd2be0bbc526ed92a5fb1b558a5a41dc9c3113
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344735"
---
# <a name="how-to-control-key-frame-animation-timing"></a><span data-ttu-id="3b321-102">Cómo: Controlar la temporización de animaciones y fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="3b321-102">How to: Control Key-Frame Animation Timing</span></span>

<span data-ttu-id="3b321-103">En este ejemplo se muestra cómo controlar la sincronización de fotogramas clave dentro de una animación de fotograma clave.</span><span class="sxs-lookup"><span data-stu-id="3b321-103">This example shows how to control the timing of key frames within a key-frame animation.</span></span> <span data-ttu-id="3b321-104">Al igual que otras animaciones, <xref:System.Windows.Media.Animation.Timeline.Duration%2A> las animaciones de fotogramas clave tienen una propiedad.</span><span class="sxs-lookup"><span data-stu-id="3b321-104">Like other animations, key-frame animations have a <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property.</span></span> <span data-ttu-id="3b321-105">Además de especificar la duración de una animación, debe especificar qué parte de esa duración se asigna a cada uno de sus fotogramas clave.</span><span class="sxs-lookup"><span data-stu-id="3b321-105">In addition to specifying the duration of an animation, you need to specify what part of that duration is allotted to each of its key frames.</span></span> <span data-ttu-id="3b321-106">Para indicar el tiempo, <xref:System.Windows.Media.Animation.KeyTime> especifique a para cada fotograma clave de la animación.</span><span class="sxs-lookup"><span data-stu-id="3b321-106">To allot the time, you specify a <xref:System.Windows.Media.Animation.KeyTime> for each key frame in the animation.</span></span>

<span data-ttu-id="3b321-107">El <xref:System.Windows.Media.Animation.KeyTime> para cada fotograma clave especifica cuándo finaliza un fotograma clave (no especifica el tiempo que se reproduce un fotograma clave).</span><span class="sxs-lookup"><span data-stu-id="3b321-107">The <xref:System.Windows.Media.Animation.KeyTime> for each key frame specifies when a key frame ends (it does not specify the length of time a key frame plays).</span></span> <span data-ttu-id="3b321-108">Puede especificar <xref:System.Windows.Media.Animation.KeyTime> como <xref:System.TimeSpan> un valor, como un <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> porcentaje <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> o como el valor especial.</span><span class="sxs-lookup"><span data-stu-id="3b321-108">You can specify a <xref:System.Windows.Media.Animation.KeyTime> as a <xref:System.TimeSpan> value, as a percentage, or as the <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> or <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> special value.</span></span>

## <a name="example"></a><span data-ttu-id="3b321-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3b321-109">Example</span></span>

<span data-ttu-id="3b321-110">En el ejemplo <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> siguiente se usa a para animar un rectángulo a través de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="3b321-110">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> to animate a rectangle across the screen.</span></span> <span data-ttu-id="3b321-111">Los tiempos clave de <xref:System.TimeSpan> los fotogramas clave se establecen con valores.</span><span class="sxs-lookup"><span data-stu-id="3b321-111">The key frames' key times are set with <xref:System.TimeSpan> values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimestimespanexample)]
[!code-vb[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimestimespanexample)]
[!code-xaml[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimestimespanexample)]

<span data-ttu-id="3b321-112">La siguiente ilustración muestra cuándo se alcanza el valor de cada fotograma clave.</span><span class="sxs-lookup"><span data-stu-id="3b321-112">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="3b321-113">![Los valores de clave se alcanzan a 3, 4 y 10 segundos](./media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span><span class="sxs-lookup"><span data-stu-id="3b321-113">![Key values are reached at 3, 4, and 10 seconds](./media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span></span>

<span data-ttu-id="3b321-114">En el ejemplo siguiente se muestra una animación idéntica, excepto que los tiempos clave de los fotogramas clave se establecen con valores de porcentaje.</span><span class="sxs-lookup"><span data-stu-id="3b321-114">The next example shows an animation that is identical, except that the key frames' key times are set with percentage values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespercentageexample)]
[!code-vb[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespercentageexample)]
[!code-xaml[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespercentageexample)]

<span data-ttu-id="3b321-115">La siguiente ilustración muestra cuándo se alcanza el valor de cada fotograma clave.</span><span class="sxs-lookup"><span data-stu-id="3b321-115">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="3b321-116">![Los valores de clave se alcanzan a 3, 4 y 10 segundos](./media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span><span class="sxs-lookup"><span data-stu-id="3b321-116">![Key values are reached at 3, 4, and 10 seconds](./media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span></span>

<span data-ttu-id="3b321-117">En el <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> ejemplo siguiente se utilizan valores de tiempo clave.</span><span class="sxs-lookup"><span data-stu-id="3b321-117">The next example uses <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> key time values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimesuniformexample)]
[!code-vb[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimesuniformexample)]
[!code-xaml[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimesuniformexample)]

<span data-ttu-id="3b321-118">La siguiente ilustración muestra cuándo se alcanza el valor de cada fotograma clave.</span><span class="sxs-lookup"><span data-stu-id="3b321-118">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="3b321-119">![Los valores de clave se alcanzan a 3.3, 6.6 y 9.9 segundos](./media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span><span class="sxs-lookup"><span data-stu-id="3b321-119">![Key values are reached at 3.3,6.6, and 9.9 seconds](./media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span></span>

<span data-ttu-id="3b321-120">El ejemplo <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> final utiliza valores de tiempo clave.</span><span class="sxs-lookup"><span data-stu-id="3b321-120">The final example uses <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> key time values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespacedexample)]
[!code-vb[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespacedexample)]
[!code-xaml[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespacedexample)]

<span data-ttu-id="3b321-121">La siguiente ilustración muestra cuándo se alcanza el valor de cada fotograma clave.</span><span class="sxs-lookup"><span data-stu-id="3b321-121">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="3b321-122">![Los valores de clave se alcanzan a 0, 5 y 10 segundos](./media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span><span class="sxs-lookup"><span data-stu-id="3b321-122">![Key values are reached at 0, 5, and 10 seconds](./media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span></span>

<span data-ttu-id="3b321-123">Para simplificar, las versiones de código de este ejemplo usan animaciones locales, no guiones gráficos, porque solo se aplica una sola animación a una sola propiedad, pero los ejemplos se pueden modificar para usar guiones gráficos en su lugar.</span><span class="sxs-lookup"><span data-stu-id="3b321-123">For simplicity, the code versions of this example use local animations, not storyboards, because only a single animation is being applied to a single property, but the examples may be modified to use storyboards instead.</span></span> <span data-ttu-id="3b321-124">Para obtener un ejemplo que muestra cómo declarar un guión gráfico en el código, vea [Animar una propiedad mediante un guión gráfico](how-to-animate-a-property-by-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="3b321-124">For an example showing how to declare a storyboard in code, see [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md).</span></span>

<span data-ttu-id="3b321-125">Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="3b321-125">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span> <span data-ttu-id="3b321-126">Para obtener más información acerca de las animaciones de fotogramas clave, vea Información general sobre [animaciones de fotogramas](key-frame-animations-overview.md)clave .</span><span class="sxs-lookup"><span data-stu-id="3b321-126">For more information about key frame animations, see the [Key-Frame Animations Overview](key-frame-animations-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3b321-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b321-127">See also</span></span>

- [<span data-ttu-id="3b321-128">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="3b321-128">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="3b321-129">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="3b321-129">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="3b321-130">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="3b321-130">How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
