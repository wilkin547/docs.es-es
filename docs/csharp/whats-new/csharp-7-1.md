---
title: Novedades de C# 7.1
description: "Información general sobre las nuevas características de C# 7.1."
keywords: "Diseño del lenguaje C#, 7.1, Visual Studio 2017"
author: billwagner
ms.author: wiwagn
ms.date: 08/16/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: 02f1f8fc8f0a3221e00e2a3c43ce06423ca43672
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="whats-new-in-c-71"></a>Novedades de C# 7.1

7.1 de C# es la primera versión de punto para el lenguaje C#. Marca una cadencia de versión mayor para el idioma. Puede utilizar las nuevas características más pronto, lo ideal es que cuando esté listo cada nueva característica. C# 7.1 incorpora la posibilidad de configurar el compilador para que coincida con una versión especificada del idioma. Que permite separar la decisión de herramientas de actualización de la decisión de la actualización de versiones de idioma.

7.1 de C# agrega los [selección de la versión de idioma](#language-version-selection) elemento de configuración, tres nuevas características del lenguaje y comportamiento del compilador nuevo.

Las nuevas características de lenguaje en esta versión son:

* [`async``Main` (método)](#async-main)
  - El punto de entrada para una aplicación puede tener la `async` modificador.
* [`default`expresiones literales](#default-literal-expressions)
  - Puede usar expresiones literales de forma predeterminada en las expresiones de valor predeterminado cuando se puede inferir el tipo de destino.
* [Nombres de elementos de tupla deducido](#inferred-tuple-element-names)
  - Los nombres de elementos de tupla pueden deducirse de la inicialización de la tupla en muchos casos.

Por último, el compilador tiene dos opciones `/refout` y `/refonly` ese control [hacen referencia a generación del ensamblado](#reference-assembly-generation).

## <a name="language-version-selection"></a>Selección de la versión de idioma

El compilador de C# admite 7.1 de C# a partir de Visual Studio 2017 versión 15.3 o .NET Core SDK 2.0. Sin embargo, las 7.1 características están desactivadas de forma predeterminada. Para habilitar las 7.1 características, debe cambiar la configuración de la versión de idioma para el proyecto.

En Visual Studio, haga doble clic en el nodo del proyecto en el Explorador de soluciones y seleccione **propiedades**. Seleccione el **generar** pestaña y seleccione la **avanzadas** botón. En la lista desplegable, seleccione **C# versión secundaria más reciente (más reciente)**, o una versión específica **C# 7.1** tal y como se muestra en la siguiente imagen. El `latest` valor significa que va a utilizar la versión secundaria más reciente en la máquina actual. La `C# 7.1` significa que desea usar C# 7.1, incluso después de que se liberan las versiones secundarias más recientes.

![Configuración de la versión de idioma](./media/csharp-7-1/advanced-build-settings.png)

Como alternativa, puede editar el archivo "csproj" y agregar o modificar las siguientes líneas:

```xml
<PropertyGroup>
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

> [!NOTE]
> Si usa el IDE de Visual Studio para actualizar los archivos csproj, el IDE crea nodos independientes para cada configuración de compilación. Podrá normalmente establece el valor igual en todas las configuraciones de compilación, pero debe establecer de forma explícita para cada configuración de compilación, o seleccione "Todas las configuraciones" cuando se modifica este valor. Verá lo siguiente en el archivo csproj:

```xml
<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>

<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

Valores válidos para el `LangVersion` elemento son:

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

Las cadenas especiales `default` y `latest` resolver en las últimas versiones de idioma principal y secundaria instaladas en el equipo de compilación, respectivamente.

Esta configuración desacopla instalar nuevas versiones del SDK y herramientas en el entorno de desarrollo de la elección de incorporar nuevas características del lenguaje en un proyecto. Puede instalar el SDK y herramientas más recientes en el equipo de compilación. Cada proyecto puede configurarse para usar una versión específica del idioma para su compilación.

## <a name="async-main"></a>Async principal

Un *async principal* método le permite usar `await` en su `Main` método.
Anteriormente tendría que escribir:

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

Ahora puede escribir:

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

Si el programa no devuelve un código de salida, puede declarar un `Main` método que devuelve un <xref:System.Threading.Tasks.Task>:

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

Puede leer más acerca de los detalles en el [async principal](../programming-guide/main-and-command-args/index.md) tema en la Guía de programación.

## <a name="default-literal-expressions"></a>Expresiones literales de forma predeterminada

Expresiones literales predeterminados constituyen una mejora en expresiones de valor predeterminado.
Estas expresiones inicializan una variable en el valor predeterminado. Donde anteriormente habría que escribir:

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

Ahora se puede omitir el tipo en el lado derecho de la inicialización:

```csharp
Func<string, bool> whereClause = default;
```

Se puede obtener más información acerca de esta mejora en el tema de la Guía de programación de C# en [predeterminado expresiones de valor](../programming-guide/statements-expressions-operators/default-value-expressions.md).

Esta mejora también cambia algunas de las reglas de análisis de la [palabra clave predeterminada](../language-reference/keywords/default.md).

## <a name="inferred-tuple-element-names"></a>Nombres de elementos de tupla deducido

Esta característica es una pequeña mejora la característica de tuplas que se introdujo en C# 7.0. Muchas veces cuando se inicializa una tupla, las variables utilizadas para el lado derecho de la asignación son los mismos que los nombres que desea para los elementos de tupla:

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

Los nombres de elementos de tupla se pueden inferir a partir de las variables que se utiliza para inicializar la tupla en C# 7.1:

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

Puede aprender más acerca de esta característica en el [tuplas](../tuples.md) tema.

## <a name="reference-assembly-generation"></a>Generación del ensamblado de referencia

Hay dos nuevas opciones de compilador que generen *ensamblados de referencia*: [/refout](../language-reference/compiler-options/refout-compiler-option.md) y [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).
Los temas vinculados explican estas opciones y los ensamblados de referencia con más detalle.
