---
title: 'Cómo: Animar una rotación 3D mediante cuaterniones'
ms.date: 03/30/2017
helpviewer_keywords:
- quaternions [WPF]
- animation [WPF], 3D translations [WPF], with quaternions
- 3D translations [WPF], animating [WPF], with quaternions
ms.assetid: adca9cb1-066b-4de8-abbb-6b4007579ee7
ms.openlocfilehash: 0d229b0a714cc53459943fae751ab4d4f787d7d8
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112250"
---
# <a name="how-to-animate-a-3d-rotation-using-quaternions"></a>Cómo: Animar una rotación 3D mediante cuaterniones
En este ejemplo se muestra cómo animar una rotación de un objeto 3D mediante cuaterniones.  
  
 El código siguiente <xref:System.Windows.Media.Media3D.QuaternionRotation3D> muestra un usado <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> como <xref:System.Windows.Media.Media3D.RotateTransform3D>el valor de la propiedad de un archivo .  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline1)]  
  
 Esto <xref:System.Windows.Media.Media3D.QuaternionRotation3D> se anima <xref:System.Windows.Media.Animation.QuaternionAnimation> con <xref:System.Windows.Media.Animation.Storyboard> un dentro de un uso del código de abajo.  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline2)]  
  
## <a name="example"></a>Ejemplo  
 El código siguiente muestra el ejemplo completo.  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexamplewholepage)]  
  
## <a name="see-also"></a>Consulte también

- [Información general sobre animaciones](animation-overview.md)
- [Crear una escena 3D](how-to-create-a-3-d-scene.md)
- [Descripción general de los gráficos 3D](3-d-graphics-overview.md)
- [Información general sobre transformaciones](transforms-overview.md)
- [Animar una rotación 3D mediante guiones gráficos](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [Animar una rotación 3D mediante Rotation3DAnimation](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
