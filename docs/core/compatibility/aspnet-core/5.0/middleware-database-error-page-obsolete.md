---
title: 'Cambio importante: Middleware: página de errores de la base de datos marcada como obsoleta'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado Middleware: página de errores de la base de datos marcada como obsoleta'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: f828b5e20c2a9a709d675e435caa99727aebd5b6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760225"
---
# <a name="middleware-database-error-page-marked-as-obsolete"></a>Middleware: página de errores de la base de datos marcada como obsoleta

[DatabaseErrorPageMiddleware](/dotnet/api/microsoft.aspnetcore.diagnostics.entityframeworkcore.databaseerrorpagemiddleware?view=aspnetcore-3.0) y los métodos de extensión asociados se han marcado como obsoletos en ASP.NET Core 5.0. El middleware y los métodos de extensión se quitarán en ASP.NET Core 6.0. En su lugar, `DatabaseDeveloperPageExceptionFilter` y sus métodos de extensión proporcionarán la funcionalidad.

Para obtener información, consulte la incidencia de GitHub [dotnet/aspnetcore#24987](https://github.com/dotnet/aspnetcore/issues/24987).

## <a name="version-introduced"></a>Versión introducida

5.0 RC 1

## <a name="old-behavior"></a>Comportamiento anterior

`DatabaseErrorPageMiddleware` y sus métodos de extensión asociados no estaban obsoletos.

## <a name="new-behavior"></a>Comportamiento nuevo

`DatabaseErrorPageMiddleware` y sus métodos de extensión asociados están obsoletos.

## <a name="reason-for-change"></a>Motivo del cambio

`DatabaseErrorPageMiddleware` se migró a una API extensible para la [página de excepciones para el desarrollador](/aspnet/core/fundamentals/error-handling#developer-exception-page). Para obtener más información sobre la API extensible, vea la incidencia de GitHub [dotnet/aspnetcore#8536](https://github.com/dotnet/aspnetcore/issues/8536).

## <a name="recommended-action"></a>Acción recomendada

Siga los pasos siguientes:

1. Deje de usar `DatabaseErrorPageMiddleware` en el proyecto. Por ejemplo, quite la llamada al método `UseDatabaseErrorPage` de `Startup.Configure`:

    ```csharp
    public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
    {
        if (env.IsDevelopment())
        {
            app.UseDatabaseErrorPage();
        }
    }
    ```

1. Agregue la página de excepciones para el desarrollador al proyecto. Por ejemplo, llame al método <xref:Microsoft.AspNetCore.Builder.DeveloperExceptionPageExtensions.UseDeveloperExceptionPage%2A> en `Startup.Configure`:

    ```csharp
    public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
    {
        if (env.IsDevelopment())
        {
            app.UseDeveloperExceptionPage();
        }
    }
    ```

1. Agregue el paquete NuGet [Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore](https://www.nuget.org/packages/Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore) al archivo de proyecto.

1. Agregue el filtro de excepción de la página del desarrollador de bases de datos a la colección de servicios. Por ejemplo, llame al método `AddDatabaseDeveloperPageExceptionFilter` en `Startup.ConfigureServices`:

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddDatabaseDeveloperPageExceptionFilter();
    }
    ```

## <a name="affected-apis"></a>API afectadas

- [Microsoft.AspNetCore.Builder.DatabaseErrorPageExtensions.UseDatabaseErrorPage](/dotnet/api/microsoft.aspnetcore.builder.databaseerrorpageextensions.usedatabaseerrorpage?view=aspnetcore-3.0)
- [Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore.DatabaseErrorPageMiddleware](/dotnet/api/microsoft.aspnetcore.diagnostics.entityframeworkcore.databaseerrorpagemiddleware?view=aspnetcore-3.0)

<!--

### Category

ASP.NET Core

### Affected APIs

- `Overload:Microsoft.AspNetCore.Builder.DatabaseErrorPageExtensions.UseDatabaseErrorPage`
- `T:Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore.DatabaseErrorPageMiddleware`

-->
