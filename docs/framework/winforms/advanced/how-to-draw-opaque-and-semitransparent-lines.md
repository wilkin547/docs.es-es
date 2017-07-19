---
title: "C&#243;mo: Dibujar l&#237;neas opacas y semitransparentes | Microsoft Docs"
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
  - "combinación alfa, dibujar líneas"
  - "dibujar, líneas"
  - "líneas, dibujar con combinación alfa"
  - "transparencia, líneas"
ms.assetid: 8f2508af-f495-4223-b5cc-646cbbb520eb
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# C&#243;mo: Dibujar l&#237;neas opacas y semitransparentes
Al dibujar una línea, debe pasar un objeto <xref:System.Drawing.Pen> al método <xref:System.Drawing.Graphics.DrawLine%2A> de la clase <xref:System.Drawing.Graphics>.  Uno de los parámetros del constructor <xref:System.Drawing.Pen.%23ctor%2A> es un objeto <xref:System.Drawing.Color>.  Para dibujar una línea opaca, establezca el componente alfa del color en 255.  Para dibujar una línea semitransparente, establezca el componente alfa en cualquier valor entre 1 y 254.  
  
 Cuando se dibuja una línea semitransparente sobre un fondo, el color de la línea se mezcla con los colores del fondo.  El componente alfa especifica cómo se mezclan los colores de la línea y del fondo; los valores alfa cercanos a 0 dan más importancia a los colores de fondo y los cercanos a 255 dan más importancia al color de la línea.  
  
## Ejemplo  
 En el ejemplo siguiente se dibuja un mapa de bits y, después, se dibujan tres líneas que usan el mapa de bits como fondo.  La primera línea usa un componente alfa de 255, por lo que es opaca.  La segunda y tercera líneas usan un componente alfa de 128, por lo que son semitransparentes; puede ver la imagen de fondo a través de las líneas.  La instrucción que establece la propiedad <xref:System.Drawing.Graphics.CompositingQuality%2A> hace que la mezcla de la tercera línea se realice conjuntamente con la corrección gamma.  
  
 En la siguiente ilustración se muestra el resultado del código siguiente.  
  
 ![Opaco y semitransparente](../../../../docs/framework/winforms/advanced/media/compqualline.png "compqualline")  
  
 [!code-csharp[System.Drawing.AlphaBlending#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.AlphaBlending#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#11)]  
  
## Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## Vea también  
 [Líneas y rellenos con mezcla alfa](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)   
 [Cómo: Proporcionar un fondo transparente a un control](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)   
 [Cómo: Dibujar con pinceles opacos y semitransparentes](../../../../docs/framework/winforms/advanced/how-to-draw-with-opaque-and-semitransparent-brushes.md)