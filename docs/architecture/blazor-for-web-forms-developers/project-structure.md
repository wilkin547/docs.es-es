---
title: Estructura del proyecto para aplicaciones increíbles
description: Obtenga información sobre cómo se comparan las estructuras de proyecto de los proyectos de formularios Web Forms y increíbles de ASP.NET.
author: danroth27
ms.author: daroth
ms.date: 09/11/2019
ms.openlocfilehash: 2c383e86ff22f5a3460476998992b66e9417cc11
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2020
ms.locfileid: "78675000"
---
# <a name="project-structure-for-blazor-apps"></a>Estructura del proyecto para aplicaciones increíbles

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

A pesar de las diferencias importantes de la estructura del proyecto, los formularios Web Forms de ASP.NET y el increíbles comparten muchos conceptos similares. Aquí veremos la estructura de un proyecto increíble y lo comparamos con un proyecto de formularios Web Forms ASP.NET.

Para crear su primera aplicación increíble, siga las instrucciones de los [pasos de introducción más rápido](/aspnet/core/blazor/get-started). Puede seguir las instrucciones para crear una aplicación de servidor más brillante o una aplicación webassembly increíblemente hospedada en ASP.NET Core. A excepción de la lógica específica del modelo de hospedaje, la mayor parte del código en ambos proyectos es el mismo.

## <a name="project-file"></a>Archivo de proyecto

Las aplicaciones de servidor increíbles son proyectos de .NET Core. El archivo de proyecto de la aplicación de servidor de extraordinariamente es tan sencillo como puede obtener:

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>
```

El archivo de proyecto de una aplicación de webassembly increíblemente es algo más complicado (los números de versión exactos pueden variar):

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

Los proyectos de webassembly increíbles tienen como destino .NET Standard en lugar de .NET Core porque se ejecutan en el explorador en un entorno de tiempo de ejecución .NET basado en webassembly. No se puede instalar .NET en un explorador Web como puede hacerlo en un servidor o un equipo del desarrollador. Por consiguiente, el proyecto hace referencia al marco de trabajo de extraordinarias mediante referencias de paquetes individuales.

Por comparación, un proyecto de formularios Web Forms de ASP.NET predeterminado incluye casi 300 líneas de XML en su archivo *. csproj* , la mayoría de las cuales está enumerando explícitamente los distintos archivos de código y contenido en el proyecto. Muchas de las simplificaciones en los proyectos basados en .NET Core y .NET Standard proceden de las propiedades y los destinos predeterminados importados haciendo referencia al SDK de `Microsoft.NET.Sdk.Web`, que a menudo se conoce como el SDK Web. El SDK de web incluye caracteres comodín y otras ventajas que simplifican la inclusión de archivos de código y contenido en el proyecto. No es necesario enumerar los archivos explícitamente. Cuando el destino es .NET Core, el SDK de web también agrega referencias de marco de trabajo a .NET Core y ASP.NET Core Marcos compartidos. Los marcos de trabajo son visibles desde el nodo **dependencias** > **Marcos** en la ventana de **Explorador de soluciones** . Los marcos compartidos son colecciones de ensamblados que se instalaron en el equipo al instalar .NET Core.

Aunque se admiten, las referencias de ensamblado individuales son menos comunes en los proyectos de .NET Core. La mayoría de las dependencias del proyecto se administran como referencias de paquetes NuGet. Solo necesita hacer referencia a las dependencias de paquete de nivel superior en los proyectos de .NET Core. Las dependencias transitivas se incluyen automáticamente. En lugar de usar el archivo *packages. config* que se encuentra normalmente en los proyectos de formularios web forms de ASP.net para hacer referencia a los paquetes, las referencias de paquete se agregan al archivo de proyecto mediante el elemento `<PackageReference>`.

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
</ItemGroup>
```

## <a name="entry-point"></a>Punto de entrada

El punto de entrada de la aplicación de servidor de increíbles se define en el archivo *Program.CS* , como se verá en una aplicación de consola. Cuando se ejecuta la aplicación, crea y ejecuta una instancia de host web con los valores predeterminados específicos de Web Apps. El host Web administra el ciclo de vida de la aplicación de servidor increíble y configura los servicios de nivel de host. Algunos ejemplos de estos servicios son la configuración, el registro, la inserción de dependencias y el servidor HTTP. Este código es principalmente reutilizable y a menudo se deja sin cambios.

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

