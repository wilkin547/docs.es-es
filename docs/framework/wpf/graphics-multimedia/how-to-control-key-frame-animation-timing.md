---
title: 'Cómo: Controlar la temporización de animaciones y fotogramas clave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], timing
- timing key-fram animation
ms.assetid: b059216f-7d4b-4ca8-a019-bc287ee7bf16
ms.openlocfilehash: d65bf6f7643adf1d98d468853ae8017a4a6554ac
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44086198"
---
# <a name="how-to-control-key-frame-animation-timing"></a><span data-ttu-id="db24c-102">Cómo: Controlar la temporización de animaciones y fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="db24c-102">How to: Control Key-Frame Animation Timing</span></span>
<span data-ttu-id="db24c-103">En este ejemplo se muestra cómo controlar la temporización de fotogramas clave dentro de una animación de fotogramas clave.</span><span class="sxs-lookup"><span data-stu-id="db24c-103">This example shows how to control the timing of key frames within a key-frame animation.</span></span> <span data-ttu-id="db24c-104">Al igual que otras animaciones, animaciones de fotogramas clave tienen una <xref:System.Windows.Media.Animation.Timeline.Duration%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="db24c-104">Like other animations, key-frame animations have a <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property.</span></span> <span data-ttu-id="db24c-105">Además de especificar la duración de una animación, deberá especificar qué parte de esa duración se asigna a cada uno de los fotogramas clave.</span><span class="sxs-lookup"><span data-stu-id="db24c-105">In addition to specifying the duration of an animation, you need to specify what part of that duration is allotted to each of its key frames.</span></span> <span data-ttu-id="db24c-106">Para asignar el tiempo, especifica un <xref:System.Windows.Media.Animation.KeyTime> para cada fotograma clave en la animación.</span><span class="sxs-lookup"><span data-stu-id="db24c-106">To allot the time, you specify a <xref:System.Windows.Media.Animation.KeyTime> for each key frame in the animation.</span></span>  
  
 <span data-ttu-id="db24c-107">El <xref:System.Windows.Media.Animation.KeyTime> para cada fotograma clave especifica cuando finaliza (no especificar el período de tiempo se reproduce un fotograma clave).</span><span class="sxs-lookup"><span data-stu-id="db24c-107">The <xref:System.Windows.Media.Animation.KeyTime> for each key frame specifies when a key frame ends (it does not specify the length of time a key frame plays).</span></span> <span data-ttu-id="db24c-108">Puede especificar un <xref:System.Windows.Media.Animation.KeyTime> como un <xref:System.TimeSpan> valor, como un porcentaje o como el <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> o <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> valor especial.</span><span class="sxs-lookup"><span data-stu-id="db24c-108">You can specify a <xref:System.Windows.Media.Animation.KeyTime> as a <xref:System.TimeSpan> value, as a percentage, or as the <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> or <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> special value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db24c-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="db24c-109">Example</span></span>  
 <span data-ttu-id="db24c-110">En el ejemplo siguiente se usa un <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> para animar un rectángulo en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="db24c-110">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> to animate a rectangle across the screen.</span></span> <span data-ttu-id="db24c-111">Los tiempos clave de los fotogramas clave se establecen con <xref:System.TimeSpan> valores.</span><span class="sxs-lookup"><span data-stu-id="db24c-111">The key frames' key times are set with <xref:System.TimeSpan> values.</span></span>  
  
 [!code-csharp[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimestimespanexample)]
 [!code-vb[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimestimespanexample)]
 [!code-xaml[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimestimespanexample)]  
  
 <span data-ttu-id="db24c-112">La siguiente ilustración se muestra cuando se alcanza el valor de cada fotograma clave.</span><span class="sxs-lookup"><span data-stu-id="db24c-112">The following illustration shows when the value of each key frame is reached.</span></span>  
  
 <span data-ttu-id="db24c-113">![Los valores de clave se alcanzan a 3, 4 y 10 segundos](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span><span class="sxs-lookup"><span data-stu-id="db24c-113">![Key values are reached at 3, 4, and 10 seconds](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span></span>  
  
 <span data-ttu-id="db24c-114">El ejemplo siguiente muestra una animación que es idéntica, salvo que los tiempos clave de los fotogramas clave se establecen con valores de porcentaje.</span><span class="sxs-lookup"><span data-stu-id="db24c-114">The next example shows an animation that is identical, except that the key frames' key times are set with percentage values.</span></span>  
  
 [!code-csharp[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespercentageexample)]
 [!code-vb[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespercentageexample)]
 [!code-xaml[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespercentageexample)]  
  
 <span data-ttu-id="db24c-115">La siguiente ilustración se muestra cuando se alcanza el valor de cada fotograma clave.</span><span class="sxs-lookup"><span data-stu-id="db24c-115">The following illustration shows when the value of each key frame is reached.</span></span>  
  
 <span data-ttu-id="db24c-116">![Los valores de clave se alcanzan a 3, 4 y 10 segundos](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span><span class="sxs-lookup"><span data-stu-id="db24c-116">![Key values are reached at 3, 4, and 10 seconds](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span></span>  
  
 <span data-ttu-id="db24c-117">El ejemplo siguiente se usa <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> tiempo valores de clave.</span><span class="sxs-lookup"><span data-stu-id="db24c-117">The next example uses <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> key time values.</span></span>  
  
 [!code-csharp[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimesuniformexample)]
 [!code-vb[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimesuniformexample)]
 [!code-xaml[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimesuniformexample)]  
  
 <span data-ttu-id="db24c-118">La siguiente ilustración se muestra cuando se alcanza el valor de cada fotograma clave.</span><span class="sxs-lookup"><span data-stu-id="db24c-118">The following illustration shows when the value of each key frame is reached.</span></span>  
  
 <span data-ttu-id="db24c-119">![Los valores de clave se alcanzan en 3.3,6.6, 6.6 y 9.9 segundos](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span><span class="sxs-lookup"><span data-stu-id="db24c-119">![Key values are reached at 3.3,6.6, and 9.9 seconds](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span></span>  
  
 <span data-ttu-id="db24c-120">El último ejemplo utiliza <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> tiempo valores de clave.</span><span class="sxs-lookup"><span data-stu-id="db24c-120">The final example uses <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> key time values.</span></span>  
  
 [!code-csharp[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespacedexample)]
 [!code-vb[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespacedexample)]
 [!code-xaml[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespacedexample)]  
  
 <span data-ttu-id="db24c-121">La siguiente ilustración se muestra cuando se alcanza el valor de cada fotograma clave.</span><span class="sxs-lookup"><span data-stu-id="db24c-121">The following illustration shows when the value of each key frame is reached.</span></span>  
  
 <span data-ttu-id="db24c-122">![Los valores de clave se alcanzan a 0, 5 y 10 segundos](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span><span class="sxs-lookup"><span data-stu-id="db24c-122">![Key values are reached at 0, 5, and 10 seconds](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span></span>  
  
 <span data-ttu-id="db24c-123">Por motivos de simplicidad, las versiones de código de este ejemplo usan animaciones locales, no guiones gráficos, porque se aplica solo a una animación única a una sola propiedad, pero se pueden modificar los ejemplos para usar guiones gráficos en su lugar.</span><span class="sxs-lookup"><span data-stu-id="db24c-123">For simplicity, the code versions of this example use local animations, not storyboards, because only a single animation is being applied to a single property, but the examples may be modified to use storyboards instead.</span></span> <span data-ttu-id="db24c-124">Para obtener un ejemplo que muestra cómo declarar un guión gráfico en el código, consulte [animar una propiedad utilizando un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="db24c-124">For an example showing how to declare a storyboard in code, see [Animate a Property by Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).</span></span>  
  
 <span data-ttu-id="db24c-125">Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="db24c-125">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span> <span data-ttu-id="db24c-126">Para obtener más información acerca de las animaciones de fotogramas clave, consulte el [información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span><span class="sxs-lookup"><span data-stu-id="db24c-126">For more information about key frame animations, see the [Key-Frame Animations Overview](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db24c-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="db24c-127">See Also</span></span>  
 [<span data-ttu-id="db24c-128">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="db24c-128">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="db24c-129">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="db24c-129">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="db24c-130">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="db24c-130">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
