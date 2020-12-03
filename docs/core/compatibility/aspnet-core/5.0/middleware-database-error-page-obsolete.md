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
# <a name="middleware-database-error-page-marked-as-obsolete"></a><span data-ttu-id="6e6ad-103">Middleware: página de errores de la base de datos marcada como obsoleta</span><span class="sxs-lookup"><span data-stu-id="6e6ad-103">Middleware: Database error page marked as obsolete</span></span>

<span data-ttu-id="6e6ad-104">[DatabaseErrorPageMiddleware](/dotnet/api/microsoft.aspnetcore.diagnostics.entityframeworkcore.databaseerrorpagemiddleware?view=aspnetcore-3.0) y los métodos de extensión asociados se han marcado como obsoletos en ASP.NET Core 5.0.</span><span class="sxs-lookup"><span data-stu-id="6e6ad-104">The [DatabaseErrorPageMiddleware](/dotnet/api/microsoft.aspnetcore.diagnostics.entityframeworkcore.databaseerrorpagemiddleware?view=aspnetcore-3.0) and its associated extension methods were marked as obsolete in ASP.NET Core 5.0.</span></span> <span data-ttu-id="6e6ad-105">El middleware y los métodos de extensión se quitarán en ASP.NET Core 6.0.</span><span class="sxs-lookup"><span data-stu-id="6e6ad-105">The middleware and extension methods will be removed in ASP.NET Core 6.0.</span></span> <span data-ttu-id="6e6ad-106">En su lugar, `DatabaseDeveloperPageExceptionFilter` y sus métodos de extensión proporcionarán la funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="6e6ad-106">The functionality will instead be provided by `DatabaseDeveloperPageExceptionFilter` and its extension methods.</span></span>

