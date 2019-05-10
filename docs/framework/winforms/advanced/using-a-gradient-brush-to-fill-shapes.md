---
title: Utilizar un pincel degradado para rellenar formas
ms.date: 03/30/2017
helpviewer_keywords:
- brushes [Windows Forms], gradient brushes
- gradient brushes
- examples [Windows Forms], gradient brushes
ms.assetid: 2c6037b9-05bd-44c0-a22a-19584b722524
ms.openlocfilehash: 7ff555ba4fd81e9123e5f9e9feed38a0ec9d0a08
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063597"
---
# <a name="using-a-gradient-brush-to-fill-shapes"></a>Utilizar un pincel degradado para rellenar formas
Puede utilizar un pincel de degradado para rellenar una forma con un color cambio gradualmente. Por ejemplo, puede utilizar un degradado horizontal para rellenar una forma con un color que cambia gradualmente a medida que se desplaza desde el borde izquierdo de la forma para el borde derecho. Imagine un rectángulo con un borde izquierdo de color negro (representado por los componentes rojos, verde y azules 0, 0, 0) y un borde derecho de color rojo (representado por 255, 0, 0). Si el rectángulo es 256 píxeles de ancho, el componente rojo de un píxel determinado será una unidad mayor que el componente rojo del píxel a su izquierda. El píxel situado en una fila tiene los componentes de color (0, 0, 0), el segundo tiene (1, 0, 0), el tercer píxel tiene (2, 0, 0) y así sucesivamente, hasta llegar al píxel más a la derecha, que tiene componentes de color (255, 0, 0). Estos valores de color interpolado constituyen el degradado de color.  
  
 Un degradado lineal cambia de color se mueve horizontalmente, verticalmente o en paralelo para una línea inclinada especificada. Un degradado de trazado cambia de color se mueve sobre el interior y el límite de una ruta de acceso. Puede personalizar los degradados de ruta de acceso para lograr una gran variedad de efectos.  
  
 La siguiente ilustración se muestra un rectángulo relleno con un pincel de degradado lineal y una elipse rellena con un pincel de degradado de la ruta de acceso:  
  
 ![Un rectángulo relleno con un pincel de degradado con una elipse.](./media/using-a-gradient-brush-to-fill-shapes/rectangle-ellipse-gradient-brush.png)  
  
## <a name="in-this-section"></a>En esta sección  
 [Cómo: Crear un degradado lineal](how-to-create-a-linear-gradient.md)  
 Muestra cómo crear un uso de degradado lineal el <xref:System.Drawing.Drawing2D.LinearGradientBrush> clase.  
  
 [Cómo: Crear un degradado de trazado](how-to-create-a-path-gradient.md)  
 Describe cómo crear un degradado de ruta de acceso mediante la <xref:System.Drawing.Drawing2D.PathGradientBrush> clase.  
  
 [Cómo: Aplicar corrección Gamma a un degradado](how-to-apply-gamma-correction-to-a-gradient.md)  
 Explica cómo usar la corrección gamma con un pincel de degradado.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 Contiene una descripción de esta clase y contiene vínculos a todos sus miembros.  
  
 <xref:System.Drawing.Drawing2D.PathGradientBrush?displayProperty=nameWithType>  
 Contiene una descripción de esta clase y contiene vínculos a todos sus miembros.
