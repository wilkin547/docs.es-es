---
title: "L&#237;neas y rellenos con mezcla alfa | Microsoft Docs"
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
  - "combinación alfa"
  - "combinación alfa, con rellenos"
  - "combinación alfa, con líneas"
  - "ejemplos [Windows Forms], combinación alfa"
  - "rellenos, combinación alfa"
  - "líneas, agregar transparencia"
  - "líneas, combinación alfa"
  - "formas, agregar transparencia"
ms.assetid: 5440f48c-3ac9-44c3-b170-c1c110bdbab8
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# L&#237;neas y rellenos con mezcla alfa
En [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], un color es un valor de 32 bits con 8 bits para cada uno de los siguientes valores: alfa, rojo, verde y azul.  El valor alfa indica la transparencia del color; es decir, la medida en que el color se mezcla con el color de fondo.  Los valores alfa van de 0 a 255, donde 0 representa un color totalmente transparente y 255 un color totalmente opaco.  
  
 La mezcla alfa es una mezcla píxel por píxel de los datos de color de origen y de fondo.  Cada uno de los tres componentes \(rojo, verde y azul\) de un color de origen dado se mezcla con el componente correspondiente del color de fondo, según la siguiente fórmula:  
  
 displayColor \= sourceColor × alpha \/ 255 \+ backgroundColor × \(255 – alpha\) \/ 255  
  
 Por ejemplo, supongamos que el componente rojo del color de origen es 150 y el componente rojo del color de fondo es 100.  Si el valor alfa es 200, el componente rojo del color resultante se calcula de la siguiente manera:  
  
 150 × 200 \/ 255 \+ 100 × \(255 – 200\) \/ 255 \= 139  
  
## En esta sección  
 [Cómo: Dibujar líneas opacas y semitransparentes](../../../../docs/framework/winforms/advanced/how-to-draw-opaque-and-semitransparent-lines.md)  
 Muestra cómo dibujar líneas con mezcla alfa.  
  
 [Cómo: Dibujar con pinceles opacos y semitransparentes](../../../../docs/framework/winforms/advanced/how-to-draw-with-opaque-and-semitransparent-brushes.md)  
 Explica cómo realizar la mezcla alfa con pinceles.  
  
 [Cómo: Utilizar el modo de composición para controlar la mezcla alfa](../../../../docs/framework/winforms/advanced/how-to-use-compositing-mode-to-control-alpha-blending.md)  
 Describe cómo controlar la mezcla alfa mediante <xref:System.Drawing.Drawing2D.CompositingMode>.  
  
 [Cómo: Utilizar una matriz de colores para establecer valores alfa en imágenes](../../../../docs/framework/winforms/advanced/how-to-use-a-color-matrix-to-set-alpha-values-in-images.md)  
 Explica cómo utilizar un objeto <xref:System.Drawing.Imaging.ColorMatrix> para controlar la mezcla alfa.