---
title: Lápices, líneas y rectángulos en GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines
- GDI+, lines
- drawing [Windows Forms], rectangles
- rectangles
- drawing [Windows Forms], lines
- GDI+, pens
- examples [Windows Forms], drawing lines and shapes
- examples [Windows Forms], pens
- GDI+, rectangles
- examples [Windows Forms], GDI+
- lines [Windows Forms], dashed
ms.assetid: 30b25aae-e3eb-4479-bdb8-187cf651fc84
ms.openlocfilehash: eb09d9a0df5ed3498e32e37bb5b23ff6c8744857
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54523381"
---
# <a name="pens-lines-and-rectangles-in-gdi"></a><span data-ttu-id="38749-102">Lápices, líneas y rectángulos en GDI+</span><span class="sxs-lookup"><span data-stu-id="38749-102">Pens, Lines, and Rectangles in GDI+</span></span>
<span data-ttu-id="38749-103">Para dibujar líneas con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] , deberá crear un <xref:System.Drawing.Graphics> objeto y un <xref:System.Drawing.Pen> objeto.</span><span class="sxs-lookup"><span data-stu-id="38749-103">To draw lines with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] you need to create a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="38749-104">El <xref:System.Drawing.Graphics> objeto proporciona los métodos que realmente realizan el dibujo, y el <xref:System.Drawing.Pen> objeto almacena atributos, como el estilo, ancho y color de línea.</span><span class="sxs-lookup"><span data-stu-id="38749-104">The <xref:System.Drawing.Graphics> object provides the methods that actually do the drawing, and the <xref:System.Drawing.Pen> object stores attributes, such as line color, width, and style.</span></span>  
  
