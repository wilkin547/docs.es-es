---
title: "C&#243;mo: Disponer una forma en mosaico con una imagen | Microsoft Docs"
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
  - "mapas de bits [Windows Forms], rellenar formas"
  - "imágenes [Windows Forms], rellenar formas"
  - "formas, disponer con imágenes"
  - "pinceles de textura, disponer imágenes con"
ms.assetid: 6d407891-6e5c-4495-a546-3da5604e9fb8
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Disponer una forma en mosaico con una imagen
De la misma manera que se forma un mosaico poniendo unas piezas al lado de las otras, las imágenes rectangulares se pueden disponer unas al lado de otras de manera que rellenen una forma, constituyendo un mosaico.  Para organizar en mosaico el interior de una forma, utilice un pincel de textura.  Cuando se crea un objeto <xref:System.Drawing.TextureBrush>, uno de los argumentos que se pasa al constructor es un objeto <xref:System.Drawing.Image>.  Cuando se usa el pincel de textura para pintar el interior de una forma, ésta se rellena con copias repetidas de esta imagen.  
  
 La propiedad del modo de ajuste del objeto <xref:System.Drawing.TextureBrush> determina cómo se orienta la imagen cuando se repite en una cuadrícula rectangular.  Todas las piezas de mosaico de la cuadrícula pueden tener la misma orientación o se puede voltear la imagen desde una posición de la cuadrícula hasta la siguiente.  El volteo puede ser horizontal, vertical o ambas cosas.  En los ejemplos siguientes se muestran disposiciones en mosaico con distintos tipos de volteo.  
  
### Para disponer una imagen en mosaico  
  
-   En este ejemplo se utiliza la siguiente imagen de 75×75 para disponer en mosaico un rectángulo de 200×200.  
  
 ![Mosaico 1](../../../../docs/framework/winforms/advanced/media/tile1.png "tile1")  
  
-   En la siguiente ilustración se muestra cómo se organiza en mosaico el rectángulo con la imagen.  Observe que todas las piezas tienen la misma orientación; no hay volteo.  
  
 ![Mosaico 2](../../../../docs/framework/winforms/advanced/media/tile2.png "tile2")  
  
 [!code-csharp[System.Drawing.UsingABrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingABrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#31)]  
  
### Para voltear una imagen horizontalmente al disponerla en mosaico  
  
-   En este ejemplo se utiliza la misma imagen de 75×75 para disponer en mosaico un rectángulo de 200×200.  El modo de ajuste se ha establecido para voltear horizontalmente la imagen.  En la siguiente ilustración se muestra cómo se organiza en mosaico el rectángulo con la imagen.  Observe que, al desplazarse de una pieza a la siguiente de una misma fila, la imagen se voltea horizontalmente.  
  
 ![Mosaico 3](../../../../docs/framework/winforms/advanced/media/tile3.png "tile3")  
  
 [!code-csharp[System.Drawing.UsingABrush#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.UsingABrush#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#32)]  
  
### Para voltear una imagen verticalmente al disponerla en mosaico  
  
-   En este ejemplo se utiliza la misma imagen de 75×75 para disponer en mosaico un rectángulo de 200×200.  El modo de ajuste se ha establecido para voltear verticalmente la imagen.  
  
     [!code-csharp[System.Drawing.UsingABrush#33](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#33)]
     [!code-vb[System.Drawing.UsingABrush#33](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#33)]  
  
### Para voltear una imagen horizontal y verticalmente al disponerla en mosaico  
  
-   En este ejemplo se utiliza la misma imagen de 75×75 para disponer en mosaico un rectángulo de 200×200.  El modo de ajuste se ha establecido para voltear la imagen horizontal y verticalmente.  En la siguiente ilustración se muestra cómo se organiza en mosaico el rectángulo con la imagen.  Observe que al desplazarse de una pieza a la siguiente en la misma fila, la imagen se voltea horizontalmente y al desplazarse de una pieza a la siguiente en la misma columna la imagen se voltea verticalmente.  
  
 ![Mosaico 5](../../../../docs/framework/winforms/advanced/media/tile5.png "tile5")  
  
 [!code-csharp[System.Drawing.UsingABrush#34](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.UsingABrush#34](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#34)]  
  
## Vea también  
 [Utilizar un pincel para rellenar formas](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)