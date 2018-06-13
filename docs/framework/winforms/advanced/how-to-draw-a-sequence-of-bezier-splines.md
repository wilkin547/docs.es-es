---
title: 'Cómo: dibujar una secuencia de B&#233;curvas spline de Bézier'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- splines [Windows Forms], drawing Bezier
- Bezier splines [Windows Forms], drawing sequence of
ms.assetid: 37a0bedb-20c2-4cf0-91fa-a5509e826b30
ms.openlocfilehash: 8439e08109630b9a59c8e0359aa4d18e5241412c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521412"
---
# <a name="how-to-draw-a-sequence-of-b233zier-splines"></a><span data-ttu-id="c7621-102">Cómo: dibujar una secuencia de B&#233;curvas spline de Bézier</span><span class="sxs-lookup"><span data-stu-id="c7621-102">How to: Draw a Sequence of B&#233;zier Splines</span></span>
<span data-ttu-id="c7621-103">Puede usar el <xref:System.Drawing.Graphics.DrawBeziers%2A> método de la <xref:System.Drawing.Graphics> conectado de clase para dibujar una secuencia de curvas spline de Bézier.</span><span class="sxs-lookup"><span data-stu-id="c7621-103">You can use the <xref:System.Drawing.Graphics.DrawBeziers%2A> method of the <xref:System.Drawing.Graphics> class to draw a sequence of connected Bézier splines.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7621-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c7621-104">Example</span></span>  
 <span data-ttu-id="c7621-105">En el ejemplo siguiente se dibuja una curva formada por dos curvas spline de Bézier conectadas.</span><span class="sxs-lookup"><span data-stu-id="c7621-105">The following example draws a curve that consists of two connected Bézier splines.</span></span> <span data-ttu-id="c7621-106">El punto de conexión de la primera curva spline de Bézier es el punto inicial de la segunda curva spline de Bézier.</span><span class="sxs-lookup"><span data-stu-id="c7621-106">The endpoint of the first Bézier spline is the start point of the second Bézier spline.</span></span>  
  
 <span data-ttu-id="c7621-107">La siguiente ilustración muestra la curvas spline conectadas junto con los siete puntos.</span><span class="sxs-lookup"><span data-stu-id="c7621-107">The following illustration shows the connected splines along with the seven points.</span></span>  
  
 <span data-ttu-id="c7621-108">![B-Spline](../../../../docs/framework/winforms/advanced/media/bezierspline2.png "BezierSpline2")</span><span class="sxs-lookup"><span data-stu-id="c7621-108">![Bezier Spline](../../../../docs/framework/winforms/advanced/media/bezierspline2.png "BezierSpline2")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c7621-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="c7621-109">Compiling the Code</span></span>  
 <span data-ttu-id="c7621-110">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="c7621-110">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7621-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7621-111">See Also</span></span>  
 [<span data-ttu-id="c7621-112">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c7621-112">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="c7621-113">Curvas spline de Bézier en GDI+</span><span class="sxs-lookup"><span data-stu-id="c7621-113">Bézier Splines in GDI+</span></span>](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)  
 [<span data-ttu-id="c7621-114">Crear y dibujar curvas</span><span class="sxs-lookup"><span data-stu-id="c7621-114">Constructing and Drawing Curves</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)
