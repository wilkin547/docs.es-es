---
title: "Cómo: Animar un giro 3D mediante cuaterniones"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- quaternions [WPF]
- animation [WPF], 3-D translations [WPF], with quaternions
- 3-D translations [WPF], animating [WPF], with quaternions
ms.assetid: adca9cb1-066b-4de8-abbb-6b4007579ee7
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4485e7dfc6a72f559f6df69f77e7afd98ab8aaf5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-a-3-d-rotation-using-quaternions"></a><span data-ttu-id="66d57-102">Cómo: Animar un giro 3D mediante cuaterniones</span><span class="sxs-lookup"><span data-stu-id="66d57-102">How to: Animate a 3-D Rotation Using Quaternions</span></span>
<span data-ttu-id="66d57-103">En este ejemplo se muestra cómo animar un giro de un objeto 3D utilizando cuaterniones.</span><span class="sxs-lookup"><span data-stu-id="66d57-103">This example shows how to animate a rotation of a 3-D object using quaternions.</span></span>  
  
 <span data-ttu-id="66d57-104">El código siguiente muestra un <xref:System.Windows.Media.Media3D.QuaternionRotation3D> utilizar como el valor de la <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> propiedad de un <xref:System.Windows.Media.Media3D.RotateTransform3D>.</span><span class="sxs-lookup"><span data-stu-id="66d57-104">The code below shows a <xref:System.Windows.Media.Media3D.QuaternionRotation3D> used as the value for the <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> property of a <xref:System.Windows.Media.Media3D.RotateTransform3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline1)]  
  
 <span data-ttu-id="66d57-105">Esto <xref:System.Windows.Media.Media3D.QuaternionRotation3D> se anima con un <xref:System.Windows.Media.Animation.QuaternionAnimation> dentro de un <xref:System.Windows.Media.Animation.Storyboard> con el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="66d57-105">This <xref:System.Windows.Media.Media3D.QuaternionRotation3D> is animated with a <xref:System.Windows.Media.Animation.QuaternionAnimation> within a <xref:System.Windows.Media.Animation.Storyboard> using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline2)]  
  
## <a name="example"></a><span data-ttu-id="66d57-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="66d57-106">Example</span></span>  
 <span data-ttu-id="66d57-107">El código siguiente muestra el ejemplo completo.</span><span class="sxs-lookup"><span data-stu-id="66d57-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="66d57-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="66d57-108">See Also</span></span>  
 [<span data-ttu-id="66d57-109">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="66d57-109">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="66d57-110">Crear una escena 3D</span><span class="sxs-lookup"><span data-stu-id="66d57-110">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [<span data-ttu-id="66d57-111">Información general sobre gráficos 3D</span><span class="sxs-lookup"><span data-stu-id="66d57-111">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [<span data-ttu-id="66d57-112">Información general sobre transformaciones</span><span class="sxs-lookup"><span data-stu-id="66d57-112">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [<span data-ttu-id="66d57-113">Animar un giro 3D mediante Storyboards</span><span class="sxs-lookup"><span data-stu-id="66d57-113">Animate a 3-D Rotation Using Storyboards</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-storyboards.md)  
 [<span data-ttu-id="66d57-114">Animar un giro 3D mediante Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="66d57-114">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
