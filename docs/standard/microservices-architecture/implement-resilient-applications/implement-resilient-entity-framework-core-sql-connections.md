---
title: Implementación de conexiones SQL resistentes de Entity Framework Core
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedores | Implementación de conexiones SQL resistentes de Entity Framework Core. Esta técnica es especialmente importante cuando se usa Azure SQL Database en la nube.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 06/08/2018
ms.openlocfilehash: 59db9cdb894f76f54e77732be47dc6140a594121
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2018
ms.locfileid: "44192449"
---
# <a name="implement-resilient-entity-framework-core-sql-connections"></a><span data-ttu-id="43e3d-104">Implementación de conexiones SQL resistentes de Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="43e3d-104">Implement resilient Entity Framework Core SQL connections</span></span>

<span data-ttu-id="43e3d-105">Para Azure SQL DB, Entity Framework Core ya proporciona la lógica de reintento y resistencia de conexión de base de datos interna.</span><span class="sxs-lookup"><span data-stu-id="43e3d-105">For Azure SQL DB, Entity Framework Core already provides internal database connection resiliency and retry logic.</span></span> <span data-ttu-id="43e3d-106">Pero debe habilitar la estrategia de ejecución de Entity Framework para cada conexión de DbContext si quiere tener [conexiones resistentes de EF Core](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency).</span><span class="sxs-lookup"><span data-stu-id="43e3d-106">But you need to enable the Entity Framework execution strategy for each DbContext connection if you want to have [resilient EF Core connections](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency).</span></span>

<span data-ttu-id="43e3d-107">Por ejemplo, el código siguiente en el nivel de conexión de EF Core permite conexiones resistentes de SQL que se vuelven a intentar si se produce un error en la conexión.</span><span class="sxs-lookup"><span data-stu-id="43e3d-107">For instance, the following code at the EF Core connection level enables resilient SQL connections that are retried if the connection fails.</span></span>

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

## <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a><span data-ttu-id="43e3d-108">Estrategias de ejecución y transacciones explícitas mediante BeginTransaction y varios DbContexts</span><span class="sxs-lookup"><span data-stu-id="43e3d-108">Execution strategies and explicit transactions using BeginTransaction and multiple DbContexts</span></span>

<span data-ttu-id="43e3d-109">Cuando se habilitan los reintentos en las conexiones de EF Core, cada operación que se realiza mediante EF Core se convierte en su propia operación que se puede reintentar.</span><span class="sxs-lookup"><span data-stu-id="43e3d-109">When retries are enabled in EF Core connections, each operation you perform using EF Core becomes its own retryable operation.</span></span> <span data-ttu-id="43e3d-110">Cada consulta y cada llamada a SaveChanges se reintentará como una unidad si se produce un error transitorio.</span><span class="sxs-lookup"><span data-stu-id="43e3d-110">Each query and each call to SaveChanges will be retried as a unit if a transient failure occurs.</span></span>

<span data-ttu-id="43e3d-111">Sin embargo, si el código inicia una transacción con BeginTransaction, va a definir su propio grupo de operaciones que se deben tratar como una unidad: todo dentro de la transacción se debe revertir si se produce un error.</span><span class="sxs-lookup"><span data-stu-id="43e3d-111">However, if your code initiates a transaction using BeginTransaction, you are defining your own group of operations that need to be treated as a unit—everything inside the transaction has be rolled back if a failure occurs.</span></span> <span data-ttu-id="43e3d-112">Verá una excepción similar a la siguiente si intenta ejecutar esa transacción cuando usa una estrategia de ejecución de EF (directiva de reintentos) e incluye varias llamadas de SaveChanges desde varios DbContexts en la transacción.</span><span class="sxs-lookup"><span data-stu-id="43e3d-112">You will see an exception like the following if you attempt to execute that transaction when using an EF execution strategy (retry policy) and you include several SaveChanges calls from multiple DbContexts in the transaction.</span></span>

> <span data-ttu-id="43e3d-113">System.InvalidOperationException: la estrategia de ejecución configurada "SqlServerRetryingExecutionStrategy" no es compatible con las transacciones que el usuario inicie.</span><span class="sxs-lookup"><span data-stu-id="43e3d-113">System.InvalidOperationException: The configured execution strategy 'SqlServerRetryingExecutionStrategy' does not support user initiated transactions.</span></span> <span data-ttu-id="43e3d-114">Use la estrategia de ejecución que devuelve "DbContext.Database.CreateExecutionStrategy()" para ejecutar todas las operaciones en la transacción como una unidad que se puede reintentar.</span><span class="sxs-lookup"><span data-stu-id="43e3d-114">Use the execution strategy returned by 'DbContext.Database.CreateExecutionStrategy()' to execute all the operations in the transaction as a retriable unit.</span></span>

