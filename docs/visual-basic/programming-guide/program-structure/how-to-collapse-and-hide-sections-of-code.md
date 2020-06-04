---
title: Procedimiento Contracción y ocultación de secciones de código
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: c11affe9c4dd4251ba8ff4b87029d314970b5fcb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404854"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a>Cómo: Contraer y ocultar secciones de código (Visual Basic)

La `#Region` directiva permite contraer y ocultar secciones de código en archivos de Visual Basic. La `#Region` directiva permite especificar un bloque de código que se puede expandir o contraer cuando se usa el editor de código de Visual Studio. La capacidad de ocultar el código de forma selectiva facilita la administración y la lectura de los archivos. Para obtener más información, vea [Esquematización](/visualstudio/ide/outlining).

`#Region`las directivas admiten la semántica de bloques de código como `#If...#End If` . Esto significa que no pueden comenzar en un bloque y finalizar en otro; el inicio y el final deben estar en el mismo bloque. `#Region`no se admiten directivas en las funciones.

## <a name="to-collapse-and-hide-a-section-of-code"></a>Para contraer y ocultar una sección de código

Coloque la sección de código entre las `#Region` `#End Region` instrucciones y, como en el ejemplo siguiente:

[!code-vb[VbVbalrConditionalComp#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#6)]

El `#Region` bloque se puede usar varias veces en un archivo de código; por lo tanto, los usuarios pueden definir sus propios bloques de procedimientos y clases que, a su vez, se pueden contraer. `#Region`los bloques también se pueden anidar dentro de otros `#Region` bloques.

> [!NOTE]
> Ocultar código no impide que se compile y no afecta a las `#If...#End If` instrucciones.

## <a name="see-also"></a>Consulte también

- [Compilación condicional](conditional-compilation.md)
- [#Region (Directiva)](../../language-reference/directives/region-directive.md)
- [#If...Then...#Else (directivas)](../../language-reference/directives/if-then-else-directives.md)
- [esquematizar](/visualstudio/ide/outlining)
