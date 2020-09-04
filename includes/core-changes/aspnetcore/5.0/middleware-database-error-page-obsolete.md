---
ms.openlocfilehash: f1129500c9b779256b2650fe6fa855152cb3ae80
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811289"
---
### <a name="middleware-database-error-page-marked-as-obsolete"></a><span data-ttu-id="99dac-101">Middleware: página de errores de la base de datos marcada como obsoleta</span><span class="sxs-lookup"><span data-stu-id="99dac-101">Middleware: Database error page marked as obsolete</span></span>

<span data-ttu-id="99dac-102">[DatabaseErrorPageMiddleware](/dotnet/api/microsoft.aspnetcore.diagnostics.entityframeworkcore.databaseerrorpagemiddleware?view=aspnetcore-3.0) y los métodos de extensión asociados se han marcado como obsoletos en ASP.NET Core 5.0.</span><span class="sxs-lookup"><span data-stu-id="99dac-102">The [DatabaseErrorPageMiddleware](/dotnet/api/microsoft.aspnetcore.diagnostics.entityframeworkcore.databaseerrorpagemiddleware?view=aspnetcore-3.0) and its associated extension methods were marked as obsolete in ASP.NET Core 5.0.</span></span> <span data-ttu-id="99dac-103">El middleware y los métodos de extensión se quitarán en ASP.NET Core 6.0.</span><span class="sxs-lookup"><span data-stu-id="99dac-103">The middleware and extension methods will be removed in ASP.NET Core 6.0.</span></span> <span data-ttu-id="99dac-104">En su lugar, `DatabaseDeveloperPageExceptionFilter` y sus métodos de extensión proporcionarán la funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="99dac-104">The functionality will instead be provided by `DatabaseDeveloperPageExceptionFilter` and its extension methods.</span></span>

