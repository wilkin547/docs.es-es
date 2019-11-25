---
title: Overloads
ms.date: 07/20/2015
f1_keywords:
- vb.Overloads
- Overloads
helpviewer_keywords:
- Overloads keyword [Visual Basic]
- hiding by signature
- Shadows keyword [Visual Basic]
- signature, hiding by
ms.assetid: 0c6820b8-25b2-4664-bc59-5ca93c99c042
ms.openlocfilehash: 44823b409cfa81dc889aabacf101fac90bf851e0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351408"
---
# <a name="overloads-visual-basic"></a>Overloads (Visual Basic)

Especifica que una propiedad o procedimiento vuelve a declarar una o varias propiedades o procedimientos existentes con el mismo nombre.

## <a name="remarks"></a>Comentarios

*Overloading* is the practice of supplying more than one definition for a given property or procedure name in the same scope. Redeclaring a property or procedure with a different signature is sometimes called *hiding by signature*.

## <a name="rules"></a>Reglas

- **Declaration Context.** You can use `Overloads` only in a property or procedure declaration statement.

- **Combined Modifiers.** You cannot specify `Overloads` together with [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) in the same procedure declaration.

- **Required Differences.** The *signature* in this declaration must be different from the signature of every property or procedure that it overloads. La firma incluye el nombre de propiedad o procedimiento más lo siguiente:

  - el número de parámetros

  - el orden de los parámetros

  - los tipos de datos de los parámetros

  - el número de parámetros de tipo (para un procedimiento genérico)

  - el tipo de valor devuelto (solo para un procedimiento de operador de conversión)

  Todas las sobrecargas deben tener el mismo nombre, pero cada una debe diferir de todas las demás en uno o varios de los aspectos anteriores. Esto permite al compilador distinguir qué versión debe utilizar cuando el código llama a la propiedad o el procedimiento.

- **Disallowed Differences.** El cambio de uno o varios de los siguientes aspectos no es válido para sobrecargar una propiedad o un procedimiento, porque no forman parte de la firma:

  - si devuelve o no un valor (para un procedimiento)

  - el tipo de datos del valor devuelto (excepto para un operador de conversión)

  - los nombres de los parámetros o parámetros de tipo

  - las restricciones en los parámetros de tipo (para un procedimiento genérico)

  - palabras clave de modificador de parámetro (como `ByRef` o `Optional`)

  - palabras clave de modificador de propiedad o procedimiento (como `Public` o `Shared`)

- **Optional Modifier.** You do not have to use the `Overloads` modifier when you are defining multiple overloaded properties or procedures in the same class. Sin embargo, si utiliza `Overloads` en una de las declaraciones, debe utilizarlo en todas ellas.

- **Shadowing and Overloading.** `Overloads` can also be used to shadow an existing member, or set of overloaded members, in a base class. Al utilizar `Overloads` de esta forma, declara la propiedad o el método con el mismo nombre y la misma lista de parámetros que el miembro de clase base y no proporciona la palabra clave `Shadows`.

Si usa `Overrides`, el compilador agrega de forma implícita `Overloads` para que las API de la biblioteca trabajen más fácilmente con C#.

El modificador `Overloads` se puede utilizar en los contextos siguientes:

- [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)

- [Operator (instrucción)](../../../visual-basic/language-reference/statements/operator-statement.md)

- [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)

- [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a>Vea también

- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
- [Sobrecarga de procedimientos](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [Definir un operador de conversión](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
