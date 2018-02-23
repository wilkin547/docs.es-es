---
title: Uso de bases de datos NoSQL como una infraestructura de persistencia
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedor | Uso de las bases de datos NoSQL como una infraestructura de persistencia
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/12/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: a6f3a991529aea6560eb12f1400ba2750795ebff
ms.sourcegitcommit: 08684dd61444c2f072b89b926370f750e456fca1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2018
---
# <a name="using-nosql-databases-as-a-persistence-infrastructure"></a><span data-ttu-id="c2a74-104">Uso de bases de datos NoSQL como una infraestructura de persistencia</span><span class="sxs-lookup"><span data-stu-id="c2a74-104">Using NoSQL databases as a persistence infrastructure</span></span>

<span data-ttu-id="c2a74-105">Cuando se usan bases de datos NoSQL para el nivel de datos de infraestructura, normalmente no se utiliza un ORM como Entity Framework Core.</span><span class="sxs-lookup"><span data-stu-id="c2a74-105">When you use NoSQL databases for your infrastructure data tier, you typically do not use an ORM like Entity Framework Core.</span></span> <span data-ttu-id="c2a74-106">En su lugar, se utiliza la API proporcionada por el motor de NoSQL, como por ejemplo Azure Cosmos DB, MongoDB, Cassandra, RavenDB, CouchDB o tablas de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="c2a74-106">Instead you use the API provided by the NoSQL engine, such as Azure Cosmos DB, MongoDB, Cassandra, RavenDB, CouchDB, or Azure Storage Tables.</span></span>

<span data-ttu-id="c2a74-107">Pero cuando se usa una base de datos NoSQL, especialmente una orientada a documentos como Azure Cosmos DB, CouchDB o RavenDB, la forma de diseñar el modelo con agregados DDD es parcialmente similar a cómo se puede hacer en EF Core, en lo que respecta a la identificación de las raíces agregadas, las clases de entidad secundarias y las clases de objeto de valor.</span><span class="sxs-lookup"><span data-stu-id="c2a74-107">However, when you use a NoSQL database, especially a document-oriented database like Azure Cosmos DB, CouchDB, or RavenDB, the way you design your model with DDD aggregates is partially similar to how you can do it in EF Core, in regards to the identification of aggregate roots, child entity classes, and value object classes.</span></span> <span data-ttu-id="c2a74-108">Pero, en última instancia, la selección de la base de datos afectará al diseño.</span><span class="sxs-lookup"><span data-stu-id="c2a74-108">But, ultimately, the database selection will impact in your design.</span></span>

<span data-ttu-id="c2a74-109">Cuando utilice una base de datos orientada a documentos, implemente un agregado como un solo documento serializado en JSON o en otro formato.</span><span class="sxs-lookup"><span data-stu-id="c2a74-109">When you use a document-oriented database, you implement an aggregate as a single document, serialized in JSON or another format.</span></span> <span data-ttu-id="c2a74-110">Pero el uso de la base de datos es transparente desde un punto de vista del código de dominio de modelo.</span><span class="sxs-lookup"><span data-stu-id="c2a74-110">However, the use of the database is transparent from a domain model code point of view.</span></span> <span data-ttu-id="c2a74-111">Cuando se usa una base de datos NoSQL, también se utilizan las clases de entidad y las clases raíz de agregado, pero con más flexibilidad que cuando se usa EF Core porque la persistencia no es relacional.</span><span class="sxs-lookup"><span data-stu-id="c2a74-111">When using a NoSQL database, you still are using entity classes and aggregate root classes, but with more flexibility than when using EF Core because the persistence is not relational.</span></span>

<span data-ttu-id="c2a74-112">La diferencia radica en cómo se persiste ese modelo.</span><span class="sxs-lookup"><span data-stu-id="c2a74-112">The difference is in how you persist that model.</span></span> <span data-ttu-id="c2a74-113">Si implementa el modelo de dominio basándose en las clases de entidad POCO, independientemente de la persistencia de la infraestructura, quizá parezca que puede cambiar a una infraestructura de persistencia diferente, incluso desde relacional a NoSQL.</span><span class="sxs-lookup"><span data-stu-id="c2a74-113">If you implemented your domain model based on POCO entity classes, agnostic to the infrastructure persistence, it might look like you could move to a different persistence infrastructure, even from relational to NoSQL.</span></span> <span data-ttu-id="c2a74-114">Pero ese no debería ser el objetivo.</span><span class="sxs-lookup"><span data-stu-id="c2a74-114">However, that should not be your goal.</span></span> <span data-ttu-id="c2a74-115">Siempre hay restricciones en las bases de datos diferentes insertará, por lo que no se podrá tener el mismo modelo para bases de datos relacionales o NoSQL.</span><span class="sxs-lookup"><span data-stu-id="c2a74-115">There are always constraints in the different databases will push you back, so you will not be able to have the same model for relational or NoSQL databases.</span></span> <span data-ttu-id="c2a74-116">Cambiar modelos de persistencia tendría su importancia, dado que las transacciones y las operaciones de persistencia serán muy diferentes.</span><span class="sxs-lookup"><span data-stu-id="c2a74-116">Changing persistence models would not be trivial, because transactions and persistence operations will be very different.</span></span>

<span data-ttu-id="c2a74-117">Por ejemplo, en una base de datos orientada a documentos, es correcto que una raíz agregada tenga varias propiedades de colección secundaria.</span><span class="sxs-lookup"><span data-stu-id="c2a74-117">For example, in a document-oriented database, it is okay for an aggregate root to have multiple child collection properties.</span></span> <span data-ttu-id="c2a74-118">En una base de datos relacional, consultar varias propiedades de colección secundaria es complicado, porque se recibe una instrucción UNION ALL SQL de EF.</span><span class="sxs-lookup"><span data-stu-id="c2a74-118">In a relational database, querying multiple child collection properties is awful, because you get a UNION ALL SQL statement back from EF.</span></span> <span data-ttu-id="c2a74-119">Tener el mismo modelo de dominio para bases de datos relacionales o bases de datos NoSQL no es sencillo y no debería intentarse.</span><span class="sxs-lookup"><span data-stu-id="c2a74-119">Having the same domain model for relational databases or NoSQL databases is not simple, and you should not try it.</span></span> <span data-ttu-id="c2a74-120">El modelo debe diseñarse entendiendo el uso que se va a hacer de los datos en cada base de datos en particular.</span><span class="sxs-lookup"><span data-stu-id="c2a74-120">You really have to design your model with an understanding of how the data is going to be used in each particular database.</span></span>

