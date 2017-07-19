---
title: "Crear y dibujar curvas | Microsoft Docs"
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
  - "curvas, dibujar"
  - "dibujar, curvas"
  - "ejemplos [Windows Forms], dibujar curvas"
ms.assetid: 76e92623-4130-4644-b867-faca58bdb3a2
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Crear y dibujar curvas
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] admite varios tipos de curvas: elipses, arcos, curvas spline cardinales y curvas spline de Bézier.  Una elipse queda definida por su rectángulo delimitador; un arco es parte de una elipse definida por un ángulo de inicio y un ángulo de barrido.  Una curva spline cardinal queda definida por una matriz de puntos y un parámetro de tensión: la curva pasa suavemente por cada punto de la matriz y el parámetro de tensión influye el modo en que se inclina la curva.  Una curva spline de Bézier queda definida por dos puntos extremos y dos puntos de control: la curva no pasa por los puntos de control, pero estos puntos influyen en la dirección y la inclinación del recorrido de la curva de un extremo a otro.  
  
## En esta sección  
 [Cómo: Dibujar curvas spline cardinales](../../../../docs/framework/winforms/advanced/how-to-draw-cardinal-splines.md)  
 Describe las curvas spline cardinales y cómo dibujarlas.  
  
 [Cómo: Dibujar una curva spline de Bézier](../../../../docs/framework/winforms/advanced/how-to-draw-a-single-bezier-spline.md)  
 Describe una curva spline de Bézier y cómo dibujar una.  
  
 [Cómo: Dibujar una secuencia de curvas spline de Bézier](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)  
 Explica cómo dibujar varias curvas spline de Bézier secuencialmente.