## <a name="drawing-a-line"></a><span data-ttu-id="38749-105">Dibujar una línea</span><span class="sxs-lookup"><span data-stu-id="38749-105">Drawing a Line</span></span>  
 <span data-ttu-id="38749-106">Para dibujar una línea, llame a la <xref:System.Drawing.Graphics.DrawLine%2A> método de la <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="38749-106">To draw a line, call the <xref:System.Drawing.Graphics.DrawLine%2A> method of the <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="38749-107">El <xref:System.Drawing.Pen> objeto se pasa como uno de los argumentos para el <xref:System.Drawing.Graphics.DrawLine%2A> método.</span><span class="sxs-lookup"><span data-stu-id="38749-107">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawLine%2A> method.</span></span> <span data-ttu-id="38749-108">El ejemplo siguiente dibuja una línea desde el punto (4, 2) para el punto (12, 6):</span><span class="sxs-lookup"><span data-stu-id="38749-108">The following example draws a line from the point (4, 2) to the point (12, 6):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#41)]
 [!code-vb[LinesCurvesAndShapes#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#41)]  
  
 <span data-ttu-id="38749-109"><xref:System.Drawing.Graphics.DrawLine%2A> es un método sobrecargado de la <xref:System.Drawing.Graphics> clase, por lo que hay varias maneras de proporcionar argumentos.</span><span class="sxs-lookup"><span data-stu-id="38749-109"><xref:System.Drawing.Graphics.DrawLine%2A> is an overloaded method of the <xref:System.Drawing.Graphics> class, so there are several ways you can supply it with arguments.</span></span> <span data-ttu-id="38749-110">Por ejemplo, puede crear dos <xref:System.Drawing.Point> objetos y pase el <xref:System.Drawing.Point> objetos como argumentos para el <xref:System.Drawing.Graphics.DrawLine%2A> método:</span><span class="sxs-lookup"><span data-stu-id="38749-110">For example, you can construct two <xref:System.Drawing.Point> objects and pass the <xref:System.Drawing.Point> objects as arguments to the <xref:System.Drawing.Graphics.DrawLine%2A> method:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#42)]
 [!code-vb[LinesCurvesAndShapes#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#42)]  
  
## <a name="constructing-a-pen"></a><span data-ttu-id="38749-111">Creación de un lápiz</span><span class="sxs-lookup"><span data-stu-id="38749-111">Constructing a Pen</span></span>  
 <span data-ttu-id="38749-112">Puede especificar ciertos atributos al construir un <xref:System.Drawing.Pen> objeto.</span><span class="sxs-lookup"><span data-stu-id="38749-112">You can specify certain attributes when you construct a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="38749-113">Por ejemplo, una `Pen` constructor permite especificar el color y ancho.</span><span class="sxs-lookup"><span data-stu-id="38749-113">For example, one `Pen` constructor allows you to specify color and width.</span></span> <span data-ttu-id="38749-114">En el ejemplo siguiente se dibuja una línea azul de ancho 2 de (0, 0) a (60, 30):</span><span class="sxs-lookup"><span data-stu-id="38749-114">The following example draws a blue line of width 2 from (0, 0) to (60, 30):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#43)]
 [!code-vb[LinesCurvesAndShapes#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#43)]  
  
## <a name="dashed-lines-and-line-caps"></a><span data-ttu-id="38749-115">Las líneas discontinuas y extremos de línea</span><span class="sxs-lookup"><span data-stu-id="38749-115">Dashed Lines and Line Caps</span></span>  
 <span data-ttu-id="38749-116">El <xref:System.Drawing.Pen> objeto también expone propiedades, como <xref:System.Drawing.Pen.DashStyle%2A>, que puede usar para especificar las características de la línea.</span><span class="sxs-lookup"><span data-stu-id="38749-116">The <xref:System.Drawing.Pen> object also exposes properties, such as <xref:System.Drawing.Pen.DashStyle%2A>, that you can use to specify features of the line.</span></span> <span data-ttu-id="38749-117">En el ejemplo siguiente se dibuja una línea discontinua de (100, 50) a (300, 80):</span><span class="sxs-lookup"><span data-stu-id="38749-117">The following example draws a dashed line from (100, 50) to (300, 80):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#44](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#44)]
 [!code-vb[LinesCurvesAndShapes#44](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#44)]  
  
 <span data-ttu-id="38749-118">Puede usar las propiedades de la <xref:System.Drawing.Pen> objeto para establecer muchos más atributos de la línea.</span><span class="sxs-lookup"><span data-stu-id="38749-118">You can use the properties of the <xref:System.Drawing.Pen> object to set many more attributes of the line.</span></span> <span data-ttu-id="38749-119">El <xref:System.Drawing.Pen.StartCap%2A> y <xref:System.Drawing.Pen.EndCap%2A> propiedades especifican la apariencia de los extremos de la línea; los extremos pueden ser sin formato, cuadrados, redondeado, triangular, o una forma personalizada.</span><span class="sxs-lookup"><span data-stu-id="38749-119">The <xref:System.Drawing.Pen.StartCap%2A> and <xref:System.Drawing.Pen.EndCap%2A> properties specify the appearance of the ends of the line; the ends can be flat, square, rounded, triangular, or a custom shape.</span></span> <span data-ttu-id="38749-120">El <xref:System.Drawing.Pen.LineJoin%2A> propiedad le permite especificar si líneas conectadas son ángulo (unidas con esquinas en ángulo), biseladas, redondeadas o recorta.</span><span class="sxs-lookup"><span data-stu-id="38749-120">The <xref:System.Drawing.Pen.LineJoin%2A> property lets you specify whether connected lines are mitered (joined with sharp corners), beveled, rounded, or clipped.</span></span> <span data-ttu-id="38749-121">La siguiente ilustración muestra las líneas con varios estilos de extremo y combinación.</span><span class="sxs-lookup"><span data-stu-id="38749-121">The following illustration shows lines with various cap and join styles.</span></span>  
  
 <span data-ttu-id="38749-122">![Lines](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art04.gif "Aboutgdip02_art04")</span><span class="sxs-lookup"><span data-stu-id="38749-122">![Lines](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art04.gif "Aboutgdip02_art04")</span></span>  
  
## <a name="drawing-a-rectangle"></a><span data-ttu-id="38749-123">Dibuja un rectángulo</span><span class="sxs-lookup"><span data-stu-id="38749-123">Drawing a Rectangle</span></span>  
 <span data-ttu-id="38749-124">Dibujar rectángulos con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] es similar a dibujar las líneas.</span><span class="sxs-lookup"><span data-stu-id="38749-124">Drawing rectangles with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] is similar to drawing lines.</span></span> <span data-ttu-id="38749-125">Para dibujar un rectángulo, necesita un <xref:System.Drawing.Graphics> objeto y un <xref:System.Drawing.Pen> objeto.</span><span class="sxs-lookup"><span data-stu-id="38749-125">To draw a rectangle, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="38749-126">El <xref:System.Drawing.Graphics> objeto proporciona un <xref:System.Drawing.Graphics.DrawRectangle%2A> método y el <xref:System.Drawing.Pen> objeto almacena atributos, como el color y ancho de línea.</span><span class="sxs-lookup"><span data-stu-id="38749-126">The <xref:System.Drawing.Graphics> object provides a <xref:System.Drawing.Graphics.DrawRectangle%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as line width and color.</span></span> <span data-ttu-id="38749-127">El <xref:System.Drawing.Pen> objeto se pasa como uno de los argumentos para el <xref:System.Drawing.Graphics.DrawRectangle%2A> método.</span><span class="sxs-lookup"><span data-stu-id="38749-127">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method.</span></span> <span data-ttu-id="38749-128">En el ejemplo siguiente se dibuja un rectángulo con la esquina superior izquierda en (100, 50), un ancho de 80 y un alto de 40:</span><span class="sxs-lookup"><span data-stu-id="38749-128">The following example draws a rectangle with its upper-left corner at (100, 50), a width of 80, and a height of 40:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#45](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#45)]
 [!code-vb[LinesCurvesAndShapes#45](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#45)]  
  
 <span data-ttu-id="38749-129"><xref:System.Drawing.Graphics.DrawRectangle%2A> es un método sobrecargado de la <xref:System.Drawing.Graphics> clase, por lo que hay varias maneras de proporcionar argumentos.</span><span class="sxs-lookup"><span data-stu-id="38749-129"><xref:System.Drawing.Graphics.DrawRectangle%2A> is an overloaded method of the <xref:System.Drawing.Graphics> class, so there are several ways you can supply it with arguments.</span></span> <span data-ttu-id="38749-130">Por ejemplo, puede construir un <xref:System.Drawing.Rectangle> objeto y pase el <xref:System.Drawing.Rectangle> de objeto para el <xref:System.Drawing.Graphics.DrawRectangle%2A> método como argumento:</span><span class="sxs-lookup"><span data-stu-id="38749-130">For example, you can construct a <xref:System.Drawing.Rectangle> object and pass the <xref:System.Drawing.Rectangle> object to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method as an argument:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#46](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#46)]
 [!code-vb[LinesCurvesAndShapes#46](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#46)]  
  
 <span data-ttu-id="38749-131">Un <xref:System.Drawing.Rectangle> objeto tiene propiedades y métodos para manipular y recopilar información sobre el rectángulo.</span><span class="sxs-lookup"><span data-stu-id="38749-131">A <xref:System.Drawing.Rectangle> object has methods and properties for manipulating and gathering information about the rectangle.</span></span> <span data-ttu-id="38749-132">Por ejemplo, el <xref:System.Drawing.Rectangle.Inflate%2A> y <xref:System.Drawing.Rectangle.Offset%2A> métodos cambian el tamaño y posición del rectángulo.</span><span class="sxs-lookup"><span data-stu-id="38749-132">For example, the <xref:System.Drawing.Rectangle.Inflate%2A> and <xref:System.Drawing.Rectangle.Offset%2A> methods change the size and position of the rectangle.</span></span> <span data-ttu-id="38749-133">El <xref:System.Drawing.Rectangle.IntersectsWith%2A> método indica si el rectángulo forma una intersección con otra dada rectángulo y el <xref:System.Drawing.Rectangle.Contains%2A> método indica si un punto determinado está dentro del rectángulo.</span><span class="sxs-lookup"><span data-stu-id="38749-133">The <xref:System.Drawing.Rectangle.IntersectsWith%2A> method tells you whether the rectangle intersects another given rectangle, and the <xref:System.Drawing.Rectangle.Contains%2A> method tells you whether a given point is inside the rectangle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38749-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="38749-134">See also</span></span>
- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Rectangle?displayProperty=nameWithType>
- [<span data-ttu-id="38749-135">Cómo: Crear un lápiz</span><span class="sxs-lookup"><span data-stu-id="38749-135">How to: Create a Pen</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)
- [<span data-ttu-id="38749-136">Cómo: Dibujar una línea en un formulario de Windows</span><span class="sxs-lookup"><span data-stu-id="38749-136">How to: Draw a Line on a Windows Form</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-line-on-a-windows-form.md)
- [<span data-ttu-id="38749-137">Cómo: Dibujar una forma con contorno</span><span class="sxs-lookup"><span data-stu-id="38749-137">How to: Draw an Outlined Shape</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)
