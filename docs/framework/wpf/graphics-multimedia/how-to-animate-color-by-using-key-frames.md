---
title: 'Cómo: Animar un color mediante fotogramas clave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [WPF], animating with key frames
- animation [WPF], colors with key frames
- key frames [WPF], animating colors with
ms.assetid: ab04ffa6-4de9-4d5b-a3b4-4e35d5b2ef35
ms.openlocfilehash: 8a444706f7541b52722ab8257a88e76c3e1b0938
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344748"
---
# <a name="how-to-animate-color-by-using-key-frames"></a><span data-ttu-id="b7cc9-102">Cómo: Animar un color mediante fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="b7cc9-102">How to: Animate Color by Using Key Frames</span></span>
<span data-ttu-id="b7cc9-103">En este ejemplo se <xref:System.Windows.Media.SolidColorBrush.Color%2A> muestra <xref:System.Windows.Media.SolidColorBrush> cómo animar la de a mediante fotogramas clave.</span><span class="sxs-lookup"><span data-stu-id="b7cc9-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> of a <xref:System.Windows.Media.SolidColorBrush> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7cc9-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b7cc9-104">Example</span></span>  
 <span data-ttu-id="b7cc9-105">En el ejemplo <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> siguiente se <xref:System.Windows.Media.SolidColorBrush.Color%2A> utiliza <xref:System.Windows.Media.SolidColorBrush>la clase para animar la propiedad de un archivo .</span><span class="sxs-lookup"><span data-stu-id="b7cc9-105">The following example uses the <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> property of a <xref:System.Windows.Media.SolidColorBrush>.</span></span> <span data-ttu-id="b7cc9-106">Esta animación utiliza tres fotogramas clave de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="b7cc9-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="b7cc9-107">Durante los dos primeros segundos, <xref:System.Windows.Media.Animation.LinearColorKeyFrame> utiliza una instancia de la clase para cambiar gradualmente el color de verde a rojo.</span><span class="sxs-lookup"><span data-stu-id="b7cc9-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearColorKeyFrame> class to gradually change the color from green to red.</span></span> <span data-ttu-id="b7cc9-108">Los fotogramas <xref:System.Windows.Media.Animation.LinearColorKeyFrame> clave lineales como crean una transición lineal suave entre los valores.</span><span class="sxs-lookup"><span data-stu-id="b7cc9-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearColorKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="b7cc9-109">Durante el final del siguiente medio segundo, <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> utiliza una instancia de la clase para cambiar rápidamente el color de rojo a amarillo.</span><span class="sxs-lookup"><span data-stu-id="b7cc9-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> class to quickly change the color from red to yellow.</span></span> <span data-ttu-id="b7cc9-110">Los fotogramas <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> clave discretos como crear cambios repentinos entre los valores, es decir, el cambio de color en esta parte de la animación se produce rápidamente y no es sutil.</span><span class="sxs-lookup"><span data-stu-id="b7cc9-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> create sudden changes between values, that is, the color change in this part of the animation occurs quickly and is not subtle.</span></span>  
  
3. <span data-ttu-id="b7cc9-111">Durante los dos segundos finales, utiliza una instancia de la <xref:System.Windows.Media.Animation.SplineColorKeyFrame> clase para cambiar el color de nuevo, esta vez de amarillo a verde.</span><span class="sxs-lookup"><span data-stu-id="b7cc9-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame> class to change the color again—this time from yellow back to green.</span></span> <span data-ttu-id="b7cc9-112">Los fotogramas <xref:System.Windows.Media.Animation.SplineColorKeyFrame> clave de spline como crean una <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> transición variable entre los valores según los valores de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b7cc9-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineColorKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="b7cc9-113">En este ejemplo, el cambio de color comienza despacio y se acelera exponencialmente hacia el final del segmento temporal.</span><span class="sxs-lookup"><span data-stu-id="b7cc9-113">In this example, the change in color begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="b7cc9-114">Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="b7cc9-114">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7cc9-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7cc9-115">See also</span></span>

- <xref:System.Windows.Media.SolidColorBrush.Color%2A>
- <xref:System.Windows.Media.SolidColorBrush>
- <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>
- [<span data-ttu-id="b7cc9-116">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="b7cc9-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="b7cc9-117">Temas de procedimientos de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="b7cc9-117">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
