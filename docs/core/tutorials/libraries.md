---
title: Desarrollo de bibliotecas con la CLI de .NET Core
description: Aprenda a crear bibliotecas de .NET Core con la CLI de .NET Core. Creará una biblioteca que admite varios marcos de trabajo.
author: cartermp
ms.topic: how-to
ms.date: 05/01/2017
ms.openlocfilehash: e98ce9e08c8d92bb4c89348e21cece60de811848
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2020
ms.locfileid: "92223702"
---
# <a name="develop-libraries-with-the-net-core-cli"></a>Desarrollo de bibliotecas con la CLI de .NET Core

En este artículo se explica cómo escribir bibliotecas para .NET con la CLI de .NET Core. La CLI proporciona una experiencia eficaz y de bajo nivel que funciona en todos los SO compatibles. De todos modos puede seguir compilando bibliotecas con Visual Studio; si esa es la experiencia de su preferencia, [consulte la guía sobre Visual Studio](library-with-visual-studio.md).

## <a name="prerequisites"></a>Requisitos previos

Necesita [la CLI y el SDK de .NET Core](https://dotnet.microsoft.com/download) que están instalados en la máquina.

En las secciones de este documento que se refieren a las versiones de .NET Framework, necesita tener instalado [.NET Framework](https://dotnet.microsoft.com) en una máquina con Windows.

Además, si desea admitir destinos de .NET Framework anteriores, deberá instalar paquetes de destino o desarrollador desde la [página de archivos de descarga de .NET](https://dotnet.microsoft.com/download/archives). Consulte la tabla siguiente:

| Versión de .NET Framework | Qué debe descargar                                       |
| ---------------------- | ------------------------------------------------------ |
| 4.6.1                  | Paquete de compatibilidad de .NET Framework 4.6.1                    |
| 4.6                    | Paquete de compatibilidad de .NET Framework 4.6                      |
| 4.5.2                  | Paquete de desarrollador de .NET Framework 4.5.2                    |
| 4.5.1                  | Paquete de desarrollador de .NET Framework 4.5.1                    |
| 4.5                    | Kit de desarrollo de software de Windows para Windows 8         |
| 4.0                    | Windows SDK para Windows 7 y .NET Framework 4         |
| 2.0, 3.0 y 3.5      | Entorno de ejecución de .NET Framework 3.5 SP1 (o una versión posterior a Windows 8) |

## <a name="how-to-target-net-standard"></a>Establecimiento de .NET Standard como destino

Si no conoce .NET Standard, consulte el tema [.NET Standard](../../standard/net-standard.md) para más información.

En ese artículo podrá ver una tabla que asigna las versiones de .NET Standard a diversas implementaciones:

[!INCLUDE [net-standard-table](../../../includes/net-standard-table.md)]

Este es el significado de la tabla para crear una biblioteca:

La versión de .NET Standard que elija será un equilibrio entre el acceso a las API más recientes y la capacidad de apuntar a más implementaciones .NET y más versiones de .NET Standard. Puede controlar el intervalo de versiones y plataformas de destino si elige una versión de `netstandardX.X` (donde `X.X` es un número de versión) y la agrega al archivo del proyecto (`.csproj` o `.fsproj`).

En función de sus necesidades, tiene tres opciones principales cuando el destino es .NET Standard.

1. Puede usar la versión predeterminada de .NET Standard que se proporciona con plantillas, `netstandard1.4`, que le permite acceder a la mayoría de API en .NET Standard mientras sigue siendo compatible con UWP, .NET Framework 4.6.1 y .NET Standard 2.0.

    ```xml
    <Project Sdk="Microsoft.NET.Sdk">
      <PropertyGroup>
        <TargetFramework>netstandard1.4</TargetFramework>
      </PropertyGroup>
    </Project>
    ```

2. Puede usar una versión anterior o posterior de .NET Standard modificando el valor en el nodo `TargetFramework` de su archivo del proyecto.

    Las versiones del estándar .NET son compatibles con versiones anteriores. Eso significa que las bibliotecas `netstandard1.0` se pueden ejecutar en plataformas `netstandard1.1` y versiones superiores. Sin embargo, no hay compatibilidad con versiones posteriores. Las plataformas de .NET Standard anteriores no pueden hacer referencia a las posteriores. Esto significa que las bibliotecas `netstandard1.0` no pueden hacer referencia a las bibliotecas que tienen como destino `netstandard1.1` o una versión superior. Seleccione la versión estándar que tiene la combinación adecuada de compatibilidad con API y plataformas que necesita. Por ahora le recomendamos `netstandard1.4`.

3. Si desea tener como destino .NET Framework versión 4.0 o inferior, o bien desea usar una API disponible en .NET Framework pero no disponible en el estándar .NET (por ejemplo, `System.Drawing`), lea las secciones siguientes y sepa cómo tener compatibilidad con múltiples versiones.

## <a name="how-to-target-net-framework"></a>Uso de .NET Framework como destino

> [!NOTE]
> En estas instrucciones se supone que tiene instalado .NET Framework en su máquina. Consulte los [requisitos previos](#prerequisites) para instalar las dependencias.

Tenga en cuenta que algunas de las versiones de .NET Framework que se usan aquí ya no cuentan con soporte técnico. Consulte las [P+F sobre la directiva del ciclo de vida de soporte técnico de .NET Framework](https://support.microsoft.com/gp/framework_faq/en-us) sobre las versiones sin soporte técnico.

Si quiere llegar a la mayor cantidad posible de desarrolladores y proyectos, use .NET Framework 4.0 como el destino de línea base. Para tener .NET Framework como destino, comience utilizando el moniker de la plataforma de destino (TFM) correcto que corresponda a la versión de .NET Framework que desea admitir.

| Versión de .NET Framework | TFM      |
| ---------------------- | -------- |
| .NET Framework 2.0     | `net20`  |
| .NET Framework 3.0     | `net30`  |
| .NET Framework 3,5     | `net35`  |
| .NET Framework 4.0     | `net40`  |
| .NET Framework 4.5     | `net45`  |
| .NET Framework 4.5.1   | `net451` |
| .NET Framework 4.5.2   | `net452` |
| .NET Framework 4.6     | `net46`  |
| .NET Framework 4.6.1   | `net461` |
| .NET Framework 4.6.2   | `net462` |
| .NET Framework 4.7     | `net47`  |
| .NET Framework 4.8     | `net48`  |

Después, inserte el TFM en la sección `TargetFramework` de su archivo del proyecto. El siguiente es un ejemplo de cómo podría escribir una biblioteca que tenga como destino .NET Framework 4.0:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>net40</TargetFramework>
  </PropertyGroup>
</Project>
```

Y listo. Aunque esto solo hace la compilación para .NET Framework 4, puede usar la biblioteca en las versiones más recientes de .NET Framework.

## <a name="how-to-multitarget"></a>Cómo lograr la compatibilidad con varias versiones

> [!NOTE]
> Las instrucciones siguientes suponen que tiene instalado .NET Framework en su máquina. Consulte la sección de [requisitos previos](#prerequisites) para información sobre las dependencias que debe instalar y dónde descargarlas.

Es posible que deba tener como destino versiones anteriores de .NET Framework cuando el proyecto admite .NET Framework y .NET Core. En este escenario, si desea usar API más recientes y construcciones de lenguaje para los destinos más recientes, use las directivas `#if` en el código. También es posible que tenga que agregar distintos paquetes y dependencias para cada plataforma que tiene como destino para incluir las distintas API necesarias para cada caso.

Por ejemplo, digamos que tiene una biblioteca que realiza operaciones de red a través de HTTP. En el estándar .NET y .NET Framework versión 4.5 o superiores, puede usar la clase `HttpClient` del espacio de nombres `System.Net.Http`. Sin embargo, las versiones anteriores de .NET Framework no tienen la clase `HttpClient`, por lo que, en su lugar, podría usar la clase `WebClient` del espacio de nombres `System.Net` para esas versiones.

Su archivo del proyecto podría tener la siguiente apariencia:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFrameworks>netstandard1.4;net40;net45</TargetFrameworks>
  </PropertyGroup>

  <!-- Need to conditionally bring in references for the .NET Framework 4.0 target -->
  <ItemGroup Condition="'$(TargetFramework)' == 'net40'">
    <Reference Include="System.Net" />
  </ItemGroup>

  <!-- Need to conditionally bring in references for the .NET Framework 4.5 target -->
  <ItemGroup Condition="'$(TargetFramework)' == 'net45'">
    <Reference Include="System.Net.Http" />
    <Reference Include="System.Threading.Tasks" />
  </ItemGroup>
</Project>
```

Observará tres cambios principales aquí:

1. El nodo `TargetFramework` se ha reemplazado por `TargetFrameworks`, y se expresan tres TFM dentro.
1. Existe un nodo `<ItemGroup>` para el destino `net40` que se dirige a una referencia de .NET Framework.
1. Existe un nodo `<ItemGroup>` para el destino `net45` que se dirige a dos referencias de .NET Framework.

El sistema de compilación conoce los siguientes símbolos del preprocesador que se usan en las directivas `#if`:

[!INCLUDE [Preprocessor symbols](../../../includes/preprocessor-symbols.md)]

Aquí se muestra un ejemplo en el que se usa la compilación condicional por destino:

```csharp
using System;
using System.Text.RegularExpressions;
#if NET40
// This only compiles for the .NET Framework 4 targets
using System.Net;
#else
 // This compiles for all other targets
using System.Net.Http;
using System.Threading.Tasks;
#endif

namespace MultitargetLib
{
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
            string url = "https://www.dotnetfoundation.org/";

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
            string url = "https://www.dotnetfoundation.org/";

            // HttpClient is thread-safe, so no need to explicitly lock here
            var result = await _client.GetStringAsync(url);

            int dotNetCount = Regex.Matches(result, ".NET").Count;

            return $"dotnetfoundation.org mentions .NET {dotNetCount} times in its HTML!";
        }
#endif
    }
}
```

Si crea este proyecto con `dotnet build`, observará tres directorios en la carpeta `bin/`:

```
net40/
net45/
netstandard1.4/
```

Cada uno de ellos contiene los archivos `.dll` para cada destino.

## <a name="how-to-test-libraries-on-net-core"></a>Prueba de las bibliotecas en .NET Core

Es importante poder probar las plataformas. Puede usar [xUnit](https://xunit.github.io/) o MSTest de fábrica. Ambos son perfectamente adecuados para las pruebas unitarias de su biblioteca en .NET Core. Cómo configurar la solución con proyectos de prueba dependerá de la [estructura de la solución](#structuring-a-solution). En el ejemplo siguiente se presupone que los directorios de origen y de prueba residen en el mismo directorio de nivel superior.

> [!NOTE]
> Esto usa algunos comandos de la [CLI de .NET Core](../tools/index.md). Vea [dotnet new](../tools/dotnet-new.md) y [dotnet sln](../tools/dotnet-sln.md) para obtener más información.

1. Configure la solución. Puede hacerlo con los siguientes comandos:

   ```dotnetcli
   mkdir SolutionWithSrcAndTest
   cd SolutionWithSrcAndTest
   dotnet new sln
   dotnet new classlib -o MyProject
   dotnet new xunit -o MyProject.Test
   dotnet sln add MyProject/MyProject.csproj
   dotnet sln add MyProject.Test/MyProject.Test.csproj
   ```

   Esto creará proyectos y se vincularán conjuntamente en una solución. Su directorio para `SolutionWithSrcAndTest` debe tener el siguiente aspecto:

   ```
   /SolutionWithSrcAndTest
   |__SolutionWithSrcAndTest.sln
   |__MyProject/
   |__MyProject.Test/
   ```

1. Vaya al directorio del proyecto de prueba y agregue una referencia a `MyProject.Test` desde `MyProject`.

   ```dotnetcli
   cd MyProject.Test
   dotnet add reference ../MyProject/MyProject.csproj
   ```

1. Restaurar paquetes y crear proyectos:

   ```dotnetcli
   dotnet restore
   dotnet build
   ```

   [!INCLUDE[DotNet Restore Note](../../../includes/dotnet-restore-note.md)]

1. Compruebe que xUnit se ejecuta mediante la ejecución del comando `dotnet test`. Si decide usar MSTest, entonces debe ejecutarse en su lugar el ejecutor de la consola de MSTest.

Y listo. Ahora puede probar la biblioteca en todas las plataformas; para ello, use herramientas de línea de comandos. Para seguir con las pruebas ahora que ya está todo configurado, probar la biblioteca es un proceso muy simple:

1. Haga los cambios en la biblioteca.
1. Ejecute las pruebas desde la línea de comandos, en el directorio de prueba, con el comando `dotnet test`.

El código se recompilará automáticamente cuando invoque el comando `dotnet test`.

## <a name="how-to-use-multiple-projects"></a>Uso de varios proyectos

Una necesidad en común de las bibliotecas de mayor tamaño es ubicar la funcionalidad en distintos proyectos.

Imagine que desea compilar una biblioteca que se pudiera consumir en C# y F# idiomático. Eso significaría que los usuarios de las bibliotecas las consumirían de manera natural para C# o F#. Por ejemplo, en C#, podría consumir la biblioteca de la siguiente manera:

```csharp
using AwesomeLibrary.CSharp;

public Task DoThings(Data data)
{
    var convertResult = await AwesomeLibrary.ConvertAsync(data);
    var result = AwesomeLibrary.Process(convertResult);
    // do something with result
}
```

En F#, sería de la siguiente manera:

```fsharp
open AwesomeLibrary.FSharp

let doWork data = async {
    let! result = AwesomeLibrary.AsyncConvert data // Uses an F# async function rather than C# async method
    // do something with result
}
```

Escenarios de consumo similares a este significan que las API a las que se tiene acceso deben tener una estructura distinta para C# y para F#.  Un enfoque común para lograrlo es factorizar toda la lógica de una biblioteca en un proyecto central, con los proyectos de C# y F# definiendo los niveles de API que hacen llamadas a ese proyecto central.  En el resto de la sección se usarán los siguientes nombres:

* **AwesomeLibrary.Core** : un proyecto central que contiene toda la lógica de la biblioteca
* **AwesomeLibrary.CSharp** : un proyecto con API públicas pensado para el consumo en C#
* **AwesomeLibrary.FSharp** : un proyecto con API públicas pensado para el consumo en F#

Puede ejecutar los siguientes comandos en su terminal para generar la misma estructura de esta guía:

```dotnetcli
mkdir AwesomeLibrary && cd AwesomeLibrary
dotnet new sln
mkdir AwesomeLibrary.Core && cd AwesomeLibrary.Core && dotnet new classlib
cd ..
mkdir AwesomeLibrary.CSharp && cd AwesomeLibrary.CSharp && dotnet new classlib
cd ..
mkdir AwesomeLibrary.FSharp && cd AwesomeLibrary.FSharp && dotnet new classlib -lang "F#"
cd ..
dotnet sln add AwesomeLibrary.Core/AwesomeLibrary.Core.csproj
dotnet sln add AwesomeLibrary.CSharp/AwesomeLibrary.CSharp.csproj
dotnet sln add AwesomeLibrary.FSharp/AwesomeLibrary.FSharp.fsproj
```

Esto agregará los tres proyectos anteriores y un archivo de solución que los vincula conjuntamente. Crear el archivo de solución y vincular los proyectos le permitirá restaurar y crear proyectos desde un nivel superior.

### <a name="project-to-project-referencing"></a>Referencias entre proyectos

La mejor manera de hacer referencia a un proyecto es usar la CLI de .NET Core para agregar una referencia de proyecto. Desde los directorios del proyecto **AwesomeLibrary.CSharp** y **AwesomeLibrary.FSharp** , puede ejecutar el siguiente comando:

```dotnetcli
dotnet add reference ../AwesomeLibrary.Core/AwesomeLibrary.Core.csproj
```

Los archivos del proyecto para **AwesomeLibrary.CSharp** y **AwesomeLibrary.FSharp** ahora harán referencia a **AwesomeLibrary.Core** como un destino `ProjectReference`.  Puede comprobar esto inspeccionando los archivos del proyecto y observando lo siguiente en ellos:

```xml
<ItemGroup>
  <ProjectReference Include="..\AwesomeLibrary.Core\AwesomeLibrary.Core.csproj" />
</ItemGroup>
```

Puede agregar esta sección a cada archivo del proyecto manualmente si prefiere no usar la CLI de .NET Core.

### <a name="structuring-a-solution"></a>Estructura de una solución

Otro aspecto importante de las soluciones de varios proyectos es establecer una buena estructura de proyecto general. Puede organizar el código de la manera que quiera, y siempre y cuando vincule cada proyecto a su archivo de solución con `dotnet sln add`, podrá ejecutar `dotnet restore` y `dotnet build` en el nivel de solución.
