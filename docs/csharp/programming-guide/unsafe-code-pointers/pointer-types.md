---
title: Tipos de puntero - Guía de programación de C#
ms.custom: seodec18
ms.date: 04/20/2018
helpviewer_keywords:
- unsafe code [C#], pointers
- pointers [C#]
ms.openlocfilehash: 81e9a86c4761b329918bf04023dea42d2e1ad6f5
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423528"
---
# <a name="pointer-types-c-programming-guide"></a>Tipos de puntero (Guía de programación de C#)

En un contexto no seguro, un tipo puede ser un tipo de puntero, un tipo de valor o un tipo de referencia. Una declaración de tipos de puntero toma una de las siguientes formas:

``` csharp
type* identifier;
void* identifier; //allowed but not recommended
```

El tipo especificado antes de `*` en un tipo de puntero se denomina **tipo referente**. Cualquiera de los tipos siguientes puede ser un tipo referente:

- Cualquier tipo integral: [sbyte](../../language-reference/builtin-types/integral-numeric-types.md), [byte](../../language-reference/builtin-types/integral-numeric-types.md), [short](../../language-reference/builtin-types/integral-numeric-types.md), [ushort](../../language-reference/builtin-types/integral-numeric-types.md), [int](../../language-reference/builtin-types/integral-numeric-types.md), [uint](../../language-reference/builtin-types/integral-numeric-types.md), [long](../../language-reference/builtin-types/integral-numeric-types.md), [ulong](../../language-reference/builtin-types/integral-numeric-types.md).
- Cualquier tipo de punto flotante: [float](../../language-reference/keywords/float.md), [doble](../../language-reference/keywords/double.md).
- [char](../../language-reference/keywords/char.md).
- [bool](../../language-reference/keywords/bool.md).
- [decimal](../../language-reference/keywords/decimal.md).
- Cualquier tipo [enum](../../language-reference/keywords/enum.md).
- Cualquier tipo de puntero. Esto permite expresiones como `void**`.
- Cualquier tipo struct definido por el usuario que solo contenga campos de tipos no administrados.

Los tipos de puntero no heredan de [object](../../language-reference/keywords/object.md) y no existe ninguna conversión entre tipos de puntero y `object`. Además, las conversiones boxing y unboxing no admiten punteros. Sin embargo, puede realizar la conversión entre diferentes tipos de puntero y entre tipos de puntero y tipos enteros.

Cuando declare varios punteros en la misma declaración, únicamente debe escribir el asterisco (*) con el tipo subyacente; no se usa como prefijo en cada nombre de puntero. Por ejemplo:

```csharp
int* p1, p2, p3;   // Ok
int *p1, *p2, *p3;   // Invalid in C#
```

Un puntero no puede señalar a una referencia ni a un [struct](../../language-reference/keywords/struct.md) que contenga referencias, porque una referencia de objeto puede recolectarse como elemento no utilizado aunque haya un puntero que la señale. El recolector de elementos no utilizados no realiza un seguimiento de si algún tipo de puntero señala a un objeto.

El valor de la variable de puntero de tipo `myType*` es la dirección de una variable de tipo `myType`. A continuación se muestran ejemplos de declaraciones de tipos de puntero:

|Ejemplo|DESCRIPCIÓN|
|-------------|-----------------|
|`int* p`|`p` es un puntero a un entero.|
|`int** p`|`p` es un puntero a un puntero a un entero.|
|`int*[] p`|`p` es una matriz unidimensional de punteros a enteros.|
|`char* p`|`p` es un puntero a un valor char.|
|`void* p`|`p` es un puntero a un tipo desconocido.|

El operador de direccionamiento indirecto del puntero * puede usarse para obtener acceso al contenido de la ubicación señalada por la variable de puntero. Por ejemplo, consideremos la siguiente declaración:

```csharp
int* myVariable;
```

La expresión `*myVariable` denota la variable `int` que se encuentra en la dirección contenida en `myVariable`.

Hay varios ejemplos de punteros en los temas [fixed Statement](../../language-reference/keywords/fixed-statement.md) (fixed [Instrucción, Referencia de C#])y [Pointer Conversions](../../programming-guide/unsafe-code-pointers/pointer-conversions.md) (Conversiones de puntero [Guía de programación de C#]). En el ejemplo siguiente se usa la palabra clave `unsafe` y la instrucción `fixed` y se muestra cómo incrementar un puntero interior.  Puede pegar este código en la función Main de una aplicación de consola para ejecutarla. Estos ejemplos deben compilarse con el conjunto de opciones del compilador [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md).

[!code-csharp[Using pointer types](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#5)]

No se puede aplicar el operador de direccionamiento indirecto a un puntero de tipo `void*`. Sin embargo, es posible usar una conversión para convertir un puntero void en cualquier otro tipo de puntero y viceversa.

Un puntero puede ser `null`. La aplicación del operador de direccionamiento indirecto a un puntero NULL da como resultado un comportamiento definido por la implementación.

Pasar punteros entre métodos puede provocar un comportamiento no definido. Valore la posibilidad de usar un método que devuelva un puntero a una variable local mediante un parámetro `in`, `out` o `ref`, o bien como resultado de la función. Si el puntero se estableció en un bloque fijo, es posible que la variable a la que señala ya no sea fija.

En la tabla siguiente se muestran los operadores e instrucciones que pueden funcionar en punteros en un contexto no seguro:

|Operador/Instrucción|Usar|
|-------------------------|---------|
|`*`|Realiza el direccionamiento indirecto del puntero.|
|`->`|Obtiene acceso a un miembro de un struct a través de un puntero.|
|`[]`|Indiza un puntero.|
|`&`|Obtiene la dirección de una variable.|
|`++` y `--`|Incrementa y disminuye los punteros.|
|`+` y `-`|Realiza aritmética con punteros.|
|`==`, `!=`, `<`, `>`, `<=` y `>=`|Compara los punteros.|
|[`stackalloc` operator](../../language-reference/operators/stackalloc.md)|Asigna memoria en la pila.|
|[Instrucción `fixed`](../../language-reference/keywords/fixed-statement.md)|Fija provisionalmente una variable para que pueda encontrarse su dirección.|

Para obtener más información sobre los operadores relacionados con el puntero, vea [Operadores relacionados con el puntero](../../language-reference/operators/pointer-related-operators.md).

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea la sección [Tipos de puntero](~/_csharplang/spec/unsafe-code.md#pointer-types) de [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Código no seguro y punteros](index.md)
- [Conversiones de puntero](pointer-conversions.md)
- [Tipos](../../language-reference/keywords/types.md)
- [unsafe](../../language-reference/keywords/unsafe.md)
