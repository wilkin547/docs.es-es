---
title: Procedimiento Crear una variable que no cambie de valor (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
ms.openlocfilehash: d201e95463dd0431825fee03ebfd340ac80cc552
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630886"
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a>Procedimiento Crear una variable que no cambie de valor (Visual Basic)

La noción de una variable que no cambia su valor podría parecer contradictoria. Pero hay situaciones en las que una constante no es factible y resulta útil tener una variable con un valor fijo. En tal caso, puede definir una variable miembro con la palabra clave [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) .

No se puede usar la [instrucción const](../../../../visual-basic/language-reference/statements/const-statement.md) para declarar y asignar un valor constante en las siguientes circunstancias:

- La `Const` instrucción no acepta el tipo de datos que desea usar

- No conoce el valor en tiempo de compilación

- No se puede calcular el valor constante en tiempo de compilación

### <a name="to-create-a-variable-that-does-not-change-in-value"></a>Para crear una variable que no cambie de valor

1. En el nivel de módulo, declare una variable miembro con la [instrucción Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)e incluya la palabra clave [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) .

    ```vb
    Dim ReadOnly timeStarted
    ```

    Solo se puede `ReadOnly` especificar en una variable miembro. Esto significa que debe definir la variable en el nivel de módulo, fuera de cualquier procedimiento.

2. Si puede calcular el valor en una sola instrucción en tiempo de compilación, use una cláusula de inicialización en `Dim` la instrucción. Siga la cláusula [as](../../../../visual-basic/language-reference/statements/as-clause.md) con un signo igual (`=`), seguido de una expresión. Asegúrese de que el compilador puede evaluar esta expresión en un valor constante.

    ```vb
    Dim ReadOnly timeStarted As Date = Now
    ```

    Puede asignar un valor a una `ReadOnly` variable solo una vez. Una vez hecho esto, ningún código puede cambiar su valor.

    Si no conoce el valor en tiempo de compilación o no puede calcularlo en tiempo de compilación en una sola instrucción, puede asignarlo en tiempo de ejecución en un constructor. Para ello, debe declarar la variable en `ReadOnly` el nivel de clase o estructura. En el constructor de esa clase o estructura, calcule el valor fijo de la variable y asígnelo a la variable antes de volver del constructor.

## <a name="see-also"></a>Vea también

- [WriteOnly](../../../../visual-basic/language-reference/modifiers/writeonly.md)
- [Const (instrucción)](../../../../visual-basic/language-reference/statements/const-statement.md)
