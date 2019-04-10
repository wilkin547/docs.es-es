---
title: Filtrar Animar el grosor de un borde mediante fotogramas clave
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], border thickness with key frames
- key frames [WPF], animating border thickness with
- border thickness [WPF], animating with key frames
ms.assetid: 3a9cb463-0a63-407d-aae7-3fbb1a559947
ms.openlocfilehash: 101fd077bf125faadbd9a0186c2282e4b20ee78f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59301794"
---
# <a name="how-to-animate-the-thickness-of-a-border-by-using-key-frames"></a><span data-ttu-id="2907b-102">Filtrar Animar el grosor de un borde mediante fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="2907b-102">How to: Animate the Thickness of a Border by Using Key Frames</span></span>
<span data-ttu-id="2907b-103">En este ejemplo se muestra cómo animar la <xref:System.Windows.Controls.Control.BorderThickness%2A> propiedad de un <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="2907b-103">This example shows how to animate the <xref:System.Windows.Controls.Control.BorderThickness%2A> property of a <xref:System.Windows.Controls.Border>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2907b-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2907b-104">Example</span></span>  
 <span data-ttu-id="2907b-105">En el ejemplo siguiente se usa el <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> clase se va a animar el <xref:System.Windows.Controls.Control.BorderThickness%2A> propiedad de un <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="2907b-105">The following example uses the <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Controls.Control.BorderThickness%2A> property of a <xref:System.Windows.Controls.Border>.</span></span> <span data-ttu-id="2907b-106">Esta animación utiliza tres fotogramas clave de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="2907b-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="2907b-107">Durante el primer medio segundo, utiliza una instancia de la <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> clase para aumentar gradualmente el grosor del borde.</span><span class="sxs-lookup"><span data-stu-id="2907b-107">During the first half second, uses an instance of the <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> class to gradually increase the thickness of the border.</span></span> <span data-ttu-id="2907b-108">El ejemplo se utiliza <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> para crear un aumento lineal suavizado entre los valores.</span><span class="sxs-lookup"><span data-stu-id="2907b-108">The example uses <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> to create a smooth linear increase between values.</span></span>  
  
2. <span data-ttu-id="2907b-109">Al final de la siguiente medio segundo, utiliza una instancia de la <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> clase para aumentar de repente el grosor del borde.</span><span class="sxs-lookup"><span data-stu-id="2907b-109">At the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> class to suddenly increase the thickness of the border.</span></span> <span data-ttu-id="2907b-110">Los fotogramas clave discretos como los derivan de <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> crean saltos súbitos entre los valores, es decir, el movimiento de la animación es brusco.</span><span class="sxs-lookup"><span data-stu-id="2907b-110">Discrete key frames like those derived from <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
3. <span data-ttu-id="2907b-111">Durante los dos últimos segundos, utiliza una instancia de la <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> clase para reducir el grosor del borde.</span><span class="sxs-lookup"><span data-stu-id="2907b-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> class to decrease the thickness of the border.</span></span> <span data-ttu-id="2907b-112">Los fotogramas clave spline como los derivan de <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> crean una transición variable entre los valores según los valores de la <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="2907b-112">Spline key frames like those derived from <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="2907b-113">En este fotograma clave, la animación se inicia lentamente y se va acelerando de forma exponencial hacia el final del segmento temporal.</span><span class="sxs-lookup"><span data-stu-id="2907b-113">In this key frame, the animation starts off slow and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-xaml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="2907b-114">Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="2907b-114">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2907b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="2907b-115">See also</span></span>

- <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>
- [<span data-ttu-id="2907b-116">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="2907b-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="2907b-117">Temas de procedimientos de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="2907b-117">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
- [<span data-ttu-id="2907b-118">Animar el valor del grosor de un borde</span><span class="sxs-lookup"><span data-stu-id="2907b-118">Animate a BorderThickness Value</span></span>](../controls/how-to-animate-a-borderthickness-value.md)
