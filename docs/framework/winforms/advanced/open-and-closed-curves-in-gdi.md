---
title: Curvas abiertas y cerradas en GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- curves [Windows Forms], filling
- GDI+, curves
- curves [Windows Forms], drawing
- curves
ms.assetid: 08d2cc9a-dc9d-4eed-bcbb-2c8e2ca5d3ae
ms.openlocfilehash: 06afdc4549f7c3c9b0636e5c7052dcca87a153f1
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505455"
---
# <a name="open-and-closed-curves-in-gdi"></a><span data-ttu-id="47446-102">Curvas abiertas y cerradas en GDI+</span><span class="sxs-lookup"><span data-stu-id="47446-102">Open and Closed Curves in GDI+</span></span>
<span data-ttu-id="47446-103">La siguiente ilustración muestra dos curvas: una abierta y otra cerrada.</span><span class="sxs-lookup"><span data-stu-id="47446-103">The following illustration shows two curves: one open and one closed.</span></span>  
  
 <span data-ttu-id="47446-104">![Curvas abiertas y cerradas](./media/aboutgdip02-art24.gif "Aboutgdip02_art24")</span><span class="sxs-lookup"><span data-stu-id="47446-104">![Open & Closed curves](./media/aboutgdip02-art24.gif "Aboutgdip02_art24")</span></span>  
  
