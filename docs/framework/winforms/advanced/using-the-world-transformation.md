---
title: "Utilizar la transformaci&#243;n de coordenadas universales | Microsoft Docs"
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
  - "gráficos, transformación universal"
  - "transformación universal, ejemplos"
ms.assetid: 1e717711-1361-448e-aa49-0f3ec43110c9
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Utilizar la transformaci&#243;n de coordenadas universales
La transformación de coordenadas universales es una propiedad de la clase <xref:System.Drawing.Graphics>.  Los números que especifican la transformación de coordenadas universales están almacenados en un objeto <xref:System.Drawing.Drawing2D.Matrix> que representa una matriz de 3x3.  Las clases <xref:System.Drawing.Drawing2D.Matrix> y<xref:System.Drawing.Graphics> tienen varios métodos para establecer los números en la matriz de transformación de coordenadas universales.  
  
## Tipos diferente de transformaciones  
 En el ejemplo siguiente, el código crea primero un rectángulo de 50x50 y lo sitúa en el origen \(0, 0\).  El origen está en la esquina superior izquierda del área de cliente.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.MiscLegacyTopics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#11)]  
  
 El código siguiente aplica una transformación de ajuste de tamaño que expande el rectángulo por un factor de 1,75 en la dirección del eje x y lo encoge por un factor de 0,5 en la dirección del eje y:  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.MiscLegacyTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#12)]  
  
 El resultado es un rectángulo que es más largo en la dirección x y más corto en la dirección y que el original.  
  
 Para girar el rectángulo en lugar de cambiar su tamaño, use el código siguiente:  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.MiscLegacyTopics#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#13)]  
  
 Para trasladar el rectángulo, use el código siguiente:  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#14](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.MiscLegacyTopics#14](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#14)]  
  
## Vea también  
 <xref:System.Drawing.Drawing2D.Matrix>   
 [Sistemas de coordenadas y transformaciones](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)   
 [Usar transformaciones en la interfaz GDI\+ administrada](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)