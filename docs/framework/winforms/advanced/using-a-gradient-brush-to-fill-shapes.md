---
title: Utilizar un pincel degradado para rellenar formas
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- brushes [Windows Forms], gradient brushes
- gradient brushes
- examples [Windows Forms], gradient brushes
ms.assetid: 2c6037b9-05bd-44c0-a22a-19584b722524
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6a84a68f9082d00559938c2710b6574690fa6ab4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="using-a-gradient-brush-to-fill-shapes"></a><span data-ttu-id="b43f1-102">Utilizar un pincel degradado para rellenar formas</span><span class="sxs-lookup"><span data-stu-id="b43f1-102">Using a Gradient Brush to Fill Shapes</span></span>
<span data-ttu-id="b43f1-103">Puede utilizar un pincel de degradado para rellenar una forma con un color que cambia gradualmente.</span><span class="sxs-lookup"><span data-stu-id="b43f1-103">You can use a gradient brush to fill a shape with a gradually changing color.</span></span> <span data-ttu-id="b43f1-104">Por ejemplo, puede utilizar un degradado horizontal para rellenar una forma con un color que cambia gradualmente a medida que se desplaza desde el borde izquierdo de la forma para el borde derecho.</span><span class="sxs-lookup"><span data-stu-id="b43f1-104">For example, you can use a horizontal gradient to fill a shape with color that changes gradually as you move from the left edge of the shape to the right edge.</span></span> <span data-ttu-id="b43f1-105">Imagine un rectángulo con un borde izquierdo es negro (representado por los componentes rojos, verde y azules 0, 0, 0) y un borde derecho de color rojo (representado por 255, 0, 0).</span><span class="sxs-lookup"><span data-stu-id="b43f1-105">Imagine a rectangle with a left edge that is black (represented by red, green, and blue components 0, 0, 0) and a right edge that is red (represented by 255, 0, 0).</span></span> <span data-ttu-id="b43f1-106">Si el rectángulo es 256 píxeles de ancho, el componente rojo de un píxel determinado será una unidad mayor que el componente rojo del píxel situado a su izquierda.</span><span class="sxs-lookup"><span data-stu-id="b43f1-106">If the rectangle is 256 pixels wide, the red component of a given pixel will be one greater than the red component of the pixel to its left.</span></span> <span data-ttu-id="b43f1-107">El píxel situado en una fila tiene componentes de color (0, 0, 0), el segundo tiene (1, 0, 0), el tercer píxel (2, 0, 0) y así sucesivamente, hasta llegar al píxel más a la derecha, que tiene componentes de color (255, 0, 0).</span><span class="sxs-lookup"><span data-stu-id="b43f1-107">The leftmost pixel in a row has color components (0, 0, 0), the second pixel has (1, 0, 0), the third pixel has (2, 0, 0), and so on, until you get to the rightmost pixel, which has color components (255, 0, 0).</span></span> <span data-ttu-id="b43f1-108">Estos valores de color interpolados forman el degradado de color.</span><span class="sxs-lookup"><span data-stu-id="b43f1-108">These interpolated color values make up the color gradient.</span></span>  
  
 <span data-ttu-id="b43f1-109">Un degradado lineal cambia de color se mueve horizontalmente, verticalmente o en paralelo a una línea inclinada especificada.</span><span class="sxs-lookup"><span data-stu-id="b43f1-109">A linear gradient changes color as you move horizontally, vertically, or parallel to a specified slanted line.</span></span> <span data-ttu-id="b43f1-110">Un degradado de trazado cambia de color se mueve sobre el interior y el límite de una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="b43f1-110">A path gradient changes color as you move about the interior and boundary of a path.</span></span> <span data-ttu-id="b43f1-111">Puede personalizar degradados de ruta de acceso para lograr una gran variedad de efectos.</span><span class="sxs-lookup"><span data-stu-id="b43f1-111">You can customize path gradients to achieve a wide variety of effects.</span></span>  
  
 <span data-ttu-id="b43f1-112">La ilustración siguiente muestra un rectángulo relleno con un pincel de degradado lineal y una elipse rellena con un pincel de degradado de trazado.</span><span class="sxs-lookup"><span data-stu-id="b43f1-112">The following illustration shows a rectangle filled with a linear gradient brush and an ellipse filled with a path gradient brush.</span></span>  
  
 <span data-ttu-id="b43f1-113">![Degradado](../../../../docs/framework/winforms/advanced/media/gradient2.png "gradient2")</span><span class="sxs-lookup"><span data-stu-id="b43f1-113">![Gradient](../../../../docs/framework/winforms/advanced/media/gradient2.png "gradient2")</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b43f1-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b43f1-114">In This Section</span></span>  
 [<span data-ttu-id="b43f1-115">Crear un degradado lineal</span><span class="sxs-lookup"><span data-stu-id="b43f1-115">How to: Create a Linear Gradient</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-linear-gradient.md)  
 <span data-ttu-id="b43f1-116">Muestra cómo crear un utilizando degradado lineal la <xref:System.Drawing.Drawing2D.LinearGradientBrush> clase.</span><span class="sxs-lookup"><span data-stu-id="b43f1-116">Shows how to create a linear gradient using the <xref:System.Drawing.Drawing2D.LinearGradientBrush> class.</span></span>  
  
 [<span data-ttu-id="b43f1-117">Crear un degradado de trazado</span><span class="sxs-lookup"><span data-stu-id="b43f1-117">How to: Create a Path Gradient</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-path-gradient.md)  
 <span data-ttu-id="b43f1-118">Describe cómo crear un degradado de ruta de acceso utilizando la <xref:System.Drawing.Drawing2D.PathGradientBrush> clase.</span><span class="sxs-lookup"><span data-stu-id="b43f1-118">Describes how to create a path gradient using the <xref:System.Drawing.Drawing2D.PathGradientBrush> class.</span></span>  
  
 [<span data-ttu-id="b43f1-119">Aplicar corrección gamma a un degradado</span><span class="sxs-lookup"><span data-stu-id="b43f1-119">How to: Apply Gamma Correction to a Gradient</span></span>](../../../../docs/framework/winforms/advanced/how-to-apply-gamma-correction-to-a-gradient.md)  
 <span data-ttu-id="b43f1-120">Explica cómo utilizar la corrección gamma con un pincel de degradado.</span><span class="sxs-lookup"><span data-stu-id="b43f1-120">Explains how to use gamma correction with a gradient brush.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="b43f1-121">Referencia</span><span class="sxs-lookup"><span data-stu-id="b43f1-121">Reference</span></span>  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 <span data-ttu-id="b43f1-122">Contiene una descripción de esta clase y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="b43f1-122">Contains a description of this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Drawing2D.PathGradientBrush?displayProperty=nameWithType>  
 <span data-ttu-id="b43f1-123">Contiene una descripción de esta clase y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="b43f1-123">Contains a description of this class and has links to all of its members.</span></span>
