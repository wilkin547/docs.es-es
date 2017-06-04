---
title: "C&#243;mo: Construir fuentes y familias de fuentes | Microsoft Docs"
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
  - "familias de fuentes, construir"
  - "fuentes, construir"
ms.assetid: d3a4a223-9492-4b54-9afd-db1c31c3cefd
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Construir fuentes y familias de fuentes
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] agrupa las fuentes que tienen el mismo tipo de letra pero distintos estilos en familias de fuentes.  Por ejemplo, la familia de fuentes Arial contiene las siguientes fuentes:  
  
-   Arial Normal  
  
-   Arial Negrita  
  
-   Arial Cursiva  
  
-   Arial Negrita Cursiva  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] utiliza cuatro estilos para formar familias: normal, negrita, cursiva y negrita cursiva.  Los adjetivos como *narrow* y *rounded* no se consideran estilos, si no que forman parte del nombre de la familia.  Por ejemplo, Arial Narrow es una familia de fuentes que contiene los siguientes miembros:  
  
-   Arial Narrow Normal  
  
-   Arial Narrow Negrita  
  
-   Arial Narrow Cursiva  
  
-   Arial Narrow Negrita Cursiva  
  
 Antes de poder dibujar el texto con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], necesita construir un objeto<xref:System.Drawing.FontFamily> y un objeto <xref:System.Drawing.Font>.  El objeto <xref:System.Drawing.FontFamily> especifica el tipo de letra \(por ejemplo, Arial\) y el objeto <xref:System.Drawing.Font> especifica el tamaño, el estilo y las unidades.  
  
## Ejemplo  
 En el ejemplo siguiente se construye una fuente Arial normal con un tamaño de 16 píxeles:  En el código siguiente, el primer argumento pasado al constructor <xref:System.Drawing.Font.%23ctor%2A> es el objeto <xref:System.Drawing.FontFamily>.  El segundo argumento especifica el tamaño de la fuente medido en unidades identificadas por el cuarto argumento.  El tercer argumento identifica el estilo.  
  
 <xref:System.Drawing.GraphicsUnit> es un miembro de la enumeración <xref:System.Drawing.GraphicsUnit> y <xref:System.Drawing.FontStyle> es un miembro de la enumeración <xref:System.Drawing.FontStyle>.  
  
 [!code-csharp[System.Drawing.FontsAndText#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.FontsAndText#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#61)]  
  
## Compilar el código  
 El ejemplo anterior está diseñado para formularios Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## Vea también  
 [Utilizar fuentes y texto](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)   
 [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)