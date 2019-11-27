---
title: 'Cómo: Crear una variable nueva'
ms.date: 07/20/2015
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
ms.openlocfilehash: 2a2b5b8bef3b66f9727f0e65b61882186c007e94
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353634"
---
# <a name="how-to-create-a-new-variable-visual-basic"></a>Cómo: Crear una nueva variable (Visual Basic)

Cree una variable con una [instrucción Dim](../../../../visual-basic/language-reference/statements/dim-statement.md).

### <a name="to-create-a-new-variable"></a>Para crear una nueva variable

1. Declare la variable en una instrucción `Dim`.

    ```vb
    Dim newCustomer
    ```

2. Incluye especificaciones para las características de la variable, como [Private](../../../../visual-basic/language-reference/modifiers/private.md), [static](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)o [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md). Para obtener más información, vea características de los [elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).

    ```vb
    Public Static newCustomer
    ```

    No necesita la palabra clave `Dim` si usa otras palabras clave en la declaración.

3. Siga las especificaciones con el nombre de la variable, que debe seguir Visual Basic reglas y convenciones. Para obtener más información, vea [nombres de elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).

    ```vb
    Public Static newCustomer
    ```

4. Siga el nombre con la cláusula [as](../../../../visual-basic/language-reference/statements/as-clause.md) para especificar el tipo de datos de la variable.

    ```vb
    Public Static newCustomer As Customer
    ```

    Si no especifica el tipo de datos, utiliza el valor predeterminado: `Object`.

5. Siga la cláusula `As` con un signo igual (`=`) y siga el signo igual con el valor inicial de la variable.

    Visual Basic asigna el valor especificado a la variable cada vez que se ejecuta la instrucción `Dim`. Si no especifica un valor inicial, Visual Basic asigna el valor inicial predeterminado para el tipo de datos de la variable cuando entra por primera vez en el código que contiene la instrucción `Dim`.

    Si la variable es un tipo de referencia, puede crear una instancia de su clase incluyendo la palabra clave [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) en la cláusula `As`. Si no usa `New`, el valor inicial de la variable es [Nothing](../../../../visual-basic/language-reference/nothing.md).

    ```vb
    Public Static newCustomer As New Customer
    ```

## <a name="see-also"></a>Vea también

- [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [Declaración de variables](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Nombres de elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Características de los elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Instrucciones](../../../../visual-basic/language-reference/statements/index.md)
- [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Option Infer (instrucción)](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
