---
title: Novedades de C# 7.1
description: Información general sobre las nuevas características en C# 7.1.
ms.date: 04/09/2019
ms.openlocfilehash: c79c8576f9cbbd921ebf30bd84ee5a817d6dc6e7
ms.sourcegitcommit: 859b2ba0c74a1a5a4ad0d59a3c3af23450995981
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/11/2019
ms.locfileid: "59480968"
---
# <a name="whats-new-in-c-71"></a>Novedades de C# 7.1

C# 7.1 es la primera versión secundaria del lenguaje C#. Marca una cadencia de versión mayor en el lenguaje. Podrá usar las nuevas características más pronto, lo ideal es que cuando vayan estando listas. C# 7.1 incluye la posibilidad de configurar el compilador para que coincida con una versión especificada del lenguaje. Ello permite aislar la decisión de actualizar las herramientas de la decisión de actualizar las versiones de lenguaje.

C# 7.1 incorpora el elemento de configuración de [selección de versión de lenguaje](../language-reference/configure-language-version.md), tres nuevas características de lenguaje y un nuevo comportamiento del compilador.

Las nuevas características de lenguaje de esta versión son las siguientes:

* [`async` `Main` método](#async-main)
  - El punto de entrada de una aplicación puede tener el modificador `async`.
* [`default` expresiones literales](#default-literal-expressions)
  - Se pueden usar expresiones literales predeterminadas en expresiones de valor predeterminadas cuando el tipo de destino se pueda inferir.
* [Nombres de elementos de tupla inferidos](#inferred-tuple-element-names)
  - En muchos casos, los nombres de elementos de tupla se pueden deducir de la inicialización de la tupla.
* [Coincidencia de patrones en parámetros de tipo genérico](#pattern-matching-on-generic-type-parameters)
  - Puede usar expresiones de coincidencia de patrones en variables cuyo tipo es un parámetro de tipo genérico.

Por último, el compilador tiene dos opciones, `/refout` y `/refonly`, que controlan la [generación de ensamblados de referencia](#reference-assembly-generation).

Para usar las características más recientes en una versión secundaria, tendrá que [configurar la versión del idioma de compilador](../language-reference/configure-language-version.md) y seleccionar la versión.

## <a name="async-main"></a>Async main

Un método *async main* permite usar `await` en el método `Main`.
Anteriormente, hubiera sido necesario escribir lo siguiente:

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

Ahora se puede escribir esto:

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

Si el programa no devuelve un código de salida, puede declarar un método `Main` que devuelva una <xref:System.Threading.Tasks.Task>:

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

En el artículo sobre [async main](../programming-guide/main-and-command-args/index.md) de la guía de programación puede leer más detalles al respecto.

## <a name="default-literal-expressions"></a>Expresiones literales predeterminadas

Las expresiones literales predeterminadas constituyen una mejora con respecto a las expresiones de valor predeterminadas.
Estas expresiones inicializan una variable en el valor predeterminado. Donde anteriormente habría que escribir:

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

Ahora, se puede pasar por alto el tipo del lado derecho de la inicialización:

```csharp
Func<string, bool> whereClause = default;
```

Encontrará más información sobre esta mejora en el artículo sobre las [expresiones de valor predeterminadas](../programming-guide/statements-expressions-operators/default-value-expressions.md) de la guía de programación de C#.

Esta mejora cambia también algunas de las reglas de análisis de [palabras claves predeterminadas](../language-reference/keywords/default.md).

## <a name="inferred-tuple-element-names"></a>Nombres de elementos de tupla inferidos

Esta característica supone una pequeña mejora con respecto a la característica de tuplas incluida en C# 7.0. Muchas veces, cuando se inicializa una tupla, las variables usadas en el lado derecho de la asignación son las mismas que los nombres que querríamos dar a los elementos de tupla:

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

Ahora, los nombres de los elementos de tupla se pueden deducir de las variables empleadas para inicializar la tupla en C# 7.1:

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

Encontrará más información sobre esta característica en el artículo sobre [tuplas](../tuples.md).

## <a name="pattern-matching-on-generic-type-parameters"></a>Coincidencia de patrones en parámetros de tipo genérico

A partir de C# 7.1, la expresión de patrón para `is` y el patrón de tipo `switch` pueden tener el tipo de un parámetro de tipo genérico. Esto puede ser especialmente útil al comprobar los tipos que pueden ser tipos `struct` o `class` y si quiere evitar la conversión boxing.

## <a name="reference-assembly-generation"></a>Generación de ensamblados de referencia

Existen dos nuevas opciones del compilador con las que se generan *ensamblados solo de referencia*: [/refout](../language-reference/compiler-options/refout-compiler-option.md) y [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).
En los artículos de los vínculos se explican estas opciones y los ensamblados de referencia de manera más pormenorizada.
