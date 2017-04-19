---
title: Desarrollo de bibliotecas con herramientas multiplataforma
description: Desarrollo de bibliotecas con herramientas multiplataforma
keywords: .NET, .NET Core
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 9f6e8679-bd7e-4317-b3f9-7255a260d9cf
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 94b6d965c7a39a02723b641f6551e54dd4df1f07
ms.lasthandoff: 03/07/2017

---

# <a name="developing-libraries-with-cross-platform-tools"></a>Desarrollo de bibliotecas con herramientas multiplataforma

> [!WARNING]
> Este tema todavía no se ha actualizado a la última versión de las herramientas.

En este artículo se explica cómo escribir bibliotecas para .NET mediante el uso de herramientas multiplataforma de la CLI.  La CLI proporciona una experiencia eficaz y de bajo nivel que funciona en todos los SO compatibles.  De todos modos puede seguir compilando bibliotecas con Visual Studio; si esa es la experiencia de su preferencia, [consulte la guía sobre Visual Studio](libraries-with-vs.md).

## <a name="prerequisites"></a>Requisitos previos

Necesita [la CLI y el SDK de .NET Core](https://www.microsoft.com/net/core) que están instalados en la máquina.

En las secciones de este documento que se refieren a las versiones de .NET Framework o Bibliotecas de clases portables (PCL), necesita tener instalado [.NET Framework](http://getdotnet.azurewebsites.net/) en una máquina con Windows.  

Además, si desea admitir destinos de .NET Framework anteriores, deberá instalar paquetes de compatibilidad/desarrollador para versiones anteriores del marco de trabajo que se encuentran en la [página de plataformas de destino .NET](http://getdotnet.azurewebsites.net/target-dotnet-platforms.html).  Consulte la tabla siguiente:

| Versión de .NET Framework | Qué debe descargar |
| ---------------------- | ----------------- |
| 4.6.1 | Paquete de compatibilidad de .NET Framework 4.6.1 |
| 4.6 | Paquete de compatibilidad de .NET Framework 4.6 |
| 4.5.2 | Paquete de desarrollador de .NET Framework 4.5.2 |
| 4.5.1 | Paquete de desarrollador de .NET Framework 4.5.1 |
| 4.5 | Kit de desarrollo de software de Windows para Windows 8 |
| 4.0 | Windows SDK para Windows 7 y .NET Framework 4 |
| 2.0, 3.0 y 3.5 | Entorno de ejecución de .NET Framework 3.5 SP1 (o una versión posterior a Windows 8) |

## <a name="how-to-target-the-net-standard"></a>Estándar .NET como destino

Si no conoce bien el estándar .NET, consulte la [Biblioteca estándar de .NET](../../standard/library.md) para más información.

En ese artículo podrá ver una tabla que asigna las versiones del estándar .NET a diversas implementaciones:

| Nombre de la plataforma | Alias |  |  |  |  |  | | |
| :---------- | :--------- |:--------- |:--------- |:--------- |:--------- |:--------- |:--------- |:--------- |
|Estándar .NET | netstandard | 1.0 | 1.1 | 1.2 | 1.3 | 1.4 | 1.5 | 1.6 |
|Núcleo de .NET|netcoreapp|&rarr;|&rarr;|&rarr;|&rarr;|&rarr;|&rarr;|1.0|
|.NET Framework|net|&rarr;|4.5|4.5.1|4.6|4.6.1|4.6.2|4.6.3|
|Plataformas Mono/Xamarin||&rarr;|&rarr;|&rarr;|&rarr;|&rarr;|&rarr;|*|
|Plataforma universal de Windows|uap|&rarr;|&rarr;|&rarr;|&rarr;|10.0|||
|Windows|win|&rarr;|8.0|8.1|||||
|Windows Phone|wpa|&rarr;|&rarr;|8.1|||||
|Windows Phone Silverlight|wp|8.0|||||||

Este es el significado de la tabla para crear una biblioteca:

La versión del estándar de la plataforma .NET que elija será un equilibrio entre el acceso a las API más recientes y la capacidad de apuntar a más plataformas .NET y más versiones de Framework.  Puede controlar el intervalo de versiones y plataformas de destino si elige una versión de `netstandardX.X` (donde `X.X` es un número de versión) y la agrega al archivo `project.json`.

Además, el correspondiente [paquete NuGet del que se depende](https://www.nuget.org/packages/NETStandard.Library/) es `NETStandard.Library` versión `1.6.0`.  A pesar de que nada evita que dependa de `Microsoft.NETCore.App` como ocurre con las aplicaciones de consola, en general no se recomienda.  Si necesita API de un paquete que no está especificado en `NETStandard.Library`, siempre puede especificar ese paquete además de `NETStandard.Library` en la sección `dependencies` del archivo `project.json`.

En función de sus necesidades, tiene 3 opciones principales cuando el destino es el estándar .NET.

1. Puede usar la versión más reciente del estándar .NET, `netstandard1.6`, que es cuando desea acceso a la mayoría de las API y no importa si tiene menos alcance entre las implementaciones.
2. Puede usar una versión inferior del estándar .NET para tener como destino las implementaciones .NET anteriores. El costo aquí es que no tiene acceso a algunas de las API más recientes.
    
    Por ejemplo, si quisiera tener una compatibilidad garantizada con .NET Framework 4.6 y superior, debería elegir `netstandard1.3`:

    ```json
    {
        "dependencies":{
            "NETStandard.Library":"1.6.0"
        },
        "frameworks":{
            "netstandard1.3":{}
        }
    }
    ```
    
    Las versiones del estándar .NET son compatibles con versiones anteriores. Eso significa que las bibliotecas `netstandard1.0` se pueden ejecutar en plataformas `netstandard1.1` y versiones superiores.  Sin embargo, no existe compatibilidad con versiones posteriores: las plataformas del estándar .NET inferiores no pueden hacer referencia a las superiores.  Esto significa que las bibliotecas `netstandard1.0` no pueden hacer referencia a las bibliotecas que tienen como destino `netstandard1.1` o una versión superior.  Seleccione la versión estándar que tiene la combinación adecuada de compatibilidad con API y plataformas que necesita.
    
3. Si desea tener como destino .NET Framework versión 4.0 o inferior, o bien desea usar una API disponible en .NET Framework pero no disponible en el estándar .NET (por ejemplo, `System.Drawing`), lea las secciones siguientes y sepa cómo tener compatibilidad con múltiples versiones.

## <a name="how-to-target-the-net-framework"></a>.NET Framework como destino

> [!NOTE]
> Estas instrucciones suponen que tiene instalado .NET Framework en su máquina.  Consulte los [requisitos previos](#prerequisites) para instalar las dependencias.

Tenga en cuenta que algunas de las versiones de .NET Framework que se usan aquí ya no cuentan con soporte técnico.  Consulte las [P+F sobre la directiva del ciclo de vida de soporte técnico de .NET Framework](https://support.microsoft.com/gp/framework_faq/en-us) sobre las versiones sin soporte técnico.

Si desea llegar a la mayor cantidad posible de desarrolladores y proyectos, use .NET Framework 4 como el destino de base de referencia. Para tener .NET Framework como destino, deberá comenzar por el uso del moniker de la plataforma de destino (TFM) correcto que corresponda a la versión de .NET Framework que desea admitir.

```
.NET Framework 2.0   --> net20
.NET Framework 3.0   --> net30
.NET Framework 3.5   --> net35
.NET Framework 4.0   --> net40
.NET Framework 4.5   --> net45
.NET Framework 4.5.1 --> net451
.NET Framework 4.5.2 --> net452
.NET Framework 4.6   --> net46
.NET Framework 4.6.1 --> net461
.NET Framework 4.6.2 --> net462
.NET Framework 4.6.3 --> net463
```

El siguiente es un ejemplo de cómo podría escribir una biblioteca que tenga como destino la versión .NET Framework 4:

```json
{
    "frameworks":{
        "net40":{}
    }
}
```

Y listo.  Aunque esto solo hace la compilación para .NET Framework 4, puede usar la biblioteca en las versiones más recientes de .NET Framework.

## <a name="how-to-target-a-portable-class-library-pcl"></a>Biblioteca de clases portable (PCL) como destino

> [!NOTE]
> Estas instrucciones suponen que tiene instalado .NET Framework en su máquina.  Consulte los [requisitos previos](#prerequisites) para instalar las dependencias.

Tener como destino un perfil de PCL es un poco más complicado que tener como destino el estándar .NET o .NET Framework.  Para comenzar, [haga referencia a esta lista de perfiles de PCL](http://embed.plnkr.co/03ck2dCtnJogBKHJ9EjY/preview) para encontrar el destino NuGet que corresponda al perfil de PCL al que apunta.

Luego, deberá hacer lo siguiente:

1. Cree una entrada nueva en `frameworks` en el `project.json`, con el nombre `.NETPortable,Version=v{version},Profile=Profile{profile}`, donde `{version}` y `{profile}` correspondan, respectivamente, a un número de versión de PCL y un número de perfil.
2. En esta entrada nueva, muestre cada ensamblado que se usa para ese destino en una entrada `frameworkAssemblies`.  Esto incluye `mscorlib`, `System` y `System.Core`.
3. Si usa la compatibilidad con múltiples versiones (consulte la sección siguiente), debe mostrar explícitamente las dependencias de cada destino en sus entradas de destino.  Ya no podrá usar una entrada `dependencies` global.

El siguiente ejemplo tiene como destino el perfil 328 de PCL. El perfil 328 admite: estándar .NET 1.4, .NET Framework 4, Windows 8, Windows Phone 8.1, Windows Phone Silverlight 8.1 y Silverlight 5.

```json
{
    "frameworks":{
        ".NETPortable,Version=v4.0,Profile=Profile328":{
            "frameworkAssemblies":{
                "mscorlib":"",
                "System":"",
                "System.Core":""
            }
        }
    }
}
```

Cuando compila un proyecto que incluye el perfil 328 de PCL como un marco de trabajo en el archivo *project.json*, se tendrá esta subcarpeta en la carpeta */bin/debug*:

```
portable-net40+sl50+netcore45+wpa81+wp8/
```

Esta carpeta incluye los archivos `.dll` que son necesarios para ejecutar la biblioteca.

## <a name="how-to-multitarget"></a>Cómo lograr la compatibilidad con múltiples versiones

> [!NOTE]
> Las instrucciones siguientes suponen que tiene instalado .NET Framework en su máquina.  Consulte la sección de [requisitos previos](#prerequisites) para información sobre las dependencias que debe instalar y dónde descargarlas.

Es posible que deba tener como destino versiones anteriores de .NET Framework cuando el proyecto admite .NET Framework y .NET Core. En este escenario, si desea usar API más recientes y construcciones de lenguaje para los destinos más recientes, use las directivas `#if` en el código. También es posible que tenga que agregar distintos paquetes y dependencias en el `project.json file` para cada plataforma que tiene como destino para incluir las distintas API necesarias para cada caso.

Por ejemplo, digamos que tiene una biblioteca que realiza operaciones de red a través de HTTP. En el estándar .NET y .NET Framework versión 4.5 o superiores, puede usar la clase `HttpClient` del espacio de nombres `System.Net.Http`. Sin embargo, las versiones anteriores de .NET Framework no tienen la clase `HttpClient`, por lo que, en su lugar, podría usar la clase `WebClient` del espacio de nombres `System.Net` para esas versiones.

Por lo tanto, el archivo `project.json` podría tener la siguiente apariencia:

```json
{
    "frameworks":{
        "net40":{
            "frameworkAssemblies": {
                "System.Net":"",
                "System.Text.RegularExpressions":""
            }
        },
        "net452":{
            "frameworkAssemblies":{
                "System.Net":"",
                "System.Net.Http":"",
                "System.Text.RegularExpressions":"",
                "System.Threading.Tasks":""
            }
        },
        "netstandard1.6":{
            "dependencies": {
                "NETStandard.Library":"1.6.0",
            }
        }
    }
}
```

Tenga en cuenta que se debe hacer una referencia explícita a los ensamblados de .NET Framework en los destinos `net40` y `net452`; además, las referencias de NuGet también aparecen explícitamente en el destino `netstandard1.6`.  Esto es necesario en los escenarios de compatibilidad con múltiples versiones.

Luego, las instrucciones `using` del archivo de origen se pueden ajustar de la manera siguiente:

```csharp
#if NET40
// This only compiles for the .NET Framework 4 targets
using System.Net;
#else
// This compiles for all other targets
using System.Net.Http;
using System.Threading.Tasks;
#endif
```

El sistema de compilación conoce los siguientes símbolos del preprocesador que se usan en las directivas `#if`:

```
.NET Framework 2.0   --> NET20
.NET Framework 3.5   --> NET35
.NET Framework 4.0   --> NET40
.NET Framework 4.5   --> NET45
.NET Framework 4.5.1 --> NET451
.NET Framework 4.5.2 --> NET452
.NET Framework 4.6   --> NET46
.NET Framework 4.6.1 --> NET461
.NET Framework 4.6.2 --> NET462
.NET Standard 1.0    --> NETSTANDARD1_0
.NET Standard 1.1    --> NETSTANDARD1_1
.NET Standard 1.2    --> NETSTANDARD1_2
.NET Standard 1.3    --> NETSTANDARD1_3
.NET Standard 1.4    --> NETSTANDARD1_4
.NET Standard 1.5    --> NETSTANDARD1_5
.NET Standard 1.6    --> NETSTANDARD1_6
```

En la mitad del origen, puede usar directivas `#if` para usar esas bibliotecas de manera condicional. Por ejemplo:

```csharp
    public class Library
    {
#if NET40
        private readonly WebClient _client = new WebClient();
        private readonly object _locker = new object();
#else
        private readonly HttpClient _client = new HttpClient();
#endif

#if NET40
        // .NET Framework 4.0 does not have async/await
        public string GetDotNetCount()
        {
            string url = "http://www.dotnetfoundation.org/";
          
            var uri = new Uri(url);
            
            string result = "";
            
            // Lock here to provide thread-safety.
            lock(_locker)
            {
                result = _client.DownloadString(uri);
            }
            
            int dotNetCount = Regex.Matches(result, ".NET").Count;
            
            return $"Dotnet Foundation mentions .NET {dotNetCount} times!";
        }
#else
        // .NET 4.5+ can use async/await!
        public async Task<string> GetDotNetCountAsync()
        {
            string url = "http://www.dotnetfoundation.org/";
            
            // HttpClient is thread-safe, so no need to explicitly lock here
            var result = await _client.GetStringAsync(url);
            
            int dotNetCount = Regex.Matches(result, ".NET").Count;
            
            return $"dotnetfoundation.orgmentions .NET {dotNetCount} times in its HTML!";
        }
#endif
    }
```

Cuando compila un proyecto que incluye `net40`, `net45` y `netstandard1.6` como marcos de trabajo en el archivo *project.json* , se tendrán estas subcarpetas en la carpeta */bin/debug*:

```
net40/
net45/
netstandard1.6/
```

### <a name="but-what-about-multitargeting-with-portable-class-libraries"></a>¿Qué pasa, entonces, con la compatibilidad con múltiples versiones con las Bibliotecas de clases portables?

Si desea realizar una compilación cruzada con un destino de PCL, debe agregar una definición de compilación en el archivo `project.json` en `buildOptions` del destino de PCL.  Luego, puede usar directivas `#if` en el origen, las que usan la definición de compilación como símbolo de preprocesador.

Por ejemplo, si desea tener como destino el [perfil 328 de PCL](http://embed.plnkr.co/03ck2dCtnJogBKHJ9EjY/preview) (.NET Framework 4, Windows 8, Windows Phone Silverlight 8, Windows Phone 8.1, Silverlight 5), podría hacer referencia a él como "PORTABLE328" cuando se realice la compilación cruzada.  Simplemente agréguelo al archivo `project.json` como un atributo `buildOptions`:

```json
{
    "frameworks":{
        "netstandard1.6":{
           "dependencies":{
                "NETStandard.Library":"1.6.0",
            }
        },
        ".NETPortable,Version=v4.0,Profile=Profile328":{
            "buildOptions": {
                "define": [ "PORTABLE328" ]
            },
            "frameworkAssemblies":{
                "mscorlib":"",
                "System":"",
                "System.Core":"",
                "System.Net"
            }
        }
    }
}

```

Ahora puede realizar una compilación condicional con respecto a ese destino:

```csharp
#if !PORTABLE328
using System.Net.Http;
using System.Threading.Tasks;
// Potentially other namespaces which aren't compatible with Profile 328
#endif
```

Debido a que el compilador ahora reconoce `PORTABLE328`, la biblioteca del perfil 328 de PCL que un compilador generó no incluirá `System.Net.Http` ni `System.Threading.Tasks`.

Cuando compila un proyecto que incluye el perfil 328 de PCL y `netstandard1.6` como marcos de trabajo en el archivo *project.json*, se tendrán estas subcarpetas en la carpeta */bin/debug*:

```
portable-net40+sl50+netcore45+wpa81+wp8/
netstandard1.6/
```

## <a name="how-to-use-native-dependencies"></a>Uso de dependencias nativas

Es posible que desee escribir una biblioteca que dependa de un archivo `.dll` nativo.  Tiene dos opciones si escribe una biblioteca de ese estilo:

1. Haga referencia al `.dll` nativo directamente en su `project.json`.
2. Empaquete ese `.dll` en su propio paquete NuGet y dependa de ese paquete.

En la primera opción, deberá incluir las siguientes acciones en el archivo `project.json`:

1. Establecer `allowUnsafe` en `true` en una sección `buildOptions`.
2. Especificar un [identificador de entorno de ejecución (RID)](../rid-catalog.md) en una sección `runtimes`.
3. Especificar la ruta de acceso a los archivos `.dll` nativos a los que hace referencia.

Este es un `project.json` de ejemplo de un archivo `.dll` nativo en el directorio raíz del proyecto que se ejecuta en Windows:

```json
{
    "buildOptions":{
        "allowUnsafe":true
    },
    "runtimes":{
        "win10-x64":{}
    },
    "packOptions":{
        "files":{
            "mappings":{
                "runtimes/win10-x64/native":{
                    "includeFiles":[ "native-lib.dll"]
                }
            }            
        }
    }
}
```

Si distribuye la biblioteca como paquete, se recomienda que coloque el archivo `.dll` en el nivel raíz del proyecto.

En la segunda opción, deberá compilar un paquete NuGet a partir de los archivos `.dll`, hospédelo en una fuente NuGet o MyGet y dependa directamente de él.  De todos modos deberá establecer `allowUnsafe` en `true` en la sección `buildOptions` de `project.json`.  A continuación puede ver un ejemplo (suponiendo que `MyNativeLib` es un paquete NuGet en la versión `1.2.0`):

```json
{
    "buildOptions":{
        "allowUnsafe":true
    },
    "dependencies":{
        "MyNativeLib":"1.2.0"
    }
}
```

Si desea ver un ejemplo de cómo empaquetar archivos binarios nativos entre plataformas, revise [ASP.NET Libuv Package](https://github.com/aspnet/libuv-package) y la [referencia correspondiente en KestrelHttpServer](https://github.com/aspnet/KestrelHttpServer/blob/1.0.0/src/Microsoft.AspNetCore.Server.Kestrel/project.json#L19).

## <a name="how-to-test-libraries-on-net-core"></a>Prueba de las bibliotecas en .NET Core

Es importante poder probar las plataformas.  Resulta más sencillo usar [xUnit](http://xunit.github.io/), que también es la herramienta de prueba que usan los proyectos .NET Core.  Cómo configurar la solución con proyectos de prueba dependerá de la [estructura de la solución](#structuring-a-solution).  En el ejemplo siguiente se presume que todos los proyectos de origen se encuentran bajo una carpeta `/src` de nivel superior y todos los proyectos de prueba se encuentran bajo una carpeta `/test` de nivel superior.

1. Asegúrese de tener un archivo `global.json` en el nivel de la solución que comprenda dónde están los proyectos de prueba:
    
    ```json
    {
        "projects":[ "src", "test"]
    }
    ```
    
    La estructura de carpetas de la solución se tendrá un aspecto similar al siguiente:
    
    ```
    /SolutionWithSrcAndTest
    |__global.json
    |__/src
    |__/test
    ```
    
2. Cree un proyecto de prueba nuevo mediante la creación de una carpeta de proyecto en la carpeta `/test` y un archivo `project.json` en la carpeta del proyecto nuevo.  Para crear el archivo `project.json`, puede ejecutar el comando `dotnet new` y, luego, modificar el archivo `project.json`.  El archivo debe incluir lo siguiente:

   * `netcoreapp1.0`como la única entrada en `frameworks`.
   * Una referencia a `Microsoft.NETCore.App` versión `1.0.0`.
   * Una referencia a xUnit versión `2.2.0-beta2-build3300`.
   * `dotnet-test-xunit`Una referencia a `2.2.0-preview2-build1029` versión
   * Una referencia de proyecto a la biblioteca que se prueba.
   * La entrada `"testRunner":"xunit"`.
   
   A continuación puede ver un ejemplo (`LibraryUnderTest` versión `1.0.0` es la biblioteca que se prueba):
   
   ```json
   {
        "testRunner":"xunit",
        "dependencies":{
            "LibraryUnderTest":{
                "version":"1.0.0",
                "target":"project"
            },
            "Microsoft.NETCore.App":{
                "version":"1.0.0",
                "type":"platform"
            },
            "xunit":"2.2.0-beta2-build3300",
            "dotnet-test-xunit":"2.2.0-preview2-build1029",
        },
        "frameworks":{
            "netcoreapp1.0":{}
        }
   }
   ```
3. Ejecute `dotnet restore` para restaurar los paquetes.  Si todavía no restauró los paquetes, debe hacerlo en el nivel de la solución.

4. Vaya al proyecto de prueba y ejecute las pruebas con `dotnet test`:

    ```
    $ cd path-to-your-test-project
    $ dotnet test
    ```

Y listo.  Ahora puede probar la biblioteca en todas las plataformas; para ello, use herramientas de línea de comandos.  Para seguir con las pruebas ahora que ya está todo configurado, probar la biblioteca es un proceso muy simple:

1. Haga los cambios en la biblioteca.
2. Ejecute las pruebas desde la línea de comandos, en el directorio de prueba, con el comando `dotnet test`.

El código se recompilará automáticamente cuando invoque el comando `dotnet test`.

Solo debe recordar ejecutar `dotnet restore` desde la línea de comandos cada vez que agregue una dependencia nueva y estará listo para continuar.

## <a name="how-to-use-multiple-projects"></a>Uso de varios proyectos

Una necesidad en común de las bibliotecas de mayor tamaño es ubicar la funcionalidad en distintos proyectos.

Imagine que desea compilar una biblioteca que se pudiera consumir en C# y F# idiomático.  Eso significaría que los usuarios de las bibliotecas las consumirían de manera natural para C# o F#.  Por ejemplo, en C#, podría consumir la biblioteca de la siguiente manera:

```csharp
var convertResult = await AwesomeLibrary.ConvertAsync(data);
var result = AwesomeLibrary.Process(convertResult);
```  

En F#, sería de la siguiente manera:

```fsharp
let result =
    data
    |> AwesomeLibrary.convertAsync 
    |> Async.RunSynchronously 
    |> AwesomeLibrary.process
```

Escenarios de consumo similares a este significan que las API a las que se tiene acceso deben tener una estructura distinta para C# y para F#.  Un enfoque común para lograrlo es factorizar toda la lógica de una biblioteca en un proyecto central, con los proyectos de C# y F# definiendo los niveles de API que hacen llamadas a ese proyecto central.  En el resto de la sección se usarán los siguientes nombres:

* **AwesomeLibrary.Core**: un proyecto central que contiene toda la lógica de la biblioteca.
* **AwesomeLibrary.CSharp**: un proyecto con API públicas pensado para el consumo en C.#
* **AwesomeLibrary.FSharp**: un proyecto con API públicas pensado para el consumo en F.#

### <a name="project-to-project-referencing"></a>Referencias entre proyectos

La mejor forma de hacer referencia a un proyecto es la siguiente:

1. Asegúrese de que el proyecto al que desea hacer referencia tiene un buen nombre para su carpeta contenedora en el disco.  Se usará este nombre para hacer referencia al proyecto.
2. Haga referencia al nombre de (1) en el archivo `project.json` del proyecto usado y especifique `"target":"project"`.

Los archivos `project.json` para **AwesomeLibrary.CSharp** y **AwesomeLibrary.FSharp** ahora deben hacer referencia a **AwesomeLibrary.Core** como un destino `project`.  Si no usa la compatibilidad con múltiples versiones, puede usar la entrada `dependencies` global:

```json
{
    "dependencies":{
        "AwesomeLibrary.Core":{
            "target":"project"
        }
    }
}
```

Si usa la compatibilidad con múltiples versiones, es posible que no pueda usar una entrada `dependencies` global y puede que deba hacer referencia a **AwesomeLibrary.Core** en una entrada `dependencies` a nivel de destino.  Por ejemplo, si tuviese a `netstandard1.6` como destino, podría hacerlo de la siguiente manera:

```json
{
    "frameworks":{
        "netstandard1.6":{
            "dependencies":{
                "AwesomeLibrary.Core":{
                    "target":"project"
                }
            }
        }
    }
}
```

### <a name="structuring-a-solution"></a>Estructura de una solución

Otro aspecto importante de las soluciones de varios proyectos es establecer una buena estructura de proyecto general. Para estructurar una biblioteca de varios proyectos, debe usar las carpetas `/src` y `/test` de nivel superior:

```
/AwesomeLibrary
|__global.json
|__/src
   |__/AwesomeLibrary.Core
      |__Source Files
      |__project.json
   |__/AwesomeLibrary.CSharp
      |__Source Files
      |__project.json
   |__/AwesomeLibrary.FSharp
      |__Source Files
      |__project.json
|__/test
   |__/AwesomeLibrary.Core.Tests
      |__Test Files
      |__project.json
   |__/AwesomeLibrary.CSharp.Tests
      |__Test Files
      |__project.json
   |__/AwesomeLibrary.FSharp.Tests
      |__Test Files
      |__project.json
```

El archivo `global.json` de esta solución tendría una apariencia similar a la siguiente:

```json
{
    "projects":["src", "test"]
}
```

Este enfoque sigue el mismo patrón establecido por las plantillas del proyecto en el comando `dotnet new`, donde todos los proyectos se encuentran en un directorio `/src` y todas las pruebas, en un directorio `/test`.

Aquí se muestra cómo podría restaurar paquetes, además de compilar y probar todo el proyecto:

```
$ dotnet restore
$ cd src/AwesomeLibrary.FSharp
$ dotnet build
$ cd ../AwesomeLibrary.CSharp
$ dotnet build
$ cd ../../test/AwesomeLibrary.Core.Tests
$ dotnet test
$ cd ../AwesomeLibrary.CSharp.Tests
$ dotnet test
$ cd ../AwesomeLibrary.FSharp.Tests
$ dotnet test
```

Y listo.

