---
title: Procedimiento Crear un pincel sólido
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- solid color brushes
- brushes [Windows Forms], examples
- brushes [Windows Forms], creating solid
ms.assetid: 85c3fe7d-fb1d-4591-8a9f-d75b556b90af
ms.openlocfilehash: d7fb7c11a69cae69210dd2eece3336bc40c505c7
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711985"
---
# <a name="how-to-create-a-solid-brush"></a>Filtrar Crear un pincel sólido
Este ejemplo se crea un <xref:System.Drawing.SolidBrush> objeto que puede utilizarse por un <xref:System.Drawing.Graphics> objeto para rellenar formas.  
  
## <a name="example"></a>Ejemplo  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## <a name="robust-programming"></a>Programación sólida  
 Cuando haya terminado de usarlos, debe llamar a <xref:System.IDisposable.Dispose%2A> en objetos que consuman recursos del sistema, como los objetos de pincel.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Drawing.SolidBrush>
- <xref:System.Drawing.Brush>
- [Introducción a la programación de gráficos](getting-started-with-graphics-programming.md)
- [Pinceles y formas rellenas en GDI+](brushes-and-filled-shapes-in-gdi.md)
- [Utilizar un pincel para rellenar formas](using-a-brush-to-fill-shapes.md)
