---
title: 'Cómo: Animar el grosor de un borde mediante fotogramas clave'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], border thickness with key frames
- key frames [WPF], animating border thickness with
- border thickness [WPF], animating with key frames
ms.assetid: 3a9cb463-0a63-407d-aae7-3fbb1a559947
ms.openlocfilehash: 884b62e88c347449ae39caa9c028d09db39b9f4b
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344695"
---
# <a name="how-to-animate-the-thickness-of-a-border-by-using-key-frames"></a><span data-ttu-id="fce20-102">Cómo: Animar el grosor de un borde mediante fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="fce20-102">How to: Animate the Thickness of a Border by Using Key Frames</span></span>
<span data-ttu-id="fce20-103">En este ejemplo se <xref:System.Windows.Controls.Control.BorderThickness%2A> muestra <xref:System.Windows.Controls.Border>cómo animar la propiedad de un archivo .</span><span class="sxs-lookup"><span data-stu-id="fce20-103">This example shows how to animate the <xref:System.Windows.Controls.Control.BorderThickness%2A> property of a <xref:System.Windows.Controls.Border>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fce20-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fce20-104">Example</span></span>  
 <span data-ttu-id="fce20-105">En el ejemplo <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> siguiente se <xref:System.Windows.Controls.Control.BorderThickness%2A> utiliza <xref:System.Windows.Controls.Border>la clase para animar la propiedad de un archivo .</span><span class="sxs-lookup"><span data-stu-id="fce20-105">The following example uses the <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Controls.Control.BorderThickness%2A> property of a <xref:System.Windows.Controls.Border>.</span></span> <span data-ttu-id="fce20-106">Esta animación utiliza tres fotogramas clave de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="fce20-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="fce20-107">Durante el primer medio segundo, <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> utiliza una instancia de la clase para aumentar gradualmente el grosor del borde.</span><span class="sxs-lookup"><span data-stu-id="fce20-107">During the first half second, uses an instance of the <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> class to gradually increase the thickness of the border.</span></span> <span data-ttu-id="fce20-108">El ejemplo <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> se utiliza para crear un aumento lineal suave entre los valores.</span><span class="sxs-lookup"><span data-stu-id="fce20-108">The example uses <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> to create a smooth linear increase between values.</span></span>  
  
2. <span data-ttu-id="fce20-109">Al final del siguiente medio segundo, utiliza <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> una instancia de la clase para aumentar repentinamente el grosor del borde.</span><span class="sxs-lookup"><span data-stu-id="fce20-109">At the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> class to suddenly increase the thickness of the border.</span></span> <span data-ttu-id="fce20-110">Los fotogramas clave discretos como los derivados de <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> crear saltos repentinos entre los valores, es decir, el movimiento de la animación es desigual.</span><span class="sxs-lookup"><span data-stu-id="fce20-110">Discrete key frames like those derived from <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
3. <span data-ttu-id="fce20-111">Durante los dos segundos finales, utiliza una instancia de la <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> clase para disminuir el grosor del borde.</span><span class="sxs-lookup"><span data-stu-id="fce20-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> class to decrease the thickness of the border.</span></span> <span data-ttu-id="fce20-112">Los fotogramas clave de <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> spline como los derivados crean <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> una transición variable entre los valores según los valores de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="fce20-112">Spline key frames like those derived from <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="fce20-113">En este fotograma clave, la animación se inicia lentamente y se va acelerando de forma exponencial hacia el final del segmento temporal.</span><span class="sxs-lookup"><span data-stu-id="fce20-113">In this key frame, the animation starts off slow and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-xaml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="fce20-114">Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="fce20-114">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fce20-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="fce20-115">See also</span></span>

- <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>
- [<span data-ttu-id="fce20-116">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="fce20-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="fce20-117">Temas de procedimientos de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="fce20-117">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
- [<span data-ttu-id="fce20-118">Animar el valor del grosor de un borde</span><span class="sxs-lookup"><span data-stu-id="fce20-118">Animate a BorderThickness Value</span></span>](../controls/how-to-animate-a-borderthickness-value.md)
