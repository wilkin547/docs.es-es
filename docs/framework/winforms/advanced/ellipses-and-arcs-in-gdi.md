---
title: "Elipses y arcos en GDI+ | Microsoft Docs"
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
  - "arcos"
  - "dibujar, arcos"
  - "dibujar, elipses"
  - "elipses"
  - "GDI+, arcos"
  - "GDI+, elipses"
ms.assetid: 34f35133-a835-4ca4-81f6-0dfedee8b683
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Elipses y arcos en GDI+
Resulta sencillo dibujar elipses y arcos utilizando los métodos <xref:System.Drawing.Graphics.DrawEllipse%2A> y <xref:System.Drawing.Graphics.DrawArc%2A> de la clase <xref:System.Drawing.Graphics>.  
  
## Dibujar una elipse  
 Para dibujar una elipse son necesarios un objeto <xref:System.Drawing.Graphics> y un objeto <xref:System.Drawing.Pen>.  El objeto <xref:System.Drawing.Graphics> proporciona el método <xref:System.Drawing.Graphics.DrawEllipse%2A>, y el objeto <xref:System.Drawing.Pen> almacena atributos como el ancho y el color de la línea que se utiliza para representar la elipse.  El objeto <xref:System.Drawing.Pen> se pasa como uno de los argumentos del método <xref:System.Drawing.Graphics.DrawEllipse%2A>.  El resto de los argumentos que se pasan al método <xref:System.Drawing.Graphics.DrawEllipse%2A> especifican el rectángulo delimitador de la elipse.  En la siguiente ilustración se muestra una elipse junto con su rectángulo delimitador.  
  
 ![Elipses y arcos](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art05.png "Aboutgdip02\_art05")  
  
 En el siguiente ejemplo se dibuja una elipse; el rectángulo delimitador tiene un ancho de 80, un alto de 40 y una esquina superior izquierda de \(100, 50\):  
  
 [!code-csharp[LinesCurvesAndShapes#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#51)]
 [!code-vb[LinesCurvesAndShapes#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#51)]  
  
 <xref:System.Drawing.Graphics.DrawEllipse%2A> es un método sobrecargado de la clase <xref:System.Drawing.Graphics>, por lo que existen varias formas de suministrar argumentos a dicho método.  Por ejemplo, se puede construir un objeto <xref:System.Drawing.Rectangle> y pasar este objeto <xref:System.Drawing.Rectangle> como argumento al método <xref:System.Drawing.Graphics.DrawEllipse%2A>:  
  
 [!code-csharp[LinesCurvesAndShapes#52](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#52)]
 [!code-vb[LinesCurvesAndShapes#52](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#52)]  
  
## Dibujar un arco  
 Un arco es una parte de una elipse.  Para dibujar un arco, se llama al método <xref:System.Drawing.Graphics.DrawArc%2A> de la clase <xref:System.Drawing.Graphics>.  Los parámetros del método <xref:System.Drawing.Graphics.DrawArc%2A> son los mismos que los del método <xref:System.Drawing.Graphics.DrawEllipse%2A>, a excepción de que <xref:System.Drawing.Graphics.DrawArc%2A> precisa un ángulo inicial y un ángulo de barrido.  En el siguiente ejemplo se dibuja un arco con un ángulo inicial de 30 grados y un ángulo de barrido de 180 grados:  
  
 [!code-csharp[LinesCurvesAndShapes#53](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#53)]
 [!code-vb[LinesCurvesAndShapes#53](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#53)]  
  
 En la siguiente ilustración se muestran el arco, la elipse y el rectángulo delimitador.  
  
 ![Elipses y arcos](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art06.png "Aboutgdip02\_art06")  
  
## Vea también  
 <xref:System.Drawing.Graphics?displayProperty=fullName>   
 <xref:System.Drawing.Pen?displayProperty=fullName>   
 [Líneas, curvas y formas](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Cómo: Crear objetos Graphics para dibujar](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)   
 [Cómo: Crear un lápiz](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)   
 [Cómo: Dibujar una forma con contorno](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)