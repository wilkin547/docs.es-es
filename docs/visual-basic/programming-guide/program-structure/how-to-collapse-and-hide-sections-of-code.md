---
title: 'Cómo: Contraer y ocultar secciones de código'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: e7aacdc3f41199127b00d276b382ec4a5f258da0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347406"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a>Cómo: Contraer y ocultar secciones de código (Visual Basic)

La Directiva `#Region` permite contraer y ocultar secciones de código en archivos de Visual Basic. La Directiva `#Region` permite especificar un bloque de código que se puede expandir o contraer cuando se usa el editor de código de Visual Studio. La capacidad de ocultar el código de forma selectiva facilita la administración y la lectura de los archivos. Para obtener más información, vea [Esquematización](/visualstudio/ide/outlining).

las directivas de `#Region` admiten la semántica de bloques de código como `#If...#End If`. Esto significa que no pueden comenzar en un bloque y finalizar en otro; el inicio y el final deben estar en el mismo bloque. las directivas de `#Region` no se admiten en funciones.

## <a name="to-collapse-and-hide-a-section-of-code"></a>Para contraer y ocultar una sección de código

Coloque la sección de código entre las instrucciones `#Region` y `#End Region`, como en el ejemplo siguiente:

[!code-vb[VbVbalrConditionalComp#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#6)]

El bloque `#Region` se puede usar varias veces en un archivo de código; por lo tanto, los usuarios pueden definir sus propios bloques de procedimientos y clases que, a su vez, se pueden contraer. `#Region` bloques también se pueden anidar dentro de otros bloques de `#Region`.

> [!NOTE]
> Ocultar código no impide que se compile y no afecta a `#If...#End If` instrucciones.

## <a name="see-also"></a>Vea también

- [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [#Region (directiva)](../../../visual-basic/language-reference/directives/region-directive.md)
- [#If...Then...#Else (directivas)](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Esquematización](/visualstudio/ide/outlining)
