---
title: "C&#243;mo: Crear figuras a partir de l&#237;neas, curvas y formas | Microsoft Docs"
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
  - "figuras, crear a partir de líneas"
  - "figuras, crear a partir de formas"
ms.assetid: 82fd56c7-b443-4765-9b7c-62ce030656ec
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Crear figuras a partir de l&#237;neas, curvas y formas
Para crear una figura, construya un <xref:System.Drawing.Drawing2D.GraphicsPath> y, a continuación, llame a métodos como <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> y <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> para agregar tipos primitivos al trazado.  
  
## Ejemplo  
 Los ejemplos de código siguientes crean trazados que tienen las figuras:  
  
-   En el primer ejemplo se crea un trazado que tiene una sola figura.  La figura está formada por un único arco.  El arco tiene un ángulo de barrido de \-180 grados, que va en sentido contrario a las agujas del reloj en el sistema de coordenadas predeterminado.  
  
-   En el segundo ejemplo se crea un trazado que tiene dos figuras.  La primera figura es un arco seguido de una línea.  La segunda figura es una línea seguida de una curva seguida de una línea.  La primera figura se deja abierta, la segunda está cerrada.  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#21)]  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#22)]  
  
## Compilar el código  
 Los ejemplos anteriores están diseñados para formularios Windows Forms y requieren <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador del evento <xref:System.Windows.Forms.Control.Paint>.  
  
## Vea también  
 <xref:System.Drawing.Drawing2D.GraphicsPath>   
 [Crear y dibujar trazados](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)   
 [Utilizar lápiz para dibujar líneas y formas](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)