---
title: Procedimiento Animar un giro 3D mediante Storyboards
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF]
- 3-D translations [WPF], animating [WPF], with Storyboards
- animation [WPF], 3-D translations [WPF], with Storyboards
ms.assetid: 1020e44e-e21e-49a8-be53-53cbc1910e83
ms.openlocfilehash: 0e5e0b4e2b991b15ff7a49da65bfe96485e66fcc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54589810"
---
# <a name="how-to-animate-a-3-d-rotation-using-storyboards"></a>Procedimiento Animar un giro 3D mediante Storyboards
El ejemplo siguiente muestra cómo hacer girar mientras se "tambalea" animar un objeto 3D el <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> y <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> las propiedades de un <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> objeto. Esto <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> objeto especifica la transformación de giro del objeto 3D y sus propiedades de animación por lo que crea el efecto de giro deseado. En el guión gráfico, <xref:System.Windows.Media.Animation.DoubleAnimation> sirve para animar la <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> propiedad mientras <xref:System.Windows.Media.Animation.Vector3DAnimation> sirve para animar el <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> propiedad.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## <a name="see-also"></a>Vea también
- [Animar un giro 3D mediante Rotation3DAnimation](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [Animar un giro 3D mediante fotogramas clave (Rotation3DAnimationUsingKeyFrames)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-key-frames.md)
- [Información general sobre gráficos 3D](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
- [Información general sobre objetos Storyboard ](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
