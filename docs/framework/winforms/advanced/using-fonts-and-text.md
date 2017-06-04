---
title: "Utilizar fuentes y texto | Microsoft Docs"
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
  - "ejemplos [Windows Forms], fuentes y texto"
  - "fuentes, usar en Windows Forms"
  - "GDI, dibujar texto [formularios Windows Forms]"
  - "cadenas [formularios Windows Forms], dibujar en formularios Windows Forms"
  - "texto [Windows Forms], dibujar en formularios Windows Forms"
ms.assetid: d43640f3-da94-4df2-a29d-a9d021a1c069
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Utilizar fuentes y texto
Hay varias clases proporcionadas por [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] y [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] para dibujar texto en Windows Forms.  La clase <xref:System.Drawing.Graphics> de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] tiene varios métodos <xref:System.Drawing.Graphics.DrawString%2A> que permiten especificar varias características de texto, como ubicación, rectángulo delimitador, fuente y formato.  Además, puede dibujar y medir el texto con [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] utilizando los métodos <xref:System.Windows.Forms.TextRenderer.DrawText%2A> y <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> estáticos proporcionados por la clase `TextRenderer`.  Los métodos [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] también le permiten especificar la ubicación, la fuente y el formato.  Puede elegir [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] o [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] para representar texto; sin embargo, [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] generalmente proporciona mejor rendimiento y una medición de texto más precisa.  Otras clases que contribuyen a la representación del texto incluyen `FontFamily`, `Font`, <xref:System.Drawing.StringFormat> y `TextFormatFlags`.  
  
## En esta sección  
 [Cómo: Construir fuentes y familias de fuentes](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)  
 Muestra cómo crear objetos `Font` y `FontFamily`.  
  
 [Cómo: Dibujar texto en una ubicación especificada](../../../../docs/framework/winforms/advanced/how-to-draw-text-at-a-specified-location.md)  
 Describe cómo dibujar texto en una determinada ubicación utilizando [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] y [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  
  
 [Cómo: Dibujar texto ajustado en un rectángulo](../../../../docs/framework/winforms/advanced/how-to-draw-wrapped-text-in-a-rectangle.md)  
 Explica cómo dibujar texto en un rectángulo mediante [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] y [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  
  
 [Cómo: Dibujar texto con GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 Muestra cómo utilizar [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] para dibujar texto.  
  
 [Cómo: Alinear texto dibujado](../../../../docs/framework/winforms/advanced/how-to-align-drawn-text.md)  
 Muestra cómo dar formato a texto [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] y [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  
  
 [Cómo: Crear texto vertical](../../../../docs/framework/winforms/advanced/how-to-create-vertical-text.md)  
 Describe cómo dibujar texto alineado verticalmente con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
 [Cómo: Establecer posiciones de tabulación en texto dibujado](../../../../docs/framework/winforms/advanced/how-to-set-tab-stops-in-drawn-text.md)  
 Muestra cómo dibujar texto con posiciones de tabulación con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
 [Cómo: Enumerar las fuentes instaladas](../../../../docs/framework/winforms/advanced/how-to-enumerate-installed-fonts.md)  
 Describe cómo mostrar los nombres de fuentes instaladas.  
  
 [Cómo: Crear una colección de fuentes privada](../../../../docs/framework/winforms/advanced/how-to-create-a-private-font-collection.md)  
 Describe cómo crear un objeto <xref:System.Drawing.Text.PrivateFontCollection>.  
  
 [Cómo: Obtener medidas de fuentes](../../../../docs/framework/winforms/advanced/how-to-obtain-font-metrics.md)  
 Muestra cómo obtener medidas de fuente como el ascenso y descenso de celda.  
  
 [Cómo: Utilizar la función de suavizado de contorno con texto](../../../../docs/framework/winforms/advanced/how-to-use-antialiasing-with-text.md)  
 Explica cómo utilizar el suavizado de contorno al dibujar el texto.  
  
## Referencia  
 <xref:System.Drawing.Font>  
 Describe esta clase y contiene vínculos a todos sus miembros.  
  
 <xref:System.Drawing.FontFamily>  
 Describe esta clase y contiene vínculos a todos sus miembros.  
  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 Describe esta clase y contiene vínculos a todos sus miembros.  
  
 <xref:System.Windows.Forms.TextRenderer>  
 Describe esta clase y contiene vínculos a todos sus miembros.  
  
 <xref:System.Windows.Forms.TextFormatFlags>  
 Describe esta clase y contiene vínculos a todos sus miembros.