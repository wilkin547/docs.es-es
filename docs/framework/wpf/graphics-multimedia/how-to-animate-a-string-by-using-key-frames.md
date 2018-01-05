---
title: "Cómo: Animar una cadena mediante fotogramas clave"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], strings with key frames
- strings [WPF], animating with key frames
- key frames [WPF], animating strings with
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1692777a97754fb7f6481b2d9cb8942dcb62df77
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-string-by-using-key-frames"></a><span data-ttu-id="b23e9-102">Cómo: Animar una cadena mediante fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="b23e9-102">How to: Animate a String by Using Key Frames</span></span>
<span data-ttu-id="b23e9-103">Este ejemplo muestra cómo animar una cadena, que en este ejemplo es el <xref:System.Windows.Controls.ContentControl.Content%2A> propiedad de un <xref:System.Windows.Controls.Button> control, mediante el uso de fotogramas clave.</span><span class="sxs-lookup"><span data-stu-id="b23e9-103">This example shows how to animate a string, which in this example is the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b23e9-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b23e9-104">Example</span></span>  
 <span data-ttu-id="b23e9-105">En el ejemplo siguiente se usa el <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> clase para animar la <xref:System.Windows.Controls.ContentControl.Content%2A> propiedad de un <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="b23e9-105">The following example uses the <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="b23e9-106">Todos los fotogramas clave en este ejemplo utilizan una instancia de la <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> clase porque una animación de cadena que se crea con fotogramas clave solo puede utilizar los fotogramas clave discretos.</span><span class="sxs-lookup"><span data-stu-id="b23e9-106">All the key frames in this example use an instance of the <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> class because a string animation that is created with key frames can only use discrete key frames.</span></span> <span data-ttu-id="b23e9-107">Los fotogramas clave discretos como <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> crean saltos súbitos entre valores, es decir, los cambios en la animación se producen rápidamente y no son sutiles.</span><span class="sxs-lookup"><span data-stu-id="b23e9-107">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> create sudden jumps between values, that is, changes to the animation occur quickly and are not subtle.</span></span>  
  
 [!code-xaml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="b23e9-108">Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](http://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="b23e9-108">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b23e9-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="b23e9-109">See Also</span></span>  
 <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>  
 <xref:System.Windows.Controls.ContentControl.Content%2A>  
 <xref:System.Windows.Controls.Button>  
 <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>  
 [<span data-ttu-id="b23e9-110">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="b23e9-110">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="b23e9-111">Temas de procedimientos de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="b23e9-111">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
