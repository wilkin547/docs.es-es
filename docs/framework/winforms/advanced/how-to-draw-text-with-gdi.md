---
title: "C&#243;mo: Dibujar texto con GDI | Microsoft Docs"
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
  - "dibujar, texto"
  - "GDI, dibujar texto [formularios Windows Forms]"
  - "texto, dibujar con TextRenderer"
  - "Windows Forms, dibujar texto con GDI"
ms.assetid: 2a19fe5d-2ace-451c-94db-01cb1118ef7b
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Dibujar texto con GDI
Con el método <xref:System.Windows.Forms.TextRenderer.DrawText%2A> de la clase <xref:System.Windows.Forms.TextRenderer>, puede tener acceso a la funcionalidad de [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] para dibujar texto en un formulario o control.  La representación del texto en [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] normalmente ofrece un mayor rendimiento y una medida más precisa del texto que [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
> [!NOTE]
>  Los métodos <xref:System.Windows.Forms.TextRenderer.DrawText%2A> de la clase <xref:System.Windows.Forms.TextRenderer> no se admiten para imprimir.  Al imprimir, siempre utilice los métodos <xref:System.Drawing.Graphics.DrawString%2A> de la clase <xref:System.Drawing.Graphics>.  
  
## Ejemplo  
 El ejemplo de código siguiente muestra cómo dibujar el texto en varias líneas dentro de un rectángulo con el método <xref:System.Windows.Forms.TextRenderer.DrawText%2A>.  
  
 [!code-csharp[System.Windows.Forms.TextRendererExamples#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.TextRendererExamples#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/VB/Form1.vb#7)]  
  
 Para representar texto con la clase <xref:System.Windows.Forms.TextRenderer>, necesita una interfaz <xref:System.Drawing.IDeviceContext>, como <xref:System.Drawing.Graphics> y <xref:System.Drawing.Font>, una ubicación para dibujar el texto y el color con el que se va a dibujar.  Opcionalmente, puede especificar el formato de texto utilizando la enumeración <xref:System.Windows.Forms.TextFormatFlags>.  
  
 Para obtener más información sobre cómo obtener <xref:System.Drawing.Graphics>, vea [Cómo: Crear objetos Graphics para dibujar](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).  Para obtener más información sobre cómo construir una clase <xref:System.Drawing.Font>, vea [Cómo: Construir fuentes y familias de fuentes](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md).  
  
## Compilar el código  
 El ejemplo anterior está diseñado para formularios Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## Vea también  
 <xref:System.Windows.Forms.TextRenderer>   
 <xref:System.Drawing.Font>   
 <xref:System.Drawing.Color>   
 <xref:System.Drawing.Color>   
 [Utilizar fuentes y texto](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)