---
title: 'Cómo: Aplicar material a la parte anterior y posterior de un objeto 3D'
ms.date: 03/30/2017
helpviewer_keywords:
- 3-D objects [WPF], applying Material class
- Material class [WPF], applying to both sides of 3-D object
- classes [WPF], Material
ms.assetid: d93c8ad6-4939-4d29-9544-4d16d98093c1
ms.openlocfilehash: 0ccf0aa045886f0731cd22ecdc8e14fa6af55fd2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559739"
---
# <a name="how-to-apply-material-to-the-front-and-back-of-a-3-d-object"></a><span data-ttu-id="6cdce-102">Cómo: Aplicar material a la parte anterior y posterior de un objeto 3D</span><span class="sxs-lookup"><span data-stu-id="6cdce-102">How to: Apply Material to the Front and Back of a 3-D Object</span></span>
<span data-ttu-id="6cdce-103">En el ejemplo siguiente se muestra cómo aplicar un <xref:System.Windows.Media.Media3D.Material> de objetos al principio y el reverso un 3D y animar el objeto para mostrar ambos lados del objeto.</span><span class="sxs-lookup"><span data-stu-id="6cdce-103">The following example shows how to apply a <xref:System.Windows.Media.Media3D.Material> to the front and back of a 3-D object and animate the object to show both sides of the object.</span></span> <span data-ttu-id="6cdce-104">El <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> propiedad de un <xref:System.Windows.Media.Media3D.GeometryModel3D> se usa para aplicar un color rojo <xref:System.Windows.Media.Brush> a la parte frontal del objeto y el <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> propiedad de la <xref:System.Windows.Media.Media3D.GeometryModel3D> se usa para aplicar un azul <xref:System.Windows.Media.Brush> a la parte posterior del objeto.</span><span class="sxs-lookup"><span data-stu-id="6cdce-104">The <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a red <xref:System.Windows.Media.Brush> to the front side of the object and the <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> property of the <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a blue <xref:System.Windows.Media.Brush> to the back side of the object.</span></span> <span data-ttu-id="6cdce-105">El código siguiente muestra la aplicación de los materiales al objeto:</span><span class="sxs-lookup"><span data-stu-id="6cdce-105">The code below shows the application of the materials to the object:</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="6cdce-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6cdce-106">Example</span></span>  
 <span data-ttu-id="6cdce-107">El código siguiente muestra el ejemplo completo.</span><span class="sxs-lookup"><span data-stu-id="6cdce-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="6cdce-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="6cdce-108">See Also</span></span>  
 [<span data-ttu-id="6cdce-109">Crear una escena 3D</span><span class="sxs-lookup"><span data-stu-id="6cdce-109">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [<span data-ttu-id="6cdce-110">Información general sobre gráficos 3D</span><span class="sxs-lookup"><span data-stu-id="6cdce-110">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [<span data-ttu-id="6cdce-111">Animar propiedades de material en una escena 3D</span><span class="sxs-lookup"><span data-stu-id="6cdce-111">Animate Material Properties in a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-material-properties-in-a-3-d-scene.md)  
 [<span data-ttu-id="6cdce-112">Aplicar material emisor a un objeto tridimensional</span><span class="sxs-lookup"><span data-stu-id="6cdce-112">Apply Emissive Material to a 3-D Object</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-emissive-material-to-a-3-d-object.md)
