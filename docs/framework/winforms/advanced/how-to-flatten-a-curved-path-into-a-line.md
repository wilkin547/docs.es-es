---
title: Procedimiento para aplanar un trazado curvo en una línea
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], flattening curves into lines
- curves [Windows Forms], flattening
- GraphicsPath object
- paths [Windows Forms], flattening
- drawing [Windows Forms], flattening curves
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
ms.openlocfilehash: a151b4244e14d3704fd5fa1c55de92211981232f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781373"
---
# <a name="how-to-flatten-a-curved-path-into-a-line"></a><span data-ttu-id="5b973-102">Procedimiento para aplanar un trazado curvo en una línea</span><span class="sxs-lookup"><span data-stu-id="5b973-102">How to: Flatten a Curved Path into a Line</span></span>
<span data-ttu-id="5b973-103">Un <xref:System.Drawing.Drawing2D.GraphicsPath> objeto almacena una secuencia de líneas y curvas spline de Bézier.</span><span class="sxs-lookup"><span data-stu-id="5b973-103">A <xref:System.Drawing.Drawing2D.GraphicsPath> object stores a sequence of lines and Bézier splines.</span></span> <span data-ttu-id="5b973-104">Puede agregar varios tipos de curvas (elipses, arcos, curvas spline cardinales) a una ruta de acceso, pero se convierte cada curva en una curva spline de Bézier antes de almacenarse en la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="5b973-104">You can add several types of curves (ellipses, arcs, cardinal splines) to a path, but each curve is converted to a Bézier spline before it is stored in the path.</span></span> <span data-ttu-id="5b973-105">Acoplamiento de una ruta de acceso consiste en convertir cada curva spline de Bézier en la ruta de acceso a una secuencia de líneas rectas.</span><span class="sxs-lookup"><span data-stu-id="5b973-105">Flattening a path consists of converting each Bézier spline in the path to a sequence of straight lines.</span></span> <span data-ttu-id="5b973-106">La siguiente ilustración muestra una ruta de acceso antes y después de hacerlo.</span><span class="sxs-lookup"><span data-stu-id="5b973-106">The following illustration shows a path before and after flattening.</span></span>  
  
 <span data-ttu-id="5b973-107">![Líneas rectas y curvas](./media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span><span class="sxs-lookup"><span data-stu-id="5b973-107">![Straight Lines and Curves](./media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span></span>  
  
### <a name="to-flatten-a-path"></a><span data-ttu-id="5b973-108">Para aplanar un trazado</span><span class="sxs-lookup"><span data-stu-id="5b973-108">To Flatten a Path</span></span>  
  
- <span data-ttu-id="5b973-109">Llame a la <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> método de un <xref:System.Drawing.Drawing2D.GraphicsPath> objeto.</span><span class="sxs-lookup"><span data-stu-id="5b973-109">call the <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method of a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="5b973-110">El <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> método recibe un argumento de aplanamiento que especifica la distancia máxima entre el trazado y la ruta de acceso original.</span><span class="sxs-lookup"><span data-stu-id="5b973-110">The <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method receives a flatness argument that specifies the maximum distance between the flattened path and the original path.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b973-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b973-111">See also</span></span>

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- [<span data-ttu-id="5b973-112">Líneas, curvas y formas</span><span class="sxs-lookup"><span data-stu-id="5b973-112">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="5b973-113">Crear y dibujar trazados</span><span class="sxs-lookup"><span data-stu-id="5b973-113">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