<span data-ttu-id="c2a74-121">Una ventaja de utilizar las bases de datos NoSQL es que las entidades estén menos normalizadas, por lo que no se establece una asignación de tabla.</span><span class="sxs-lookup"><span data-stu-id="c2a74-121">A benefit when using NoSQL databases is that the entities are more denormalized, so you do not set a table mapping.</span></span> <span data-ttu-id="c2a74-122">El modelo de dominio puede ser más flexible que al utilizar una base de datos relacional.</span><span class="sxs-lookup"><span data-stu-id="c2a74-122">Your domain model can be more flexible than when using a relational database.</span></span>

<span data-ttu-id="c2a74-123">Al diseñar el modelo de dominio basándose en agregados, el cambio a bases de datos NoSQL y orientadas a documentos podría ser incluso más sencillo que usar una base de datos relacional, puesto que los agregados que se diseñan son similares a documentos serializados en una base de datos orientada a documentos.</span><span class="sxs-lookup"><span data-stu-id="c2a74-123">When you design your domain model based on aggregates, moving to NoSQL and document-oriented databases might be even easier than using a relational database, because the aggregates you design are similar to serialized documents in a document-oriented database.</span></span> <span data-ttu-id="c2a74-124">Luego puede incluir en esas "bolsas" toda la información que necesite para ese agregado.</span><span class="sxs-lookup"><span data-stu-id="c2a74-124">Then you can include in those “bags” all the information you might need for that aggregate.</span></span>

<span data-ttu-id="c2a74-125">Por ejemplo, el siguiente código JSON es una implementación de ejemplo de un agregado de pedido cuando se usa una base de datos orientada a documentos.</span><span class="sxs-lookup"><span data-stu-id="c2a74-125">For instance, the following JSON code is a sample implementation of an order aggregate when using a document-oriented database.</span></span> <span data-ttu-id="c2a74-126">Es similar al orden agregado de pedido que implementamos en el ejemplo eShopOnContainers, pero sin utilizar EF Core debajo.</span><span class="sxs-lookup"><span data-stu-id="c2a74-126">It is similar to the order aggregate we implemented in the eShopOnContainers sample, but without using EF Core underneath.</span></span>

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

## <a name="introduction-to-azure-cosmos-db-and-the-native-cosmos-db-api"></a><span data-ttu-id="c2a74-127">Introducción a Azure Cosmos DB y la API Cosmos DB nativa</span><span class="sxs-lookup"><span data-stu-id="c2a74-127">Introduction to Azure Cosmos DB and the native Cosmos DB API</span></span>

