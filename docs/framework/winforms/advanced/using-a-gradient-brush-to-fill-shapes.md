---
title: "Utilizar un pincel degradado para rellenar formas | Microsoft Docs"
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
  - "pinceles, pinceles degradados"
  - "ejemplos [Windows Forms], pinceles degradados"
  - "pinceles degradados"
ms.assetid: 2c6037b9-05bd-44c0-a22a-19584b722524
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Utilizar un pincel degradado para rellenar formas
Se puede utilizar un pincel degradado para rellenar una forma con un color que cambia gradualmente.  Por ejemplo, se puede utilizar un degradado horizontal para rellenar una forma con un color que cambia gradualmente desde el borde izquierdo de la forma hacia el borde derecho.  Imagínese un rectángulo con un borde izquierdo de color negro \(representado por los componentes rojo, verde y azul 0, 0, 0\) y un borde derecho de color rojo \(representado por 255, 0, 0\).  Si el rectángulo tiene un ancho de 256 píxeles, el componente rojo de un píxel determinado será una unidad mayor que el componente rojo del píxel situado a su izquierda.  El píxel situado más a la izquierda en una fila tiene los componentes de color \(0, 0, 0\), el segundo tiene \(1, 0, 0\), el tercero \(2, 0, 0\) y así sucesivamente, hasta llegar al píxel situado más a la derecha, que tiene los componentes de color \(255, 0, 0\).  Estos valores de color interpolados forman el degradado de color.  
  
 Un degradado lineal cambia el color en un desplazamiento horizontal, vertical o paralelo a una línea inclinada especificada.  Un degradado de trazado cambia el color en un desplazamiento por el interior y el límite de un trazado.  Los degradados de trazados se pueden personalizar para obtener una gran variedad de efectos.  
  
 En la siguiente ilustración se muestra un rectángulo relleno con un pincel degradado lineal y una elipse rellena con un pincel degradado de trazado.  
  
 ![Degradado](../../../../docs/framework/winforms/advanced/media/gradient2.png "gradient2")  
  
## En esta sección  
 [Cómo: Crear un degradado lineal](../../../../docs/framework/winforms/advanced/how-to-create-a-linear-gradient.md)  
 Muestra cómo crear un degradado lineal mediante la clase <xref:System.Drawing.Drawing2D.LinearGradientBrush>.  
  
 [Cómo: Crear un degradado de trazado](../../../../docs/framework/winforms/advanced/how-to-create-a-path-gradient.md)  
 Describe cómo crear un degradado de trazado mediante la clase <xref:System.Drawing.Drawing2D.PathGradientBrush>.  
  
 [Cómo: Aplicar corrección gamma a un degradado](../../../../docs/framework/winforms/advanced/how-to-apply-gamma-correction-to-a-gradient.md)  
 Explica cómo utilizar la corrección gamma con un pincel de degradado.  
  
## Referencia  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=fullName>  
 Contiene una descripción de esta clase y tiene vínculos a todos sus miembros.  
  
 <xref:System.Drawing.Drawing2D.PathGradientBrush?displayProperty=fullName>  
 Contiene una descripción de esta clase y tiene vínculos a todos sus miembros.