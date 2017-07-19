---
title: "Limitar la superficie de dibujo en GDI+ | Microsoft Docs"
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
  - "recortar, con GDI+"
  - "GDI+, recortar"
  - "GDI+, restringir la superficie de dibujo"
ms.assetid: 8b5f71d9-d2f0-4540-9c41-740f90fd4c26
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Limitar la superficie de dibujo en GDI+
La acción de recortar implica la restricción del dibujo a cierto rectángulo o región.  En la siguiente ilustración se muestra la cadena "Hello" recortada en una región con forma de corazón.  
  
 ![Superficie de dibujo restringida](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art30.gif "AboutGdip02\_Art30")  
  
## Recortar con regiones  
 Las regiones se pueden construir a partir de trazados, y los trazados pueden contener los contornos de cadenas, de modo que se puede utilizar texto con contorno para recortar.  En la siguiente ilustración se muestra un conjunto de elipses concéntricas recortadas en el interior de una cadena de texto.  
  
 ![Superficie de dibujo restringida](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art31.png "AboutGdip02\_Art31")  
  
 Para dibujar con recorte, hay que crear un objeto <xref:System.Drawing.Graphics>, establecer su propiedad <xref:System.Drawing.Graphics.Clip%2A> y, después, llamar a los métodos de dibujo de ese mismo objeto <xref:System.Drawing.Graphics>:  
  
 [!code-csharp[LinesCurvesAndShapes#91](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#91)]
 [!code-vb[LinesCurvesAndShapes#91](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#91)]  
  
## Vea también  
 <xref:System.Drawing.Graphics?displayProperty=fullName>   
 <xref:System.Drawing.Region?displayProperty=fullName>   
 [Líneas, curvas y formas](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Utilizar regiones](../../../../docs/framework/winforms/advanced/using-regions.md)