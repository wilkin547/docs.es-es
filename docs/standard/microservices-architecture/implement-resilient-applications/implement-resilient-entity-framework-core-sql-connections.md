---
title: Implementar conexiones de Entity Framework Core SQL resistentes
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Implementar conexiones de Entity Framework Core SQL resistentes
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 8600625c2022d69ebaa2645c2a8159a848b12ff0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-resilient-entity-framework-core-sql-connections"></a><span data-ttu-id="76b34-104">Implementar conexiones de Entity Framework Core SQL resistentes</span><span class="sxs-lookup"><span data-stu-id="76b34-104">Implementing resilient Entity Framework Core SQL connections</span></span>

<span data-ttu-id="76b34-105">Base de datos de SQL Azure, Entity Framework Core ya proporciona la lógica de reintento y resistencia de conexión de base de datos interna.</span><span class="sxs-lookup"><span data-stu-id="76b34-105">For Azure SQL DB, Entity Framework Core already provides internal database connection resiliency and retry logic.</span></span> <span data-ttu-id="76b34-106">Pero debe habilitar la estrategia de ejecución de Entity Framework para cada conexión de DbContext si desea que estén [resistentes conexiones con el núcleo de EF](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency).</span><span class="sxs-lookup"><span data-stu-id="76b34-106">But you need to enable the Entity Framework execution strategy for each DbContext connection if you want to have [resilient EF Core connections](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency).</span></span>

<span data-ttu-id="76b34-107">Por ejemplo, el código siguiente en el nivel de conexión de EF Core permite resistentes conexiones de SQL que se vuelve a intentar si se produce un error en la conexión.</span><span class="sxs-lookup"><span data-stu-id="76b34-107">For instance, the following code at the EF Core connection level enables resilient SQL connections that are retried if the connection fails.</span></span>

```csharp
// Startup.cs from any ASP.NET Core Web API
public class Startup
{
    // Other code ...
    public IServiceProvider ConfigureServices(IServiceCollection services)
    {
        // ...
        services.AddDbContext<OrderingContext>(options =>
        {
            options.UseSqlServer(Configuration["ConnectionString"],
            sqlServerOptionsAction: sqlOptions =>
            {
                sqlOptions.EnableRetryOnFailure(
                maxRetryCount: 5,
                maxRetryDelay: TimeSpan.FromSeconds(30),
                errorNumbersToAdd: null);
            });
        });
    }
//...
}
```

## <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a><span data-ttu-id="76b34-108">Estrategias de ejecución y las transacciones explícitas mediante BeginTransaction y varios DbContexts</span><span class="sxs-lookup"><span data-stu-id="76b34-108">Execution strategies and explicit transactions using BeginTransaction and multiple DbContexts</span></span>

<span data-ttu-id="76b34-109">Cuando reintentos están habilitados en las conexiones de núcleo de EF, cada operación que se realiza mediante EF principal se convierte en su propia operación reintentable.</span><span class="sxs-lookup"><span data-stu-id="76b34-109">When retries are enabled in EF Core connections, each operation you perform using EF Core becomes its own retriable operation.</span></span> <span data-ttu-id="76b34-110">Cada consulta y cada llamada a SaveChanges se reintentará como una unidad si se produce un error transitorio.</span><span class="sxs-lookup"><span data-stu-id="76b34-110">Each query and each call to SaveChanges will be retried as a unit if a transient failure occurs.</span></span>

<span data-ttu-id="76b34-111">Sin embargo, si el código inicia una transacción con BeginTransaction, va a definir su propio grupo de operaciones que se deben tratar como una unidad, todo dentro de la transacción se revierte si se produce un error.</span><span class="sxs-lookup"><span data-stu-id="76b34-111">However, if your code initiates a transaction using BeginTransaction, you are defining your own group of operations that need to be treated as a unit—everything inside the transaction has be rolled back if a failure occurs.</span></span> <span data-ttu-id="76b34-112">Verá una excepción similar al siguiente si intenta ejecutar esa transacción cuando se utiliza una estrategia de ejecución de EF (directiva de reintentos) e incluir varias llamadas de SaveChanges desde varios DbContexts en la transacción.</span><span class="sxs-lookup"><span data-stu-id="76b34-112">You will see an exception like the following if you attempt to execute that transaction when using an EF execution strategy (retry policy) and you include several SaveChanges calls from multiple DbContexts in the transaction.</span></span>

