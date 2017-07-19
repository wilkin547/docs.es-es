---
title: "Importancia del orden de transformaci&#243;n | Microsoft Docs"
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
  - "transformaciones, importancia del orden"
ms.assetid: 37d5f9dc-a5cf-4475-aa5d-34d714e808a9
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Importancia del orden de transformaci&#243;n
Un único objeto <xref:System.Drawing.Drawing2D.Matrix> puede almacenar una transformación o una secuencia de transformaciones.  Ésta última se denomina transformación compuesta.  La matriz de una transformación compuesta se obtiene multiplicando las matrices de las transformaciones individuales.  
  
## Ejemplos de transformación compuestas  
 En una transformación compuesta, es importante el orden de cada una de las transformaciones.  Por ejemplo, si primero se gira, después se cambia el tamaño y después se traslada, el resultado será distinto que si primero se traslada, después se gira y después se cambia el tamaño.  En [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], las transformaciones compuestas se compilan de izquierda a derecha.  Si S, R y T son matrices de cambio de tamaño, giro y traslado respectivamente, el producto SRT \(en ese orden\) es la matriz de la transformación compuesta que primero cambia el tamaño, luego gira y después traslada.  La matriz que se obtiene con el producto SRT es distinta a la que se obtiene con el producto TRS.  
  
 Una razón por la que el orden es importante es que las transformaciones como el giro y el cambio de tamaño se hacen en relación con el origen del sistema de coordenadas.  Cambiar el tamaño de un objeto que está centrado en el origen tiene un resultado diferente a cambiar el tamaño de un objeto que se ha alejado del origen.  De forma similar, girar un objeto que está centrado en el origen tiene un resultado diferente a girar un objeto que se ha alejado del origen.  
  
 En el ejemplo siguiente se combina el cambio de tamaño, el giro y el traslado \(en ese orden\) para formar una transformación compuesta.  El argumento <xref:System.Drawing.Drawing2D.MatrixOrder> que se pasa al método <xref:System.Drawing.Graphics.RotateTransform%2A> indica que el giro seguirá al cambio de tamaño.  Igualmente, el argumento <xref:System.Drawing.Drawing2D.MatrixOrder> que se pasa al método <xref:System.Drawing.Graphics.TranslateTransform%2A> indica que la traducción seguirá a la rotación.  <xref:System.Drawing.Drawing2D.MatrixOrder> y <xref:System.Drawing.Drawing2D.MatrixOrder> son miembros de la enumeración <xref:System.Drawing.Drawing2D.MatrixOrder>.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.MiscLegacyTopics#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#21)]  
  
 En el ejemplo siguiente se hacen las mismas llamadas a métodos que en el anterior, pero se invierte el orden de las llamadas.  El orden resultante de las operaciones es primero traslado, después giro y después cambio de tamaño, lo cual genera un resultado muy diferente a primero cambiar el tamaño, luego girar y después trasladar.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.MiscLegacyTopics#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#22)]  
  
 Una manera de invertir el orden de las transformaciones en una transformación compuesta consiste en invertir el orden de una secuencia de llamadas a métodos.  Otra forma de controlar el orden de las operaciones es cambiar el argumento de orden de la matriz.  El ejemplo siguiente es igual que el ejemplo anterior, sólo que <xref:System.Drawing.Drawing2D.MatrixOrder> se ha cambiado a <xref:System.Drawing.Drawing2D.MatrixOrder>.  La multiplicación de la matriz se hace en el orden SRT, donde S, R y T son las matrices de cambio de tamaño, giro y traslado, respectivamente.  El orden de la transformación compuesta es primero el cambio de tamaño, después el giro y después el traslado.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.MiscLegacyTopics#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#23)]  
  
 El resultado del ejemplo precedente es el mismo que el del primer ejemplo de este tema.  Esto es así por que se han invertido el orden de las llamadas a métodos y el orden de la multiplicación de la matriz.  
  
## Vea también  
 <xref:System.Drawing.Drawing2D.Matrix>   
 [Sistemas de coordenadas y transformaciones](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)   
 [Usar transformaciones en la interfaz GDI\+ administrada](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)