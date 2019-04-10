---
title: Filtrar para establecer el color de un lápiz
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pens [Windows Forms], setting color
- colored pens
ms.assetid: a9df06f9-a6d5-4d9b-a2d1-583943540775
ms.openlocfilehash: dc067f5a131951bf3af7adc68e11b948d40fc0ca
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213420"
---
# <a name="how-to-set-the-color-of-a-pen"></a>Filtrar para establecer el color de un lápiz
En este ejemplo se cambia el color de preexistente <xref:System.Drawing.Pen> objeto  
  
## <a name="example"></a>Ejemplo  
 [!code-cpp[System.Drawing.ConceptualHowTos#9](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#9)]
 [!code-csharp[System.Drawing.ConceptualHowTos#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#9)]
 [!code-vb[System.Drawing.ConceptualHowTos#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#9)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un <xref:System.Drawing.Pen> objeto denominado `myPen`.  
  
## <a name="robust-programming"></a>Programación sólida  
 Debe llamar a <xref:System.Drawing.Pen.Dispose%2A> en los objetos que consumen recursos del sistema (como <xref:System.Drawing.Pen> objetos) cuando haya terminado con ellos.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Pen>
- [Introducción a la programación de gráficos](getting-started-with-graphics-programming.md)
- [Filtrar para crear un lápiz](how-to-create-a-pen.md)
- [Utilizar lápiz para dibujar líneas y formas](using-a-pen-to-draw-lines-and-shapes.md)
- [Lápices, líneas y rectángulos en GDI+](pens-lines-and-rectangles-in-gdi.md)
