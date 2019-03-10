---
title: Líneas y rellenos con mezcla alfa
ms.date: 03/30/2017
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
ms.openlocfilehash: 7a8286fb741effaf668b87e90da04f79d1490de2
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716002"
---
# <a name="alpha-blending-lines-and-fills"></a>Líneas y rellenos con mezcla alfa
En [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], un color es un valor de 32 bits con 8 bits para alfa, rojo, verde y azul. El valor alfa indica la transparencia del color, la extensión a la que el color se mezcla con el color de fondo. Intervalo de valores alfa de 0 a 255, donde 0 representa un color completamente transparente, y 255 representa un color completamente opaco.  
  
 Combinación alfa es una mezcla de píxel a píxel de datos de origen y de fondo de color. Cada uno de los tres componentes (rojo, verde, azul) de un color de origen dado se mezcla con el componente correspondiente del color de fondo según la siguiente fórmula:  
  
 displayColor = sourceColor × alfa / 255 + backgroundColor × (alfa de 255 –) / 255  
  
 Por ejemplo, supongamos que el componente rojo del color de origen es 150 y el componente rojo del color de fondo es 100. Si el valor alfa es 200, el componente rojo del color resultante se calcula como sigue:  
  
 150 × 200 / 255 + 100 × (255 – 200) / 255 = 139  
  
## <a name="in-this-section"></a>En esta sección  
 [Cómo: Dibujar líneas opacas y semitransparentes](how-to-draw-opaque-and-semitransparent-lines.md)  
 Se muestra cómo dibujar líneas con mezcla alfa.  
  
 [Cómo: Dibujar con pinceles opacos y semitransparentes](how-to-draw-with-opaque-and-semitransparent-brushes.md)  
 Explica cómo realizar la mezcla alfa con pinceles.  
  
 [Cómo: Usar el modo de composición para controlar la mezcla alfa](how-to-use-compositing-mode-to-control-alpha-blending.md)  
 Describe cómo controlar la combinación alfa usando <xref:System.Drawing.Drawing2D.CompositingMode>.  
  
 [Cómo: Use una matriz de colores para establecer valores alfabéticos en imágenes](how-to-use-a-color-matrix-to-set-alpha-values-in-images.md)  
 Explica cómo utilizar un <xref:System.Drawing.Imaging.ColorMatrix> objeto para controlar la mezcla alfa.
