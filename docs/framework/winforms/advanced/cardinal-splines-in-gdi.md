---
title: "Curvas spline cardinales en GDI+ | Microsoft Docs"
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
  - "curvas spline cardinales"
  - "GDI+, curvas spline cardinales"
  - "curvas spline, cardinales"
ms.assetid: 09b3797a-6294-422d-9adf-a5a0a7695c0c
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Curvas spline cardinales en GDI+
Una curva spline cardinal es una secuencia de curvas individuales combinadas para formar una curva mayor.  La curva spline se especifica mediante una matriz de puntos y un parámetro de tensión.  Una curva spline cardinal pasa suavemente por cada punto de la matriz; no hay esquinas definidas ni cambios abruptos en la tensión de la curva.  En la siguiente ilustración se muestra un conjunto de puntos y una curva spline cardinal que pasa por cada punto del conjunto.  
  
 ![Curva spline cardinal](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art09.png "Aboutgdip02\_art09")  
  
## Curvas spline físicas y matemáticas  
 Una curva spline física es un trozo fino de madera o de otro material flexible.  Antes de la aparición de las curvas spline matemáticas, los diseñadores utilizaban curvas spline físicas para dibujar curvas.  Un diseñador colocaba la curva spline en un trozo de papel y la delimitaba con respecto a un conjunto determinado de puntos.  Después, el diseñador podía crear una curva dibujando a lo largo de la curva spline con un lápiz.  Un conjunto determinado de puntos podría generar varias curvas, en función de las propiedades de la curva spline física.  Por ejemplo, una curva spline con una resistencia alta a curvarse genera una curva distinta a la de una curva spline extremadamente flexible.  
  
 Las fórmulas que se utilizan para calcular curvas spline matemáticas se basan en las propiedades de barras flexibles, de modo que las curvas creadas por curvas spline matemáticas son similares a las curvas que se crearon una vez con las curvas spline físicas.  Del mismo modo que las curvas spline físicas de distinta tensión generan curvas distintas a través de un conjunto determinado de puntos, las curvas spline matemáticas con valores diferentes para el parámetro de tensión generan curvas diferentes a través de un conjunto determinado de puntos.  En la siguiente ilustración se muestran cuatro curvas spline cardinales que pasan por el mismo conjunto de puntos.  Se muestra la tensión de cada curva spline.  Una tensión de 0 se corresponde con una tensión física infinita, lo que obliga a la curva a tomar el camino más corto \(líneas rectas\) entre puntos.  Una tensión de 1 corresponde a la ausencia de tensión física, que permite a la curva spline tomar el trazado de menor curvatura total.  Con valores de tensión superiores a 1, la curva se comporta como un muelle comprimido, al que se empuja para tomar un trazado más largo.  
  
 ![Curvas spline cardinales](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art10.png "Aboutgdip02\_art10")  
  
 Las cuatro curvas spline de la ilustración anterior comparten la misma línea tangente en el punto inicial.  La tangente es la línea que va desde el punto inicial hasta el siguiente punto de la curva.  De forma similar, la tangente compartida en el extremo es la línea que va desde el extremo hasta el punto anterior de la curva.  
  
 Para dibujar una curva spline cardinal, necesita una instancia de la clase <xref:System.Drawing.Graphics>, un <xref:System.Drawing.Pen> y una matriz de los objetos <xref:System.Drawing.Point>. La instancia de la clase <xref:System.Drawing.Graphics> proporciona el método <xref:System.Drawing.Graphics.DrawCurve%2A>, que dibuja la curva spline, y <xref:System.Drawing.Pen> almacena los atributos de la curva spline, como ancho de línea y color.  La matriz de objetos <xref:System.Drawing.Point> almacena los puntos por los que pasará la curva.  En el ejemplo de código siguiente se muestra cómo dibujar una curva spline cardinal que atraviesa los puntos de  `myPointArray`.  La tensión es el tercer parámetro.  
  
 [!code-csharp[LinesCurvesAndShapes#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#31)]
 [!code-vb[LinesCurvesAndShapes#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#31)]  
  
## Vea también  
 [Líneas, curvas y formas](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Crear y dibujar curvas](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)