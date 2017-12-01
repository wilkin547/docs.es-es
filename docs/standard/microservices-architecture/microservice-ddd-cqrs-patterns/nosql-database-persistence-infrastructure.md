---
title: Uso de las bases de datos NoSQL como una infraestructura de persistencia
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Uso de las bases de datos NoSQL como una infraestructura de persistencia
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: e4b63511069b89cc5761ce7ed64f09e9035a56a3
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="using-nosql-databases-as-a-persistence-infrastructure"></a>Uso de las bases de datos NoSQL como una infraestructura de persistencia

Cuando se usa bases de datos SQL para el nivel de datos de infraestructura, normalmente debe usarse un ORM como Entity Framework Core. En su lugar, utilice la API proporcionada por el motor de NoSQL, como la base de datos de Azure Cosmos, MongoDB, Casandra, RavenDB, CouchDB o tablas de almacenamiento de Azure.

Sin embargo, cuando se usa una base de datos NoSQL, especialmente una base de datos orientada a servicios de documento como base de datos de Azure Cosmos CouchDB y RavenDB, es parcialmente similar a cómo se puede hacer en el núcleo de EF, en lo que respecta a la identificación de la manera de diseñar el modelo con DDD agregados las raíces agregadas, las clases de entidad secundarias y las clases de objeto de valor. Sin embargo, en última instancia, afectará a la selección de la base de datos en el diseño.

Cuando se usa una base de datos orientado a documentos, implemente un agregado como un solo documento serializado en JSON o en otro formato. Sin embargo, el uso de la base de datos es transparente desde un punto de código dominio modelo de vista. Cuando se usa una base de datos NoSQL, todavía está usando las clases de entidad y las clases raíz agregado, pero con más flexibilidad que cuando se usan EF principal porque la persistencia no es relacional.

La diferencia radica en la conservación de ese modelo. Si implementa el modelo de dominio basándose en las clases de entidad POCO, independiente de la persistencia de la infraestructura, puede parecer que podría mover a una infraestructura de persistencia diferentes, incluso desde relacional a NoSQL. Sin embargo, no que debe ser el objetivo. Siempre hay restricciones en las bases de datos diferentes insertará, por lo que no podrán tener el mismo modelo para relacionales o bases de datos NoSQL. Cambiar modelos de persistencia no sería trivial, porque las transacciones y las operaciones de persistencia será muy diferentes.

Por ejemplo, en una base de datos orientado a documentos, es correcto para una raíz agregada tener varias propiedades de colección secundaria. En una base de datos relacional, consultar varias propiedades de la colección secundaria es terrible, porque se recibe una instrucción UNION ALL de SQL de EF. Tener el mismo modelo de dominio para bases de datos relacionales o bases de datos NoSQL no es sencillo y no debe intentar. Tiene en realidad diseñar el modelo con una comprensión de cómo los datos se van a usar en cada base de datos determinada.

Una ventaja de utilizar las bases de datos NoSQL es que las entidades se encuentran más sin normalizar, por lo que no se establece una asignación de tabla. El modelo de dominio puede ser más flexible que cuando una base de datos relacional.

Al diseñar el modelo de dominio basándose en agregados, mover a NoSQL y bases de datos orientadas a documento podrían ser incluso más sencillo que usar una base de datos relacional, porque son similares a los agregados que se diseña serializa documentos en una base de datos orientado a documentos. A continuación, puede incluir en los contenedores de"" toda la información que necesite para ese agregado.

Por ejemplo, el siguiente código JSON es una implementación de ejemplo de un agregado de orden cuando se usa una base de datos orientado a documentos. Es similar al orden agregado que se implementa en el ejemplo eShopOnContainers, pero sin utilizar EF Core debajo.

