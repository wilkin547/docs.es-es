---
title: 'Cómo: Animar una rotación 3D mediante fotogramas clave (QuaternionAnimationUsingKeyFrames)'
ms.date: 03/30/2017
helpviewer_keywords:
- 3D translations [WPF], animating [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
- key frames [WPF], QuaternionAnimationUsingKeyFrames
- animation [WPF], 3D translations [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
ms.assetid: 09e5707b-7523-4a08-9aa7-bb13cbedccdf
ms.openlocfilehash: 5273183aaa49a743cc401dec0b4b16bae09e3129
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112302"
---
# <a name="how-to-animate-a-3d-rotation-using-key-frames-quaternionanimationusingkeyframes"></a><span data-ttu-id="07653-102">Cómo: Animar una rotación 3D mediante fotogramas clave (QuaternionAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="07653-102">How to: Animate a 3D Rotation Using Key Frames (QuaternionAnimationUsingKeyFrames)</span></span>
<span data-ttu-id="07653-103">En el ejemplo <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> siguiente, se utiliza para hacer que un objeto 3D gire.</span><span class="sxs-lookup"><span data-stu-id="07653-103">In the following example, <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> is used to make a 3D object rotate.</span></span> <span data-ttu-id="07653-104">Esta animación utiliza los siguientes fotogramas clave:</span><span class="sxs-lookup"><span data-stu-id="07653-104">This animation uses the following key frames:</span></span>  
  
1. <span data-ttu-id="07653-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame>se utiliza para crear una interpolación lineal suave entre los valores.</span><span class="sxs-lookup"><span data-stu-id="07653-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> is used to create a smooth, linear interpolation between values.</span></span>  
  
2. <span data-ttu-id="07653-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame>se utiliza para crear "saltos" repentinos entre los valores (sin interpolación).</span><span class="sxs-lookup"><span data-stu-id="07653-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> is used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3. <span data-ttu-id="07653-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame>se utiliza para crear una transición <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> variable entre valores dependiendo de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="07653-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> is used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="07653-108">En el ejemplo siguiente, esta parte de la animación comienza lentamente, pero hacia el final del segmento de tiempo, se acelera exponencialmente.</span><span class="sxs-lookup"><span data-stu-id="07653-108">In the example below, this part of the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07653-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="07653-109">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationUsingKeyFramesExample.xaml#quaternionanimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="07653-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="07653-110">See also</span></span>

- [<span data-ttu-id="07653-111">Animar una rotación 3D mediante guiones gráficos</span><span class="sxs-lookup"><span data-stu-id="07653-111">Animate a 3D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="07653-112">Animar una rotación 3D mediante Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="07653-112">Animate a 3D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [<span data-ttu-id="07653-113">Animar una rotación 3D con cuaterniones</span><span class="sxs-lookup"><span data-stu-id="07653-113">Animate a 3D Rotation Using Quaternions</span></span>](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [<span data-ttu-id="07653-114">Animar una rotación 3D mediante fotogramas clave (Rotation3DAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="07653-114">Animate a 3D Rotation Using Key Frames (Rotation3DAnimationUsingKeyFrames)</span></span>](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [<span data-ttu-id="07653-115">Descripción general de los gráficos 3D</span><span class="sxs-lookup"><span data-stu-id="07653-115">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="07653-116">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="07653-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
