---
title: Procedimiento para aplanar un trazado curvo en una línea
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], flattening curves into lines
- curves [Windows Forms], flattening
- GraphicsPath object
- paths [Windows Forms], flattening
- drawing [Windows Forms], flattening curves
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
ms.openlocfilehash: d59a802618ddd5080c651e822ed4c09641f7f170
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645364"
---
# <a name="how-to-flatten-a-curved-path-into-a-line"></a>Procedimiento para aplanar un trazado curvo en una línea
Un <xref:System.Drawing.Drawing2D.GraphicsPath> objeto almacena una secuencia de líneas y curvas spline de Bézier. Puede agregar varios tipos de curvas (elipses, arcos, curvas spline cardinales) a una ruta de acceso, pero se convierte cada curva en una curva spline de Bézier antes de almacenarse en la ruta de acceso. Acoplamiento de una ruta de acceso consiste en convertir cada curva spline de Bézier en la ruta de acceso a una secuencia de líneas rectas. La siguiente ilustración muestra una ruta de acceso antes y después de hacerlo.  
  
 ![Líneas rectas y curvas](./media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")  
  
### <a name="to-flatten-a-path"></a>Para aplanar un trazado  
  
- Llame a la <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> método de un <xref:System.Drawing.Drawing2D.GraphicsPath> objeto. El <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> método recibe un argumento de aplanamiento que especifica la distancia máxima entre el trazado y la ruta de acceso original.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- [Líneas, curvas y formas](lines-curves-and-shapes.md)
- [Crear y dibujar trazados](constructing-and-drawing-paths.md)
