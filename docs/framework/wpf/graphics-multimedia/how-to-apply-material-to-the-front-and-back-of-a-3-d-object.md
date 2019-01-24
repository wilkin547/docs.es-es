---
title: Procedimiento Aplicar material a la parte anterior y posterior de un objeto 3D
ms.date: 03/30/2017
helpviewer_keywords:
- 3-D objects [WPF], applying Material class
- Material class [WPF], applying to both sides of 3-D object
- classes [WPF], Material
ms.assetid: d93c8ad6-4939-4d29-9544-4d16d98093c1
ms.openlocfilehash: 16f30e3a880d7dcc943a9583ba0f04c4bd682827
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54652038"
---
# <a name="how-to-apply-material-to-the-front-and-back-of-a-3-d-object"></a><span data-ttu-id="1152b-102">Procedimiento Aplicar material a la parte anterior y posterior de un objeto 3D</span><span class="sxs-lookup"><span data-stu-id="1152b-102">How to: Apply Material to the Front and Back of a 3-D Object</span></span>
<span data-ttu-id="1152b-103">El ejemplo siguiente muestra cómo aplicar un <xref:System.Windows.Media.Media3D.Material> objeto a la parte frontal y posterior de un 3D y animar el objeto para mostrar ambos lados del objeto.</span><span class="sxs-lookup"><span data-stu-id="1152b-103">The following example shows how to apply a <xref:System.Windows.Media.Media3D.Material> to the front and back of a 3-D object and animate the object to show both sides of the object.</span></span> <span data-ttu-id="1152b-104">El <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> propiedad de un <xref:System.Windows.Media.Media3D.GeometryModel3D> se usa para aplicar un color rojo <xref:System.Windows.Media.Brush> a la parte frontal del objeto y el <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> propiedad de la <xref:System.Windows.Media.Media3D.GeometryModel3D> se usa para aplicar un azul <xref:System.Windows.Media.Brush> a la parte posterior del objeto.</span><span class="sxs-lookup"><span data-stu-id="1152b-104">The <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a red <xref:System.Windows.Media.Brush> to the front side of the object and the <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> property of the <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a blue <xref:System.Windows.Media.Brush> to the back side of the object.</span></span> <span data-ttu-id="1152b-105">El código siguiente muestra la aplicación de los materiales en el objeto:</span><span class="sxs-lookup"><span data-stu-id="1152b-105">The code below shows the application of the materials to the object:</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="1152b-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1152b-106">Example</span></span>  
 <span data-ttu-id="1152b-107">El código siguiente muestra el ejemplo completo.</span><span class="sxs-lookup"><span data-stu-id="1152b-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="1152b-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="1152b-108">See also</span></span>
- [<span data-ttu-id="1152b-109">Crear una escena 3D</span><span class="sxs-lookup"><span data-stu-id="1152b-109">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="1152b-110">Información general sobre gráficos 3D</span><span class="sxs-lookup"><span data-stu-id="1152b-110">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
- [<span data-ttu-id="1152b-111">Animar propiedades de material en una escena 3D</span><span class="sxs-lookup"><span data-stu-id="1152b-111">Animate Material Properties in a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-material-properties-in-a-3-d-scene.md)
- [<span data-ttu-id="1152b-112">Aplicar material emisor a un objeto tridimensional</span><span class="sxs-lookup"><span data-stu-id="1152b-112">Apply Emissive Material to a 3-D Object</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-emissive-material-to-a-3-d-object.md)
