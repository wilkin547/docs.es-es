---
title: Procedimiento Crear un lápiz
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], creating pens
- pens [Windows Forms], creating
- Pen object
ms.assetid: 7fbea8b7-7ac1-4413-9c17-733a850381e3
ms.openlocfilehash: 3d88824845bf357dd9ee5f1ee8fd02f095aee605
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716925"
---
# <a name="how-to-create-a-pen"></a>Filtrar Crear un lápiz
Este ejemplo se crea un <xref:System.Drawing.Pen> objeto.  
  
## <a name="example"></a>Ejemplo  
 [!code-cpp[System.Drawing.ConceptualHowTos#3](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#3)]
 [!code-csharp[System.Drawing.ConceptualHowTos#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#3)]
 [!code-vb[System.Drawing.ConceptualHowTos#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#3)]  
  
## <a name="robust-programming"></a>Programación sólida  
 Cuando haya terminado de usar objetos que consumen recursos del sistema, como <xref:System.Drawing.Pen> objetos, debe llamar a <xref:System.Drawing.Pen.Dispose%2A> en ellos.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Drawing.Pen>
- [Introducción a la programación de gráficos](getting-started-with-graphics-programming.md)
- [Lápices, líneas y rectángulos en GDI+](pens-lines-and-rectangles-in-gdi.md)