Las aplicaciones de webassembly increíbles también definen un punto de entrada en *Program.CS*. El código tiene un aspecto ligeramente diferente. El código es similar en que está configurando el host de la aplicación para proporcionar los mismos servicios de nivel de host a la aplicación. Sin embargo, el host de aplicación de webassembly no configura un servidor HTTP porque se ejecuta directamente en el explorador.

Las aplicaciones increíbles tienen una `Startup` clase en lugar de un archivo *global. asax* para definir la lógica de inicio de la aplicación. La clase `Startup` se usa para configurar la aplicación y los servicios específicos de la aplicación. En la aplicación de servidor de extraordinarias, se usa la clase de `Startup` para configurar el extremo de la conexión en tiempo real utilizada por el increíbles entre los exploradores cliente y el servidor. En la aplicación webassembly de extraordinarias, la clase `Startup` define los componentes raíz de la aplicación y dónde se deben representar. Veremos más en profundidad la clase `Startup` en la sección de inicio de la [aplicación](./app-startup.md) .

## <a name="static-files"></a>Archivos estáticos

A diferencia de los proyectos de formularios Web Forms de ASP.NET, no todos los archivos de un proyecto más increíblemente se pueden solicitar como archivos estáticos. Solo los archivos de la carpeta *wwwroot* son direccionables por Web. Esta carpeta se conoce como "raíz Web" de la aplicación. Cualquier cosa fuera de la raíz Web de la aplicación *no es* direccionable por Web. Este programa de instalación proporciona un nivel de seguridad adicional que evita la exposición accidental de archivos de proyecto a través de la Web.

## <a name="configuration"></a>Configuración

La configuración de las aplicaciones de formularios Web Forms de ASP.NET se controla normalmente mediante uno o más archivos *Web. config* . Las aplicaciones increíbles no suelen tener archivos *Web. config* . Si lo hacen, el archivo solo se utiliza para configurar los valores específicos de IIS cuando se hospedan en IIS. En su lugar, las aplicaciones de servidor increíbles usan las abstracciones de configuración de ASP.NET Core (las aplicaciones webassembly increíblemente no admiten actualmente las mismas abstracciones de configuración, pero pueden ser una característica agregada en el futuro). Por ejemplo, la aplicación de servidor increíblemente predeterminada almacena algunos valores en *appSettings. JSON*.

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

La mayoría de los archivos de los proyectos más increíbles son archivos *. Razor* . Razor es un lenguaje de plantillas basado en HTML C# que se usa para generar dinámicamente la interfaz de usuario Web. Los archivos *. Razor* definen los componentes que componen la interfaz de usuario de la aplicación. En la mayoría de los casos, los componentes son idénticos para las aplicaciones de servidor y de webassembler increíblemente. Los componentes de extraordinariamente son análogos a los controles de usuario de formularios Web Forms de ASP.NET.

Cada archivo de componente de Razor se compila en una clase .NET cuando se compila el proyecto. La clase generada captura el estado del componente, la lógica de representación, los métodos de ciclo de vida, los controladores de eventos y otra lógica. Veremos la creación de componentes en la sección [creación de componentes de interfaz de usuario reutilizables con](./components.md) más increíble.

Los archivos *_Imports. Razor* no son archivos de componentes de Razor. En su lugar, definen un conjunto de directivas de Razor para importar en otros archivos *. Razor* dentro de la misma carpeta y en sus subcarpetas. Por ejemplo, un archivo *_Imports. Razor* es una manera convencional de agregar instrucciones de `using` para los espacios de nombres más usados:

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

¿Dónde están las páginas de las aplicaciones increíbles? El increíble no define una extensión de archivo independiente para las páginas direccionables, como los archivos *. aspx* de las aplicaciones de formularios Web Forms de ASP.net. En su lugar, las páginas se definen asignando rutas a los componentes. Normalmente, una ruta se asigna mediante la Directiva de Razor `@page`. Por ejemplo, el componente `Counter` creado en el archivo *pages/Counter. Razor* define la ruta siguiente:

```razor
@page "/counter"
```

El enrutamiento en increíblemente se controla en el lado cliente, no en el servidor. A medida que el usuario navega en el explorador, increíble intercepta la navegación y, a continuación, representa el componente con la ruta coincidente.