```json
{
    "id": "2017001",
    "orderDate": "2/25/2017",
    "buyerId": "1234567",
    "address": [
        {
        "street": "100 One Microsoft Way",
        "city": "Redmond",
        "state": "WA",
        "zip": "98052",
        "country": "U.S."
        }
    ],
    "orderItems": [
        {"id": 20170011, "productId": "123456", "productName": ".NET T-Shirt",
        "unitPrice": 25, "units": 2, "discount": 0},
        {"id": 20170012, "productId": "123457", "productName": ".NET Mug",
        "unitPrice": 15, "units": 1, "discount": 0}
    ]
}
```

Cuando se usa una C\# modelo para implementar el agregado que va a usar algo parecido a Azure Cosmos DB SDK, el agregado es similar a la C\# POCO clases que se usan con EF principales. La diferencia radica en la forma para usarlos desde las capas de aplicación y la infraestructura, como en el código siguiente:

```csharp
// C# EXAMPLE OF AN ORDER AGGREGATE BEING PERSISTED WITH DOCUMENTDB API
// *** Domain Model Code ***
// Aggregate: Create an Order object with its child entities and/or value objects.
// Then, use AggregateRoot’s methods to add the nested objects so invariants and
// logic is consistent across the nested properties (value objects and entities).
// This can be saved as JSON as is without converting into rows/columns.
Order orderAggregate = new Order
{
    Id = "2017001",
    OrderDate = new DateTime(2005, 7, 1),
    BuyerId = "1234567",
    PurchaseOrderNumber = "PO18009186470"
}

Address address = new Address
{
    Street = "100 One Microsoft Way",
    City = "Redmond",
    State = "WA",
    Zip = "98052",
    Country = "U.S."
}

orderAggregate.UpdateAddress(address);
OrderItem orderItem1 = new OrderItem
{
    Id = 20170011,
    ProductId = "123456",
    ProductName = ".NET T-Shirt",
    UnitPrice = 25,
    Units = 2,
    Discount = 0;
};

OrderItem orderItem2 = new OrderItem
{
    Id = 20170012,
    ProductId = "123457",
    ProductName = ".NET Mug",
    UnitPrice = 15,
    Units = 1,
    Discount = 0;
};

//Using methods with domain logic within the entity. No anemic-domain model
orderAggregate.AddOrderItem(orderItem1);
orderAggregate.AddOrderItem(orderItem2);

// *** End of Domain Model Code ***
//...
// *** Infrastructure Code using Cosmos DB Client API ***
Uri collectionUri = UriFactory.CreateDocumentCollectionUri(databaseName,
    collectionName);

await client.CreateDocumentAsync(collectionUri, order);

// As your app evolves, let's say your object has a new schema. You can insert
// OrderV2 objects without any changes to the database tier.
Order2 newOrder = GetOrderV2Sample("IdForSalesOrder2");
await client.CreateDocumentAsync(collectionUri, newOrder);
```

Puede ver que la forma de trabajar con el modelo de dominio puede ser similar a la manera en que se utiliza en la capa de modelo de dominio cuando la infraestructura es EF. Todavía use los mismos métodos de raíz agregada para garantizar la coherencia, las invariantes y validaciones en el agregado.

Sin embargo, al almacenar el modelo en la base de datos NoSQL, el código y cambio en la API drásticamente en comparación con el código básico de EF o cualquier otro código relacionadas con bases de datos relacionales.

#### <a name="additional-resources"></a>Recursos adicionales

-   **Modelado de datos en DocumentDB**
    [*https://docs.microsoft.com/azure/documentdb/documentdb-modeling-data*](https://docs.microsoft.com/azure/documentdb/documentdb-modeling-data)

-   **Vaughn Vernon. ¿El almacén de agregado Ideal controlada por el dominio diseño? ** 
     [ *https://vaughnvernon.co/?p=942*](https://vaughnvernon.co/?p=942)

-   **Un almacén de eventos para .NET independiente de persistencia.** Repositorio de GitHub.
    [*https://github.com/NEventStore/NEventStore*](https://github.com/NEventStore/NEventStore)


>[!div class="step-by-step"]
[Anterior] (infrastructure-persistence-layer-implemenation-entity-framework-core.md) [siguiente] (microservice-application-layer-web-api-design.md)
