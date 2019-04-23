---
title: Procedimiento Dibujar un único B&#233;Spline de Bézier
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines [Windows Forms], drawing
- drawing [Windows Forms], Bezier splines
ms.assetid: f4f3fe30-f0a6-4743-ac91-11310cebea9f
ms.openlocfilehash: ebb53e7df979a553ed4a44deba34345c9ecac772
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59171683"
---
# <a name="how-to-draw-a-single-b233zier-spline"></a><span data-ttu-id="a8200-102">Procedimiento Dibujar un único B&#233;Spline de Bézier</span><span class="sxs-lookup"><span data-stu-id="a8200-102">How to: Draw a Single B&#233;zier Spline</span></span>
<span data-ttu-id="a8200-103">Una curva spline de Bézier queda definida por cuatro puntos: un punto inicial, dos puntos de control y un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="a8200-103">A Bézier spline is defined by four points: a start point, two control points, and an endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8200-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8200-104">Example</span></span>  
 <span data-ttu-id="a8200-105">El ejemplo siguiente dibuja una curva spline de Bézier con el punto inicial (10, 100) y el punto de conexión (200, 100).</span><span class="sxs-lookup"><span data-stu-id="a8200-105">The following example draws a Bézier spline with start point (10, 100) and endpoint (200, 100).</span></span> <span data-ttu-id="a8200-106">Los puntos de control son (100, 10) y (150, 150).</span><span class="sxs-lookup"><span data-stu-id="a8200-106">The control points are (100, 10) and (150, 150).</span></span>  
  
 <span data-ttu-id="a8200-107">La siguiente ilustración muestra la curva spline de Bézier resultante junto con su punto de inicio y puntos de control de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="a8200-107">The following illustration shows the resulting Bézier spline along with its start point, control points, and endpoint.</span></span> <span data-ttu-id="a8200-108">La ilustración también muestra las forma convexa de spline, que es un polígono formado mediante la conexión de cuatro puntos con líneas rectas.</span><span class="sxs-lookup"><span data-stu-id="a8200-108">The illustration also shows the spline's convex hull, which is a polygon formed by connecting the four points with straight lines.</span></span>  
  
 ![Ilustración de una curva Bézier Spline.](./media/how-to-draw-a-single-bezier-spline/bezier-spline-illustration.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a8200-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="a8200-110">Compiling the Code</span></span>  
 <span data-ttu-id="a8200-111">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de la <xref:System.Windows.Forms.Control.Paint> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="a8200-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8200-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8200-112">See also</span></span>

- <xref:System.Drawing.Graphics.DrawBezier%2A>
- [<span data-ttu-id="a8200-113">Curvas spline de Bézier en GDI+</span><span class="sxs-lookup"><span data-stu-id="a8200-113">Bézier Splines in GDI+</span></span>](bezier-splines-in-gdi.md)
- [<span data-ttu-id="a8200-114">Cómo: Dibujar una secuencia de curvas spline de Bézier</span><span class="sxs-lookup"><span data-stu-id="a8200-114">How to: Draw a Sequence of Bézier Splines</span></span>](how-to-draw-a-sequence-of-bezier-splines.md)
