---
title: Trazados de gráficos en GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], paths
- GDI+, drawing paths
- paths [Windows Forms], drawing
- drawing [Windows Forms], paths
ms.assetid: a5500dec-666c-41fd-9da3-2169dd89c5eb
ms.openlocfilehash: c9a43065210f5ef0fffcae01cc7eb88349696b6b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59140509"
---
# <a name="graphics-paths-in-gdi"></a><span data-ttu-id="8c6ab-102">Trazados de gráficos en GDI+</span><span class="sxs-lookup"><span data-stu-id="8c6ab-102">Graphics Paths in GDI+</span></span>
<span data-ttu-id="8c6ab-103">Las rutas de acceso se crean mediante la combinación de líneas, rectángulos y curvas simples.</span><span class="sxs-lookup"><span data-stu-id="8c6ab-103">Paths are formed by combining lines, rectangles, and simple curves.</span></span> <span data-ttu-id="8c6ab-104">Recuerde que en el [información general sobre gráficos de Vector](vector-graphics-overview.md) que los siguientes bloques de creación básicos han demostrado para ser útiles para dibujar imágenes:</span><span class="sxs-lookup"><span data-stu-id="8c6ab-104">Recall from the [Vector Graphics Overview](vector-graphics-overview.md) that the following basic building blocks have proven to be the most useful for drawing pictures:</span></span>  
  
-   <span data-ttu-id="8c6ab-105">Líneas</span><span class="sxs-lookup"><span data-stu-id="8c6ab-105">Lines</span></span>  
  
-   <span data-ttu-id="8c6ab-106">Rectángulos</span><span class="sxs-lookup"><span data-stu-id="8c6ab-106">Rectangles</span></span>  
  
-   <span data-ttu-id="8c6ab-107">Botón de puntos suspensivos</span><span class="sxs-lookup"><span data-stu-id="8c6ab-107">Ellipses</span></span>  
  
-   <span data-ttu-id="8c6ab-108">Arcos</span><span class="sxs-lookup"><span data-stu-id="8c6ab-108">Arcs</span></span>  
  
-   <span data-ttu-id="8c6ab-109">Polígonos</span><span class="sxs-lookup"><span data-stu-id="8c6ab-109">Polygons</span></span>  
  
-   <span data-ttu-id="8c6ab-110">Curvas spline cardinales</span><span class="sxs-lookup"><span data-stu-id="8c6ab-110">Cardinal splines</span></span>  
  
-   <span data-ttu-id="8c6ab-111">Curvas spline de Bézier</span><span class="sxs-lookup"><span data-stu-id="8c6ab-111">Bézier splines</span></span>  
  
 <span data-ttu-id="8c6ab-112">En GDI +, el <xref:System.Drawing.Drawing2D.GraphicsPath> objeto le permite recopilar una secuencia de estos bloques de creación en una sola unidad.</span><span class="sxs-lookup"><span data-stu-id="8c6ab-112">In GDI+, the <xref:System.Drawing.Drawing2D.GraphicsPath> object allows you to collect a sequence of these building blocks into a single unit.</span></span> <span data-ttu-id="8c6ab-113">A continuación, se puede dibujar toda la secuencia de líneas, rectángulos, polígonos y curvas con una llamada a la <xref:System.Drawing.Graphics.DrawPath%2A> método de la <xref:System.Drawing.Graphics> clase.</span><span class="sxs-lookup"><span data-stu-id="8c6ab-113">The entire sequence of lines, rectangles, polygons, and curves can then be drawn with one call to the <xref:System.Drawing.Graphics.DrawPath%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="8c6ab-114">La siguiente ilustración muestra una ruta de acceso creado mediante la combinación de una línea, un arco, una curva spline de Bézier y una curva spline cardinal.</span><span class="sxs-lookup"><span data-stu-id="8c6ab-114">The following illustration shows a path created by combining a line, an arc, a Bézier spline, and a cardinal spline.</span></span>  
  
 <span data-ttu-id="8c6ab-115">![Path](./media/aboutgdip02-art14.gif "Aboutgdip02_art14")</span><span class="sxs-lookup"><span data-stu-id="8c6ab-115">![Path](./media/aboutgdip02-art14.gif "Aboutgdip02_art14")</span></span>  
  
