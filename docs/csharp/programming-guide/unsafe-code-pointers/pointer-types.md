---
title: Tipos de puntero - Guía de programación de C#
ms.date: 04/20/2018
helpviewer_keywords:
- unsafe code [C#], pointers
- pointers [C#]
ms.openlocfilehash: 7bbfa6b2238458d3248da830cf9d6ac36551b431
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "79507040"
---
# <a name="pointer-types-c-programming-guide"></a>Tipos de puntero (Guía de programación de C#)

En un contexto no seguro, un tipo puede ser un tipo de puntero, un tipo de valor o un tipo de referencia. Una declaración de tipos de puntero toma una de las siguientes formas:

``` csharp
type* identifier;
void* identifier; //allowed but not recommended
```

El tipo especificado antes de `*` en un tipo de puntero se denomina **tipo referente**. Solo un [tipo no administrado](../../language-reference/builtin-types/unmanaged-types.md) puede ser un tipo de referente.

Los tipos de puntero no heredan de [object](../../language-reference/builtin-types/reference-types.md) y no existe ninguna conversión entre tipos de puntero y `object`. Además, las conversiones boxing y unboxing no admiten punteros. Sin embargo, puede realizar la conversión entre diferentes tipos de puntero y entre tipos de puntero y tipos enteros.

Cuando declare varios punteros en la misma declaración, únicamente debe escribir el asterisco (*) con el tipo subyacente; no se usa como prefijo en cada nombre de puntero. Por ejemplo:

```csharp
int* p1, p2, p3;   // Ok
int *p1, *p2, *p3;   // Invalid in C#
```

Un puntero no puede señalar a una referencia ni a un [struct](../../language-reference/builtin-types/struct.md) que contenga referencias, porque una referencia de objeto puede recolectarse como elemento no utilizado aunque haya un puntero que la señale. El recolector de elementos no utilizados no realiza un seguimiento de si algún tipo de puntero señala a un objeto.

El valor de la variable de puntero de tipo `myType*` es la dirección de una variable de tipo `myType`. A continuación se muestran ejemplos de declaraciones de tipos de puntero:

|Ejemplo|Descripción|
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

Hay varios ejemplos de punteros en los temas [fixed (Instrucción)](../../language-reference/keywords/fixed-statement.md) y [Conversiones de puntero (Guía de programación de C#)](./pointer-conversions.md). En el ejemplo siguiente se usa la palabra clave `unsafe` y la instrucción `fixed` y se muestra cómo incrementar un puntero interior.  Puede pegar este código en la función Main de una aplicación de consola para ejecutarla. Estos ejemplos deben compilarse con el conjunto de opciones del compilador [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md).

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
|[`stackalloc`](../../language-reference/operators/stackalloc.md)|Asigna memoria en la pila.|
|[Instrucción `fixed`](../../language-reference/keywords/fixed-statement.md)|Fija provisionalmente una variable para que pueda encontrarse su dirección.|

Para obtener más información sobre los operadores relacionados con el puntero, vea [Operadores relacionados con el puntero](../../language-reference/operators/pointer-related-operators.md).

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea la sección [Tipos de puntero](~/_csharplang/spec/unsafe-code.md#pointer-types) de [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Código no seguro y punteros](index.md)
- [Conversiones de puntero](pointer-conversions.md)
- [Tipos de referencia](../../language-reference/keywords/reference-types.md)
- [Tipos de valor](../../language-reference/builtin-types/value-types.md)
- [unsafe](../../language-reference/keywords/unsafe.md)
