---
title: Implementar conexiones SQL resistentes de Entity Framework Core
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Implementar conexiones SQL resistentes de Entity Framework Core
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 79f115a2d897463c213eda6f4d6951ff0cbeb3ca
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105480"
---
# <a name="implementing-resilient-entity-framework-core-sql-connections"></a>Implementar conexiones SQL resistentes de Entity Framework Core

Para Azure SQL DB, Entity Framework Core ya proporciona la lógica de reintento y resistencia de conexión de base de datos interna. Pero debe habilitar la estrategia de ejecución de Entity Framework para cada conexión de DbContext si quiere tener [conexiones resistentes de EF Core](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency).

Por ejemplo, el código siguiente en el nivel de conexión de EF Core permite conexiones resistentes de SQL que se vuelven a intentar si se produce un error en la conexión.

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

## <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a>Estrategias de ejecución y transacciones explícitas mediante BeginTransaction y varios DbContexts

Cuando se habilitan los reintentos en las conexiones de EF Core, cada operación que se realiza mediante EF Core se convierte en su propia operación que se puede reintentar. Cada consulta y cada llamada a SaveChanges se reintentará como una unidad si se produce un error transitorio.

Sin embargo, si el código inicia una transacción con BeginTransaction, va a definir su propio grupo de operaciones que se deben tratar como una unidad: todo dentro de la transacción se debe revertir si se produce un error. Verá una excepción similar a la siguiente si intenta ejecutar esa transacción cuando usa una estrategia de ejecución de EF (directiva de reintentos) e incluye varias llamadas de SaveChanges desde varios DbContexts en la transacción.

> System.InvalidOperationException: la estrategia de ejecución configurada "SqlServerRetryingExecutionStrategy" no es compatible con las transacciones que el usuario inicie. Use la estrategia de ejecución que devuelve "DbContext.Database.CreateExecutionStrategy()" para ejecutar todas las operaciones en la transacción como una unidad que se puede reintentar.

La solución consiste en invocar manualmente la estrategia de ejecución de EF con un delegado que representa a todos los elementos que se deben ejecutar. Si se produce un error transitorio, la estrategia de ejecución vuelve a invocar al delegado. Por ejemplo, el código siguiente muestra cómo se implementa en eShopOnContainers con dos DbContexts múltiples (\_catalogContext y el IntegrationEventLogContext) al actualizar un producto y, después, guardar el objeto ProductPriceChangedIntegrationEvent, que debe usar un DbContext diferente.

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

El primer DbContext es \_catalogContext y el segundo DbContext está dentro del objeto \_integrationEventLogService. La acción Commit se realiza a través de varios DbContexts mediante una estrategia de ejecución de EF.

## <a name="additional-resources"></a>Recursos adicionales

-   **Connection Resiliency and Command Interception with the Entity Framework (Resistencia de la conexión e intercepción de comandos con Entity Framework)**
    [*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)

-   **Cesar de la Torre. Using Resilient Entity Framework Core Sql Connections and Transactions (Usar conexiones y transacciones SQL resistentes de Entity Framework Core)**
    <https://blogs.msdn.microsoft.com/cesardelatorre/2017/03/26/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/>


>[!div class="step-by-step"]
[Anterior](implement-retries-exponential-backoff.md)
[Siguiente](implement-custom-http-call-retries-exponential-backoff.md)
