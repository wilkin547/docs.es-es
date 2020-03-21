---
title: 'Cómo: Animar la posición y la dirección de una cámara mediante fotogramas clave'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], camera direction with key frames
- key frames [WPF], animating camera direction
- animation [WPF], camera position with key frames
- camera position [WPF], animating with key frames
- key frames [WPF], animating camera position
- camera direction [WPF], animating with key frames
ms.assetid: 5753024e-0057-454d-947f-43ea686879c7
ms.openlocfilehash: 28471f9b42140a6c75b043d33939503528b63194
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112172"
---
# <a name="how-to-animate-camera-position-and-direction-using-key-frames"></a><span data-ttu-id="71cdc-102">Cómo: Animar la posición y la dirección de una cámara mediante fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="71cdc-102">How to: Animate Camera Position and Direction Using Key Frames</span></span>
<span data-ttu-id="71cdc-103">En el ejemplo <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> siguiente, se utiliza <xref:System.Windows.Media.Media3D.PerspectiveCamera> para animar la posición de a en una escena 3D.</span><span class="sxs-lookup"><span data-stu-id="71cdc-103">In the following example, <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> is used to animate the position of a <xref:System.Windows.Media.Media3D.PerspectiveCamera> in a 3D scene.</span></span> <span data-ttu-id="71cdc-104">Además, <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> se utiliza para animar la dirección que apunta la cámara en la escena 3D.</span><span class="sxs-lookup"><span data-stu-id="71cdc-104">In addition, <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> is used to animate the direction the camera is pointing in the 3D scene.</span></span> <span data-ttu-id="71cdc-105">Ambas animaciones utilizan varios fotogramas clave que crean una serie de efectos de animación:</span><span class="sxs-lookup"><span data-stu-id="71cdc-105">Both of these animations use several key frames which create a series of animation effects:</span></span>  
  
1. <span data-ttu-id="71cdc-106"><xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame>y <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> se utilizan para crear una interpolación lineal suave entre los valores.</span><span class="sxs-lookup"><span data-stu-id="71cdc-106"><xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame> and <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> are used to create a smooth, linear interpolation between values.</span></span>  
  
2. <span data-ttu-id="71cdc-107"><xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame>y <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> se utilizan para crear "saltos" repentinos entre los valores (sin interpolación).</span><span class="sxs-lookup"><span data-stu-id="71cdc-107"><xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame> and <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> are used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3. <span data-ttu-id="71cdc-108"><xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame>y <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> se utilizan para crear una transición <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> variable entre los valores en función de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="71cdc-108"><xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame> and <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> are used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="71cdc-109">En el ejemplo siguiente, la animación comienza lentamente, pero hacia el final del segmento de tiempo, se acelera exponencialmente.</span><span class="sxs-lookup"><span data-stu-id="71cdc-109">In the example below, the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71cdc-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="71cdc-110">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="71cdc-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="71cdc-111">See also</span></span>

- [<span data-ttu-id="71cdc-112">Animar la posición y la dirección de una cámara en una escena 3D</span><span class="sxs-lookup"><span data-stu-id="71cdc-112">Animate Camera Position and Direction in a 3D Scene</span></span>](how-to-animate-camera-position-and-direction-in-a-3d-scene.md)
- [<span data-ttu-id="71cdc-113">Descripción general de los gráficos 3D</span><span class="sxs-lookup"><span data-stu-id="71cdc-113">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
