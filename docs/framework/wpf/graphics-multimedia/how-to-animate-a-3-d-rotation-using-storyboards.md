---
title: Procedimiento Animar un giro 3D mediante Storyboards
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF]
- 3-D translations [WPF], animating [WPF], with Storyboards
- animation [WPF], 3-D translations [WPF], with Storyboards
ms.assetid: 1020e44e-e21e-49a8-be53-53cbc1910e83
ms.openlocfilehash: 20f5bf565ded624e4ea7e1e615f09b4c698526bd
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357227"
---
# <a name="how-to-animate-a-3-d-rotation-using-storyboards"></a>Filtrar Animar un giro 3D mediante Storyboards
El ejemplo siguiente muestra cómo hacer girar mientras se "tambalea" animar un objeto 3D el <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> y <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> las propiedades de un <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> objeto. Esto <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> objeto especifica la transformación de giro del objeto 3D y sus propiedades de animación por lo que crea el efecto de giro deseado. En el guión gráfico, <xref:System.Windows.Media.Animation.DoubleAnimation> sirve para animar la <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> propiedad mientras <xref:System.Windows.Media.Animation.Vector3DAnimation> sirve para animar el <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> propiedad.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## <a name="see-also"></a>Vea también
- [Animar un giro 3D mediante Rotation3DAnimation](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [Animar un giro 3D mediante fotogramas clave (Rotation3DAnimationUsingKeyFrames)](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [Información general sobre gráficos 3D](3-d-graphics-overview.md)
- [Información general sobre objetos Storyboard ](storyboards-overview.md)
