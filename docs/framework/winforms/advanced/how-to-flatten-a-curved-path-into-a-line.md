---
title: 'Cómo: Aplanar un trazado curvo en una línea'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], flattening curves into lines
- curves [Windows Forms], flattening
- GraphicsPath object
- paths [Windows Forms], flattening
- drawing [Windows Forms], flattening curves
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
ms.openlocfilehash: a3a8467dc5906a88911672316bb0f2ed3607d3a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521208"
---
# <a name="how-to-flatten-a-curved-path-into-a-line"></a><span data-ttu-id="3078c-102">Cómo: Aplanar un trazado curvo en una línea</span><span class="sxs-lookup"><span data-stu-id="3078c-102">How to: Flatten a Curved Path into a Line</span></span>
<span data-ttu-id="3078c-103">Un <xref:System.Drawing.Drawing2D.GraphicsPath> objeto almacena una secuencia de líneas y curvas spline de Bézier.</span><span class="sxs-lookup"><span data-stu-id="3078c-103">A <xref:System.Drawing.Drawing2D.GraphicsPath> object stores a sequence of lines and Bézier splines.</span></span> <span data-ttu-id="3078c-104">Puede agregar varios tipos de curvas (elipses, arcos, curvas spline cardinales) a una ruta de acceso, pero cada curva se convierte en una curva spline de Bézier antes de almacenarse en la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="3078c-104">You can add several types of curves (ellipses, arcs, cardinal splines) to a path, but each curve is converted to a Bézier spline before it is stored in the path.</span></span> <span data-ttu-id="3078c-105">Una ruta de acceso de aplanamiento consiste en convertir cada curva spline de Bézier en la ruta de acceso a una secuencia de líneas rectas.</span><span class="sxs-lookup"><span data-stu-id="3078c-105">Flattening a path consists of converting each Bézier spline in the path to a sequence of straight lines.</span></span> <span data-ttu-id="3078c-106">En la siguiente ilustración muestra una ruta de acceso antes y después de la reducción.</span><span class="sxs-lookup"><span data-stu-id="3078c-106">The following illustration shows a path before and after flattening.</span></span>  
  
 <span data-ttu-id="3078c-107">![Líneas rectas y curvas](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span><span class="sxs-lookup"><span data-stu-id="3078c-107">![Straight Lines and Curves](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span></span>  
  
### <a name="to-flatten-a-path"></a><span data-ttu-id="3078c-108">Para aplanar un trazado</span><span class="sxs-lookup"><span data-stu-id="3078c-108">To Flatten a Path</span></span>  
  
-   <span data-ttu-id="3078c-109">Llame a la <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> método de una <xref:System.Drawing.Drawing2D.GraphicsPath> objeto.</span><span class="sxs-lookup"><span data-stu-id="3078c-109">call the <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method of a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="3078c-110">El <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> método recibe un argumento de aplanamiento que especifica la distancia máxima entre el trazado aplanado y la ruta de acceso original.</span><span class="sxs-lookup"><span data-stu-id="3078c-110">The <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method receives a flatness argument that specifies the maximum distance between the flattened path and the original path.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3078c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="3078c-111">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>  
 [<span data-ttu-id="3078c-112">Líneas, curvas y formas</span><span class="sxs-lookup"><span data-stu-id="3078c-112">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="3078c-113">Crear y dibujar trazados</span><span class="sxs-lookup"><span data-stu-id="3078c-113">Constructing and Drawing Paths</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)
