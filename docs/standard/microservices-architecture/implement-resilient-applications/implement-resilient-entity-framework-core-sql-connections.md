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
# <a name="implementing-resilient-entity-framework-core-sql-connections"></a>Implementar conexiones de Entity Framework Core SQL resistentes

Base de datos de SQL Azure, Entity Framework Core ya proporciona la lógica de reintento y resistencia de conexión de base de datos interna. Pero debe habilitar la estrategia de ejecución de Entity Framework para cada conexión de DbContext si desea que estén [resistentes conexiones con el núcleo de EF](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency).

Por ejemplo, el código siguiente en el nivel de conexión de EF Core permite resistentes conexiones de SQL que se vuelve a intentar si se produce un error en la conexión.

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

## <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a>Estrategias de ejecución y las transacciones explícitas mediante BeginTransaction y varios DbContexts

Cuando reintentos están habilitados en las conexiones de núcleo de EF, cada operación que se realiza mediante EF principal se convierte en su propia operación reintentable. Cada consulta y cada llamada a SaveChanges se reintentará como una unidad si se produce un error transitorio.

Sin embargo, si el código inicia una transacción con BeginTransaction, va a definir su propio grupo de operaciones que se deben tratar como una unidad, todo dentro de la transacción se revierte si se produce un error. Verá una excepción similar al siguiente si intenta ejecutar esa transacción cuando se utiliza una estrategia de ejecución de EF (directiva de reintentos) e incluir varias llamadas de SaveChanges desde varios DbContexts en la transacción.

> System.InvalidOperationException: La estrategia de ejecución configurada 'SqlServerRetryingExecutionStrategy' no es compatible con las transacciones iniciadas por el usuario. Utilice la estrategia de ejecución devuelta por 'DbContext.Database.CreateExecutionStrategy()' para ejecutar todas las operaciones en la transacción como una unidad reintentable.

La solución consiste en invocar manualmente la estrategia de ejecución de EF con un delegado que representa todos los elementos que se debe ejecutar. Si se produce un error transitorio, la estrategia de ejecución invoca al delegado de nuevo. Por ejemplo, el código siguiente muestra cómo se implementa en eShopOnContainers con dos DbContexts varios (\_catalogContext y la IntegrationEventLogContext) al actualizar un producto y, a continuación, guardar el Objeto ProductPriceChangedIntegrationEvent, que se debe usar un DbContext diferentes.

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

Es el primer DbContext \_catalogContext y el segundo DbContext está dentro de la \_integrationEventLogService objeto. La acción de confirmación se realiza a través de varios DbContexts mediante una estrategia de ejecución de EF.

## <a name="additional-resources"></a>Recursos adicionales

-   **Resistencia de conexión y comando interceptación con Entity Framework**
    [*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)

-   **Cesar de la Torre. Utilizar resistente Entity Framework Core Sql conexiones y transacciones**
    <https://blogs.msdn.microsoft.com/cesardelatorre/2017/03/26/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/>


>[!div class="step-by-step"]
[Anterior] (implementar-reintentos-exponencial-backoff.md) [siguiente] (implement-custom-http-call-retries-exponential-backoff.md)
