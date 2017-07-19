---
title: "L&#225;pices, l&#237;neas y rect&#225;ngulos en GDI+ | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "dibujar, líneas"
  - "dibujar, rectángulos"
  - "ejemplos [Windows Forms], dibujar líneas y formas"
  - "ejemplos [Windows Forms], GDI+"
  - "ejemplos [Windows Forms], lápices"
  - "GDI+, líneas"
  - "GDI+, lápices"
  - "GDI+, rectángulos"
  - "líneas"
  - "líneas, con guión"
  - "rectángulos"
ms.assetid: 30b25aae-e3eb-4479-bdb8-187cf651fc84
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# L&#225;pices, l&#237;neas y rect&#225;ngulos en GDI+
Para dibujar líneas con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] necesita crear un objeto <xref:System.Drawing.Graphics> y un objeto <xref:System.Drawing.Pen>.  El objeto <xref:System.Drawing.Graphics> proporciona los métodos que realmente realizan el dibujo, y el objeto <xref:System.Drawing.Pen> almacena atributos como el estilo, el ancho y el color de línea.  
  
## Dibujar una línea  
 Para dibujar una línea, llame al método <xref:System.Drawing.Graphics.DrawLine%2A> del objeto <xref:System.Drawing.Graphics>.  El objeto <xref:System.Drawing.Pen> se pasa como uno de los argumentos del método <xref:System.Drawing.Graphics.DrawLine%2A>.  En el siguiente ejemplo se dibuja una línea del punto \(4, 2\) al punto \(12, 6\):  
  
 [!code-csharp[LinesCurvesAndShapes#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#41)]
 [!code-vb[LinesCurvesAndShapes#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#41)]  
  
 <xref:System.Drawing.Graphics.DrawLine%2A> es un método sobrecargado de la clase <xref:System.Drawing.Graphics>, por lo que existen varias formas de suministrar argumentos a dicho método.  Por ejemplo, se pueden construir dos objetos <xref:System.Drawing.Point> y pasar dichos objetos <xref:System.Drawing.Point>como argumentos al método <xref:System.Drawing.Graphics.DrawLine%2A>:  
  
 [!code-csharp[LinesCurvesAndShapes#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#42)]
 [!code-vb[LinesCurvesAndShapes#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#42)]  
  
## Construir un lápiz  
 Cuando se construye un objeto <xref:System.Drawing.Pen> pueden especificarse ciertos atributos.  Por ejemplo, un constructor `Pen` permite especificar el color y el ancho.  En el siguiente ejemplo se dibuja una línea azul de ancho 2 de \(0, 0\) a \(60, 30\):  
  
 [!code-csharp[LinesCurvesAndShapes#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#43)]
 [!code-vb[LinesCurvesAndShapes#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#43)]  
  
## Líneas discontinuas y extremos de línea  
 El objeto <xref:System.Drawing.Pen> también expone propiedades, como <xref:System.Drawing.Pen.DashStyle%2A>, que pueden utilizarse para especificar características de la línea.  En el siguiente ejemplo se dibuja una línea discontinua de \(100, 50\) a \(300, 80\):  
  
 [!code-csharp[LinesCurvesAndShapes#44](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#44)]
 [!code-vb[LinesCurvesAndShapes#44](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#44)]  
  
 Las propiedades del objeto <xref:System.Drawing.Pen> pueden utilizarse para establecer muchos más atributos de la línea.  Las propiedades <xref:System.Drawing.Pen.StartCap%2A> y <xref:System.Drawing.Pen.EndCap%2A> especifican la apariencia de los extremos de la línea; los extremos pueden ser lisos, cuadrados, redondeados, triangulares o pueden tener una forma personalizada.  La propiedad <xref:System.Drawing.Pen.LineJoin%2A> permite especificar si las líneas conectadas están en ángulo \(unidas con esquinas definidas\), biseladas, redondeadas o recortadas.  En la siguiente ilustración se muestran líneas con varios estilos de combinación y extremos.  
  
 ![Líneas](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art04.png "Aboutgdip02\_art04")  
  
## Dibujar un rectángulo  
 Dibujar rectángulos con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] es parecido a dibujar líneas.  Para dibujar un rectángulo son necesarios un objeto <xref:System.Drawing.Graphics> y un objeto <xref:System.Drawing.Pen>.  El objeto <xref:System.Drawing.Graphics> proporciona un método <xref:System.Drawing.Graphics.DrawRectangle%2A> y el objeto <xref:System.Drawing.Pen> almacena atributos tales como el color y el ancho de línea.  El objeto <xref:System.Drawing.Pen> se pasa como uno de los argumentos del método <xref:System.Drawing.Graphics.DrawRectangle%2A>.  En el siguiente ejemplo se dibuja un rectángulo con la esquina superior izquierda en \(100, 50\), un ancho de 80 y un alto de 40:  
  
 [!code-csharp[LinesCurvesAndShapes#45](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#45)]
 [!code-vb[LinesCurvesAndShapes#45](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#45)]  
  
 <xref:System.Drawing.Graphics.DrawRectangle%2A> es un método sobrecargado de la clase <xref:System.Drawing.Graphics>, por lo que existen varias formas de suministrar argumentos a dicho método.  Por ejemplo, se puede construir un objeto <xref:System.Drawing.Rectangle> y pasar el objeto <xref:System.Drawing.Rectangle> como argumento al método <xref:System.Drawing.Graphics.DrawRectangle%2A>:  
  
 [!code-csharp[LinesCurvesAndShapes#46](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#46)]
 [!code-vb[LinesCurvesAndShapes#46](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#46)]  
  
 Un objeto <xref:System.Drawing.Rectangle> tiene métodos y propiedades para manipular y recopilar información sobre el rectángulo.  Por ejemplo, los métodos <xref:System.Drawing.Rectangle.Inflate%2A> y <xref:System.Drawing.Rectangle.Offset%2A> cambian el tamaño y la posición del rectángulo.  El método <xref:System.Drawing.Rectangle.IntersectsWith%2A> indica si el rectángulo forma una intersección con otro rectángulo determinado y el método <xref:System.Drawing.Rectangle.Contains%2A> indica si un punto determinado se encuentra dentro del rectángulo.  
  
## Vea también  
 <xref:System.Drawing.Graphics?displayProperty=fullName>   
 <xref:System.Drawing.Pen?displayProperty=fullName>   
 <xref:System.Drawing.Rectangle?displayProperty=fullName>   
 [Cómo: Crear un lápiz](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)   
 [Cómo: Dibujar una línea en Windows Forms](../../../../docs/framework/winforms/advanced/how-to-draw-a-line-on-a-windows-form.md)   
 [Cómo: Dibujar una forma con contorno](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)