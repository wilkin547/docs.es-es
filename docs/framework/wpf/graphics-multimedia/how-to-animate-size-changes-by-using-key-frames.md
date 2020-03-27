---
title: 'Cómo: Animar los cambios de tamaño mediante fotogramas clave'
ms.date: 03/30/2017
helpviewer_keywords:
- key frames [WPF], animating size changes with
- animation [WPF], size changes with key frames
- size changes [WPF], animating with key frames
ms.assetid: 86bd2950-d4c9-4ec4-aa8d-7dc3ccadded4
ms.openlocfilehash: 42cecfc9df4304be4033ea39edc0517016de4a92
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344661"
---
# <a name="how-to-animate-size-changes-by-using-key-frames"></a><span data-ttu-id="7a1bc-102">Cómo: Animar los cambios de tamaño mediante fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="7a1bc-102">How to: Animate Size Changes by Using Key Frames</span></span>
<span data-ttu-id="7a1bc-103">En este ejemplo se muestra cómo animar los cambios del tamaño mediante fotogramas clave.</span><span class="sxs-lookup"><span data-stu-id="7a1bc-103">This example shows how to animate size changes by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a1bc-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7a1bc-104">Example</span></span>  
 <span data-ttu-id="7a1bc-105">En el ejemplo <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> siguiente se <xref:System.Windows.Media.ArcSegment.Size%2A> utiliza <xref:System.Windows.Media.ArcSegment>la clase para animar la propiedad de un archivo .</span><span class="sxs-lookup"><span data-stu-id="7a1bc-105">The following example uses the <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.ArcSegment.Size%2A> property of an <xref:System.Windows.Media.ArcSegment>.</span></span> <span data-ttu-id="7a1bc-106">Esta animación utiliza tres fotogramas clave de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="7a1bc-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="7a1bc-107">Durante el primer medio segundo de la <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> animación, utiliza una instancia de la clase para aumentar gradualmente el tamaño del arco. Los fotogramas <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> clave lineales como crean una transición lineal suave entre los valores.</span><span class="sxs-lookup"><span data-stu-id="7a1bc-107">During the first half second of the animation, uses an instance of the <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> class to gradually increase the size of the arc. Linear key frames like <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="7a1bc-108">Al final del siguiente medio segundo, utiliza <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> una instancia de la clase para aumentar repentinamente el tamaño del arco. Los fotogramas <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> clave discretos como crear saltos repentinos entre valores, es decir, los cambios de tamaño se producen repentinamente y no son sutiles.</span><span class="sxs-lookup"><span data-stu-id="7a1bc-108">At the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> class to suddenly increase the size of the arc. Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> create sudden jumps between values, that is, the size changes occur suddenly and are not subtle.</span></span>  
  
3. <span data-ttu-id="7a1bc-109">Durante los últimos dos segundos, utiliza una instancia de la <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> clase para aumentar el tamaño del arco. Los fotogramas <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> clave de spline como crean una <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> transición variable entre los valores según los valores de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="7a1bc-109">Over the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> class to increase the size of the arc. Spline key frames like <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="7a1bc-110">En este ejemplo, el tamaño del arco aumenta lentamente al principio y va aumentando exponencialmente hacia el final del segmento temporal.</span><span class="sxs-lookup"><span data-stu-id="7a1bc-110">In this example, the size of the arc increases slowly at first and then increases exponentially toward the end of the time segment.</span></span>  
  
 [!code-xaml[keyframes_snip#SizeAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/SizeAnimationUsingKeyFramesExample.xaml#sizeanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="7a1bc-111">Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="7a1bc-111">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a1bc-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a1bc-112">See also</span></span>

- <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>
- <xref:System.Windows.Media.ArcSegment.Size%2A>
- <xref:System.Windows.Media.ArcSegment>
- <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>
- <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>
- [<span data-ttu-id="7a1bc-113">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="7a1bc-113">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="7a1bc-114">Temas de procedimientos de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="7a1bc-114">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
