---
description: 'Más información acerca de cómo: crear una variable que no cambie de valor (Visual Basic)'
title: Procedimiento para crear una variable que no cambia de valor
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
ms.openlocfilehash: 0392a27249de3bf604a73c8f8aaa16caf6f1c3e2
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100481940"
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a>Cómo: Crear una variable que no cambia de valor (Visual Basic)

La noción de una variable que no cambia su valor podría parecer contradictoria. Pero hay situaciones en las que una constante no es factible y resulta útil tener una variable con un valor fijo. En tal caso, puede definir una variable miembro con la palabra clave [ReadOnly](../../../language-reference/modifiers/readonly.md) .

No se puede usar la [instrucción const](../../../language-reference/statements/const-statement.md) para declarar y asignar un valor constante en las siguientes circunstancias:

- La `Const` instrucción no acepta el tipo de datos que desea usar

- No conoce el valor en tiempo de compilación

- No se puede calcular el valor constante en tiempo de compilación

### <a name="to-create-a-variable-that-does-not-change-in-value"></a>Para crear una variable que no cambie de valor

1. En el nivel de módulo, declare una variable miembro con la [instrucción Dim](../../../language-reference/statements/dim-statement.md)e incluya la palabra clave [ReadOnly](../../../language-reference/modifiers/readonly.md) .

    ```vb
    Dim ReadOnly timeStarted
    ```

    Solo se puede especificar `ReadOnly` en una variable miembro. Esto significa que debe definir la variable en el nivel de módulo, fuera de cualquier procedimiento.

2. Si puede calcular el valor en una sola instrucción en tiempo de compilación, use una cláusula de inicialización en la `Dim` instrucción. Siga la cláusula [as](../../../language-reference/statements/as-clause.md) con un signo igual ( `=` ), seguido de una expresión. Asegúrese de que el compilador puede evaluar esta expresión en un valor constante.

    ```vb
    Dim ReadOnly timeStarted As Date = Now
    ```

    Puede asignar un valor a una `ReadOnly` variable solo una vez. Una vez hecho esto, ningún código puede cambiar su valor.

    Si no conoce el valor en tiempo de compilación o no puede calcularlo en tiempo de compilación en una sola instrucción, puede asignarlo en tiempo de ejecución en un constructor. Para ello, debe declarar la `ReadOnly` variable en el nivel de clase o estructura. En el constructor de esa clase o estructura, calcule el valor fijo de la variable y asígnelo a la variable antes de volver del constructor.

## <a name="see-also"></a>Consulte también

- [WriteOnly](../../../language-reference/modifiers/writeonly.md)
- [Instrucción Const](../../../language-reference/statements/const-statement.md)