<span data-ttu-id="43e3d-115">La solución consiste en invocar manualmente la estrategia de ejecución de EF con un delegado que representa a todos los elementos que se deben ejecutar.</span><span class="sxs-lookup"><span data-stu-id="43e3d-115">The solution is to manually invoke the EF execution strategy with a delegate representing everything that needs to be executed.</span></span> <span data-ttu-id="43e3d-116">Si se produce un error transitorio, la estrategia de ejecución vuelve a invocar al delegado.</span><span class="sxs-lookup"><span data-stu-id="43e3d-116">If a transient failure occurs, the execution strategy will invoke the delegate again.</span></span> <span data-ttu-id="43e3d-117">Por ejemplo, el código siguiente muestra cómo se implementa en eShopOnContainers con dos DbContexts múltiples (\_catalogContext y el IntegrationEventLogContext) al actualizar un producto y, después, guardar el objeto ProductPriceChangedIntegrationEvent, que debe usar un DbContext diferente.</span><span class="sxs-lookup"><span data-stu-id="43e3d-117">For example, the following code show how it is implemented in eShopOnContainers with two multiple DbContexts (\_catalogContext and the IntegrationEventLogContext) when updating a product and then saving the ProductPriceChangedIntegrationEvent object, which needs to use a different DbContext.</span></span>

```csharp
public async Task<IActionResult> UpdateProduct([FromBody]CatalogItem
    productToUpdate)
{
    // Other code ...
    // Update current product
    catalogItem = productToUpdate;

    // Use of an EF Core resiliency strategy when using multiple DbContexts
    // within an explicit transaction
    // See:
    // https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency
    var strategy = _catalogContext.Database.CreateExecutionStrategy();
    await strategy.ExecuteAsync(async () =>
    {
        // Achieving atomicity between original Catalog database operation and the
        // IntegrationEventLog thanks to a local transaction
        using (var transaction = _catalogContext.Database.BeginTransaction())
        {
            _catalogContext.CatalogItems.Update(catalogItem);
            await _catalogContext.SaveChangesAsync();
            // Save to EventLog only if product price changed
            if (raiseProductPriceChangedEvent)
            await _integrationEventLogService.SaveEventAsync(priceChangedEvent);
            transaction.Commit();
        }
    });
}
```

<span data-ttu-id="43e3d-118">El primer DbContext es \_catalogContext y el segundo DbContext está dentro del objeto \_integrationEventLogService.</span><span class="sxs-lookup"><span data-stu-id="43e3d-118">The first DbContext is \_catalogContext and the second DbContext is within the \_integrationEventLogService object.</span></span> <span data-ttu-id="43e3d-119">La acción Commit se realiza a través de varios DbContexts mediante una estrategia de ejecución de EF.</span><span class="sxs-lookup"><span data-stu-id="43e3d-119">The Commit action is performed across multiple DbContexts using an EF execution strategy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="43e3d-120">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="43e3d-120">Additional resources</span></span>

-   <span data-ttu-id="43e3d-121">**EF Connection Resiliency** (Entity Framework Core) (Resistencia de las conexiones de EF [Entity Framework Core])[*https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)</span><span class="sxs-lookup"><span data-stu-id="43e3d-121">**EF Connection Resiliency** (Entity Framework Core) [*https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)</span></span>

-   <span data-ttu-id="43e3d-122">**Connection Resiliency and Command Interception with the Entity Framework (Resistencia de la conexión e intercepción de comandos con Entity Framework)**
    [*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)</span><span class="sxs-lookup"><span data-stu-id="43e3d-122">**Connection Resiliency and Command Interception with the Entity Framework**
[*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)</span></span>

-   <span data-ttu-id="43e3d-123">**Cesar de la Torre. Using Resilient Entity Framework Core Sql Connections and Transactions (Usar conexiones y transacciones SQL resistentes de Entity Framework Core)**
    <https://blogs.msdn.microsoft.com/cesardelatorre/2017/03/26/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/></span><span class="sxs-lookup"><span data-stu-id="43e3d-123">**Cesar de la Torre. Using Resilient Entity Framework Core Sql Connections and Transactions**
<https://blogs.msdn.microsoft.com/cesardelatorre/2017/03/26/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/></span></span>

>[!div class="step-by-step"]
<span data-ttu-id="43e3d-124">[Anterior](implement-retries-exponential-backoff.md)
[Siguiente](explore-custom-http-call-retries-exponential-backoff.md)</span><span class="sxs-lookup"><span data-stu-id="43e3d-124">[Previous](implement-retries-exponential-backoff.md)
[Next](explore-custom-http-call-retries-exponential-backoff.md)</span></span>
