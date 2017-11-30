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
# <a name="how-to-animate-camera-position-and-direction-in-a-3d-scene"></a><span data-ttu-id="23d74-102">Cómo: Animar la posición y la dirección de una cámara en una escena 3D</span><span class="sxs-lookup"><span data-stu-id="23d74-102">How to: Animate Camera Position and Direction in a 3D Scene</span></span>
<span data-ttu-id="23d74-103">En el ejemplo siguiente se muestra cómo animar la posición de una cámara y animar la dirección en la que apunta en una escena 3D.</span><span class="sxs-lookup"><span data-stu-id="23d74-103">The following example shows how to animate the position of a camera and animate the direction it is pointing in a 3D scene.</span></span> <span data-ttu-id="23d74-104">Esto se realiza mediante <xref:System.Windows.Media.Animation.Point3DAnimation> y <xref:System.Windows.Media.Animation.Vector3DAnimation> para animar la <xref:System.Windows.Media.Media3D.ProjectionCamera.Position%2A> y <xref:System.Windows.Media.Media3D.ProjectionCamera.LookDirection%2A> propiedades respectivamente, de la <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span><span class="sxs-lookup"><span data-stu-id="23d74-104">This is done by using <xref:System.Windows.Media.Animation.Point3DAnimation> and <xref:System.Windows.Media.Animation.Vector3DAnimation> to animate the <xref:System.Windows.Media.Media3D.ProjectionCamera.Position%2A> and <xref:System.Windows.Media.Media3D.ProjectionCamera.LookDirection%2A> properties respectively of the <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span></span> <span data-ttu-id="23d74-105">Puede usar una animación similar al siguiente para cambiar la vista del espectador de una escena en respuesta a un evento.</span><span class="sxs-lookup"><span data-stu-id="23d74-105">You might use an animation like this to change the onlooker's view of a scene in response to an event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23d74-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="23d74-106">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationExample.xaml#pointvector3danimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="23d74-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="23d74-107">See Also</span></span>  
 <xref:System.Windows.Media.Animation.Vector3DAnimation>  
 <xref:System.Windows.Media.Animation.Point3DAnimation>  
 [<span data-ttu-id="23d74-108">Animar la posición y la dirección de una cámara mediante fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="23d74-108">Animate Camera Position and Direction Using Key Frames</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-camera-position-and-direction-using-key-frames.md)  
 [<span data-ttu-id="23d74-109">Información general sobre gráficos 3D</span><span class="sxs-lookup"><span data-stu-id="23d74-109">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
