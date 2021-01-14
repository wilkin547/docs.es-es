---
title: Estructura del proyecto para las Blazor aplicaciones
description: Obtenga información sobre cómo se comparan las estructuras de proyecto de formularios Web Forms y proyectos de ASP.NET Blazor .
author: danroth27
ms.author: daroth
no-loc:
- Blazor
- WebAssembly
ms.date: 11/20/2020
ms.openlocfilehash: ba7113c88db728f30812821deaf7c06a80663d1f
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "98189094"
---
# <a name="project-structure-for-no-locblazor-apps"></a>Estructura del proyecto para las Blazor aplicaciones

A pesar de las diferencias importantes en la estructura del proyecto, ASP.NET Web Forms y Blazor comparta muchos conceptos similares. Aquí veremos la estructura de un Blazor proyecto y lo comparamos con un proyecto de formularios web forms ASP.net.

Para crear su primera Blazor aplicación, siga las instrucciones de los [ Blazor pasos de introducción](/aspnet/core/blazor/get-started). Puede seguir las instrucciones para crear una Blazor aplicación de servidor o una Blazor WebAssembly aplicación hospedada en ASP.net Core. A excepción de la lógica específica del modelo de hospedaje, la mayor parte del código en ambos proyectos es el mismo.

## <a name="project-file"></a>Archivo del proyecto

Blazor Las aplicaciones de servidor son proyectos de .NET. El archivo de proyecto para la Blazor aplicación de servidor es tan sencillo como puede obtener:

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
  </PropertyGroup>

</Project>
```

El archivo de proyecto de una Blazor WebAssembly aplicación tiene un aspecto ligeramente más implicado (los números de versión exactos pueden variar):

```xml
<Project Sdk="Microsoft.NET.Sdk.BlazorWebAssembly">

  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.AspNetCore.Components.WebAssembly" Version="5.0.0" />
    <PackageReference Include="Microsoft.AspNetCore.Components.WebAssembly.DevServer" Version="5.0.0" PrivateAssets="all" />
    <PackageReference Include="System.Net.Http.Json" Version="5.0.0" />
  </ItemGroup>

</Project>
```

BlazorWebAssemblylos destinos `Microsoft.NET.Sdk.BlazorWebAssembly` del proyecto en lugar del `Microsoft.NET.Sdk.Web` SDK porque se ejecutan en el explorador en un entorno de WebAssembly tiempo de ejecución .net basado en. No se puede instalar .NET en un explorador Web como puede hacerlo en un servidor o un equipo del desarrollador. Por consiguiente, el proyecto hace referencia al Blazor marco mediante referencias de paquete individuales.

Por comparación, un proyecto de formularios Web Forms de ASP.NET predeterminado incluye casi 300 líneas de XML en su archivo *. csproj* , la mayoría de las cuales está enumerando explícitamente los distintos archivos de código y contenido en el proyecto. Con la versión de `.NET 5` `Blazor Server` y la `Blazor WebAssembly` aplicación puede compartir fácilmente un entorno de ejecución unificado.

Aunque se admiten, las referencias de ensamblado individuales son menos comunes en los proyectos de .NET. La mayoría de las dependencias del proyecto se administran como referencias de paquetes NuGet. Solo necesita hacer referencia a las dependencias de paquete de nivel superior en los proyectos de .NET. Las dependencias transitivas se incluyen automáticamente. En lugar de usar el archivo *packages.config* que se encuentra normalmente en los proyectos de formularios web forms de ASP.net para hacer referencia a los paquetes, las referencias de paquete se agregan al archivo de proyecto mediante el `<PackageReference>` elemento.

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
</ItemGroup>
```

## <a name="entry-point"></a>Punto de entrada

El Blazor punto de entrada de la aplicación de servidor se define en el archivo *Program.CS* , como se verá en una aplicación de consola. Cuando se ejecuta la aplicación, crea y ejecuta una instancia de host web con los valores predeterminados específicos de Web Apps. El host de Web administra el Blazor ciclo de vida de la aplicación de servidor y configura los servicios de nivel de host. Algunos ejemplos de estos servicios son la configuración, el registro, la inserción de dependencias y el servidor HTTP. Este código es principalmente reutilizable y a menudo se deja sin cambios.

```csharp
public class Program
{
    public static void Main(string[] args)
    {
        CreateHostBuilder(args).Build().Run();
    }

    public static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureWebHostDefaults(webBuilder =>
            {
                webBuilder.UseStartup<Startup>();
            });
}
```

Blazorlas WebAssembly aplicaciones también definen un punto de entrada en *Program.CS*. El código tiene un aspecto ligeramente diferente. El código es similar en que está configurando el host de la aplicación para proporcionar los mismos servicios de nivel de host a la aplicación. Sin embargo, el host de la WebAssembly aplicación no configura un servidor http porque se ejecuta directamente en el explorador.

