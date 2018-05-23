---
title: Novedades de C# 7.1
description: Información general sobre las nuevas características en C# 7.1.
ms.date: 08/16/2017
ms.openlocfilehash: 00baec45d7582d3ac12c7b0865241f5cd8159246
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="whats-new-in-c-71"></a>Novedades de C# 7.1

C# 7.1 es la primera versión secundaria del lenguaje C#. Marca una cadencia de versión mayor en el lenguaje. Podrá usar las nuevas características más pronto, lo ideal es que cuando vayan estando listas. C# 7.1 incluye la posibilidad de configurar el compilador para que coincida con una versión especificada del lenguaje. Ello permite aislar la decisión de actualizar las herramientas de la decisión de actualizar las versiones de lenguaje.

C# 7.1 incorpora el elemento de configuración de [selección de versión de lenguaje](#language-version-selection), tres nuevas características de lenguaje y un nuevo comportamiento del compilador.

Las nuevas características de lenguaje de esta versión son las siguientes:

* [Método `async` `Main`](#async-main)
  - El punto de entrada de una aplicación puede tener el modificador `async`.
* [Expresiones literales `default`](#default-literal-expressions)
  - Se pueden usar expresiones literales predeterminadas en expresiones de valor predeterminadas cuando el tipo de destino se pueda inferir.
* [Nombres de elementos de tupla inferidos](#inferred-tuple-element-names)
  - En muchos casos, los nombres de elementos de tupla se pueden deducir de la inicialización de la tupla.

Por último, el compilador tiene dos opciones, `/refout` y `/refonly`, que controlan la [generación de ensamblados de referencia](#reference-assembly-generation).

## <a name="language-version-selection"></a>Selección de versión del lenguaje

El compilador de C# admite C# 7.1 desde Visual Studio 2017 versión 15.3 o el SDK de .NET Core 2.0. Las siguientes características de 7.1, en cambio, están deshabilitadas de forma predeterminada. Para habilitarlas, debe cambiar la configuración de la versión de lenguaje del proyecto.

En el Explorador de soluciones de Visual Studio, haga clic con el botón derecho en el nodo de proyecto y seleccione **Propiedades**. Seleccione la pestaña **Compilar** y, después, el botón **Opciones avanzadas**. En la lista desplegable, seleccione **C# latest minor version (latest)** (última versión secundaria de C# [más reciente]) o la versión específica **C# 7.1**, tal y como se muestra en la siguiente imagen. El valor `latest` indica que se va a usar la versión secundaria más reciente en el equipo actual. `C# 7.1` señala que se quiere usar C# 7.1, aun cuando posteriormente se lancen versiones secundarias más recientes.

![Establecer la versión de lenguaje](./media/csharp-7-1/advanced-build-settings.png)

También puede editar el archivo "csproj" y agregar o modificar las siguientes líneas:

```xml
<PropertyGroup>
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

> [!NOTE]
> Si usa el IDE de Visual Studio para actualizar los archivos csproj, este creará nodos independientes por cada configuración de compilación existente. Normalmente, se establece el mismo valor en todas las configuraciones de compilación, pero deberá establecerse de forma explícita en cada configuración de compilación, o bien seleccionar "All Configurations" (Todas las configuraciones) cuando este valor se modifique. Verá lo siguiente en el archivo csproj:

```xml
<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>

<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

Estos son los valores válidos en el elemento `LangVersion`:

* `ISO-1`
* `ISO-2`
* `3`
* `4`
* `5`
* `6`
* `7`
* `7.1`
* `default`
* `latest`

Las cadenas especiales `default` y `latest` se resuelven en las versiones de lenguaje principal y secundaria respectivamente más recientes que haya instaladas en el equipo de compilación.

Esta configuración hace que no haya conexión entre la instalación de nuevas versiones del SDK y herramientas en el entorno de desarrollo y la decisión de incorporar nuevas características del lenguaje en un proyecto. Puede instalar el SDK y las herramientas más recientes en el equipo de compilación. Cada proyecto se puede configurar para que, durante su compilación, se use una versión de lenguaje específica.

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
