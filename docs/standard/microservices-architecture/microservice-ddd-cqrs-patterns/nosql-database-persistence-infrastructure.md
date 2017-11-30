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
# <a name="using-nosql-databases-as-a-persistence-infrastructure"></a><span data-ttu-id="2de4b-104">Uso de las bases de datos NoSQL como una infraestructura de persistencia</span><span class="sxs-lookup"><span data-stu-id="2de4b-104">Using NoSQL databases as a persistence infrastructure</span></span>

<span data-ttu-id="2de4b-105">Cuando se usa bases de datos SQL para el nivel de datos de infraestructura, normalmente debe usarse un ORM como Entity Framework Core.</span><span class="sxs-lookup"><span data-stu-id="2de4b-105">When you use NoSQL databases for your infrastructure data tier, you typically do not use an ORM like Entity Framework Core.</span></span> <span data-ttu-id="2de4b-106">En su lugar, utilice la API proporcionada por el motor de NoSQL, como la base de datos de Azure Cosmos, MongoDB, Casandra, RavenDB, CouchDB o tablas de almacenamiento de Azure.</span><span class="sxs-lookup"><span data-stu-id="2de4b-106">Instead you use the API provided by the NoSQL engine, such as Azure Cosmos DB, MongoDB, Cassandra, RavenDB, CouchDB, or Azure Storage Tables.</span></span>

<span data-ttu-id="2de4b-107">Sin embargo, cuando se usa una base de datos NoSQL, especialmente una base de datos orientada a servicios de documento como base de datos de Azure Cosmos CouchDB y RavenDB, es parcialmente similar a cómo se puede hacer en el núcleo de EF, en lo que respecta a la identificación de la manera de diseñar el modelo con DDD agregados las raíces agregadas, las clases de entidad secundarias y las clases de objeto de valor.</span><span class="sxs-lookup"><span data-stu-id="2de4b-107">However, when you use a NoSQL database, especially a document-oriented database like Azure Cosmos DB, CouchDB, or RavenDB, the way you design your model with DDD aggregates is partially similar to how you can do it in EF Core, in regards to the identification of aggregate roots, child entity classes, and value object classes.</span></span> <span data-ttu-id="2de4b-108">Sin embargo, en última instancia, afectará a la selección de la base de datos en el diseño.</span><span class="sxs-lookup"><span data-stu-id="2de4b-108">But, ultimately, the database selection will impact in your design.</span></span>

<span data-ttu-id="2de4b-109">Cuando se usa una base de datos orientado a documentos, implemente un agregado como un solo documento serializado en JSON o en otro formato.</span><span class="sxs-lookup"><span data-stu-id="2de4b-109">When you use a document-oriented database, you implement an aggregate as a single document, serialized in JSON or another format.</span></span> <span data-ttu-id="2de4b-110">Sin embargo, el uso de la base de datos es transparente desde un punto de código dominio modelo de vista.</span><span class="sxs-lookup"><span data-stu-id="2de4b-110">However, the use of the database is transparent from a domain model code point of view.</span></span> <span data-ttu-id="2de4b-111">Cuando se usa una base de datos NoSQL, todavía está usando las clases de entidad y las clases raíz agregado, pero con más flexibilidad que cuando se usan EF principal porque la persistencia no es relacional.</span><span class="sxs-lookup"><span data-stu-id="2de4b-111">When using a NoSQL database, you still are using entity classes and aggregate root classes, but with more flexibility than when using EF Core because the persistence is not relational.</span></span>

