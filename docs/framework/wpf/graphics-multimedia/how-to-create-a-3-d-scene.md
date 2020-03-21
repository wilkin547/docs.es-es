---
title: 'Cómo: Crear una escena 3D'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scenes [WPF], 3D
- 3D scenes
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
ms.openlocfilehash: 36453894e06e7b59f339c21713449140c17f6851
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112107"
---
# <a name="how-to-create-a-3d-scene"></a><span data-ttu-id="cbfcf-102">Cómo: Crear una escena 3D</span><span class="sxs-lookup"><span data-stu-id="cbfcf-102">How to: Create a 3D Scene</span></span>
<span data-ttu-id="cbfcf-103">En este ejemplo se muestra cómo crear un objeto 3D que se parece a una hoja plana de papel que se ha girado.</span><span class="sxs-lookup"><span data-stu-id="cbfcf-103">This example shows how to create a 3D object that looks like a flat sheet of paper which has been rotated.</span></span> <span data-ttu-id="cbfcf-104">A <xref:System.Windows.Controls.Viewport3D> junto con los siguientes componentes se utilizan para crear esta escena 3D simple:</span><span class="sxs-lookup"><span data-stu-id="cbfcf-104">A <xref:System.Windows.Controls.Viewport3D> along with the following components are used to create this simple 3D scene:</span></span>  
  
- <span data-ttu-id="cbfcf-105">Se crea una <xref:System.Windows.Media.Media3D.PerspectiveCamera>cámara con un archivo .</span><span class="sxs-lookup"><span data-stu-id="cbfcf-105">A camera is created using a <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span></span> <span data-ttu-id="cbfcf-106">La cámara especifica qué parte de la escena 3D es visible.</span><span class="sxs-lookup"><span data-stu-id="cbfcf-106">The camera specifies what part of the 3D scene is viewable.</span></span>  
  
- <span data-ttu-id="cbfcf-107">Se crea una malla para especificar la forma del objeto <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> 3D (hoja de papel) utilizando la propiedad de <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="cbfcf-107">A mesh is created to specify the shape of 3D object (sheet of paper) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
- <span data-ttu-id="cbfcf-108">Se especifica que se especifique un material que se mostrará en la <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> superficie <xref:System.Windows.Media.Media3D.GeometryModel3D>del objeto (gradiente lineal en esta muestra) utilizando la propiedad de .</span><span class="sxs-lookup"><span data-stu-id="cbfcf-108">A material is specified to be displayed on the surface of the object (linear gradient in this sample) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
- <span data-ttu-id="cbfcf-109">Se crea una luz para <xref:System.Windows.Media.Media3D.DirectionalLight>brillar sobre el objeto utilizando .</span><span class="sxs-lookup"><span data-stu-id="cbfcf-109">A light is created to shine on the object using <xref:System.Windows.Media.Media3D.DirectionalLight>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cbfcf-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cbfcf-110">Example</span></span>  
 <span data-ttu-id="cbfcf-111">El código siguiente muestra cómo crear una escena 3D en XAML.</span><span class="sxs-lookup"><span data-stu-id="cbfcf-111">The code below shows how to create a 3D scene in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="cbfcf-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cbfcf-112">Example</span></span>  
 <span data-ttu-id="cbfcf-113">El código siguiente muestra cómo crear la misma escena 3D en código de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="cbfcf-113">The code below shows how to create the same 3D scene in procedural code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="cbfcf-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cbfcf-114">See also</span></span>

- [<span data-ttu-id="cbfcf-115">Descripción general de los gráficos 3D</span><span class="sxs-lookup"><span data-stu-id="cbfcf-115">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
