---
description: ?? Operadores ?? y ?? - Referencia de C#
title: ?? Operadores ?? y ?? - Referencia de C#
ms.date: 09/10/2019
f1_keywords:
- ??_CSharpKeyword
- ??=_CSharpKeyword
helpviewer_keywords:
- null-coalescing operator [C#]
- ?? operator [C#]
- null-coalescing assignment [C#]
- ??= operator [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
ms.openlocfilehash: 273bc6d3a4c65c09dc600621b435bf0d1baea9e4
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89118291"
---
# <a name="-and--operators-c-reference"></a>?? Operadores ?? y ?? (referencia de C#)

El operador de uso combinado de NULL `??` devuelve el valor del operando izquierdo si no es `null`; en caso contrario, evalúa el operando derecho y devuelve su resultado. El operador `??` no evalúa su operando derecho si el operando izquierdo se evalúa como no NULL.

Disponible en C# 8.0 y versiones posteriores, el operador de asignación de uso combinado de NULL `??=` asigna el valor de su operando derecho al operando izquierdo solo si el operando izquierdo se evalúa como `null`. El operador `??=` no evalúa su operando derecho si el operando izquierdo se evalúa como no NULL.

[!code-csharp[null-coalescing assignment](snippets/shared/NullCoalescingOperator.cs#Assignment)]

El operando izquierdo del operador `??=` debe ser una variable, una [propiedad](../../programming-guide/classes-and-structs/properties.md) o un elemento de [indizador](../../programming-guide/indexers/index.md).

En C# 7.3 y versiones anteriores, el tipo del operando izquierdo del operador `??` debe ser un [tipo de referencia](../keywords/reference-types.md) o un [tipo de valor que acepta valores NULL](../builtin-types/nullable-value-types.md). A partir C# 8.0, ese requisito se reemplaza por lo siguiente: el tipo del operando izquierdo de los operadores `??` y `??=` no puede ser un tipo de valor que no acepta valores NULL. En concreto, a partir de C# 8.0 puede usar los operadores de fusión de NULL con parámetros de tipo sin restricciones:

[!code-csharp[unconstrained type parameter](snippets/shared/NullCoalescingOperator.cs#UnconstrainedType)]

Los operadores de uso combinado de NULL son asociativos a la derecha. Es decir, las expresiones del formulario

```csharp
a ?? b ?? c
d ??= e ??= f
```

se evalúan como

```csharp
a ?? (b ?? c)
d ??= (e ??= f)
```

## <a name="examples"></a>Ejemplos

Los operadores `??` y `??=` puede resultar útiles en los siguientes escenarios:

- En expresiones con los [operadores no condicionales ? y ?[]](member-access-operators.md#null-conditional-operators--and-), puede usar el operador `??` para proporcionar una expresión alternativa para evaluar en caso de que el resultado de la expresión con la operación condicional NULL sea `null`:

  [!code-csharp-interactive[with null-conditional](snippets/shared/NullCoalescingOperator.cs#WithNullConditional)]

- Cuando trabaja con [tipos de valor que aceptan valores NULL](../builtin-types/nullable-value-types.md) y necesita proporcionar un valor de un tipo de valor subyacente, use el operador `??` para especificar el valor para proporcionar en caso de que un valor de tipo que acepta valores NULL sea `null`:

  [!code-csharp-interactive[with nullable types](snippets/shared/NullCoalescingOperator.cs#WithNullableTypes)]

  Use el método <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> si el valor que se va usar cuando un valor de tipo que acepta valores NULL es `null` debe ser el valor predeterminado del tipo de valor subyacente.

- A partir de C# 7.0, puede usar una [expresión `throw`](../keywords/throw.md#the-throw-expression) como el operando derecho del operador `??` para hacer el código de comprobación de argumentos más conciso:

  [!code-csharp[with throw expression](snippets/shared/NullCoalescingOperator.cs#WithThrowExpression)]

  El ejemplo anterior también muestra cómo usar [miembros con forma de expresión](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) para definir una propiedad.

- A partir de C# 8.0, puede usar el operador `??=` para reemplazar el código del formulario

  ```csharp
  if (variable is null)
  {
      variable = expression;
  }
  ```

  por el siguiente código:

  ```csharp
  variable ??= expression;
  ```

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

Los operadores `??` y `??=` no se pueden sobrecargar.

## <a name="c-language-specification"></a>especificación del lenguaje C#

Para obtener más información sobre el operador `??`, vea la sección [El operador de uso combinado de NULL](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

Para más información sobre el operador `??=`, consulte la [nota de propuesta de características](~/_csharplang/proposals/csharp-8.0/null-coalescing-assignment.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores y expresiones de C#](index.md)
- [Operadores ?. y ?[]](member-access-operators.md#null-conditional-operators--and-)
- [Operador ?:](conditional-operator.md)
