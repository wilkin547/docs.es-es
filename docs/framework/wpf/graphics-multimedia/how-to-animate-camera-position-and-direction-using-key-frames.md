---
title: Filtrar Animar la posición y la dirección de una cámara mediante fotogramas clave
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], camera direction with key frames
- key frames [WPF], animating camera direction
- animation [WPF], camera position with key frames
- camera position [WPF], animating with key frames
- key frames [WPF], animating camera position
- camera direction [WPF], animating with key frames
ms.assetid: 5753024e-0057-454d-947f-43ea686879c7
ms.openlocfilehash: 44464cc314d649516998338e36c1b523101ac4e2
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59346085"
---
# <a name="how-to-animate-camera-position-and-direction-using-key-frames"></a><span data-ttu-id="0d0cc-102">Filtrar Animar la posición y la dirección de una cámara mediante fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="0d0cc-102">How to: Animate Camera Position and Direction Using Key Frames</span></span>
<span data-ttu-id="0d0cc-103">En el ejemplo siguiente, <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> sirve para animar la posición de un <xref:System.Windows.Media.Media3D.PerspectiveCamera> en una escena 3D.</span><span class="sxs-lookup"><span data-stu-id="0d0cc-103">In the following example, <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> is used to animate the position of a <xref:System.Windows.Media.Media3D.PerspectiveCamera> in a 3D scene.</span></span> <span data-ttu-id="0d0cc-104">Además, <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> se usa para animar la dirección señala la cámara en la escena 3D.</span><span class="sxs-lookup"><span data-stu-id="0d0cc-104">In addition, <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> is used to animate the direction the camera is pointing in the 3D scene.</span></span> <span data-ttu-id="0d0cc-105">Ambas animaciones utilizan varios fotogramas clave que crean una serie de efectos de animación:</span><span class="sxs-lookup"><span data-stu-id="0d0cc-105">Both of these animations use several key frames which create a series of animation effects:</span></span>  
  
1. <xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame> <span data-ttu-id="0d0cc-106">y <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> se utilizan para crear una interpolación lineal suave entre valores.</span><span class="sxs-lookup"><span data-stu-id="0d0cc-106">and <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> are used to create a smooth, linear interpolation between values.</span></span>  
  
2. <xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame> <span data-ttu-id="0d0cc-107">y <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> se utilizan para crear "saltos" súbitos entre los valores (sin interpolación).</span><span class="sxs-lookup"><span data-stu-id="0d0cc-107">and <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> are used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3. <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame> <span data-ttu-id="0d0cc-108">y <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> se utilizan para crear una transición variable entre los valores según el <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="0d0cc-108">and <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> are used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="0d0cc-109">En el ejemplo siguiente, la animación se inicia lentamente, pero hacia el final del segmento temporal, se acelera exponencialmente.</span><span class="sxs-lookup"><span data-stu-id="0d0cc-109">In the example below, the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d0cc-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0d0cc-110">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="0d0cc-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d0cc-111">See also</span></span>

- [<span data-ttu-id="0d0cc-112">Animar la posición y la dirección de una cámara en una escena 3D</span><span class="sxs-lookup"><span data-stu-id="0d0cc-112">Animate Camera Position and Direction in a 3D Scene</span></span>](how-to-animate-camera-position-and-direction-in-a-3d-scene.md)
- [<span data-ttu-id="0d0cc-113">Información general sobre gráficos 3D</span><span class="sxs-lookup"><span data-stu-id="0d0cc-113">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
