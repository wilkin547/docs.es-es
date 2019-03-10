---
title: Crear y dibujar curvas
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [Windows Forms], curves
- examples [Windows Forms], drawing curves
- curves [Windows Forms], drawing
ms.assetid: 76e92623-4130-4644-b867-faca58bdb3a2
ms.openlocfilehash: 92e7b1e8b4ce37db633b5dafe212a252b854d1af
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702716"
---
# <a name="constructing-and-drawing-curves"></a>Crear y dibujar curvas
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] admite varios tipos de curvas: elipses, arcos, curvas spline cardinales y curvas spline de Bézier. Una elipse se define por su rectángulo delimitador; un arco es una parte de una elipse definida por un ángulo inicial y un ángulo de barrido. Una curva spline cardinal se define mediante una matriz de puntos y un parámetro de tensión, la curva suavemente pasa por cada punto de la matriz y el parámetro de tensión influye en la manera en que la curva. Una curva spline de Bézier se define mediante dos puntos de conexión y dos puntos de control de que la curva no pasa por los puntos de control, pero los puntos de control influyen en la dirección y doblar la curva de tránsito de un extremo a otro.  
  
## <a name="in-this-section"></a>En esta sección  
 [Cómo: Dibujar curvas spline cardinales](how-to-draw-cardinal-splines.md)  
 Describe las curvas spline cardinales y cómo dibujarlas.  
  
 [Cómo: Dibujar una curva Spline de Bézier](how-to-draw-a-single-bezier-spline.md)  
 Describe una curva spline de Bézier y cómo se dibujan uno.  
  
 [Cómo: Dibujar una secuencia de curvas spline de Bézier](how-to-draw-a-sequence-of-bezier-splines.md)  
 Explica cómo dibujar varias curvas spline de Bézier en secuencia.
