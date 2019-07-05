---
title: 'Operadores de acceso a miembros: referencia de C#'
description: Obtenga información sobre los operadores de C# que puede usar para acceder a los miembros de tipos.
ms.date: 05/09/2019
author: pkulikov
f1_keywords:
- ._CSharpKeyword
- '[]_CSharpKeyword'
- ()_CSharpKeyword
helpviewer_keywords:
- member access operators [C#]
- member access operator [C#]
- dot operator [C#]
- . operator [C#]
- subscript operator [C#]
- square brackets [] operator [C#]
- indexer operator [C#]
- '[] operator [C#]'
- null-conditional operators [C#]
- Elvis operator [C#]
- ?. operator [C#]
- ?[] operator [C#]
- invocation operator [C#]
- method call [C#]
- method invocation [C#]
- delegate invocation [C#]
- () operator [C#]
ms.openlocfilehash: 4f1d79497f255f52a87dce44f1b5b8709adfada7
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2019
ms.locfileid: "67401474"
---
# <a name="member-access-operators-c-reference"></a>Operadores de acceso a miembros (referencia de C#)

Puede usar los siguientes operadores cuando tiene acceso a un miembro de tipo:

- [`.` (acceso a miembros)](#member-access-operator-): para acceder a un miembro de un espacio de nombres o un tipo
- [`[]` (elemento de matriz o acceso a indizador)](#indexer-operator-): para acceder a un elemento de matriz o un indizador de tipo
- [`?.` y `?[]` (operadores condicionales NULL)](#null-conditional-operators--and-): para realizar una operación de acceso a elementos o miembros solo si un operando es distinto de NULL
- [`()` (invocación)](#invocation-operator-): para llamar a un método de acceso o invocar un delegado

## <a name="member-access-operator-"></a>Operador de acceso a miembros.

Use el token `.` para acceder a un miembro de un espacio de nombres o un tipo, como se muestran en los ejemplos siguientes:

- Use `.` para acceder a un espacio de nombres anidado dentro de un espacio de nombres, como se muestra en el siguiente ejemplo de una [directiva `using`](../keywords/using-directive.md):

  [!code-csharp[nested namespaces](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#NestedNamespace)]

- Use `.` para formar un *nombre completo* para tener acceso a un tipo dentro de un espacio de nombres, como se muestra en el código siguiente:

  [!code-csharp[qualified name](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#QualifiedName)]

  Utilice una [directiva `using`](../keywords/using-directive.md) para hacer que el uso de nombres completos sea opcional.

- Use `.` para tener acceso a los [miembros de tipo](../../programming-guide/classes-and-structs/index.md#members), que no son estáticos y, como se muestra en el código siguiente:

  [!code-csharp-interactive[type members](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#TypeMemberAccess)]

También puede usar `.` para acceder a un [método de extensión](../../programming-guide/classes-and-structs/extension-methods.md).

## <a name="indexer-operator-"></a>Operador del indizador []

Los corchetes, `[]`, se suelen usar para el acceso a matriz, indizador o elemento de puntero.

### <a name="array-access"></a>Acceso a matriz

En el ejemplo siguiente se muestra cómo se obtiene acceso a los elementos de matriz:

[!code-csharp-interactive[array access](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#Arrays)]

Si un índice de matriz se encuentra fuera de los límites de la dimensión correspondiente de una matriz, se produce una excepción <xref:System.IndexOutOfRangeException>.

Tal como se muestra en el ejemplo anterior, también usa corchetes al declarar un tipo de matriz o crear instancias de matriz.

Para obtener más información sobre las matrices, consulte [Matrices](../../programming-guide/arrays/index.md).

### <a name="indexer-access"></a>Acceso a indizador

En el siguiente ejemplo se usa el tipo <xref:System.Collections.Generic.Dictionary%602> de .NET para mostrar el acceso a indizador:

[!code-csharp-interactive[indexer access](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#Indexers)]

Los indizadores le permiten indizar las instancias de un tipo definido por el usuario de un modo similar a la indización de matrices. A diferencia de los índices de matriz, que deben ser enteros, los argumentos de indizador se pueden declarar para ser de cualquier tipo.

Para más información sobre los indizadores, consulte [Indizadores](../../programming-guide/indexers/index.md).

### <a name="other-usages-of-"></a>Otros usos de []

Para información sobre el acceso de los elementos de puntero, consulte la sección [Operador de acceso de elemento de puntero](pointer-related-operators.md#pointer-element-access-operator-) del artículo [Operadores relacionados con el puntero](pointer-related-operators.md).

También usa los corchetes para especificar [atributos](../../programming-guide/concepts/attributes/index.md):

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="null-conditional-operators--and-"></a>Operadores condicionales NULL ?. y ?[]

Disponible en C# 6 y versiones posteriores, un operador condicional NULL aplica una operación de acceso a miembros, `?.`, o acceso a elementos, `?[]`, a su operando solo si dicho operando se evalúa como no NULL. Si el operando se evalúa como `null`, el resultado de aplicar el operador es `null`. El operador de acceso de miembro condicional NULL `?.` también se conoce con el nombre de operador Elvis.

Los operadores de condición NULL se cortocircuitan. Es decir, si una operación en una cadena de la operación de acceso a elementos o miembros condicional devuelve `null`, no se ejecuta el resto de la cadena. En el ejemplo siguiente, `B` no se evalúa si `A` se evalúa como `null` y `C` no se evalúa si `A` o `B` se evalúan como `null`:

```csharp
A?.B?.Do(C);
A?.B?[C];
```

En el siguiente ejemplo se muestra el uso de los operadores `?.` y `?[]`:

[!code-csharp-interactive[null-conditional operators](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#NullConditional)]

El ejemplo anterior también muestra el uso del [operador de uso combinado de NULL](null-coalescing-operator.md). Puede usar el operador de uso combinado de NULL para proporcionar una expresión alternativa a fin de evaluar en caso de que el resultado de la operación condicional NULL sea `null`.

### <a name="thread-safe-delegate-invocation"></a>Invocación de delegado seguro para subprocesos

Use el operador `?.` para comprobar si un delegado es distinto de NULL y se invoca de forma segura para subprocesos (por ejemplo, cuando se [genera un evento](../../../standard/events/how-to-raise-and-consume-events.md)), tal como se muestra en el código siguiente:

```csharp
PropertyChanged?.Invoke(…)
```

Ese código es equivalente al código siguiente que se usaría en C# 5 o una versión anterior:

```csharp
var handler = this.PropertyChanged;
if (handler != null)
{
    handler(…);
}
```

## <a name="invocation-operator-"></a>Operador de invocación ()

Utilice paréntesis, `()`, para llamar a un [método](../../programming-guide/classes-and-structs/methods.md) o invocar un [delegado](../../programming-guide/delegates/index.md).

En el ejemplo siguiente se muestra cómo llamar a un método, con o sin argumentos, y cómo invocar un delegado:

[!code-csharp-interactive[invocation with ()](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#Invocation)]

También usa paréntesis al invocar un [constructor](../../programming-guide/classes-and-structs/constructors.md) con el operador [`new`](new-operator.md).

### <a name="other-usages-of-"></a>Otros usos de ()

También usa los paréntesis para especificar el orden en el que se van a evaluar operaciones en una expresión. Para más información, consulte la sección [Agregar paréntesis](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) del artículo [Operadores](../../programming-guide/statements-expressions-operators/operators.md). Para ver la lista de operadores ordenados por nivel de precedencia, consulte [Operadores de C#](index.md).

[Expresiones de conversión](type-testing-and-conversion-operators.md#cast-operator-), que realizan conversiones de tipo explícitas, también utilizan paréntesis.

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

Los operadores `.` y `()` no se pueden sobrecargar. El operador `[]` también se considera un operador que no se puede sobrecargar. Use [indizadores](../../programming-guide/indexers/index.md) para admitir la indización con tipos definidos por el usuario.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):

- [Acceso a miembros](~/_csharplang/spec/expressions.md#member-access)
- [Acceso a elementos](~/_csharplang/spec/expressions.md#element-access)
- [Operador condicional de NULL](~/_csharplang/spec/expressions.md#null-conditional-operator)
- [Expresiones de invocación](~/_csharplang/spec/expressions.md#invocation-expressions)

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores de C#](index.md)
- [?? (operador de uso combinado de NULL)](null-coalescing-operator.md)
