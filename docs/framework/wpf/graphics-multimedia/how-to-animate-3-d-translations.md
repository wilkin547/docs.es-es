---
title: Procedimiento Animar traslaciones 3D
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3-D translations
- 3-D translations [WPF], animating
ms.assetid: d4eece1f-0cd2-4a2c-8370-293354c380e4
ms.openlocfilehash: 6d7e0b422d6e76d5d0e25ad276550613f264e9bc
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661186"
---
# <a name="how-to-animate-3-d-translations"></a><span data-ttu-id="bfac0-102">Procedimiento Animar traslaciones 3D</span><span class="sxs-lookup"><span data-stu-id="bfac0-102">How to: Animate 3-D Translations</span></span>
<span data-ttu-id="bfac0-103">En este tema se muestra cómo animar una transformación de traslación establecido en un modelo 3D.</span><span class="sxs-lookup"><span data-stu-id="bfac0-103">This topic demonstrates how to animate a translation transformation set on a 3-D model.</span></span>  
  
 <span data-ttu-id="bfac0-104">El código siguiente muestra la aplicación de un <xref:System.Windows.Media.Media3D.TranslateTransform3D> de objeto para el <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> propiedad de un <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="bfac0-104">The code below shows the application of a <xref:System.Windows.Media.Media3D.TranslateTransform3D> object to the <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline1)]  
  
 <span data-ttu-id="bfac0-105">El <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> propiedad de este <xref:System.Windows.Media.Media3D.TranslateTransform3D> objeto se anima mediante el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="bfac0-105">The <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> property of this <xref:System.Windows.Media.Media3D.TranslateTransform3D> object is animated using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline2)]  
  
## <a name="example"></a><span data-ttu-id="bfac0-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bfac0-106">Example</span></span>  
 <span data-ttu-id="bfac0-107">El código siguiente muestra el ejemplo completo.</span><span class="sxs-lookup"><span data-stu-id="bfac0-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="bfac0-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="bfac0-108">See also</span></span>

- [<span data-ttu-id="bfac0-109">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="bfac0-109">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="bfac0-110">Crear una escena 3D</span><span class="sxs-lookup"><span data-stu-id="bfac0-110">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="bfac0-111">Información general sobre gráficos 3D</span><span class="sxs-lookup"><span data-stu-id="bfac0-111">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="bfac0-112">Información general sobre transformaciones</span><span class="sxs-lookup"><span data-stu-id="bfac0-112">Transforms Overview</span></span>](transforms-overview.md)
