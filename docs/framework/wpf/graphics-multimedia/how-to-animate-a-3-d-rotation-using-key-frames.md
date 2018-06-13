---
title: 'Cómo: Animar un giro 3D mediante fotogramas clave'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3-D translations [WPF], with key frames (Rotation3DAnimation)
- key frames [WPF], Rotation3DAnimation
- 3-D translations [WPF], animating [WPF], with key frames (Rotation3DAnimation)
ms.assetid: 6f671b95-7f30-4836-9a4f-aeb7dc30121f
ms.openlocfilehash: 085b2da20410d53fce6099131bf07249bde3209c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557630"
---
# <a name="how-to-animate-a-3-d-rotation-using-key-frames"></a><span data-ttu-id="a475c-102">Cómo: Animar un giro 3D mediante fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="a475c-102">How to: Animate a 3-D Rotation Using Key Frames</span></span>
<span data-ttu-id="a475c-103">En el ejemplo siguiente, <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> se usa para hacer girar mientras su eje de rotación anima resultante en una "oscilante" un objeto 3D.</span><span class="sxs-lookup"><span data-stu-id="a475c-103">In the following example, <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> is used to make a 3D object rotate while its axis of rotation animates resulting in a "wobble".</span></span> <span data-ttu-id="a475c-104">Esta animación usa los fotogramas clave siguientes:</span><span class="sxs-lookup"><span data-stu-id="a475c-104">This animation uses the following key frames:</span></span>  
  
1.  <span data-ttu-id="a475c-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> se utiliza para crear una interpolación lineal uniforme entre los valores.</span><span class="sxs-lookup"><span data-stu-id="a475c-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> is used to create a smooth, linear interpolation between values.</span></span>  
  
2.  <span data-ttu-id="a475c-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> se utiliza para crear "saltos" súbitos entre los valores (sin interpolación).</span><span class="sxs-lookup"><span data-stu-id="a475c-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> is used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3.  <span data-ttu-id="a475c-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> se utiliza para crear una transición variable entre los valores según el <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="a475c-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> is used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="a475c-108">En el ejemplo siguiente, esta parte de la animación se inicia lentamente, pero hacia el final del segmento de tiempo, acelera exponencialmente.</span><span class="sxs-lookup"><span data-stu-id="a475c-108">In the example below, this part of the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a475c-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a475c-109">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#Rotation3DAnimationUsingKeyFramesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotation3DAnimationUsingKeyFramesExample.xaml#rotation3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="a475c-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="a475c-110">See Also</span></span>  
 [<span data-ttu-id="a475c-111">Información general sobre gráficos 3D</span><span class="sxs-lookup"><span data-stu-id="a475c-111">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [<span data-ttu-id="a475c-112">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="a475c-112">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="a475c-113">Animar un giro 3D mediante Storyboards</span><span class="sxs-lookup"><span data-stu-id="a475c-113">Animate a 3-D Rotation Using Storyboards</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-storyboards.md)  
 [<span data-ttu-id="a475c-114">Animar un giro 3D mediante Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="a475c-114">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)  
 [<span data-ttu-id="a475c-115">Animar un giro 3D mediante cuaterniones</span><span class="sxs-lookup"><span data-stu-id="a475c-115">Animate a 3-D Rotation Using Quaternions</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-quaternions.md)  
 [<span data-ttu-id="a475c-116">Animar un giro 3D mediante fotogramas clave (QuaternionAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="a475c-116">Animate a 3-D Rotation Using Key Frames (QuaternionAnimationUsingKeyFrames)</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animate-a-3-d-rotation-quaternionanimationusingkeyframes.md)
