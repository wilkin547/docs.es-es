---
title: Procedimiento para establecer el color de un lápiz
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pens [Windows Forms], setting color
- colored pens
ms.assetid: a9df06f9-a6d5-4d9b-a2d1-583943540775
ms.openlocfilehash: ee2d3f8cdf6dd10ca2a9ff0dd3e66b164c84f21b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64637001"
---
# <a name="how-to-set-the-color-of-a-pen"></a>Procedimiento para establecer el color de un lápiz
En este ejemplo se cambia el color de preexistente <xref:System.Drawing.Pen> objeto  
  
## <a name="example"></a>Ejemplo  
 [!code-cpp[System.Drawing.ConceptualHowTos#9](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#9)]
 [!code-csharp[System.Drawing.ConceptualHowTos#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#9)]
 [!code-vb[System.Drawing.ConceptualHowTos#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#9)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Un <xref:System.Drawing.Pen> objeto denominado `myPen`.  
  
## <a name="robust-programming"></a>Programación sólida  
 Debe llamar a <xref:System.Drawing.Pen.Dispose%2A> en los objetos que consumen recursos del sistema (como <xref:System.Drawing.Pen> objetos) cuando haya terminado con ellos.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Pen>
- [Introducción a la programación de gráficos](getting-started-with-graphics-programming.md)
- [Cómo: Crear un lápiz](how-to-create-a-pen.md)
- [Utilizar lápiz para dibujar líneas y formas](using-a-pen-to-draw-lines-and-shapes.md)
- [Lápices, líneas y rectángulos en GDI+](pens-lines-and-rectangles-in-gdi.md)
