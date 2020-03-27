---
title: 'Cómo: Animar un objeto Boolean mediante fotogramas clave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Booleans [WPF], animating with key frames
- animation [WPF], Booleans with key frames
- key frames [WPF], animating Booleans with
ms.assetid: 4b0fac96-6231-4fcf-9775-4dd673ddc785
ms.openlocfilehash: 35704996dcf21fe463169dc13572941bcd8fbad1
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344932"
---
# <a name="how-to-animate-a-boolean-by-using-key-frames"></a><span data-ttu-id="8823f-102">Cómo: Animar un objeto Boolean mediante fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="8823f-102">How to: Animate a Boolean by Using Key Frames</span></span>
<span data-ttu-id="8823f-103">En este ejemplo se muestra cómo <xref:System.Windows.Controls.Button> animar el valor de propiedad booleana de un control mediante fotogramas clave.</span><span class="sxs-lookup"><span data-stu-id="8823f-103">This example shows how to animate the Boolean property value of a <xref:System.Windows.Controls.Button> control by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8823f-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8823f-104">Example</span></span>  
 <span data-ttu-id="8823f-105">En el ejemplo <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames> siguiente se <xref:System.Windows.UIElement.IsEnabled%2A> utiliza <xref:System.Windows.Controls.Button> la clase para animar la propiedad de un control.</span><span class="sxs-lookup"><span data-stu-id="8823f-105">The following example uses the <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames> class to animate the <xref:System.Windows.UIElement.IsEnabled%2A> property of a <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="8823f-106">Todos los fotogramas clave de este <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> ejemplo utilizan una instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="8823f-106">All the key frames in this example use an instance of the <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> class.</span></span> <span data-ttu-id="8823f-107">Los fotogramas <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> clave discretos como crear saltos repentinos entre valores, es decir, el movimiento de la animación es desigual.</span><span class="sxs-lookup"><span data-stu-id="8823f-107">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-csharp[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/BooleanAnimationUsingKeyFramesExample.cs#booleananimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/booleananimationusingkeyframesexample.vb#booleananimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/BooleanAnimationUsingKeyFramesExample.xaml#booleananimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="8823f-108">Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="8823f-108">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8823f-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="8823f-109">See also</span></span>

- <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>
- <xref:System.Windows.UIElement.IsEnabled%2A>
- <xref:System.Windows.Controls.Button>
- [<span data-ttu-id="8823f-110">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="8823f-110">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="8823f-111">Temas de procedimientos de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="8823f-111">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
