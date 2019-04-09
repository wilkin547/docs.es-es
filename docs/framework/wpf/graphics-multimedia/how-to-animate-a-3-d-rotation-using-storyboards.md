---
title: Filtrar Animar un giro 3D mediante Storyboards
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF]
- 3-D translations [WPF], animating [WPF], with Storyboards
- animation [WPF], 3-D translations [WPF], with Storyboards
ms.assetid: 1020e44e-e21e-49a8-be53-53cbc1910e83
ms.openlocfilehash: 03b01205f1a31426a01b09533b350682c384df4b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59146203"
---
# <a name="how-to-animate-a-3-d-rotation-using-storyboards"></a>Filtrar Animar un giro 3D mediante Storyboards
El ejemplo siguiente muestra cómo hacer girar mientras se "tambalea" animar un objeto 3D el <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> y <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> las propiedades de un <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> objeto. Esto <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> objeto especifica la transformación de giro del objeto 3D y sus propiedades de animación por lo que crea el efecto de giro deseado. En el guión gráfico, <xref:System.Windows.Media.Animation.DoubleAnimation> sirve para animar la <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> propiedad mientras <xref:System.Windows.Media.Animation.Vector3DAnimation> sirve para animar el <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> propiedad.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## <a name="see-also"></a>Vea también

- [Animar un giro 3D mediante Rotation3DAnimation](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [Animar un giro 3D mediante fotogramas clave (Rotation3DAnimationUsingKeyFrames)](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [Información general sobre gráficos 3D](3-d-graphics-overview.md)
- [Información general sobre objetos Storyboard](storyboards-overview.md)
