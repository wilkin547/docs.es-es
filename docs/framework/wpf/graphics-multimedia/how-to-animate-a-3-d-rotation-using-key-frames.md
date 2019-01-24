---
title: Procedimiento Animar un giro 3D mediante fotogramas clave
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3-D translations [WPF], with key frames (Rotation3DAnimation)
- key frames [WPF], Rotation3DAnimation
- 3-D translations [WPF], animating [WPF], with key frames (Rotation3DAnimation)
ms.assetid: 6f671b95-7f30-4836-9a4f-aeb7dc30121f
ms.openlocfilehash: 129b672411edf03dc5b98d1568c49704e66bea25
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663640"
---
# <a name="how-to-animate-a-3-d-rotation-using-key-frames"></a><span data-ttu-id="c2e0f-102">Procedimiento Animar un giro 3D mediante fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="c2e0f-102">How to: Animate a 3-D Rotation Using Key Frames</span></span>
<span data-ttu-id="c2e0f-103">En el ejemplo siguiente, <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> se usa para hacer girar mientras su eje de rotación resultante en un "oscilante" anima un objeto 3D.</span><span class="sxs-lookup"><span data-stu-id="c2e0f-103">In the following example, <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> is used to make a 3D object rotate while its axis of rotation animates resulting in a "wobble".</span></span> <span data-ttu-id="c2e0f-104">Esta animación usa los fotogramas clave siguientes:</span><span class="sxs-lookup"><span data-stu-id="c2e0f-104">This animation uses the following key frames:</span></span>  
  
1.  <span data-ttu-id="c2e0f-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> se usa para crear una interpolación lineal suave entre valores.</span><span class="sxs-lookup"><span data-stu-id="c2e0f-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> is used to create a smooth, linear interpolation between values.</span></span>  
  
2.  <span data-ttu-id="c2e0f-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> se usa para crear "saltos" súbitos entre los valores (sin interpolación).</span><span class="sxs-lookup"><span data-stu-id="c2e0f-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> is used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3.  <span data-ttu-id="c2e0f-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> se utiliza para crear una transición variable entre los valores según el <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="c2e0f-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> is used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="c2e0f-108">En el ejemplo siguiente, esta parte de la animación se inicia lentamente, pero hacia el final del segmento temporal, se acelera exponencialmente.</span><span class="sxs-lookup"><span data-stu-id="c2e0f-108">In the example below, this part of the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2e0f-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c2e0f-109">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#Rotation3DAnimationUsingKeyFramesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotation3DAnimationUsingKeyFramesExample.xaml#rotation3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="c2e0f-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="c2e0f-110">See also</span></span>
- [<span data-ttu-id="c2e0f-111">Información general sobre gráficos 3D</span><span class="sxs-lookup"><span data-stu-id="c2e0f-111">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
- [<span data-ttu-id="c2e0f-112">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="c2e0f-112">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)
- [<span data-ttu-id="c2e0f-113">Animar un giro 3D mediante Storyboards</span><span class="sxs-lookup"><span data-stu-id="c2e0f-113">Animate a 3-D Rotation Using Storyboards</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="c2e0f-114">Animar un giro 3D mediante Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="c2e0f-114">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [<span data-ttu-id="c2e0f-115">Animar un giro 3D mediante cuaterniones</span><span class="sxs-lookup"><span data-stu-id="c2e0f-115">Animate a 3-D Rotation Using Quaternions</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-quaternions.md)
- [<span data-ttu-id="c2e0f-116">Animar un giro 3D mediante fotogramas clave (QuaternionAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="c2e0f-116">Animate a 3-D Rotation Using Key Frames (QuaternionAnimationUsingKeyFrames)</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animate-a-3-d-rotation-quaternionanimationusingkeyframes.md)