## <a name="using-a-path"></a><span data-ttu-id="8c6ab-116">Uso de una ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="8c6ab-116">Using a Path</span></span>  
 <span data-ttu-id="8c6ab-117">El <xref:System.Drawing.Drawing2D.GraphicsPath> clase proporciona los métodos siguientes para crear una secuencia de elementos que se va a dibujar: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (para curvas spline cardinales), y <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A>.</span><span class="sxs-lookup"><span data-stu-id="8c6ab-117">The <xref:System.Drawing.Drawing2D.GraphicsPath> class provides the following methods for creating a sequence of items to be drawn: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (for cardinal splines), and <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A>.</span></span> <span data-ttu-id="8c6ab-118">Cada uno de estos métodos está sobrecargada; es decir, cada método es compatible con varias listas de parámetros.</span><span class="sxs-lookup"><span data-stu-id="8c6ab-118">Each of these methods is overloaded; that is, each method supports several different parameter lists.</span></span> <span data-ttu-id="8c6ab-119">Por ejemplo, una variación de la <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> método recibe cuatro enteros y otra variación de la <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> método recibe dos <xref:System.Drawing.Point> objetos.</span><span class="sxs-lookup"><span data-stu-id="8c6ab-119">For example, one variation of the <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> method receives four integers, and another variation of the <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> method receives two <xref:System.Drawing.Point> objects.</span></span>  
  
 <span data-ttu-id="8c6ab-120">Los métodos para agregar líneas, rectángulos y curvas spline de Bézier a una ruta de acceso tienen varios métodos asociados que agregan varios elementos a la ruta de acceso en una sola llamada: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A>, y <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>.</span><span class="sxs-lookup"><span data-stu-id="8c6ab-120">The methods for adding lines, rectangles, and Bézier splines to a path have plural companion methods that add several items to the path in a single call: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A>, and <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>.</span></span> <span data-ttu-id="8c6ab-121">Además, el <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> y <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> disponen de métodos, <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> y <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A>, que agregan una curva cerrada o un gráfico circular a la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="8c6ab-121">Also, the <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> methods have companion methods, <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A>, that add a closed curve or pie to the path.</span></span>  
  
 <span data-ttu-id="8c6ab-122">Para dibujar un trazado, necesita un <xref:System.Drawing.Graphics> objeto, un <xref:System.Drawing.Pen> objeto y un <xref:System.Drawing.Drawing2D.GraphicsPath> objeto.</span><span class="sxs-lookup"><span data-stu-id="8c6ab-122">To draw a path, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Pen> object, and a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="8c6ab-123">El <xref:System.Drawing.Graphics> objeto proporciona el <xref:System.Drawing.Graphics.DrawPath%2A> método y el <xref:System.Drawing.Pen> objeto almacena atributos, como el ancho y color de la línea utilizada para representar la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="8c6ab-123">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawPath%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the path.</span></span> <span data-ttu-id="8c6ab-124">La <xref:System.Drawing.Drawing2D.GraphicsPath> objeto almacena la secuencia de líneas y curvas que conforman la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="8c6ab-124">The <xref:System.Drawing.Drawing2D.GraphicsPath> object stores the sequence of lines and curves that make up the path.</span></span> <span data-ttu-id="8c6ab-125">El <xref:System.Drawing.Pen> objeto y el <xref:System.Drawing.Drawing2D.GraphicsPath> objeto se pasan como argumentos para el <xref:System.Drawing.Graphics.DrawPath%2A> método.</span><span class="sxs-lookup"><span data-stu-id="8c6ab-125">The <xref:System.Drawing.Pen> object and the <xref:System.Drawing.Drawing2D.GraphicsPath> object are passed as arguments to the <xref:System.Drawing.Graphics.DrawPath%2A> method.</span></span> <span data-ttu-id="8c6ab-126">El ejemplo siguiente dibuja una ruta de acceso que consta de una línea, una elipse y una curva spline de Bézier:</span><span class="sxs-lookup"><span data-stu-id="8c6ab-126">The following example draws a path that consists of a line, an ellipse, and a Bézier spline:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#101](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#101)]
 [!code-vb[LinesCurvesAndShapes#101](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#101)]  
  
 <span data-ttu-id="8c6ab-127">La siguiente ilustración muestra la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="8c6ab-127">The following illustration shows the path.</span></span>  
  
 <span data-ttu-id="8c6ab-128">![Path](./media/aboutgdip02-art15.gif "Aboutgdip02_art15")</span><span class="sxs-lookup"><span data-stu-id="8c6ab-128">![Path](./media/aboutgdip02-art15.gif "Aboutgdip02_art15")</span></span>  
  
 <span data-ttu-id="8c6ab-129">Además de agregar líneas, rectángulos y curvas en una ruta de acceso, puede agregar rutas de acceso a una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="8c6ab-129">In addition to adding lines, rectangles, and curves to a path, you can add paths to a path.</span></span> <span data-ttu-id="8c6ab-130">Esto le permite combinar trazados existentes para formar las rutas de acceso largas y complejas.</span><span class="sxs-lookup"><span data-stu-id="8c6ab-130">This allows you to combine existing paths to form large, complex paths.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#102](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#102)]
 [!code-vb[LinesCurvesAndShapes#102](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#102)]  
  
 <span data-ttu-id="8c6ab-131">Hay otros dos elementos que puede agregar a una ruta de acceso: cadenas y sectores.</span><span class="sxs-lookup"><span data-stu-id="8c6ab-131">There are two other items you can add to a path: strings and pies.</span></span> <span data-ttu-id="8c6ab-132">Un gráfico circular es una parte del interior de una elipse.</span><span class="sxs-lookup"><span data-stu-id="8c6ab-132">A pie is a portion of the interior of an ellipse.</span></span> <span data-ttu-id="8c6ab-133">El ejemplo siguiente crea una ruta de acceso de un arco, una curva spline cardinal, una cadena y un gráfico circular:</span><span class="sxs-lookup"><span data-stu-id="8c6ab-133">The following example creates a path from an arc, a cardinal spline, a string, and a pie:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#103](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#103)]
 [!code-vb[LinesCurvesAndShapes#103](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#103)]  
  
 <span data-ttu-id="8c6ab-134">La siguiente ilustración muestra la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="8c6ab-134">The following illustration shows the path.</span></span> <span data-ttu-id="8c6ab-135">Tenga en cuenta que no tiene una ruta de acceso que se puede conectar se separan del arco, curva spline cardinal, cadena y circulares.</span><span class="sxs-lookup"><span data-stu-id="8c6ab-135">Note that a path does not have to be connected; the arc, cardinal spline, string, and pie are separated.</span></span>  
  
 <span data-ttu-id="8c6ab-136">![Paths](./media/aboutgdip02-art16.gif "Aboutgdip02_Art16")</span><span class="sxs-lookup"><span data-stu-id="8c6ab-136">![Paths](./media/aboutgdip02-art16.gif "Aboutgdip02_Art16")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c6ab-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c6ab-137">See also</span></span>

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- [<span data-ttu-id="8c6ab-138">Líneas, curvas y formas</span><span class="sxs-lookup"><span data-stu-id="8c6ab-138">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="8c6ab-139">Filtrar para crear objetos gráficos para dibujar</span><span class="sxs-lookup"><span data-stu-id="8c6ab-139">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="8c6ab-140">Crear y dibujar trazados</span><span class="sxs-lookup"><span data-stu-id="8c6ab-140">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
