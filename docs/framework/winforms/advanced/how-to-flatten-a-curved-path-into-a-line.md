---
title: 'Cómo: Aplanar un trazado curvo en una línea'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], flattening curves into lines
- curves [Windows Forms], flattening
- GraphicsPath object
- paths [Windows Forms], flattening
- drawing [Windows Forms], flattening curves
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
ms.openlocfilehash: a3a8467dc5906a88911672316bb0f2ed3607d3a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521208"
---
# <a name="how-to-flatten-a-curved-path-into-a-line"></a>Cómo: Aplanar un trazado curvo en una línea
Un <xref:System.Drawing.Drawing2D.GraphicsPath> objeto almacena una secuencia de líneas y curvas spline de Bézier. Puede agregar varios tipos de curvas (elipses, arcos, curvas spline cardinales) a una ruta de acceso, pero cada curva se convierte en una curva spline de Bézier antes de almacenarse en la ruta de acceso. Una ruta de acceso de aplanamiento consiste en convertir cada curva spline de Bézier en la ruta de acceso a una secuencia de líneas rectas. En la siguiente ilustración muestra una ruta de acceso antes y después de la reducción.  
  
 ![Líneas rectas y curvas](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")  
  
### <a name="to-flatten-a-path"></a>Para aplanar un trazado  
  
-   Llame a la <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> método de una <xref:System.Drawing.Drawing2D.GraphicsPath> objeto. El <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> método recibe un argumento de aplanamiento que especifica la distancia máxima entre el trazado aplanado y la ruta de acceso original.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>  
 [Líneas, curvas y formas](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Crear y dibujar trazados](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)
