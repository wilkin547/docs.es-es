---
title: B&#233;en GDI + curvas spline de Bézier
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines
- splines [Windows Forms], Bezier
- GDI+, Bezier splines
ms.assetid: 5774ce1e-87d4-4bc7-88c4-4862052781b8
ms.openlocfilehash: ff4e9eb18610b70c88e057d3d44020321bbb9f4f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59107333"
---
# <a name="b233zier-splines-in-gdi"></a><span data-ttu-id="ae4ec-102">B&#233;en GDI + curvas spline de Bézier</span><span class="sxs-lookup"><span data-stu-id="ae4ec-102">B&#233;zier Splines in GDI+</span></span>
<span data-ttu-id="ae4ec-103">Una curva spline de Bézier es una curva especificada por cuatro puntos: dos puntos finales (p1 y p2) y dos puntos de control (c1 y c2).</span><span class="sxs-lookup"><span data-stu-id="ae4ec-103">A Bézier spline is a curve specified by four points: two end points (p1 and p2) and two control points (c1 and c2).</span></span> <span data-ttu-id="ae4ec-104">La curva comienza en p1 y termina en p2.</span><span class="sxs-lookup"><span data-stu-id="ae4ec-104">The curve begins at p1 and ends at p2.</span></span> <span data-ttu-id="ae4ec-105">La curva no pasa por los puntos de control, pero los puntos de control se comportan como imanes, extracción de la curva en ciertas direcciones e influyen en el modo en que la curva.</span><span class="sxs-lookup"><span data-stu-id="ae4ec-105">The curve does not pass through the control points, but the control points act as magnets, pulling the curve in certain directions and influencing the way the curve bends.</span></span> <span data-ttu-id="ae4ec-106">La siguiente ilustración muestra una curva de Bézier junto con los extremos y los puntos de control.</span><span class="sxs-lookup"><span data-stu-id="ae4ec-106">The following illustration shows a Bézier curve along with its endpoints and control points.</span></span>  
  
 <span data-ttu-id="ae4ec-107">![Curvas spline de Bézier](./media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")</span><span class="sxs-lookup"><span data-stu-id="ae4ec-107">![Bezier Splines](./media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")</span></span>  
  
 <span data-ttu-id="ae4ec-108">La curva comienza en p1 y avanza hacia el punto de control c1.</span><span class="sxs-lookup"><span data-stu-id="ae4ec-108">The curve starts at p1 and moves toward the control point c1.</span></span> <span data-ttu-id="ae4ec-109">La tangente a la curva en p1 es la línea que va de p1 a c1.</span><span class="sxs-lookup"><span data-stu-id="ae4ec-109">The tangent line to the curve at p1 is the line drawn from p1 to c1.</span></span> <span data-ttu-id="ae4ec-110">La línea tangente en el extremo p2 es la línea trazada desde c2 a p2.</span><span class="sxs-lookup"><span data-stu-id="ae4ec-110">The tangent line at the endpoint p2 is the line drawn from c2 to p2.</span></span>  
  
