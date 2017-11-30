---
title: "Cómo: Animar la posición y la dirección de una cámara en una escena 3D"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], camera position in 3-D scenes
- camera direction [WPF], animating in 3-D scenes
- 3-D scenes [WPF], animating camera position
- 3-D scenes [WPF], animating camera direction
- camera position [WPF], animating in 3-D scenes
- animation [WPF], camera direction in 3-D scenes
ms.assetid: 480224b7-a5e5-4165-ba7f-ef760ddff94a
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 790260f974dcb0be398af202cc7156fc91efed91
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-camera-position-and-direction-in-a-3d-scene"></a>Cómo: Animar la posición y la dirección de una cámara en una escena 3D
En el ejemplo siguiente se muestra cómo animar la posición de una cámara y animar la dirección en la que apunta en una escena 3D. Esto se realiza mediante <xref:System.Windows.Media.Animation.Point3DAnimation> y <xref:System.Windows.Media.Animation.Vector3DAnimation> para animar la <xref:System.Windows.Media.Media3D.ProjectionCamera.Position%2A> y <xref:System.Windows.Media.Media3D.ProjectionCamera.LookDirection%2A> propiedades respectivamente, de la <xref:System.Windows.Media.Media3D.PerspectiveCamera>. Puede usar una animación similar al siguiente para cambiar la vista del espectador de una escena en respuesta a un evento.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationExample.xaml#pointvector3danimationexamplewholepage)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.Animation.Vector3DAnimation>  
 <xref:System.Windows.Media.Animation.Point3DAnimation>  
 [Animar la posición y la dirección de una cámara mediante fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-camera-position-and-direction-using-key-frames.md)  
 [Información general sobre gráficos 3D](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