Las rutas del componente no se deducen actualmente por la ubicación del archivo del componente, como sucede con las páginas *. aspx* . Esta característica se puede Agregar en el futuro. Cada ruta debe especificarse explícitamente en el componente. El almacenamiento de componentes enrutables en una carpeta *pages* no tiene ningún significado especial y es meramente una Convención.

En la sección [páginas, enrutamiento y diseños](./pages-routing-layouts.md) veremos más detalladamente el enrutamiento en el nivel de detalle.

## <a name="layout"></a>Diseño

En las aplicaciones de formularios Web Forms de ASP.NET, el diseño de página común se controla mediante páginas maestras (*site. Master*). En las aplicaciones increíbles, el diseño de página se controla mediante componentes de diseño (*Shared/MainLayout. Razor*). Los componentes de diseño se tratarán con más detalle en la sección [página, enrutamiento y diseños](./pages-routing-layouts.md) .

## <a name="bootstrap-blazor"></a>Arranque rápido

Para arrancar increíble, la aplicación debe:

- Especifique en qué lugar de la página se debe representar el componente raíz (*app. Razor*).
- Agregue el correspondiente script del marco de trabajo.

En la aplicación de servidor de extraordinarias, la página host del componente raíz se define en el archivo *_Host. cshtml* . Este archivo define una página de Razor, no un componente. Razor Pages usar sintaxis Razor para definir una página direccionable por el servidor, de forma muy parecida a una página *. aspx* . El método `Html.RenderComponentAsync<TComponent>(RenderMode)` se utiliza para definir dónde se debe representar un componente de nivel de raíz. La opción `RenderMode` indica la manera en que se debe representar el componente. En la tabla siguiente se describen las opciones de `RenderMode` admitidas.

|Opción                        |Descripción       |
|------------------------------|------------------|
|`RenderMode.Server`           |Se representa de forma interactiva una vez que se establece una conexión con el explorador|
|`RenderMode.ServerPrerendered`|Primer prerepresentado y después representado de forma interactiva|
|`RenderMode.Static`           |Se representa como contenido estático|

La referencia de script a *_framework/blazor.Server.js* establece la conexión en tiempo real con el servidor y, a continuación, trata todas las interacciones del usuario y las actualizaciones de la interfaz de usuario.

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

En la aplicación increíblemente webassembly, la página host es un simple archivo HTML estático en *wwwroot/index.html*. El elemento `<app>` se utiliza para indicar dónde se debe representar el componente raíz.

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

El componente específico que se va a representar se configura en el método de `Startup.Configure` de la aplicación con un selector de CSS correspondiente que indica dónde se debe representar el componente.

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

Cuando se crea un proyecto increíblemente brillante, todos los archivos de código y componentes de Razor se compilan en un único ensamblado. A diferencia de los proyectos de formularios Web Forms de ASP.NET, increíble no admite la compilación en tiempo de ejecución de la lógica de la interfaz de usuario.

## <a name="run-the-app"></a>Ejecución la aplicación

Para ejecutar la aplicación de servidor de extraordinarias, presione `F5` en Visual Studio. Las aplicaciones increíbles no admiten la compilación en tiempo de ejecución. Para ver los resultados de los cambios de código y marcado de componentes, vuelva a compilar y reiniciar la aplicación con el depurador asociado. Si ejecuta sin el depurador asociado (`Ctrl+F5`), Visual Studio inspecciona los cambios de archivo y reinicia la aplicación a medida que se realizan cambios. Actualice manualmente el explorador a medida que se realicen cambios.

Para ejecutar la aplicación increíblemente webassembly, elija uno de los siguientes enfoques:

- Ejecute el proyecto de cliente directamente mediante el servidor de desarrollo.
- Ejecute el proyecto de servidor al hospedar la aplicación con ASP.NET Core.

Las aplicaciones de webassembly increíbles no admiten la depuración con Visual Studio. Para ejecutar la aplicación, use `Ctrl+F5` en lugar de `F5`. En su lugar, puede depurar aplicaciones webassembly increíblemente directamente en el explorador. Consulte [depuración de ASP.net Core extraordinarias](/aspnet/core/blazor/debug) para obtener más información.

>[!div class="step-by-step"]
>[Anterior](hosting-models.md)
>[Siguiente](app-startup.md)