> <span data-ttu-id="76b34-113">System.InvalidOperationException: La estrategia de ejecución configurada 'SqlServerRetryingExecutionStrategy' no es compatible con las transacciones iniciadas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="76b34-113">System.InvalidOperationException: The configured execution strategy 'SqlServerRetryingExecutionStrategy' does not support user initiated transactions.</span></span> <span data-ttu-id="76b34-114">Utilice la estrategia de ejecución devuelta por 'DbContext.Database.CreateExecutionStrategy()' para ejecutar todas las operaciones en la transacción como una unidad reintentable.</span><span class="sxs-lookup"><span data-stu-id="76b34-114">Use the execution strategy returned by 'DbContext.Database.CreateExecutionStrategy()' to execute all the operations in the transaction as a retriable unit.</span></span>

<span data-ttu-id="76b34-115">La solución consiste en invocar manualmente la estrategia de ejecución de EF con un delegado que representa todos los elementos que se debe ejecutar.</span><span class="sxs-lookup"><span data-stu-id="76b34-115">The solution is to manually invoke the EF execution strategy with a delegate representing everything that needs to be executed.</span></span> <span data-ttu-id="76b34-116">Si se produce un error transitorio, la estrategia de ejecución invoca al delegado de nuevo.</span><span class="sxs-lookup"><span data-stu-id="76b34-116">If a transient failure occurs, the execution strategy will invoke the delegate again.</span></span> <span data-ttu-id="76b34-117">Por ejemplo, el código siguiente muestra cómo se implementa en eShopOnContainers con dos DbContexts varios (\_catalogContext y la IntegrationEventLogContext) al actualizar un producto y, a continuación, guardar el Objeto ProductPriceChangedIntegrationEvent, que se debe usar un DbContext diferentes.</span><span class="sxs-lookup"><span data-stu-id="76b34-117">For example, the following code show how it is implemented in eShopOnContainers with two multiple DbContexts (\_catalogContext and the IntegrationEventLogContext) when updating a product and then saving the ProductPriceChangedIntegrationEvent object, which needs to use a different DbContext.</span></span>

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

<span data-ttu-id="76b34-118">Es el primer DbContext \_catalogContext y el segundo DbContext está dentro de la \_integrationEventLogService objeto.</span><span class="sxs-lookup"><span data-stu-id="76b34-118">The first DbContext is \_catalogContext and the second DbContext is within the \_integrationEventLogService object.</span></span> <span data-ttu-id="76b34-119">La acción de confirmación se realiza a través de varios DbContexts mediante una estrategia de ejecución de EF.</span><span class="sxs-lookup"><span data-stu-id="76b34-119">The Commit action is performed across multiple DbContexts using an EF execution strategy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="76b34-120">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="76b34-120">Additional resources</span></span>

-   <span data-ttu-id="76b34-121">**Resistencia de conexión y comando interceptación con Entity Framework**
    [*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)</span><span class="sxs-lookup"><span data-stu-id="76b34-121">**Connection Resiliency and Command Interception with the Entity Framework**
[*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)</span></span>

-   <span data-ttu-id="76b34-122">**Cesar de la Torre. Utilizar resistente Entity Framework Core Sql conexiones y transacciones**
    <https://blogs.msdn.microsoft.com/cesardelatorre/2017/03/26/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/></span><span class="sxs-lookup"><span data-stu-id="76b34-122">**Cesar de la Torre. Using Resilient Entity Framework Core Sql Connections and Transactions**
<https://blogs.msdn.microsoft.com/cesardelatorre/2017/03/26/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/></span></span>


>[!div class="step-by-step"]
<span data-ttu-id="76b34-123">[Anterior] (implementar-reintentos-exponencial-backoff.md) [siguiente] (implement-custom-http-call-retries-exponential-backoff.md)</span><span class="sxs-lookup"><span data-stu-id="76b34-123">[Previous] (implement-retries-exponential-backoff.md) [Next] (implement-custom-http-call-retries-exponential-backoff.md)</span></span>