## <a name="drawing-bzier-splines"></a><span data-ttu-id="ae4ec-111">Dibujar curvas spline de Bézier</span><span class="sxs-lookup"><span data-stu-id="ae4ec-111">Drawing Bézier Splines</span></span>  
 <span data-ttu-id="ae4ec-112">Para dibujar una curva spline de Bézier, necesita una instancia de la <xref:System.Drawing.Graphics> clase y un <xref:System.Drawing.Pen>.</span><span class="sxs-lookup"><span data-stu-id="ae4ec-112">To draw a Bézier spline, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Pen>.</span></span> <span data-ttu-id="ae4ec-113">La instancia de la <xref:System.Drawing.Graphics> clase proporciona el <xref:System.Drawing.Graphics.DrawBezier%2A> método y el <xref:System.Drawing.Pen> almacena atributos, como el ancho y el color de la línea utilizada para representar la curva.</span><span class="sxs-lookup"><span data-stu-id="ae4ec-113">The instance of the <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.DrawBezier%2A> method, and the <xref:System.Drawing.Pen> stores attributes, such as width and color, of the line used to render the curve.</span></span> <span data-ttu-id="ae4ec-114">El <xref:System.Drawing.Pen> se pasa como uno de los argumentos para el <xref:System.Drawing.Graphics.DrawBezier%2A> método.</span><span class="sxs-lookup"><span data-stu-id="ae4ec-114">The <xref:System.Drawing.Pen> is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawBezier%2A> method.</span></span> <span data-ttu-id="ae4ec-115">Los argumentos restantes se pasan a la <xref:System.Drawing.Graphics.DrawBezier%2A> método son los puntos de conexión y los puntos de control.</span><span class="sxs-lookup"><span data-stu-id="ae4ec-115">The remaining arguments passed to the <xref:System.Drawing.Graphics.DrawBezier%2A> method are the endpoints and the control points.</span></span> <span data-ttu-id="ae4ec-116">En el ejemplo siguiente se dibuja una curva spline de Bézier con el punto inicial (0, 0), control puntos (40, 20) y (80, 150) y un punto final (100, 10):</span><span class="sxs-lookup"><span data-stu-id="ae4ec-116">The following example draws a Bézier spline with starting point (0, 0), control points (40, 20) and (80, 150), and ending point (100, 10):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#71](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#71)]
 [!code-vb[LinesCurvesAndShapes#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#71)]  
  
 <span data-ttu-id="ae4ec-117">La siguiente ilustración muestra la curva, los puntos de control y dos líneas tangentes.</span><span class="sxs-lookup"><span data-stu-id="ae4ec-117">The following illustration shows the curve, the control points, and two tangent lines.</span></span>  
  
 <span data-ttu-id="ae4ec-118">![Curvas spline de Bézier](./media/aboutgdip02-art12.gif "Aboutgdip02_art12")</span><span class="sxs-lookup"><span data-stu-id="ae4ec-118">![Bezier Splines](./media/aboutgdip02-art12.gif "Aboutgdip02_art12")</span></span>  
  
 <span data-ttu-id="ae4ec-119">Curvas spline de Bézier se desarrollaron originalmente Pierre Bézier para el diseño en la industria automotriz.</span><span class="sxs-lookup"><span data-stu-id="ae4ec-119">Bézier splines were originally developed by Pierre Bézier for design in the automotive industry.</span></span> <span data-ttu-id="ae4ec-120">Que ya que han demostrado para ser útil en muchos tipos de diseño asistido por ordenador y también se usan para definir los contornos de fuentes.</span><span class="sxs-lookup"><span data-stu-id="ae4ec-120">They have since proven to be useful in many types of computer-aided design and are also used to define the outlines of fonts.</span></span> <span data-ttu-id="ae4ec-121">Curvas spline de Bézier puede producir una gran variedad de formas, algunas de las cuales se muestran en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="ae4ec-121">Bézier splines can yield a wide variety of shapes, some of which are shown in the following illustration.</span></span>  
  
 <span data-ttu-id="ae4ec-122">![Paths](./media/aboutgdip02-art13.gif "Aboutgdip02_art13")</span><span class="sxs-lookup"><span data-stu-id="ae4ec-122">![Paths](./media/aboutgdip02-art13.gif "Aboutgdip02_art13")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae4ec-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae4ec-123">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [<span data-ttu-id="ae4ec-124">Líneas, curvas y formas</span><span class="sxs-lookup"><span data-stu-id="ae4ec-124">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="ae4ec-125">Crear y dibujar curvas</span><span class="sxs-lookup"><span data-stu-id="ae4ec-125">Constructing and Drawing Curves</span></span>](constructing-and-drawing-curves.md)
- [<span data-ttu-id="ae4ec-126">Cómo: Crear objetos Graphics para dibujar</span><span class="sxs-lookup"><span data-stu-id="ae4ec-126">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="ae4ec-127">Cómo: Crear un lápiz</span><span class="sxs-lookup"><span data-stu-id="ae4ec-127">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