Blazor las aplicaciones tienen una `Startup` clase en lugar de un archivo *global. asax* para definir la lógica de inicio de la aplicación. La `Startup` clase se usa para configurar la aplicación y los servicios específicos de la aplicación. En la Blazor aplicación de servidor, la `Startup` clase se usa para configurar el extremo de la conexión en tiempo real utilizada por Blazor entre los exploradores cliente y el servidor. En la Blazor WebAssembly aplicación, la `Startup` clase define los componentes raíz de la aplicación y dónde se deben representar. Veremos más en profundidad la `Startup` clase en la sección de inicio de la [aplicación](./app-startup.md) .

## <a name="static-files"></a>Archivos estáticos

A diferencia de los proyectos de formularios Web Forms de ASP.NET, no todos los archivos de un Blazor proyecto se pueden solicitar como archivos estáticos. Solo los archivos de la carpeta *wwwroot* son direccionables por Web. Esta carpeta se conoce como "raíz Web" de la aplicación. Cualquier cosa fuera de la raíz Web de la aplicación *no es* direccionable por Web. Este programa de instalación proporciona un nivel de seguridad adicional que evita la exposición accidental de archivos de proyecto a través de la Web.

## <a name="configuration"></a>Configuración

La configuración de las aplicaciones de formularios Web Forms de ASP.NET se controla normalmente mediante uno o varios archivos *web.config* . Blazor Normalmente, las aplicaciones no tienen archivos *web.config* . Si lo hacen, el archivo solo se utiliza para configurar los valores específicos de IIS cuando se hospedan en IIS. En su lugar, Blazor las aplicaciones de servidor usan las abstracciones de configuración de ASP.net Core ( Blazor WebAssembly las aplicaciones no admiten actualmente las mismas abstracciones de configuración, pero pueden ser una característica agregada en el futuro). Por ejemplo, la Blazor aplicación de servidor predeterminada almacena algunos valores en *appsettings.jsen*.

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft": "Warning",
      "Microsoft.Hosting.Lifetime": "Information"
    }
  },
  "AllowedHosts": "*"
}
```

Más información sobre la configuración en proyectos de ASP.NET Core en la sección de [configuración](./config.md) .

## <a name="razor-components"></a>Componentes de Razor

La mayoría de los archivos de los Blazor proyectos son archivos *. Razor* . Razor es un lenguaje de plantillas basado en HTML y C# que se usa para generar dinámicamente la interfaz de usuario Web. Los archivos *. Razor* definen los componentes que componen la interfaz de usuario de la aplicación. En su mayor parte, los componentes son idénticos tanto para el Blazor servidor como para las Blazor WebAssembly aplicaciones. Los componentes de Blazor son análogos a los controles de usuario de formularios Web Forms de ASP.net.

Cada archivo de componente de Razor se compila en una clase .NET cuando se compila el proyecto. La clase generada captura el estado del componente, la lógica de representación, los métodos de ciclo de vida, los controladores de eventos y otra lógica. Veremos cómo crear componentes en la sección [creación de componentes de interfaz de usuario Blazor reutilizables con](./components.md) .

Los archivos *_Imports. Razor* no son archivos de componentes de Razor. En su lugar, definen un conjunto de directivas de Razor para importar en otros archivos *. Razor* dentro de la misma carpeta y en sus subcarpetas. Por ejemplo, un archivo *_Imports. Razor* es una manera convencional de agregar `using` directivas para los espacios de nombres usados comúnmente:

```razor
@using System.Net.Http
@using Microsoft.AspNetCore.Authorization
@using Microsoft.AspNetCore.Components.Authorization
@using Microsoft.AspNetCore.Components.Forms
@using Microsoft.AspNetCore.Components.Routing
@using Microsoft.AspNetCore.Components.Web
@using Microsoft.JSInterop
@using BlazorApp1
@using BlazorApp1.Shared
```

## <a name="pages"></a>Páginas

¿Dónde están las páginas de las Blazor aplicaciones? Blazor no define una extensión de archivo independiente para las páginas direccionables, como los archivos *. aspx* de las aplicaciones de formularios Web Forms de ASP.net. En su lugar, las páginas se definen asignando rutas a los componentes. Normalmente, una ruta se asigna mediante la `@page` Directiva Razor. Por ejemplo, el `Counter` componente creado en el archivo *pages/Counter. Razor* define la ruta siguiente:

```razor
@page "/counter"
```

El enrutamiento en Blazor se controla en el lado cliente, no en el servidor. A medida que el usuario navega en el explorador, Blazor intercepta la navegación y, a continuación, representa el componente con la ruta correspondiente.

Las rutas del componente no se deducen actualmente por la ubicación del archivo del componente, como sucede con las páginas *. aspx* . Esta característica se puede Agregar en el futuro. Cada ruta debe especificarse explícitamente en el componente. El almacenamiento de componentes enrutables en una carpeta *pages* no tiene ningún significado especial y es meramente una Convención.

Veremos más detalladamente el enrutamiento en Blazor en la sección [páginas, enrutamiento y diseños](./pages-routing-layouts.md) .

## <a name="layout"></a>Layout

En las aplicaciones de formularios Web Forms de ASP.NET, un diseño de página común se controla mediante páginas maestras (*site. Master*). En Blazor las aplicaciones de, el diseño de página se controla mediante componentes de diseño (*Shared/MainLayout. Razor*). Los componentes de diseño se tratarán con más detalle en la sección [página, enrutamiento y diseños](./pages-routing-layouts.md) .

## <a name="bootstrap-no-locblazor"></a>Bootstrap Blazor

Para arrancar Blazor , la aplicación debe:

- Especifique en qué lugar de la página se debe representar el componente raíz (*app. Razor*).
- Agregue el Blazor script de marco correspondiente.

En la Blazor aplicación de servidor, la página host del componente raíz se define en el archivo *_Host. cshtml* . Este archivo define una página de Razor, no un componente. Razor Pages usar sintaxis Razor para definir una página direccionable por el servidor, de forma muy parecida a una página *. aspx* . El `Html.RenderComponentAsync<TComponent>(RenderMode)` método se utiliza para definir dónde se debe representar un componente de nivel de raíz. La `RenderMode` opción indica la manera en que se debe representar el componente. En la tabla siguiente se describen las opciones admitidas `RenderMode` .

|Opción                        |Descripción       |
|------------------------------|------------------|
|`RenderMode.Server`           |Se representa de forma interactiva una vez que se establece una conexión con el explorador|
|`RenderMode.ServerPrerendered`|Primer prerepresentado y después representado de forma interactiva|
|`RenderMode.Static`           |Se representa como contenido estático|

La referencia de script a *_framework/blazor.server.js* establece la conexión en tiempo real con el servidor y, a continuación, trata todas las interacciones del usuario y las actualizaciones de la interfaz de usuario.

```razor
@page "/"
@namespace BlazorApp1.Pages
@addTagHelper *, Microsoft.AspNetCore.Mvc.TagHelpers

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>BlazorApp1</title>
    <base href="~/" />
    <link rel="stylesheet" href="css/bootstrap/bootstrap.min.css" />
    <link href="css/site.css" rel="stylesheet" />
