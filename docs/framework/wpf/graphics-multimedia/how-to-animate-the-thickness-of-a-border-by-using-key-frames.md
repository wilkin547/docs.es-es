---
title: "Cómo: Animar el grosor de un borde mediante fotogramas clave"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], border thickness with key frames
- key frames [WPF], animating border thickness with
- border thickness [WPF], animating with key frames
ms.assetid: 3a9cb463-0a63-407d-aae7-3fbb1a559947
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 08950b2b92bfcbd28472327f12a2ee49abfd9fed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-the-thickness-of-a-border-by-using-key-frames"></a><span data-ttu-id="01593-102">Cómo: Animar el grosor de un borde mediante fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="01593-102">How to: Animate the Thickness of a Border by Using Key Frames</span></span>
<span data-ttu-id="01593-103">Este ejemplo muestra cómo animar la <xref:System.Windows.Controls.Control.BorderThickness%2A> propiedad de un <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="01593-103">This example shows how to animate the <xref:System.Windows.Controls.Control.BorderThickness%2A> property of a <xref:System.Windows.Controls.Border>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01593-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="01593-104">Example</span></span>  
 <span data-ttu-id="01593-105">En el ejemplo siguiente se usa el <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> clase para animar la <xref:System.Windows.Controls.Control.BorderThickness%2A> propiedad de un <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="01593-105">The following example uses the <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Controls.Control.BorderThickness%2A> property of a <xref:System.Windows.Controls.Border>.</span></span> <span data-ttu-id="01593-106">Esta animación utiliza tres fotogramas clave de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="01593-106">This animation uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="01593-107">Durante el primer medio segundo, utiliza una instancia de la <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> clase para aumentar gradualmente el grosor del borde.</span><span class="sxs-lookup"><span data-stu-id="01593-107">During the first half second, uses an instance of the <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> class to gradually increase the thickness of the border.</span></span> <span data-ttu-id="01593-108">El ejemplo se utiliza <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> para crear un aumento lineal suave entre valores.</span><span class="sxs-lookup"><span data-stu-id="01593-108">The example uses <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> to create a smooth linear increase between values.</span></span>  
  
2.  <span data-ttu-id="01593-109">Al final de la siguiente medio segundo, utiliza una instancia de la <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> clase para aumentar el grosor del borde de repente.</span><span class="sxs-lookup"><span data-stu-id="01593-109">At the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> class to suddenly increase the thickness of the border.</span></span> <span data-ttu-id="01593-110">Los fotogramas clave discretos como las que se derivan de <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> crean saltos súbitos entre valores, es decir, el movimiento de la animación es irregular.</span><span class="sxs-lookup"><span data-stu-id="01593-110">Discrete key frames like those derived from <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
3.  <span data-ttu-id="01593-111">Durante los últimos dos segundos, utiliza una instancia de la <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> clase para reducir el grosor del borde.</span><span class="sxs-lookup"><span data-stu-id="01593-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> class to decrease the thickness of the border.</span></span> <span data-ttu-id="01593-112">Los fotogramas clave spline como las que se derivan de <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> crear una transición variable entre los valores según los valores de la <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="01593-112">Spline key frames like those derived from <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="01593-113">En este fotograma clave, la animación se inicia lentamente y se va acelerando de forma exponencial hacia el final del segmento temporal.</span><span class="sxs-lookup"><span data-stu-id="01593-113">In this key frame, the animation starts off slow and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-xaml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="01593-114">Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](http://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="01593-114">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01593-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="01593-115">See Also</span></span>  
 <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>  
 <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>  
 <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>  
 [<span data-ttu-id="01593-116">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="01593-116">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="01593-117">Temas de procedimientos de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="01593-117">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)  
 [<span data-ttu-id="01593-118">Animar el valor del grosor de un borde</span><span class="sxs-lookup"><span data-stu-id="01593-118">Animate a BorderThickness Value</span></span>](../../../../docs/framework/wpf/controls/how-to-animate-a-borderthickness-value.md)
