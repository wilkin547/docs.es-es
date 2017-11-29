---
title: "Cómo: dibujar una sola B &#233; curva Spline de Bézier"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines [Windows Forms], drawing
- drawing [Windows Forms], Bezier splines
ms.assetid: f4f3fe30-f0a6-4743-ac91-11310cebea9f
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0ebdba9e01824cc764a6ab759da049add180ba83
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-a-single-b233zier-spline"></a><span data-ttu-id="11657-102">Cómo: dibujar una sola B &#233; curva Spline de Bézier</span><span class="sxs-lookup"><span data-stu-id="11657-102">How to: Draw a Single B&#233;zier Spline</span></span>
<span data-ttu-id="11657-103">Una curva spline de Bézier queda definida por cuatro puntos: un punto inicial, dos puntos de control y un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="11657-103">A Bézier spline is defined by four points: a start point, two control points, and an endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11657-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="11657-104">Example</span></span>  
 <span data-ttu-id="11657-105">En el ejemplo siguiente se dibuja una curva spline de Bézier con un punto de inicio (10, 100) y punto de conexión (200, 100).</span><span class="sxs-lookup"><span data-stu-id="11657-105">The following example draws a Bézier spline with start point (10, 100) and endpoint (200, 100).</span></span> <span data-ttu-id="11657-106">Los puntos de control son (100, 10) y (150, 150).</span><span class="sxs-lookup"><span data-stu-id="11657-106">The control points are (100, 10) and (150, 150).</span></span>  
  
 <span data-ttu-id="11657-107">La siguiente ilustración muestra la curva spline de Bézier resultante junto con su punto inicial, puntos de control y punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="11657-107">The following illustration shows the resulting Bézier spline along with its start point, control points, and endpoint.</span></span> <span data-ttu-id="11657-108">La ilustración también muestra convexa de la curva spline, que es un polígono formado mediante la conexión de cuatro puntos con líneas rectas.</span><span class="sxs-lookup"><span data-stu-id="11657-108">The illustration also shows the spline's convex hull, which is a polygon formed by connecting the four points with straight lines.</span></span>  
  
 <span data-ttu-id="11657-109">![B-Spline](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")</span><span class="sxs-lookup"><span data-stu-id="11657-109">![Bezier Spline](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="11657-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="11657-110">Compiling the Code</span></span>  
 <span data-ttu-id="11657-111">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="11657-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11657-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="11657-112">See Also</span></span>  
 <xref:System.Drawing.Graphics.DrawBezier%2A>  
 [<span data-ttu-id="11657-113">Curvas spline de Bézier en GDI+</span><span class="sxs-lookup"><span data-stu-id="11657-113">Bézier Splines in GDI+</span></span>](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)  
 [<span data-ttu-id="11657-114">Dibujar una secuencia de curvas spline de Bézier</span><span class="sxs-lookup"><span data-stu-id="11657-114">How to: Draw a Sequence of Bézier Splines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)
