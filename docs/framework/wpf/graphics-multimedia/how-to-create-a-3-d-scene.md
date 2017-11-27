---
title: "Cómo: Crear una escena 3D"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scenes [WPF], 3-D
- 3-D scenes
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dd84a95bf793b3da9970b605b2f02509e3938ab0
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-create-a-3-d-scene"></a><span data-ttu-id="da993-102">Cómo: Crear una escena 3D</span><span class="sxs-lookup"><span data-stu-id="da993-102">How to: Create a 3-D Scene</span></span>
<span data-ttu-id="da993-103">En este ejemplo se muestra cómo crear un objeto 3D que parece una hoja de papel que se ha girado plana.</span><span class="sxs-lookup"><span data-stu-id="da993-103">This example shows how to create a 3-D object that looks like a flat sheet of paper which has been rotated.</span></span> <span data-ttu-id="da993-104">Un <xref:System.Windows.Controls.Viewport3D> junto con los siguientes componentes se utilizan para crear esta escena 3D sencilla:</span><span class="sxs-lookup"><span data-stu-id="da993-104">A <xref:System.Windows.Controls.Viewport3D> along with the following components are used to create this simple 3-D scene:</span></span>  
  
-   <span data-ttu-id="da993-105">Se crea una cámara mediante un <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span><span class="sxs-lookup"><span data-stu-id="da993-105">A camera is created using a <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span></span> <span data-ttu-id="da993-106">La cámara especifica qué parte de la escena 3D es visible.</span><span class="sxs-lookup"><span data-stu-id="da993-106">The camera specifies what part of the 3-D scene is viewable.</span></span>  
  
-   <span data-ttu-id="da993-107">Se crea una malla para especificar la forma de objeto 3D (hoja de papel) mediante la <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> propiedad de <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="da993-107">A mesh is created to specify the shape of 3-D object (sheet of paper) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
-   <span data-ttu-id="da993-108">Se especifica el material que se mostrará en la superficie del objeto (degradado lineal en este ejemplo) con el <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> propiedad de <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="da993-108">A material is specified to be displayed on the surface of the object (linear gradient in this sample) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
-   <span data-ttu-id="da993-109">Se crea una luz para destacar en el objeto utilizando <xref:System.Windows.Media.Media3D.DirectionalLight>.</span><span class="sxs-lookup"><span data-stu-id="da993-109">A light is created to shine on the object using <xref:System.Windows.Media.Media3D.DirectionalLight>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da993-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="da993-110">Example</span></span>  
 <span data-ttu-id="da993-111">El código siguiente muestra cómo crear una escena 3D en XAML.</span><span class="sxs-lookup"><span data-stu-id="da993-111">The code below shows how to create a 3-D scene in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="da993-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="da993-112">Example</span></span>  
 <span data-ttu-id="da993-113">El código siguiente muestra cómo crear la misma escena 3D en código de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="da993-113">The code below shows how to create the same 3-D scene in procedural code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="da993-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="da993-114">See Also</span></span>  
 [<span data-ttu-id="da993-115">Información general sobre gráficos 3D</span><span class="sxs-lookup"><span data-stu-id="da993-115">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
