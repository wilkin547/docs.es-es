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
# <a name="how-to-animate-a-3d-rotation-using-storyboards"></a>Cómo: Animar una rotación 3D mediante guiones gráficos
En el ejemplo siguiente se muestra cómo hacer que un objeto 3D <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> gire <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> mientras se "wobbles" animando las <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> propiedades y de un objeto. Este <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> objeto especifica la transformación de rotación del objeto 3D y, por lo tanto, animar sus propiedades crea el efecto de rotación de deseo. Dentro del <xref:System.Windows.Media.Animation.DoubleAnimation> guión gráfico, <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> se <xref:System.Windows.Media.Animation.Vector3DAnimation> usa para <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> animar la propiedad mientras se usa para animar la propiedad.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## <a name="see-also"></a>Consulte también

- [Animar una rotación 3D mediante Rotation3DAnimation](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [Animar una rotación 3D mediante fotogramas clave (Rotation3DAnimationUsingKeyFrames)](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [Descripción general de los gráficos 3D](3-d-graphics-overview.md)
- [Información general sobre objetos Storyboard ](storyboards-overview.md)
