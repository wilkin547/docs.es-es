---
title: 'Cómo: Animar una cadena mediante fotogramas clave'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], strings with key frames
- strings [WPF], animating with key frames
- key frames [WPF], animating strings with
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
ms.openlocfilehash: 1b55afd5938073a326789e67b66fec9cfce12015
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43743825"
---
# <a name="how-to-animate-a-string-by-using-key-frames"></a><span data-ttu-id="b5ee7-102">Cómo: Animar una cadena mediante fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="b5ee7-102">How to: Animate a String by Using Key Frames</span></span>
<span data-ttu-id="b5ee7-103">En este ejemplo se muestra cómo animar una cadena, que en este ejemplo es el <xref:System.Windows.Controls.ContentControl.Content%2A> propiedad de un <xref:System.Windows.Controls.Button> control mediante fotogramas clave.</span><span class="sxs-lookup"><span data-stu-id="b5ee7-103">This example shows how to animate a string, which in this example is the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5ee7-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b5ee7-104">Example</span></span>  
 <span data-ttu-id="b5ee7-105">En el ejemplo siguiente se usa el <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> clase se va a animar el <xref:System.Windows.Controls.ContentControl.Content%2A> propiedad de un <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="b5ee7-105">The following example uses the <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="b5ee7-106">Todos los fotogramas clave en este ejemplo utilizan una instancia de la <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> clase porque una animación de cadena que se crea con fotogramas clave solo puede usar fotogramas clave discretos.</span><span class="sxs-lookup"><span data-stu-id="b5ee7-106">All the key frames in this example use an instance of the <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> class because a string animation that is created with key frames can only use discrete key frames.</span></span> <span data-ttu-id="b5ee7-107">Los fotogramas clave discretos como <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> crean saltos súbitos entre los valores, es decir, los cambios realizados en la animación se producen rápidamente y no son sutiles.</span><span class="sxs-lookup"><span data-stu-id="b5ee7-107">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> create sudden jumps between values, that is, changes to the animation occur quickly and are not subtle.</span></span>  
  
 [!code-xaml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="b5ee7-108">Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="b5ee7-108">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5ee7-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5ee7-109">See Also</span></span>  
 <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>  
 <xref:System.Windows.Controls.ContentControl.Content%2A>  
 <xref:System.Windows.Controls.Button>  
 <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>  
 [<span data-ttu-id="b5ee7-110">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="b5ee7-110">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="b5ee7-111">Temas de procedimientos de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="b5ee7-111">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
