---
title: Sobrecargas
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
ms.openlocfilehash: bd0931cab520f8580c0d7473a44e350752e287bb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392111"
---
# <a name="overloads-visual-basic"></a>Overloads (Visual Basic)

Especifica que una propiedad o procedimiento vuelve a declarar una o varias propiedades o procedimientos existentes con el mismo nombre.

## <a name="remarks"></a>Observaciones

La *sobrecarga* es la práctica de proporcionar más de una definición para un nombre de propiedad o procedimiento determinado en el mismo ámbito. La Redeclaración de una propiedad o un procedimiento con una firma diferente se denomina a veces *ocultar por firma*.

## <a name="rules"></a>Reglas

- **Contexto de declaración.** Solo se puede usar `Overloads` en una instrucción de declaración de propiedad o procedimiento.

- **Modificadores combinados.** No se puede especificar `Overloads` junto con [Shadows](shadows.md) en la misma declaración de procedimiento.

- **Diferencias requeridas.** La *firma* de esta declaración debe ser diferente de la firma de cada propiedad o procedimiento que sobrecarga. La firma incluye el nombre de propiedad o procedimiento más lo siguiente:

  - el número de parámetros

  - el orden de los parámetros

  - los tipos de datos de los parámetros

  - el número de parámetros de tipo (para un procedimiento genérico)

  - el tipo de valor devuelto (solo para un procedimiento de operador de conversión)

  Todas las sobrecargas deben tener el mismo nombre, pero cada una debe diferir de todas las demás en uno o varios de los aspectos anteriores. Esto permite al compilador distinguir qué versión debe utilizar cuando el código llama a la propiedad o el procedimiento.

- **Diferencias no permitidas.** El cambio de uno o varios de los siguientes aspectos no es válido para sobrecargar una propiedad o un procedimiento, porque no forman parte de la firma:

  - si devuelve o no un valor (para un procedimiento)

  - el tipo de datos del valor devuelto (excepto para un operador de conversión)

  - los nombres de los parámetros o parámetros de tipo

  - las restricciones en los parámetros de tipo (para un procedimiento genérico)

  - palabras clave de modificador de parámetro (como `ByRef` o `Optional`)

  - palabras clave de modificador de propiedad o procedimiento (como `Public` o `Shared`)

- **Modificador opcional.** No es necesario usar el `Overloads` modificador al definir varias propiedades o procedimientos sobrecargados en la misma clase. Sin embargo, si utiliza `Overloads` en una de las declaraciones, debe utilizarlo en todas ellas.

- **Sombreado y sobrecarga.** `Overloads`también se puede utilizar para sombrear un miembro existente, o un conjunto de miembros sobrecargados, en una clase base. Al utilizar `Overloads` de esta forma, declara la propiedad o el método con el mismo nombre y la misma lista de parámetros que el miembro de clase base y no proporciona la palabra clave `Shadows`.

Si usa `Overrides`, el compilador agrega de forma implícita `Overloads` para que las API de la biblioteca trabajen más fácilmente con C#.

El modificador `Overloads` se puede utilizar en los contextos siguientes:

- [Instrucción Function](../statements/function-statement.md)

- [Operator Statement](../statements/operator-statement.md)

- [Property Statement](../statements/property-statement.md)

- [Instrucción Sub](../statements/sub-statement.md)

## <a name="see-also"></a>Consulte también

- [Shadows](shadows.md)
- [Sobrecarga de procedimientos](../../programming-guide/language-features/procedures/procedure-overloading.md)
- [Tipos genéricos en Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
- [Procedimientos de operador](../../programming-guide/language-features/procedures/operator-procedures.md)
- [Procedimiento para definir un operador de conversión](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
