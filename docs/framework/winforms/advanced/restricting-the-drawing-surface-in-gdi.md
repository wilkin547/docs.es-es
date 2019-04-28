---
title: Limitar la superficie de dibujo en GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, clipping
- clipping [Windows Forms], using GDI+
- GDI+, restricting drawing surface
ms.assetid: 8b5f71d9-d2f0-4540-9c41-740f90fd4c26
ms.openlocfilehash: d0508166f905b45789ce638b03d0747dd6fa904e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61672645"
---
# <a name="restricting-the-drawing-surface-in-gdi"></a><span data-ttu-id="47829-102">Limitar la superficie de dibujo en GDI+</span><span class="sxs-lookup"><span data-stu-id="47829-102">Restricting the Drawing Surface in GDI+</span></span>
<span data-ttu-id="47829-103">Recortar implica la restricción del dibujo a un rectángulo o una región determinados.</span><span class="sxs-lookup"><span data-stu-id="47829-103">Clipping involves restricting drawing to a certain rectangle or region.</span></span> <span data-ttu-id="47829-104">La siguiente ilustración muestra la cadena "Hello" recortada en una región en forma de corazón.</span><span class="sxs-lookup"><span data-stu-id="47829-104">The following illustration shows the string "Hello" clipped to a heart-shaped region.</span></span>  
  
 <span data-ttu-id="47829-105">![Superficie de dibujo restringida](./media/aboutgdip02-art30.gif "AboutGdip02_Art30")</span><span class="sxs-lookup"><span data-stu-id="47829-105">![Restricted Drawing Surface](./media/aboutgdip02-art30.gif "AboutGdip02_Art30")</span></span>  
  
## <a name="clipping-with-regions"></a><span data-ttu-id="47829-106">Con regiones de recorte</span><span class="sxs-lookup"><span data-stu-id="47829-106">Clipping with Regions</span></span>  
 <span data-ttu-id="47829-107">Regiones pueden crearse a partir de las rutas de acceso y las rutas de acceso pueden contener los contornos de cadenas, por lo que puede usar texto con contorno para el recorte.</span><span class="sxs-lookup"><span data-stu-id="47829-107">Regions can be constructed from paths, and paths can contain the outlines of strings, so you can use outlined text for clipping.</span></span> <span data-ttu-id="47829-108">La siguiente ilustración muestra un conjunto de puntos suspensivos concéntricos recortada al interior de una cadena de texto.</span><span class="sxs-lookup"><span data-stu-id="47829-108">The following illustration shows a set of concentric ellipses clipped to the interior of a string of text.</span></span>  
  
 <span data-ttu-id="47829-109">![Superficie de dibujo restringida](./media/aboutgdip02-art31.gif "AboutGdip02_Art31")</span><span class="sxs-lookup"><span data-stu-id="47829-109">![Restricted Drawing Surface](./media/aboutgdip02-art31.gif "AboutGdip02_Art31")</span></span>  
  
 <span data-ttu-id="47829-110">Para dibujar con recorte, cree un <xref:System.Drawing.Graphics> de objetos, establezca su <xref:System.Drawing.Graphics.Clip%2A> propiedad y, a continuación, llame a los métodos de dibujo de ese mismo <xref:System.Drawing.Graphics> objeto:</span><span class="sxs-lookup"><span data-stu-id="47829-110">To draw with clipping, create a <xref:System.Drawing.Graphics> object, set its <xref:System.Drawing.Graphics.Clip%2A> property, and then call the drawing methods of that same <xref:System.Drawing.Graphics> object:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#91](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#91)]
 [!code-vb[LinesCurvesAndShapes#91](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#91)]  
  
## <a name="see-also"></a><span data-ttu-id="47829-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="47829-111">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Region?displayProperty=nameWithType>
- [<span data-ttu-id="47829-112">Líneas, curvas y formas</span><span class="sxs-lookup"><span data-stu-id="47829-112">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="47829-113">Utilizar regiones</span><span class="sxs-lookup"><span data-stu-id="47829-113">Using Regions</span></span>](using-regions.md)
