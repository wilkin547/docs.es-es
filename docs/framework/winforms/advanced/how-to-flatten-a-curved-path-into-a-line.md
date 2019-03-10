---
title: Filtrar Aplanar un trazado curvo en una línea
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], flattening curves into lines
- curves [Windows Forms], flattening
- GraphicsPath object
- paths [Windows Forms], flattening
- drawing [Windows Forms], flattening curves
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
ms.openlocfilehash: d4847124c7af2e0b35d6874f53b85be4891b22df
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711049"
---
# <a name="how-to-flatten-a-curved-path-into-a-line"></a><span data-ttu-id="49020-102">Procedimiento Aplanar un trazado curvo en una línea</span><span class="sxs-lookup"><span data-stu-id="49020-102">How to: Flatten a Curved Path into a Line</span></span>
<span data-ttu-id="49020-103">Un <xref:System.Drawing.Drawing2D.GraphicsPath> objeto almacena una secuencia de líneas y curvas spline de Bézier.</span><span class="sxs-lookup"><span data-stu-id="49020-103">A <xref:System.Drawing.Drawing2D.GraphicsPath> object stores a sequence of lines and Bézier splines.</span></span> <span data-ttu-id="49020-104">Puede agregar varios tipos de curvas (elipses, arcos, curvas spline cardinales) a una ruta de acceso, pero se convierte cada curva en una curva spline de Bézier antes de almacenarse en la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="49020-104">You can add several types of curves (ellipses, arcs, cardinal splines) to a path, but each curve is converted to a Bézier spline before it is stored in the path.</span></span> <span data-ttu-id="49020-105">Acoplamiento de una ruta de acceso consiste en convertir cada curva spline de Bézier en la ruta de acceso a una secuencia de líneas rectas.</span><span class="sxs-lookup"><span data-stu-id="49020-105">Flattening a path consists of converting each Bézier spline in the path to a sequence of straight lines.</span></span> <span data-ttu-id="49020-106">La siguiente ilustración muestra una ruta de acceso antes y después de hacerlo.</span><span class="sxs-lookup"><span data-stu-id="49020-106">The following illustration shows a path before and after flattening.</span></span>  
  
 <span data-ttu-id="49020-107">![Líneas rectas y curvas](./media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span><span class="sxs-lookup"><span data-stu-id="49020-107">![Straight Lines and Curves](./media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span></span>  
  
### <a name="to-flatten-a-path"></a><span data-ttu-id="49020-108">Para aplanar un trazado</span><span class="sxs-lookup"><span data-stu-id="49020-108">To Flatten a Path</span></span>  
  
-   <span data-ttu-id="49020-109">Llame a la <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> método de un <xref:System.Drawing.Drawing2D.GraphicsPath> objeto.</span><span class="sxs-lookup"><span data-stu-id="49020-109">call the <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method of a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="49020-110">El <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> método recibe un argumento de aplanamiento que especifica la distancia máxima entre el trazado y la ruta de acceso original.</span><span class="sxs-lookup"><span data-stu-id="49020-110">The <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method receives a flatness argument that specifies the maximum distance between the flattened path and the original path.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49020-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="49020-111">See also</span></span>
- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- [<span data-ttu-id="49020-112">Líneas, curvas y formas</span><span class="sxs-lookup"><span data-stu-id="49020-112">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="49020-113">Crear y dibujar trazados</span><span class="sxs-lookup"><span data-stu-id="49020-113">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
