---
title: 'Cómo: Animar una rotación 3D mediante guiones gráficos'
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF]
- 3D translations [WPF], animating [WPF], with Storyboards
- animation [WPF], 3D translations [WPF], with Storyboards
ms.assetid: 1020e44e-e21e-49a8-be53-53cbc1910e83
ms.openlocfilehash: 088f1a33cfc73a706ffed55ffff6494adaf8fca4
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112223"
---
# <a name="how-to-animate-a-3d-rotation-using-storyboards"></a><span data-ttu-id="f64d6-102">Cómo: Animar una rotación 3D mediante guiones gráficos</span><span class="sxs-lookup"><span data-stu-id="f64d6-102">How to: Animate a 3D Rotation Using Storyboards</span></span>
<span data-ttu-id="f64d6-103">En el ejemplo siguiente se muestra cómo hacer que un objeto 3D <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> gire <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> mientras se "wobbles" animando las <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> propiedades y de un objeto.</span><span class="sxs-lookup"><span data-stu-id="f64d6-103">The following example shows how to make a 3D object rotate while it "wobbles" by animating the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> and <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> properties of an <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> object.</span></span> <span data-ttu-id="f64d6-104">Este <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> objeto especifica la transformación de rotación del objeto 3D y, por lo tanto, animar sus propiedades crea el efecto de rotación de deseo.</span><span class="sxs-lookup"><span data-stu-id="f64d6-104">This <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> object specifies the rotation transform of the 3D object and so animating its properties creates the desire rotation effect.</span></span> <span data-ttu-id="f64d6-105">Dentro del <xref:System.Windows.Media.Animation.DoubleAnimation> guión gráfico, <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> se <xref:System.Windows.Media.Animation.Vector3DAnimation> usa para <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> animar la propiedad mientras se usa para animar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="f64d6-105">Within the Storyboard, <xref:System.Windows.Media.Animation.DoubleAnimation> is used to animate the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> property while <xref:System.Windows.Media.Animation.Vector3DAnimation> is used to animate the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f64d6-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f64d6-106">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="f64d6-107">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f64d6-107">See also</span></span>

- [<span data-ttu-id="f64d6-108">Animar una rotación 3D mediante Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="f64d6-108">Animate a 3D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [<span data-ttu-id="f64d6-109">Animar una rotación 3D mediante fotogramas clave (Rotation3DAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="f64d6-109">Animate a 3D Rotation Using Key Frames (Rotation3DAnimationUsingKeyFrames)</span></span>](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [<span data-ttu-id="f64d6-110">Descripción general de los gráficos 3D</span><span class="sxs-lookup"><span data-stu-id="f64d6-110">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="f64d6-111">Información general sobre objetos Storyboard </span><span class="sxs-lookup"><span data-stu-id="f64d6-111">Storyboards Overview</span></span>](storyboards-overview.md)
