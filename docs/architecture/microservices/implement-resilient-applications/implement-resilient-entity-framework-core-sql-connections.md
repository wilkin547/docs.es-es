---
title: Implementación de conexiones SQL resistentes de Entity Framework Core
description: Aprenda a implementar conexiones SQL resistentes de Entity Framework Core. Esta técnica es especialmente importante cuando se usa Azure SQL Database en la nube.
ms.date: 10/16/2018
ms.openlocfilehash: cae3550ce301750949b042957d5d10f0167e614c
ms.sourcegitcommit: 88fbb019b84c2d044d11fb4f6004aec07f2b25b1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "97899566"
---
# <a name="implement-resilient-entity-framework-core-sql-connections"></a><span data-ttu-id="fb7ef-104">Implementación de conexiones SQL resistentes de Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="fb7ef-104">Implement resilient Entity Framework Core SQL connections</span></span>

<span data-ttu-id="fb7ef-105">Para Azure SQL DB, Entity Framework (EF) Core ya proporciona la lógica de reintento y resistencia de conexión de base de datos interna.</span><span class="sxs-lookup"><span data-stu-id="fb7ef-105">For Azure SQL DB, Entity Framework (EF) Core already provides internal database connection resiliency and retry logic.</span></span> <span data-ttu-id="fb7ef-106">Pero debe habilitar la estrategia de ejecución de Entity Framework para cada conexión de <xref:Microsoft.EntityFrameworkCore.DbContext> si quiere tener [conexiones resistentes de EF Core](/ef/core/miscellaneous/connection-resiliency).</span><span class="sxs-lookup"><span data-stu-id="fb7ef-106">But you need to enable the Entity Framework execution strategy for each <xref:Microsoft.EntityFrameworkCore.DbContext> connection if you want to have [resilient EF Core connections](/ef/core/miscellaneous/connection-resiliency).</span></span>

<span data-ttu-id="fb7ef-107">Por ejemplo, el código siguiente en el nivel de conexión de EF Core permite conexiones resistentes de SQL que se vuelven a intentar si se produce un error en la conexión.</span><span class="sxs-lookup"><span data-stu-id="fb7ef-107">For instance, the following code at the EF Core connection level enables resilient SQL connections that are retried if the connection fails.</span></span>

```csharp
// Startup.cs from any ASP.NET Core Web API
public class Startup
{
    // Other code ...
    public IServiceProvider ConfigureServices(IServiceCollection services)
    {
        // ...
        services.AddDbContext<CatalogContext>(options =>
        {
            options.UseSqlServer(Configuration["ConnectionString"],
            sqlServerOptionsAction: sqlOptions =>
            {
                sqlOptions.EnableRetryOnFailure(
                maxRetryCount: 10,
                maxRetryDelay: TimeSpan.FromSeconds(30),
                errorNumbersToAdd: null);
            });
        });
    }
//...
}
```

## <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a><span data-ttu-id="fb7ef-108">Estrategias de ejecución y transacciones explícitas mediante BeginTransaction y varios DbContexts</span><span class="sxs-lookup"><span data-stu-id="fb7ef-108">Execution strategies and explicit transactions using BeginTransaction and multiple DbContexts</span></span>

<span data-ttu-id="fb7ef-109">Cuando se habilitan los reintentos en las conexiones de EF Core, cada operación que se realiza mediante EF Core se convierte en su propia operación que se puede reintentar.</span><span class="sxs-lookup"><span data-stu-id="fb7ef-109">When retries are enabled in EF Core connections, each operation you perform using EF Core becomes its own retryable operation.</span></span> <span data-ttu-id="fb7ef-110">Cada consulta y cada llamada a `SaveChanges` se reintentará como una unidad si se produce un error transitorio.</span><span class="sxs-lookup"><span data-stu-id="fb7ef-110">Each query and each call to `SaveChanges` will be retried as a unit if a transient failure occurs.</span></span>

<span data-ttu-id="fb7ef-111">Sin embargo, si su código inicia una transición con `BeginTransaction`, define su propio grupo de operaciones que deben tratarse como unidad.</span><span class="sxs-lookup"><span data-stu-id="fb7ef-111">However, if your code initiates a transaction using `BeginTransaction`, you're defining your own group of operations that need to be treated as a unit.</span></span> <span data-ttu-id="fb7ef-112">Todo el contenido de la transacción debe revertirse si se produce un error.</span><span class="sxs-lookup"><span data-stu-id="fb7ef-112">Everything inside the transaction has to be rolled back if a failure occurs.</span></span>

