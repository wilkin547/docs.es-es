---
title: Crear y dibujar curvas
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drawing [Windows Forms], curves
- examples [Windows Forms], drawing curves
- curves [Windows Forms], drawing
ms.assetid: 76e92623-4130-4644-b867-faca58bdb3a2
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 801af10f7b9e5e7998fc061537977c5bced6bdb3
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="constructing-and-drawing-curves"></a>Crear y dibujar curvas
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]admite varios tipos de curvas: elipses, arcos, curvas spline cardinales y curvas spline de Bézier. Una elipse se define por su rectángulo delimitador; un arco es una parte de una elipse definida por un ángulo inicial y un ángulo de barrido. Una curva spline cardinal se define mediante una matriz de puntos y un parámetro de tensión: la curva pasa suavemente por cada punto de la matriz, y el parámetro de tensión influye en la forma de la curva. Una curva spline de Bézier se define mediante dos puntos de conexión y dos puntos de control de que la curva no pasa por los puntos de control, pero los puntos de control influyen en la dirección y doblar la curva de tránsito de un extremo a otro.  
  
## <a name="in-this-section"></a>En esta sección  
 [Dibujar curvas spline cardinales](../../../../docs/framework/winforms/advanced/how-to-draw-cardinal-splines.md)  
 Describe las curvas spline cardinales y cómo obtenerlas.  
  
 [Dibujar una curva spline de Bézier](../../../../docs/framework/winforms/advanced/how-to-draw-a-single-bezier-spline.md)  
 Describe una curva spline de Bézier y cómo dibujar uno.  
  
 [Dibujar una secuencia de curvas spline de Bézier](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)  
 Explica cómo dibujar varias curvas spline de Bézier en secuencia.