<span data-ttu-id="6e6ad-107">Para obtener información, consulte la incidencia de GitHub [dotnet/aspnetcore#24987](https://github.com/dotnet/aspnetcore/issues/24987).</span><span class="sxs-lookup"><span data-stu-id="6e6ad-107">For discussion, see the GitHub issue at [dotnet/aspnetcore#24987](https://github.com/dotnet/aspnetcore/issues/24987).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="6e6ad-108">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="6e6ad-108">Version introduced</span></span>

<span data-ttu-id="6e6ad-109">5.0 RC 1</span><span class="sxs-lookup"><span data-stu-id="6e6ad-109">5.0 RC 1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="6e6ad-110">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="6e6ad-110">Old behavior</span></span>

<span data-ttu-id="6e6ad-111">`DatabaseErrorPageMiddleware` y sus métodos de extensión asociados no estaban obsoletos.</span><span class="sxs-lookup"><span data-stu-id="6e6ad-111">`DatabaseErrorPageMiddleware` and its associated extension methods weren't obsolete.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="6e6ad-112">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="6e6ad-112">New behavior</span></span>

<span data-ttu-id="6e6ad-113">`DatabaseErrorPageMiddleware` y sus métodos de extensión asociados están obsoletos.</span><span class="sxs-lookup"><span data-stu-id="6e6ad-113">`DatabaseErrorPageMiddleware` and its associated extension methods are obsolete.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="6e6ad-114">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="6e6ad-114">Reason for change</span></span>

<span data-ttu-id="6e6ad-115">`DatabaseErrorPageMiddleware` se migró a una API extensible para la [página de excepciones para el desarrollador](/aspnet/core/fundamentals/error-handling#developer-exception-page).</span><span class="sxs-lookup"><span data-stu-id="6e6ad-115">`DatabaseErrorPageMiddleware` was migrated to an extensible API for the [developer exception page](/aspnet/core/fundamentals/error-handling#developer-exception-page).</span></span> <span data-ttu-id="6e6ad-116">Para obtener más información sobre la API extensible, vea la incidencia de GitHub [dotnet/aspnetcore#8536](https://github.com/dotnet/aspnetcore/issues/8536).</span><span class="sxs-lookup"><span data-stu-id="6e6ad-116">For more information on the extensible API, see GitHub issue [dotnet/aspnetcore#8536](https://github.com/dotnet/aspnetcore/issues/8536).</span></span>

## <a name="recommended-action"></a><span data-ttu-id="6e6ad-117">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="6e6ad-117">Recommended action</span></span>

<span data-ttu-id="6e6ad-118">Siga los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6e6ad-118">Complete the following steps:</span></span>

1. <span data-ttu-id="6e6ad-119">Deje de usar `DatabaseErrorPageMiddleware` en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="6e6ad-119">Stop using `DatabaseErrorPageMiddleware` in your project.</span></span> <span data-ttu-id="6e6ad-120">Por ejemplo, quite la llamada al método `UseDatabaseErrorPage` de `Startup.Configure`:</span><span class="sxs-lookup"><span data-stu-id="6e6ad-120">For example, remove the `UseDatabaseErrorPage` method call from `Startup.Configure`:</span></span>

    ```csharp
    public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
    {
        if (env.IsDevelopment())
        {
            app.UseDatabaseErrorPage();
        }
    }
    ```

1. <span data-ttu-id="6e6ad-121">Agregue la página de excepciones para el desarrollador al proyecto.</span><span class="sxs-lookup"><span data-stu-id="6e6ad-121">Add the developer exception page to your project.</span></span> <span data-ttu-id="6e6ad-122">Por ejemplo, llame al método <xref:Microsoft.AspNetCore.Builder.DeveloperExceptionPageExtensions.UseDeveloperExceptionPage%2A> en `Startup.Configure`:</span><span class="sxs-lookup"><span data-stu-id="6e6ad-122">For example, call the <xref:Microsoft.AspNetCore.Builder.DeveloperExceptionPageExtensions.UseDeveloperExceptionPage%2A> method in `Startup.Configure`:</span></span>

    ```csharp
    public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
    {
        if (env.IsDevelopment())
        {
            app.UseDeveloperExceptionPage();
        }
    }
    ```

1. <span data-ttu-id="6e6ad-123">Agregue el paquete NuGet [Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore](https://www.nuget.org/packages/Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore) al archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="6e6ad-123">Add the [Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore](https://www.nuget.org/packages/Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore) NuGet package to the project file.</span></span>

1. <span data-ttu-id="6e6ad-124">Agregue el filtro de excepción de la página del desarrollador de bases de datos a la colección de servicios.</span><span class="sxs-lookup"><span data-stu-id="6e6ad-124">Add the database developer page exception filter to the services collection.</span></span> <span data-ttu-id="6e6ad-125">Por ejemplo, llame al método `AddDatabaseDeveloperPageExceptionFilter` en `Startup.ConfigureServices`:</span><span class="sxs-lookup"><span data-stu-id="6e6ad-125">For example, call the `AddDatabaseDeveloperPageExceptionFilter` method in `Startup.ConfigureServices`:</span></span>

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddDatabaseDeveloperPageExceptionFilter();
    }
    ```

## <a name="affected-apis"></a><span data-ttu-id="6e6ad-126">API afectadas</span><span class="sxs-lookup"><span data-stu-id="6e6ad-126">Affected APIs</span></span>

- [<span data-ttu-id="6e6ad-127">Microsoft.AspNetCore.Builder.DatabaseErrorPageExtensions.UseDatabaseErrorPage</span><span class="sxs-lookup"><span data-stu-id="6e6ad-127">Microsoft.AspNetCore.Builder.DatabaseErrorPageExtensions.UseDatabaseErrorPage</span></span>](/dotnet/api/microsoft.aspnetcore.builder.databaseerrorpageextensions.usedatabaseerrorpage?view=aspnetcore-3.0)
- [<span data-ttu-id="6e6ad-128">Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore.DatabaseErrorPageMiddleware</span><span class="sxs-lookup"><span data-stu-id="6e6ad-128">Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore.DatabaseErrorPageMiddleware</span></span>](/dotnet/api/microsoft.aspnetcore.diagnostics.entityframeworkcore.databaseerrorpagemiddleware?view=aspnetcore-3.0)

<!--

### Category

ASP.NET Core

### Affected APIs

- `Overload:Microsoft.AspNetCore.Builder.DatabaseErrorPageExtensions.UseDatabaseErrorPage`
- `T:Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore.DatabaseErrorPageMiddleware`

-->
