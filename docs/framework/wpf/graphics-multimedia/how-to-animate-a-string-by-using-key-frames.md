---
title: 'Cómo: Animar una cadena mediante fotogramas clave'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], strings with key frames
- strings [WPF], animating with key frames
- key frames [WPF], animating strings with
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
ms.openlocfilehash: c954806ca901bbfc3ab6d4bbcc237cd0e404f154
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344669"
---
# <a name="how-to-animate-a-string-by-using-key-frames"></a><span data-ttu-id="b3833-102">Cómo: Animar una cadena mediante fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="b3833-102">How to: Animate a String by Using Key Frames</span></span>
<span data-ttu-id="b3833-103">En este ejemplo se muestra cómo animar una <xref:System.Windows.Controls.ContentControl.Content%2A> cadena, <xref:System.Windows.Controls.Button> que en este ejemplo es la propiedad de un control, mediante marcos de clave.</span><span class="sxs-lookup"><span data-stu-id="b3833-103">This example shows how to animate a string, which in this example is the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3833-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b3833-104">Example</span></span>  
 <span data-ttu-id="b3833-105">En el ejemplo <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> siguiente se <xref:System.Windows.Controls.ContentControl.Content%2A> utiliza <xref:System.Windows.Controls.Button>la clase para animar la propiedad de un archivo .</span><span class="sxs-lookup"><span data-stu-id="b3833-105">The following example uses the <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="b3833-106">Todos los fotogramas clave de este <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> ejemplo utilizan una instancia de la clase porque una animación de cadena que se crea con fotogramas clave solo puede utilizar fotogramas clave discretos.</span><span class="sxs-lookup"><span data-stu-id="b3833-106">All the key frames in this example use an instance of the <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> class because a string animation that is created with key frames can only use discrete key frames.</span></span> <span data-ttu-id="b3833-107">Los fotogramas <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> clave discretos como crear saltos repentinos entre valores, es decir, los cambios en la animación se producen rápidamente y no son sutiles.</span><span class="sxs-lookup"><span data-stu-id="b3833-107">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> create sudden jumps between values, that is, changes to the animation occur quickly and are not subtle.</span></span>  
  
 [!code-xaml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="b3833-108">Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="b3833-108">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3833-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3833-109">See also</span></span>

- <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.ContentControl.Content%2A>
- <xref:System.Windows.Controls.Button>
- <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>
- [<span data-ttu-id="b3833-110">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="b3833-110">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="b3833-111">Temas de procedimientos de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="b3833-111">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
