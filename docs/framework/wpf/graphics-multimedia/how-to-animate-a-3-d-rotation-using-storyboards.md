---
title: "Cómo: Animar un giro 3D mediante Storyboards"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Storyboards [WPF]
- 3-D translations [WPF], animating [WPF], with Storyboards
- animation [WPF], 3-D translations [WPF], with Storyboards
ms.assetid: 1020e44e-e21e-49a8-be53-53cbc1910e83
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: aa67db777ee04edcafa6ca3a53a37a638992fe29
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-3-d-rotation-using-storyboards"></a>Cómo: Animar un giro 3D mediante Storyboards
En el ejemplo siguiente se muestra cómo hacer que un objeto 3D gire mientras se "tambalea" animando la <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> y <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> propiedades de un <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> objeto. Esto <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> objeto especifica la transformación de giro del objeto 3D y así, animando sus propiedades crea el efecto de giro deseado. En el guión gráfico, <xref:System.Windows.Media.Animation.DoubleAnimation> se usa para animar la <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> propiedad mientras <xref:System.Windows.Media.Animation.Vector3DAnimation> se usa para animar la <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> propiedad.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## <a name="see-also"></a>Vea también  
 [Animar un giro 3D mediante Rotation3DAnimation](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)  
 [Animar un giro 3D mediante fotogramas clave (Rotation3DAnimationUsingKeyFrames)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-key-frames.md)  
 [Información general sobre gráficos 3D](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [Información general sobre objetos Storyboard ](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
