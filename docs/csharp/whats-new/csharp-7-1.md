---
title: Novedades de C# 7.1
description: Información general sobre las nuevas características en C# 7.1.
ms.date: 08/16/2017
ms.openlocfilehash: 565db102284424f9d8f6fa04ec9c74b52c9da0e6
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2018
ms.locfileid: "34728659"
---
# <a name="whats-new-in-c-71"></a>Novedades de C# 7.1

C# 7.1 es la primera versión secundaria del lenguaje C#. Marca una cadencia de versión mayor en el lenguaje. Podrá usar las nuevas características más pronto, lo ideal es que cuando vayan estando listas. C# 7.1 incluye la posibilidad de configurar el compilador para que coincida con una versión especificada del lenguaje. Ello permite aislar la decisión de actualizar las herramientas de la decisión de actualizar las versiones de lenguaje.

C# 7.1 incorpora el elemento de configuración de [selección de versión de lenguaje](../language-reference/configure-language-version.md), tres nuevas características de lenguaje y un nuevo comportamiento del compilador.

Las nuevas características de lenguaje de esta versión son las siguientes:

* [Método `async` `Main`](#async-main)
  - El punto de entrada de una aplicación puede tener el modificador `async`.
* [Expresiones literales `default`](#default-literal-expressions)
  - Se pueden usar expresiones literales predeterminadas en expresiones de valor predeterminadas cuando el tipo de destino se pueda inferir.
* [Nombres de elementos de tupla inferidos](#inferred-tuple-element-names)
  - En muchos casos, los nombres de elementos de tupla se pueden deducir de la inicialización de la tupla.

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

En el tema sobre [async main](../programming-guide/main-and-command-args/index.md) de la guía de programación puede leer más detalles al respecto.

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

Encontrará más información sobre esta mejora en el tema sobre las [expresiones de valor predeterminadas](../programming-guide/statements-expressions-operators/default-value-expressions.md) de la guía de programación de C#.

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

Encontrará más información sobre esta característica en el tema sobre [tuplas](../tuples.md).

## <a name="reference-assembly-generation"></a>Generación de ensamblados de referencia

Existen dos nuevas opciones del compilador con las que se generan *ensamblados solo de referencia*: [/refout](../language-reference/compiler-options/refout-compiler-option.md) y [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).
En los temas de los vínculos se explican estas opciones y los ensamblados de referencia de manera más pormenorizada.
