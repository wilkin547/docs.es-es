---
title: Procedimiento Contraer y ocultar secciones de código (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: 1282269f06f89645c213f3daaa1bd29e95a44d35
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54668722"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a>Procedimiento Contraer y ocultar secciones de código (Visual Basic)
El `#Region` directiva le permite contraer y ocultar secciones de código en archivos de Visual Basic. El `#Region` directiva le permite especificar un bloque de código que se puede expandir o contraer cuando se usa el editor de código de Visual Studio. La capacidad de ocultar selectivamente el código hace que los archivos más fáciles de administrar y más fácil de leer. Para obtener más información, vea [Esquematización](/visualstudio/ide/outlining).  
  
 `#Region` las directivas son compatibles con semántica del bloque de código como `#If...#End If`. Esto significa que no se pueden empezar en un bloque y terminar en otra; en el mismo bloque deben ser el inicio y finalización. `#Region` no se admiten directivas dentro de las funciones.  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a>Para contraer y ocultar una sección de código  
  
-   Coloque la sección de código entre la `#Region` y `#End Region` instrucciones, como en el ejemplo siguiente:  
  
     [!code-vb[VbVbalrConditionalComp#6](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/how-to-collapse-and-hide-sections-of-code_1.vb)]  
  
     El `#Region` bloque se puede usar varias veces en un archivo de código; por lo tanto, los usuarios pueden definir sus propios bloques de procedimientos y las clases que a su vez, se pueden contraer. `#Region` También pueden anidarse dentro de otros bloques `#Region` bloques.  
  
    > [!NOTE]
    >  Ocultar el código no evita que se está compilando y no afecta a `#If...#End If` instrucciones.  
  
## <a name="see-also"></a>Vea también
- [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [#Region (directiva)](../../../visual-basic/language-reference/directives/region-directive.md)
- [#If...Then...#Else (directivas)](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Esquematización](/visualstudio/ide/outlining)