<span data-ttu-id="99dac-105">Para obtener información, consulte la incidencia de GitHub [dotnet/aspnetcore#24987](https://github.com/dotnet/aspnetcore/issues/24987).</span><span class="sxs-lookup"><span data-stu-id="99dac-105">For discussion, see the GitHub issue at [dotnet/aspnetcore#24987](https://github.com/dotnet/aspnetcore/issues/24987).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="99dac-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="99dac-106">Version introduced</span></span>

<span data-ttu-id="99dac-107">5.0 RC 1</span><span class="sxs-lookup"><span data-stu-id="99dac-107">5.0 RC 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="99dac-108">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="99dac-108">Old behavior</span></span>

<span data-ttu-id="99dac-109">`DatabaseErrorPageMiddleware` y sus métodos de extensión asociados no estaban obsoletos.</span><span class="sxs-lookup"><span data-stu-id="99dac-109">`DatabaseErrorPageMiddleware` and its associated extension methods weren't obsolete.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="99dac-110">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="99dac-110">New behavior</span></span>

<span data-ttu-id="99dac-111">`DatabaseErrorPageMiddleware` y sus métodos de extensión asociados están obsoletos.</span><span class="sxs-lookup"><span data-stu-id="99dac-111">`DatabaseErrorPageMiddleware` and its associated extension methods are obsolete.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="99dac-112">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="99dac-112">Reason for change</span></span>

<span data-ttu-id="99dac-113">`DatabaseErrorPageMiddleware` se migró a una API extensible para la [página de excepciones para el desarrollador](/aspnet/core/fundamentals/error-handling#developer-exception-page).</span><span class="sxs-lookup"><span data-stu-id="99dac-113">`DatabaseErrorPageMiddleware` was migrated to an extensible API for the [developer exception page](/aspnet/core/fundamentals/error-handling#developer-exception-page).</span></span> <span data-ttu-id="99dac-114">Para obtener más información sobre la API extensible, vea la incidencia de GitHub [dotnet/aspnetcore#8536](https://github.com/dotnet/aspnetcore/issues/8536).</span><span class="sxs-lookup"><span data-stu-id="99dac-114">For more information on the extensible API, see GitHub issue [dotnet/aspnetcore#8536](https://github.com/dotnet/aspnetcore/issues/8536).</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="99dac-115">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="99dac-115">Recommended action</span></span>

<span data-ttu-id="99dac-116">Siga los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="99dac-116">Complete the following steps:</span></span>

1. <span data-ttu-id="99dac-117">Deje de usar `DatabaseErrorPageMiddleware` en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="99dac-117">Stop using `DatabaseErrorPageMiddleware` in your project.</span></span> <span data-ttu-id="99dac-118">Por ejemplo, quite la llamada al método `UseDatabaseErrorPage` de `Startup.Configure`:</span><span class="sxs-lookup"><span data-stu-id="99dac-118">For example, remove the `UseDatabaseErrorPage` method call from `Startup.Configure`:</span></span>

    ```csharp
    public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
    {
        if (env.IsDevelopment())
        {
            app.UseDatabaseErrorPage();
        }
    }
    ```

1. <span data-ttu-id="99dac-119">Agregue la página de excepciones para el desarrollador al proyecto.</span><span class="sxs-lookup"><span data-stu-id="99dac-119">Add the developer exception page to your project.</span></span> <span data-ttu-id="99dac-120">Por ejemplo, llame al método <xref:Microsoft.AspNetCore.Builder.DeveloperExceptionPageExtensions.UseDeveloperExceptionPage%2A> en `Startup.Configure`:</span><span class="sxs-lookup"><span data-stu-id="99dac-120">For example, call the <xref:Microsoft.AspNetCore.Builder.DeveloperExceptionPageExtensions.UseDeveloperExceptionPage%2A> method in `Startup.Configure`:</span></span>

    ```csharp
    public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
    {
        if (env.IsDevelopment())
        {
            app.UseDeveloperExceptionPage();
        }
    }
    ```

1. <span data-ttu-id="99dac-121">Agregue el filtro de excepción de la página del desarrollador de bases de datos a la colección de servicios.</span><span class="sxs-lookup"><span data-stu-id="99dac-121">Add the database developer page exception filter to the services collection.</span></span> <span data-ttu-id="99dac-122">Por ejemplo, llame al método `AddDatabaseDeveloperPageExceptionFilter` en `Startup.ConfigureServices`:</span><span class="sxs-lookup"><span data-stu-id="99dac-122">For example, call the `AddDatabaseDeveloperPageExceptionFilter` method in `Startup.ConfigureServices`:</span></span>

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddDatabaseDeveloperPageExceptionFilter();
    }
    ```

#### <a name="category"></a><span data-ttu-id="99dac-123">Categoría</span><span class="sxs-lookup"><span data-stu-id="99dac-123">Category</span></span>

<span data-ttu-id="99dac-124">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="99dac-124">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="99dac-125">API afectadas</span><span class="sxs-lookup"><span data-stu-id="99dac-125">Affected APIs</span></span>

- [<span data-ttu-id="99dac-126">Microsoft.AspNetCore.Builder.DatabaseErrorPageExtensions.UseDatabaseErrorPage</span><span class="sxs-lookup"><span data-stu-id="99dac-126">Microsoft.AspNetCore.Builder.DatabaseErrorPageExtensions.UseDatabaseErrorPage</span></span>](/dotnet/api/microsoft.aspnetcore.builder.databaseerrorpageextensions.usedatabaseerrorpage?view=aspnetcore-3.0)
- [<span data-ttu-id="99dac-127">Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore.DatabaseErrorPageMiddleware</span><span class="sxs-lookup"><span data-stu-id="99dac-127">Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore.DatabaseErrorPageMiddleware</span></span>](/dotnet/api/microsoft.aspnetcore.diagnostics.entityframeworkcore.databaseerrorpagemiddleware?view=aspnetcore-3.0)

<!-- 

#### Affected APIs

- `Overload:Microsoft.AspNetCore.Builder.DatabaseErrorPageExtensions.UseDatabaseErrorPage`
- `T:Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore.DatabaseErrorPageMiddleware`

-->
