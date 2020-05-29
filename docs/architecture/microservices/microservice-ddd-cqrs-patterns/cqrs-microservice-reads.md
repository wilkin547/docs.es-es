---
title: Implementación de lecturas/consultas en un microservicio CQRS
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Información sobre la implementación del lado de consultas de CQRS en el microservicio Ordering en eShopOnContainers mediante Dapper.
ms.date: 10/08/2018
ms.openlocfilehash: 71db95e6fc17475693183be9c6854884cd331ce1
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614414"
---
# <a name="implement-readsqueries-in-a-cqrs-microservice"></a>Implementación de lecturas/consultas en un microservicio CQRS

Para lecturas/consultas, el microservicio de pedidos (Ordering) de la aplicación de referencia eShopOnContainers implementa las consultas de manera independiente del modelo DDD y el área transaccional. Esto se hacía principalmente porque las demandas de consultas y transacciones son muy diferentes. Las escrituras ejecutan transacciones que deben ser compatibles con la lógica del dominio. Por otro lado, las consultas son idempotentes y se pueden segregar de las reglas de dominio.

El enfoque es sencillo, como se muestra en la figura 7-3. La interfaz API se implementa mediante los controladores de API Web con cualquier infraestructura, como un microasignador objeto-relacional (ORM) como Dapper, y devolviendo ViewModel dinámicos según las necesidades de las aplicaciones de interfaz de usuario.

![Diagrama que muestra una visión general del lado de las consultas en un microservicio CQRS simplificado.](./media/cqrs-microservice-reads/simple-approach-cqrs-queries.png)

**Figura 7-3**. El enfoque más sencillo para las consultas en un microservicio CQRS

El enfoque más sencillo para el lado de las consultas en un enfoque CQRS simplificado se puede implementar consultando la base de datos con un Micro-ORM como Dapper, devolviendo ViewModel dinámicos. Las definiciones de consulta realizan una consulta a la base de datos y devuelven un ViewModel dinámico creado sobre la marcha para cada consulta. Puesto que las consultas son idempotentes, no cambian los datos por muchas veces que ejecute una consulta. Por lo tanto, no es necesario estar restringido por un patrón DDD usado en el lado transaccional, como agregados y otros patrones, y por eso las consultas se separan del área transaccional. Consulta la base de datos para obtener los datos que necesita la interfaz de usuario y devolver un ViewModel dinámico que no tiene que estar definido estáticamente en ningún lugar (no hay clases para los ViewModel), excepto en las propias instrucciones SQL.

