---
title: 'Cómo: Aplicar material en la parte delantera y trasera de un objeto 3D'
ms.date: 03/30/2017
helpviewer_keywords:
- 3D objects [WPF], applying Material class
- Material class [WPF], applying to both sides of 3D object
- classes [WPF], Material
ms.assetid: d93c8ad6-4939-4d29-9544-4d16d98093c1
ms.openlocfilehash: 5c24879d97e7857fb07fcef4a9ba8efa901e4a39
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112146"
---
# <a name="how-to-apply-material-to-the-front-and-back-of-a-3d-object"></a><span data-ttu-id="bb9e8-102">Cómo: Aplicar material en la parte delantera y trasera de un objeto 3D</span><span class="sxs-lookup"><span data-stu-id="bb9e8-102">How to: Apply Material to the Front and Back of a 3D Object</span></span>
<span data-ttu-id="bb9e8-103">En el ejemplo siguiente <xref:System.Windows.Media.Media3D.Material> se muestra cómo aplicar a a la parte delantera y trasera de un objeto 3D y animar el objeto para mostrar ambos lados del objeto.</span><span class="sxs-lookup"><span data-stu-id="bb9e8-103">The following example shows how to apply a <xref:System.Windows.Media.Media3D.Material> to the front and back of a 3D object and animate the object to show both sides of the object.</span></span> <span data-ttu-id="bb9e8-104">La <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> propiedad <xref:System.Windows.Media.Media3D.GeometryModel3D> de a se <xref:System.Windows.Media.Brush> utiliza para aplicar un rojo <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> a <xref:System.Windows.Media.Media3D.GeometryModel3D> la parte frontal <xref:System.Windows.Media.Brush> del objeto y la propiedad de la se utiliza para aplicar un azul a la parte posterior del objeto.</span><span class="sxs-lookup"><span data-stu-id="bb9e8-104">The <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a red <xref:System.Windows.Media.Brush> to the front side of the object and the <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> property of the <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a blue <xref:System.Windows.Media.Brush> to the back side of the object.</span></span> <span data-ttu-id="bb9e8-105">El código siguiente muestra la aplicación de los materiales al objeto:</span><span class="sxs-lookup"><span data-stu-id="bb9e8-105">The code below shows the application of the materials to the object:</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="bb9e8-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bb9e8-106">Example</span></span>  
 <span data-ttu-id="bb9e8-107">El código siguiente muestra el ejemplo completo.</span><span class="sxs-lookup"><span data-stu-id="bb9e8-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="bb9e8-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bb9e8-108">See also</span></span>

- [<span data-ttu-id="bb9e8-109">Crear una escena 3D</span><span class="sxs-lookup"><span data-stu-id="bb9e8-109">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="bb9e8-110">Descripción general de los gráficos 3D</span><span class="sxs-lookup"><span data-stu-id="bb9e8-110">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="bb9e8-111">Animar propiedades de material en una escena 3D</span><span class="sxs-lookup"><span data-stu-id="bb9e8-111">Animate Material Properties in a 3D Scene</span></span>](how-to-animate-material-properties-in-a-3-d-scene.md)
- [<span data-ttu-id="bb9e8-112">Aplicar material emisivo a un objeto 3D</span><span class="sxs-lookup"><span data-stu-id="bb9e8-112">Apply Emissive Material to a 3D Object</span></span>](how-to-apply-emissive-material-to-a-3-d-object.md)
