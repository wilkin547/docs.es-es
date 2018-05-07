---
title: 'Cómo: Animar un giro 3D mediante cuaterniones'
ms.date: 03/30/2017
helpviewer_keywords:
- quaternions [WPF]
- animation [WPF], 3-D translations [WPF], with quaternions
- 3-D translations [WPF], animating [WPF], with quaternions
ms.assetid: adca9cb1-066b-4de8-abbb-6b4007579ee7
ms.openlocfilehash: 4c2a46aad1feeefe5c7c31ec192f46b8c891337f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-animate-a-3-d-rotation-using-quaternions"></a>Cómo: Animar un giro 3D mediante cuaterniones
En este ejemplo se muestra cómo animar un giro de un objeto 3D utilizando cuaterniones.  
  
 El código siguiente muestra un <xref:System.Windows.Media.Media3D.QuaternionRotation3D> utilizar como el valor de la <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> propiedad de un <xref:System.Windows.Media.Media3D.RotateTransform3D>.  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline1)]  
  
 Esto <xref:System.Windows.Media.Media3D.QuaternionRotation3D> se anima con un <xref:System.Windows.Media.Animation.QuaternionAnimation> dentro de un <xref:System.Windows.Media.Animation.Storyboard> con el código siguiente.  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline2)]  
  
## <a name="example"></a>Ejemplo  
 El código siguiente muestra el ejemplo completo.  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexamplewholepage)]  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Crear una escena 3D](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [Información general sobre gráficos 3D](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [Información general sobre transformaciones](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [Animar un giro 3D mediante Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-storyboards.md)  
 [Animar un giro 3D mediante Rotation3DAnimation](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
