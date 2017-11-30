---
title: "Líneas y rellenos con mezcla alfa"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- lines [Windows Forms], adding transparency
- examples [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with lines
- alpha blending
- lines [Windows Forms], alpha blending
- fills [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with fills
- shapes [Windows Forms], adding transparency
ms.assetid: 5440f48c-3ac9-44c3-b170-c1c110bdbab8
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5b3c0ee3ec82d4d8447c43b7dc9b275591ebe890
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="alpha-blending-lines-and-fills"></a>Líneas y rellenos con mezcla alfa
En [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], un color es un valor de 32 bits con 8 bits para alfa, rojo, verde y azul. El valor alfa indica la transparencia del color, la extensión a la que el color se mezcla con el color de fondo. Los valores alfa oscilan entre 0 y 255, donde 0 representa un color totalmente transparente, y 255 representa un color totalmente opaco.  
  
 Combinación alfa es una mezcla píxel por píxel de los datos de color de fondo y fuente. Cada uno de los tres componentes (rojo, verde, azul) de un color de origen dado se mezcla con el componente correspondiente del color de fondo según la siguiente fórmula:  
  
 displayColor = sourceColor × alfa / 255 + backgroundColor × (alfa de 255 –) / 255  
  
 Por ejemplo, imagine que el componente rojo del color de origen es 150 y el componente rojo del color de fondo es 100. Si el valor alfa es 200, el componente rojo del color resultante se calcula como sigue:  
  
 150 × 200 / 255 + 100 × (255 – 200) / 255 = 139  
  
## <a name="in-this-section"></a>En esta sección  
 [Dibujar líneas opacas y semitransparentes](../../../../docs/framework/winforms/advanced/how-to-draw-opaque-and-semitransparent-lines.md)  
 Muestra cómo dibujar líneas con mezcla alfa.  
  
 [Dibujar con pinceles opacos y semitransparentes](../../../../docs/framework/winforms/advanced/how-to-draw-with-opaque-and-semitransparent-brushes.md)  
 Explica cómo realizar la mezcla alfa con pinceles.  
  
 [Utilizar el modo de composición para controlar la mezcla alfa](../../../../docs/framework/winforms/advanced/how-to-use-compositing-mode-to-control-alpha-blending.md)  
 Describe cómo controlar la mezcla alfa mediante <xref:System.Drawing.Drawing2D.CompositingMode>.  
  
 [Utilizar una matriz de colores para establecer valores alfa en imágenes](../../../../docs/framework/winforms/advanced/how-to-use-a-color-matrix-to-set-alpha-values-in-images.md)  
 Explica cómo utilizar un <xref:System.Drawing.Imaging.ColorMatrix> objeto que se va a controlar la mezcla alfa.