</head>
<body>
    <app>
        @(await Html.RenderComponentAsync<App>(RenderMode.ServerPrerendered))
    </app>

    <script src="_framework/blazor.server.js"></script>
</body>
</html>
```

En la Blazor WebAssembly aplicación, la página host es un archivo HTML estático simple en *wwwroot/index.html*. El `<div>` elemento con el identificador denominado `app` se utiliza para indicar dónde se debe representar el componente raíz.

```html
<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
    <title>BlazorApp2</title>
    <base href="/" />
    <link href="css/bootstrap/bootstrap.min.css" rel="stylesheet" />
    <link href="css/app.css" rel="stylesheet" />
    <link href="blazor-web.styles.css" rel="stylesheet" />
</head>

<body>
    <div id="app">Loading...</div>

    <div id="blazor-error-ui">
        An unhandled error has occurred.
        <a href="" class="reload">Reload</a>
        <a class="dismiss">🗙</a>
    </div>
    <script src="_framework/blazor.webassembly.js"></script>
</body>

</html>

```

El componente raíz que se va a representar se especifica en el método de la aplicación `Program.Main` con la flexibilidad de registrar los servicios mediante la inserción de dependencias. Para obtener más información, vea [ASP.net Core la Blazor inserción de dependencias](/aspnet/core/blazor/fundamentals/dependency-injection?pivots=webassembly).

```csharp
public class Program
{
    public static async Task Main(string[] args)
    {
        var builder = WebAssemblyHostBuilder.CreateDefault(args);
        builder.RootComponents.Add<App>("#app");

        ....
        ....
    }
}
```

## <a name="build-output"></a>Resultado de la compilación

Cuando se compila un Blazor proyecto, todos los componentes de Razor y los archivos de código se compilan en un único ensamblado. A diferencia de los proyectos de formularios Web Forms de ASP.NET, Blazor no admite la compilación en tiempo de ejecución de la lógica de IU.

## <a name="run-the-app"></a>Ejecutar la aplicación

Para ejecutar la Blazor aplicación de servidor, presione `F5` en Visual Studio. Blazor las aplicaciones no admiten la compilación en tiempo de ejecución. Para ver los resultados de los cambios de código y marcado de componentes, vuelva a compilar y reiniciar la aplicación con el depurador asociado. Si se ejecuta sin el depurador adjunto ( `Ctrl+F5` ), Visual Studio inspecciona los cambios de archivo y reinicia la aplicación a medida que se realizan cambios. Actualice manualmente el explorador a medida que se realicen cambios.

Para ejecutar la Blazor WebAssembly aplicación, elija uno de los métodos siguientes:

- Ejecute el proyecto de cliente directamente mediante el servidor de desarrollo.
- Ejecute el proyecto de servidor al hospedar la aplicación con ASP.NET Core.

Blazorlas WebAssembly aplicaciones se pueden depurar en el explorador y Visual Studio. vea [depurar ASP.net Core Blazor WebAssembly ](/aspnet/core/blazor/debug) para obtener más información.

>[!div class="step-by-step"]
>[Anterior](hosting-models.md)
>[Siguiente](app-startup.md)
