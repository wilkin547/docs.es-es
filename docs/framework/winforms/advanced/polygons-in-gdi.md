---
title: Polígonos en GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- polygons
- drawing [Windows Forms], polygons
- GDI+, polygons
ms.assetid: a72213d2-d69a-4c2b-a75c-be7b20390c13
ms.openlocfilehash: 3ac6b9b651e65a45612cf2bd8ff17990c5cfba0f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525852"
---
# <a name="polygons-in-gdi"></a><span data-ttu-id="34524-102">Polígonos en GDI+</span><span class="sxs-lookup"><span data-stu-id="34524-102">Polygons in GDI+</span></span>
<span data-ttu-id="34524-103">Un polígono es una forma cerrada con tres o más líneas rectas.</span><span class="sxs-lookup"><span data-stu-id="34524-103">A polygon is a closed shape with three or more straight sides.</span></span> <span data-ttu-id="34524-104">Por ejemplo, un triángulo es un polígono con tres lados, un rectángulo es un polígono con cuatro lados y un Pentágono es un polígono con cinco lados.</span><span class="sxs-lookup"><span data-stu-id="34524-104">For example, a triangle is a polygon with three sides, a rectangle is a polygon with four sides, and a pentagon is a polygon with five sides.</span></span> <span data-ttu-id="34524-105">La ilustración siguiente muestra varios polígonos.</span><span class="sxs-lookup"><span data-stu-id="34524-105">The following illustration shows several polygons.</span></span>  
  
 <span data-ttu-id="34524-106">![Polígonos](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art07.gif "Aboutgdip02_art07")</span><span class="sxs-lookup"><span data-stu-id="34524-106">![Polygons](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art07.gif "Aboutgdip02_art07")</span></span>  
  
## <a name="drawing-a-polygon"></a><span data-ttu-id="34524-107">Dibujar un polígono</span><span class="sxs-lookup"><span data-stu-id="34524-107">Drawing a Polygon</span></span>  
 <span data-ttu-id="34524-108">Para dibujar un polígono, necesita un <xref:System.Drawing.Graphics> objeto, un <xref:System.Drawing.Pen> objeto y una matriz de <xref:System.Drawing.Point> (o <xref:System.Drawing.PointF>) objetos.</span><span class="sxs-lookup"><span data-stu-id="34524-108">To draw a polygon, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Pen> object, and an array of <xref:System.Drawing.Point> (or <xref:System.Drawing.PointF>) objects.</span></span> <span data-ttu-id="34524-109">El <xref:System.Drawing.Graphics> objeto proporciona el <xref:System.Drawing.Graphics.DrawPolygon%2A> método.</span><span class="sxs-lookup"><span data-stu-id="34524-109">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawPolygon%2A> method.</span></span> <span data-ttu-id="34524-110">El <xref:System.Drawing.Pen> objeto almacena atributos, como el ancho y color de la línea que se usa para representar el polígono y la matriz de <xref:System.Drawing.Point> objetos almacena los puntos que estén conectados mediante líneas rectas.</span><span class="sxs-lookup"><span data-stu-id="34524-110">The <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the polygon, and the array of <xref:System.Drawing.Point> objects stores the points to be connected by straight lines.</span></span> <span data-ttu-id="34524-111">El <xref:System.Drawing.Pen> objeto y la matriz de <xref:System.Drawing.Point> objetos se pasan como argumentos a la <xref:System.Drawing.Graphics.DrawPolygon%2A> método.</span><span class="sxs-lookup"><span data-stu-id="34524-111">The <xref:System.Drawing.Pen> object and the array of <xref:System.Drawing.Point> objects are passed as arguments to the <xref:System.Drawing.Graphics.DrawPolygon%2A> method.</span></span> <span data-ttu-id="34524-112">En el ejemplo siguiente se dibuja un polígono de tres lados.</span><span class="sxs-lookup"><span data-stu-id="34524-112">The following example draws a three-sided polygon.</span></span> <span data-ttu-id="34524-113">Tenga en cuenta que hay sólo tres puntos en `myPointArray`: (0, 0), (50, 30) y (30, 60).</span><span class="sxs-lookup"><span data-stu-id="34524-113">Note that there are only three points in `myPointArray`: (0, 0), (50, 30), and (30, 60).</span></span> <span data-ttu-id="34524-114">El <xref:System.Drawing.Graphics.DrawPolygon%2A> método cierra automáticamente el polígono debe dibujar una línea desde (30, 60) hacia el punto inicial (0, 0).</span><span class="sxs-lookup"><span data-stu-id="34524-114">The <xref:System.Drawing.Graphics.DrawPolygon%2A> method automatically closes the polygon by drawing a line from (30, 60) back to the starting point (0, 0).</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#111](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#111)]
 [!code-vb[LinesCurvesAndShapes#111](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#111)]  
  
 <span data-ttu-id="34524-115">En la siguiente ilustración se muestra el polígono.</span><span class="sxs-lookup"><span data-stu-id="34524-115">The following illustration shows the polygon.</span></span>  
  
 <span data-ttu-id="34524-116">![Polígono](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art08.gif "Aboutgdip02_art08")</span><span class="sxs-lookup"><span data-stu-id="34524-116">![Polygon](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art08.gif "Aboutgdip02_art08")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34524-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="34524-117">See Also</span></span>  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [<span data-ttu-id="34524-118">Líneas, curvas y formas</span><span class="sxs-lookup"><span data-stu-id="34524-118">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="34524-119">Crear un lápiz</span><span class="sxs-lookup"><span data-stu-id="34524-119">How to: Create a Pen</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)