<span data-ttu-id="2de4b-112">La diferencia radica en la conservación de ese modelo.</span><span class="sxs-lookup"><span data-stu-id="2de4b-112">The difference is in how you persist that model.</span></span> <span data-ttu-id="2de4b-113">Si implementa el modelo de dominio basándose en las clases de entidad POCO, independiente de la persistencia de la infraestructura, puede parecer que podría mover a una infraestructura de persistencia diferentes, incluso desde relacional a NoSQL.</span><span class="sxs-lookup"><span data-stu-id="2de4b-113">If you implemented your domain model based on POCO entity classes, agnostic to the infrastructure persistence, it might look like you could move to a different persistence infrastructure, even from relational to NoSQL.</span></span> <span data-ttu-id="2de4b-114">Sin embargo, no que debe ser el objetivo.</span><span class="sxs-lookup"><span data-stu-id="2de4b-114">However, that should not be your goal.</span></span> <span data-ttu-id="2de4b-115">Siempre hay restricciones en las bases de datos diferentes insertará, por lo que no podrán tener el mismo modelo para relacionales o bases de datos NoSQL.</span><span class="sxs-lookup"><span data-stu-id="2de4b-115">There are always constraints in the different databases will push you back, so you will not be able to have the same model for relational or NoSQL databases.</span></span> <span data-ttu-id="2de4b-116">Cambiar modelos de persistencia no sería trivial, porque las transacciones y las operaciones de persistencia será muy diferentes.</span><span class="sxs-lookup"><span data-stu-id="2de4b-116">Changing persistence models would not be trivial, because transactions and persistence operations will be very different.</span></span>

<span data-ttu-id="2de4b-117">Por ejemplo, en una base de datos orientado a documentos, es correcto para una raíz agregada tener varias propiedades de colección secundaria.</span><span class="sxs-lookup"><span data-stu-id="2de4b-117">For example, in a document-oriented database, it is okay for an aggregate root to have multiple child collection properties.</span></span> <span data-ttu-id="2de4b-118">En una base de datos relacional, consultar varias propiedades de la colección secundaria es terrible, porque se recibe una instrucción UNION ALL de SQL de EF.</span><span class="sxs-lookup"><span data-stu-id="2de4b-118">In a relational database, querying multiple child collection properties is awful, because you get a UNION ALL SQL statement back from EF.</span></span> <span data-ttu-id="2de4b-119">Tener el mismo modelo de dominio para bases de datos relacionales o bases de datos NoSQL no es sencillo y no debe intentar.</span><span class="sxs-lookup"><span data-stu-id="2de4b-119">Having the same domain model for relational databases or NoSQL databases is not simple, and you should not try it.</span></span> <span data-ttu-id="2de4b-120">Tiene en realidad diseñar el modelo con una comprensión de cómo los datos se van a usar en cada base de datos determinada.</span><span class="sxs-lookup"><span data-stu-id="2de4b-120">You really have to design your model with an understanding of how the data is going to be used in each particular database.</span></span>

<span data-ttu-id="2de4b-121">Una ventaja de utilizar las bases de datos NoSQL es que las entidades se encuentran más sin normalizar, por lo que no se establece una asignación de tabla.</span><span class="sxs-lookup"><span data-stu-id="2de4b-121">A benefit when using NoSQL databases is that the entities are more denormalized, so you do not set a table mapping.</span></span> <span data-ttu-id="2de4b-122">El modelo de dominio puede ser más flexible que cuando una base de datos relacional.</span><span class="sxs-lookup"><span data-stu-id="2de4b-122">Your domain model can be more flexible than when using a relational database.</span></span>

<span data-ttu-id="2de4b-123">Al diseñar el modelo de dominio basándose en agregados, mover a NoSQL y bases de datos orientadas a documento podrían ser incluso más sencillo que usar una base de datos relacional, porque son similares a los agregados que se diseña serializa documentos en una base de datos orientado a documentos.</span><span class="sxs-lookup"><span data-stu-id="2de4b-123">When you design your domain model based on aggregates, moving to NoSQL and document-oriented databases might be even easier than using a relational database, because the aggregates you design are similar to serialized documents in a document-oriented database.</span></span> <span data-ttu-id="2de4b-124">A continuación, puede incluir en los contenedores de"" toda la información que necesite para ese agregado.</span><span class="sxs-lookup"><span data-stu-id="2de4b-124">Then you can include in those “bags” all the information you might need for that aggregate.</span></span>

<span data-ttu-id="2de4b-125">Por ejemplo, el siguiente código JSON es una implementación de ejemplo de un agregado de orden cuando se usa una base de datos orientado a documentos.</span><span class="sxs-lookup"><span data-stu-id="2de4b-125">For instance, the following JSON code is a sample implementation of an order aggregate when using a document-oriented database.</span></span> <span data-ttu-id="2de4b-126">Es similar al orden agregado que se implementa en el ejemplo eShopOnContainers, pero sin utilizar EF Core debajo.</span><span class="sxs-lookup"><span data-stu-id="2de4b-126">It is similar to the order aggregate we implemented in the eShopOnContainers sample, but without using EF Core underneath.</span></span>

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

