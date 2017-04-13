---
title: "C&#243;mo: Utilizar la funci&#243;n de suavizado de contorno con texto | Microsoft Docs"
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
  - "suavizado de contorno, con texto"
  - "cadenas [formularios Windows Forms], suavizado de contorno al dibujar"
  - "cadenas [formularios Windows Forms], dibujo suavizado"
  - "texto [Windows Forms], suavizado de contorno"
  - "texto [Windows Forms], suavizado"
ms.assetid: 48fc34f3-f236-4b01-a0cb-f0752e6d22ae
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# C&#243;mo: Utilizar la funci&#243;n de suavizado de contorno con texto
El *suavizado de contorno*  se refiere al suavizado de los bordes escalonados de los gráficos y texto dibujados para mejorar su apariencia y legibilidad.  Con las clases administradas de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], puede representar texto suavizado de gran calidad, así como texto de menor calidad.  Normalmente, una mayor calidad de representación requiere más tiempo de procesamiento que una calidad inferior.  Para establecer el nivel de calidad del texto, establezca la propiedad <xref:System.Drawing.Graphics.TextRenderingHint%2A> de <xref:System.Drawing.Graphics> en uno de los elementos de la enumeración <xref:System.Drawing.Text.TextRenderingHint>.  
  
## Ejemplo  
 En el ejemplo de código siguiente se dibuja texto con dos configuraciones de calidad diferentes.  
  
 La ilustración siguiente muestra el resultado del código de ejemplo.  
  
 ![Texto de las fuentes](../../../../docs/framework/winforms/advanced/media/fontstext10.png "FontsText10")  
  
 [!code-csharp[System.Drawing.FontsAndText#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  
  
## Compilar el código  
 El ejemplo anterior está diseñado para formularios Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## Vea también  
 [Utilizar fuentes y texto](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)