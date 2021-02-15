---
description: 'Más información acerca de cómo: crear una nueva variable (Visual Basic)'
title: Procedimiento para crear una variable
ms.date: 07/20/2015
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
ms.openlocfilehash: b473a247bc5b4d9c1d65f4721ecba3621b232e27
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100481966"
---
# <a name="how-to-create-a-new-variable-visual-basic"></a>Cómo: Crear una nueva variable (Visual Basic)

Cree una variable con una [instrucción Dim](../../../language-reference/statements/dim-statement.md).

### <a name="to-create-a-new-variable"></a>Para crear una nueva variable

1. Declare la variable en una `Dim` instrucción.

    ```vb
    Dim newCustomer
    ```

2. Incluye especificaciones para las características de la variable, como [Private](../../../language-reference/modifiers/private.md), [static](../../../language-reference/modifiers/static.md), [Shadows](../../../language-reference/modifiers/shadows.md)o [WithEvents](../../../language-reference/modifiers/withevents.md). Para obtener más información, vea características de los [elementos declarados](../declared-elements/declared-element-characteristics.md).

    ```vb
    Public Static newCustomer
    ```

    No necesita la `Dim` palabra clave si utiliza otras palabras clave en la declaración.

3. Siga las especificaciones con el nombre de la variable, que debe seguir Visual Basic reglas y convenciones. Para obtener más información, vea [nombres de elementos declarados](../declared-elements/declared-element-names.md).

    ```vb
    Public Static newCustomer
    ```

4. Siga el nombre con la cláusula [as](../../../language-reference/statements/as-clause.md) para especificar el tipo de datos de la variable.

    ```vb
    Public Static newCustomer As Customer
    ```

    Si no se especifica el tipo de datos, se usa el valor predeterminado: `Object` .

5. Siga la `As` cláusula con un signo igual ( `=` ) y siga el signo igual con el valor inicial de la variable.

    Visual Basic asigna el valor especificado a la variable cada vez que se ejecuta la `Dim` instrucción. Si no especifica un valor inicial, Visual Basic asigna el valor inicial predeterminado para el tipo de datos de la variable cuando entra por primera vez en el código que contiene la `Dim` instrucción.

    Si la variable es un tipo de referencia, puede crear una instancia de su clase incluyendo la palabra clave [New Operator](../../../language-reference/operators/new-operator.md) en la `As` cláusula. Si no usa `New` , el valor inicial de la variable es [Nothing](../../../language-reference/nothing.md).

    ```vb
    Public Static newCustomer As New Customer
    ```

## <a name="see-also"></a>Consulte también

- [Variables](index.md)
- [Declaración de variable](variable-declaration.md)
- [Declared Element Names](../declared-elements/declared-element-names.md)
- [Características de los elementos declarados](../declared-elements/declared-element-characteristics.md)
- [Tipos de valor y tipos de referencia](../data-types/value-types-and-reference-types.md)
- [Instrucciones](../../../language-reference/statements/index.md)
- [Inferencia de tipo de variable local](local-type-inference.md)
- [Option Infer (instrucción)](../../../language-reference/statements/option-infer-statement.md)
