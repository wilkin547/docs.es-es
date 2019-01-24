---
title: Procedimiento Establecer el Color de un lápiz
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pens [Windows Forms], setting color
- colored pens
ms.assetid: a9df06f9-a6d5-4d9b-a2d1-583943540775
ms.openlocfilehash: d0402a7d6bb641ef6d97eb41bc25f3c59b3b4250
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54569445"
---
# <a name="how-to-set-the-color-of-a-pen"></a>Procedimiento Establecer el Color de un lápiz
En este ejemplo se cambia el color de preexistente <xref:System.Drawing.Pen> objeto  
  
## <a name="example"></a>Ejemplo  
 [!code-cpp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#9)]
 [!code-csharp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#9)]
 [!code-vb[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#9)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un <xref:System.Drawing.Pen> objeto denominado `myPen`.  
  
## <a name="robust-programming"></a>Programación sólida  
 Debe llamar a <xref:System.Drawing.Pen.Dispose%2A> en los objetos que consumen recursos del sistema (como <xref:System.Drawing.Pen> objetos) cuando haya terminado con ellos.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Drawing.Pen>
- [Introducción a la programación de gráficos](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)
- [Cómo: Crear un lápiz](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)
- [Utilizar lápiz para dibujar líneas y formas](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
- [Lápices, líneas y rectángulos en GDI+](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)
