---
title: Utilizar un pincel degradado para rellenar formas
ms.date: 03/30/2017
helpviewer_keywords:
- brushes [Windows Forms], gradient brushes
- gradient brushes
- examples [Windows Forms], gradient brushes
ms.assetid: 2c6037b9-05bd-44c0-a22a-19584b722524
ms.openlocfilehash: 857a9276a731ae5e69b3caa1a639d1315aba9901
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="using-a-gradient-brush-to-fill-shapes"></a>Utilizar un pincel degradado para rellenar formas
Puede utilizar un pincel de degradado para rellenar una forma con un color que cambia gradualmente. Por ejemplo, puede utilizar un degradado horizontal para rellenar una forma con un color que cambia gradualmente a medida que se desplaza desde el borde izquierdo de la forma para el borde derecho. Imagine un rectángulo con un borde izquierdo es negro (representado por los componentes rojos, verde y azules 0, 0, 0) y un borde derecho de color rojo (representado por 255, 0, 0). Si el rectángulo es 256 píxeles de ancho, el componente rojo de un píxel determinado será una unidad mayor que el componente rojo del píxel situado a su izquierda. El píxel situado en una fila tiene componentes de color (0, 0, 0), el segundo tiene (1, 0, 0), el tercer píxel (2, 0, 0) y así sucesivamente, hasta llegar al píxel más a la derecha, que tiene componentes de color (255, 0, 0). Estos valores de color interpolados forman el degradado de color.  
  
 Un degradado lineal cambia de color se mueve horizontalmente, verticalmente o en paralelo a una línea inclinada especificada. Un degradado de trazado cambia de color se mueve sobre el interior y el límite de una ruta de acceso. Puede personalizar degradados de ruta de acceso para lograr una gran variedad de efectos.  
  
 La ilustración siguiente muestra un rectángulo relleno con un pincel de degradado lineal y una elipse rellena con un pincel de degradado de trazado.  
  
 ![Degradado](../../../../docs/framework/winforms/advanced/media/gradient2.png "gradient2")  
  
## <a name="in-this-section"></a>En esta sección  
 [Crear un degradado lineal](../../../../docs/framework/winforms/advanced/how-to-create-a-linear-gradient.md)  
 Muestra cómo crear un utilizando degradado lineal la <xref:System.Drawing.Drawing2D.LinearGradientBrush> clase.  
  
 [Crear un degradado de trazado](../../../../docs/framework/winforms/advanced/how-to-create-a-path-gradient.md)  
 Describe cómo crear un degradado de ruta de acceso utilizando la <xref:System.Drawing.Drawing2D.PathGradientBrush> clase.  
  
 [Aplicar corrección gamma a un degradado](../../../../docs/framework/winforms/advanced/how-to-apply-gamma-correction-to-a-gradient.md)  
 Explica cómo utilizar la corrección gamma con un pincel de degradado.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 Contiene una descripción de esta clase y contiene vínculos a todos sus miembros.  
  
 <xref:System.Drawing.Drawing2D.PathGradientBrush?displayProperty=nameWithType>  
 Contiene una descripción de esta clase y contiene vínculos a todos sus miembros.
