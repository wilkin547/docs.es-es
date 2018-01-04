---
title: Elipses y arcos en GDI+
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
- arcs
- GDI+, arcs
- drawing [Windows Forms], ellipses
- GDI+, ellipses
- ellipses
- drawing [Windows Forms], arcs
ms.assetid: 34f35133-a835-4ca4-81f6-0dfedee8b683
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 71126942f4cde37cc5d26bfba029c5f50f1065a3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ellipses-and-arcs-in-gdi"></a><span data-ttu-id="18e8c-102">Elipses y arcos en GDI+</span><span class="sxs-lookup"><span data-stu-id="18e8c-102">Ellipses and Arcs in GDI+</span></span>
<span data-ttu-id="18e8c-103">Fácilmente puede dibujar elipses y arcos utilizando la <xref:System.Drawing.Graphics.DrawEllipse%2A> y <xref:System.Drawing.Graphics.DrawArc%2A> métodos de la <xref:System.Drawing.Graphics> clase.</span><span class="sxs-lookup"><span data-stu-id="18e8c-103">You can easily draw ellipses and arcs using the <xref:System.Drawing.Graphics.DrawEllipse%2A> and <xref:System.Drawing.Graphics.DrawArc%2A> methods of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="drawing-an-ellipse"></a><span data-ttu-id="18e8c-104">Dibujar una elipse</span><span class="sxs-lookup"><span data-stu-id="18e8c-104">Drawing an Ellipse</span></span>  
 <span data-ttu-id="18e8c-105">Para dibujar una elipse, necesita un <xref:System.Drawing.Graphics> objeto y un <xref:System.Drawing.Pen> objeto.</span><span class="sxs-lookup"><span data-stu-id="18e8c-105">To draw an ellipse, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="18e8c-106">El <xref:System.Drawing.Graphics> objeto proporciona el <xref:System.Drawing.Graphics.DrawEllipse%2A> método y el <xref:System.Drawing.Pen> objeto almacena atributos, como el ancho y color de la línea que se usa para representar la elipse.</span><span class="sxs-lookup"><span data-stu-id="18e8c-106">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawEllipse%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the ellipse.</span></span> <span data-ttu-id="18e8c-107">El <xref:System.Drawing.Pen> objeto se pasa como uno de los argumentos para el <xref:System.Drawing.Graphics.DrawEllipse%2A> método.</span><span class="sxs-lookup"><span data-stu-id="18e8c-107">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method.</span></span> <span data-ttu-id="18e8c-108">Los argumentos restantes se pasan a la <xref:System.Drawing.Graphics.DrawEllipse%2A> método especifican el rectángulo delimitador de la elipse.</span><span class="sxs-lookup"><span data-stu-id="18e8c-108">The remaining arguments passed to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method specify the bounding rectangle for the ellipse.</span></span> <span data-ttu-id="18e8c-109">En la siguiente ilustración se muestra una elipse junto con su rectángulo delimitador.</span><span class="sxs-lookup"><span data-stu-id="18e8c-109">The following illustration shows an ellipse along with its bounding rectangle.</span></span>  
  
 <span data-ttu-id="18e8c-110">![Elipses y arcos](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art05.gif "Aboutgdip02_art05")</span><span class="sxs-lookup"><span data-stu-id="18e8c-110">![Ellipses and arcs](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art05.gif "Aboutgdip02_art05")</span></span>  
  
 <span data-ttu-id="18e8c-111">En el ejemplo siguiente se dibuja una elipse; el rectángulo delimitador tiene un ancho de 80, un alto de 40 y una esquina superior izquierda de (100, 50):</span><span class="sxs-lookup"><span data-stu-id="18e8c-111">The following example draws an ellipse; the bounding rectangle has a width of 80, a height of 40, and an upper-left corner of (100, 50):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#51)]
 [!code-vb[LinesCurvesAndShapes#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#51)]  
  
 <span data-ttu-id="18e8c-112"><xref:System.Drawing.Graphics.DrawEllipse%2A>es un método sobrecargado de la <xref:System.Drawing.Graphics> de la clase, por lo que hay varias formas de proporcionar argumentos.</span><span class="sxs-lookup"><span data-stu-id="18e8c-112"><xref:System.Drawing.Graphics.DrawEllipse%2A> is an overloaded method of the <xref:System.Drawing.Graphics> class, so there are several ways you can supply it with arguments.</span></span> <span data-ttu-id="18e8c-113">Por ejemplo, puede crear un <xref:System.Drawing.Rectangle> y pase el <xref:System.Drawing.Rectangle> a la <xref:System.Drawing.Graphics.DrawEllipse%2A> método como argumento:</span><span class="sxs-lookup"><span data-stu-id="18e8c-113">For example, you can construct a <xref:System.Drawing.Rectangle> and pass the <xref:System.Drawing.Rectangle> to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method as an argument:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#52](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#52)]
 [!code-vb[LinesCurvesAndShapes#52](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#52)]  
  
## <a name="drawing-an-arc"></a><span data-ttu-id="18e8c-114">Dibujar un arco</span><span class="sxs-lookup"><span data-stu-id="18e8c-114">Drawing an Arc</span></span>  
 <span data-ttu-id="18e8c-115">Un arco es una parte de una elipse.</span><span class="sxs-lookup"><span data-stu-id="18e8c-115">An arc is a portion of an ellipse.</span></span> <span data-ttu-id="18e8c-116">Para dibujar un arco, se llama a la <xref:System.Drawing.Graphics.DrawArc%2A> método de la <xref:System.Drawing.Graphics> clase.</span><span class="sxs-lookup"><span data-stu-id="18e8c-116">To draw an arc, you call the <xref:System.Drawing.Graphics.DrawArc%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="18e8c-117">Los parámetros de la <xref:System.Drawing.Graphics.DrawArc%2A> método son los mismos que los parámetros de la <xref:System.Drawing.Graphics.DrawEllipse%2A> método, salvo que <xref:System.Drawing.Graphics.DrawArc%2A> precisa un ángulo inicial y ángulo de barrido.</span><span class="sxs-lookup"><span data-stu-id="18e8c-117">The parameters of the <xref:System.Drawing.Graphics.DrawArc%2A> method are the same as the parameters of the <xref:System.Drawing.Graphics.DrawEllipse%2A> method, except that <xref:System.Drawing.Graphics.DrawArc%2A> requires a starting angle and sweep angle.</span></span> <span data-ttu-id="18e8c-118">En el ejemplo siguiente se dibuja un arco con un ángulo inicial de 30 grados y un ángulo de barrido de 180 grados:</span><span class="sxs-lookup"><span data-stu-id="18e8c-118">The following example draws an arc with a starting angle of 30 degrees and a sweep angle of 180 degrees:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#53](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#53)]
 [!code-vb[LinesCurvesAndShapes#53](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#53)]  
  
 <span data-ttu-id="18e8c-119">En la siguiente ilustración muestra el arco, la elipse y el rectángulo delimitador.</span><span class="sxs-lookup"><span data-stu-id="18e8c-119">The following illustration shows the arc, the ellipse, and the bounding rectangle.</span></span>  
  
 <span data-ttu-id="18e8c-120">![Elipses y arcos](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art06.gif "Aboutgdip02_art06")</span><span class="sxs-lookup"><span data-stu-id="18e8c-120">![Ellipses and arcs](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art06.gif "Aboutgdip02_art06")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18e8c-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="18e8c-121">See Also</span></span>  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [<span data-ttu-id="18e8c-122">Líneas, curvas y formas</span><span class="sxs-lookup"><span data-stu-id="18e8c-122">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="18e8c-123">Crear objetos Graphics para dibujar</span><span class="sxs-lookup"><span data-stu-id="18e8c-123">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [<span data-ttu-id="18e8c-124">Crear un lápiz</span><span class="sxs-lookup"><span data-stu-id="18e8c-124">How to: Create a Pen</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)  
 [<span data-ttu-id="18e8c-125">Dibujar una forma con contorno</span><span class="sxs-lookup"><span data-stu-id="18e8c-125">How to: Draw an Outlined Shape</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)
