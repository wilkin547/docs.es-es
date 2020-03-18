---
title: Estructura del proyecto para aplicaciones Blazor
description: Conozca cómo se comparan las estructuras de proyecto de ASP.NET proyectos de formularios Web Forms y Blazor.
author: danroth27
ms.author: daroth
ms.date: 09/11/2019
ms.openlocfilehash: 2c383e86ff22f5a3460476998992b66e9417cc11
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401746"
---
# <a name="project-structure-for-blazor-apps"></a>Estructura del proyecto para aplicaciones Blazor

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

A pesar de sus significativas diferencias en la estructura del proyecto, ASP.NET Web Forms y Blazor comparten muchos conceptos similares. Aquí, veremos la estructura de un proyecto Blazor y lo compararemos con un proyecto de formularios Web Forms ASP.NET.

Para crear su primera aplicación Blazor, siga las instrucciones de los [pasos de introducción de Blazor](/aspnet/core/blazor/get-started). Puede seguir las instrucciones para crear una aplicación Blazor Server o una aplicación Blazor WebAssembly hospedada en ASP.NET Core. A excepción de la lógica específica del modelo de hospedaje, la mayor parte del código de ambos proyectos es el mismo.

## <a name="project-file"></a>Archivo del proyecto

Las aplicaciones de Blazor Server son proyectos de .NET Core. El archivo de proyecto para la aplicación Blazor Server es tan simple como puede obtener:

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>
```

El archivo de proyecto para una aplicación Blazor WebAssembly parece un poco más implicado (los números de versión exactos pueden variar):

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
    <RazorLangVersion>3.0</RazorLangVersion>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.AspNetCore.Blazor" Version="3.1.0" />
    <PackageReference Include="Microsoft.AspNetCore.Blazor.Build" Version="3.1.0" PrivateAssets="all" />
    <PackageReference Include="Microsoft.AspNetCore.Blazor.HttpClient" Version="3.1.0" />
    <PackageReference Include="Microsoft.AspNetCore.Blazor.DevServer" Version="3.1.0" PrivateAssets="all" />
  </ItemGroup>

  <ItemGroup>
    <ProjectReference Include="..\Shared\BlazorWebAssemblyApp1.Shared.csproj" />
  </ItemGroup>

</Project>
```

Los proyectos blazor WebAssembly tienen como destino .NET Standard en lugar de .NET Core porque se ejecutan en el explorador en un tiempo de ejecución de .NET basado en WebAssembly. No puede instalar .NET en un explorador web como en un servidor o equipo de desarrollador. Por consiguiente, el proyecto hace referencia al marco Blazor utilizando referencias de paquetes individuales.

En comparación, un proyecto de formularios Web Forms de ASP.NET predeterminado incluye casi 300 líneas de XML en su archivo *.csproj,* la mayoría de los cuales enumera explícitamente los distintos archivos de código y contenido del proyecto. Muchas de las simplificaciones de los proyectos basados en .NET Core y .NET Standard `Microsoft.NET.Sdk.Web` proceden de los destinos predeterminados y las propiedades importadas haciendo referencia al SDK, a menudo denominado simplemente el SDK web. El SDK web incluye comodines y otras comodidades que simplifican la inclusión de código y archivos de contenido en el proyecto. No es necesario enumerar los archivos explícitamente. Al tener como destino .NET Core, el SDK web también agrega referencias de marco de trabajo a los marcos compartidos de .NET Core y ASP.NET Core. Los marcos de trabajo son visibles desde **el** > **marcos** de trabajo nodo en el Explorador de **soluciones** ventana. Los marcos compartidos son colecciones de ensamblados que se instalaron en el equipo al instalar .NET Core.

