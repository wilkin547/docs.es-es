---
title: 'Operadores y expresiones de acceso a miembros: referencia de C#'
description: Obtenga información sobre los operadores de C# que puede usar para acceder a los miembros de tipos.
ms.date: 04/17/2020
author: pkulikov
f1_keywords:
- ._CSharpKeyword
- '[]_CSharpKeyword'
- ()_CSharpKeyword
- ^_CSharpKeyword
- .._CSharpKeyword
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
- ^ operator [C#]
- index from end operator [C#]
- hat operator [C#]
- .. operator [C#]
- range operator [C#]
ms.openlocfilehash: 59e01b17d78032714803629d503a92ba86a20fdc
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83394641"
---
# <a name="member-access-operators-and-expressions-c-reference"></a>Operadores y expresiones de acceso a miembros (referencia de C#)

Puede usar los operadores y expresiones siguientes cuando accede a un miembro de tipo:

- [`.` (acceso a miembros)](#member-access-expression-): para acceder a un miembro de un espacio de nombres o un tipo
- [`[]` (elemento de matriz o acceso a indizador)](#indexer-operator-): para acceder a un elemento de matriz o un indizador de tipo
- [`?.` y `?[]` (operadores condicionales NULL)](#null-conditional-operators--and-): para realizar una operación de acceso a elementos o miembros solo si un operando es distinto de NULL
- [`()` (invocación)](#invocation-expression-): para llamar a un método de acceso o invocar un delegado
- [`^` (índice desde el final) ](#index-from-end-operator-): para indicar que la posición del elemento se encuentra a partir del final de una secuencia
- [`..` (intervalo)](#range-operator-): para especificar un intervalo de índices que puede utilizar para obtener un intervalo de elementos de secuencia

## <a name="member-access-expression-"></a>Expresión de acceso a miembros.

Use el token `.` para acceder a un miembro de un espacio de nombres o un tipo, como se muestran en los ejemplos siguientes:

- Use `.` para acceder a un espacio de nombres anidado dentro de un espacio de nombres, como se muestra en el siguiente ejemplo de una [directiva `using`](../keywords/using-directive.md):

  [!code-csharp[nested namespaces](snippets/MemberAccessOperators.cs#NestedNamespace)]

- Use `.` para formar un *nombre completo* para tener acceso a un tipo dentro de un espacio de nombres, como se muestra en el código siguiente:

  [!code-csharp[qualified name](snippets/MemberAccessOperators.cs#QualifiedName)]

  Utilice una [directiva `using`](../keywords/using-directive.md) para hacer que el uso de nombres completos sea opcional.

- Use `.` para tener acceso a los [miembros de tipo](../../programming-guide/classes-and-structs/index.md#members), que no son estáticos y, como se muestra en el código siguiente:

  [!code-csharp-interactive[type members](snippets/MemberAccessOperators.cs#TypeMemberAccess)]

También puede usar `.` para acceder a un [método de extensión](../../programming-guide/classes-and-structs/extension-methods.md).

## <a name="indexer-operator-"></a>Operador del indizador []

Los corchetes, `[]`, se suelen usar para el acceso a matriz, indizador o elemento de puntero.

### <a name="array-access"></a>Acceso a matriz

En el ejemplo siguiente se muestra cómo se obtiene acceso a los elementos de matriz:

[!code-csharp-interactive[array access](snippets/MemberAccessOperators.cs#Arrays)]

Si un índice de matriz se encuentra fuera de los límites de la dimensión correspondiente de una matriz, se produce una excepción <xref:System.IndexOutOfRangeException>.

Tal como se muestra en el ejemplo anterior, también usa corchetes al declarar un tipo de matriz o crear instancias de matriz.

Para obtener más información sobre las matrices, consulte [Matrices](../../programming-guide/arrays/index.md).

### <a name="indexer-access"></a>Acceso a indizador

En el ejemplo siguiente se usa el tipo <xref:System.Collections.Generic.Dictionary%602> de .NET para mostrar el acceso al indizador:

[!code-csharp-interactive[indexer access](snippets/MemberAccessOperators.cs#Indexers)]

Los indizadores le permiten indizar las instancias de un tipo definido por el usuario de un modo similar a la indización de matrices. A diferencia de los índices de matriz, que deben ser enteros, los parámetros de indizador se pueden declarar para ser de cualquier tipo.

Para más información sobre los indizadores, consulte [Indizadores](../../programming-guide/indexers/index.md).

### <a name="other-usages-of-"></a>Otros usos de []

Para información sobre el acceso de los elementos de puntero, consulte la sección [Operador de acceso de elemento de puntero](pointer-related-operators.md#pointer-element-access-operator-) del artículo [Operadores relacionados con el puntero](pointer-related-operators.md).

También usa los corchetes para especificar [atributos](../../programming-guide/concepts/attributes/index.md):

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="null-conditional-operators--and-"></a>Operadores condicionales NULL ?. y ?[]

Disponible en C# 6 y versiones posteriores, un operador condicional NULL aplica una operación de [acceso a miembros](#member-access-expression-), `?.`, o [acceso a elementos](#indexer-operator-), `?[]`, a su operando solo si dicho operando se evalúa como no `null`. Es decir:

- Si `a` se evalúa como `null`, el resultado de `a?.x` o `a?[x]` es `null`.
- Si `a` se evalúa como no NULL, el resultado de `a?.x` o `a?[x]` es el mismo que el resultado de `a.x` o `a[x]`, respectivamente.

  > [!NOTE]
  > Si `a.x` o `a[x]` producen una excepción, `a?.x` o `a?[x]` produciría la misma excepción para `a` no NULL. Por ejemplo, si `a` es una instancia de matriz que no es NULL y `x` está fuera de los límites de `a`, `a?[x]` produciría una excepción <xref:System.IndexOutOfRangeException>.

Los operadores de condición NULL se cortocircuitan. Es decir, si una operación en una cadena de la operación de acceso a elementos o miembros condicional devuelve `null`, no se ejecuta el resto de la cadena. En el ejemplo siguiente, `B` no se evalúa si `A` se evalúa como `null` y `C` no se evalúa si `A` o `B` se evalúan como `null`:

```csharp
A?.B?.Do(C);
A?.B?[C];
```

En el siguiente ejemplo se muestra el uso de los operadores `?.` y `?[]`:

[!code-csharp-interactive[null-conditional operators](snippets/MemberAccessOperators.cs#NullConditional)]

En el ejemplo anterior también se usa el [operador de fusión de NULL `??`](null-coalescing-operator.md) para especificar una expresión alternativa que se evaluará en caso de que el resultado de la operación condicional NULL sea `null`.

Si `a.x` o `a[x]` es de un tipo de valor que no admite un valor NULL, `T`, `a?.x` o `a?[x]` es del [tipo de valor que admite un valor NULL](../builtin-types/nullable-value-types.md) `T?` correspondiente. Si necesita una expresión de tipo `T`, aplique el operador de fusión de NULL `??` a una expresión condicional NULL, tal como se muestra en el ejemplo siguiente:

[!code-csharp-interactive[null-conditional with null-coalescing](snippets/MemberAccessOperators.cs#NullConditionalWithNullCoalescing)]

En el ejemplo anterior, si no utiliza el operador `??`, `numbers?.Length < 2` da como resultado `false` cuando `numbers` es `null`.

El operador de acceso de miembro condicional NULL `?.` también se conoce con el nombre de operador Elvis.

> [!NOTE]
> En C# 8, el [operador null-forgiving](null-forgiving.md) finaliza la lista de operaciones null-conditional anteriores. Por ejemplo, la expresión `x?.y!.z` se analiza como `(x?.y)!.z`. Debido a esta interpretación, `z` se evalúa incluso si `x` es `null`, lo que puede dar lugar a <xref:System.NullReferenceException>.

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

Es un modo seguro para subprocesos de asegurarse de que solo se invoca un `handler` que no es NULL. Dado que las instancias de delegado son inmutables, ningún subproceso puede cambiar el valor al que hace referencia la variable local `handler`. En concreto, si el código que ha ejecutado otro subproceso cancela la suscripción del evento `PropertyChanged` y `PropertyChanged` se convierte en `null` antes de que se invoque `handler`, el objeto al que hace referencia `handler` queda intacto. El operador `?.` evalúa el operando de la izquierda no más de una vez, lo que garantiza que no se pueda cambiar a `null` después de verificarse como no NULL.

## <a name="invocation-expression-"></a>Expresión de invocación ()

Utilice paréntesis, `()`, para llamar a un [método](../../programming-guide/classes-and-structs/methods.md) o invocar un [delegado](../../programming-guide/delegates/index.md).

En el ejemplo siguiente se muestra cómo llamar a un método, con o sin argumentos, y cómo invocar un delegado:

[!code-csharp-interactive[invocation with ()](snippets/MemberAccessOperators.cs#Invocation)]

También usa paréntesis al invocar un [constructor](../../programming-guide/classes-and-structs/constructors.md) con el operador [`new`](new-operator.md).

### <a name="other-usages-of-"></a>Otros usos de ()

También usa los paréntesis para ajustar el orden en el que se van a evaluar operaciones en una expresión. Para obtener más información, vea [Operadores de C# (referencia de C#)](index.md).

[Expresiones de conversión](type-testing-and-cast.md#cast-expression), que realizan conversiones de tipo explícitas, también utilizan paréntesis.

## <a name="index-from-end-operator-"></a>Indexación desde el operador final ^

Disponible en C# 8.0 y versiones posteriores, el operador `^` indica la posición del elemento a partir del final de una secuencia. En el caso de una secuencia de longitud `length`, `^n` apunta al elemento con desplazamiento `length - n` desde el inicio de una secuencia. Por ejemplo, `^1` apunta al último elemento de una secuencia y `^length` apunta al primer elemento de una secuencia.

[!code-csharp[index from end](snippets/MemberAccessOperators.cs#IndexFromEnd)]

Como se muestra en el ejemplo anterior, la expresión `^e` es del tipo <xref:System.Index?displayProperty=nameWithType>. En la expresión `^e`, el resultado de `e` debe poderse convertir implícitamente a `int`.

También puede usar el operador `^` con el [operador de intervalo](#range-operator-) para crear un intervalo de índices. Para más información, consulte [Índices y rangos](../../tutorials/ranges-indexes.md).

## <a name="range-operator-"></a>Operador de intervalo .

Disponible en C# 8.0 y versiones posteriores, el operador `..` especifica el inicio y el final de un intervalo de índices como sus operandos. El operando izquierdo es un inicio *inclusivo* de un intervalo. El operando derecho es un inicio *exclusivo* de un intervalo. Cualquiera de los operandos puede ser un índice desde el inicio o desde el final de una secuencia, tal y como muestra el ejemplo siguiente:

[!code-csharp[range examples](snippets/MemberAccessOperators.cs#Ranges)]

Como se muestra en el ejemplo anterior, la expresión `a..b` es del tipo <xref:System.Range?displayProperty=nameWithType>. En la expresión `a..b`, los resultados de `a` y `b` deben poderse convertir implícitamente a `int` o <xref:System.Index>.

Puede omitir cualquiera de los operandos del operador `..` para obtener un intervalo abierto:

- `a..` es equivalente a `a..^0`
- `..b` es equivalente a `0..b`
- `..` es equivalente a `0..^0`

[!code-csharp[ranges with omitted operands](snippets/MemberAccessOperators.cs#RangesOptional)]

Para más información, consulte [Índices y rangos](../../tutorials/ranges-indexes.md).

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

Los operadores `.`, `()`, `^` y `..` no se pueden sobrecargar. El operador `[]` también se considera un operador que no se puede sobrecargar. Use [indizadores](../../programming-guide/indexers/index.md) para admitir la indización con tipos definidos por el usuario.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):

- [Acceso a miembros](~/_csharplang/spec/expressions.md#member-access)
- [Acceso a elementos](~/_csharplang/spec/expressions.md#element-access)
- [Operador condicional de NULL](~/_csharplang/spec/expressions.md#null-conditional-operator)
- [Expresiones de invocación](~/_csharplang/spec/expressions.md#invocation-expressions)

Para más información sobre índices y rangos, vea la [nota de propuesta de características](~/_csharplang/proposals/csharp-8.0/ranges.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores de C#](index.md)
- [?? (operador de uso combinado de NULL)](null-coalescing-operator.md)
- [Operador ::](namespace-alias-qualifier.md)
