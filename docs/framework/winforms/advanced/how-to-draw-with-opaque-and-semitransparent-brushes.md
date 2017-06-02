---
title: "C&#243;mo: Dibujar con pinceles opacos y semitransparentes | Microsoft Docs"
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
  - "combinación alfa, pincel"
  - "pinceles, con semitransparentes"
  - "formas semitransparentes, dibujar"
  - "transparencia, formas semitransparentes"
ms.assetid: a4f6f6b8-3bc8-440a-84af-d62ef0f8ff40
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# C&#243;mo: Dibujar con pinceles opacos y semitransparentes
Cuando se rellena una forma, se debe pasar un objeto <xref:System.Drawing.Brush> en uno de los métodos de relleno de la clase <xref:System.Drawing.Graphics>.  El único parámetro del constructor <xref:System.Drawing.SolidBrush.%23ctor%2A> es un objeto <xref:System.Drawing.Color>.  Para rellenar una forma opaca, establezca el componente alfa del color en 255.  Para rellenar una forma semitransparente, establezca el componente alfa en cualquier valor entre 1 y 254.  
  
 Cuando se rellena una forma semitransparente, el color de la forma se mezcla con los colores del fondo.  El componente alfa especifica cómo se mezclan los colores de la forma y del fondo; los valores alfa cercanos a 0 dan más importancia a los colores de fondo y los cercanos a 255 dan más importancia al color de la forma.  
  
## Ejemplo  
 En el ejemplo siguiente se dibuja un mapa de bits y después se rellenan tres elipses que se superponen al mapa de bits.  La primera elipse usa un componente alfa de 255, por lo que es opaca.  La segunda y tercera elipses usan un componente alfa de 128, por lo que son semitransparentes; puede ver la imagen de fondo a través de las elipses.  La instrucción que establece la propiedad <xref:System.Drawing.Graphics.CompositingQuality%2A> hace que la mezcla de la tercera elipse se realice conjuntamente con la corrección gamma.  
  
 En la siguiente ilustración se muestra el resultado del código siguiente.  
  
 ![Opaco y semitransparente](../../../../docs/framework/winforms/advanced/media/compqualellipse.png "compqualellipse")  
  
 [!code-csharp[System.Drawing.AlphaBlending#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.AlphaBlending#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#31)]  
  
## Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## Vea también  
 [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Líneas y rellenos con mezcla alfa](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)   
 [Cómo: Proporcionar un fondo transparente a un control](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)   
 [Cómo: Dibujar líneas opacas y semitransparentes](../../../../docs/framework/winforms/advanced/how-to-draw-opaque-and-semitransparent-lines.md)