Aunque se admiten, las referencias de ensamblado individuales son menos comunes en los proyectos de .NET Core. La mayoría de las dependencias del proyecto se controlan como referencias de paquete NuGet. Solo necesita hacer referencia a dependencias de paquetes de nivel superior en proyectos de .NET Core. Las dependencias transitivas se incluyen automáticamente. En lugar de usar el archivo *packages.config* que se encuentra normalmente en ASP.NET proyectos `<PackageReference>` de formularios Web Forms para hacer referencia a paquetes, las referencias de paquete se agregan al archivo de proyecto mediante el elemento.

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
</ItemGroup>
```

## <a name="entry-point"></a>Punto de entrada

El punto de entrada de la aplicación Blazor Server se define en el archivo *Program.cs,* como se verá en una aplicación de consola. Cuando se ejecuta la aplicación, crea y ejecuta una instancia de host web con valores predeterminados específicos de las aplicaciones web. El host web administra el ciclo de vida de la aplicación Blazor Server y configura servicios de nivel de host. Ejemplos de estos servicios son la configuración, el registro, la inserción de dependencias y el servidor HTTP. Este código es principalmente reutilizable y a menudo se deja sin cambios.

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

Las aplicaciones Blazor WebAssembly también definen un punto de entrada en *Program.cs*. El código se ve ligeramente diferente. El código es similar en que está configurando el host de la aplicación para proporcionar los mismos servicios de nivel de host a la aplicación. Sin embargo, el host de la aplicación WebAssembly no configura un servidor HTTP porque se ejecuta directamente en el explorador.

Las aplicaciones Blazor tienen una `Startup` clase en lugar de un archivo *Global.asax* para definir la lógica de inicio de la aplicación. La `Startup` clase se usa para configurar la aplicación y los servicios específicos de la aplicación. En la aplicación Blazor `Startup` Server, la clase se utiliza para configurar el punto de conexión para la conexión en tiempo real utilizada por Blazor entre los exploradores del cliente y el servidor. En la aplicación Blazor `Startup` WebAssembly, la clase define los componentes raíz de la aplicación y dónde se deben representar. Echaremos un vistazo más `Startup` profundo a la clase en la sección Inicio de la [aplicación.](./app-startup.md)

## <a name="static-files"></a>Archivos estáticos

A diferencia de ASP.NET proyectos de formularios Web Forms, no todos los archivos de un proyecto de Blazor se pueden solicitar como archivos estáticos. Solo los archivos de la carpeta *wwwroot* son direccionables por la web. Esta carpeta se refiere a la "raíz web" de la aplicación. Cualquier cosa fuera de la raíz web de la aplicación *no es* direccionable a la web. Esta configuración proporciona un nivel adicional de seguridad que evita la exposición accidental de archivos de proyecto a través de la web.

## <a name="configuration"></a>Configuración

La configuración en ASP.NET aplicaciones de formularios Web Forms normalmente se controla mediante uno o varios archivos *web.config.* Las aplicaciones blazor normalmente no tienen archivos *web.config.* Si lo hacen, el archivo solo se usa para configurar la configuración específica de IIS cuando se hospeda en IIS. En su lugar, las aplicaciones de Blazor Server usan las abstracciones de configuración de ASP.NET Core (las aplicaciones Blazor WebAssembly no admiten actualmente las mismas abstracciones de configuración, pero puede ser una característica agregada en el futuro). Por ejemplo, la aplicación Blazor Server predeterminada almacena algunos valores en *appsettings.json*.

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

Aprenderemos más sobre la configuración en ASP.NET proyectos Core en la sección [Configuración.](./config.md)

## <a name="razor-components"></a>Componentes de Razor

La mayoría de los archivos de los proyectos de Blazor son archivos *.razor.* Razor es un lenguaje de plantillas basado en HTML y C- que se usa para generar dinámicamente la interfaz de usuario web. Los archivos *.razor* definen los componentes que componen la interfaz de usuario de la aplicación. En su mayor parte, los componentes son idénticos para las aplicaciones Blazor Server y Blazor WebAssembly. Los componentes de Blazor son análogos a los controles de usuario en ASP.NET formularios Web Forms.

Cada archivo de componente de Razor se compila en una clase .NET cuando se compila el proyecto. La clase generada captura el estado del componente, la lógica de representación, los métodos del ciclo de vida, los controladores de eventos y otra lógica. Veremos la creación de componentes en la sección Creación de componentes de interfaz de [usuario reutilizables con Blazor.](./components.md)

Los archivos *_Imports.razor* no son archivos de componentes de Razor. En su lugar, definen un conjunto de directivas Razor para importar en otros archivos *.razor* dentro de la misma carpeta y en sus subcarpetas. Por ejemplo, un archivo *_Imports.razor* es `using` una forma convencional de agregar instrucciones para espacios de nombres de uso común:

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

¿Dónde están las páginas de las aplicaciones de Blazor? Blazor no define una extensión de archivo independiente para páginas direccionables, como los archivos *.aspx* en ASP.NET aplicaciones de formularios Web Forms. En su lugar, las páginas se definen asignando rutas a los componentes. Normalmente, una ruta `@page` se asigna mediante la directiva Razor. Por ejemplo, `Counter` el componente creado en el archivo *Pages/Counter.razor* define la ruta siguiente:

```razor
@page "/counter"
```

El enrutamiento en Blazor se maneja en el lado del cliente, no en el servidor. A medida que el usuario navega en el explorador, Blazor intercepta la navegación y, a continuación, representa el componente con la ruta coincidente.

Las rutas de componentes no se deducen actualmente por la ubicación del archivo del componente como lo son con las páginas *.aspx.* Esta función se puede agregar en el futuro. Cada ruta debe especificarse explícitamente en el componente. Almacenar componentes enrutables en una carpeta *Pages* no tiene un significado especial y es puramente una convención.

Veremos con más detalle el enrutamiento en Blazor en la sección [Páginas, enrutamiento y diseños.](./pages-routing-layouts.md)

## <a name="layout"></a>Diseño

En ASP.NET aplicaciones de formularios Web Forms, el diseño de página común se controla mediante páginas maestras (*Site.Master*). En las aplicaciones blazor, el diseño de página se controla mediante componentes de diseño (*Shared/MainLayout.razor*). Los componentes de diseño se tratarán con más detalle en la sección [Página, enrutamiento y diseños.](./pages-routing-layouts.md)

## <a name="bootstrap-blazor"></a>Bootstrap Blazor

Para arrancar Blazor, la aplicación debe:

- Especifique en qué parte de la página se debe representar el componente raíz (*App.Razor*).
- Agregue el script de marco Blazor correspondiente.

En la aplicación Blazor Server, la página host del componente raíz se define en el archivo *_Host.cshtml.* Este archivo define una página de razor, no un componente. Razor Pages usa la sintaxis de Razor para definir una página direccionable por el servidor, muy similar a una página *.aspx.* El `Html.RenderComponentAsync<TComponent>(RenderMode)` método se utiliza para definir dónde se debe representar un componente de nivel raíz. La `RenderMode` opción indica la forma en que se debe representar el componente. En la tabla siguiente `RenderMode` se describen las opciones admitidas.

|Opción                        |Descripción       |
|------------------------------|------------------|
|`RenderMode.Server`           |Renderizado interactivamente una vez que se establece una conexión con el navegador|
|`RenderMode.ServerPrerendered`|Primero prerendered y luego renderizado interactivamente|
|`RenderMode.Static`           |Representado como contenido estático|

La referencia de script a *_framework/blazor.server.js* establece la conexión en tiempo real con el servidor y, a continuación, se ocupa de todas las interacciones del usuario y actualizaciones de la interfaz de usuario.

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

En la aplicación Blazor WebAssembly, la página host es un archivo HTML estático simple en *wwwroot/index.html*. El `<app>` elemento se utiliza para indicar dónde se debe representar el componente raíz.

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
    <title>BlazorApp2</title>
    <base href="/" />
    <link href="css/bootstrap/bootstrap.min.css" rel="stylesheet" />
    <link href="css/site.css" rel="stylesheet" />
</head>
<body>
    <app>Loading...</app>

    <script src="_framework/blazor.webassembly.js"></script>
</body>
</html>
```

