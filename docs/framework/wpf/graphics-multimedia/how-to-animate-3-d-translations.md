---
title: 'Cómo: Animar traslaciones 3D'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3-D translations
- 3-D translations [WPF], animating
ms.assetid: d4eece1f-0cd2-4a2c-8370-293354c380e4
ms.openlocfilehash: b9307e1c9ca13b465acd76091f364c538416a5b3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556775"
---
# <a name="how-to-animate-3-d-translations"></a><span data-ttu-id="77a4e-102">Cómo: Animar traslaciones 3D</span><span class="sxs-lookup"><span data-stu-id="77a4e-102">How to: Animate 3-D Translations</span></span>
<span data-ttu-id="77a4e-103">Este tema muestra cómo animar una transformación de conversión establecer en un [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] modelo.</span><span class="sxs-lookup"><span data-stu-id="77a4e-103">This topic demonstrates how to animate a translation transformation set on a [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] model.</span></span>  
  
 <span data-ttu-id="77a4e-104">El código siguiente muestra la aplicación de un <xref:System.Windows.Media.Media3D.TranslateTransform3D> el objeto a la <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> propiedad de un <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="77a4e-104">The code below shows the application of a <xref:System.Windows.Media.Media3D.TranslateTransform3D> object to the <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline1)]  
  
 <span data-ttu-id="77a4e-105">El <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> propiedad de este <xref:System.Windows.Media.Media3D.TranslateTransform3D> objeto se anima mediante el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="77a4e-105">The <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> property of this <xref:System.Windows.Media.Media3D.TranslateTransform3D> object is animated using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline2)]  
  
## <a name="example"></a><span data-ttu-id="77a4e-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="77a4e-106">Example</span></span>  
 <span data-ttu-id="77a4e-107">El código siguiente muestra el ejemplo completo.</span><span class="sxs-lookup"><span data-stu-id="77a4e-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="77a4e-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="77a4e-108">See Also</span></span>  
 [<span data-ttu-id="77a4e-109">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="77a4e-109">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="77a4e-110">Crear una escena 3D</span><span class="sxs-lookup"><span data-stu-id="77a4e-110">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [<span data-ttu-id="77a4e-111">Información general sobre gráficos 3D</span><span class="sxs-lookup"><span data-stu-id="77a4e-111">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [<span data-ttu-id="77a4e-112">Información general sobre transformaciones</span><span class="sxs-lookup"><span data-stu-id="77a4e-112">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
