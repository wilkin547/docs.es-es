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
ms.openlocfilehash: 2b74b03137d5a450fb1e436a514877d1a17229ad
ms.sourcegitcommit: 15ab532fd5e1f8073a4b678922d93b68b521bfa0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "58654255"
---
# <a name="how-to-draw-a-sequence-of-b233zier-splines"></a><span data-ttu-id="f4357-102">Filtrar Dibujar una secuencia de B&#233;curvas spline de Bézier</span><span class="sxs-lookup"><span data-stu-id="f4357-102">How to: Draw a Sequence of B&#233;zier Splines</span></span>
<span data-ttu-id="f4357-103">Puede usar el <xref:System.Drawing.Graphics.DrawBeziers%2A> método de la <xref:System.Drawing.Graphics> conectado de clase para dibujar una secuencia de curvas spline de Bézier.</span><span class="sxs-lookup"><span data-stu-id="f4357-103">You can use the <xref:System.Drawing.Graphics.DrawBeziers%2A> method of the <xref:System.Drawing.Graphics> class to draw a sequence of connected Bézier splines.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4357-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f4357-104">Example</span></span>  
 <span data-ttu-id="f4357-105">El ejemplo siguiente dibuja una curva que consta de dos curvas spline de Bézier conectadas.</span><span class="sxs-lookup"><span data-stu-id="f4357-105">The following example draws a curve that consists of two connected Bézier splines.</span></span> <span data-ttu-id="f4357-106">El punto de conexión de la primera curva spline de Bézier es el punto inicial de la segunda curva spline de Bézier.</span><span class="sxs-lookup"><span data-stu-id="f4357-106">The endpoint of the first Bézier spline is the start point of the second Bézier spline.</span></span>  
  
 <span data-ttu-id="f4357-107">La siguiente ilustración muestra las curvas spline conectada junto con los siete puntos:</span><span class="sxs-lookup"><span data-stu-id="f4357-107">The following illustration shows the connected splines along with the seven points:</span></span>  
  
 ![Gráfico que muestra las curvas spline conectada junto con los siete puntos.](./media/how-to-draw-a-sequence-of-bezier-splines/bezier-spline-seven-points.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f4357-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="f4357-109">Compiling the Code</span></span>  
 <span data-ttu-id="f4357-110">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de la <xref:System.Windows.Forms.Control.Paint> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="f4357-110">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4357-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4357-111">See also</span></span>
- [<span data-ttu-id="f4357-112">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f4357-112">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="f4357-113">Curvas spline de Bézier en GDI+</span><span class="sxs-lookup"><span data-stu-id="f4357-113">Bézier Splines in GDI+</span></span>](bezier-splines-in-gdi.md)
- [<span data-ttu-id="f4357-114">Crear y dibujar curvas</span><span class="sxs-lookup"><span data-stu-id="f4357-114">Constructing and Drawing Curves</span></span>](constructing-and-drawing-curves.md)
