---
title: Novedades de .NET Core 3.0
description: Obtenga información sobre las características nuevas de .NET Core 3.0.
dev_langs:
- csharp
- vb
author: thraka
ms.author: adegeo
ms.date: 12/31/2018
ms.openlocfilehash: 9a43f9407d530224b5ad4775ef3a8c0ef2a9fe27
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828415"
---
# <a name="whats-new-in-net-core-30-preview-2"></a>Novedades de .NET Core 3.0 (versión preliminar 2)

En este artículo se describen las novedades de .NET Core 3.0 (versión preliminar 2). Una de las mejoras más importantes es la compatibilidad con las aplicaciones de Escritorio de Windows (solo Windows). Mediante el uso de un componente de SDK de .NET Core 3.0 denominado "Escritorio de Windows", puede trasladar sus aplicaciones de Windows Presentation Foundation (WPF) y Windows Forms. Para ser más precisos, el componente Escritorio de Windows solo se admite e incluye en Windows. Para obtener más información, vea la sección [Escritorio de Windows](#windows-desktop) de más adelante.

.NET Core 3.0 agrega compatibilidad con C# 8.0.

[Descargue .NET Core 3.0 (versión preliminar 2) y empiece a usarlo](https://aka.ms/netcore3download) ahora mismo en Windows, Mac y Linux. Puede ver los detalles completos de la versión en las [notas de la versión preliminar 2 de .NET Core 3.0](https://aka.ms/netcore3releasenotes).

Para más información sobre lo que se ha publicado con cada versión, vea los anuncios siguientes:

- [Anuncio de la versión preliminar 1 de .NET Core 3.0](https://blogs.msdn.microsoft.com/dotnet/2018/12/04/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/)
- [Anuncio de la versión preliminar 2 de .NET Core 3.0](https://blogs.msdn.microsoft.com/dotnet/2019/01/29/announcing-net-core-3-preview-2/)

## <a name="c-8"></a>C# 8

.NET Core 3.0 admite C# 8 y, a partir de .NET Core 3.0 (versión preliminar 2), admite estas nuevas características. Para obtener más información sobre las características de C# 8.0, consulte las siguientes entradas de blog:

- [Do more with patterns in C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2019/01/24/do-more-with-patterns-in-c-8-0/) (Hacer más con patrones en C# 8.0)
- [Take C# 8.0 for a spin](https://blogs.msdn.microsoft.com/dotnet/2018/12/05/take-c-8-0-for-a-spin/) (Probar C# 8.0)
- [Building C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/) (Compilación de C# 8.0)


### <a name="ranges-and-indices"></a>Rangos e índices

El nuevo tipo `Index` se puede utilizar para la indización. Puede crear uno desde un índice `int` que cuente desde el principio o con un operador `^` de prefijo (C#) que cuente desde el final:

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

También hay un tipo `Range`, que consta de dos valores `Index`, uno para el inicio y otro para el final, y se puede escribir con una expresión de rango `x..y` (C#). A continuación, puede crear un índice con un rango `Range` con el fin de generar un segmento:

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

### <a name="async-streams"></a>Flujos asincrónicos

El tipo `IAsyncEnumerable<T>` es una nueva versión asincrónica de `IEnumerable<T>`. El lenguaje permite ejecutar la instrucción `await foreach` en `IAsyncEnumerable<T>` para consumir sus elementos, y usar la instrucción `yield return` en ellos para generar los elementos.

En el ejemplo siguiente se muestra la producción y el consumo de flujos asincrónicos. La instrucción `foreach` es asincrónica y usa `yield return` para generar un flujo asincrónico para los llamadores. Este patrón (que usa `yield return`) es el modelo recomendado para generar flujos asincrónicos.

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result; 
    }
}
```

Además de poder ejecutar `await foreach`, también puede crear iteradores asincrónicos, por ejemplo, uno que devuelva un enumerador `IAsyncEnumerable/IAsyncEnumerator` en el que pueda ejecutar `await` y `yield`. Para los objetos que deban eliminarse, puede usar `IAsyncDisposable`, que implementan varios tipos BCL, como `Stream` y `Timer`.

>[!NOTE]
>Necesita .NET Core 3.0 (versión preliminar 2) para usar flujos asincrónicos si desea desarrollar con Visual Studio 2019 (versión preliminar 2) o la última versión preliminar de la [extensión de C# para Visual Studio Code](https://github.com/OmniSharp/omnisharp-vscode/releases/tag/v1.18.0-beta5). Si usa .NET Core 3.0 (versión preliminar) en la línea de comandos, todo funcionará según lo previsto.

### <a name="using-declarations"></a>Declaraciones using

Las *declaraciones using* son una nueva forma de garantizar que su objeto se elimine correctamente. Una *declaración using* mantiene activo el objeto mientras sigue en el ámbito. Una vez que el objeto deja de estar en el ámbito, se elimina automáticamente. Esto reducirá las *instrucciones using* anidadas y hará que su código esté más limpio.

```csharp
static void Main(string[] args)
{
    using var options = Parse(args);
    if (options["verbose"]) { WriteLine("Logging..."); }

} // options disposed here
```

### <a name="switch-expressions"></a>Expresiones switch

Las *expresiones switch* son una forma más limpia de hacer una *instrucción switch*, pero, al tratarse de una expresión, devuelve un valor. Las *expresiones switch* también se integran completamente con la coincidencia de patrones y usan el patrón de descarte, `_`, para representar el valor `default`.

Puede ver la sintaxis de las *expresiones switch* en el siguiente ejemplo:

```csharp
static string Display(object o) => o switch
{
    Point { X: 0, Y: 0 }         => "origin",
    Point { X: var x, Y: var y } => $"({x}, {y})",
    _                            => "unknown"
};
```

Hay dos patrones en juego en este ejemplo. `o` coincide en primer lugar con el *patrón de tipo* `Point` y, a continuación, con el *patrón de propiedad* entre *{llaves}*. `_` describe `discard pattern`, que es igual a `default` para las *instrucciones switch*.

Los patrones le permiten escribir código declarativo que captura su intención en lugar de código de procedimientos que implementa pruebas para esta. El compilador pasa a ser responsable de la implementación de ese aburrido código de procedimientos y se garantiza su correcta realización en todo momento.

Seguirá habiendo casos en los que las *instrucciones switch* sean una opción mejor que las *expresiones switch* y los patrones puedan usarse con ambos estilos de sintaxis.

Para obtener más información, consulte [Do more with patterns in C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2019/01/24/do-more-with-patterns-in-c-8-0/) (Hacer más con patrones en C# 8.0).

## <a name="ieee-floating-point-improvements"></a>Mejoras de punto flotante de IEEE

Las API de punto flotante se están actualizando para cumplir la [revisión IEEE 754-2008](https://en.wikipedia.org/wiki/IEEE_754-2008_revision). El objetivo de estos cambios es exponer todas las operaciones "obligatorias" y garantizar que cumplan de forma conductual la especificación IEEE.

Correcciones de análisis y formato:

* Analice y redondee entradas de cualquier longitud correctamente.
* Analice y formatee el cero negativo correctamente.
* Analice Infinity y NaN correctamente realizando una comprobación sin distinción entre mayúsculas y minúsculas, y permitiendo un `+` anterior opcional si procede.

Las nuevas API matemáticas tienen:

* `BitIncrement/BitDecrement`\
Corresponde a las operaciones IEEE `nextUp` y `nextDown`. Devuelven el número de punto flotante más pequeño que compara mayor o menor que la entrada (respectivamente). Por ejemplo, `Math.BitIncrement(0.0)` devolvería `double.Epsilon`.

* `MaxMagnitude/MinMagnitude`\
Corresponde a las operaciones IEEE `maxNumMag` y `minNumMag`, que devuelven el valor que es mayor o menor en magnitud de las dos entradas (respectivamente). Por ejemplo, `Math.MaxMagnitude(2.0, -3.0)` devolvería `-3.0`.

* `ILogB`\
Corresponde a la operación IEEE `logB` que devuelve un valor integral. Devuelve el registro de base 2 integral del parámetro de entrada. Es, eficazmente, igual que `floor(log2(x))`, pero se hace con un error de redondeo mínimo.

* `ScaleB`\
Corresponde a la operación IEEE `scaleB` que toma un valor integral. Devuelve eficazmente `x * pow(2, n)`, pero se hace con un error de redondeo mínimo.

* `Log2`\
Corresponde a la operación IEEE `log2`. Devuelve el logaritmo de base 2. Minimiza el error de redondeo.

* `FusedMultiplyAdd`\
Corresponde a la operación IEEE `fma`. Realiza una multiplicación y suma fusionadas. Es decir, realiza `(x * y) + z` como operación única, minimizando así el error de redondeo. Un ejemplo sería `FusedMultiplyAdd(1e308, 2.0, -1e308)`, que devuelve `1e308`. La operación `(1e308 * 2.0) - 1e308` regular devuelve `double.PositiveInfinity`.

* `CopySign`\
Corresponde a la operación IEEE `copySign`. Devuelve el valor de `x`, pero con el signo de `y`.

## <a name="net-platform-dependent-intrinsics"></a>Objetos intrínsecos dependientes de la plataforma .NET

Se han agregado API que permiten el acceso a determinadas instrucciones CPU orientadas al rendimiento, como los conjuntos de **instrucciones de manipulación de bits** o **SIMD**. Estas instrucciones pueden ayudar a lograr grandes mejoras en el rendimiento en situaciones determinadas, como el procesamiento de datos eficaz en paralelo. Además de exponer las API para que sus programas las usen, las bibliotecas de .NET han empezado a utilizar estas instrucciones para mejorar el rendimiento.

Las siguientes solicitudes de incorporación de cambios de CoreCLR muestran algunos de los objetos intrínsecos, a través de la implementación o el uso:

* [Implement simple SSE2 hardware intrinsics](https://github.com/dotnet/coreclr/pull/15585) (Implementar objetos intrínsecos de hardware SSE2 sencillos)
* [Implement the SSE hardware intrinsics](https://github.com/dotnet/coreclr/pull/15538) (Implementar los objetos intrínsecos de hardware SSE)
* [Arm64 Base HW Intrinsics](https://github.com/dotnet/coreclr/pull/16822) (Objetos intrínsecos de hardware base Arm64)
* [Use TZCNT and LZCNT for Locate{First|Last}Found{Byte|Char}](https://github.com/dotnet/coreclr/pull/21073) (Usar TZCNT y LZCNT para Locate{First|Last}Found{Byte|Char})

Para obtener más información, consulte [Objetos intrínsecos dependientes de la plataforma .NET](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md), que define un enfoque de definición de esta infraestructura de hardware, permitiendo a Microsoft, a los proveedores de chips o a cualquier otra empresa o persona definir API de chip/hardware que deben exponerse a código .NET.

## <a name="default-executables"></a>Archivos ejecutables predeterminados

.NET Core compilará ahora los [archivos ejecutables dependientes de marco de trabajo](../deploying/index.md#framework-dependent-executables-fde) de forma predeterminada. Se trata de una novedad en las aplicaciones que usan una versión de .NET Core instalada de forma global. Hasta ahora, solo las [implementaciones autocontenidas](../deploying/index.md#self-contained-deployments-scd) producirían un archivo ejecutable.

Durante `dotnet build` o `dotnet publish`, se crea un archivo ejecutable siempre que coincida con el entorno y la plataforma del SDK que usa. Estos ejecutables funcionan de la misma forma que los ejecutables nativos:

* Haga doble clic en el archivo ejecutable.
* También puede iniciar la aplicación desde un símbolo del sistema directamente, como `myapp.exe` en Windows y `./myapp` en Linux y macOS.

## <a name="build-copies-dependencies"></a>Compilación de dependencias de copias

`dotnet build` ahora copia las dependencias de NuGet de la aplicación desde la caché de NuGet en la carpeta de salida de compilación. Anteriormente, las dependencias solo se copiaban como parte de `dotnet publish`. 

Hay algunas operaciones, como la publicación de páginas Razor y la vinculación, que aún es necesario publicar.


## <a name="local-dotnet-tools"></a>Herramientas de dotnet locales

>[!WARNING]
>Se ha producido un cambio en las herramientas locales de .NET Core entre .NET Core 3.0 (versión preliminar 1) y .NET Core 3.0 (versión preliminar 2).  Si ha probado herramientas locales en la versión preliminar 1 ejecutando un comando como `dotnet tool restore` o `dotnet tool install`, debe eliminar su carpeta de la caché de las herramientas locales antes de que las herramientas locales funcionen correctamente en la versión preliminar 2. Esta carpeta se encuentra en:
>
>En Mac, Linux: `rm -r $HOME/.dotnet/toolResolverCache`
>
>En Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`
>
>Si no elimina esta carpeta, recibirá un error.

Aunque .NET Core 2.1 admitía herramientas globales, .NET Core 3.0 ahora cuenta con herramientas locales. Las herramientas locales son similares a las globales, pero están asociadas a una ubicación concreta del disco. De este modo, se pueden usar herramientas por proyecto y por repositorio. Las herramientas instaladas de forma local no están disponibles de manera global. Las herramientas se distribuyen como paquetes NuGet.

Las herramientas locales se basan en un nombre de archivo de manifiesto `dotnet-tools.json` del directorio actual. Este archivo de manifiesto define las herramientas que estarán disponibles en esa carpeta y a continuación. Al crear este archivo de manifiesto en la raíz del repositorio, asegúrese de que cualquier usuario que clone el código pueda restaurar y usar las herramientas que se necesitan para trabajar correctamente con el código.

Para crear un archivo de manifiesto `dotnet-tools.json`, use:

```console
dotnet new tool-manifest
```

Agregue una nueva herramienta al manifiesto local con:

```console
dotnet tool install <packageId>
```

También puede enumerar las herramientas en el manifiesto local con:

```console
dotnet tool list
```

Para ver qué herramientas se instalan globalmente, use:

```console
dotnet tool list -g
```

Cuando el archivo de manifiesto de herramientas locales está disponible, pero las herramientas definidas en el manifiesto no se han instalado, use el comando siguiente para descargar e instalar automáticamente estas herramientas:

```console
dotnet tool restore
```

Ejecute una herramienta local con el comando siguiente:

```console
dotnet tool run <tool-command-name>
```

Cuando se ejecuta una herramienta local, dotnet busca un manifiesto en la estructura de directorios actual. Cuando se encuentra un archivo de manifiesto de herramientas, se busca la herramienta solicitada. Si la herramienta se encuentra en el manifiesto, pero no en la caché, el usuario recibe un error y debe ejecutar `dotnet tool restore`.

Para quitar una herramienta del archivo de manifiesto de herramientas locales, ejecute el siguiente comando:

```console
dotnet tool uninstall <packageId>
```

El archivo de manifiesto de herramientas está diseñado para poder modificarse manualmente (podría hacerlo para actualizar la versión necesaria para trabajar con el repositorio). A continuación, se muestra un archivo `dotnet-tools.json` de ejemplo:

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "dotnetsay": {
      "version": "2.1.4",
      "commands": [
        "dotnetsay"
      ]
    },
    "t-rex": {
      "version": "1.0.103",
      "commands": [
        "t-rex"
      ]
    }
  }
}
```

Para las herramientas locales y globales, se requiere una versión compatible del entorno de ejecución. Actualmente, muchas herramientas de NuGet.org tienen como destino el entorno de ejecución de .NET Core 2.1. Para instalarlas de forma global o local, aún es necesario instalar el [entorno de ejecución de .NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1).

## <a name="windows-desktop"></a>Escritorio de Windows

A partir de la versión preliminar 1 de .NET Core 3.0, puede compilar aplicaciones de Escritorio de Windows con WPF y Windows Forms. Estos marcos también admiten el uso de controles modernos y los estilos de Fluent de la biblioteca de XAML de la interfaz de usuario de Windows (WinUI) a través de [islas XAML](/windows/uwp/xaml-platform/xaml-host-controls).

El componente Escritorio de Windows forma parte del SDK de Windows .NET Core 3.0.

Puede crear una aplicación de Windows Forms o WPF con los siguientes comandos `dotnet`:

```console
dotnet new wpf
dotnet new winforms
```

Visual Studio 2019 (versión preliminar 2) agrega plantillas de **nuevo proyecto** para WPF y Windows Forms de .NET Core 3.0. Los diseñadores aún no se admiten. Y puede abrir, iniciar y depurar estos proyectos en Visual Studio 2019.

Visual Studio 2017 15.9 agrega la capacidad de [habilitar versiones preliminares de .NET Core](https://blogs.msdn.microsoft.com/dotnet/2018/11/13/net-core-tooling-update-for-visual-studio-2017-version-15-9/), pero debe activar esa característica y no es un escenario admitido.

Los nuevos proyectos son los mismos que los existentes de .NET Core, con algunas adiciones. Esta es la comparación del proyecto de consola de .NET Core básico y un proyecto básico de Windows Forms y WPF.

En un proyecto de consola de .NET Core, se usa el SDK `Microsoft.NET.Sdk` y se declara una dependencia en .NET Core 3.0 a través del marco de destino `netcoreapp3.0`. Para crear una aplicación de Escritorio de Windows, use el SDK `Microsoft.NET.Sdk.WindowsDesktop` y elija qué marco de interfaz de usuario usará:

```diff
-<Project Sdk="Microsoft.NET.Sdk">
+<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
+   <UseWPF>true</UseWPF>
  </PropertyGroup>
</Project>
```

Para elegir Windows Forms en WPF, establezca `UseWindowsForms` en lugar de `UseWPF`:

```diff
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
-   <UseWPF>true</UseWPF>
+   <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>
</Project>
```

`UseWPF` y `UseWindowsForms` se puede establecer en `true` si la aplicación usa ambos marcos, por ejemplo, cuando un cuadro de diálogo de Windows Forms hospeda un control de WPF.

Comparta sus comentarios en los repositorios [dotnet/winforms](https://github.com/dotnet/winforms/issues), [dotnet/wpf](https://github.com/dotnet/wpf/issues) y [dotnet/core](https://github.com/dotnet/core/issues).

## <a name="msix-deployment-for-windows-desktop"></a>Implementación de MSIX para escritorio de Windows

[MSIX](https://docs.microsoft.com/windows/msix/) es un nuevo formato del paquete de la aplicación de Windows. Se puede usar para implementar aplicaciones de escritorio de .NET Core 3.0 en Windows 10.

El [proyecto de paquete de aplicación de Windows](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), disponible en Visual Studio 2019 (versión preliminar 2), le permite crear paquetes de MSIX con aplicaciones de .NET Core [independientes](../deploying/index.md#self-contained-deployments-scd).

>Nota: El archivo del proyecto de .NET Core debe especificar los tiempos de ejecución admitidos en la propiedad `<RuntimeIdentifiers>`:
```xml
<RuntimeIdentifiers>win-x86;win-x64</RuntimeIdentifiers>
```

## <a name="fast-built-in-json-support"></a>Compatibilidad con JSON integrada con rápido rendimiento

El ecosistema .NET depende de [**Json.NET**](https://www.newtonsoft.com/json) y otras bibliotecas populares de JSON, que siguen siendo buenas opciones. **Json.NET** utiliza cadenas .NET como su tipo de datos base, que son UTF-16 en segundo plano.

La nueva compatibilidad con JSON integrada es el alto rendimiento, una baja asignación y se basa en `Span<byte>`. Se han agregado tres nuevos tipos relacionados con JSON principales a .NET Core 3.0 y el espacio de nombres `System.Text.Json`.

### <a name="utf8jsonreader"></a>Utf8JsonReader

`System.Text.Json.Utf8JsonReader` es un lector de solo avance, de baja asignación y de alto rendimiento para texto JSON con codificación UTF-8 que se lee desde `ReadOnlySpan<byte>`. `Utf8JsonReader` es un tipo fundamental de bajo nivel que puede utilizarse para crear analizadores y deserializadores personalizados. La lectura a través de una carga JSON con el nuevo lector `Utf8JsonReader` es el doble de rápido que con el lector de **Json.NET**. No se realiza la asignación hasta que se necesite actualizar los tokens JSON como cadenas (UTF-16).

Esta nueva API incluirá los siguientes componentes:

* En la versión preliminar 1: lector JSON (acceso secuencial)
* Próximamente: escritor JSON, DOM (acceso aleatorio), y serializador y deserializador poco

Este es el bucle de lectura básico para el lector `Utf8JsonReader` que puede utilizarse como punto inicial:

```csharp
using System.Text.Json;

public static void Utf8JsonReaderLoop(ReadOnlySpan<byte> dataUtf8)
{
    var json = new Utf8JsonReader(dataUtf8, isFinalBlock: true, state: default);

    while (json.Read())
    {
        JsonTokenType tokenType = json.TokenType;
        ReadOnlySpan<byte> valueSpan = json.ValueSpan;
        switch (tokenType)
        {
            case JsonTokenType.StartObject:
            case JsonTokenType.EndObject:
                break;
            case JsonTokenType.StartArray:
            case JsonTokenType.EndArray:
                break;
            case JsonTokenType.PropertyName:
                break;
            case JsonTokenType.String:
                string valueString = json.GetStringValue();
                break;
            case JsonTokenType.Number:
                if (!json.TryGetInt32Value(out int valueInteger))
                {
                    throw new FormatException();
                }
                break;
            case JsonTokenType.True:
            case JsonTokenType.False:
                bool valueBool = json.GetBooleanValue();
                break;
            case JsonTokenType.Null:
                break;
            default:
                throw new ArgumentException();
        }
    }

    dataUtf8 = dataUtf8.Slice((int)json.BytesConsumed);
    JsonReaderState state = json.CurrentState;
}
```

### <a name="utf8jsonwriter"></a>Utf8JsonWriter

`System.Text.Json.Utf8JsonWriter` proporciona una forma de escribir texto JSON con codificación UTF-8 de alto rendimiento, sin almacenar en caché y de solo avance a partir de tipos de .NET comunes como `String`, `Int32` y `DateTime`. Al igual que el lector, el escritor es un tipo fundamental de bajo nivel que puede utilizarse para crear serializadores personalizados. Escribir una carga útil JSON con el nuevo `Utf8JsonWriter` es entre un 30 y un 80% más rápido que usar el escritor de **Json.NET** y no asigna.

A continuación se muestra un uso del ejemplo del `Utf8JsonWriter` que se puede utilizar como punto inicial:

```csharp
static int WriteJson(IBufferWriter<byte> output, long[] extraData)
{
    var json = new Utf8JsonWriter(output, state: default);

    json.WriteStartObject();

    json.WriteNumber("age", 15, escape: false);
    json.WriteString("date", DateTime.Now);
    json.WriteString("first", "John");
    json.WriteString("last", "Smith");

    json.WriteStartArray("phoneNumbers", escape: false);
    json.WriteStringValue("425-000-1212", escape: false);
    json.WriteStringValue("425-000-1213");
    json.WriteEndArray();

    json.WriteStartObject("address");
    json.WriteString("street", "1 Microsoft Way");
    json.WriteString("city", "Redmond");
    json.WriteNumber("zip", 98052);
    json.WriteEndObject();

    json.WriteStartArray("ExtraArray");
    for (var i = 0; i < extraData.Length; i++)
    {
        json.WriteNumberValue(extraData[i]);
    }
    json.WriteEndArray();

    json.WriteEndObject();

    json.Flush(isFinalBlock: true);

    return (int)json.BytesWritten;
}
```

El `Utf8JsonWriter` acepta `IBufferWriter<byte>` como la ubicación de resultados en la que se van a escribir de forma sincrónica los datos JSON y, usted, como autor de llamada, debe proporcionar una implementación concreta. La plataforma no incluye actualmente una implementación de esta interfaz. Se puede ver un ejemplo de `IBufferWriter<byte>` en [https://gist.github.com/ahsonkhan/c76a1cc4dc7107537c3fdc0079a68b35](https://gist.github.com/ahsonkhan/c76a1cc4dc7107537c3fdc0079a68b35)

### <a name="jsondocument"></a>JsonDocument

`System.Text.Json.JsonDocument` se basa en `Utf8JsonReader`. `JsonDocument` proporciona la capacidad de analizar datos JSON y crear un Document Object Model (DOM) de solo lectura que se puede consultar para admitir el acceso aleatorio y la enumeración. Se puede obtener acceso a los elementos JSON que redactan los datos a través del tipo `JsonElement` expuesto por `JsonDocument` como una propiedad llamada `RootElement`. El `JsonElement` contiene la matriz de JSON y enumeradores del objeto junto con las API para convertir texto JSON en tipos de .NET comunes. El análisis de una carga útil JSON típica y el acceso a todos sus miembros con el `JsonDocument` son de dos a tres veces más rápidos que **Json.NET** con asignaciones muy pequeñas de datos redimensionados de forma razonable (p. ej., inferiores a 1 MB).

A continuación se muestra un uso del ejemplo del `JsonDocument` y `JsonElement` que se puede utilizar como punto inicial:

```csharp
static double ParseJson()
{
    const string json = " [ { \"name\": \"John\" }, [ \"425-000-1212\", 15 ], { \"grades\": [ 90, 80, 100, 75 ] } ]";

    double average = -1;

    using (JsonDocument doc = JsonDocument.Parse(json))
    {
        JsonElement root = doc.RootElement;
        JsonElement info = root[1];

        string phoneNumber = info[0].GetString();
        int age = info[1].GetInt32();

        JsonElement grades = root[2].GetProperty("grades");

        double sum = 0;
        foreach (JsonElement grade in grades.EnumerateArray())
        {
            sum += grade.GetInt32();
        }

        int numberOfCourses = grades.GetArrayLength();
        average = sum / numberOfCourses;
    }

    return average;
}
```

## <a name="assembly-unloadability"></a>Descargabilidad de ensamblado

La descargabilidad de ensamblado es una nueva funcionalidad de `AssemblyLoadContext`. Esta nueva característica es transparente en gran medida desde una perspectiva de la API, exponiéndose con solo algunas API nuevas. Habilita un contexto de cargador que se va a descargar, liberando toda la memoria para tipos de los que se creó una instancia, campos estáticos y el propio ensamblado. Una aplicación debe poder cargar y descargar ensamblados a través de este mecanismo para siempre sin experimentar una fuga de memoria.

Esta nueva funcionalidad se puede usar para escenarios similares a:

* Escenarios de complemento donde se requiere la carga y descarga dinámica de complementos. 
* Compilación, ejecución y posterior vaciado dinámicos de código. Útil para sitios web, motores de scripting, etc.
* Carga de ensamblados para la introspección (como ReflectionOnlyLoad), aunque [MetadataLoadContext](#type-metadataloadcontext) (lanzado en la versión preliminar 1) será una mejor opción en muchos casos.

Para obtener más información, consulte el documento [Using Unloadability](https://github.com/dotnet/coreclr/pull/22221) (Uso de descargabilidad).

La descargabilidad de ensamblado requiere una atención significativa para garantizar que todas las referencias a objetos administrados desde fuera de un contexto de cargador se entiendan y administren. Al solicitarse la descarga del contexto de cargador, es necesario que no se haya hecho referencia a ninguna referencia externa para que el contexto de cargador sea coherente solo consigo mismo.

Los dominios de aplicación (AppDomains) proporcionaron la descargabilidad de ensamblado en .NET Framework. Estos no se admiten con .NET Core. AppDomains contaban tanto con ventajas como con limitaciones en comparación con este nuevo modelo. Considere la posibilidad de que este nuevo modelo de cargador sea más flexible y tenga un rendimiento más alto en comparación con AppDomains.

## <a name="windows-native-interop"></a>Interoperabilidad nativa de Windows

Windows ofrece una API nativa enriquecida con formato de API de C planas, COM y WinRT. Desde .NET Core 1.0, se ha admitido **P/Invoke**. Ahora con .NET Core 3.0, se ha agregado la compatibilidad con la capacidad de **CoCreate COM APIs** (Cocrear API de COM) y **Activate WinRT APIs** (Activar API de WinRT).

Puede ver un ejemplo de uso de COM con el [código fuente de demostración de Excel](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).


## <a name="type-sequencereader"></a>Tipo: SequenceReader

En .NET Core 3.0, se ha agregado `System.Buffers.SequenceReader`, que se puede usar como lector de `ReadOnlySequence<T>`. De este modo, se puede realizar un análisis de alto rendimiento y de asignación baja de los datos `System.IO.Pipelines` que pueden atravesar varios búferes de respaldo. 

En el ejemplo siguiente, se interrumpe una entrada `Sequence` en las líneas delimitadas `CR/LF` válidas:

```csharp
private static ReadOnlySpan<byte> CRLF => new byte[] { (byte)'\r', (byte)'\n' };

public static void ReadLines(ReadOnlySequence<byte> sequence)
{
    SequenceReader<byte> reader = new SequenceReader<byte>(sequence);

    while (!reader.End)
    {
        if (!reader.TryReadToAny(out ReadOnlySpan<byte> line, CRLF, advancePastDelimiter:false))
        {
            // Couldn't find another delimiter
            // ...
        }

        if (!reader.IsNext(CRLF, advancePast: true))
        {
            // Not a good CR/LF pair
            // ...
        }

        // line is valid, process
        ProcessLine(line);
    }
}
```

## <a name="type-metadataloadcontext"></a>Tipo: MetadataLoadContext

Se ha agregado el tipo `MetadataLoadContext` que permite leer los metadatos de ensamblado sin que afecte al dominio de aplicación del llamador. Los ensamblados se leen como datos, incluidos los ensamblados compilados para arquitecturas y plataformas distintas al entorno en tiempo de ejecución actual. `MetadataLoadContext` se superpone con <xref:System.Reflection.Assembly.ReflectionOnlyLoad*>, que solo está disponible en .NET Framework.

`MetdataLoadContext` está disponible en el paquete [System.Reflection.MetadataLoadContext](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext). Se trata de un paquete de .NET Standard 2.0.

`MetadataLoadContext`expone las API similares al tipo <xref:System.Runtime.Loader.AssemblyLoadContext>, pero no se basa en ese tipo. De forma similar a <xref:System.Runtime.Loader.AssemblyLoadContext>, `MetadataLoadContext` habilita la carga de ensamblados dentro del universo de carga de ensamblados aislados. Las API de `MetdataLoadContext` devuelven objetos <xref:System.Reflection.Assembly>, lo que permite el uso de API de reflexión conocidas. Las API orientadas a la ejecución, como [MethodBase.Invoke](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/src/System/Reflection/TypeLoading/Methods/RoMethod.cs#L127), no se permiten y generan la excepción InvalidOperationException.

El ejemplo siguiente muestra cómo buscar tipos concretos en un ensamblado que implementa una interfaz determinada:

```csharp
var paths = new string[] {@"C:\myapp\mscorlib.dll", @"C:\myapp\myapp.dll"};
var resolver = new PathAssemblyResolver(paths);
using (var lc = new MetadataLoadContext(resolver))
{
    Assembly a = lc.LoadFromAssemblyName("myapp");
    Type myInterface = a.GetType("MyApp.IPluginInterface");
    foreach (Type t in a.GetTypes())
    {
        if (t.IsClass && myInterface.IsAssignableFrom(t))
            Console.WriteLine($"Class {t.FullName} implements IPluginInterface");
    }
}
```

Los escenarios para `MetadataLoadContext` incluyen características de tiempo de diseño, herramientas de tiempo de compilación y características de alumbrado en tiempo de ejecución que necesitan inspeccionar un conjunto de ensamblados como datos y que tienen todos los bloqueos de archivo y la memoria liberada después de la inspección.

`MetadataLoadContext` tiene una clase de resolución que se transmite a su constructor. El trabajo de la resolución consiste en cargar un ensamblado `Assembly` dado su `AssemblyName`. La clase de la resolución se deriva de la clase abstracta `MetadataAssemblyResolver`. Se proporciona una implementación de la resolución para escenarios basados en rutas de acceso con `PathAssemblyResolver`.

[MetadataLoadContext pruebas](https://github.com/dotnet/corefx/tree/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests) muestra muchos casos de uso. Las [pruebas de ensamblado](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests/Assembly/AssemblyTests.cs) son un buen punto inicial.

## <a name="tls-13--openssl-111-on-linux"></a>TLS 1.3 y OpenSSL 1.1.1 en Linux

.NET Core ahora usará la [compatibilidad con TLS 1.3 en OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/) cuando esté disponible en un entorno determinado. TLS 1.3 aporta varias ventajas, según el [equipo de OpenSSL](https://www.openssl.org/blog/blog/2018/09/11/release111/):

* Mejora de los tiempos de conexión gracias a una reducción del número de recorridos de ida y vuelta necesario entre el cliente y servidor.

* Mejora de la seguridad gracias a la eliminación de varios algoritmos criptográficos obsoletos y no seguros y al mayor cifrado del protocolo de enlace de la conexión.

La versión preliminar 1 de .NET Core 3.0 puede usar **OpenSSL 1.1.1**, **OpenSSL 1.1.0** o **OpenSSL 1.0.2** (la mejor versión que se encuentre en un sistema Linux).  Cuando **OpenSSL 1.1.1** está disponible, los tipos SslStream y HttpClient usarán **TLS 1.3** al usar `SslProtocols.None` (protocolos predeterminados del sistema), dando por sentado que el cliente y el servidor admiten **TLS 1.3**.

En el siguiente ejemplo se muestra la versión preliminar 1 de .NET Core 3.0 en Ubuntu 18.10 con conexión a <https://www.cloudflare.com>:

```csharp
using System;
using System.Net.Security;
using System.Net.Sockets;
using System.Threading.Tasks;

namespace tlstest
{
    class Program
    {
        static async Task Main()
        {
            using (TcpClient tcpClient = new TcpClient())
            {
                string targetHost = "www.cloudflare.com";

                await tcpClient.ConnectAsync(targetHost, 443);

                using (SslStream sslStream = new SslStream(tcpClient.GetStream()))
                {
                    await sslStream.AuthenticateAsClientAsync(targetHost);
                    await Console.Out.WriteLineAsync($"Connected to {targetHost} with {sslStream.SslProtocol}");
                }
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/tlstest$ dotnet run
Connected to www.cloudflare.com with Tls13
user@comp-ubuntu1810:~/tlstest$ openssl version
OpenSSL 1.1.1  11 Sep 2018
```

>[!IMPORTANT]
>Windows y macOS aún no admiten **TLS 1.3**. .NET Core 3.0 será compatible con **TLS 1.3** en estos sistemas operativos cuando haya disponible soporte técnico.

## <a name="cryptography"></a>Criptografía

Se ha agregado compatibilidad con los cifrados **AES-GCM** y **AES-CCM**, que se implementan a través de `System.Security.Cryptography.AesGcm` y `System.Security.Cryptography.AesCcm`. Estos algoritmos son el [cifrado autenticado con algoritmos de datos de asociación (AEAD)](https://en.wikipedia.org/wiki/Authenticated_encryption) y los primeros algoritmos de cifrado autenticado (AE) agregados a .NET Core.

En el código siguiente se muestra cómo utilizar el cifrado **AesGcm** para cifrar y descifrar datos aleatorios.

El código de **AesCcm** sería casi idéntico (solo los nombres de variables de clase serían diferentes).

```csharp
// key should be: pre-known, derived, or transported via another channel, such as RSA encryption
byte[] key = new byte[16];
RandomNumberGenerator.Fill(key);

byte[] nonce = new byte[12];
RandomNumberGenerator.Fill(nonce);

// normally this would be your data
byte[] dataToEncrypt = new byte[1234];
byte[] associatedData = new byte[333];
RandomNumberGenerator.Fill(dataToEncrypt);
RandomNumberGenerator.Fill(associatedData);

// these will be filled during the encryption
byte[] tag = new byte[16];
byte[] ciphertext = new byte[dataToEncrypt.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Encrypt(nonce, dataToEncrypt, ciphertext, tag, associatedData);
}

// tag, nonce, ciphertext, associatedData should be sent to the other part

byte[] decryptedData = new byte[ciphertext.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Decrypt(nonce, ciphertext, tag, decryptedData, associatedData);
}

// do something with the data
// this should always print that data is the same
Console.WriteLine($"AES-GCM: Decrypted data is{(dataToEncrypt.SequenceEqual(decryptedData) ? "the same as" : "different than")} original data.");
```

## <a name="cryptographic-key-importexport"></a>Importación y exportación de claves criptográfica

La versión preliminar 1 de .NET Core 3.0 admite la importación y exportación de claves asimétricas públicas y privadas de los formatos estándar, sin necesidad de usar un certificado X.509.

Todos los tipos de clave (RSA, DSA, ECDsa y ECDiffieHellman) son compatibles con el formato **X.509 SubjectPublicKeyInfo** de las claves públicas, y con los formatos **PKCS #8 PrivateKeyInfo** y **EncryptedPrivateKeyInfo de PKCS #8**  de las claves privadas. Además, RSA admite **PKCS #1 RSAPublicKey** y **PKCS #1 RSAPrivateKey**. Todos los métodos de exportación e importación generan datos binarios con codificación DER. Si una clave se almacena en el formato PEM de texto descriptivo, el llamador debe descodificar en base64 el contenido antes de llamar a un método de importación.

```csharp
using System;
using System.IO;
using System.Security.Cryptography;

namespace rsakeyprint
{
    class Program
    {
        static void Main(string[] args)
        {
            using (RSA rsa = RSA.Create())
            {
                byte[] keyBytes = File.ReadAllBytes(args[0]);
                rsa.ImportRSAPrivateKey(keyBytes, out int bytesRead);
 
                Console.WriteLine($"Read {bytesRead} bytes, {keyBytes.Length-bytesRead} extra byte(s) in file.");
                RSAParameters rsaParameters = rsa.ExportParameters(true);
                Console.WriteLine(BitConverter.ToString(rsaParameters.D));
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/rsakeyprint$ echo Making a small key to save on screen space.
Making a small key to save on screen space.
user@comp-ubuntu1810:~/rsakeyprint$ openssl genrsa 768 | openssl rsa -outform der -out rsa.key
Generating RSA private key, 768 bit long modulus (2 primes)
..+++++++
........+++++++
e is 65537 (0x010001)
writing RSA key
user@comp-ubuntu1810:~/rsakeyprint$ dotnet run rsa.key
Read 461 bytes, 0 extra byte(s) in file.
0F-D0-82-34-F8-13-38-4A-7F-C7-52-4A-F6-93-F8-FB-6D-98-7A-6A-04-3B-BC-35-8C-7D-AC-A5-A3-6E-AD-C1-66-30-81-2C-2A-DE-DA-60-03-6A-2C-D9-76-15-7F-61-97-57-
79-E1-6E-45-62-C3-83-04-97-CB-32-EF-C5-17-5F-99-60-92-AE-B6-34-6F-30-06-03-AC-BF-15-24-43-84-EB-83-60-EF-4D-3B-BD-D9-5D-56-26-F0-51-CE-F1
user@comp-ubuntu1810:~/rsakeyprint$ openssl rsa -in rsa.key -inform der -text -noout | grep -A7 private
privateExponent:
    0f:d0:82:34:f8:13:38:4a:7f:c7:52:4a:f6:93:f8:
    fb:6d:98:7a:6a:04:3b:bc:35:8c:7d:ac:a5:a3:6e:
    ad:c1:66:30:81:2c:2a:de:da:60:03:6a:2c:d9:76:
    15:7f:61:97:57:79:e1:6e:45:62:c3:83:04:97:cb:
    32:ef:c5:17:5f:99:60:92:ae:b6:34:6f:30:06:03:
    ac:bf:15:24:43:84:eb:83:60:ef:4d:3b:bd:d9:5d:
    56:26:f0:51:ce:f1
```

Los archivos PKCS#8 pueden inspeccionarse con la clase `System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo`.

Los archivos PFX/PKCS#12 se pueden inspeccionar y manipular con `System.Security.Cryptography.Pkcs.Pkcs12Info` y `System.Security.Cryptography.Pkcs.Pkcs12Builder`, respectivamente.

## <a name="serialport-for-linux"></a>SerialPort para Linux

.NET Core 3.0 ahora admite <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> en Linux.

Anteriormente, .NET Core solo admite el uso del tipo `SerialPort` en Windows.

## <a name="more-bcl-improvements"></a>Más mejoras de BCL

`Span<T>`, `Memory<T>` y los tipos relacionados que se introdujeron en .NET Core 2.1 se han optimizado en .NET Core 3.0. Operaciones comunes, como la construcción de intervalos, la segmentación, el análisis y la aplicación de formato funcionan mejor ahora. 

Además, los tipos como `String` se han mejorado para que sean más eficaces cuando se utilizan como claves con `Dictionary<TKey, TValue>` y otras colecciones. No se requiere ningún cambio de código para aprovechar estas mejoras.

Las mejoras siguientes también son nuevas en la versión preliminar 1 de .NET Core 3:

* Compatibilidad con Brotli integrada en HttpClient
* ThreadPool.UnsafeQueueWorkItem(IThreadPoolWorkItem)
* Unsafe.Unbox
* CancellationToken.Unregister
* Operadores aritméticos complejos
* API de socket para TCP persistente
* StringBuilder.GetChunks
* Análisis de IPEndPoint
* RandomNumberGenerator.GetInt32

## <a name="tiered-compilation"></a>Compilación en niveles

La [compilación en niveles](https://blogs.msdn.microsoft.com/dotnet/2018/08/02/tiered-compilation-preview-in-net-core-2-1/) está activada de forma predeterminada con .NET Core 3.0. Se trata de una característica que permite que el entorno de ejecución use de forma más adaptable el compilador Just-In-Time (JIT) para obtener un mejor rendimiento, tanto en el inicio como al maximizar el rendimiento.

Se agregó como una característica opcional en [.NET Core 2.1](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/) y, más tarde, se habilitó de forma predeterminada en la [versión preliminar 2 de .NET Core 2.2](https://blogs.msdn.microsoft.com/dotnet/2018/09/12/announcing-net-core-2-2-preview-2/). Posteriormente, se revirtió a opcional con .NET Core 2.2.

## <a name="arm64-linux-support"></a>Compatibilidad con ARM64 para Linux

Se ha agregado compatibilidad con ARM64 para Linux. El principal caso de uso de ARM64 son escenarios de IoT.

Las [imágenes de Docker de Alpine, Debian y Ubuntu están disponibles en .NET Core para ARM64](https://hub.docker.com/r/microsoft/dotnet/).

Consulte la página sobre el [estado de ARM64 para .NET Core](https://github.com/dotnet/announcements/issues/82) si desea obtener más información.

>[!NOTE]
> Windows aún no ofrece soporte técnico para **ARM64**.

## <a name="install-net-core-30-previews-on-linux-with-snap"></a>Instalar versiones preliminares de .NET Core 3.0 en Linux con Snap

Snap es la forma preferida de instalar y probar versiones preliminares de .NET Core en [distribuciones de Linux que admiten Snap](https://docs.snapcraft.io/installing-snapd/6735).

Después de configurar Snap en su sistema, ejecute el comando siguiente para instalar el [SDK de versión preliminar de .NET Core 3.0](https://snapcraft.io/dotnet-sdk).

```console
sudo snap install dotnet-sdk --beta --classic
```
 
Cuando se instale .NET Core con el paquete Snap, el comando de .NET Core predeterminado será `dotnet-sdk.dotnet`, en lugar de solo `dotnet`. La ventaja del comando con espacio de nombres es que no entrará en conflicto con una versión de .NET Core instalada globalmente que pueda tener. A este comando se le puede llamar `dotnet` con:

```console
sudo snap alias dotnet-sdk.dotnet dotnet
```

Algunas distribuciones requieren un paso adicional para habilitar acceso al certificado SSL. Consulte nuestra [Instalación de Linux](https://github.com/dotnet/core/blob/master/Documentation/linux-setup.md) para obtener detalles.

## <a name="gpio-support-for-raspberry-pi"></a>Compatibilidad de GPIO con Raspberry Pi

Se han publicado en NuGet dos nuevos paquetes que puede usar para la programación GPIO.

* [System.Device.Gpio](https://www.nuget.org/packages/System.Device.Gpio/0.1.0-prerelease.19078.2)
* [Iot.Device.Bindings](https://www.nuget.org/packages/Iot.Device.Bindings/0.1.0-prerelease.19078.2)

Los paquetes GPIO incluyen API para dispositivos GPIO, SPI, I2C y PWM. El paquete de enlaces de IoT incluye [enlaces de dispositivo](https://github.com/dotnet/iot/blob/master/src/devices/README.md) para diversos chips y sensores, los mismos disponibles en [dotnet/iot - src/devices](https://github.com/dotnet/iot/tree/master/src/devices).

Las API de puerto serie actualizadas que se anunciaron como parte de .NET Core 3.0 (versión preliminar 1) no forman parte de estos paquetes, pero están disponibles como parte de la plataforma .NET Core.


## <a name="platform-support"></a>Compatibilidad de la plataforma

Los siguientes sistemas operativos admitirán .NET Core 3:

* Cliente de Windows: 7, 8.1, 10 (1607+)
* Windows Server: 20012 R2 SP1+
* macOS: 10.12+
* RHEL: 6+
* Fedora: 26+
* Ubuntu: 16.04+
* Debian: 9+
* SLES: 12+
* openSUSE: 42.3+
* Alpine: 3.8+

La compatibilidad con el chip sigue:

* x64 en Windows, macOS y Linux
* x86 en Windows
* ARM32 en Windows y Linux
* ARM64 en Linux

En Linux, ARM32 se admite en Debian 9+ y Ubuntu 16.04+. En ARM64, es igual que ARM32 con la adición de Alpine 3.8. Estas son las mismas versiones de esas distribuciones tal cual compatibles con X64.

Las imágenes de Docker para .NET Core 3.0 están disponibles en [microsoft/dotnet en Docker Hub](https://hub.docker.com/r/microsoft/dotnet/). Microsoft se encuentra actualmente en proceso de adopción de [Registro de contenedor de Microsoft (MCR)](https://cloudblogs.microsoft.com/opensource/2019/01/17/improved-discovery-experience-microsoft-containers-docker-hub/) y se espera que las imágenes de .NET Core 3.0 finales se publiquen solo en MCR.
