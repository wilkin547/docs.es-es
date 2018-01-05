---
title: "Cómo: Animar un punto mediante fotogramas clave"
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
- key frames [WPF], animating Points with
- Points [WPF], animating with key frames
- animation [WPF], Points with key frames
ms.assetid: d2e2ef10-0773-4133-856e-d41c09f60ded
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4c115d31c6ace26f8fd9dd6cff3fdeead89eea33
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-point-by-using-key-frames"></a><span data-ttu-id="abe7d-102">Cómo: Animar un punto mediante fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="abe7d-102">How to: Animate a Point by Using Key Frames</span></span>
<span data-ttu-id="abe7d-103">Este ejemplo muestra cómo utilizar el <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> clase para animar un <xref:System.Windows.Point>.</span><span class="sxs-lookup"><span data-stu-id="abe7d-103">This example shows how to use the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> class to animate a <xref:System.Windows.Point>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="abe7d-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="abe7d-104">Example</span></span>  
 <span data-ttu-id="abe7d-105">En el ejemplo siguiente se mueve una elipse a lo largo de un trazado triangular.</span><span class="sxs-lookup"><span data-stu-id="abe7d-105">The following example moves an ellipse along a triangular path.</span></span> <span data-ttu-id="abe7d-106">El ejemplo se utiliza la <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> clase para animar la <xref:System.Windows.Media.EllipseGeometry.Center%2A> propiedad de un <xref:System.Windows.Media.EllipseGeometry>.</span><span class="sxs-lookup"><span data-stu-id="abe7d-106">The example uses the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.EllipseGeometry.Center%2A> property of an <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="abe7d-107">Esta animación utiliza tres fotogramas clave de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="abe7d-107">This animation uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="abe7d-108">Durante el primer medio segundo, utiliza una instancia de la <xref:System.Windows.Media.Animation.LinearPointKeyFrame> clase para mover la elipse a lo largo de una ruta de acceso a una velocidad constante desde su posición inicial.</span><span class="sxs-lookup"><span data-stu-id="abe7d-108">During the first half second, uses an instance of the <xref:System.Windows.Media.Animation.LinearPointKeyFrame> class to move the ellipse along a path at a steady rate from its starting position.</span></span> <span data-ttu-id="abe7d-109">Al igual que los fotogramas clave lineales <xref:System.Windows.Media.Animation.LinearPointKeyFrame> crean una interpolación lineal suavizada entre los valores.</span><span class="sxs-lookup"><span data-stu-id="abe7d-109">Linear key frames like <xref:System.Windows.Media.Animation.LinearPointKeyFrame> create a smooth linear interpolation between values.</span></span>  
  
2.  <span data-ttu-id="abe7d-110">Durante el final de la siguiente medio segundo, utiliza una instancia de la <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> clase para mover repentinamente la elipse a lo largo de la ruta de acceso a la siguiente posición.</span><span class="sxs-lookup"><span data-stu-id="abe7d-110">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> class to suddenly move the ellipse along the path to the next position.</span></span> <span data-ttu-id="abe7d-111">Los fotogramas clave discretos como <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> crear saltos súbitos entre los valores.</span><span class="sxs-lookup"><span data-stu-id="abe7d-111">Discrete key frames like <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> create sudden jumps between values.</span></span>  
  
3.  <span data-ttu-id="abe7d-112">Durante los últimos dos segundos, utiliza una instancia de la <xref:System.Windows.Media.Animation.SplinePointKeyFrame> clase para devolver la elipse a su posición inicial.</span><span class="sxs-lookup"><span data-stu-id="abe7d-112">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplinePointKeyFrame> class to move the ellipse back to its starting position.</span></span> <span data-ttu-id="abe7d-113">Al igual que los fotogramas clave spline <xref:System.Windows.Media.Animation.SplinePointKeyFrame> crear una transición variable entre los valores según los valores de la <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="abe7d-113">Spline key frames like <xref:System.Windows.Media.Animation.SplinePointKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="abe7d-114">En este ejemplo, la animación comienza despacio y se acelera exponencialmente hacia el final del segmento temporal.</span><span class="sxs-lookup"><span data-stu-id="abe7d-114">In this example, the animation begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/PointAnimationUsingKeyFramesExample.cs#pointanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/pointanimationusingkeyframesexample.vb#pointanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/PointAnimationUsingKeyFramesExample.xaml#pointanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="abe7d-115">Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](http://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="abe7d-115">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
 <span data-ttu-id="abe7d-116">Para mantener la coherencia con otros ejemplos de animación, en las versiones de código de este ejemplo utiliza un <xref:System.Windows.Media.Animation.Storyboard> objeto que se va a aplicar el <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>.</span><span class="sxs-lookup"><span data-stu-id="abe7d-116">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>.</span></span> <span data-ttu-id="abe7d-117">Sin embargo, al aplicar una animación única en código, es más fácil utilizar el <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> método en lugar de usar un <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="abe7d-117">However, when applying a single animation in code, it's simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="abe7d-118">Para obtener un ejemplo, vea [Animar una propiedad sin utilizar un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="abe7d-118">For an example, see [Animate a Property Without Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abe7d-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="abe7d-119">See Also</span></span>  
 <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>  
 <xref:System.Windows.Media.EllipseGeometry.Center%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Media.EllipseGeometry>  
 [<span data-ttu-id="abe7d-120">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="abe7d-120">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="abe7d-121">Temas de procedimientos de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="abe7d-121">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
