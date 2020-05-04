---
title: Operadores relacionados con el puntero (referencia de C#)
description: Obtenga información sobre los operadores de C# que se pueden usar al trabajar con punteros.
ms.date: 05/20/2019
author: pkulikov
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- pointer related operators [C#]
- address-of operator [C#]
- '& operator [C#]'
- pointer indirection operator [C#]
- dereference operator [C#]
- '* operator [C#]'
- pointer member access operator [C#]
- -> operator [C#]
- pointer element access [C#]
- '[] operator [C#]'
- pointer arithmetic [C#]
- pointer increment [C#]
- pointer decrement [C#]
- pointer comparison [C#]
ms.openlocfilehash: 7eb6666d10c44c342f69c7cfc763feb1b7b98c9d
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "81738601"
---
# <a name="pointer-related-operators-c-reference"></a>Operadores relacionados con el puntero (referencia de C#)

Puede usar los siguientes operadores para trabajar con punteros:

- Operador unario [`&` (address-of)](#address-of-operator-): para obtener la dirección de una variable
- Operador unario [`*` (direccionamiento indirecto del puntero)](#pointer-indirection-operator-): para obtener la variable a la que apunta un puntero
- Operadores [`->` (acceso a miembros)](#pointer-member-access-operator--) y [`[]` (acceso de elemento)](#pointer-element-access-operator-)
- Operadores aritméticos [`+`, `-`, `++` y `--`](#pointer-arithmetic-operators)
- Operadores de comparación [`==`, `!=`, `<`, `>`, `<=` y `>=`](#pointer-comparison-operators)

Para obtener información sobre los tipos de punteros, vea [Tipos de puntero](../../programming-guide/unsafe-code-pointers/pointer-types.md).

> [!NOTE]
> Cualquier operación con punteros requiere un contexto [unsafe](../keywords/unsafe.md). El código que contiene bloques no seguros debe compilarse con la opción del compilador [`-unsafe`](../compiler-options/unsafe-compiler-option.md).

## <a name="address-of-operator-amp"></a><a name="address-of-operator-"></a> Operador Address-of &amp;

El operador unario `&` devuelve la dirección de su operando:

[!code-csharp[address of local](snippets/PointerOperators.cs#AddressOf)]

El operando del operador `&` debe ser una variable fija. Las variables *fijas* son las que residen en ubicaciones de almacenamiento que no se ven afectadas por el funcionamiento del [recolector de elementos no utilizados](../../../standard/garbage-collection/index.md). En el ejemplo anterior, la variable local `number` es una variable fija, ya que reside en la pila. Las variables que residen en ubicaciones de almacenamiento que pueden verse afectadas por el recolector de elementos no utilizados (por ejemplo, reubicadas) se denominan variables *móviles*. Los campos de objeto y los elementos de matriz son ejemplos de variables móviles. Puede obtener la dirección de una variable móvil si la "fija" o "ancla" con una [instrucción `fixed`](../keywords/fixed-statement.md). La dirección obtenida solo es válida dentro del bloque de una instrucción `fixed`. En el ejemplo siguiente se muestra cómo usar una instrucción `fixed` y el operador `&`:

[!code-csharp[address of fixed](snippets/PointerOperators.cs#AddressOfFixed)]

No se puede obtener la dirección de una constante o un valor.

Para obtener más información sobre las variables fijas y móviles, vea la sección [Variables fijas y móviles](~/_csharplang/spec/unsafe-code.md#fixed-and-moveable-variables) de [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

El operador binario `&` calcula el [AND lógico](boolean-logical-operators.md#logical-and-operator-) de sus operandos booleanos o el [AND lógico bit a bit](bitwise-and-shift-operators.md#logical-and-operator-) de sus operandos enteros.

## <a name="pointer-indirection-operator-"></a>Operador de direccionamiento indirecto del puntero *

El operador unario de direccionamiento indirecto del puntero `*` obtiene la variable a la que apunta su operando. También se conoce como operador de desreferencia. El operando del operador `*` debe ser un tipo de puntero.

[!code-csharp[pointer indirection](snippets/PointerOperators.cs#PointerIndirection)]

No se puede aplicar el operador `*` a una expresión de tipo `void*`.

El operador binario `*` calcula la [multiplicación](arithmetic-operators.md#multiplication-operator-) de sus operandos numéricos.

## <a name="pointer-member-access-operator--"></a>Operador de acceso a miembros de puntero ->

El operador `->` combina el [direccionamiento indirecto del puntero](#pointer-indirection-operator-) y el [acceso a miembros](member-access-operators.md#member-access-expression-). Es decir, si `x` es un puntero de tipo `T*` y `y` es un miembro accesible de tipo `T`, una expresión con el formato

```csharp
x->y
```

es equivalente a

```csharp
(*x).y
```

En el siguiente ejemplo se muestra el uso del operador `->`:

[!code-csharp[pointer member access](snippets/PointerOperators.cs#MemberAccess)]

No se puede aplicar el operador `->` a una expresión de tipo `void*`.

## <a name="pointer-element-access-operator-"></a>Operador de acceso de elemento de puntero []

En el caso de una expresión `p` de un tipo de puntero, un acceso de elemento de puntero con el formato `p[n]` se evalúa como `*(p + n)`, donde `n` debe ser de un tipo convertible de forma implícita en `int`, `uint`, `long` o `ulong`. Para obtener información sobre el comportamiento del operador `+` con punteros, vea la sección [Suma o resta de un valor entero en un puntero](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer).

En el ejemplo siguiente se muestra cómo acceder a los elementos de matriz con un puntero y el operador `[]`:

[!code-csharp[pointer element access](snippets/PointerOperators.cs#ElementAccess)]

En el ejemplo anterior, una expresión [`stackalloc`](stackalloc.md) asigna un bloque de memoria en la pila.

> [!NOTE]
> El operador de acceso de elemento de puntero no busca errores fuera de límites.

No puede usar `[]` para el acceso de elemento de puntero con una expresión de tipo `void*`.

También puede usar el operador `[]` para [acceso de elemento de matriz o indizador](member-access-operators.md#indexer-operator-).

## <a name="pointer-arithmetic-operators"></a>Operadores aritméticos de puntero

Puede realizar las siguientes operaciones aritméticas con punteros:

- Agregar o restar un valor entero en un puntero
- Restar dos punteros
- Incrementar o reducir un puntero

No es posible realizar esas operaciones con punteros de tipo `void*`.

Para obtener información sobre las operaciones aritméticas admitidas con tipos numéricos, vea [Operadores aritméticos](arithmetic-operators.md).

### <a name="addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer"></a>Suma o resta de un valor entero en un puntero

En el caso de un puntero `p` de tipo `T*` y una expresión `n` de un tipo convertible de forma implícita en `int`, `uint`, `long` o `ulong`, la suma y la resta se definen de este modo:

- Ambas expresiones `p + n` y `n + p` generan un puntero de tipo `T*` que resulta de agregar `n * sizeof(T)` a la dirección proporcionada por `p`.
- La expresión `p - n` genera un puntero de tipo `T*` que resulta de restar `n * sizeof(T)` a la dirección proporcionada por `p`.

El [operador `sizeof`](sizeof.md) obtiene el tamaño de un tipo en bytes.

En el siguiente ejemplo se muestra el uso del operador `+` con un puntero:

[!code-csharp[pointer addition](snippets/PointerOperators.cs#AddNumber)]

### <a name="pointer-subtraction"></a>Resta de puntero

En el caso de dos punteros `p1` y `p2` de tipo `T*`, la expresión `p1 - p2` genera la diferencia entre las direcciones proporcionadas por `p1` y `p2` dividida por `sizeof(T)`. El tipo del resultado es `long`. Es decir, `p1 - p2` se calcula como `((long)(p1) - (long)(p2)) / sizeof(T)`.

El ejemplo siguiente muestra la resta de puntero:

[!code-csharp[pointer subtraction](snippets/PointerOperators.cs#SubtractPointers)]

### <a name="pointer-increment-and-decrement"></a>Incremento y decremento de puntero

El operador de incremento `++`[agrega](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer) 1 a su operando de puntero. El operador de decremento `--`[resta](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer) 1 a su operando de puntero.

Ambos operadores se admiten con dos formatos: postfijo (`p++` y `p--`) y prefijo (`++p` y `--p`). El resultado de `p++` y `p--` es el valor de `p` *antes* de la operación. El resultado de `++p` y `--p` es el valor de `p` *después* de la operación.

El ejemplo siguiente muestra el comportamiento de los operadores de incremento postfijo y prefijo:

[!code-csharp[pointer increment](snippets/PointerOperators.cs#Increment)]

## <a name="pointer-comparison-operators"></a>Operadores de comparación de puntero

Puede usar los operadores `==`, `!=`, `<`, `>`, `<=` y `>=` para comparar los operandos de cualquier tipo de puntero, incluido `void*`. Esos operadores comparan las direcciones proporcionadas por los dos operandos como si fueran enteros sin signo.

Para obtener información sobre el comportamiento de esos operadores para operandos de otros tipos, vea los artículos [Operadores de igualdad](equality-operators.md) y [Operadores de comparación](comparison-operators.md).

## <a name="operator-precedence"></a>Prioridad de operadores

En la lista siguiente se ordenan los operadores relacionados con el puntero desde la prioridad más alta a la más baja:

- Operadores de incremento `x++` y decremento `x--` postfijos y operadores `->` y `[]`
- Operadores de incremento `++x` y decremento `--x` prefijos y operadores `&` y `*`
- Operadores `+` y `-` de suma
- Operadores de comparación `<`, `>`, `<=` y `>=`
- Operadores de igualdad `==` y `!=`

Use paréntesis, `()`, para cambiar el orden de evaluación impuesto por la prioridad de los operadores.

Para obtener la lista completa de los operadores de C# ordenados por nivel de prioridad, vea la sección [Prioridad de operadores](index.md#operator-precedence) del artículo [Operadores de C#](index.md).

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

Un tipo definido por el usuario no puede sobrecargar los operadores relacionados con el puntero `&`, `*`, `->` y `[]`.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):

- [Variables fijas y móviles](~/_csharplang/spec/unsafe-code.md#fixed-and-moveable-variables)
- [El operador address-of](~/_csharplang/spec/unsafe-code.md#the-address-of-operator)
- [Direccionamiento indirecto del puntero](~/_csharplang/spec/unsafe-code.md#pointer-indirection)
- [Acceso a miembros de puntero](~/_csharplang/spec/unsafe-code.md#pointer-member-access)
- [Acceso de elemento de puntero](~/_csharplang/spec/unsafe-code.md#pointer-element-access)
- [Aritmética de puntero](~/_csharplang/spec/unsafe-code.md#pointer-arithmetic)
- [Incremento y decremento de puntero](~/_csharplang/spec/unsafe-code.md#pointer-increment-and-decrement)
- [Comparación de punteros](~/_csharplang/spec/unsafe-code.md#pointer-comparison)

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores de C#](index.md)
- [Tipos de puntero](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [unsafe (palabra clave)](../keywords/unsafe.md)
- [fixed (palabra clave)](../keywords/fixed-statement.md)
- [stackalloc](stackalloc.md)
- [sizeof (operador)](sizeof.md)
