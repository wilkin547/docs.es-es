---
title: Filtrar Animar un giro 3D mediante fotogramas clave (QuaternionAnimationUsingKeyFrames)
ms.date: 03/30/2017
helpviewer_keywords:
- 3-D translations [WPF], animating [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
- key frames [WPF], QuaternionAnimationUsingKeyFrames
- animation [WPF], 3-D translations [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
ms.assetid: 09e5707b-7523-4a08-9aa7-bb13cbedccdf
ms.openlocfilehash: f0b46e488f5f0ff0a918d7766998528fef001794
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59100111"
---
# <a name="how-to-animate-a-3-d-rotation-using-key-frames-quaternionanimationusingkeyframes"></a><span data-ttu-id="d662f-102">Filtrar Animar un giro 3D mediante fotogramas clave (QuaternionAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="d662f-102">How to: Animate a 3-D Rotation Using Key Frames (QuaternionAnimationUsingKeyFrames)</span></span>
<span data-ttu-id="d662f-103">En el ejemplo siguiente, <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> se usa para hacer girar un objeto 3D.</span><span class="sxs-lookup"><span data-stu-id="d662f-103">In the following example, <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> is used to make a 3D object rotate.</span></span> <span data-ttu-id="d662f-104">Esta animación usa los fotogramas clave siguientes:</span><span class="sxs-lookup"><span data-stu-id="d662f-104">This animation uses the following key frames:</span></span>  
  
1.  <xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> <span data-ttu-id="d662f-105">se usa para crear una interpolación lineal suave entre valores.</span><span class="sxs-lookup"><span data-stu-id="d662f-105">is used to create a smooth, linear interpolation between values.</span></span>  
  
2.  <xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> <span data-ttu-id="d662f-106">se usa para crear "saltos" súbitos entre los valores (sin interpolación).</span><span class="sxs-lookup"><span data-stu-id="d662f-106">is used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3.  <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> <span data-ttu-id="d662f-107">se utiliza para crear una transición variable entre los valores según el <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="d662f-107">is used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="d662f-108">En el ejemplo siguiente, esta parte de la animación se inicia lentamente, pero hacia el final del segmento temporal, se acelera exponencialmente.</span><span class="sxs-lookup"><span data-stu-id="d662f-108">In the example below, this part of the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d662f-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d662f-109">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationUsingKeyFramesExample.xaml#quaternionanimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="d662f-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="d662f-110">See also</span></span>

- [<span data-ttu-id="d662f-111">Animar un giro 3D mediante Storyboards</span><span class="sxs-lookup"><span data-stu-id="d662f-111">Animate a 3-D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="d662f-112">Animar un giro 3D mediante Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="d662f-112">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [<span data-ttu-id="d662f-113">Animar un giro 3D mediante cuaterniones</span><span class="sxs-lookup"><span data-stu-id="d662f-113">Animate a 3-D Rotation Using Quaternions</span></span>](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [<span data-ttu-id="d662f-114">Animar un giro 3D mediante fotogramas clave (Rotation3DAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="d662f-114">Animate a 3-D Rotation Using Key Frames (Rotation3DAnimationUsingKeyFrames)</span></span>](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [<span data-ttu-id="d662f-115">Información general sobre gráficos 3D</span><span class="sxs-lookup"><span data-stu-id="d662f-115">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="d662f-116">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="d662f-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
