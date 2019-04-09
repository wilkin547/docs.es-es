---
title: Filtrar Animar la posición y la dirección de una cámara en una escena 3D
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], camera position in 3-D scenes
- camera direction [WPF], animating in 3-D scenes
- 3-D scenes [WPF], animating camera position
- 3-D scenes [WPF], animating camera direction
- camera position [WPF], animating in 3-D scenes
- animation [WPF], camera direction in 3-D scenes
ms.assetid: 480224b7-a5e5-4165-ba7f-ef760ddff94a
ms.openlocfilehash: b64263a495ffe845a76317aad8f5b4a14e11b31e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59146008"
---
# <a name="how-to-animate-camera-position-and-direction-in-a-3d-scene"></a>Filtrar Animar la posición y la dirección de una cámara en una escena 3D
El ejemplo siguiente muestra cómo animar la posición de una cámara y animar la dirección en la que apunta en una escena 3D. Esto se realiza mediante <xref:System.Windows.Media.Animation.Point3DAnimation> y <xref:System.Windows.Media.Animation.Vector3DAnimation> para animar la <xref:System.Windows.Media.Media3D.ProjectionCamera.Position%2A> y <xref:System.Windows.Media.Media3D.ProjectionCamera.LookDirection%2A> propiedades respectivamente, de la <xref:System.Windows.Media.Media3D.PerspectiveCamera>. Puede usar una animación similar al siguiente para cambiar la vista del espectador de una escena en respuesta a un evento.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationExample.xaml#pointvector3danimationexamplewholepage)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.Animation.Vector3DAnimation>
- <xref:System.Windows.Media.Animation.Point3DAnimation>
- [Animar la posición y la dirección de una cámara mediante fotogramas clave](how-to-animate-camera-position-and-direction-using-key-frames.md)
- [Información general sobre gráficos 3D](3-d-graphics-overview.md)