<span data-ttu-id="fb7ef-113">Si intenta ejecutar esa transacción cuando se usa una estrategia de ejecución de EF (directiva de reintentos) y llama a `SaveChanges` de varios DbContext, obtendrá una excepción como esta:</span><span class="sxs-lookup"><span data-stu-id="fb7ef-113">If you try to execute that transaction when using an EF execution strategy (retry policy) and you call `SaveChanges` from multiple DbContexts, you'll get an exception like this one:</span></span>

> <span data-ttu-id="fb7ef-114">System.InvalidOperationException: la estrategia de ejecución configurada "SqlServerRetryingExecutionStrategy" no es compatible con las transacciones que el usuario inicie.</span><span class="sxs-lookup"><span data-stu-id="fb7ef-114">System.InvalidOperationException: The configured execution strategy 'SqlServerRetryingExecutionStrategy' does not support user initiated transactions.</span></span> <span data-ttu-id="fb7ef-115">Use la estrategia de ejecución que devuelve "DbContext.Database.CreateExecutionStrategy()" para ejecutar todas las operaciones en la transacción como una unidad que se puede reintentar.</span><span class="sxs-lookup"><span data-stu-id="fb7ef-115">Use the execution strategy returned by 'DbContext.Database.CreateExecutionStrategy()' to execute all the operations in the transaction as a retriable unit.</span></span>

<span data-ttu-id="fb7ef-116">La solución consiste en invocar manualmente la estrategia de ejecución de EF con un delegado que representa a todos los elementos que se deben ejecutar.</span><span class="sxs-lookup"><span data-stu-id="fb7ef-116">The solution is to manually invoke the EF execution strategy with a delegate representing everything that needs to be executed.</span></span> <span data-ttu-id="fb7ef-117">Si se produce un error transitorio, la estrategia de ejecución vuelve a invocar al delegado.</span><span class="sxs-lookup"><span data-stu-id="fb7ef-117">If a transient failure occurs, the execution strategy will invoke the delegate again.</span></span> <span data-ttu-id="fb7ef-118">Por ejemplo, el código siguiente muestra cómo se implementa en eShopOnContainers con dos DbContexts múltiples (\_catalogContext y el IntegrationEventLogContext) al actualizar un producto y, después, guardar el objeto ProductPriceChangedIntegrationEvent, que debe usar un DbContext diferente.</span><span class="sxs-lookup"><span data-stu-id="fb7ef-118">For example, the following code show how it's implemented in eShopOnContainers with two multiple DbContexts (\_catalogContext and the IntegrationEventLogContext) when updating a product and then saving the ProductPriceChangedIntegrationEvent object, which needs to use a different DbContext.</span></span>

```csharp
public async Task<IActionResult> UpdateProduct(
    [FromBody]CatalogItem productToUpdate)
{
    // Other code ...

    var oldPrice = catalogItem.Price;
    var raiseProductPriceChangedEvent = oldPrice != productToUpdate.Price;

    // Update current product
    catalogItem = productToUpdate;

    // Save product's data and publish integration event through the Event Bus
    // if price has changed
    if (raiseProductPriceChangedEvent)
    {
        //Create Integration Event to be published through the Event Bus
        var priceChangedEvent = new ProductPriceChangedIntegrationEvent(
          catalogItem.Id, productToUpdate.Price, oldPrice);

       // Achieving atomicity between original Catalog database operation and the
       // IntegrationEventLog thanks to a local transaction
       await _catalogIntegrationEventService.SaveEventAndCatalogContextChangesAsync(
           priceChangedEvent);

       // Publish through the Event Bus and mark the saved event as published
       await _catalogIntegrationEventService.PublishThroughEventBusAsync(
           priceChangedEvent);
    }
    // Just save the updated product because the Product's Price hasn't changed.
    else
    {
        await _catalogContext.SaveChangesAsync();
    }
}
```

<span data-ttu-id="fb7ef-119">El primer contexto <xref:Microsoft.EntityFrameworkCore.DbContext> es `_catalogContext` y el segundo contexto `DbContext` está dentro del objeto `_catalogIntegrationEventService`.</span><span class="sxs-lookup"><span data-stu-id="fb7ef-119">The first <xref:Microsoft.EntityFrameworkCore.DbContext> is `_catalogContext` and the second `DbContext` is within the `_catalogIntegrationEventService` object.</span></span> <span data-ttu-id="fb7ef-120">La acción Commit se realiza a través de todos los objetos `DbContext` mediante una estrategia de ejecución de EF.</span><span class="sxs-lookup"><span data-stu-id="fb7ef-120">The Commit action is performed across all `DbContext` objects using an EF execution strategy.</span></span>

