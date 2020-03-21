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
# <a name="how-to-animate-camera-position-and-direction-using-key-frames"></a>Cómo: Animar la posición y la dirección de una cámara mediante fotogramas clave
En el ejemplo <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> siguiente, se utiliza <xref:System.Windows.Media.Media3D.PerspectiveCamera> para animar la posición de a en una escena 3D. Además, <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> se utiliza para animar la dirección que apunta la cámara en la escena 3D. Ambas animaciones utilizan varios fotogramas clave que crean una serie de efectos de animación:  
  
1. <xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame>y <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> se utilizan para crear una interpolación lineal suave entre los valores.  
  
2. <xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame>y <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> se utilizan para crear "saltos" repentinos entre los valores (sin interpolación).  
  
3. <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame>y <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> se utilizan para crear una transición <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> variable entre los valores en función de la propiedad. En el ejemplo siguiente, la animación comienza lentamente, pero hacia el final del segmento de tiempo, se acelera exponencialmente.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>Consulte también

- [Animar la posición y la dirección de una cámara en una escena 3D](how-to-animate-camera-position-and-direction-in-a-3d-scene.md)
- [Descripción general de los gráficos 3D](3-d-graphics-overview.md)
