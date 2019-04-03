---
title: Filtrar Contraer y ocultar secciones de código (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: bf2a7188456097ac227039e4d902a14eb182664c
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822306"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a>Filtrar Contraer y ocultar secciones de código (Visual Basic)
El `#Region` directiva le permite contraer y ocultar secciones de código en archivos de Visual Basic. El `#Region` directiva le permite especificar un bloque de código que se puede expandir o contraer cuando se usa el editor de código de Visual Studio. La capacidad de ocultar selectivamente el código hace que los archivos más fáciles de administrar y más fácil de leer. Para obtener más información, vea [Esquematización](/visualstudio/ide/outlining).  
  
 `#Region` las directivas son compatibles con semántica del bloque de código como `#If...#End If`. Esto significa que no se pueden empezar en un bloque y terminar en otra; en el mismo bloque deben ser el inicio y finalización. `#Region` no se admiten directivas dentro de las funciones.  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a>Para contraer y ocultar una sección de código  
  
-   Coloque la sección de código entre la `#Region` y `#End Region` instrucciones, como en el ejemplo siguiente:  
  
     [!code-vb[VbVbalrConditionalComp#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#6)]  
  
     El `#Region` bloque se puede usar varias veces en un archivo de código; por lo tanto, los usuarios pueden definir sus propios bloques de procedimientos y las clases que a su vez, se pueden contraer. `#Region` También pueden anidarse dentro de otros bloques `#Region` bloques.  
  
    > [!NOTE]
    >  Ocultar el código no evita que se está compilando y no afecta a `#If...#End If` instrucciones.  
  
## <a name="see-also"></a>Vea también

- [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [#Region (directiva)](../../../visual-basic/language-reference/directives/region-directive.md)
- [#If...Then...#Else (directivas)](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Esquematización](/visualstudio/ide/outlining)
