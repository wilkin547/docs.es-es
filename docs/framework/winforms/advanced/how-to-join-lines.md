---
title: "C&#243;mo: Unir l&#237;neas | Microsoft Docs"
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
  - "estilo de unión de línea biselada"
  - "dibujar, unir líneas"
  - "gráficos, unir líneas"
  - "GraphicsPath (objeto)"
  - "unión de línea"
  - "líneas, combinar"
  - "estilo de unión de línea en ángulo"
  - "Pen (clase)"
  - "estilo de unión de línea redonda"
ms.assetid: 9fc480c2-3c75-4fd1-8ab5-296a99e820e2
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Unir l&#237;neas
Una unión de líneas es el área común formada por dos líneas cuyos finales se encuentran o se superponen.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona tres estilos de unión de la línea: en ángulo, bisel y redondo.  El estilo de la unión de líneas es una propiedad de la clase <xref:System.Drawing.Pen>.  Cuando se especifica un estilo de unión de líneas para un objeto <xref:System.Drawing.Pen>, ese estilo se aplicará a todas las líneas conectadas de cualquier objeto <xref:System.Drawing.Drawing2D.GraphicsPath> dibujado con ese lápiz.  
  
 En la siguiente ilustración se muestra el resultado del ejemplo de unión de líneas biselada.  
  
 ![Plumas](../../../../docs/framework/winforms/advanced/media/pens5.png "pens5")  
  
## Ejemplo  
 El estilo de unión de líneas se puede especificar mediante la propiedad <xref:System.Drawing.Pen.LineJoin%2A> de la clase <xref:System.Drawing.Pen>.  En el ejemplo se muestra una unión de líneas biselada entre una línea horizontal y otra vertical.  En el código siguiente, el valor <xref:System.Drawing.Drawing2D.LineJoin> asignado a la propiedad <xref:System.Drawing.Pen.LineJoin%2A> es un miembro de la enumeración <xref:System.Drawing.Drawing2D.LineJoin>.  Los otros miembros de la enumeración <xref:System.Drawing.Drawing2D.LineJoin> son <xref:System.Drawing.Drawing2D.LineJoin> y <xref:System.Drawing.Drawing2D.LineJoin>.  
  
 [!code-csharp[System.Drawing.UsingAPen#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingAPen#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#31)]  
  
## Compilar el código  
 El ejemplo anterior está diseñado para formularios Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## Vea también  
 [Utilizar lápiz para dibujar líneas y formas](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)