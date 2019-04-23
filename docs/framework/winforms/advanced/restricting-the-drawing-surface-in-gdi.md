---
title: Limitar la superficie de dibujo en GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, clipping
- clipping [Windows Forms], using GDI+
- GDI+, restricting drawing surface
ms.assetid: 8b5f71d9-d2f0-4540-9c41-740f90fd4c26
ms.openlocfilehash: d0508166f905b45789ce638b03d0747dd6fa904e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59074968"
---
# <a name="restricting-the-drawing-surface-in-gdi"></a>Limitar la superficie de dibujo en GDI+
Recortar implica la restricción del dibujo a un rectángulo o una región determinados. La siguiente ilustración muestra la cadena "Hello" recortada en una región en forma de corazón.  
  
 ![Superficie de dibujo restringida](./media/aboutgdip02-art30.gif "AboutGdip02_Art30")  
  
## <a name="clipping-with-regions"></a>Con regiones de recorte  
 Regiones pueden crearse a partir de las rutas de acceso y las rutas de acceso pueden contener los contornos de cadenas, por lo que puede usar texto con contorno para el recorte. La siguiente ilustración muestra un conjunto de puntos suspensivos concéntricos recortada al interior de una cadena de texto.  
  
 ![Superficie de dibujo restringida](./media/aboutgdip02-art31.gif "AboutGdip02_Art31")  
  
 Para dibujar con recorte, cree un <xref:System.Drawing.Graphics> de objetos, establezca su <xref:System.Drawing.Graphics.Clip%2A> propiedad y, a continuación, llame a los métodos de dibujo de ese mismo <xref:System.Drawing.Graphics> objeto:  
  
 [!code-csharp[LinesCurvesAndShapes#91](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#91)]
 [!code-vb[LinesCurvesAndShapes#91](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#91)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Region?displayProperty=nameWithType>
- [Líneas, curvas y formas](lines-curves-and-shapes.md)
- [Utilizar regiones](using-regions.md)
