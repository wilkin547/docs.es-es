---
title: "Pol&#237;gonos en GDI+ | Microsoft Docs"
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
  - "dibujar, polígonos"
  - "GDI+, polígonos"
  - "polígonos"
ms.assetid: a72213d2-d69a-4c2b-a75c-be7b20390c13
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Pol&#237;gonos en GDI+
Un polígono es una forma cerrada con tres o más líneas rectas.  Por ejemplo, un triángulo es un polígono con tres lados, un rectángulo es un polígono con cuatro lados y un pentágono es un polígono con cinco lados.  En la siguiente ilustración se muestran varios polígonos.  
  
 ![Polígonos](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art07.png "Aboutgdip02\_art07")  
  
## Dibujar un polígono  
 Para dibujar un polígono se necesita un objeto <xref:System.Drawing.Graphics>, un objeto <xref:System.Drawing.Pen> y una matriz de objetos <xref:System.Drawing.Point> \(o <xref:System.Drawing.PointF>\).  El objeto <xref:System.Drawing.Graphics> proporciona el método <xref:System.Drawing.Graphics.DrawPolygon%2A>.  El objeto <xref:System.Drawing.Pen> almacena atributos, como el ancho y el color de la línea utilizada para representar el polígono, y la matriz de objetos <xref:System.Drawing.Point> almacena los puntos que se van a conectar mediante líneas rectas.  El objeto <xref:System.Drawing.Pen> y la matriz de objetos <xref:System.Drawing.Point> se pasan como argumentos al método <xref:System.Drawing.Graphics.DrawPolygon%2A>.  En el siguiente ejemplo se dibuja un polígono de tres lados.  Tenga en cuenta que sólo existen tres puntos en  `myPointArray`: \(0, 0\), \(50, 30\) y \(30, 60\).  El método <xref:System.Drawing.Graphics.DrawPolygon%2A> cierra el polígono automáticamente ya que dibuja una línea desde \(30, 60\) hacia atrás hasta el punto inicial \(0, 0\).  
  
 [!code-csharp[LinesCurvesAndShapes#111](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#111)]
 [!code-vb[LinesCurvesAndShapes#111](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#111)]  
  
 En la siguiente ilustración se muestra el polígono.  
  
 ![Polígono](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art08.png "Aboutgdip02\_art08")  
  
## Vea también  
 <xref:System.Drawing.Graphics?displayProperty=fullName>   
 <xref:System.Drawing.Pen?displayProperty=fullName>   
 [Líneas, curvas y formas](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Cómo: Crear un lápiz](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)