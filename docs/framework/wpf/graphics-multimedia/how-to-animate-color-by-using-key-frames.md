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
ms.openlocfilehash: cb09a54df3d99e05e89ec0f3d9f17b0e9fe78647
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43501183"
---
# <a name="how-to-animate-color-by-using-key-frames"></a><span data-ttu-id="a97c3-102">Cómo: Animar un color mediante fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="a97c3-102">How to: Animate Color by Using Key Frames</span></span>
<span data-ttu-id="a97c3-103">En este ejemplo se muestra cómo animar la <xref:System.Windows.Media.SolidColorBrush.Color%2A> de un <xref:System.Windows.Media.SolidColorBrush> mediante fotogramas clave.</span><span class="sxs-lookup"><span data-stu-id="a97c3-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> of a <xref:System.Windows.Media.SolidColorBrush> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a97c3-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a97c3-104">Example</span></span>  
 <span data-ttu-id="a97c3-105">En el ejemplo siguiente se usa el <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> clase se va a animar el <xref:System.Windows.Media.SolidColorBrush.Color%2A> propiedad de un <xref:System.Windows.Media.SolidColorBrush>.</span><span class="sxs-lookup"><span data-stu-id="a97c3-105">The following example uses the <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> property of a <xref:System.Windows.Media.SolidColorBrush>.</span></span> <span data-ttu-id="a97c3-106">Esta animación utiliza tres fotogramas clave de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="a97c3-106">This animation uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="a97c3-107">Durante los primeros dos segundos, utiliza una instancia de la <xref:System.Windows.Media.Animation.LinearColorKeyFrame> clase para cambiar gradualmente el color de verde a rojo.</span><span class="sxs-lookup"><span data-stu-id="a97c3-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearColorKeyFrame> class to gradually change the color from green to red.</span></span> <span data-ttu-id="a97c3-108">Los fotogramas clave lineales como <xref:System.Windows.Media.Animation.LinearColorKeyFrame> crean una transición lineal suave entre valores.</span><span class="sxs-lookup"><span data-stu-id="a97c3-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearColorKeyFrame> create a smooth linear transition between values.</span></span>  
  
2.  <span data-ttu-id="a97c3-109">Durante el fin de la siguiente medio segundo, utiliza una instancia de la <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> clase para cambiar rápidamente el color de rojo a amarillo.</span><span class="sxs-lookup"><span data-stu-id="a97c3-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> class to quickly change the color from red to yellow.</span></span> <span data-ttu-id="a97c3-110">Los fotogramas clave discretos como <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> crean cambios súbitos entre los valores, es decir, el cambio de color en esta parte de la animación se produce de forma rápida y brusca.</span><span class="sxs-lookup"><span data-stu-id="a97c3-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> create sudden changes between values, that is, the color change in this part of the animation occurs quickly and is not subtle.</span></span>  
  
3.  <span data-ttu-id="a97c3-111">Durante los dos últimos segundos, utiliza una instancia de la <xref:System.Windows.Media.Animation.SplineColorKeyFrame> clase vuelvan a cambiar el color, esta vez de amarillo a verde.</span><span class="sxs-lookup"><span data-stu-id="a97c3-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame> class to change the color again—this time from yellow back to green.</span></span> <span data-ttu-id="a97c3-112">Los fotogramas clave spline como <xref:System.Windows.Media.Animation.SplineColorKeyFrame> crean una transición variable entre los valores según los valores de la <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="a97c3-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineColorKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="a97c3-113">En este ejemplo, el cambio de color comienza despacio y se acelera exponencialmente hacia el final del segmento temporal.</span><span class="sxs-lookup"><span data-stu-id="a97c3-113">In this example, the change in color begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="a97c3-114">Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="a97c3-114">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a97c3-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a97c3-115">See Also</span></span>  
 <xref:System.Windows.Media.SolidColorBrush.Color%2A>  
 <xref:System.Windows.Media.SolidColorBrush>  
 <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>  
 [<span data-ttu-id="a97c3-116">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="a97c3-116">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="a97c3-117">Temas de procedimientos de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="a97c3-117">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