<span data-ttu-id="c2a74-128">[Azure Cosmos DB](https://docs.microsoft.com/en-us/azure/cosmos-db/introduction) es el servicio de base de datos distribuida globalmente de Microsoft para aplicaciones críticas.</span><span class="sxs-lookup"><span data-stu-id="c2a74-128">[Azure Cosmos DB](https://docs.microsoft.com/en-us/azure/cosmos-db/introduction) is Microsoft's globally distributed database service for mission-critical applications.</span></span> <span data-ttu-id="c2a74-129">Azure Cosmos DB proporciona [distribución global inmediata](https://docs.microsoft.com/en-us/azure/cosmos-db/distribute-data-globally), [escalado flexible de rendimiento y almacenamiento](https://docs.microsoft.com/en-us/azure/cosmos-db/partition-data) en todo el mundo, latencias de milisegundo de un solo dígito en el percentil 99, [cinco niveles de coherencia bien definidos](https://docs.microsoft.com/en-us/azure/cosmos-db/consistency-levels) y alta disponibilidad garantizada, todo ello respaldado por [los mejores SLA del sector](https://azure.microsoft.com/support/legal/sla/cosmos-db/).</span><span class="sxs-lookup"><span data-stu-id="c2a74-129">Azure Cosmos DB provides [turn-key global distribution](https://docs.microsoft.com/en-us/azure/cosmos-db/distribute-data-globally), [elastic scaling of throughput and storage](https://docs.microsoft.com/en-us/azure/cosmos-db/partition-data) worldwide, single-digit millisecond latencies at the 99th percentile, [five well-defined consistency levels](https://docs.microsoft.com/en-us/azure/cosmos-db/consistency-levels), and guaranteed high availability, all backed by [industry-leading SLAs](https://azure.microsoft.com/support/legal/sla/cosmos-db/).</span></span> <span data-ttu-id="c2a74-130">Azure Cosmos DB [indiza automáticamente los datos](http://www.vldb.org/pvldb/vol8/p1668-shukla.pdf) sin necesidad de administrar el esquema y el índice.</span><span class="sxs-lookup"><span data-stu-id="c2a74-130">Azure Cosmos DB [automatically indexes data](http://www.vldb.org/pvldb/vol8/p1668-shukla.pdf) without requiring you to deal with schema and index management.</span></span> <span data-ttu-id="c2a74-131">Es multimodelo y admite modelos de datos de documentos, clave-valor, gráfico y columnas.</span><span class="sxs-lookup"><span data-stu-id="c2a74-131">It is multi-model and supports document, key-value, graph, and columnar data models.</span></span>

<span data-ttu-id="c2a74-132">![](./media/image19.1.png) Figura 9-19.</span><span class="sxs-lookup"><span data-stu-id="c2a74-132">![](./media/image19.1.png) Figure 9-19.</span></span> <span data-ttu-id="c2a74-133">Distribución global de Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="c2a74-133">Azure Cosmos DB global distribution</span></span>

<span data-ttu-id="c2a74-134">Cuando se usa un modelo C\# para implementar el agregado que va a usar la API de Azure Cosmos DB, el agregado puede ser similar a las clases POCO de C\# que se usan con EF Core.</span><span class="sxs-lookup"><span data-stu-id="c2a74-134">When you use a C\# model to implement the aggregate to be used by the Azure Cosmos DB API, the aggregate can be similar to the C\# POCO classes used with EF Core.</span></span> <span data-ttu-id="c2a74-135">La diferencia radica en la forma de usarlos desde la aplicación y las capas de la infraestructura, como en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="c2a74-135">The difference is in the way to use them from the application and infrastructure layers, as in the following code:</span></span>

```csharp
// C# EXAMPLE OF AN ORDER AGGREGATE BEING PERSISTED WITH AZURE COSMOS DB API
// *** Domain Model Code ***
// Aggregate: Create an Order object with its child entities and/or value objects.
// Then, use AggregateRoot’s methods to add the nested objects so invariants and
// logic is consistent across the nested properties (value objects and entities).

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

//Using methods with domain logic within the entity. No anemic-domain model
orderAggregate.AddOrderItem(orderItem1);
orderAggregate.AddOrderItem(orderItem2);
// *** End of Domain Model Code ***

// *** Infrastructure Code using Cosmos DB Client API ***
Uri collectionUri = UriFactory.CreateDocumentCollectionUri(databaseName,
    collectionName);

await client.CreateDocumentAsync(collectionUri, orderAggregate);

// As your app evolves, let's say your object has a new schema. You can insert
// OrderV2 objects without any changes to the database tier.
Order2 newOrder = GetOrderV2Sample("IdForSalesOrder2");
await client.CreateDocumentAsync(collectionUri, newOrder);
```

<span data-ttu-id="c2a74-136">Puede ver que la forma de trabajar con el modelo de dominio puede ser similar a la manera en que se utiliza en la capa de modelo de dominio cuando la infraestructura es EF.</span><span class="sxs-lookup"><span data-stu-id="c2a74-136">You can see that the way you work with your domain model can be similar to the way you use it in your domain model layer when the infrastructure is EF.</span></span> <span data-ttu-id="c2a74-137">Se siguen usando los mismos métodos raíz de agregación para garantizar la coherencia, las invariantes y las validaciones en el agregado.</span><span class="sxs-lookup"><span data-stu-id="c2a74-137">You still use the same aggregate root methods to ensure consistency, invariants, and validations within the aggregate.</span></span>

<span data-ttu-id="c2a74-138">Pero cuando se persiste el modelo en la base de datos NoSQL, el código y la API cambian drásticamente en comparación con el código de EF Core o cualquier otro código relacionado con las bases de datos relacionales.</span><span class="sxs-lookup"><span data-stu-id="c2a74-138">However, when you persist your model into the NoSQL database, the code and API change dramatically compared to EF Core code or any other code related to relational databases.</span></span>

## <a name="implementing-net-code-targeting-mongodb-and-azure-cosmos-db"></a><span data-ttu-id="c2a74-139">Implementación de código de .NET destinado a MongoDB y Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="c2a74-139">Implementing .NET code targeting MongoDB and Azure Cosmos DB</span></span>

### <a name="using-azure-cosmos-db-from-net-containers"></a><span data-ttu-id="c2a74-140">Uso de Azure Cosmos DB desde contenedores de .NET</span><span class="sxs-lookup"><span data-stu-id="c2a74-140">Using Azure Cosmos DB from .NET containers</span></span>

<span data-ttu-id="c2a74-141">Se puede acceder a las bases de datos de Azure Cosmos DB desde código de .NET que se ejecuta en contenedores, como en cualquier otra aplicación. NET.</span><span class="sxs-lookup"><span data-stu-id="c2a74-141">You can access Azure Cosmos DB databases from .NET code running in containers, like from any other .NET application.</span></span> <span data-ttu-id="c2a74-142">Por ejemplo, los microservicios Locations.API y Marketing.API de eShopOnContainers se implementan para que puedan utilizar las bases de datos de Azure Cosmos DB.</span><span class="sxs-lookup"><span data-stu-id="c2a74-142">For instance, the Locations.API and Marketing.API microservices in eShopOnContainers are implemented so they can consume Azure Cosmos DB databases.</span></span>

<span data-ttu-id="c2a74-143">Pero hay una limitación en Azure Cosmos DB desde un punto de vista del entorno de desarrollo Docker.</span><span class="sxs-lookup"><span data-stu-id="c2a74-143">However, there’s a limitation in Azure Cosmos DB from a Docker development environment point of view.</span></span> <span data-ttu-id="c2a74-144">A pesar de que hay un [emulador de Azure Cosmos DB](https://docs.microsoft.com/en-us/azure/cosmos-db/local-emulator) local capaz de ejecutarse en una máquina de desarrollo local (por ejemplo, un equipo PC), hasta finales de 2017, solo es compatible con Windows, pero no con Linux.</span><span class="sxs-lookup"><span data-stu-id="c2a74-144">Even when there’s a on-premises [Azure Cosmos DB Emulator](https://docs.microsoft.com/en-us/azure/cosmos-db/local-emulator) able to run in a local development machine (like a PC), as of late 2017, it just supports Windows, not Linux.</span></span> 

<span data-ttu-id="c2a74-145">También existe la posibilidad de ejecutar este emulador en Docker, pero solo en los contenedores de Windows, no en los de Linux.</span><span class="sxs-lookup"><span data-stu-id="c2a74-145">There is also the possibility to run this emulator on Docker, but just on Windows Containers with the , not Linux Containers.</span></span> <span data-ttu-id="c2a74-146">Eso es un hándicap inicial para el entorno de desarrollo si la aplicación se implementa como contenedores de Linux, puesto que actualmente no es posible implementar al mismo tiempo contenedores de Windows y Linux en Docker para Windows.</span><span class="sxs-lookup"><span data-stu-id="c2a74-146">That is an initial handicap for the development environment if your application is deployed as Linux containers, since, currently, you cannot deploy Linux and Windows Containers on Docker for Windows at the same time.</span></span> <span data-ttu-id="c2a74-147">Todos los contenedores que se implementen tienen que ser de Linux o de Windows.</span><span class="sxs-lookup"><span data-stu-id="c2a74-147">Either all containers being deployed have to be for Linux or for Windows.</span></span>  

<span data-ttu-id="c2a74-148">La implementación ideal y más sencilla para una solución de desarrollo o pruebas consiste en ser capaz de implementar los sistemas de base de datos como contenedores junto con los contenedores personalizados para que sus entornos de desarrollo o pruebas sean siempre coherentes.</span><span class="sxs-lookup"><span data-stu-id="c2a74-148">The ideal and more straightforward deployment for a dev/test solution is to be able to deploy your database systems as containers along with your custom containers so your dev/test environments are always consistent.</span></span>

### <a name="use-mongodb-api-for-local-devtest-linuxwindows-containers-plus-azure-cosmos-db"></a><span data-ttu-id="c2a74-149">Uso de la API de MongoDB para contenedores locales de desarrollo o pruebas de Linux y Windows además de Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="c2a74-149">Use MongoDB API for local dev/test Linux/Windows containers plus Azure Cosmos DB</span></span>

<span data-ttu-id="c2a74-150">Las bases de datos de COSMOS DB son compatibles con la API de MongoDB para. NET, además de con el protocolo de conexión de MongoDB nativo.</span><span class="sxs-lookup"><span data-stu-id="c2a74-150">Cosmos DB databases support MongoDB API for .NET as well as the native MongoDB wire protocol.</span></span> <span data-ttu-id="c2a74-151">Esto significa que, utilizando los controladores existentes, la aplicación escrita para MongoDB ahora puede comunicarse con Cosmos DB y usar las bases de datos de Cosmos DB en lugar de las bases de datos de MongoDB, tal como se muestra en la figura 9-20.</span><span class="sxs-lookup"><span data-stu-id="c2a74-151">This means that by using existing drivers, your application written for MongoDB can now communicate with Cosmos DB and use Cosmos DB databases instead of MongoDB databases, as shown in Figure 9-20.</span></span>

<span data-ttu-id="c2a74-152">![](./media/image19.2.png) Figura 9-20.</span><span class="sxs-lookup"><span data-stu-id="c2a74-152">![](./media/image19.2.png) Figure 9-20.</span></span> <span data-ttu-id="c2a74-153">Uso de la API de MongoDB y el protocolo para acceder Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="c2a74-153">Using MongoDB API and protocol to access Azure Cosmos DB</span></span>

<span data-ttu-id="c2a74-154">Esto es un método muy práctico para la prueba de conceptos en entornos de Docker con contenedores Linux porque la [imagen de MongoDB Docker](https://hub.docker.com/r/_/mongo/) es una imagen multiarquitectura que admite contenedores de Docker de Linux y Windows.</span><span class="sxs-lookup"><span data-stu-id="c2a74-154">This is a very convenient approach for proof of concepts in Docker environments with Linux containers because the [MongoDB Docker image](https://hub.docker.com/r/_/mongo/) is a multi-arch image that supports Docker Linux containers and Docker Windows containers.</span></span>

<span data-ttu-id="c2a74-155">Como se muestra en la imagen 9-21, mediante la API de MongoDB, eShopOnContainers admite contenedores de MongoDB de Linux y Windows para el entorno de desarrollo local. Después, puede mover a una solución de nube PaaS escalable como Azure Cosmos DB simplemente [cambiando la cadena de conexión de MongoDB para que apunte a Azure Cosmos DB](https://docs.microsoft.com/en-us/azure/cosmos-db/connect-mongodb-account).</span><span class="sxs-lookup"><span data-stu-id="c2a74-155">As shown in the image 9-21, by using the MongoDB API, eShopOnContainers supports MongoDB Linux and Windows containers for the local development environment but then, you can move to a scalable, PaaS cloud solution as Azure Cosmos DB by simply [changing the MongoDB connection string to point to Azure Cosmos DB](https://docs.microsoft.com/en-us/azure/cosmos-db/connect-mongodb-account).</span></span> 

<span data-ttu-id="c2a74-156">![](./media/image20-bis.png) Figura 9-21.</span><span class="sxs-lookup"><span data-stu-id="c2a74-156">![](./media/image20-bis.png) Figure 9-21.</span></span> <span data-ttu-id="c2a74-157">eShopOnContainers con contenedores de MongoDB para desarrollo o entorno o Azure Cosmos DB para producción</span><span class="sxs-lookup"><span data-stu-id="c2a74-157">eShopOnContainers using MongoDB containers for dev-env or Azure Cosmos DB for production</span></span>

<span data-ttu-id="c2a74-158">La base de datos Azure Cosmos DB de producción se ejecuta en la nube de Azure como un servicio escalable y de PaaS.</span><span class="sxs-lookup"><span data-stu-id="c2a74-158">The production Azure Cosmos DB would be running in Azure’s cloud as a PaaS and scalable service.</span></span>

<span data-ttu-id="c2a74-159">Los contenedores de .NET Core personalizados pueden ejecutarse en un host Docker de desarrollo local (es decir, con Docker para Windows en un equipo Windows 10) o implementarse en un entorno de producción, como Kubernetes en Azure AKS o Azure Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="c2a74-159">Your custom .NET Core containers can run on a local development Docker host (that is using Docker for Windows in a Windows 10 machine) or be deployed into a production environment, like Kubernetes in Azure AKS or Azure Service Fabric.</span></span> <span data-ttu-id="c2a74-160">En este segundo entorno, implemente solo los contenedores personalizados de .NET Core, pero no el contenedor de MongoDB ya que usaría Azure Cosmos DB en la nube para controlar los datos de producción.</span><span class="sxs-lookup"><span data-stu-id="c2a74-160">In this second environment, you would deploy only the .NET Core custom containers but not the MongoDB container since you’d be using Azure Cosmos DB in the cloud for handling the data in production.</span></span>

<span data-ttu-id="c2a74-161">Una ventaja evidente de utilizar la API de MongoDB es que la solución puede ejecutarse en dos motores de base de datos, MongoDB o Azure Cosmos DB, por lo que sería fácil migrar a otros entornos.</span><span class="sxs-lookup"><span data-stu-id="c2a74-161">A clear benefit of using the MongoDB API is that your solution could run in both database engines, MongoDB or Azure Cosmos DB, so migrations to different environments should be easy.</span></span> <span data-ttu-id="c2a74-162">Pero en ocasiones merece la pena usar una API nativa (es decir, la API de Cosmos DB nativa) con el fin de aprovechar al máximo las capacidades de un determinado motor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="c2a74-162">However, sometimes it is worthwhile to use a native API (that is the native Cosmos DB API) in order to take full advantage of the capabilities of a specific database engine.</span></span>

<span data-ttu-id="c2a74-163">Para comparar el uso de MongoDB frente a Cosmos DB en la nube, consulte las [ventajas de usar Azure Cosmos DB en esta página](https://docs.microsoft.com/en-us/azure/cosmos-db/mongodb-introduction).</span><span class="sxs-lookup"><span data-stu-id="c2a74-163">For further comparison between simply using MongoDB versus Cosmos DB in the cloud, see the [Benefits of using Azure Cosmos DB in this page](https://docs.microsoft.com/en-us/azure/cosmos-db/mongodb-introduction).</span></span> 


### <a name="analyze-your-approach-for-production-applications-mongodb-api-vs-cosmos-db-api"></a><span data-ttu-id="c2a74-164">Análisis del enfoque para aplicaciones de producción: API de MongoDB frente a API de Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="c2a74-164">Analyze your approach for production applications: MongoDB API vs. Cosmos DB API</span></span>

<span data-ttu-id="c2a74-165">En eShopOnContainers, estamos usando API de MongoDB porque nuestra prioridad era fundamentalmente tener un entorno de desarrollo o pruebas coherente con una base de datos NoSQL que también pudiese funcionar con Azure Cosmos DB.</span><span class="sxs-lookup"><span data-stu-id="c2a74-165">In eShopOnContainers, we’re using MongoDB API because our priority was fundamentally to have a consistent dev/test environment using a NoSQL database that could also work with Azure Cosmos DB.</span></span>

<span data-ttu-id="c2a74-166">Pero si se pretende utilizar la API de MongoDB para tener acceso a Azure Cosmos DB en aplicaciones de Azure para producción, se deben analizar y comparar las diferencias entre las capacidades y el rendimiento al usar la API de MongoDB para acceder a las bases de datos de Azure Cosmos DB y usar la API de Azure Cosmos DB nativa.</span><span class="sxs-lookup"><span data-stu-id="c2a74-166">However, if you planning to use MongoDB API to access Azure Cosmos DB in Azure for production applications, you should analyze the differences in capabilities and performance when using MongoDB API to access Azure Cosmos DB databases compared to using the native Azure Cosmos DB API.</span></span> <span data-ttu-id="c2a74-167">Si el resultado es similar, se puede utilizar la API de MongoDB, con la ventaja de admitir dos motores de base de datos NoSQL al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="c2a74-167">If it is similar you can use MongoDB API, and you get the benefit of supporting two NoSQL database engines at the same time.</span></span> 

<span data-ttu-id="c2a74-168">También podría utilizar clústeres de MongoDB como base de datos de producción en la nube de Azure, con [MongoDB Azure Service](https://www.mongodb.com/scale/mongodb-azure-service).</span><span class="sxs-lookup"><span data-stu-id="c2a74-168">You could also use MongoDB clusters as the production database in Azure’s cloud, too, with [MongoDB Azure Service](https://www.mongodb.com/scale/mongodb-azure-service).</span></span> <span data-ttu-id="c2a74-169">Pero eso no es un servicio PaaS proporcionado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c2a74-169">But that is not a PaaS service provided by Microsoft.</span></span> <span data-ttu-id="c2a74-170">En este caso, Azure solo hospeda la solución procedente de MongoDB.</span><span class="sxs-lookup"><span data-stu-id="c2a74-170">In this case, Azure is just hosting that solution coming from MongoDB.</span></span>

<span data-ttu-id="c2a74-171">Básicamente, esto es simplemente una renuncia que indica que no debe usar siempre la API de MongoDB en Azure Cosmos DB, como hicimos en eShopOnContainers, puesto que se trataba de una opción conveniente para los contenedores de Linux.</span><span class="sxs-lookup"><span data-stu-id="c2a74-171">Basically, this is just a disclaimer stating that you shouldn’t always use MongoDB API against Azure Cosmos DB, as we did in eShopOnContainers because it was a convenient choice for Linux containers.</span></span> <span data-ttu-id="c2a74-172">La decisión debe basarse en las necesidades específicas y las pruebas que deba hacer en la aplicación de producción.</span><span class="sxs-lookup"><span data-stu-id="c2a74-172">The decision should be based on the specific needs and tests you need to do for your production application.</span></span>  

### <a name="the-code-using-mongodb-api-in-net-core-applications"></a><span data-ttu-id="c2a74-173">El código: uso de la API de MongoDB en aplicaciones de .NET Core</span><span class="sxs-lookup"><span data-stu-id="c2a74-173">The code: Using MongoDB API in .NET Core applications</span></span>

<span data-ttu-id="c2a74-174">La API de MongoDB para .NET se basa en los paquetes NuGet que debe agregar a los proyectos, como Locations.API en la figura 9-22.</span><span class="sxs-lookup"><span data-stu-id="c2a74-174">MongoDB API for .NET is based on NuGet packages that you need to add to your projects, like the Locations.API shown in Figure 9-22.</span></span>

<span data-ttu-id="c2a74-175">![](./media/image21-bis.png) Figura 9-22.</span><span class="sxs-lookup"><span data-stu-id="c2a74-175">![](./media/image21-bis.png) Figure 9-22.</span></span> <span data-ttu-id="c2a74-176">Referencias de paquetes NuGet de la API MongoDB en un proyecto de .NET Core</span><span class="sxs-lookup"><span data-stu-id="c2a74-176">MongoDB API NuGet packages references in a .NET Core project</span></span>

<span data-ttu-id="c2a74-177">En las secciones siguientes investigaremos el código.</span><span class="sxs-lookup"><span data-stu-id="c2a74-177">Let's investigate the code in the following sections.</span></span>

#### <a name="a-model-used-by-mongodb-api"></a><span data-ttu-id="c2a74-178">Un modelo usado por la API de MongoDB</span><span class="sxs-lookup"><span data-stu-id="c2a74-178">A Model used by MongoDB API</span></span>

<span data-ttu-id="c2a74-179">En primer lugar, debe definir un modelo que contendrá los datos procedentes de la base de datos en el espacio de memoria de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c2a74-179">First, you need to define a model that will hold the data coming from the database in your application’s memory space.</span></span> <span data-ttu-id="c2a74-180">Este es un ejemplo del modelo que se usa para Locations en eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="c2a74-180">Here’s an example of the model used for Locations at eShopOnContainers.</span></span>

```csharp
using MongoDB.Bson;
using MongoDB.Bson.Serialization.Attributes;
using MongoDB.Driver.GeoJsonObjectModel;
using System.Collections.Generic;

public class Locations
{
    [BsonId]
    [BsonRepresentation(BsonType.ObjectId)]
    public string Id { get; set; }
    public int LocationId { get; set; }
    public string Code { get; set; }
    [BsonRepresentation(BsonType.ObjectId)]
    public string Parent_Id { get; set; }
    public string Description { get; set; }
    public double Latitude { get; set; }
    public double Longitude { get; set; }
    public GeoJsonPoint<GeoJson2DGeographicCoordinates> Location 
                                                             { get; private set; }
    public GeoJsonPolygon<GeoJson2DGeographicCoordinates> Polygon 
                                                             { get; private set; }
    public void SetLocation(double lon, double lat) => SetPosition(lon, lat);
    public void SetArea(List<GeoJson2DGeographicCoordinates> coordinatesList) 
                                                    => SetPolygon(coordinatesList);

    private void SetPosition(double lon, double lat)
    {
        Latitude = lat;
        Longitude = lon;
        Location = new GeoJsonPoint<GeoJson2DGeographicCoordinates>(
            new GeoJson2DGeographicCoordinates(lon, lat));
    }

    private void SetPolygon(List<GeoJson2DGeographicCoordinates> coordinatesList)
    {
        Polygon = new GeoJsonPolygon<GeoJson2DGeographicCoordinates>(
                  new GeoJsonPolygonCoordinates<GeoJson2DGeographicCoordinates>(
                  new GeoJsonLinearRingCoordinates<GeoJson2DGeographicCoordinates>(
                                                                 coordinatesList)));
    }
}
```

<span data-ttu-id="c2a74-181">Puede ver que hay unos cuantos atributos y tipos procedentes de los paquetes NuGet de MongoDB.</span><span class="sxs-lookup"><span data-stu-id="c2a74-181">You can see there are a few attributes and types coming from the MongoDB NuGet packages.</span></span>

<span data-ttu-id="c2a74-182">Las bases de datos NoSQL suelen ser muy adecuadas para trabajar con datos jerárquicos no relacionales.</span><span class="sxs-lookup"><span data-stu-id="c2a74-182">NoSQL databases are usually very well suited for working with non-relational hierarchical data.</span></span> <span data-ttu-id="c2a74-183">En este ejemplo utilizamos tipos de MongoDB especiales para ubicaciones geográficas, como `GeoJson2DGeographicCoordinates`.</span><span class="sxs-lookup"><span data-stu-id="c2a74-183">In this example, we are using MongoDB types expecially made for geo-locations, like `GeoJson2DGeographicCoordinates`.</span></span>

#### <a name="retrieve-the-database-and-the-collection"></a><span data-ttu-id="c2a74-184">Recuperación de la base de datos y la colección</span><span class="sxs-lookup"><span data-stu-id="c2a74-184">Retrieve the database and the collection</span></span>

<span data-ttu-id="c2a74-185">En eShopOnContainers, hemos creado un contexto de base de datos personalizado donde implementamos el código para recuperar la base de datos y MongoCollections, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="c2a74-185">In eShopOnContainers, we have created a custom database context where we implement the code to retrieve the database and the MongoCollections, as in the following code.</span></span>

```csharp
public class LocationsContext
{
    private readonly IMongoDatabase _database = null;

    public LocationsContext(IOptions<LocationSettings> settings)
    {
        var client = new MongoClient(settings.Value.ConnectionString);
        if (client != null)
            _database = client.GetDatabase(settings.Value.Database);
    }

    public IMongoCollection<Locations> Locations
    {
        get
        {
            return _database.GetCollection<Locations>("Locations");
        }
    }       
}
```

#### <a name="retrieve-the-data"></a><span data-ttu-id="c2a74-186">Recuperación de los datos</span><span class="sxs-lookup"><span data-stu-id="c2a74-186">Retrieve the data</span></span>

<span data-ttu-id="c2a74-187">En código C#, al igual que con controladores de API Web o implementación de repositorios personalizada, puede escribir un código similar al siguiente al consultar a través de la API de MongoDB.</span><span class="sxs-lookup"><span data-stu-id="c2a74-187">In C# code, like Web API controllers or custom Repositories implementation, you can write similar code to the following when querying through the MongoDB API.</span></span> <span data-ttu-id="c2a74-188">Tenga en cuenta que el objeto `_context` es una instancia de la clase `LocationsContext` anterior.</span><span class="sxs-lookup"><span data-stu-id="c2a74-188">Note that the `_context` object is an instance of the previous `LocationsContext` class.</span></span>

```csharp
public async Task<Locations> GetAsync(int locationId)
{
    var filter = Builders<Locations>.Filter.Eq("LocationId", locationId);
    return await _context.Locations
                            .Find(filter)
                            .FirstOrDefaultAsync();
}
```

#### <a name="use-an-env-var-in-the-docker-composeoverrideyml-file-for-the-mongodb-connection-string"></a><span data-ttu-id="c2a74-189">Uso de env-var en el archivo docker-compose.override.yml para la cadena de conexión de MongoDB</span><span class="sxs-lookup"><span data-stu-id="c2a74-189">Use an env-var in the docker-compose.override.yml file for the MongoDB connection string</span></span>

<span data-ttu-id="c2a74-190">Al crear un objeto MongoClient, se necesita un parámetro fundamental que es precisamente el parámetro `ConnectionString` que apunta a la base de datos correcta.</span><span class="sxs-lookup"><span data-stu-id="c2a74-190">When creating a MongoClient object, it needs a fundamental parameter which is precisely the `ConnectionString` parameter pointing to the right database.</span></span> <span data-ttu-id="c2a74-191">En el caso de eShopOnContainers, la cadena de conexión puede apuntar a un contenedor local de MongoDB Docker local o a una base de datos de "producción" de Azure Cosmos DB.</span><span class="sxs-lookup"><span data-stu-id="c2a74-191">In the case of eShopOnContainers, the connection string can point to a local MongoDB Docker container or to a “production” Azure Cosmos DB database.</span></span>  <span data-ttu-id="c2a74-192">Esa cadena de conexión procede de las variables de entorno definidas en los archivos `docker-compose.override.yml` que se utilizan al implementar con docker-compose o Visual Studio, como se muestra en el siguiente código yml.</span><span class="sxs-lookup"><span data-stu-id="c2a74-192">That connection string comes from the environment variables defined in the `docker-compose.override.yml` files used when deploying with docker-compose or Visual Studio, as in the following yml code.</span></span>

```yml
# docker-compose.override.yml
version: '3'
services:
  # Other services
  locations.api:
    environment:
      # Other settings
      - ConnectionString=${ESHOP_AZURE_COSMOSDB:-mongodb://nosql.data}

```

<span data-ttu-id="c2a74-193">La variable de entorno `ConnectionString` se resuelve de esta manera: si la variable global `ESHOP_AZURE_COSMOSDB` está definida en el archivo `.env` con la cadena de conexión de Azure Cosmos DB, la utilizará para acceder a la base de datos de Azure Cosmos DB en la nube.</span><span class="sxs-lookup"><span data-stu-id="c2a74-193">The `ConnectionString` environment variable is resolved this way: If the `ESHOP_AZURE_COSMOSDB` global variable is defined in the `.env` file with the Azure Cosmos DB connection string, it will use it to access the Azure Cosmos DB database in the cloud.</span></span> 

<span data-ttu-id="c2a74-194">El código siguiente muestra el archivo `.env` con la variable de entorno global de cadena de conexión de Azure Cosmos DB, tal y como se implementa en eShopOnContainers:</span><span class="sxs-lookup"><span data-stu-id="c2a74-194">The following code shows the `.env` file with the Azure Cosmos DB connection string global environment variable, as implemented in eShopOnContainers:</span></span>

```yml
# .env file, in eShopOnContainers root folder
# Other Docker environment variables

ESHOP_EXTERNAL_DNS_NAME_OR_IP=localhost
ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP=<YourDockerHostIP>

#ESHOP_AZURE_COSMOSDB=<YourAzureCosmosDBConnData>

#Other environment variables for additional Azure infrastructure assets
#ESHOP_AZURE_REDIS_BASKET_DB=<YourAzureRedisBasketInfo>
#ESHOP_AZURE_STORAGE_CATALOG_URL=<YourAzureStorage_Catalog_BLOB_URL>
#ESHOP_AZURE_SERVICE_BUS=<YourAzureServiceBusInfo>
```

<span data-ttu-id="c2a74-195">Debe quitar la marca de comentario de la línea ESHOP_AZURE_COSMOSDB y actualizarla con su cadena de conexión de Azure Cosmos DB obtenida en Azure Portal como se explica en [Conectar una aplicación de MongoDB a Azure Cosmos DB](https://docs.microsoft.com/en-us/azure/cosmos-db/connect-mongodb-account).</span><span class="sxs-lookup"><span data-stu-id="c2a74-195">You should uncomment the ESHOP_AZURE_COSMOSDB line and update it with your Azure Cosmos DB connection string obtained from the Azure portal as explained in [Connect a MongoDB application to Azure Cosmos DB](https://docs.microsoft.com/en-us/azure/cosmos-db/connect-mongodb-account).</span></span>

<span data-ttu-id="c2a74-196">Si la variable global `ESHOP_AZURE_COSMOSDB` está vacía, lo que significa que la marca de comentario se ha quitado del archivo `.env`, entonces el contenedor usa una cadena de conexión de MongoDB predeterminada que apunta al contenedor de MongoDB local implementado en eShopOnContainers que se denomina `nosql.data`, tal y como se muestra en el siguiente código .yml.</span><span class="sxs-lookup"><span data-stu-id="c2a74-196">If the `ESHOP_AZURE_COSMOSDB` global variable is empty, meaning that it is commented out in the `.env` file, then the container uses a default MongoDB connection string pointing to the local MongoDB container deployed in eShopOnContainers which is named `nosql.data`, as shown in the following .yml code.</span></span> 

#### <a name="additional-resources"></a><span data-ttu-id="c2a74-197">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c2a74-197">Additional resources</span></span>

-   <span data-ttu-id="c2a74-198">**Modelado de datos del documento para bases de datos NoSQL**
    [*https://docs.microsoft.com/es-es/azure/cosmos-db/modeling-data*](https://docs.microsoft.com/en-us/azure/cosmos-db/modeling-data)</span><span class="sxs-lookup"><span data-stu-id="c2a74-198">**Modeling document data for NoSQL databases**
[*https://docs.microsoft.com/en-us/azure/cosmos-db/modeling-data*](https://docs.microsoft.com/en-us/azure/cosmos-db/modeling-data)</span></span>

-   <span data-ttu-id="c2a74-199">**Vaughn Vernon. The Ideal Domain-Driven Design Aggregate Store?** (¿El almacén de agregado ideal de diseño controlado por dominio?)
    [*https://vaughnvernon.co/?p=942*](https://vaughnvernon.co/?p=942)</span><span class="sxs-lookup"><span data-stu-id="c2a74-199">**Vaughn Vernon. The Ideal Domain-Driven Design Aggregate Store?**
[*https://vaughnvernon.co/?p=942*](https://vaughnvernon.co/?p=942)</span></span>

-   <span data-ttu-id="c2a74-200">**Introducción a Azure Cosmos DB: API para MongoDB** 
    [*https://docs.microsoft.com/es-es/azure/cosmos-db/mongodb-introduction*](https://docs.microsoft.com/en-us/azure/cosmos-db/mongodb-introduction)</span><span class="sxs-lookup"><span data-stu-id="c2a74-200">**Introduction to Azure Cosmos DB: API for MongoDB** 
[*https://docs.microsoft.com/en-us/azure/cosmos-db/mongodb-introduction*](https://docs.microsoft.com/en-us/azure/cosmos-db/mongodb-introduction)</span></span>

-   <span data-ttu-id="c2a74-201">**Azure Cosmos DB: Compilar una aplicación web de API MongoDB con .NET y Azure Portal** 
    [* https://docs.microsoft.com/es-es/azure/cosmos-db/create-mongodb-dotnet *](https://docs.microsoft.com/en-us/azure/cosmos-db/create-mongodb-dotnet )</span><span class="sxs-lookup"><span data-stu-id="c2a74-201">**Azure Cosmos DB: Build a MongoDB API web app with .NET and the Azure portal** 
[*https://docs.microsoft.com/en-us/azure/cosmos-db/create-mongodb-dotnet *](https://docs.microsoft.com/en-us/azure/cosmos-db/create-mongodb-dotnet )</span></span>

-   <span data-ttu-id="c2a74-202">**Uso del Emulador de Azure Cosmos DB para desarrollo y pruebas de forma local** 
    [*https://docs.microsoft.com/es-es/azure/cosmos-db/local-emulator*](https://docs.microsoft.com/en-us/azure/cosmos-db/local-emulator)</span><span class="sxs-lookup"><span data-stu-id="c2a74-202">**Use the Azure Cosmos DB Emulator for local development and testing** 
[*https://docs.microsoft.com/en-us/azure/cosmos-db/local-emulator*](https://docs.microsoft.com/en-us/azure/cosmos-db/local-emulator)</span></span>

-   <span data-ttu-id="c2a74-203">**Conectar una aplicación de MongoDB a Azure Cosmos DB** 
    [*https://docs.microsoft.com/es-es/azure/cosmos-db/connect-mongodb-account*](https://docs.microsoft.com/en-us/azure/cosmos-db/connect-mongodb-account)</span><span class="sxs-lookup"><span data-stu-id="c2a74-203">**Connect a MongoDB application to Azure Cosmos DB** 
[*https://docs.microsoft.com/en-us/azure/cosmos-db/connect-mongodb-account*](https://docs.microsoft.com/en-us/azure/cosmos-db/connect-mongodb-account)</span></span>

-   <span data-ttu-id="c2a74-204">**Imagen de Docker de Emulador de Cosmos DB (contenedor de Windows)** 
    [*https://hub.docker.com/r/microsoft/azure-cosmosdb-emulator/*](https://hub.docker.com/r/microsoft/azure-cosmosdb-emulator/)</span><span class="sxs-lookup"><span data-stu-id="c2a74-204">**The Cosmos DB Emulator Docker image (Windows Container)** 
[*https://hub.docker.com/r/microsoft/azure-cosmosdb-emulator/*](https://hub.docker.com/r/microsoft/azure-cosmosdb-emulator/)</span></span>

-   <span data-ttu-id="c2a74-205">**Imagen de Docker de MongoDB (contenedor Linux y Windows)** 
    [*https://hub.docker.com/r/_/mongo/*](https://hub.docker.com/r/_/mongo/)</span><span class="sxs-lookup"><span data-stu-id="c2a74-205">**The MongoDB Docker image (Linux and Windows Container)** 
[*https://hub.docker.com/r/_/mongo/*](https://hub.docker.com/r/_/mongo/)</span></span>

-   <span data-ttu-id="c2a74-206">**Azure Cosmos DB: Uso de Studio 3T con una cuenta de MongoDB API** 
    [*https://docs.microsoft.com/es-es/azure/cosmos-db/mongodb-mongochef*](https://docs.microsoft.com/en-us/azure/cosmos-db/mongodb-mongochef)</span><span class="sxs-lookup"><span data-stu-id="c2a74-206">**Use MongoChef (Studio 3T) with an Azure Cosmos DB: API for MongoDB account** 
[*https://docs.microsoft.com/en-us/azure/cosmos-db/mongodb-mongochef*](https://docs.microsoft.com/en-us/azure/cosmos-db/mongodb-mongochef)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="c2a74-207">[Anterior] (infrastructure-persistence-layer-implemenation-entity-framework-core.md) [Siguiente] (microservice-application-layer-web-api-design.md)</span><span class="sxs-lookup"><span data-stu-id="c2a74-207">[Previous] (infrastructure-persistence-layer-implemenation-entity-framework-core.md) [Next] (microservice-application-layer-web-api-design.md)</span></span>