El componente específico que se va `Startup.Configure` a representar se configura en el método de la aplicación con un selector CSS correspondiente que indica dónde se debe representar el componente.

```csharp
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
    }

    public void Configure(IComponentsApplicationBuilder app)
    {
        app.AddComponent<App>("app");
    }
}
```

## <a name="build-output"></a>Resultado de la compilación

Cuando se compila un proyecto de Blazor, todos los archivos de código y componentes de Razor se compilan en un único ensamblado. A diferencia de ASP.NET proyectos de formularios Web Forms, Blazor no admite la compilación en tiempo de ejecución de la lógica de interfaz de usuario.

## <a name="run-the-app"></a>Ejecución la aplicación

Para ejecutar la aplicación Blazor Server, presione `F5` en Visual Studio. Las aplicaciones blazor no admiten la compilación en tiempo de ejecución. Para ver los resultados de los cambios de marcado de código y componentes, vuelva a generar y reinicie la aplicación con el depurador adjunto. Si se ejecuta sin`Ctrl+F5`el depurador adjunto ( ), Visual Studio busca cambios en los archivos y reinicia la aplicación a medida que se realizan cambios. Actualice manualmente el explorador a medida que se realizan cambios.

Para ejecutar la aplicación Blazor WebAssembly, elija uno de los siguientes enfoques:

- Ejecute el proyecto de cliente directamente mediante el servidor de desarrollo.
- Ejecute el proyecto de servidor al hospedar la aplicación con ASP.NET Core.

Las aplicaciones WebAssembly de Blazor no admiten la depuración mediante Visual Studio. Para ejecutar la `Ctrl+F5` aplicación, `F5`use en lugar de . En su lugar, puede depurar las aplicaciones Blazor WebAssembly directamente en el explorador. Consulte [Depurar ASP.NET Core Blazor](/aspnet/core/blazor/debug) para obtener más información.

>[!div class="step-by-step"]
>[Anterior](hosting-models.md)
>[Siguiente](app-startup.md)
