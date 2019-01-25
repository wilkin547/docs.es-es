---
title: Elipses y arcos en GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- arcs
- GDI+, arcs
- drawing [Windows Forms], ellipses
- GDI+, ellipses
- ellipses
- drawing [Windows Forms], arcs
ms.assetid: 34f35133-a835-4ca4-81f6-0dfedee8b683
ms.openlocfilehash: 93f82d35449c42772e9fbd1b7454364885b38769
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54697210"
---
# <a name="ellipses-and-arcs-in-gdi"></a><span data-ttu-id="a1580-102">Elipses y arcos en GDI+</span><span class="sxs-lookup"><span data-stu-id="a1580-102">Ellipses and Arcs in GDI+</span></span>
<span data-ttu-id="a1580-103">Dibujar elipses y arcos utilizando el <xref:System.Drawing.Graphics.DrawEllipse%2A> y <xref:System.Drawing.Graphics.DrawArc%2A> métodos de la <xref:System.Drawing.Graphics> clase.</span><span class="sxs-lookup"><span data-stu-id="a1580-103">You can easily draw ellipses and arcs using the <xref:System.Drawing.Graphics.DrawEllipse%2A> and <xref:System.Drawing.Graphics.DrawArc%2A> methods of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="drawing-an-ellipse"></a><span data-ttu-id="a1580-104">Dibujar una elipse</span><span class="sxs-lookup"><span data-stu-id="a1580-104">Drawing an Ellipse</span></span>  
 <span data-ttu-id="a1580-105">Para dibujar una elipse, necesita un <xref:System.Drawing.Graphics> objeto y un <xref:System.Drawing.Pen> objeto.</span><span class="sxs-lookup"><span data-stu-id="a1580-105">To draw an ellipse, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="a1580-106">El <xref:System.Drawing.Graphics> objeto proporciona el <xref:System.Drawing.Graphics.DrawEllipse%2A> método y el <xref:System.Drawing.Pen> objeto almacena atributos, como el ancho y color de la línea utilizada para representar la elipse.</span><span class="sxs-lookup"><span data-stu-id="a1580-106">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawEllipse%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the ellipse.</span></span> <span data-ttu-id="a1580-107">El <xref:System.Drawing.Pen> objeto se pasa como uno de los argumentos para el <xref:System.Drawing.Graphics.DrawEllipse%2A> método.</span><span class="sxs-lookup"><span data-stu-id="a1580-107">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method.</span></span> <span data-ttu-id="a1580-108">Los argumentos restantes se pasan a la <xref:System.Drawing.Graphics.DrawEllipse%2A> método especifican el rectángulo delimitador de la elipse.</span><span class="sxs-lookup"><span data-stu-id="a1580-108">The remaining arguments passed to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method specify the bounding rectangle for the ellipse.</span></span> <span data-ttu-id="a1580-109">La siguiente ilustración muestra una elipse junto con su rectángulo delimitador.</span><span class="sxs-lookup"><span data-stu-id="a1580-109">The following illustration shows an ellipse along with its bounding rectangle.</span></span>  
  
 <span data-ttu-id="a1580-110">![Elipses y arcos](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art05.gif "Aboutgdip02_art05")</span><span class="sxs-lookup"><span data-stu-id="a1580-110">![Ellipses and arcs](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art05.gif "Aboutgdip02_art05")</span></span>  
  
 <span data-ttu-id="a1580-111">En el ejemplo siguiente se dibuja una elipse; rectángulo que tiene un ancho de 80, un alto de 40 y una esquina superior izquierda de (100, 50):</span><span class="sxs-lookup"><span data-stu-id="a1580-111">The following example draws an ellipse; the bounding rectangle has a width of 80, a height of 40, and an upper-left corner of (100, 50):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#51)]
 [!code-vb[LinesCurvesAndShapes#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#51)]  
  
 <span data-ttu-id="a1580-112"><xref:System.Drawing.Graphics.DrawEllipse%2A> es un método sobrecargado de la <xref:System.Drawing.Graphics> clase, por lo que hay varias maneras de proporcionar argumentos.</span><span class="sxs-lookup"><span data-stu-id="a1580-112"><xref:System.Drawing.Graphics.DrawEllipse%2A> is an overloaded method of the <xref:System.Drawing.Graphics> class, so there are several ways you can supply it with arguments.</span></span> <span data-ttu-id="a1580-113">Por ejemplo, puede construir un <xref:System.Drawing.Rectangle> y pase el <xref:System.Drawing.Rectangle> a la <xref:System.Drawing.Graphics.DrawEllipse%2A> método como argumento:</span><span class="sxs-lookup"><span data-stu-id="a1580-113">For example, you can construct a <xref:System.Drawing.Rectangle> and pass the <xref:System.Drawing.Rectangle> to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method as an argument:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#52](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#52)]
 [!code-vb[LinesCurvesAndShapes#52](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#52)]  
  
## <a name="drawing-an-arc"></a><span data-ttu-id="a1580-114">Dibujar un arco</span><span class="sxs-lookup"><span data-stu-id="a1580-114">Drawing an Arc</span></span>  
 <span data-ttu-id="a1580-115">Un arco es una parte de una elipse.</span><span class="sxs-lookup"><span data-stu-id="a1580-115">An arc is a portion of an ellipse.</span></span> <span data-ttu-id="a1580-116">Para dibujar un arco, llame a la <xref:System.Drawing.Graphics.DrawArc%2A> método de la <xref:System.Drawing.Graphics> clase.</span><span class="sxs-lookup"><span data-stu-id="a1580-116">To draw an arc, you call the <xref:System.Drawing.Graphics.DrawArc%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="a1580-117">Los parámetros de la <xref:System.Drawing.Graphics.DrawArc%2A> método son los mismos que los parámetros de la <xref:System.Drawing.Graphics.DrawEllipse%2A> método, salvo que <xref:System.Drawing.Graphics.DrawArc%2A> requiere un ángulo inicial y ángulo de barrido.</span><span class="sxs-lookup"><span data-stu-id="a1580-117">The parameters of the <xref:System.Drawing.Graphics.DrawArc%2A> method are the same as the parameters of the <xref:System.Drawing.Graphics.DrawEllipse%2A> method, except that <xref:System.Drawing.Graphics.DrawArc%2A> requires a starting angle and sweep angle.</span></span> <span data-ttu-id="a1580-118">El ejemplo siguiente dibuja un arco con un ángulo inicial de 30 grados y un ángulo de barrido de 180 grados:</span><span class="sxs-lookup"><span data-stu-id="a1580-118">The following example draws an arc with a starting angle of 30 degrees and a sweep angle of 180 degrees:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#53](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#53)]
 [!code-vb[LinesCurvesAndShapes#53](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#53)]  
  
 <span data-ttu-id="a1580-119">La siguiente ilustración muestra el arco, la elipse y el rectángulo delimitador.</span><span class="sxs-lookup"><span data-stu-id="a1580-119">The following illustration shows the arc, the ellipse, and the bounding rectangle.</span></span>  
  
 <span data-ttu-id="a1580-120">![Elipses y arcos](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art06.gif "Aboutgdip02_art06")</span><span class="sxs-lookup"><span data-stu-id="a1580-120">![Ellipses and arcs](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art06.gif "Aboutgdip02_art06")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1580-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1580-121">See also</span></span>
- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [<span data-ttu-id="a1580-122">Líneas, curvas y formas</span><span class="sxs-lookup"><span data-stu-id="a1580-122">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)
- [<span data-ttu-id="a1580-123">Cómo: Crear objetos Graphics para dibujar</span><span class="sxs-lookup"><span data-stu-id="a1580-123">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="a1580-124">Cómo: Crear un lápiz</span><span class="sxs-lookup"><span data-stu-id="a1580-124">How to: Create a Pen</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)
- [<span data-ttu-id="a1580-125">Cómo: Dibujar una forma con contorno</span><span class="sxs-lookup"><span data-stu-id="a1580-125">How to: Draw an Outlined Shape</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)