Puesto que se trata de un método sencillo, el código necesario para el lado de las consultas (como código que usa un micro ORM como [Dapper](https://github.com/StackExchange/Dapper)) pueden implementarse [dentro del mismo proyecto de API Web](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Queries/OrderQueries.cs). Esto se muestra en la Figura 7-4. Las consultas se definen en el proyecto de microservicio **Ordering.API** dentro de la solución eShopOnContainers.

![Captura de pantalla de la carpeta Queries del proyecto Ordering.API.](./media/cqrs-microservice-reads/ordering-api-queries-folder.png)

**Figura 7-4**. Consultas (Queries) en el microservicio de pedidos (Ordering) en eShopOnContainers

## <a name="use-viewmodels-specifically-made-for-client-apps-independent-from-domain-model-constraints"></a>Uso de ViewModel específicos para aplicaciones de cliente, sin las restricciones del modelo de dominio

Dado que las consultas se realizan para obtener los datos que necesitan para las aplicaciones cliente, el tipo de valor devuelto puede estar hecho específicamente para los clientes, en función de los datos devueltos por las consultas. Estos modelos, u objetos de transferencia de datos (DTO), se denominan ViewModel.

Los datos devueltos (ViewModel) pueden ser el resultado de combinar datos de varias entidades o tablas de la base de datos, o incluso de varios agregados definidos en el modelo de dominio para el área transaccional. En este caso, dado que va a crear consultas independientes del modelo de dominio, se ignoran las restricciones y los límites de agregados, y se pueden consultar cualquier tabla y columna que necesite. Este enfoque proporciona gran flexibilidad y productividad a los desarrolladores que crean o actualizan las consultas.

Los ViewModel pueden ser tipos estáticos definidos en las clases. O bien, se pueden crear dinámicamente en función de las consultas realizadas (tal y como se implementa en el microservicio de pedidos), lo que resulta muy ágil para los desarrolladores.

## <a name="use-dapper-as-a-micro-orm-to-perform-queries"></a>Uso de Dapper como micro ORM para realizar consultas

Para la consulta puede usar cualquier micro ORM, Entity Framework Core o incluso ADO.NET estándar. En la aplicación de ejemplo, se seleccionó Dapper para el microservicio de pedidos en eShopOnContainers como un buen ejemplo de un micro ORM popular. Dapper puede ejecutar consultas SQL estándar con un gran rendimiento, porque es un marco de trabajo ligero. Con Dapper, se puede escribir una consulta SQL que puede acceder a varias tablas y combinarlas.

Dapper es un proyecto de código abierto (creado originalmente por Sam Saffron) y forma parte de los bloques de creación que se usan en [Stack Overflow](https://stackoverflow.com/). Para usar Dapper, solo hay que instalarlo a través del [paquete Dapper de NuGet](https://www.nuget.org/packages/Dapper), tal y como se muestra en la ilustración siguiente:

![Captura de pantalla del paquete Dapper en la vista de paquetes de NuGet.](./media/cqrs-microservice-reads/drapper-package-nuget.png)

También debe agregar una directiva `using` para que el código tenga acceso a los métodos de extensión de Dapper.

Cuando se utiliza Dapper en el código, se usa directamente la clase <xref:System.Data.SqlClient.SqlConnection> disponible en el espacio de nombres <xref:System.Data.SqlClient>. Mediante el método QueryAsync y otros métodos de extensión que extienden la clase <xref:System.Data.SqlClient.SqlConnection>, se ejecutan las consultas de una manera sencilla y eficaz.

## <a name="dynamic-versus-static-viewmodels"></a>ViewModel dinámicos frente a estáticos

Cuando se devuelven ViewModel desde el servidor a las aplicaciones cliente, se puede pensar en esos ViewModel como DTO (Objetos de transferencia de datos) que pueden ser diferentes a las entidades de dominio interno de su modelo de entidad, ya que los ViewModel contienen los datos de la forma en que la aplicación cliente necesita. Por lo tanto, en muchos casos, se pueden agregar datos procedentes de varias entidades de dominio y crear los ViewModel exactamente según la forma en que la aplicación cliente necesita los datos.

Esos ViewModels o DTO se pueden definir explícitamente (como clases de contenedor de datos), como la clase `OrderSummary` que se muestra en un fragmento de código posterior. O bien, podría devolver simplemente ViewModels dinámicos o DTO dinámicos en función de los atributos devueltos por las consultas como un tipo dinámico.

### <a name="viewmodel-as-dynamic-type"></a>ViewModel como tipo dinámico

Como se muestra en el siguiente código, las consultas pueden devolver un `ViewModel` directamente al devolver un tipo *dinámico* que internamente se basa en los atributos devueltos por una consulta. Esto significa que el subconjunto de atributos que se devuelve se basa en la propia consulta. Por tanto, si se agrega una nueva columna a la consulta o combinación, esos datos se agregan dinámicamente al `ViewModel` devuelto.

```csharp
using Dapper;
using Microsoft.Extensions.Configuration;
using System.Data.SqlClient;
using System.Threading.Tasks;
using System.Dynamic;
using System.Collections.Generic;

public class OrderQueries : IOrderQueries
{
    public async Task<IEnumerable<dynamic>> GetOrdersAsync()
    {
        using (var connection = new SqlConnection(_connectionString))
        {
            connection.Open();
            return await connection.QueryAsync<dynamic>(
                @"SELECT o.[Id] as ordernumber,
                o.[OrderDate] as [date],os.[Name] as [status],
                SUM(oi.units*oi.unitprice) as total
                FROM [ordering].[Orders] o
                LEFT JOIN[ordering].[orderitems] oi ON o.Id = oi.orderid
                LEFT JOIN[ordering].[orderstatus] os on o.OrderStatusId = os.Id
                GROUP BY o.[Id], o.[OrderDate], os.[Name]");
        }
    }
}
```

Lo importante es que, mediante el uso de un tipo dinámico, la colección de datos devuelta dinámicamente se ensambla como un ViewModel.

**Ventajas**: este enfoque reduce la necesidad de modificar las clases estáticas de ViewModel cada vez que se actualice la frase SQL de una consulta, lo que hace que este enfoque de diseño sea ágil a la hora de codificar, sencillo y rápido de evolucionar con respecto a los cambios en el futuro.

**Inconvenientes**: a largo plazo, los tipos dinámicos pueden perjudicar a la claridad y afectar a la compatibilidad de un servicio con las aplicaciones cliente. Además, el software middleware como Swashbuckle no puede proporcionar el mismo nivel de documentación en tipos devueltos si se utilizan tipos dinámicos.

### <a name="viewmodel-as-predefined-dto-classes"></a>ViewModel como clases DTO predefinidas

**Ventajas**: disponer de clases ViewModel predefinidas estáticas, como "contratos" basados en clases DTO explícitas, es definitivamente mejor para las API públicas, pero también para los microservicios a largo plazo, aunque solo los use la misma aplicación.

Si quiere especificar los tipos de respuesta de Swagger, debe utilizar clases DTO explícitas como tipo de valor devuelto. Por lo tanto, las clases DTO predefinidas permiten ofrecer información más completa de Swagger. Eso mejora la documentación y la compatibilidad de la API al utilizar una API.

**Inconvenientes**: tal y como se mencionó anteriormente, al actualizar el código se requieren algunos pasos adicionales para actualizar las clases DTO.

*Sugerencia basada en nuestra experiencia*: en las consultas que se implementan en el microservicio de pedidos en eShopOnContainers, iniciamos el desarrollo con ViewModel dinámicos porque resultaba sencillo y ágil en las primeras fases de desarrollo. Pero, una vez que se estabilizó el desarrollo, optamos por refactorizar las API y usar DTO estático o predefinido para los ViewModel, porque es más fácil para los consumidores del microservicio conocer los tipos DTO explícitos, utilizados como "contratos".

En el ejemplo siguiente, puede ver cómo la consulta devuelve datos mediante una clase ViewModel DTO explícita: la clase OrderSummary.

```csharp
using Dapper;
using Microsoft.Extensions.Configuration;
using System.Data.SqlClient;
using System.Threading.Tasks;
using System.Dynamic;
using System.Collections.Generic;

public class OrderQueries : IOrderQueries
{
  public async Task<IEnumerable<OrderSummary>> GetOrdersAsync()
    {
        using (var connection = new SqlConnection(_connectionString))
        {
            connection.Open();
            return await connection.QueryAsync<OrderSummary>(
                  @"SELECT o.[Id] as ordernumber,
                  o.[OrderDate] as [date],os.[Name] as [status],
                  SUM(oi.units*oi.unitprice) as total
                  FROM [ordering].[Orders] o
                  LEFT JOIN[ordering].[orderitems] oi ON  o.Id = oi.orderid
                  LEFT JOIN[ordering].[orderstatus] os on o.OrderStatusId = os.Id
                  GROUP BY o.[Id], o.[OrderDate], os.[Name]
                  ORDER BY o.[Id]");
        }
    }
}
```

#### <a name="describe-response-types-of-web-apis"></a>Descripción de los tipos de respuesta de las API Web

Lo que más preocupa a los desarrolladores que utilizan API Web y microservicios es lo que se devuelve, sobre todo los tipos de respuesta y los códigos de error (si no son los habituales). Los tipos de respuesta se administran en las anotaciones de datos y en los comentarios XML.

Sin una documentación correcta en la interfaz de usuario de Swagger, el consumidor desconoce los tipos que se devuelven o los códigos HTTP que se pueden devolver. Este problema se corrige agregando <xref:Microsoft.AspNetCore.Mvc.ProducesResponseTypeAttribute?displayProperty=nameWithType>, para que Swashbuckle pueda generar información completa sobre el modelo de devolución y los valores de API, como se muestra en el siguiente código:

```csharp
namespace Microsoft.eShopOnContainers.Services.Ordering.API.Controllers
{
    [Route("api/v1/[controller]")]
    [Authorize]
    public class OrdersController : Controller
    {
        //Additional code...
        [Route("")]
        [HttpGet]
        [ProducesResponseType(typeof(IEnumerable<OrderSummary>),
            (int)HttpStatusCode.OK)]
        public async Task<IActionResult> GetOrders()
        {
            var userid = _identityService.GetUserIdentity();
            var orders = await _orderQueries
                .GetOrdersFromUserAsync(Guid.Parse(userid));
            return Ok(orders);
        }
    }
}
```

Pero el atributo `ProducesResponseType` no puede utilizar un tipo dinámico, sino que requiere utilizar tipos explícitos, como ViewModel DTO `OrderSummary`, se mostrado en el ejemplo siguiente:

```csharp
public class OrderSummary
{
    public int ordernumber { get; set; }
    public DateTime date { get; set; }
    public string status { get; set; }
    public double total { get; set; }
}
```

Este es otro de los motivos por los que, a largo plazo, los tipos explícitos son mejores que los tipos dinámicos. Cuando se usa el atributo `ProducesResponseType`, también se puede especificar cuál es el resultado esperado en lo que respecta a posibles errores/códigos HTTP, como 200, 400, etc.

En la siguiente imagen, se puede ver cómo la interfaz de usuario de Swagger de interfaz de usuario muestra la información de ResponseType.

![Captura de pantalla de la página de interfaz de usuario de Swagger para Ordering API.](./media/cqrs-microservice-reads/swagger-ordering-http-api.png)

**Figura 7-5**. Interfaz de usuario de Swagger que muestra los tipos de respuesta y los posibles códigos de estado HTTP de una API Web

En la ilustración anterior se pueden ver algunos valores de ejemplo basados en los tipos ViewModel, además de los posibles códigos de estado HTTP que se pueden devolver.

## <a name="additional-resources"></a>Recursos adicionales

- **Dapper**  
 <https://github.com/StackExchange/dapper-dot-net>

- **Julie Lerman. Puntos de datos: Dapper, Entity Framework y aplicaciones híbridas (artículo de MSDN magazine)**  
  <https://docs.microsoft.com/archive/msdn-magazine/2016/may/data-points-dapper-entity-framework-and-hybrid-apps>

- **Páginas de ayuda de ASP.NET Core Web API mediante Swagger**  
  <https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger?tabs=visual-studio>

>[!div class="step-by-step"]
>[Anterior](eshoponcontainers-cqrs-ddd-microservice.md)
>[Siguiente](ddd-oriented-microservice.md)