<span data-ttu-id="2de4b-127">Cuando se usa una C\# modelo para implementar el agregado que va a usar algo parecido a Azure Cosmos DB SDK, el agregado es similar a la C\# POCO clases que se usan con EF principales.</span><span class="sxs-lookup"><span data-stu-id="2de4b-127">When you use a C\# model to implement the aggregate to be used by something like the Azure Cosmos DB SDK, the aggregate is similar to the C\# POCO classes used with EF Core.</span></span> <span data-ttu-id="2de4b-128">La diferencia radica en la forma para usarlos desde las capas de aplicación y la infraestructura, como en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="2de4b-128">The difference is in the way to use them from the application and infrastructure layers, as in the following code:</span></span>

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

<span data-ttu-id="2de4b-129">Puede ver que la forma de trabajar con el modelo de dominio puede ser similar a la manera en que se utiliza en la capa de modelo de dominio cuando la infraestructura es EF.</span><span class="sxs-lookup"><span data-stu-id="2de4b-129">You can see that the way you work with your domain model can be similar to the way you use it in your domain model layer when the infrastructure is EF.</span></span> <span data-ttu-id="2de4b-130">Todavía use los mismos métodos de raíz agregada para garantizar la coherencia, las invariantes y validaciones en el agregado.</span><span class="sxs-lookup"><span data-stu-id="2de4b-130">You still use the same aggregate root methods to ensure consistency, invariants, and validations within the aggregate.</span></span>

<span data-ttu-id="2de4b-131">Sin embargo, al almacenar el modelo en la base de datos NoSQL, el código y cambio en la API drásticamente en comparación con el código básico de EF o cualquier otro código relacionadas con bases de datos relacionales.</span><span class="sxs-lookup"><span data-stu-id="2de4b-131">However, when you persist your model into the NoSQL database, the code and API change dramatically compared to EF Core code or any other code related to relational databases.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="2de4b-132">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="2de4b-132">Additional resources</span></span>

-   <span data-ttu-id="2de4b-133">**Modelado de datos en DocumentDB**
    [*https://docs.microsoft.com/azure/documentdb/documentdb-modeling-data*](https://docs.microsoft.com/azure/documentdb/documentdb-modeling-data)</span><span class="sxs-lookup"><span data-stu-id="2de4b-133">**Modeling data in DocumentDB**
[*https://docs.microsoft.com/azure/documentdb/documentdb-modeling-data*](https://docs.microsoft.com/azure/documentdb/documentdb-modeling-data)</span></span>

-   <span data-ttu-id="2de4b-134">**Vaughn Vernon. ¿El almacén de agregado Ideal controlada por el dominio diseño? ** 
     [ *https://vaughnvernon.co/?p=942*](https://vaughnvernon.co/?p=942)</span><span class="sxs-lookup"><span data-stu-id="2de4b-134">**Vaughn Vernon. The Ideal Domain-Driven Design Aggregate Store?**
[*https://vaughnvernon.co/?p=942*](https://vaughnvernon.co/?p=942)</span></span>

-   <span data-ttu-id="2de4b-135">**Un almacén de eventos para .NET independiente de persistencia.**</span><span class="sxs-lookup"><span data-stu-id="2de4b-135">**A persistence agnostic Event Store for .NET.**</span></span> <span data-ttu-id="2de4b-136">Repositorio de GitHub.</span><span class="sxs-lookup"><span data-stu-id="2de4b-136">GitHub repo.</span></span>
    [<span data-ttu-id="2de4b-137">*https://github.com/NEventStore/NEventStore*</span><span class="sxs-lookup"><span data-stu-id="2de4b-137">*https://github.com/NEventStore/NEventStore*</span></span>](https://github.com/NEventStore/NEventStore)


>[!div class="step-by-step"]
<span data-ttu-id="2de4b-138">[Anterior] (infrastructure-persistence-layer-implemenation-entity-framework-core.md) [siguiente] (microservice-application-layer-web-api-design.md)</span><span class="sxs-lookup"><span data-stu-id="2de4b-138">[Previous] (infrastructure-persistence-layer-implemenation-entity-framework-core.md) [Next] (microservice-application-layer-web-api-design.md)</span></span>
