---
title: Filtrar Dibujar curvas spline cardinales
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cardinal splines [Windows Forms], drawing
- drawing [Windows Forms], cardinal splines
- graphics [Windows Forms], cardinal splines
ms.assetid: a4a41e80-4461-4b47-b6bd-2c5e68881994
ms.openlocfilehash: 0f5c7a8555130e884b641648d1ffc9865f44dc1e
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2019
ms.locfileid: "58464702"
---
# <a name="how-to-draw-cardinal-splines"></a><span data-ttu-id="5af37-102">Filtrar Dibujar curvas spline cardinales</span><span class="sxs-lookup"><span data-stu-id="5af37-102">How to: Draw Cardinal Splines</span></span>
<span data-ttu-id="5af37-103">Una curva spline cardinal es una curva que se pasa sin problemas a través de un conjunto determinado de puntos.</span><span class="sxs-lookup"><span data-stu-id="5af37-103">A cardinal spline is a curve that passes smoothly through a given set of points.</span></span> <span data-ttu-id="5af37-104">Para dibujar una curva spline cardinal, cree un <xref:System.Drawing.Graphics> objeto y pasar la dirección de una matriz de puntos para el <xref:System.Drawing.Graphics.DrawCurve%2A> método.</span><span class="sxs-lookup"><span data-stu-id="5af37-104">To draw a cardinal spline, create a <xref:System.Drawing.Graphics> object and pass the address of an array of points to the <xref:System.Drawing.Graphics.DrawCurve%2A> method.</span></span>  
  
### <a name="drawing-a-bell-shaped-cardinal-spline"></a><span data-ttu-id="5af37-105">Dibujar una curva Cardinal Spline en forma de campana</span><span class="sxs-lookup"><span data-stu-id="5af37-105">Drawing a Bell-Shaped Cardinal Spline</span></span>  
  
-   <span data-ttu-id="5af37-106">El ejemplo siguiente dibuja una curva spline cardinal en forma de campana que pasa por cinco puntos designados.</span><span class="sxs-lookup"><span data-stu-id="5af37-106">The following example draws a bell-shaped cardinal spline that passes through five designated points.</span></span> <span data-ttu-id="5af37-107">La siguiente ilustración muestra la curva y cinco puntos.</span><span class="sxs-lookup"><span data-stu-id="5af37-107">The following illustration shows the curve and five points.</span></span>  
  
     ![Diagrama que muestra una curva spline cardinal en forma de campana.](./media/how-to-draw-cardinal-splines/bell-shaped-cardinal-spline.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#21)]  
  
### <a name="drawing-a-closed-cardinal-spline"></a><span data-ttu-id="5af37-109">Dibujar una curva Cardinal Spline cerrada</span><span class="sxs-lookup"><span data-stu-id="5af37-109">Drawing a Closed Cardinal Spline</span></span>  
  
-   <span data-ttu-id="5af37-110">Use la <xref:System.Drawing.Graphics.DrawClosedCurve%2A> método de la <xref:System.Drawing.Graphics> clase para dibujar una curva spline cardinal cerrada.</span><span class="sxs-lookup"><span data-stu-id="5af37-110">Use the <xref:System.Drawing.Graphics.DrawClosedCurve%2A> method of the <xref:System.Drawing.Graphics> class to draw a closed cardinal spline.</span></span> <span data-ttu-id="5af37-111">En una curva spline cardinal cerrada, la curva continúa hasta el último punto de la matriz y se conecta con el primer punto de la matriz.</span><span class="sxs-lookup"><span data-stu-id="5af37-111">In a closed cardinal spline, the curve continues through the last point in the array and connects with the first point in the array.</span></span> <span data-ttu-id="5af37-112">El ejemplo siguiente dibuja una curva spline cardinal cerrada que pasa por seis puntos designados.</span><span class="sxs-lookup"><span data-stu-id="5af37-112">The following example draws a closed cardinal spline that passes through six designated points.</span></span> <span data-ttu-id="5af37-113">La siguiente ilustración muestra la spline cerrada junto con los seis puntos:</span><span class="sxs-lookup"><span data-stu-id="5af37-113">The following illustration shows the closed spline along with the six points:</span></span>  
  
 ![Diagrama que muestra una curva spline cardinal cerrada.](./media/how-to-draw-cardinal-splines/closed-cardinal-spine.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#22)]  
  
### <a name="changing-the-bend-of-a-cardinal-spline"></a><span data-ttu-id="5af37-115">Cambiar el plegado de una curva Cardinal Spline</span><span class="sxs-lookup"><span data-stu-id="5af37-115">Changing the Bend of a Cardinal Spline</span></span>  
  
-   <span data-ttu-id="5af37-116">Cambiar la forma en la inclinación de una curva spline cardinal pasando un argumento de tensión el <xref:System.Drawing.Graphics.DrawCurve%2A> método.</span><span class="sxs-lookup"><span data-stu-id="5af37-116">Change the way a cardinal spline bends by passing a tension argument to the <xref:System.Drawing.Graphics.DrawCurve%2A> method.</span></span> <span data-ttu-id="5af37-117">El ejemplo siguiente dibuja tres curvas spline cardinales que pasan por el mismo conjunto de puntos.</span><span class="sxs-lookup"><span data-stu-id="5af37-117">The following example draws three cardinal splines that pass through the same set of points.</span></span> <span data-ttu-id="5af37-118">La siguiente ilustración muestra las tres curvas spline junto con sus valores de tensión.</span><span class="sxs-lookup"><span data-stu-id="5af37-118">The following illustration shows the three splines along with their tension values.</span></span> <span data-ttu-id="5af37-119">Tenga en cuenta que cuando la tensión es 0, los puntos están conectados mediante líneas rectas.</span><span class="sxs-lookup"><span data-stu-id="5af37-119">Note that when the tension is 0, the points are connected by straight lines.</span></span>  
  
 ![Diagrama que muestra tres curvas spline cardinales.](./media/how-to-draw-cardinal-splines/three-cardinal-splines.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#23)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5af37-121">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="5af37-121">Compiling the Code</span></span>  
 <span data-ttu-id="5af37-122">Los ejemplos anteriores están diseñados para su uso con Windows Forms y necesitan <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de la <xref:System.Windows.Forms.Control.Paint> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="5af37-122">The preceding examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5af37-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="5af37-123">See also</span></span>
- [<span data-ttu-id="5af37-124">Líneas, curvas y formas</span><span class="sxs-lookup"><span data-stu-id="5af37-124">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="5af37-125">Crear y dibujar curvas</span><span class="sxs-lookup"><span data-stu-id="5af37-125">Constructing and Drawing Curves</span></span>](constructing-and-drawing-curves.md)
