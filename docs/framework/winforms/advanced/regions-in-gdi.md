---
title: "Regiones de GDI+ | Microsoft Docs"
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
  - "dibujar, regiones"
  - "GDI+, regiones"
  - "regiones"
ms.assetid: 52184f9b-16dd-4bbd-85be-029112644ceb
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Regiones de GDI+
Una región es una parte del área de presentación de un dispositivo de salida.  Las regiones pueden ser simples \(un único rectángulo\) o complejas \(una combinación de polígonos y curvas cerradas\).  En la siguiente ilustración se muestran dos regiones: una construida a partir de un rectángulo, y la otra construida a partir de un trazado.  
  
 ![Regiones](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art27.png "AboutGdip02\_Art27")  
  
## Utilizar regiones  
 Las regiones se utilizan a menudo para recortar y comprobar clics con el mouse.  La acción de recortar implica la restricción del dibujo a determinada región del área de presentación, normalmente la parte que necesita una actualización.  La comprobación de clics con el mouse implica una comprobación que determine si el cursor se encuentra en cierta región de la pantalla cuando se presiona el botón del mouse.  
  
 Se puede construir una región a partir de un rectángulo o de un trazado.  También se pueden crear regiones complejas mediante la combinación de regiones existentes.  La clase <xref:System.Drawing.Region> proporciona los métodos siguientes para combinar las regiones: <xref:System.Drawing.Region.Intersect%2A>, <xref:System.Drawing.Region.Union%2A>, <xref:System.Drawing.Region.Xor%2A>, <xref:System.Drawing.Region.Exclude%2A> y <xref:System.Drawing.Region.Complement%2A>.  
  
 La intersección de dos regiones es el conjunto de todos los puntos que pertenecen a ambas regiones.  La unión es el conjunto de todos los puntos que pertenecen a una u otra región.  El complemento de una región es el conjunto de todos los puntos que no están en la región.  En la siguiente ilustración se muestra la intersección y la unión de las dos regiones de la ilustración anterior.  
  
 ![Regiones](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art28.gif "AboutGdip02\_Art28")  
  
 El método <xref:System.Drawing.Region.Xor%2A>, aplicado a un par de regiones, genera una región que contiene todos los puntos que pertenecen a una región o a otra, pero no a ambas.  El método <xref:System.Drawing.Region.Exclude%2A>, aplicado a un par de regiones, genera una región que contiene todos los puntos que pertenecen a la primera región y que no están en la segunda.  En la siguiente ilustración se muestran las regiones que se generan al aplicar los métodos <xref:System.Drawing.Region.Xor%2A> y <xref:System.Drawing.Region.Exclude%2A> a las dos regiones que se muestran al principio de este tema.  
  
 ![Regiones](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art29.png "AboutGdip02\_Art29")  
  
 Para rellenar una región son necesarios los objetos <xref:System.Drawing.Graphics>,  <xref:System.Drawing.Brush> y <xref:System.Drawing.Region>.  El objeto <xref:System.Drawing.Graphics> proporciona el método <xref:System.Drawing.Graphics.FillRegion%2A> y el objeto <xref:System.Drawing.Brush> almacena atributos del relleno, como el color y la trama.  En el siguiente ejemplo se rellena una región con un color sólido.  
  
 [!code-csharp[LinesCurvesAndShapes#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#61)]
 [!code-vb[LinesCurvesAndShapes#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#61)]  
  
## Vea también  
 <xref:System.Drawing.Region?displayProperty=fullName>   
 [Líneas, curvas y formas](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Utilizar regiones](../../../../docs/framework/winforms/advanced/using-regions.md)