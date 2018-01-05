---
title: "Cómo: Animar la posición y la dirección de una cámara mediante fotogramas clave"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], camera direction with key frames
- key frames [WPF], animating camera direction
- animation [WPF], camera position with key frames
- camera position [WPF], animating with key frames
- key frames [WPF], animating camera position
- camera direction [WPF], animating with key frames
ms.assetid: 5753024e-0057-454d-947f-43ea686879c7
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 06e815ddd8beb48f80f13d93604773079fcffa06
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-camera-position-and-direction-using-key-frames"></a><span data-ttu-id="3f151-102">Cómo: Animar la posición y la dirección de una cámara mediante fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="3f151-102">How to: Animate Camera Position and Direction Using Key Frames</span></span>
<span data-ttu-id="3f151-103">En el ejemplo siguiente, <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> se usa para animar la posición de un <xref:System.Windows.Media.Media3D.PerspectiveCamera> en una escena 3D.</span><span class="sxs-lookup"><span data-stu-id="3f151-103">In the following example, <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> is used to animate the position of a <xref:System.Windows.Media.Media3D.PerspectiveCamera> in a 3D scene.</span></span> <span data-ttu-id="3f151-104">Además, <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> se usa para animar la dirección en que apunta la cámara en la escena 3D.</span><span class="sxs-lookup"><span data-stu-id="3f151-104">In addition, <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> is used to animate the direction the camera is pointing in the 3D scene.</span></span> <span data-ttu-id="3f151-105">En ambas animaciones utilizan varios fotogramas clave que crean una serie de efectos de animación:</span><span class="sxs-lookup"><span data-stu-id="3f151-105">Both of these animations use several key frames which create a series of animation effects:</span></span>  
  
1.  <span data-ttu-id="3f151-106"><xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame>y <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> se utilizan para crear una interpolación lineal uniforme entre los valores.</span><span class="sxs-lookup"><span data-stu-id="3f151-106"><xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame> and <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> are used to create a smooth, linear interpolation between values.</span></span>  
  
2.  <span data-ttu-id="3f151-107"><xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame>y <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> se utilizan para crear "saltos" súbitos entre los valores (sin interpolación).</span><span class="sxs-lookup"><span data-stu-id="3f151-107"><xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame> and <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> are used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3.  <span data-ttu-id="3f151-108"><xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame>y <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> se utilizan para crear una transición variable entre los valores según el <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="3f151-108"><xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame> and <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> are used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="3f151-109">En el ejemplo siguiente, la animación se inicia lentamente, pero hacia el final del segmento de tiempo, acelera exponencialmente.</span><span class="sxs-lookup"><span data-stu-id="3f151-109">In the example below, the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f151-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3f151-110">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="3f151-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f151-111">See Also</span></span>  
 [<span data-ttu-id="3f151-112">Animar la posición y la dirección de una cámara en una escena 3D</span><span class="sxs-lookup"><span data-stu-id="3f151-112">Animate Camera Position and Direction in a 3D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-camera-position-and-direction-in-a-3d-scene.md)  
 [<span data-ttu-id="3f151-113">Información general sobre gráficos 3D</span><span class="sxs-lookup"><span data-stu-id="3f151-113">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
