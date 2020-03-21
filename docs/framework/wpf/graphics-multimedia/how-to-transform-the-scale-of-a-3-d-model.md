---
title: 'Cómo: Transformar la Escala de un Modelo 3D'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], 3D objects
- 3D objects [WPF], scaling
ms.assetid: f3fdfe33-f7dc-44b0-84a5-e43b89947f35
ms.openlocfilehash: be41a0e10929912c1b54bf7140d743d9453199bf
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111990"
---
# <a name="how-to-transform-the-scale-of-a-3d-model"></a><span data-ttu-id="333ef-102">Cómo: Transformar la Escala de un Modelo 3D</span><span class="sxs-lookup"><span data-stu-id="333ef-102">How to: Transform the Scale of a 3D Model</span></span>
<span data-ttu-id="333ef-103">En este ejemplo se muestra cómo escalar un objeto 3D.</span><span class="sxs-lookup"><span data-stu-id="333ef-103">This example shows how to scale a 3D object.</span></span> <span data-ttu-id="333ef-104">Para escalar un objeto 3D, utilice un <xref:System.Windows.Media.Media3D.ScaleTransform3D>archivo .</span><span class="sxs-lookup"><span data-stu-id="333ef-104">To scale a 3D object, use a <xref:System.Windows.Media.Media3D.ScaleTransform3D>.</span></span> <span data-ttu-id="333ef-105">Las <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>propiedades <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> , , y cambian el tamaño del elemento según el factor que especifique.</span><span class="sxs-lookup"><span data-stu-id="333ef-105">The <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>, and <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> properties resize the element by the factor you specify.</span></span> <span data-ttu-id="333ef-106">Por ejemplo, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> un valor de 1,5 estira un objeto al 150 por ciento de su ancho original.</span><span class="sxs-lookup"><span data-stu-id="333ef-106">For example, a <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> value of 1.5 stretches an object to 150 percent of its original width.</span></span> <span data-ttu-id="333ef-107">Un <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> valor de 0,5 reduce la altura de un objeto en un 50 por ciento.</span><span class="sxs-lookup"><span data-stu-id="333ef-107">A <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> value of 0.5 shrinks the height of an object by 50 percent.</span></span> <span data-ttu-id="333ef-108">El código siguiente <xref:System.Windows.Media.Media3D.ScaleTransform3D> muestra el uso <xref:System.Windows.Media.Media3D.GeometryModel3D>de a como transformación para un archivo .</span><span class="sxs-lookup"><span data-stu-id="333ef-108">The code below shows using a <xref:System.Windows.Media.Media3D.ScaleTransform3D> as the transform for a <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="333ef-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="333ef-109">Example</span></span>  
 <span data-ttu-id="333ef-110">El código siguiente muestra el ejemplo completo.</span><span class="sxs-lookup"><span data-stu-id="333ef-110">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="333ef-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="333ef-111">See also</span></span>

- [<span data-ttu-id="333ef-112">Animate 3D Translations</span><span class="sxs-lookup"><span data-stu-id="333ef-112">Animate 3D Translations</span></span>](how-to-animate-3-d-translations.md)
- [<span data-ttu-id="333ef-113">Crear una escena 3D</span><span class="sxs-lookup"><span data-stu-id="333ef-113">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="333ef-114">Descripción general de los gráficos 3D</span><span class="sxs-lookup"><span data-stu-id="333ef-114">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
