---
title: "Informaci&#243;n general acerca de gr&#225;ficos vectoriales | Microsoft Docs"
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
  - "sistemas de coordenadas"
  - "gráficos, gráficos vectoriales"
  - "extremos inclusive-inclusive"
ms.assetid: 0195df81-66be-452d-bb53-5a582ebfdc09
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Informaci&#243;n general acerca de gr&#225;ficos vectoriales
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] dibuja líneas, rectángulos y otras formas en un sistema de coordenadas.  Se puede elegir entre varios sistemas de coordenadas, pero el sistema de coordenadas predeterminado tiene el origen en la esquina superior izquierda, con el eje x apuntando hacia la derecha y el eje y apuntando hacia abajo.  La unidad de medida del sistema de coordenadas predeterminado es el píxel.  
  
## Los bloques de creación de GDI\+  
 ![Gráfico vectorial](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art01.png "AboutGdip02\_Art01")  
  
 Un monitor del sistema crea su pantalla en una matriz rectangular de puntos a los que se denomina elementos de imagen o píxeles.  El número de píxeles que aparece en la pantalla varía de un monitor a otro, y el número de píxeles que aparece en un monitor individual suele poder configurarlo, hasta cierto punto, el usuario.  
  
 ![Gráfico vectorial](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art02.png "AboutGdip02\_Art02")  
  
 Cuando se utiliza [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] para dibujar una línea, un rectángulo o una curva, se proporciona cierta información clave sobre el elemento que se va a dibujar.  Por ejemplo, es posible especificar una línea si se proporcionan dos puntos y se puede especificar un rectángulo si se proporciona un punto, un alto y un ancho.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] funciona junto con el software del controlador de vídeo para determinar qué píxeles deben encenderse para mostrar la línea, el rectángulo o la curva.  En la siguiente ilustración se muestra la forma en que se activan los píxeles para mostrar una línea del punto \(4, 2\) al punto \(12, 8\).  
  
 ![Gráfico vectorial](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art03.png "AboutGdip02\_Art03")  
  
 Con el tiempo, determinados bloques de creación han resultado ser los más útiles para crear imágenes bidimensionales.  Estos bloques de creación, todos ellos compatibles con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], se indican en la lista siguiente:  
  
-   Líneas  
  
-   Rectángulos  
  
-   Elipses  
  
-   Arcos  
  
-   Polígonos  
  
-   Curvas spline cardinales  
  
-   Curvas spline de Bézier  
  
## Métodos para dibujar con un objeto Graphics  
 La clase <xref:System.Drawing.Graphics> de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona los métodos siguientes para dibujar los elementos enumerados en la lista anterior: <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawRectangle%2A>, <xref:System.Drawing.Graphics.DrawEllipse%2A>, <xref:System.Drawing.Graphics.DrawPolygon%2A>, <xref:System.Drawing.Graphics.DrawArc%2A>, <xref:System.Drawing.Graphics.DrawCurve%2A> \(para las curvas spline cardinales\) y <xref:System.Drawing.Graphics.DrawBezier%2A>.  Cada uno de estos métodos está sobrecargado, es decir, cada método admite varias listas de parámetros distintas.  Por ejemplo, una variación del método <xref:System.Drawing.Graphics.DrawLine%2A> recibe un objeto <xref:System.Drawing.Pen> y cuatro enteros, mientras que otra variación del método <xref:System.Drawing.Graphics.DrawLine%2A> recibe un objeto <xref:System.Drawing.Pen> y dos objetos <xref:System.Drawing.Point>.  
  
 Los métodos para dibujar líneas, rectángulos y curvas spline de Bézier tienen métodos asociados plurales que dibujan varios elementos en una única llamada: <xref:System.Drawing.Graphics.DrawLines%2A>, <xref:System.Drawing.Graphics.DrawRectangles%2A> y <xref:System.Drawing.Graphics.DrawBeziers%2A>.  Además, el método <xref:System.Drawing.Graphics.DrawCurve%2A> tiene un método asociado, <xref:System.Drawing.Graphics.DrawClosedCurve%2A>, que cierra una curva conectando el extremo con el punto inicial de la curva.  
  
 Todos los métodos de dibujo de la clase <xref:System.Drawing.Graphics> funcionan junto con un objeto <xref:System.Drawing.Pen>.  Para poder dibujar algo se deben crear dos objetos por lo menos: un objeto <xref:System.Drawing.Graphics> y un objeto <xref:System.Drawing.Pen>.  El objeto <xref:System.Drawing.Pen> almacena atributos, como el color y el ancho de línea, del elemento que se va a dibujar.  El objeto <xref:System.Drawing.Pen> se pasa como uno de los argumentos del método de dibujo.  Por ejemplo, una variación del método <xref:System.Drawing.Graphics.DrawLine%2A> recibe un objeto <xref:System.Drawing.Pen> y cuatro enteros, tal y como se muestra en el siguiente ejemplo, en el que se dibuja un rectángulo con un ancho de 100, un alto de 50 y una esquina superior izquierda de \(20, 10\):  
  
 [!code-csharp[LinesCurvesAndShapes#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#11)]
 [!code-vb[LinesCurvesAndShapes#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#11)]  
  
## Vea también  
 <xref:System.Drawing.Graphics?displayProperty=fullName>   
 <xref:System.Drawing.Pen?displayProperty=fullName>   
 [Líneas, curvas y formas](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Cómo: Crear objetos Graphics para dibujar](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)