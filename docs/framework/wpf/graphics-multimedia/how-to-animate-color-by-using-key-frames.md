---
title: "Cómo: Animar un color mediante fotogramas clave"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [WPF], animating with key frames
- animation [WPF], colors with key frames
- key frames [WPF], animating colors with
ms.assetid: ab04ffa6-4de9-4d5b-a3b4-4e35d5b2ef35
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4c6b4dc6ee04b20f47599bad84dda4648da255ca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-color-by-using-key-frames"></a><span data-ttu-id="a6c16-102">Cómo: Animar un color mediante fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="a6c16-102">How to: Animate Color by Using Key Frames</span></span>
<span data-ttu-id="a6c16-103">Este ejemplo muestra cómo animar la <xref:System.Windows.Media.SolidColorBrush.Color%2A> de un <xref:System.Windows.Media.SolidColorBrush> mediante el uso de fotogramas clave.</span><span class="sxs-lookup"><span data-stu-id="a6c16-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> of a <xref:System.Windows.Media.SolidColorBrush> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6c16-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a6c16-104">Example</span></span>  
 <span data-ttu-id="a6c16-105">En el ejemplo siguiente se usa el <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> clase para animar la <xref:System.Windows.Media.SolidColorBrush.Color%2A> propiedad de un <xref:System.Windows.Media.SolidColorBrush>.</span><span class="sxs-lookup"><span data-stu-id="a6c16-105">The following example uses the <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> property of a <xref:System.Windows.Media.SolidColorBrush>.</span></span> <span data-ttu-id="a6c16-106">Esta animación utiliza tres fotogramas clave de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="a6c16-106">This animation uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="a6c16-107">Durante los primeros dos segundos, utiliza una instancia de la <xref:System.Windows.Media.Animation.LinearColorKeyFrame> clase cambian gradualmente el color de verde a rojo.</span><span class="sxs-lookup"><span data-stu-id="a6c16-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearColorKeyFrame> class to gradually change the color from green to red.</span></span> <span data-ttu-id="a6c16-108">Al igual que los fotogramas clave lineales <xref:System.Windows.Media.Animation.LinearColorKeyFrame> crear una transición lineal suave entre valores.</span><span class="sxs-lookup"><span data-stu-id="a6c16-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearColorKeyFrame> create a smooth linear transition between values.</span></span>  
  
2.  <span data-ttu-id="a6c16-109">Durante el final de la siguiente medio segundo, utiliza una instancia de la <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> clase para cambiar rápidamente el color de rojo a amarillo.</span><span class="sxs-lookup"><span data-stu-id="a6c16-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> class to quickly change the color from red to yellow.</span></span> <span data-ttu-id="a6c16-110">Los fotogramas clave discretos como <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> crear cambios bruscos entre valores, es decir, el cambio de color en esta parte de la animación se produce con rapidez y no es sutil.</span><span class="sxs-lookup"><span data-stu-id="a6c16-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> create sudden changes between values, that is, the color change in this part of the animation occurs quickly and is not subtle.</span></span>  
  
3.  <span data-ttu-id="a6c16-111">Durante los últimos dos segundos, utiliza una instancia de la <xref:System.Windows.Media.Animation.SplineColorKeyFrame> clase para cambiar el color de nuevo, esta vez de amarillo a verde.</span><span class="sxs-lookup"><span data-stu-id="a6c16-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame> class to change the color again—this time from yellow back to green.</span></span> <span data-ttu-id="a6c16-112">Al igual que los fotogramas clave spline <xref:System.Windows.Media.Animation.SplineColorKeyFrame> crear una transición variable entre los valores según los valores de la <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="a6c16-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineColorKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="a6c16-113">En este ejemplo, el cambio de color comienza despacio y se acelera exponencialmente hacia el final del segmento temporal.</span><span class="sxs-lookup"><span data-stu-id="a6c16-113">In this example, the change in color begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="a6c16-114">Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](http://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="a6c16-114">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6c16-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6c16-115">See Also</span></span>  
 <xref:System.Windows.Media.SolidColorBrush.Color%2A>  
 <xref:System.Windows.Media.SolidColorBrush>  
 <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>  
 [<span data-ttu-id="a6c16-116">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="a6c16-116">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="a6c16-117">Temas de procedimientos de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="a6c16-117">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
