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
# <a name="how-to-animate-a-3d-rotation-using-quaternions"></a><span data-ttu-id="affb9-102">Cómo: Animar una rotación 3D mediante cuaterniones</span><span class="sxs-lookup"><span data-stu-id="affb9-102">How to: Animate a 3D Rotation Using Quaternions</span></span>
<span data-ttu-id="affb9-103">En este ejemplo se muestra cómo animar una rotación de un objeto 3D mediante cuaterniones.</span><span class="sxs-lookup"><span data-stu-id="affb9-103">This example shows how to animate a rotation of a 3D object using quaternions.</span></span>  
  
 <span data-ttu-id="affb9-104">El código siguiente <xref:System.Windows.Media.Media3D.QuaternionRotation3D> muestra un usado <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> como <xref:System.Windows.Media.Media3D.RotateTransform3D>el valor de la propiedad de un archivo .</span><span class="sxs-lookup"><span data-stu-id="affb9-104">The code below shows a <xref:System.Windows.Media.Media3D.QuaternionRotation3D> used as the value for the <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> property of a <xref:System.Windows.Media.Media3D.RotateTransform3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline1)]  
  
 <span data-ttu-id="affb9-105">Esto <xref:System.Windows.Media.Media3D.QuaternionRotation3D> se anima <xref:System.Windows.Media.Animation.QuaternionAnimation> con <xref:System.Windows.Media.Animation.Storyboard> un dentro de un uso del código de abajo.</span><span class="sxs-lookup"><span data-stu-id="affb9-105">This <xref:System.Windows.Media.Media3D.QuaternionRotation3D> is animated with a <xref:System.Windows.Media.Animation.QuaternionAnimation> within a <xref:System.Windows.Media.Animation.Storyboard> using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline2)]  
  
## <a name="example"></a><span data-ttu-id="affb9-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="affb9-106">Example</span></span>  
 <span data-ttu-id="affb9-107">El código siguiente muestra el ejemplo completo.</span><span class="sxs-lookup"><span data-stu-id="affb9-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="affb9-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="affb9-108">See also</span></span>

- [<span data-ttu-id="affb9-109">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="affb9-109">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="affb9-110">Crear una escena 3D</span><span class="sxs-lookup"><span data-stu-id="affb9-110">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="affb9-111">Descripción general de los gráficos 3D</span><span class="sxs-lookup"><span data-stu-id="affb9-111">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="affb9-112">Información general sobre transformaciones</span><span class="sxs-lookup"><span data-stu-id="affb9-112">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="affb9-113">Animar una rotación 3D mediante guiones gráficos</span><span class="sxs-lookup"><span data-stu-id="affb9-113">Animate a 3D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="affb9-114">Animar una rotación 3D mediante Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="affb9-114">Animate a 3D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
