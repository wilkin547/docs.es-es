---
title: "Cómo: Animar un objeto Double mediante fotogramas clave"
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
- Doubles [WPF], animating with key frames
- animation [WPF], Doubles with key frames
- key frames [WPF], animating Doubles with
ms.assetid: 3a1a7dba-7694-4907-8a2f-3408baebfa82
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e87717f6e2691142efa54a7e363f1038f8b74c1b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-double-by-using-key-frames"></a><span data-ttu-id="4c59d-102">Cómo: Animar un objeto Double mediante fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="4c59d-102">How to: Animate a Double by Using Key Frames</span></span>
<span data-ttu-id="4c59d-103">Este ejemplo muestra cómo animar el valor de una propiedad que toma un <xref:System.Double> mediante el uso de fotogramas clave.</span><span class="sxs-lookup"><span data-stu-id="4c59d-103">This example shows how to animate the value of a property that takes a <xref:System.Double> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c59d-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4c59d-104">Example</span></span>  
 <span data-ttu-id="4c59d-105">En el ejemplo siguiente se mueve un rectángulo por una pantalla.</span><span class="sxs-lookup"><span data-stu-id="4c59d-105">The following example moves a rectangle across a screen.</span></span> <span data-ttu-id="4c59d-106">El ejemplo se utiliza la <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> clase para animar la <xref:System.Windows.Media.TranslateTransform.X%2A> propiedad de un <xref:System.Windows.Media.TranslateTransform> aplicado a un <xref:System.Windows.Shapes.Rectangle>.</span><span class="sxs-lookup"><span data-stu-id="4c59d-106">The example uses the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.TranslateTransform.X%2A> property of a <xref:System.Windows.Media.TranslateTransform> applied to a <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="4c59d-107">Esta animación, que se repite indefinidamente, utiliza tres fotogramas clave de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="4c59d-107">This animation, which repeats indefinitely, uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="4c59d-108">Durante los primeros tres segundos, utiliza una instancia de la <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> clase para mover el rectángulo a lo largo de una ruta de acceso a una velocidad constante desde su posición inicial hasta la posición 500.</span><span class="sxs-lookup"><span data-stu-id="4c59d-108">During the first three seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> class to move the rectangle along a path at a steady rate from its starting position to the 500 position.</span></span> <span data-ttu-id="4c59d-109">Al igual que los fotogramas clave lineales <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> crear una transición lineal suave entre valores.</span><span class="sxs-lookup"><span data-stu-id="4c59d-109">Linear key frames like <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> create a smooth linear transition between values.</span></span>  
  
2.  <span data-ttu-id="4c59d-110">Al final del cuarto segundo, utiliza una instancia de la <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> clase para mover repentinamente el rectángulo a la posición siguiente.</span><span class="sxs-lookup"><span data-stu-id="4c59d-110">At the end of the fourth second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> class to suddenly move the rectangle to the next position.</span></span> <span data-ttu-id="4c59d-111">Los fotogramas clave discretos como <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> crear saltos súbitos entre los valores.</span><span class="sxs-lookup"><span data-stu-id="4c59d-111">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> create sudden jumps between values.</span></span> <span data-ttu-id="4c59d-112">En este ejemplo, el rectángulo está en la posición inicial y aparece de pronto en la posición 500.</span><span class="sxs-lookup"><span data-stu-id="4c59d-112">In this example, the rectangle is at the starting position and then suddenly appears at the 500 position.</span></span>  
  
3.  <span data-ttu-id="4c59d-113">En los dos últimos segundos, utiliza una instancia de la <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> clase para devolver el rectángulo a su posición inicial.</span><span class="sxs-lookup"><span data-stu-id="4c59d-113">In the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> class to move the rectangle back to its starting position.</span></span> <span data-ttu-id="4c59d-114">Al igual que los fotogramas clave spline <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> crear una transición variable entre los valores según el valor de la <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="4c59d-114">Spline key frames like <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> create a variable transition between values according to the value of the <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="4c59d-115">En este ejemplo, el rectángulo comienza a moverse despacio y se acelera exponencialmente hacia el final del segmento temporal.</span><span class="sxs-lookup"><span data-stu-id="4c59d-115">In this example, the rectangle begins by moving slowly and then speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/AltDoubleAnimationUsingKeyFramesExample.cs#altdoubleanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/altdoubleanimationusingkeyframesexample.vb#altdoubleanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/AltDoubleAnimationUsingKeyFramesExample.xaml#altdoubleanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="4c59d-116">Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](http://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="4c59d-116">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
 <span data-ttu-id="4c59d-117">Para mantener la coherencia con otros ejemplos de animación, en las versiones de código de este ejemplo utiliza un <xref:System.Windows.Media.Animation.Storyboard> objeto que se va a aplicar el <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span><span class="sxs-lookup"><span data-stu-id="4c59d-117">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span></span> <span data-ttu-id="4c59d-118">O bien, cuando se aplica una animación en código, es más fácil utilizar el <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> método en lugar de usar un <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="4c59d-118">Alternatively, when applying a single animation in code, it is simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="4c59d-119">Para obtener un ejemplo, vea [Animar una propiedad sin utilizar un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="4c59d-119">For an example, see [Animate a Property Without Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c59d-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c59d-120">See Also</span></span>  
 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>  
 <xref:System.Windows.Shapes.Rectangle>  
 <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>  
 <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>  
 <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>  
 [<span data-ttu-id="4c59d-121">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="4c59d-121">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="4c59d-122">Temas de procedimientos de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="4c59d-122">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
