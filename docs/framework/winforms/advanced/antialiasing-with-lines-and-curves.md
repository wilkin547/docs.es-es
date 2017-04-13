---
title: "Suavizado de contorno con l&#237;neas y curvas | Microsoft Docs"
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
  - "suavizado de contorno"
  - "suavizado de contorno, modos de suavizado"
  - "GDI+, suavizado de contorno"
ms.assetid: 810da1a4-c136-4abf-88df-68e49efdd8d4
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Suavizado de contorno con l&#237;neas y curvas
Cuando utiliza [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] para dibujar una línea, proporciona el punto inicial y el punto final de la línea, pero no tiene que suministrar ninguna información sobre los píxeles individuales de la línea.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] funciona junto con el software del controlador de vídeo para determinar qué píxeles se encenderán para mostrar la línea en un dispositivo de presentación determinado.  
  
## Aliasing \(efecto escalonado\)  
 Piense en la línea recta de color rojo que va del punto \(4, 2\) al punto \(16, 10\).  Suponga que el sistema de coordenadas tiene su origen en la esquina superior izquierda y que la unidad de medida es el píxel.  Suponga también que el eje x apunta hacia la derecha y que el eje y apunta hacia abajo.  En la siguiente ilustración se muestra una vista ampliada de la línea roja dibujada sobre un fondo de varios colores.  
  
 ![Línea, sin suavizado de contorno &#40;anti&#45;aliasing&#41;](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art33.png "AboutGdip02\_Art33")  
  
 Los píxeles rojos utilizados para representar la línea son opacos.  No existen píxeles parcialmente transparentes en la línea.  Este tipo de representación de línea le da a ésta una apariencia escalonada y la línea se asemeja un poco a una escalera.  A esta técnica de representación de una línea con una escalera se le denomina "aliasing"; la escalera es un "alias" para la línea teórica.  
  
## Suavizado de contorno  
 Una técnica más sofisticada para la representación de una línea implica el uso de píxeles parcialmente transparentes junto con píxeles opacos.  Los píxeles se establecen en rojo puro, o en cierta mezcla de rojo y el color de fondo, dependiendo de lo próximos que estén de la línea.  Este tipo de representación se denomina suavizado de contorno y el resultado es una línea que el ojo humano percibe como más regular.  En la siguiente ilustración se muestra la forma en que ciertos píxeles se mezclan con el fondo para generar una línea con suavizado de contorno.  
  
 ![Suavizar el contorno de una línea](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art34.png "AboutGdip02\_Art34")  
  
 El suavizado de contorno puede aplicarse también a curvas.  En la siguiente ilustración se muestra una vista ampliada de una elipse suavizada.  
  
 ![Suavizar el contorno de curvas](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art35.png "AboutGdip02\_Art35")  
  
 En la siguiente ilustración se muestra la misma elipse con su tamaño real, una vez sin suavizado de contorno y otra con él.  
  
 ![Ejemplo de suavizado de contorno &#40;anti&#45;aliasing&#41;](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art36.gif "AboutGdip02\_Art36")  
  
 Para dibujar líneas y curvas que utilicen suavizado de contorno, cree una instancia de la clase <xref:System.Drawing.Graphics> y establezca su propiedad <xref:System.Drawing.Graphics.SmoothingMode%2A> en <xref:System.Drawing.Drawing2D.SmoothingMode> o <xref:System.Drawing.Drawing2D.SmoothingMode>.  A continuación, hay que llamar a uno de los métodos de dibujo de la misma clase <xref:System.Drawing.Graphics>.  
  
 [!code-csharp[LinesCurvesAndShapes#81](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#81)]
 [!code-vb[LinesCurvesAndShapes#81](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#81)]  
  
## Vea también  
 <xref:System.Drawing.Drawing2D.SmoothingMode?displayProperty=fullName>   
 [Líneas, curvas y formas](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Cómo: Utilizar la función de suavizado de contorno con texto](../../../../docs/framework/winforms/advanced/how-to-use-antialiasing-with-text.md)