## <a name="managed-interface-for-curves"></a><span data-ttu-id="47446-105">Interfaz administrada para curvas</span><span class="sxs-lookup"><span data-stu-id="47446-105">Managed Interface for Curves</span></span>  
 <span data-ttu-id="47446-106">Curvas cerradas tienen un interior y por lo tanto, se pueden rellenar con un pincel.</span><span class="sxs-lookup"><span data-stu-id="47446-106">Closed curves have an interior and therefore can be filled with a brush.</span></span> <span data-ttu-id="47446-107">El <xref:System.Drawing.Graphics> en GDI + clase proporciona los siguientes métodos para rellenar curvas y formas cerradas: <xref:System.Drawing.Graphics.FillRectangle%2A>, <xref:System.Drawing.Graphics.FillEllipse%2A>, <xref:System.Drawing.Graphics.FillPie%2A>, <xref:System.Drawing.Graphics.FillPolygon%2A>, <xref:System.Drawing.Graphics.FillClosedCurve%2A>, <xref:System.Drawing.Graphics.FillPath%2A>, y <xref:System.Drawing.Graphics.FillRegion%2A>.</span><span class="sxs-lookup"><span data-stu-id="47446-107">The <xref:System.Drawing.Graphics> class in GDI+ provides the following methods for filling closed shapes and curves: <xref:System.Drawing.Graphics.FillRectangle%2A>, <xref:System.Drawing.Graphics.FillEllipse%2A>, <xref:System.Drawing.Graphics.FillPie%2A>, <xref:System.Drawing.Graphics.FillPolygon%2A>, <xref:System.Drawing.Graphics.FillClosedCurve%2A>, <xref:System.Drawing.Graphics.FillPath%2A>, and <xref:System.Drawing.Graphics.FillRegion%2A>.</span></span> <span data-ttu-id="47446-108">Cuando llame a uno de estos métodos, debe pasar uno de los tipos de pincel (<xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, o <xref:System.Drawing.Drawing2D.PathGradientBrush>) como argumento.</span><span class="sxs-lookup"><span data-stu-id="47446-108">Whenever you call one of these methods, you must pass one of the specific brush types (<xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, or <xref:System.Drawing.Drawing2D.PathGradientBrush>) as an argument.</span></span>  
  
 <span data-ttu-id="47446-109">El <xref:System.Drawing.Graphics.FillPie%2A> método es un complemento para el <xref:System.Drawing.Graphics.DrawArc%2A> método.</span><span class="sxs-lookup"><span data-stu-id="47446-109">The <xref:System.Drawing.Graphics.FillPie%2A> method is a companion to the <xref:System.Drawing.Graphics.DrawArc%2A> method.</span></span> <span data-ttu-id="47446-110">Al igual que el <xref:System.Drawing.Graphics.DrawArc%2A> método dibuja una parte del contorno de una elipse, la <xref:System.Drawing.Graphics.FillPie%2A> método rellena una parte del interior de una elipse.</span><span class="sxs-lookup"><span data-stu-id="47446-110">Just as the <xref:System.Drawing.Graphics.DrawArc%2A> method draws a portion of the outline of an ellipse, the <xref:System.Drawing.Graphics.FillPie%2A> method fills a portion of the interior of an ellipse.</span></span> <span data-ttu-id="47446-111">El ejemplo siguiente dibuja un arco y rellena la parte correspondiente del interior de la elipse:</span><span class="sxs-lookup"><span data-stu-id="47446-111">The following example draws an arc and fills the corresponding portion of the interior of the ellipse:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#21](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#21)]
 [!code-vb[LinesCurvesAndShapes#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#21)]  
  
 <span data-ttu-id="47446-112">La siguiente ilustración muestra el arco y el sector relleno.</span><span class="sxs-lookup"><span data-stu-id="47446-112">The following illustration shows the arc and the filled pie.</span></span>  
  
 <span data-ttu-id="47446-113">![Curvas abiertas y cerradas](./media/aboutgdip02-art25.gif "Aboutgdip02_art25")</span><span class="sxs-lookup"><span data-stu-id="47446-113">![Open & Closed curves](./media/aboutgdip02-art25.gif "Aboutgdip02_art25")</span></span>  
  
 <span data-ttu-id="47446-114">El <xref:System.Drawing.Graphics.FillClosedCurve%2A> método es un complemento para el <xref:System.Drawing.Graphics.DrawClosedCurve%2A> método.</span><span class="sxs-lookup"><span data-stu-id="47446-114">The <xref:System.Drawing.Graphics.FillClosedCurve%2A> method is a companion to the <xref:System.Drawing.Graphics.DrawClosedCurve%2A> method.</span></span> <span data-ttu-id="47446-115">Ambos métodos cerrará automáticamente la curva conectando el punto final para el punto de partida.</span><span class="sxs-lookup"><span data-stu-id="47446-115">Both methods automatically close the curve by connecting the ending point to the starting point.</span></span> <span data-ttu-id="47446-116">En el ejemplo siguiente se dibuja una curva que pasa a través de (0, 0), (60, 20) y (40, 50).</span><span class="sxs-lookup"><span data-stu-id="47446-116">The following example draws a curve that passes through (0, 0), (60, 20), and (40, 50).</span></span> <span data-ttu-id="47446-117">A continuación, la curva se cierra automáticamente mediante la conexión (40, 50) hasta el punto inicial (0, 0), y el interior se rellena con un color sólido.</span><span class="sxs-lookup"><span data-stu-id="47446-117">Then, the curve is automatically closed by connecting (40, 50) to the starting point (0, 0), and the interior is filled with a solid color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#22](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#22)]
 [!code-vb[LinesCurvesAndShapes#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#22)]  
  
 <span data-ttu-id="47446-118">El <xref:System.Drawing.Graphics.FillPath%2A> método rellena el interior de las partes independientes de una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="47446-118">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the interiors of the separate pieces of a path.</span></span> <span data-ttu-id="47446-119">Si una parte de una ruta de acceso no forma una curva cerrada o una forma, el <xref:System.Drawing.Graphics.FillPath%2A> método cierra automáticamente esa parte de la ruta de acceso antes de llenarlo.</span><span class="sxs-lookup"><span data-stu-id="47446-119">If a piece of a path doesn't form a closed curve or shape, the <xref:System.Drawing.Graphics.FillPath%2A> method automatically closes that piece of the path before filling it.</span></span> <span data-ttu-id="47446-120">El ejemplo siguiente se dibuja y rellena una ruta de acceso que consta de un arco, una curva spline cardinal, una cadena y un gráfico circular:</span><span class="sxs-lookup"><span data-stu-id="47446-120">The following example draws and fills a path that consists of an arc, a cardinal spline, a string, and a pie:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#23](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#23)]
 [!code-vb[LinesCurvesAndShapes#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#23)]  
  
 <span data-ttu-id="47446-121">La siguiente ilustración muestra la ruta de acceso con y sin el relleno sólido.</span><span class="sxs-lookup"><span data-stu-id="47446-121">The following illustration shows the path with and without the solid fill.</span></span> <span data-ttu-id="47446-122">Tenga en cuenta que el texto de la cadena que se describen, pero no se rellena, por el <xref:System.Drawing.Graphics.DrawPath%2A> método.</span><span class="sxs-lookup"><span data-stu-id="47446-122">Note that the text in the string is outlined, but not filled, by the <xref:System.Drawing.Graphics.DrawPath%2A> method.</span></span> <span data-ttu-id="47446-123">Es el <xref:System.Drawing.Graphics.FillPath%2A> método que pinta el interior de los caracteres de la cadena.</span><span class="sxs-lookup"><span data-stu-id="47446-123">It is the <xref:System.Drawing.Graphics.FillPath%2A> method that paints the interiors of the characters in the string.</span></span>  
  
 <span data-ttu-id="47446-124">![Cadena en una ruta de acceso](./media/aboutgdip02-art26.gif "Aboutgdip02_art26")</span><span class="sxs-lookup"><span data-stu-id="47446-124">![String in a path](./media/aboutgdip02-art26.gif "Aboutgdip02_art26")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47446-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="47446-125">See also</span></span>

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- [<span data-ttu-id="47446-126">Líneas, curvas y formas</span><span class="sxs-lookup"><span data-stu-id="47446-126">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="47446-127">Cómo: Crear objetos Graphics para dibujar</span><span class="sxs-lookup"><span data-stu-id="47446-127">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="47446-128">Crear y dibujar trazados</span><span class="sxs-lookup"><span data-stu-id="47446-128">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
