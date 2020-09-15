---
description: '! (permite valores NULL): referencia de C#'
title: '! (permite valores NULL): referencia de C#'
ms.date: 10/11/2019
f1_keywords:
- nullForgiving_CSharpKeyword
helpviewer_keywords:
- null-forgiving operator [C#]
- '! operator [C#]'
ms.openlocfilehash: 5418f96a3b4515224c49a1c1aa38784c348a86db
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2020
ms.locfileid: "89516156"
---
# <a name="-null-forgiving-operator-c-reference"></a>! (permite valores NULL) (referencia de C#)

Disponible en C# 8.0 y versiones posteriores, el operador `!` de postfijo unario es el operador que permite un valor NULL. En un [contexto de anotación que admite un valor NULL](../../nullable-references.md#nullable-annotation-context) habilitado, se usa el operador que permite un valor NULL para declarar que la expresión `x` de un tipo de referencia no es `null`: `x!`. El operador `!` de prefijo unario es el [operador lógico de negación](boolean-logical-operators.md#logical-negation-operator-).

El operador que permite un valor NULL no tiene ningún efecto en tiempo de ejecución. Solo afecta al análisis de flujo estático del compilador al cambiar el estado NULL de la expresión. En tiempo de ejecución, la expresión `x!` se evalúa en el resultado de la expresión subyacente `x`.

> [!NOTE]
> En C# 8, el operador null-forgiving finaliza la lista de operaciones [null-conditional](member-access-operators.md#null-conditional-operators--and-) anteriores. Por ejemplo, la expresión `x?.y!.z` se analiza como `(x?.y)!.z`. Debido a esta interpretación, `z` se evalúa incluso si `x` es `null`, lo que puede dar lugar a <xref:System.NullReferenceException>.

Para obtener más información sobre la característica de tipos de referencia que admiten un valor NULL, consulte [Tipos de referencia que admiten un valor NULL](../builtin-types/nullable-reference-types.md).

## <a name="examples"></a>Ejemplos

Uno de los casos de uso del operador que permite un valor NULL es probar la lógica de validación de argumentos. Por ejemplo, considere la siguiente clase:

[!code-csharp[Person class](snippets/shared/NullForgivingOperator.cs#PersonClass)]

Con el [marco de pruebas MSTest](../../../core/testing/unit-testing-with-mstest.md) puede crear la prueba siguiente para la lógica de validación en el constructor:

[!code-csharp[Person test](snippets/shared/NullForgivingOperator.cs#TestPerson)]

Sin el operador que permite un valor NULL, el compilador genera la advertencia siguiente para el código anterior: `Warning CS8625: Cannot convert null literal to non-nullable reference type`. Al usar el operador que permite un valor NULL, se notifica al compilador que lo esperado es que se pase `null` y no se debe advertir al respecto.

También puede usar el operador que permite valores NULL cuando sepa a ciencia cierta que una expresión no puede ser `null`, pero el compilador no consigue reconocerlo. En el ejemplo siguiente, si el método `IsValid` devuelve `true`, su argumento no es `null` y puede desreferenciarlo de forma segura:

[!code-csharp[Use null-forgiving operator](snippets/shared/NullForgivingOperator.cs#UseNullForgiving)]

Sin el operador que permite un valor NULL, el compilador genera la advertencia siguiente para el código `p.Name`: `Warning CS8602: Dereference of a possibly null reference`.

Si puede modificar el método `IsValid`, puede usar el atributo [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute) para notificar al compilador que un argumento del método `IsValid` no puede ser `null` cuando el método devuelve `true`:

[!code-csharp[Use an attribute](snippets/shared/NullForgivingOperator.cs#UseAttribute)]

En el ejemplo anterior, no es necesario usar el operador que permite un valor NULL porque el compilador tiene suficiente información para averiguar que `p` no puede ser `null` en la instrucción `if`. Para más información sobre los atributos que permiten proporcionar información adicional sobre el estado NULL de una variable, vea [Actualización de las API con atributos para definir las expectativas NULL](../attributes/nullable-analysis.md).

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, consulte la sección [The null-forgiving operator](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md#the-null-forgiving-operator) (El operador que admite valores NULL) del [borrador de la especificación de tipos de referencia que aceptan valores NULL](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores y expresiones de C#](index.md)
- [Tutorial: Diseño con tipos de referencia que admiten un valor NULL](../../tutorials/nullable-reference-types.md)
