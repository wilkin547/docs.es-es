---
title: 'Cómo: Animar un giro 3D mediante Storyboards'
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF]
- 3-D translations [WPF], animating [WPF], with Storyboards
- animation [WPF], 3-D translations [WPF], with Storyboards
ms.assetid: 1020e44e-e21e-49a8-be53-53cbc1910e83
ms.openlocfilehash: a6cc8774c14d4b393b0d04822216c894e486ba66
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556710"
---
# <a name="how-to-animate-a-3-d-rotation-using-storyboards"></a><span data-ttu-id="e349e-102">Cómo: Animar un giro 3D mediante Storyboards</span><span class="sxs-lookup"><span data-stu-id="e349e-102">How to: Animate a 3-D Rotation Using Storyboards</span></span>
<span data-ttu-id="e349e-103">En el ejemplo siguiente se muestra cómo hacer que un objeto 3D gire mientras se "tambalea" animando la <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> y <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> propiedades de un <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> objeto.</span><span class="sxs-lookup"><span data-stu-id="e349e-103">The following example shows how to make a 3D object rotate while it "wobbles" by animating the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> and <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> properties of an <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> object.</span></span> <span data-ttu-id="e349e-104">Esto <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> objeto especifica la transformación de giro del objeto 3D y así, animando sus propiedades crea el efecto de giro deseado.</span><span class="sxs-lookup"><span data-stu-id="e349e-104">This <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> object specifies the rotation transform of the 3D object and so animating its properties creates the desire rotation effect.</span></span> <span data-ttu-id="e349e-105">En el guión gráfico, <xref:System.Windows.Media.Animation.DoubleAnimation> se usa para animar la <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> propiedad mientras <xref:System.Windows.Media.Animation.Vector3DAnimation> se usa para animar la <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="e349e-105">Within the Storyboard, <xref:System.Windows.Media.Animation.DoubleAnimation> is used to animate the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> property while <xref:System.Windows.Media.Animation.Vector3DAnimation> is used to animate the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e349e-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e349e-106">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="e349e-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="e349e-107">See Also</span></span>  
 [<span data-ttu-id="e349e-108">Animar un giro 3D mediante Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="e349e-108">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)  
 [<span data-ttu-id="e349e-109">Animar un giro 3D mediante fotogramas clave (Rotation3DAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="e349e-109">Animate a 3-D Rotation Using Key Frames (Rotation3DAnimationUsingKeyFrames)</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-key-frames.md)  
 [<span data-ttu-id="e349e-110">Información general sobre gráficos 3D</span><span class="sxs-lookup"><span data-stu-id="e349e-110">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [<span data-ttu-id="e349e-111">Información general sobre objetos Storyboard </span><span class="sxs-lookup"><span data-stu-id="e349e-111">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
