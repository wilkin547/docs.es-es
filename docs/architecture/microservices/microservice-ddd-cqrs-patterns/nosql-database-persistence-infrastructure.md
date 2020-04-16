---
title: Uso de bases de datos NoSQL como una infraestructura de persistencia
description: Obtenga más información sobre el uso de bases de datos NoSql en general, y Azure Cosmos DB en concreto, como una opción para implementar la persistencia.
ms.date: 01/30/2020
ms.openlocfilehash: 9c51e48d82aa0cf0234275f09df43f7a654f0ca8
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988445"
---
# <a name="use-nosql-databases-as-a-persistence-infrastructure"></a>Uso de bases de datos NoSQL como una infraestructura de persistencia

Cuando se usan bases de datos NoSQL para el nivel de datos de infraestructura, normalmente no se utiliza un ORM como Entity Framework Core. En su lugar, se utiliza la API proporcionada por el motor de NoSQL, como por ejemplo Azure Cosmos DB, MongoDB, Cassandra, RavenDB, CouchDB o tablas de Azure Storage.

Pero cuando se usa una base de datos NoSQL, especialmente una orientada a documentos como Azure Cosmos DB, CouchDB o RavenDB, la forma de diseñar el modelo con agregados DDD es parcialmente similar a cómo se puede hacer en EF Core, en lo que respecta a la identificación de las raíces agregadas, las clases de entidad secundarias y las clases de objeto de valor. Pero, en última instancia, la selección de la base de datos afectará al diseño.

Cuando utilice una base de datos orientada a documentos, implemente un agregado como un solo documento serializado en JSON o en otro formato. Pero el uso de la base de datos es transparente desde un punto de vista del código de dominio de modelo. Cuando se usa una base de datos NoSQL, también se utilizan las clases de entidad y las clases raíz de agregado, pero con más flexibilidad que cuando se usa EF Core porque la persistencia no es relacional.

La diferencia radica en cómo se persiste ese modelo. Si implementa el modelo de dominio basándose en las clases de entidad POCO, independientemente de la persistencia de la infraestructura, quizá parezca que puede cambiar a una infraestructura de persistencia diferente, incluso desde relacional a NoSQL. Pero ese no debería ser el objetivo. Siempre hay restricciones y contrapartidas en las diferentes tecnologías de bases de datos, por lo que no se podrá tener el mismo modelo para bases de datos relacionales o NoSQL. Cambiar modelos de persistencia tiene su importancia, dado que las transacciones y las operaciones de persistencia serán muy diferentes.

Por ejemplo, en una base de datos orientada a documentos, es correcto que una raíz agregada tenga varias propiedades de colección secundaria. En una base de datos relacional, consultar varias propiedades de colección secundaria no está bien optimizado, porque se recibe una instrucción UNION ALL SQL de EF. Tener el mismo modelo de dominio para bases de datos relacionales o bases de datos NoSQL no es sencillo y no debería intentarse. El modelo debe diseñarse entendiendo el uso que se va a hacer de los datos en cada base de datos en particular.

Una ventaja de utilizar las bases de datos NoSQL es que las entidades estén menos normalizadas, por lo que no se establece una asignación de tabla. El modelo de dominio puede ser más flexible que al utilizar una base de datos relacional.

Al diseñar el modelo de dominio basándose en agregados, el cambio a bases de datos NoSQL y orientadas a documentos podría ser incluso más sencillo que usar una base de datos relacional, puesto que los agregados que se diseñan son similares a documentos serializados en una base de datos orientada a documentos. Luego puede incluir en esas "bolsas" toda la información que necesite para ese agregado.

Por ejemplo, el siguiente código JSON es una implementación de ejemplo de un agregado de pedido cuando se usa una base de datos orientada a documentos. Es similar al orden agregado de pedido que implementamos en el ejemplo eShopOnContainers, pero sin utilizar EF Core debajo.

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

## <a name="introduction-to-azure-cosmos-db-and-the-native-cosmos-db-api"></a>Introducción a Azure Cosmos DB y la API Cosmos DB nativa

[Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/introduction) es el servicio de base de datos distribuida globalmente de Microsoft para aplicaciones críticas. Azure Cosmos DB proporciona [distribución global inmediata](https://docs.microsoft.com/azure/cosmos-db/distribute-data-globally), [escalado flexible de rendimiento y almacenamiento](https://docs.microsoft.com/azure/cosmos-db/partition-data) en todo el mundo, latencias de milisegundo de un solo dígito en el percentil 99, [cinco niveles de coherencia bien definidos](https://docs.microsoft.com/azure/cosmos-db/consistency-levels) y alta disponibilidad garantizada, todo ello respaldado por [los mejores SLA del sector](https://azure.microsoft.com/support/legal/sla/cosmos-db/). Azure Cosmos DB [indiza automáticamente los datos](https://www.vldb.org/pvldb/vol8/p1668-shukla.pdf) sin necesidad de administrar el esquema y el índice. Es multimodelo y admite modelos de datos de documentos, clave-valor, gráfico y columnas.

![Diagrama que muestra la distribución global de Azure Cosmos DB.](./media/nosql-database-persistence-infrastructure/azure-cosmos-db-global-distribution.png)

**Figura 7-19**. Distribución global de Azure Cosmos DB

Cuando se usa un modelo C\# para implementar el agregado que va a usar la API de Azure Cosmos DB, el agregado puede ser similar a las clases POCO de C\# que se usan con EF Core. La diferencia radica en la forma de usarlos desde la aplicación y las capas de la infraestructura, como en el código siguiente:

```csharp
// C# EXAMPLE OF AN ORDER AGGREGATE BEING PERSISTED WITH AZURE COSMOS DB API
// *** Domain Model Code ***
// Aggregate: Create an Order object with its child entities and/or value objects.
// Then, use AggregateRoot's methods to add the nested objects so invariants and
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

Puede ver que la forma de trabajar con el modelo de dominio puede ser similar a la manera en que se utiliza en la capa de modelo de dominio cuando la infraestructura es EF. Se siguen usando los mismos métodos raíz de agregación para garantizar la coherencia, las invariantes y las validaciones en el agregado.

Pero cuando se persiste el modelo en la base de datos NoSQL, el código y la API cambian drásticamente en comparación con el código de EF Core o cualquier otro código relacionado con las bases de datos relacionales.

## <a name="implement-net-code-targeting-mongodb-and-azure-cosmos-db"></a>Implementación de código de .NET destinado a MongoDB y Azure Cosmos DB

### <a name="use-azure-cosmos-db-from-net-containers"></a>Uso de Azure Cosmos DB desde contenedores de .NET

Se puede acceder a las bases de datos de Azure Cosmos DB desde código de .NET que se ejecuta en contenedores, como en cualquier otra aplicación. NET. Por ejemplo, los microservicios Locations.API y Marketing.API de eShopOnContainers se implementan para que puedan utilizar las bases de datos de Azure Cosmos DB.

Pero hay una limitación en Azure Cosmos DB desde un punto de vista del entorno de desarrollo Docker. Aunque hay un [emulador de Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/local-emulator) local que se puede ejecutar en una máquina de desarrollo local, este solo es compatible con Windows. No se admiten Linux ni macOS.

También existe la posibilidad de ejecutar este emulador en Docker, pero solo en los contenedores de Windows, no en los de Linux. Eso es un impedimento inicial para el entorno de desarrollo si la aplicación se implementa como contenedores de Linux, puesto que actualmente no es posible implementar al mismo tiempo contenedores de Windows y Linux en Docker para Windows. Todos los contenedores que se implementen tienen que ser de Linux o de Windows.

La implementación ideal y más sencilla para una solución de desarrollo o pruebas consiste en ser capaz de implementar los sistemas de base de datos como contenedores junto con los contenedores personalizados para que sus entornos de desarrollo o pruebas sean siempre coherentes.

### <a name="use-mongodb-api-for-local-devtest-linuxwindows-containers-plus-azure-cosmos-db"></a>Uso de la API de MongoDB para contenedores locales de desarrollo o pruebas de Linux y Windows además de Azure Cosmos DB

Las bases de datos de COSMOS DB son compatibles con la API de MongoDB para. NET, además de con el protocolo de conexión de MongoDB nativo. Esto significa que, mediante los controladores existentes, la aplicación escrita para MongoDB ahora puede comunicarse con Cosmos DB y usar las bases de datos de Cosmos DB en lugar de las bases de datos de MongoDB, como se muestra en la figura 7-20.

![Diagrama que muestra que Cosmos DB admite .NET y el protocolo de conexión de MongoDB.](./media/nosql-database-persistence-infrastructure/mongodb-api-wire-protocol.png)

**Figura 7-20.** Uso de la API de MongoDB y el protocolo para acceder Azure Cosmos DB

Esto es un método muy práctico para la prueba de conceptos en entornos de Docker con contenedores Linux porque la [imagen de MongoDB Docker](https://hub.docker.com/r/_/mongo/) es una imagen multiarquitectura que admite contenedores de Docker de Linux y Windows.

Como se muestra en la siguiente imagen, mediante la API de MongoDB, eShopOnContainers admite contenedores de MongoDB de Linux y Windows para el entorno de desarrollo local. Después, puede mover a una solución de nube PaaS escalable como Azure Cosmos DB simplemente [cambiando la cadena de conexión de MongoDB para que apunte a Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/connect-mongodb-account).

![Diagrama que muestra que el microservicio Location de eShopOnContainers puede usar Cosmos DB o Mongo DB.](./media/nosql-database-persistence-infrastructure/eshoponcontainers-mongodb-containers.png)

**Figura 7-21**. eShopOnContainers con contenedores de MongoDB para desarrollo o entorno o Azure Cosmos DB para producción

La base de datos Azure Cosmos DB de producción se ejecuta en la nube de Azure como servicio escalable y de PaaS.

Los contenedores de .NET Core personalizados pueden ejecutarse en un host Docker de desarrollo local (es decir, con Docker para Windows en un equipo Windows 10) o implementarse en un entorno de producción, como Kubernetes en Azure AKS o Azure Service Fabric. En este segundo entorno, implemente solo los contenedores personalizados de .NET Core, pero no el contenedor de MongoDB ya que usaría Azure Cosmos DB en la nube para controlar los datos de producción.

Una ventaja evidente de utilizar la API de MongoDB es que la solución puede ejecutarse en dos motores de base de datos, MongoDB o Azure Cosmos DB, por lo que sería fácil migrar a otros entornos. Pero en ocasiones merece la pena usar una API nativa (es decir, la API de Cosmos DB nativa) con el fin de aprovechar al máximo las capacidades de un determinado motor de base de datos.

Para comparar el uso de MongoDB frente a Cosmos DB en la nube, consulte las [ventajas de usar Azure Cosmos DB en esta página](https://docs.microsoft.com/azure/cosmos-db/mongodb-introduction).

### <a name="analyze-your-approach-for-production-applications-mongodb-api-vs-cosmos-db-api"></a>Análisis del enfoque para aplicaciones de producción: API de MongoDB frente a API de Cosmos DB

En eShopOnContainers, usamos API de MongoDB porque nuestra prioridad era fundamentalmente tener un entorno de desarrollo o pruebas coherente con una base de datos NoSQL que también pudiese funcionar con Azure Cosmos DB.

Pero si se pretende utilizar la API de MongoDB para tener acceso a Azure Cosmos DB en aplicaciones de Azure para producción, se deben analizar y comparar las diferencias entre las capacidades y el rendimiento al usar la API de MongoDB para acceder a las bases de datos de Azure Cosmos DB y usar la API de Azure Cosmos DB nativa. Si el resultado es similar, se puede utilizar la API de MongoDB, con la ventaja de admitir dos motores de base de datos NoSQL al mismo tiempo.

También podría utilizar clústeres de MongoDB como base de datos de producción en la nube de Azure, con [MongoDB Azure Service](https://www.mongodb.com/scale/mongodb-azure-service). Pero eso no es un servicio PaaS proporcionado por Microsoft. En este caso, Azure solo hospeda la solución procedente de MongoDB.

Básicamente, esto es simplemente una declinación de responsabilidades que indica que no debe usar siempre la API de MongoDB en Azure Cosmos DB, como hicimos en eShopOnContainers, puesto que se trataba de una opción conveniente para los contenedores de Linux. La decisión debe basarse en las necesidades específicas y las pruebas que deba hacer en la aplicación de producción.

### <a name="the-code-use-mongodb-api-in-net-core-applications"></a>El código: uso de la API de MongoDB en aplicaciones .NET Core

La API de MongoDB para .NET se basa en los paquetes NuGet que debe agregar a los proyectos, como en el proyecto Locations.API que se muestra en la siguiente imagen.

![Captura de pantalla de las dependencias de los paquetes de NuGet de MongoDB.](./media/nosql-database-persistence-infrastructure/mongodb-api-nuget-packages.png)

**Figura 7-22**. Referencias de paquetes NuGet de la API MongoDB en un proyecto de .NET Core

En las secciones siguientes investigaremos el código.

#### <a name="a-model-used-by-mongodb-api"></a>Un modelo usado por la API de MongoDB

En primer lugar, debe definir un modelo que contendrá los datos procedentes de la base de datos en el espacio de memoria de la aplicación. Este es un ejemplo del modelo que se usa para Locations en eShopOnContainers.

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

Puede ver que hay unos cuantos atributos y tipos procedentes de los paquetes NuGet de MongoDB.

Las bases de datos NoSQL suelen ser muy adecuadas para trabajar con datos jerárquicos no relacionales. En este ejemplo se usan tipos de MongoDB especiales para ubicaciones geográficas, como `GeoJson2DGeographicCoordinates`.

#### <a name="retrieve-the-database-and-the-collection"></a>Recuperación de la base de datos y la colección

En eShopOnContainers, hemos creado un contexto de base de datos personalizado donde implementamos el código para recuperar la base de datos y MongoCollections, como se muestra en el código siguiente.

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

#### <a name="retrieve-the-data"></a>Recuperación de los datos

En código C#, al igual que con controladores de API Web o implementación de repositorios personalizada, puede escribir un código similar al siguiente al consultar a través de la API de MongoDB. Tenga en cuenta que el objeto `_context` es una instancia de la clase `LocationsContext` anterior.

```csharp
public async Task<Locations> GetAsync(int locationId)
{
    var filter = Builders<Locations>.Filter.Eq("LocationId", locationId);
    return await _context.Locations
                            .Find(filter)
                            .FirstOrDefaultAsync();
}
```

#### <a name="use-an-env-var-in-the-docker-composeoverrideyml-file-for-the-mongodb-connection-string"></a>Uso de env-var en el archivo docker-compose.override.yml para la cadena de conexión de MongoDB

Al crear un objeto MongoClient, se necesita un parámetro fundamental que es precisamente el parámetro `ConnectionString` que apunta a la base de datos correcta. En el caso de eShopOnContainers, la cadena de conexión puede apuntar a un contenedor local de MongoDB Docker local o a una base de datos de "producción" de Azure Cosmos DB.  Esa cadena de conexión procede de las variables de entorno definidas en los archivos `docker-compose.override.yml` que se utilizan al implementar con docker-compose o Visual Studio, como se muestra en el siguiente código yml.

```yml
# docker-compose.override.yml
version: '3.4'
services:
  # Other services
  locations-api:
    environment:
      # Other settings
      - ConnectionString=${ESHOP_AZURE_COSMOSDB:-mongodb://nosqldata}

```

La variable de entorno `ConnectionString` se resuelve de esta manera: si la variable global `ESHOP_AZURE_COSMOSDB` está definida en el archivo `.env` con la cadena de conexión de Azure Cosmos DB, la usará para acceder a la base de datos de Azure Cosmos DB en la nube. Si no está definida, tomará el valor `mongodb://nosqldata` y usará el contenedor MongoDB de desarrollo.

El código siguiente muestra el archivo `.env` con la variable de entorno global de cadena de conexión de Azure Cosmos DB, tal y como se implementa en eShopOnContainers:

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

Quite la marca de comentario de la línea ESHOP_AZURE_COSMOSDB y actualícela con su cadena de conexión de Azure Cosmos DB obtenida en Azure Portal como se explica en [Conectar una aplicación de MongoDB a Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/connect-mongodb-account).

Si la variable global `ESHOP_AZURE_COSMOSDB` está vacía, lo que significa que se comenta en el archivo `.env`, el contenedor usará una cadena de conexión de MongoDB predeterminada. Esta cadena de conexión apunta al contenedor de MongoDB local implementado en eShopOnContainers denominado `nosqldata` y definido en el archivo Docker-Compose, como se muestra en el siguiente código .yml:

``` yml
# docker-compose.yml
version: '3.4'
services:
  # ...Other services...
  nosqldata:
    image: mongo
```

#### <a name="additional-resources"></a>Recursos adicionales

- **Modelado de datos del documento para bases de datos NoSQL** \
  <https://docs.microsoft.com/azure/cosmos-db/modeling-data>

- **Vaughn Vernon. The Ideal Domain-Driven Design Aggregate Store?** (¿El almacén de agregado ideal de diseño controlado por dominio?) \
  <https://kalele.io/blog-posts/the-ideal-domain-driven-design-aggregate-store/>

- **Introducción a Azure Cosmos DB: API de MongoDB**  \
  <https://docs.microsoft.com/azure/cosmos-db/mongodb-introduction>

- **Azure Cosmos DB: Compilación de una aplicación web mediante la API de MongoDB con .NET y Azure Portal**  \
  <https://docs.microsoft.com/azure/cosmos-db/create-mongodb-dotnet>

- **Uso del Emulador de Azure Cosmos DB para desarrollo y pruebas de forma local**  \
  <https://docs.microsoft.com/azure/cosmos-db/local-emulator>

- **Conectar una aplicación de MongoDB a Azure Cosmos DB**  \
  <https://docs.microsoft.com/azure/cosmos-db/connect-mongodb-account>

- **Imagen de Docker del Emulador de Cosmos DB (contenedor Windows)**   \
  <https://hub.docker.com/r/microsoft/azure-cosmosdb-emulator/>

- **Imagen de Docker de MongoDB (contenedor Linux y Windows)**   \
  <https://hub.docker.com/_/mongo/>

- **Azure Cosmos DB: Uso de MongoChef (Studio 3T) con una cuenta de la API de MongoDB**  \
  <https://docs.microsoft.com/azure/cosmos-db/mongodb-mongochef>

>[!div class="step-by-step"]
>[Anterior](infrastructure-persistence-layer-implemenation-entity-framework-core.md)
>[Siguiente](microservice-application-layer-web-api-design.md)
