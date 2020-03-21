---
title: 'Cómo: Animar traducciones 3D'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3D translations
- 3D translations [WPF], animating
ms.assetid: d4eece1f-0cd2-4a2c-8370-293354c380e4
ms.openlocfilehash: 7d4fff9c74663bd220ad5d15a983bcb639621afd
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112263"
---
# <a name="how-to-animate-3d-translations"></a><span data-ttu-id="21aea-102">Cómo: Animar traducciones 3D</span><span class="sxs-lookup"><span data-stu-id="21aea-102">How to: Animate 3D Translations</span></span>
<span data-ttu-id="21aea-103">En este tema se muestra cómo animar un conjunto de transformación de traducción en un modelo 3D.</span><span class="sxs-lookup"><span data-stu-id="21aea-103">This topic demonstrates how to animate a translation transformation set on a 3D model.</span></span>  
  
 <span data-ttu-id="21aea-104">El código siguiente muestra <xref:System.Windows.Media.Media3D.TranslateTransform3D> la aplicación <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> de <xref:System.Windows.Media.Media3D.GeometryModel3D>un objeto a la propiedad de un archivo .</span><span class="sxs-lookup"><span data-stu-id="21aea-104">The code below shows the application of a <xref:System.Windows.Media.Media3D.TranslateTransform3D> object to the <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline1)]  
  
 <span data-ttu-id="21aea-105">La <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> propiedad <xref:System.Windows.Media.Media3D.TranslateTransform3D> de este objeto se anima utilizando el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="21aea-105">The <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> property of this <xref:System.Windows.Media.Media3D.TranslateTransform3D> object is animated using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline2)]  
  
## <a name="example"></a><span data-ttu-id="21aea-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="21aea-106">Example</span></span>  
 <span data-ttu-id="21aea-107">El código siguiente muestra el ejemplo completo.</span><span class="sxs-lookup"><span data-stu-id="21aea-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="21aea-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="21aea-108">See also</span></span>

- [<span data-ttu-id="21aea-109">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="21aea-109">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="21aea-110">Crear una escena 3D</span><span class="sxs-lookup"><span data-stu-id="21aea-110">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="21aea-111">Descripción general de los gráficos 3D</span><span class="sxs-lookup"><span data-stu-id="21aea-111">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="21aea-112">Información general sobre transformaciones</span><span class="sxs-lookup"><span data-stu-id="21aea-112">Transforms Overview</span></span>](transforms-overview.md)