<span data-ttu-id="fb7ef-121">Para lograr esta confirmación `DbContext` múltiple, el elemento `SaveEventAndCatalogContextChangesAsync` usa una clase `ResilientTransaction`, como se muestra en el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="fb7ef-121">To achieve this multiple `DbContext` commit, the `SaveEventAndCatalogContextChangesAsync` uses a `ResilientTransaction` class, as shown in the following code:</span></span>

```csharp
public class CatalogIntegrationEventService : ICatalogIntegrationEventService
{
    //…
    public async Task SaveEventAndCatalogContextChangesAsync(
        IntegrationEvent evt)
    {
        // Use of an EF Core resiliency strategy when using multiple DbContexts
        // within an explicit BeginTransaction():
        // https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency
        await ResilientTransaction.New(_catalogContext).ExecuteAsync(async () =>
        {
            // Achieving atomicity between original catalog database
            // operation and the IntegrationEventLog thanks to a local transaction
            await _catalogContext.SaveChangesAsync();
            await _eventLogService.SaveEventAsync(evt,
                _catalogContext.Database.CurrentTransaction.GetDbTransaction());
        });
    }
}
```

<span data-ttu-id="fb7ef-122">El método `ResilientTransaction.ExecuteAsync` básicamente comienza una transacción desde el contexto `DbContext` pasado (`_catalogContext`) y, a continuación, hace que el servicio `EventLogService` use dicha transacción para guardar los cambios del contexto `IntegrationEventLogContext` y, después, confirma toda la transacción.</span><span class="sxs-lookup"><span data-stu-id="fb7ef-122">The `ResilientTransaction.ExecuteAsync` method basically begins a transaction from the passed `DbContext` (`_catalogContext`) and then makes the `EventLogService` use that transaction to save changes from the `IntegrationEventLogContext` and then commits the whole transaction.</span></span>

```csharp
public class ResilientTransaction
{
    private DbContext _context;
    private ResilientTransaction(DbContext context) =>
        _context = context ?? throw new ArgumentNullException(nameof(context));

    public static ResilientTransaction New (DbContext context) =>
        new ResilientTransaction(context);

    public async Task ExecuteAsync(Func<Task> action)
    {
        // Use of an EF Core resiliency strategy when using multiple DbContexts
        // within an explicit BeginTransaction():
        // https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency
        var strategy = _context.Database.CreateExecutionStrategy();
        await strategy.ExecuteAsync(async () =>
        {
            await using var transaction = await _context.Database.BeginTransactionAsync();
            await action();
            await transaction.CommitAsync();
        });
    }
}
```

## <a name="additional-resources"></a><span data-ttu-id="fb7ef-123">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="fb7ef-123">Additional resources</span></span>

- <span data-ttu-id="fb7ef-124">**Connection Resiliency and Command Interception with EF in an ASP.NET MVC Application (Resistencia de la conexión e intercepción de comandos con EF en una aplicación de ASP.NET MVC)**  </span><span class="sxs-lookup"><span data-stu-id="fb7ef-124">**Connection Resiliency and Command Interception with EF in an ASP.NET MVC Application** </span></span>\
  [https://docs.microsoft.com/aspnet/mvc/overview/getting-started/getting-started-with-ef-using-mvc/connection-resiliency-and-command-interception-with-the-entity-framework-in-an-asp-net-mvc-application](/aspnet/mvc/overview/getting-started/getting-started-with-ef-using-mvc/connection-resiliency-and-command-interception-with-the-entity-framework-in-an-asp-net-mvc-application)

- <span data-ttu-id="fb7ef-125">**Cesar de la Torre. Using Resilient Entity Framework Core SQL Connections and Transactions (Usar conexiones y transacciones SQL resistentes de Entity Framework Core)**  </span><span class="sxs-lookup"><span data-stu-id="fb7ef-125">**Cesar de la Torre. Using Resilient Entity Framework Core SQL Connections and Transactions** </span></span>\
  <https://devblogs.microsoft.com/cesardelatorre/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/>

>[!div class="step-by-step"]
><span data-ttu-id="fb7ef-126">[Anterior](implement-retries-exponential-backoff.md)
>[Siguiente](use-httpclientfactory-to-implement-resilient-http-requests.md)</span><span class="sxs-lookup"><span data-stu-id="fb7ef-126">[Previous](implement-retries-exponential-backoff.md)
[Next](use-httpclientfactory-to-implement-resilient-http-requests.md)</span></span>
