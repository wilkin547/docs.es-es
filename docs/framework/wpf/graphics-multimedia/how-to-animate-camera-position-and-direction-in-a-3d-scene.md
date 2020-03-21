---
title: 'Cómo: Animar la posición y la dirección de una cámara en una escena 3D'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], camera position in 3D scenes
- camera direction [WPF], animating in 3D scenes
- 3D scenes [WPF], animating camera position
- 3D scenes [WPF], animating camera direction
- camera position [WPF], animating in 3D scenes
- animation [WPF], camera direction in 3D scenes
ms.assetid: 480224b7-a5e5-4165-ba7f-ef760ddff94a
ms.openlocfilehash: 5ce94e154cd5aa29b59260f893ec2b63a08db0fc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112222"
---
# <a name="how-to-animate-camera-position-and-direction-in-a-3d-scene"></a>Cómo: Animar la posición y la dirección de una cámara en una escena 3D
En el ejemplo siguiente se muestra cómo animar la posición de una cámara y animar la dirección que apunta en una escena 3D. Esto se hace <xref:System.Windows.Media.Animation.Point3DAnimation> <xref:System.Windows.Media.Animation.Vector3DAnimation> mediante el <xref:System.Windows.Media.Media3D.ProjectionCamera.Position%2A> <xref:System.Windows.Media.Media3D.ProjectionCamera.LookDirection%2A> uso y <xref:System.Windows.Media.Media3D.PerspectiveCamera>para animar las propiedades y respectivamente de la . Puede usar una animación como esta para cambiar la vista del visor de una escena en respuesta a un evento.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationExample.xaml#pointvector3danimationexamplewholepage)]  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Media.Animation.Vector3DAnimation>
- <xref:System.Windows.Media.Animation.Point3DAnimation>
- [Animar la posición y la dirección de una cámara mediante fotogramas clave](how-to-animate-camera-position-and-direction-using-key-frames.md)
- [Descripción general de los gráficos 3D](3-d-graphics-overview.md)
