---
title: "Lápices, líneas y rectángulos en GDI+"
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
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5b72bbaef26e1c61f86e354adc7df7404469ee0d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="pens-lines-and-rectangles-in-gdi"></a>Lápices, líneas y rectángulos en GDI+
Para dibujar líneas con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] necesita crear un <xref:System.Drawing.Graphics> objeto y un <xref:System.Drawing.Pen> objeto. El <xref:System.Drawing.Graphics> objeto proporciona los métodos que realmente realizan el dibujo, y el <xref:System.Drawing.Pen> objeto almacena atributos, como el color de línea, el ancho y el estilo.  
  
## <a name="drawing-a-line"></a>Dibujar una línea  
 Para dibujar una línea, llame a la <xref:System.Drawing.Graphics.DrawLine%2A> método de la <xref:System.Drawing.Graphics> objeto. El <xref:System.Drawing.Pen> objeto se pasa como uno de los argumentos para el <xref:System.Drawing.Graphics.DrawLine%2A> método. En el ejemplo siguiente se dibuja una línea desde el punto (4, 2) al punto (12, 6):  
  
 [!code-csharp[LinesCurvesAndShapes#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#41)]
 [!code-vb[LinesCurvesAndShapes#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#41)]  
  
 <xref:System.Drawing.Graphics.DrawLine%2A>es un método sobrecargado de la <xref:System.Drawing.Graphics> de la clase, por lo que hay varias formas de proporcionar argumentos. Por ejemplo, puede crear dos <xref:System.Drawing.Point> objetos y pase el <xref:System.Drawing.Point> objetos como argumentos a la <xref:System.Drawing.Graphics.DrawLine%2A> método:  
  
 [!code-csharp[LinesCurvesAndShapes#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#42)]
 [!code-vb[LinesCurvesAndShapes#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#42)]  
  
## <a name="constructing-a-pen"></a>Creación de un lápiz  
 Puede especificar ciertos atributos cuando se crea un <xref:System.Drawing.Pen> objeto. Por ejemplo, uno `Pen` constructor permite especificar el color y ancho. En el ejemplo siguiente se dibuja una línea azul de ancho 2 de (0, 0) a (60, 30):  
  
 [!code-csharp[LinesCurvesAndShapes#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#43)]
 [!code-vb[LinesCurvesAndShapes#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#43)]  
  
## <a name="dashed-lines-and-line-caps"></a>Las líneas discontinuas y extremos de línea  
 El <xref:System.Drawing.Pen> objeto también expone propiedades, como <xref:System.Drawing.Pen.DashStyle%2A>, que puede utilizarse para especificar características de la línea. En el ejemplo siguiente se dibuja una línea discontinua de (100, 50) a (300, 80):  
  
 [!code-csharp[LinesCurvesAndShapes#44](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#44)]
 [!code-vb[LinesCurvesAndShapes#44](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#44)]  
  
 Puede usar las propiedades de la <xref:System.Drawing.Pen> objeto que se va a establecer muchos más atributos de la línea. El <xref:System.Drawing.Pen.StartCap%2A> y <xref:System.Drawing.Pen.EndCap%2A> propiedades especifican la apariencia de los extremos de la línea; los extremos pueden ser sin formato, cuadrados, redondeados, triangular, o una forma personalizada. El <xref:System.Drawing.Pen.LineJoin%2A> propiedad le permite especificar si las líneas conectadas se ángulo (unidas con esquinas definidas), biseladas, redondeadas o recorta. La ilustración siguiente muestra las líneas con varios estilos de combinación y extremos.  
  
 ![Líneas](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art04.gif "Aboutgdip02_art04")  
  
## <a name="drawing-a-rectangle"></a>Dibujar un rectángulo  
 Dibujar rectángulos con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] es similar a dibujar líneas. Para dibujar un rectángulo, son necesarios un <xref:System.Drawing.Graphics> objeto y un <xref:System.Drawing.Pen> objeto. El <xref:System.Drawing.Graphics> objeto proporciona un <xref:System.Drawing.Graphics.DrawRectangle%2A> método y el <xref:System.Drawing.Pen> objeto almacena atributos, como el color y ancho de línea. El <xref:System.Drawing.Pen> objeto se pasa como uno de los argumentos para el <xref:System.Drawing.Graphics.DrawRectangle%2A> método. En el ejemplo siguiente se dibuja un rectángulo con la esquina superior izquierda en (100, 50), un ancho de 80 y un alto de 40:  
  
 [!code-csharp[LinesCurvesAndShapes#45](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#45)]
 [!code-vb[LinesCurvesAndShapes#45](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#45)]  
  
 <xref:System.Drawing.Graphics.DrawRectangle%2A>es un método sobrecargado de la <xref:System.Drawing.Graphics> de la clase, por lo que hay varias formas de proporcionar argumentos. Por ejemplo, puede crear un <xref:System.Drawing.Rectangle> objeto y pasar la <xref:System.Drawing.Rectangle> el objeto a la <xref:System.Drawing.Graphics.DrawRectangle%2A> método como argumento:  
  
 [!code-csharp[LinesCurvesAndShapes#46](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#46)]
 [!code-vb[LinesCurvesAndShapes#46](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#46)]  
  
 Un <xref:System.Drawing.Rectangle> objeto tiene métodos y propiedades para manipular y recopilar información sobre el rectángulo. Por ejemplo, el <xref:System.Drawing.Rectangle.Inflate%2A> y <xref:System.Drawing.Rectangle.Offset%2A> los métodos de cambiar el tamaño y la posición del rectángulo. El <xref:System.Drawing.Rectangle.IntersectsWith%2A> método indica si el rectángulo se corta con otra dada rectángulo y la <xref:System.Drawing.Rectangle.Contains%2A> método indica si un punto especificado está dentro del rectángulo.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 <xref:System.Drawing.Rectangle?displayProperty=nameWithType>  
 [Crear un lápiz](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)  
 [Dibujar una línea en Windows Forms](../../../../docs/framework/winforms/advanced/how-to-draw-a-line-on-a-windows-form.md)  
 [Dibujar una forma con contorno](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)
