---
title: Filtrar Dibujar una secuencia de B&#233;curvas spline de Bézier
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- splines [Windows Forms], drawing Bezier
- Bezier splines [Windows Forms], drawing sequence of
ms.assetid: 37a0bedb-20c2-4cf0-91fa-a5509e826b30
ms.openlocfilehash: 1de2f44be189cb2ff874a748ae6093c945120178
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711806"
---
# <a name="how-to-draw-a-sequence-of-b233zier-splines"></a><span data-ttu-id="83bcf-102">Filtrar Dibujar una secuencia de B&#233;curvas spline de Bézier</span><span class="sxs-lookup"><span data-stu-id="83bcf-102">How to: Draw a Sequence of B&#233;zier Splines</span></span>
<span data-ttu-id="83bcf-103">Puede usar el <xref:System.Drawing.Graphics.DrawBeziers%2A> método de la <xref:System.Drawing.Graphics> conectado de clase para dibujar una secuencia de curvas spline de Bézier.</span><span class="sxs-lookup"><span data-stu-id="83bcf-103">You can use the <xref:System.Drawing.Graphics.DrawBeziers%2A> method of the <xref:System.Drawing.Graphics> class to draw a sequence of connected Bézier splines.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83bcf-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="83bcf-104">Example</span></span>  
 <span data-ttu-id="83bcf-105">El ejemplo siguiente dibuja una curva que consta de dos curvas spline de Bézier conectadas.</span><span class="sxs-lookup"><span data-stu-id="83bcf-105">The following example draws a curve that consists of two connected Bézier splines.</span></span> <span data-ttu-id="83bcf-106">El punto de conexión de la primera curva spline de Bézier es el punto inicial de la segunda curva spline de Bézier.</span><span class="sxs-lookup"><span data-stu-id="83bcf-106">The endpoint of the first Bézier spline is the start point of the second Bézier spline.</span></span>  
  
 <span data-ttu-id="83bcf-107">La siguiente ilustración muestra las curvas spline conectada junto con los siete puntos.</span><span class="sxs-lookup"><span data-stu-id="83bcf-107">The following illustration shows the connected splines along with the seven points.</span></span>  
  
 <span data-ttu-id="83bcf-108">![Curva Bézier Spline](./media/bezierspline2.png "BezierSpline2")</span><span class="sxs-lookup"><span data-stu-id="83bcf-108">![Bezier Spline](./media/bezierspline2.png "BezierSpline2")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="83bcf-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="83bcf-109">Compiling the Code</span></span>  
 <span data-ttu-id="83bcf-110">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="83bcf-110">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83bcf-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="83bcf-111">See also</span></span>
- [<span data-ttu-id="83bcf-112">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="83bcf-112">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="83bcf-113">Curvas spline de Bézier en GDI+</span><span class="sxs-lookup"><span data-stu-id="83bcf-113">Bézier Splines in GDI+</span></span>](bezier-splines-in-gdi.md)
- [<span data-ttu-id="83bcf-114">Crear y dibujar curvas</span><span class="sxs-lookup"><span data-stu-id="83bcf-114">Constructing and Drawing Curves</span></span>](constructing-and-drawing-curves.md)
