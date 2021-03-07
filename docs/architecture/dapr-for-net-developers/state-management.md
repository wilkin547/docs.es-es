---
title: El bloque de creación de administración de estado de DAPR
description: Una descripción del bloque de creación de la administración de estado, sus características, ventajas y cómo aplicarla.
author: amolenk
ms.date: 02/07/2021
ms.reviewer: robvet
ms.openlocfilehash: 05daf18ece1da377f3d5d6a91c4839f196f14f80
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401836"
---
# <a name="the-dapr-state-management-building-block"></a>El bloque de creación de administración de estado de DAPR

Las aplicaciones distribuidas se componen de servicios independientes. Aunque cada servicio no debe tener estado, algunos servicios deben hacer un seguimiento del estado para completar las operaciones empresariales. Considere la posibilidad de usar un servicio de cesta de la compra para un sitio de comercio electrónico. Si el servicio no puede realizar un seguimiento del estado, el cliente podría perder el contenido de la cesta de la compra abandonando el sitio web, lo que da lugar a una venta perdida y una experiencia descontento del cliente. En estos casos, el estado debe conservarse en un almacén de estado distribuido. El [bloque de creación de administración de estado de DAPR](https://docs.dapr.io/developing-applications/building-blocks/state-management/) simplifica el seguimiento de estado y ofrece características avanzadas en varios almacenes de datos.

Para probar el bloque de creación de la administración de estado, consulte el [ejemplo de aplicación Counter en el capítulo 3](getting-started.md).

## <a name="what-it-solves"></a>Qué resuelve

El estado de seguimiento en una aplicación distribuida puede ser desafiante. Por ejemplo:

- La aplicación puede requerir distintos tipos de almacenes de datos.
- Pueden requerirse diferentes niveles de coherencia para obtener acceso a los datos y actualizarlos.
- Varios usuarios pueden actualizar los datos al mismo tiempo, lo que requiere una resolución de conflictos.
- Los servicios deben Reintentar cualquier [error transitorio](/aspnet/aspnet/overview/developing-apps-with-windows-azure/building-real-world-cloud-apps-with-windows-azure/transient-fault-handling) de corta duración que se produzca al interactuar con el almacén de datos.

El bloque de creación de administración de estado de DAPR aborda estos desafíos. Optimiza el estado de seguimiento sin dependencias ni con una curva de aprendizaje en SDK de almacenamiento de terceros.

> [!IMPORTANT]
> La administración de estado de DAPR ofrece una API de [clave/valor](/azure/architecture/guide/technology-choices/data-store-overview#keyvalue-stores) . La característica no admite el almacenamiento de datos relacionales o de gráficos.

## <a name="how-it-works"></a>Funcionamiento

La aplicación interactúa con un sidecar de DAPR para almacenar y recuperar datos de clave/valor. En el capó, la API sidecar consume un componente de almacén de estado configurable para conservar los datos. Los desarrolladores pueden elegir entre una creciente colección de [almacenes de Estados compatibles](https://docs.dapr.io/operations/components/setup-state-store/supported-state-stores/) que incluyen Azure Cosmos DB, SQL Server y Cassandra.

Se puede llamar a la API con HTTP o gRPC. Use la siguiente dirección URL para llamar a la API HTTP:

```http
http://localhost:<dapr-port>/v1.0/state/<store-name>/
```

- `<dapr-port>`: el puerto HTTP en el que escucha DAPR.
- `<store-name>`: nombre del componente de almacén de estado que se va a usar.

En la figura 5-1 se muestra cómo un servicio de cesta de la compra habilitado para DAPR almacena un par clave-valor mediante el componente de almacén de estado DAPR denominado `statestore` .

![Diagrama de almacenamiento de un par clave-valor en un almacén de estado de DAPR.](media/state-management/state-management-flow.png)

**Figura 5-1**. Almacenar un par clave-valor en un almacén de estado de DAPR.

Tenga en cuenta los pasos de la ilustración anterior:

1. El servicio de cesta llama a la API de administración de estado en el sidecar de DAPR. El cuerpo de la solicitud incluye una matriz JSON que puede contener varios pares clave-valor.
1. El sidecar de DAPR determina el almacén de estado en función del archivo de configuración de componentes. En este caso, es un almacén de estado de caché en Redis.
1. El sidecar conserva los datos en la caché en Redis.

La recuperación de los datos almacenados es una llamada de API similar. En el ejemplo siguiente, un comando de *rizo* recupera los datos mediante una llamada a la API de DAPR sidecar:

```console
curl http://localhost:3500/v1.0/state/statestore/basket1
```

El comando devuelve el estado almacenado en el cuerpo de la respuesta:

```json
{
  "items": [
    {
      "itemId": "DaprHoodie",
      "quantity": 1
    }
  ],
  "customerId": 1
}
```

En las secciones siguientes se explica cómo usar las características más avanzadas del bloque de creación de la administración de estado.

### <a name="consistency"></a>Coherencia

El [teorema Cap](https://en.wikipedia.org/wiki/CAP_theorem) es un conjunto de principios que se aplican a los sistemas distribuidos que almacenan el estado. En la figura 5-2 se muestran las tres propiedades del CAP teorema.

![Teorema CAP.](media/state-management/cap-theorem.png)

**Figura 5-2**. Teorema CAP.

Teorema indica que los sistemas de datos distribuidos ofrecen un equilibrio entre coherencia, disponibilidad y tolerancia de particiones. Y, que cualquier almacén *de la propiedad solo puede garantizar dos de las tres propiedades*:

- *Consistency* (**C**). Cada nodo del clúster responde con los datos más recientes, incluso si el sistema debe bloquear la solicitud hasta que se actualicen todas las réplicas. Si consulta un "sistema coherente" para un elemento que se está actualizando actualmente, no obtendrá una respuesta hasta que todas las réplicas se actualicen correctamente. Sin embargo, siempre recibirá los datos más actuales.

- *Disponibilidad* (**A**). Cada nodo devuelve una respuesta inmediata, incluso si esa respuesta no es los datos más recientes. Si consulta un "sistema disponible" para un elemento que se está actualizando, obtendrá la mejor respuesta posible que el servicio pueda proporcionar en ese momento.

- *Tolerancia de partición* (**P**). Garantiza que el sistema siga funcionando incluso si se produce un error en un nodo de datos replicado o se pierde la conectividad con otros nodos de datos replicados.

Las aplicaciones distribuidas deben controlar la propiedad **P** . A medida que los servicios se comunican entre sí con llamadas de red, se producirá una interrupción de la red (**P**). Teniendo esto en cuenta, las aplicaciones distribuidas deben ser de tipo **AP** o **CP**.

Las aplicaciones de **AP** eligen la disponibilidad a través de la coherencia. DAPR admite esta opción con su estrategia de **coherencia eventual** . Considere la posibilidad de un almacén de datos subyacente, como Azure CosmosDB, que almacena datos redundantes en varias réplicas. Con coherencia final, el almacén de estado escribe la actualización en una réplica y completa la solicitud de escritura con el cliente. Después de este tiempo, el almacén actualizará de forma asincrónica sus réplicas. Las solicitudes de lectura pueden devolver datos de cualquiera de las réplicas, incluidas las réplicas que aún no han recibido la actualización más reciente.

Las aplicaciones de **CP** eligen la coherencia con respecto a la disponibilidad. DAPR admite esta opción con su estrategia de **coherencia fuerte** . En este escenario, el almacén de estado actualizará de forma sincrónica *todos* (o, en algunos casos, un *cuórum* de) las réplicas necesarias *antes* de completar la solicitud de escritura. Las operaciones de lectura devolverán los datos más actualizados de forma coherente en las réplicas.

El nivel de coherencia de una operación de estado se especifica mediante la Asociación de una *sugerencia de coherencia* a la operación. El siguiente comando de *rizo* escribe un `Hello=World` par clave-valor en un almacén de estado mediante una sugerencia de coherencia fuerte:

```console
curl -X POST http://localhost:3500/v1.0/state/<store-name> \
  -H "Content-Type: application/json" \
  -d '[
        {
          "key": "Hello",
          "value": "World",
          "options": {
            "consistency": "strong"
          }
        }
      ]'
```

> [!IMPORTANT]
> Depende del componente de almacén de estado de DAPR para satisfacer la sugerencia de coherencia asociada a la operación. No todos los almacenes de datos admiten ambos niveles de coherencia. Si no se establece ninguna sugerencia de coherencia, el comportamiento predeterminado es **eventual**.

### <a name="concurrency"></a>Simultaneidad

En una aplicación de varios usuarios, existe la posibilidad de que varios usuarios actualicen los mismos datos simultáneamente (al mismo tiempo). DAPR admite el control de simultaneidad optimista (OCC) para administrar los conflictos. OCC se basa en una suposición de que los conflictos de actualización son infrecuentes, ya que los usuarios trabajan en diferentes partes de los datos. Es más eficaz suponer que una actualización se realizará correctamente y volverá a intentarlo si no lo hace. La alternativa, implementar el bloqueo pesimista, puede afectar al rendimiento con el bloqueo de ejecución prolongada que produce la contención de datos.

DAPR admite el control de simultaneidad optimista (OCC) mediante ETags. Una ETag es un valor asociado a una versión específica de un par clave-valor almacenado. Cada vez que se actualiza un par clave-valor, el valor ETag también se actualiza. Cuando un cliente recupera un par clave-valor, la respuesta incluye el valor ETag actual. Cuando un cliente actualiza o elimina un par clave-valor, debe devolver el valor de ETag en el cuerpo de la solicitud. Si otro cliente ha actualizado los datos mientras tanto, el ETags no coincidirá y se producirá un error en la solicitud. En este momento, el cliente debe recuperar los datos actualizados, volver a realizar el cambio y volver a enviar la actualización. Esta estrategia se denomina **First-Write-WINS**.

DAPR también admite una estrategia de **última escritura-WINS** . Con este enfoque, el cliente no adjunta un ETag a la solicitud de escritura. El componente almacén de estado siempre permitirá la actualización, incluso si el valor subyacente ha cambiado durante la sesión. Last-Write-WINS es útil para escenarios de escritura de alto rendimiento con poca contención de datos. Además, se puede tolerar la sobrescritura de una actualización de usuario ocasional.

### <a name="transactions"></a>Transacciones

DAPR puede escribir *cambios de varios elementos* en un almacén de datos como una operación única implementada como una transacción. Esta funcionalidad solo está disponible para los almacenes de datos que admiten transacciones [acid](https://en.wikipedia.org/wiki/ACID) . En el momento de redactar este documento, estos almacenes incluyen Redis, MongoDB, PostgreSQL, SQL Server y Azure CosmosDB.

En el ejemplo siguiente, se envía una operación de varios elementos al almacén de estado en una única transacción. Todas las operaciones deben realizarse correctamente para que la transacción se confirme. Si se produce un error en una o varias de las operaciones, se revierte toda la transacción.

```console
curl -X POST http://localhost:3500/v1.0/state/<store-name>/transaction \
  -H "Content-Type: application/json" \
  -d '{
        "operations": [
          {
            "operation": "upsert",
            "request": { "key": "Key1", "value": "Value1"
            }
          },
          {
            "operation": "delete",
            "request": { "key": "Key2" }
          }
        ]
      }'
```

En el caso de los almacenes de datos que no admiten transacciones, se pueden enviar varias claves como una única solicitud. En el ejemplo siguiente se muestra una operación de escritura **masiva** :

```console
curl -X POST http://localhost:3500/v1.0/state/<store-name> \
  -H "Content-Type: application/json" \
  -d '[
        { "key": "Key1", "value": "Value1" },
        { "key": "Key2", "value": "Value2" }
      ]'
```

En el caso de las operaciones masivas, DAPR enviará cada actualización del par clave-valor como una solicitud independiente al almacén de datos.

## <a name="use-the-dapr-net-sdk"></a>Uso del SDK de .NET para DAPR

El SDK de .NET para DAPR proporciona compatibilidad específica del lenguaje para la plataforma .NET Core. Los desarrolladores pueden usar la `DaprClient` clase presentada en el [capítulo 3](getting-started.md) para leer y escribir datos. En el ejemplo siguiente se muestra cómo utilizar el `DaprClient.GetStateAsync<TValue>` método para leer los datos de un almacén de estado. El método espera el nombre de almacén, `statestore` , y la clave, `AMS` , como parámetros:

```csharp
var weatherForecast = await daprClient.GetStateAsync<WeatherForecast>("statestore", "AMS");
```

Si el almacén de estado no contiene ningún dato para `AMS` la clave, el resultado será `default(WeatherForecast)` .

Para escribir datos en el almacén de datos, use el `DaprClient.SaveStateAsync<TValue>` método:

```csharp
daprClient.SaveStateAsync("statestore", "AMS", weatherForecast);
```

En el ejemplo se usa la estrategia **Last-Write-WINS** , ya que no se pasa un valor ETag al componente almacén de estado. Para usar el control de simultaneidad optimista (OCC) con una estrategia **First-Write-WINS** , primero recupere el ETag actual mediante el `DaprClient.GetStateAndETagAsync` método. A continuación, escriba el valor actualizado y pase a lo largo de la ETag recuperada mediante el `DaprClient.TrySaveStateAsync` método.

```csharp
var (weatherForecast, etag) = await daprClient.GetStateAndETagAsync<WeatherForecast>("statestore", city);

// ... make some changes to the retrieved weather forecast

var result = await daprClient.TrySaveStateAsync("statestore", city, weatherForecast, etag);
```

El `DaprClient.TrySaveStateAsync` método genera un error cuando se han cambiado los datos (y la ETag asociada) en el almacén de estado después de recuperar los datos. El método devuelve un valor booleano para indicar si la llamada se realizó correctamente. Una estrategia para controlar el error es simplemente volver a cargar los datos actualizados desde el almacén de estado, realizar el cambio de nuevo y volver a enviar la actualización.

Si siempre desea que una escritura se realice correctamente independientemente de otros cambios en los datos, use la estrategia **Last-Write-WINS** .

El SDK proporciona otros métodos para recuperar datos en masa, eliminar datos y ejecutar transacciones. Para obtener más información, vea el [repositorio del SDK de .net de DAPR](https://github.com/dapr/dotnet-sdk).

### <a name="aspnet-core-integration"></a>Integración de ASP.NET Core

DAPR también admite ASP.NET Core, un marco multiplataforma para compilar modernas aplicaciones web basadas en la nube. El SDK de DAPR integra las capacidades de administración de estado directamente en las capacidades de [enlace del modelo de ASP.net Core](/aspnet/core/mvc/models/model-binding) . La configuración es sencilla. Agregue el `IMVCBuilder.AddDapr` anexando el `.AddDapr` método de extensión en la `Startup.cs` clase tal y como se muestra en el ejemplo siguiente:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddControllers().AddDapr();
}
```

Una vez configurado, DAPR puede inyectar un par clave-valor directamente en una acción del controlador mediante el `FromState` atributo ASP.net Core. Ya no es necesario hacer referencia al `DaprClient` objeto. En el ejemplo siguiente se muestra una API Web que devuelve el Pronóstico meteorológico de una ciudad determinada:

```csharp
[HttpGet("{city}")]
public ActionResult<WeatherForecast> Get([FromState("statestore", "city")] StateEntry<WeatherForecast> forecast)
{
    if (forecast.Value == null)
    {
      return NotFound();
    }

    return forecast.Value;
}
```

En el ejemplo, el controlador carga la previsión meteorológica mediante el `FromState` atributo. El primer parámetro de atributo es el almacén de estado, `statestore` . El segundo parámetro de atributo, `city` , es el nombre de la variable de [plantilla de ruta](/aspnet/core/mvc/controllers/routing#route-templates) para obtener la clave de estado. Si omite el segundo parámetro, se usa el nombre del parámetro de método enlazado ( `forecast` ) para buscar la variable de plantilla de ruta.

La `StateEntry` clase contiene las propiedades de toda la información que se recupera para un par clave-valor único: `StoreName` , `Key` , `Value` y `ETag` . La ETag es útil para implementar la estrategia de control de simultaneidad optimista (OCC). La clase también proporciona métodos para eliminar o actualizar los datos de clave y valor recuperados sin necesidad de una `DaprClient` instancia de. En el ejemplo siguiente, el `TrySaveAsync` método se utiliza para actualizar la previsión meteorológica recuperada mediante OCC.

```csharp
[HttpPut("{city}")]
public async Task Put(WeatherForecast updatedForecast, [FromState("statestore", "city")] StateEntry<WeatherForecast> currentForecast)
{
    // update cached current forecast with updated forecast passed into service endpoint
    currentForecast.Value = updatedForecast;

    // update state store
    var success = await currentForecast.TrySaveAsync();

    // ... check result
}
```

## <a name="state-store-components"></a>Componentes del almacén de estado

En el momento de redactar este documento, DAPR proporciona compatibilidad para los siguientes almacenes de estado transaccionales:

- Azure CosmosDB
- Azure SQL Server
- MongoDB
- PostgreSQL
- Redis

DAPR también incluye compatibilidad con almacenes de estado que admiten operaciones CRUD, pero no capacidades transaccionales:

- Aerospike
- Azure Blob Storage
- Azure Table Storage
- Cassandra
- Cloudstate
- Couchbase
- etcd
- Google Cloud FireStore
- Hashicorp Consul
- Hazelcast
- Memcached
- Zookeeper

### <a name="configuration"></a>Configuración

Cuando se inicializa para el desarrollo local y autohospedado, DAPR registra Redis como el almacén de estado predeterminado. Este es un ejemplo de la configuración predeterminada del almacén de estado. Anote el nombre predeterminado, `statestore` :

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: statestore
spec:
  type: state.redis
  version: v1
  metadata:
  - name: redisHost
    value: localhost:6379
  - name: redisPassword
    value: ""
  - name: actorStateStore
    value: "true"
```

 > [!NOTE]
 > Muchos almacenes de Estados se pueden registrar en una sola aplicación con un nombre diferente.

El almacén de estado de Redis requiere los `redisHost` `redisPassword` metadatos y para conectarse a la instancia de Redis. En el ejemplo anterior, la contraseña de REDIS (que es una cadena vacía de forma predeterminada) se almacena como una cadena sin formato. El procedimiento recomendado es evitar cadenas de texto no cifrado y usar siempre referencias secretas. Para obtener más información acerca de la administración de secretos, consulte el [capítulo 10](secrets.md).

El otro campo de metadatos, `actorStateStore` , indica si el almacén de estado puede ser utilizado por el bloque de creación de actores.

### <a name="key-prefix-strategies"></a>Estrategias de prefijo de clave

Los componentes del almacén de estado permiten diferentes estrategias para almacenar pares clave-valor en el almacén subyacente. Recuerde el ejemplo anterior de un servicio de cesta de la compra que almacena los artículos que un cliente desea comprar:

```console
curl -X POST http://localhost:3500/v1.0/state/statestore \
  -H "Content-Type: application/json" \
  -d '[{
        "key": "basket1",
        "value": {
          "customerId": 1,
          "items": [
            { "itemId": "DaprHoodie", "quantity": 1 }
          ]
        }
     }]'
```

Con la herramienta de la consola de Redis, mire dentro de la caché en Redis para ver cómo el componente del almacén de estado de Redis conserva los datos:

```
127.0.0.1:6379> KEYS *
1) "basketservice||basket1"

127.0.0.1:6379> HGETALL basketservice||basket1
1) "data"
2) "{\"items\":[{\"itemId\":\"DaprHoodie\",\"quantity\":1}],\"customerId\":1}"
3) "version"
4) "1"
```

La salida muestra la **clave** de Redis completa de los datos como `basketservice||basket1` . De forma predeterminada, DAPR usa la `application id` de la instancia de DAPR ( `basketservice` ) como prefijo para la clave. Esta Convención de nomenclatura permite que varias instancias de DAPR compartan el mismo almacén de datos sin colisiones de nombre de clave. En el caso del desarrollador, es importante especificar siempre el mismo `application id` cuando se ejecuta la aplicación con DAPR. Si se omite, DAPR generará un identificador de aplicación único. Si `application id` cambia, la aplicación ya no puede tener acceso al estado almacenado con el prefijo de clave anterior.

Dicho esto, es posible configurar un *valor constante* para el prefijo de clave en el `keyPrefix` campo de metadatos del archivo de componente del almacén de estado. Considere el ejemplo siguiente:

```yaml
spec:
  metadata:
  - name: keyPrefix
  - value: MyPrefix
```

Un prefijo de clave constante permite el acceso al almacén de estado a través de varias aplicaciones DAPR. Lo que es más, si `keyPrefix` se establece en, se `none` omite por completo el prefijo.

## <a name="reference-application-eshopondapr"></a>Aplicación de referencia: eShopOnDapr

Este libro incluye una aplicación de referencia titulada `eShopOnDapr` . Se modela a partir de una aplicación de referencia de microservicios de Microsoft anterior, `eShopOnContainers` .

La arquitectura [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) original usaba una `IBasketRepository` interfaz para leer y escribir datos para el servicio de la cesta. La `RedisBasketRepository` clase proporcionó la implementación mediante Redis como almacén de datos subyacente:

```csharp
public class RedisBasketRepository : IBasketRepository
{
    private readonly ConnectionMultiplexer _redis;
    private readonly IDatabase _database;

    public RedisBasketRepository(ConnectionMultiplexer redis)
    {
        _redis = redis;
        _database = redis.GetDatabase();
    }

    public async Task<CustomerBasket> GetBasketAsync(string customerId)
    {
        var data = await _database.StringGetAsync(customerId);

        if (data.IsNullOrEmpty)
        {
            return null;
        }

        return JsonConvert.DeserializeObject<CustomerBasket>(data);
    }

    // ...
}
```

Este código utiliza el paquete de NuGet de terceros `StackExchange.Redis` . Los pasos siguientes son necesarios para cargar la cesta de la compra de un cliente determinado:

1. Inserte un `ConnectionMultiplexer` en el constructor. `ConnectionMultiplexer`Se registra con el marco de inserción de dependencias en el `Startup.cs` archivo:

   ```csharp
   services.AddSingleton<ConnectionMultiplexer>(sp =>
   {
       var settings = sp.GetRequiredService<IOptions<BasketSettings>>().Value;
       var configuration = ConfigurationOptions.Parse(settings.ConnectionString, true);
       configuration.ResolveDns = true;
       return ConnectionMultiplexer.Connect(configuration);
   });
   ```

1. Utilice `ConnectionMultiplexer` para crear una `IDatabase` instancia de en cada clase de consumo.

1. Use la `IDatabase` instancia de para ejecutar una llamada StringGet de Redis usando el especificado `customerId` como clave.

1. Compruebe si los datos se cargan desde Redis; en caso contrario, devuelve `null` .

1. Deserializa los datos de Redis a un `CustomerBasket` objeto y devuelve el resultado.

En la aplicación de referencia [eShopOnDapr](https://github.com/dotnet-architecture/eShopOnDapr) actualizada, una nueva `DaprBasketRepository` clase reemplaza a la `RedisBasketRepository` clase:

```csharp
public class DaprBasketRepository : IBasketRepository
{
    private const string StoreName = "eshop-basket-statestore";

    private readonly DaprClient _daprClient;

    public DaprBasketRepository(DaprClient daprClient)
    {
        _daprClient = daprClient ?? throw new ArgumentNullException(nameof(daprClient));;
    }

    public async Task<CustomerBasket> GetBasketAsync(string customerId)
    {
        return await _daprClient.GetStateAsync<CustomerBasket>(StoreName, customerId);
    }

    // ...
}
```

El código actualizado usa el SDK de .NET de DAPR para leer y escribir datos mediante el bloque de creación de la administración de estado. Los nuevos pasos para cargar la cesta de un cliente se han simplificado drásticamente:

1. Inserte un `DaprClient` en el constructor. `DaprClient`Se registra con el marco de inserción de dependencias en el `Startup.cs` archivo.
1. Utilice el `DaprClient.GetStateAsync` método para cargar los elementos de la cesta de compras del cliente del almacén de estado configurado y devolver el resultado.

La implementación actualizada todavía usa Redis como almacén de datos subyacente. Sin embargo, DAPR abstrae las `StackExchange.Redis` referencias y la complejidad de la aplicación. Un archivo de configuración de DAPR es todo lo que se necesita:

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: eshop-basket-statestore
  namespace: eshop
spec:
  type: state.redis
  version: v1
  metadata:
  - name: redisHost
    value: redis:6379
  - name: redisPassword
    secretKeyRef:
      name: redisPassword
auth:
  secretStore: eshop-secretstore
```

La implementación de DAPR también simplifica el cambio del almacén de datos subyacente. Por ejemplo, cambiar a Azure Table Storage solo requiere cambiar el contenido del archivo de configuración. No es necesario realizar ningún cambio en el código.

## <a name="summary"></a>Resumen

El bloque de creación de administración de estado de DAPR ofrece una API para almacenar datos de clave/valor en varios almacenes de datos. La API proporciona compatibilidad con:

- Operaciones masivas
- Coherencia fuerte y eventual
- Control de simultaneidad optimista
- Transacciones de varios elementos

El SDK de .NET proporciona compatibilidad específica del lenguaje para .NET Core y ASP.NET Core. La integración del enlace de modelos simplifica el acceso y la actualización del estado desde ASP.NET Core métodos de acción del controlador.

En la aplicación de referencia eShopOnDapr, las ventajas de pasar a la administración de estado de DAPR son claras:

1. La nueva implementación utiliza menos líneas de código.
1. Abstrae la complejidad de la API de terceros `StackExchange.Redis` .
1. Reemplazar la caché en Redis subyacente con un tipo diferente de almacén de datos ahora solo requiere cambios en el archivo de configuración del almacén de estado.

### <a name="references"></a>Referencias

- [DAPR almacenes de estado compatibles](https://docs.dapr.io/operations/components/setup-state-store/supported-state-stores/)

> [!div class="step-by-step"]
> [Anterior](reference-application.md)
> [Siguiente](service-invocation.md)
