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
ms.openlocfilehash: d59a802618ddd5080c651e822ed4c09641f7f170
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645364"
---
# <a name="how-to-flatten-a-curved-path-into-a-line"></a><span data-ttu-id="35dd8-102">Procedimiento para aplanar un trazado curvo en una línea</span><span class="sxs-lookup"><span data-stu-id="35dd8-102">How to: Flatten a Curved Path into a Line</span></span>
<span data-ttu-id="35dd8-103">Un <xref:System.Drawing.Drawing2D.GraphicsPath> objeto almacena una secuencia de líneas y curvas spline de Bézier.</span><span class="sxs-lookup"><span data-stu-id="35dd8-103">A <xref:System.Drawing.Drawing2D.GraphicsPath> object stores a sequence of lines and Bézier splines.</span></span> <span data-ttu-id="35dd8-104">Puede agregar varios tipos de curvas (elipses, arcos, curvas spline cardinales) a una ruta de acceso, pero se convierte cada curva en una curva spline de Bézier antes de almacenarse en la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="35dd8-104">You can add several types of curves (ellipses, arcs, cardinal splines) to a path, but each curve is converted to a Bézier spline before it is stored in the path.</span></span> <span data-ttu-id="35dd8-105">Acoplamiento de una ruta de acceso consiste en convertir cada curva spline de Bézier en la ruta de acceso a una secuencia de líneas rectas.</span><span class="sxs-lookup"><span data-stu-id="35dd8-105">Flattening a path consists of converting each Bézier spline in the path to a sequence of straight lines.</span></span> <span data-ttu-id="35dd8-106">La siguiente ilustración muestra una ruta de acceso antes y después de hacerlo.</span><span class="sxs-lookup"><span data-stu-id="35dd8-106">The following illustration shows a path before and after flattening.</span></span>  
  
 <span data-ttu-id="35dd8-107">![Líneas rectas y curvas](./media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span><span class="sxs-lookup"><span data-stu-id="35dd8-107">![Straight Lines and Curves](./media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span></span>  
  
### <a name="to-flatten-a-path"></a><span data-ttu-id="35dd8-108">Para aplanar un trazado</span><span class="sxs-lookup"><span data-stu-id="35dd8-108">To Flatten a Path</span></span>  
  
- <span data-ttu-id="35dd8-109">Llame a la <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> método de un <xref:System.Drawing.Drawing2D.GraphicsPath> objeto.</span><span class="sxs-lookup"><span data-stu-id="35dd8-109">call the <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method of a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="35dd8-110">El <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> método recibe un argumento de aplanamiento que especifica la distancia máxima entre el trazado y la ruta de acceso original.</span><span class="sxs-lookup"><span data-stu-id="35dd8-110">The <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method receives a flatness argument that specifies the maximum distance between the flattened path and the original path.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35dd8-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="35dd8-111">See also</span></span>

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- [<span data-ttu-id="35dd8-112">Líneas, curvas y formas</span><span class="sxs-lookup"><span data-stu-id="35dd8-112">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="35dd8-113">Crear y dibujar trazados</span><span class="sxs-lookup"><span data-stu-id="35dd8-113">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
