---
title: Implementación de lecturas/consultas en un microservicio CQRS
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Información sobre la implementación del lado de consultas de CQRS en el microservicio Ordering en eShopOnContainers mediante Dapper.
ms.date: 01/13/2021
ms.openlocfilehash: 047fc3893dcaf72a17d29f5560c928879757d024
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "98188925"
---
# <a name="implement-readsqueries-in-a-cqrs-microservice"></a><span data-ttu-id="d9255-103">Implementación de lecturas/consultas en un microservicio CQRS</span><span class="sxs-lookup"><span data-stu-id="d9255-103">Implement reads/queries in a CQRS microservice</span></span>

<span data-ttu-id="d9255-104">Para lecturas/consultas, el microservicio de pedidos (Ordering) de la aplicación de referencia eShopOnContainers implementa las consultas de manera independiente del modelo DDD y el área transaccional.</span><span class="sxs-lookup"><span data-stu-id="d9255-104">For reads/queries, the ordering microservice from the eShopOnContainers reference application implements the queries independently from the DDD model and transactional area.</span></span> <span data-ttu-id="d9255-105">Esta implementación se hacía principalmente porque las demandas de consultas y transacciones son muy diferentes.</span><span class="sxs-lookup"><span data-stu-id="d9255-105">This implementation was done primarily because the demands for queries and for transactions are drastically different.</span></span> <span data-ttu-id="d9255-106">Las escrituras ejecutan transacciones que deben ser compatibles con la lógica del dominio.</span><span class="sxs-lookup"><span data-stu-id="d9255-106">Writes execute transactions that must be compliant with the domain logic.</span></span> <span data-ttu-id="d9255-107">Por otro lado, las consultas son idempotentes y se pueden segregar de las reglas de dominio.</span><span class="sxs-lookup"><span data-stu-id="d9255-107">Queries, on the other hand, are idempotent and can be segregated from the domain rules.</span></span>

<span data-ttu-id="d9255-108">El enfoque es sencillo, como se muestra en la figura 7-3.</span><span class="sxs-lookup"><span data-stu-id="d9255-108">The approach is simple, as shown in Figure 7-3.</span></span> <span data-ttu-id="d9255-109">La interfaz API se implementa mediante los controladores de API Web con cualquier infraestructura, como un microasignador objeto-relacional (ORM) como Dapper, y devolviendo ViewModel dinámicos según las necesidades de las aplicaciones de interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="d9255-109">The API interface is implemented by the Web API controllers using any infrastructure, such as a micro Object Relational Mapper (ORM) like Dapper, and returning dynamic ViewModels depending on the needs of the UI applications.</span></span>

![Diagrama que muestra una visión general del lado de las consultas en un microservicio CQRS simplificado.](./media/cqrs-microservice-reads/simple-approach-cqrs-queries.png)

<span data-ttu-id="d9255-111">**Figura 7-3**.</span><span class="sxs-lookup"><span data-stu-id="d9255-111">**Figure 7-3**.</span></span> <span data-ttu-id="d9255-112">El enfoque más sencillo para las consultas en un microservicio CQRS</span><span class="sxs-lookup"><span data-stu-id="d9255-112">The simplest approach for queries in a CQRS microservice</span></span>

<span data-ttu-id="d9255-113">El enfoque más sencillo para el lado de las consultas en un enfoque CQRS simplificado se puede implementar consultando la base de datos con un Micro-ORM como Dapper, devolviendo ViewModel dinámicos.</span><span class="sxs-lookup"><span data-stu-id="d9255-113">The simplest approach for the queries-side in a simplified CQRS approach can be implemented by querying the database with a Micro-ORM like Dapper, returning dynamic ViewModels.</span></span> <span data-ttu-id="d9255-114">Las definiciones de consulta realizan una consulta a la base de datos y devuelven un ViewModel dinámico creado sobre la marcha para cada consulta.</span><span class="sxs-lookup"><span data-stu-id="d9255-114">The query definitions query the database and return a dynamic ViewModel built on the fly for each query.</span></span> <span data-ttu-id="d9255-115">Puesto que las consultas son idempotentes, no cambian los datos por muchas veces que ejecute una consulta.</span><span class="sxs-lookup"><span data-stu-id="d9255-115">Since the queries are idempotent, they won't change the data no matter how many times you run a query.</span></span> <span data-ttu-id="d9255-116">Por lo tanto, no es necesario estar restringido por un patrón DDD usado en el lado transaccional, como agregados y otros patrones, y por eso las consultas se separan del área transaccional.</span><span class="sxs-lookup"><span data-stu-id="d9255-116">Therefore, you don't need to be restricted by any DDD pattern used in the transactional side, like aggregates and other patterns, and that is why queries are separated from the transactional area.</span></span> <span data-ttu-id="d9255-117">Consulta la base de datos para obtener los datos que necesita la interfaz de usuario y devolver un ViewModel dinámico que no tiene que estar definido estáticamente en ningún lugar (no hay clases para los ViewModel), excepto en las propias instrucciones SQL.</span><span class="sxs-lookup"><span data-stu-id="d9255-117">You query the database for the data that the UI needs and return a dynamic ViewModel that does not need to be statically defined anywhere (no classes for the ViewModels) except in the SQL statements themselves.</span></span>

<span data-ttu-id="d9255-118">Puesto que se trata de un método sencillo, el código necesario para el lado de las consultas (como código que usa un micro ORM como [Dapper](https://github.com/StackExchange/Dapper)) pueden implementarse [dentro del mismo proyecto de API Web](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Queries/OrderQueries.cs).</span><span class="sxs-lookup"><span data-stu-id="d9255-118">Since this approach is simple, the code required for the queries side (such as code using a micro ORM like [Dapper](https://github.com/StackExchange/Dapper)) can be implemented [within the same Web API project](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Queries/OrderQueries.cs).</span></span> <span data-ttu-id="d9255-119">En la figura 7-4 se muestra este enfoque.</span><span class="sxs-lookup"><span data-stu-id="d9255-119">Figure 7-4 shows this approach.</span></span> <span data-ttu-id="d9255-120">Las consultas se definen en el proyecto de microservicio **Ordering.API** dentro de la solución eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="d9255-120">The queries are defined in the **Ordering.API** microservice project within the eShopOnContainers solution.</span></span>

![Captura de pantalla de la carpeta Queries del proyecto Ordering.API.](./media/cqrs-microservice-reads/ordering-api-queries-folder.png)

<span data-ttu-id="d9255-122">**Figura 7-4**.</span><span class="sxs-lookup"><span data-stu-id="d9255-122">**Figure 7-4**.</span></span> <span data-ttu-id="d9255-123">Consultas (Queries) en el microservicio de pedidos (Ordering) en eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="d9255-123">Queries in the Ordering microservice in eShopOnContainers</span></span>

## <a name="use-viewmodels-specifically-made-for-client-apps-independent-from-domain-model-constraints"></a><span data-ttu-id="d9255-124">Uso de ViewModel específicos para aplicaciones de cliente, sin las restricciones del modelo de dominio</span><span class="sxs-lookup"><span data-stu-id="d9255-124">Use ViewModels specifically made for client apps, independent from domain model constraints</span></span>

<span data-ttu-id="d9255-125">Dado que las consultas se realizan para obtener los datos que necesitan para las aplicaciones cliente, el tipo de valor devuelto puede estar hecho específicamente para los clientes, en función de los datos devueltos por las consultas.</span><span class="sxs-lookup"><span data-stu-id="d9255-125">Since the queries are performed to obtain the data needed by the client applications, the returned type can be specifically made for the clients, based on the data returned by the queries.</span></span> <span data-ttu-id="d9255-126">Estos modelos, u objetos de transferencia de datos (DTO), se denominan ViewModel.</span><span class="sxs-lookup"><span data-stu-id="d9255-126">These models, or Data Transfer Objects (DTOs), are called ViewModels.</span></span>

<span data-ttu-id="d9255-127">Los datos devueltos (ViewModel) pueden ser el resultado de combinar datos de varias entidades o tablas de la base de datos, o incluso de varios agregados definidos en el modelo de dominio para el área transaccional.</span><span class="sxs-lookup"><span data-stu-id="d9255-127">The returned data (ViewModel) can be the result of joining data from multiple entities or tables in the database, or even across multiple aggregates defined in the domain model for the transactional area.</span></span> <span data-ttu-id="d9255-128">En este caso, dado que va a crear consultas independientes del modelo de dominio, se ignoran las restricciones y los límites de agregados, y se pueden consultar cualquier tabla y columna que necesite.</span><span class="sxs-lookup"><span data-stu-id="d9255-128">In this case, because you are creating queries independent of the domain model, the aggregates boundaries and constraints are ignored and you're free to query any table and column you might need.</span></span> <span data-ttu-id="d9255-129">Este enfoque proporciona gran flexibilidad y productividad a los desarrolladores que crean o actualizan las consultas.</span><span class="sxs-lookup"><span data-stu-id="d9255-129">This approach provides great flexibility and productivity for the developers creating or updating the queries.</span></span>

<span data-ttu-id="d9255-130">Los elementos ViewModels pueden ser tipos estáticos definidos en clases (como se implementa en el microservicio de pedidos).</span><span class="sxs-lookup"><span data-stu-id="d9255-130">The ViewModels can be static types defined in classes (as is implemented in the ordering microservice).</span></span> <span data-ttu-id="d9255-131">O bien, se pueden crear dinámicamente en función de las consultas realizadas, lo que resulta ágil para los desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="d9255-131">Or they can be created dynamically based on the queries performed, which is agile for developers.</span></span>

## <a name="use-dapper-as-a-micro-orm-to-perform-queries"></a><span data-ttu-id="d9255-132">Uso de Dapper como micro ORM para realizar consultas</span><span class="sxs-lookup"><span data-stu-id="d9255-132">Use Dapper as a micro ORM to perform queries</span></span>

<span data-ttu-id="d9255-133">Para la consulta puede usar cualquier micro ORM, Entity Framework Core o incluso ADO.NET estándar.</span><span class="sxs-lookup"><span data-stu-id="d9255-133">You can use any micro ORM, Entity Framework Core, or even plain ADO.NET for querying.</span></span> <span data-ttu-id="d9255-134">En la aplicación de ejemplo, se seleccionó Dapper para el microservicio de pedidos en eShopOnContainers como un buen ejemplo de un micro ORM popular.</span><span class="sxs-lookup"><span data-stu-id="d9255-134">In the sample application, Dapper was selected for the ordering microservice in eShopOnContainers as a good example of a popular micro ORM.</span></span> <span data-ttu-id="d9255-135">Dapper puede ejecutar consultas SQL estándar con un gran rendimiento, porque es un marco de trabajo ligero.</span><span class="sxs-lookup"><span data-stu-id="d9255-135">It can run plain SQL queries with great performance, because it's a light framework.</span></span> <span data-ttu-id="d9255-136">Con Dapper, se puede escribir una consulta SQL que puede acceder a varias tablas y combinarlas.</span><span class="sxs-lookup"><span data-stu-id="d9255-136">Using Dapper, you can write a SQL query that can access and join multiple tables.</span></span>

<span data-ttu-id="d9255-137">Dapper es un proyecto de código abierto (creado originalmente por Sam Saffron) y forma parte de los bloques de creación que se usan en [Stack Overflow](https://stackoverflow.com/).</span><span class="sxs-lookup"><span data-stu-id="d9255-137">Dapper is an open-source project (original created by Sam Saffron), and is part of the building blocks used in [Stack Overflow](https://stackoverflow.com/).</span></span> <span data-ttu-id="d9255-138">Para usar Dapper, solo hay que instalarlo a través del [paquete Dapper de NuGet](https://www.nuget.org/packages/Dapper), tal y como se muestra en la ilustración siguiente:</span><span class="sxs-lookup"><span data-stu-id="d9255-138">To use Dapper, you just need to install it through the [Dapper NuGet package](https://www.nuget.org/packages/Dapper), as shown in the following figure:</span></span>

![Captura de pantalla del paquete Dapper en la vista de paquetes de NuGet.](./media/cqrs-microservice-reads/drapper-package-nuget.png)

<span data-ttu-id="d9255-140">También debe agregar una directiva `using` para que el código tenga acceso a los métodos de extensión de Dapper.</span><span class="sxs-lookup"><span data-stu-id="d9255-140">You also need to add a `using` directive so your code has access to the Dapper extension methods.</span></span>

<span data-ttu-id="d9255-141">Cuando se utiliza Dapper en el código, se usa directamente la clase <xref:System.Data.SqlClient.SqlConnection> disponible en el espacio de nombres <xref:System.Data.SqlClient>.</span><span class="sxs-lookup"><span data-stu-id="d9255-141">When you use Dapper in your code, you directly use the <xref:System.Data.SqlClient.SqlConnection> class available in the <xref:System.Data.SqlClient> namespace.</span></span> <span data-ttu-id="d9255-142">Mediante el método QueryAsync y otros métodos de extensión que extienden la clase <xref:System.Data.SqlClient.SqlConnection>, se ejecutan las consultas de una manera sencilla y eficaz.</span><span class="sxs-lookup"><span data-stu-id="d9255-142">Through the QueryAsync method and other extension methods that extend the <xref:System.Data.SqlClient.SqlConnection> class, you can run queries in a straightforward and performant way.</span></span>

## <a name="dynamic-versus-static-viewmodels"></a><span data-ttu-id="d9255-143">ViewModel dinámicos frente a estáticos</span><span class="sxs-lookup"><span data-stu-id="d9255-143">Dynamic versus static ViewModels</span></span>

<span data-ttu-id="d9255-144">Cuando se devuelven ViewModel desde el servidor a las aplicaciones cliente, se puede pensar en esos ViewModel como DTO (Objetos de transferencia de datos) que pueden ser diferentes a las entidades de dominio interno de su modelo de entidad, ya que los ViewModel contienen los datos de la forma en que la aplicación cliente necesita.</span><span class="sxs-lookup"><span data-stu-id="d9255-144">When returning ViewModels from the server-side to client apps, you can think about those ViewModels as DTOs (Data Transfer Objects) that can be different to the internal domain entities of your entity model because the ViewModels hold the data the way the client app needs.</span></span> <span data-ttu-id="d9255-145">Por lo tanto, en muchos casos, se pueden agregar datos procedentes de varias entidades de dominio y crear los ViewModel exactamente según la forma en que la aplicación cliente necesita los datos.</span><span class="sxs-lookup"><span data-stu-id="d9255-145">Therefore, in many cases, you can aggregate data coming from multiple domain entities and compose the ViewModels precisely according to how the client app needs that data.</span></span>

<span data-ttu-id="d9255-146">Esos ViewModels o DTO se pueden definir explícitamente (como clases de contenedor de datos), como la clase `OrderSummary` que se muestra en un fragmento de código posterior.</span><span class="sxs-lookup"><span data-stu-id="d9255-146">Those ViewModels or DTOs can be defined explicitly (as data holder classes), like the `OrderSummary` class shown in a later code snippet.</span></span> <span data-ttu-id="d9255-147">O bien, podría devolver simplemente ViewModels dinámicos o DTO dinámicos en función de los atributos devueltos por las consultas como un tipo dinámico.</span><span class="sxs-lookup"><span data-stu-id="d9255-147">Or, you could just return dynamic ViewModels or dynamic DTOs based on the attributes returned by your queries as a dynamic type.</span></span>

### <a name="viewmodel-as-dynamic-type"></a><span data-ttu-id="d9255-148">ViewModel como tipo dinámico</span><span class="sxs-lookup"><span data-stu-id="d9255-148">ViewModel as dynamic type</span></span>

<span data-ttu-id="d9255-149">Como se muestra en el siguiente código, las consultas pueden devolver un `ViewModel` directamente al devolver un tipo *dinámico* que internamente se basa en los atributos devueltos por una consulta.</span><span class="sxs-lookup"><span data-stu-id="d9255-149">As shown in the following code, a `ViewModel` can be directly returned by the queries by just returning a *dynamic* type that internally is based on the attributes returned by a query.</span></span> <span data-ttu-id="d9255-150">Esto significa que el subconjunto de atributos que se devuelve se basa en la propia consulta.</span><span class="sxs-lookup"><span data-stu-id="d9255-150">That means that the subset of attributes to be returned is based on the query itself.</span></span> <span data-ttu-id="d9255-151">Por tanto, si se agrega una nueva columna a la consulta o combinación, esos datos se agregan dinámicamente al `ViewModel` devuelto.</span><span class="sxs-lookup"><span data-stu-id="d9255-151">Therefore, if you add a new column to the query or join, that data is dynamically added to the returned `ViewModel`.</span></span>

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

<span data-ttu-id="d9255-152">Lo importante es que, mediante el uso de un tipo dinámico, la colección de datos devuelta dinámicamente se ensambla como un ViewModel.</span><span class="sxs-lookup"><span data-stu-id="d9255-152">The important point is that by using a dynamic type, the returned collection of data is dynamically assembled as the ViewModel.</span></span>

<span data-ttu-id="d9255-153">**Ventajas**: este enfoque reduce la necesidad de modificar las clases estáticas de ViewModel cada vez que se actualice la frase SQL de una consulta, lo que hace que este enfoque de diseño sea ágil a la hora de codificar, sencillo y rápido de evolucionar con respecto a los cambios en el futuro.</span><span class="sxs-lookup"><span data-stu-id="d9255-153">**Pros:** This approach reduces the need to modify static ViewModel classes whenever you update the SQL sentence of a query, making this design approach agile when coding, straightforward, and quick to evolve in regard to future changes.</span></span>

<span data-ttu-id="d9255-154">**Inconvenientes**: a largo plazo, los tipos dinámicos pueden perjudicar a la claridad y afectar a la compatibilidad de un servicio con las aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="d9255-154">**Cons:** In the long term, dynamic types can negatively impact the clarity and the compatibility of a service with client apps.</span></span> <span data-ttu-id="d9255-155">Además, el software middleware como Swashbuckle no puede proporcionar el mismo nivel de documentación en tipos devueltos si se utilizan tipos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="d9255-155">In addition, middleware software like Swashbuckle cannot provide the same level of documentation on returned types if using dynamic types.</span></span>

### <a name="viewmodel-as-predefined-dto-classes"></a><span data-ttu-id="d9255-156">ViewModel como clases DTO predefinidas</span><span class="sxs-lookup"><span data-stu-id="d9255-156">ViewModel as predefined DTO classes</span></span>

<span data-ttu-id="d9255-157">**Ventajas**: disponer de clases ViewModel predefinidas estáticas, como "contratos" basados en clases DTO explícitas, es definitivamente mejor para las API públicas, pero también para los microservicios a largo plazo, aunque solo los use la misma aplicación.</span><span class="sxs-lookup"><span data-stu-id="d9255-157">**Pros**: Having static, predefined ViewModel classes, like "contracts" based on explicit DTO classes, is definitely better for public APIs but also for long-term microservices, even if they are only used by the same application.</span></span>

<span data-ttu-id="d9255-158">Si quiere especificar los tipos de respuesta de Swagger, debe utilizar clases DTO explícitas como tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="d9255-158">If you want to specify response types for Swagger, you need to use explicit DTO classes as the return type.</span></span> <span data-ttu-id="d9255-159">Por lo tanto, las clases DTO predefinidas permiten ofrecer información más completa de Swagger.</span><span class="sxs-lookup"><span data-stu-id="d9255-159">Therefore, predefined DTO classes allow you to offer richer information from Swagger.</span></span> <span data-ttu-id="d9255-160">Eso mejora la documentación y la compatibilidad de la API al utilizar una API.</span><span class="sxs-lookup"><span data-stu-id="d9255-160">That improves the API documentation and compatibility when consuming an API.</span></span>

<span data-ttu-id="d9255-161">**Inconvenientes**: tal y como se mencionó anteriormente, al actualizar el código se requieren algunos pasos adicionales para actualizar las clases DTO.</span><span class="sxs-lookup"><span data-stu-id="d9255-161">**Cons**: As mentioned earlier, when updating the code, it takes some more steps to update the DTO classes.</span></span>

<span data-ttu-id="d9255-162">*Sugerencia basada en nuestra experiencia*: en las consultas que se implementan en el microservicio de pedidos en eShopOnContainers, iniciamos el desarrollo con ViewModel dinámicos porque resultaba sencillo y ágil en las primeras fases de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="d9255-162">*Tip based on our experience*: In the queries implemented at the Ordering microservice in eShopOnContainers, we started developing by using dynamic ViewModels as it was straightforward and agile on the early development stages.</span></span> <span data-ttu-id="d9255-163">Pero, una vez que se estabilizó el desarrollo, optamos por refactorizar las API y usar DTO estático o predefinido para los ViewModel, porque es más fácil para los consumidores del microservicio conocer los tipos DTO explícitos, utilizados como "contratos".</span><span class="sxs-lookup"><span data-stu-id="d9255-163">But, once the development was stabilized, we chose to refactor the APIs and use static or pre-defined DTOs for the ViewModels, because it is clearer for the microservice's consumers to know explicit DTO types, used as "contracts".</span></span>

<span data-ttu-id="d9255-164">En el ejemplo siguiente, puede ver cómo la consulta devuelve datos mediante una clase ViewModel DTO explícita: la clase OrderSummary.</span><span class="sxs-lookup"><span data-stu-id="d9255-164">In the following example, you can see how the query is returning data by using an explicit ViewModel DTO class: the OrderSummary class.</span></span>

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

#### <a name="describe-response-types-of-web-apis"></a><span data-ttu-id="d9255-165">Descripción de los tipos de respuesta de las API Web</span><span class="sxs-lookup"><span data-stu-id="d9255-165">Describe response types of Web APIs</span></span>

<span data-ttu-id="d9255-166">Lo que más preocupa a los desarrolladores que utilizan API Web y microservicios es lo que se devuelve, sobre todo los tipos de respuesta y los códigos de error (si no son los habituales).</span><span class="sxs-lookup"><span data-stu-id="d9255-166">Developers consuming web APIs and microservices are most concerned with what is returned—specifically response types and error codes (if not standard).</span></span> <span data-ttu-id="d9255-167">Los tipos de respuesta se administran en las anotaciones de datos y en los comentarios XML.</span><span class="sxs-lookup"><span data-stu-id="d9255-167">The response types are handled in the XML comments and data annotations.</span></span>

<span data-ttu-id="d9255-168">Sin una documentación correcta en la interfaz de usuario de Swagger, el consumidor desconoce los tipos que se devuelven o los códigos HTTP que se pueden devolver.</span><span class="sxs-lookup"><span data-stu-id="d9255-168">Without proper documentation in the Swagger UI, the consumer lacks knowledge of what types are being returned or what HTTP codes can be returned.</span></span> <span data-ttu-id="d9255-169">Este problema se corrige agregando <xref:Microsoft.AspNetCore.Mvc.ProducesResponseTypeAttribute?displayProperty=nameWithType>, para que Swashbuckle pueda generar información completa sobre el modelo de devolución y los valores de API, como se muestra en el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="d9255-169">That problem is fixed by adding the <xref:Microsoft.AspNetCore.Mvc.ProducesResponseTypeAttribute?displayProperty=nameWithType>, so Swashbuckle can generate richer information about the API return model and values, as shown in the following code:</span></span>

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

<span data-ttu-id="d9255-170">Pero el atributo `ProducesResponseType` no puede utilizar un tipo dinámico, sino que requiere utilizar tipos explícitos, como ViewModel DTO `OrderSummary`, se mostrado en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d9255-170">However, the `ProducesResponseType` attribute cannot use dynamic as a type but requires to use explicit types, like the `OrderSummary` ViewModel DTO, shown in the following example:</span></span>

```csharp
public class OrderSummary
{
    public int ordernumber { get; set; }
    public DateTime date { get; set; }
    public string status { get; set; }
    public double total { get; set; }
}
```

<span data-ttu-id="d9255-171">Este es otro de los motivos por los que, a largo plazo, los tipos explícitos son mejores que los tipos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="d9255-171">This is another reason why explicit returned types are better than dynamic types, in the long term.</span></span> <span data-ttu-id="d9255-172">Cuando se usa el atributo `ProducesResponseType`, también se puede especificar cuál es el resultado esperado en lo que respecta a posibles errores o códigos HTTP, como 200, 400, etc.</span><span class="sxs-lookup"><span data-stu-id="d9255-172">When using the `ProducesResponseType` attribute, you can also specify what is the expected outcome regarding possible HTTP errors/codes, like 200, 400, etc.</span></span>

<span data-ttu-id="d9255-173">En la siguiente imagen, se puede ver cómo la interfaz de usuario de Swagger de interfaz de usuario muestra la información de ResponseType.</span><span class="sxs-lookup"><span data-stu-id="d9255-173">In the following image, you can see how Swagger UI shows the ResponseType information.</span></span>

![Captura de pantalla de la página de interfaz de usuario de Swagger para Ordering API.](./media/cqrs-microservice-reads/swagger-ordering-http-api.png)

<span data-ttu-id="d9255-175">**Figura 7-5**.</span><span class="sxs-lookup"><span data-stu-id="d9255-175">**Figure 7-5**.</span></span> <span data-ttu-id="d9255-176">Interfaz de usuario de Swagger que muestra los tipos de respuesta y los posibles códigos de estado HTTP de una API Web</span><span class="sxs-lookup"><span data-stu-id="d9255-176">Swagger UI showing response types and possible HTTP status codes from a Web API</span></span>

<span data-ttu-id="d9255-177">En la ilustración anterior se pueden ver algunos valores de ejemplo basados en los tipos ViewModel, además de los posibles códigos de estado HTTP que se pueden devolver.</span><span class="sxs-lookup"><span data-stu-id="d9255-177">The image shows some example values based on the ViewModel types and the possible HTTP status codes that can be returned.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d9255-178">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="d9255-178">Additional resources</span></span>

- <span data-ttu-id="d9255-179">**Dapper**</span><span class="sxs-lookup"><span data-stu-id="d9255-179">**Dapper**</span></span>  
 <https://github.com/StackExchange/dapper-dot-net>

- <span data-ttu-id="d9255-180">**Julie Lerman. Puntos de datos: Dapper, Entity Framework y aplicaciones híbridas (artículo de MSDN magazine)**</span><span class="sxs-lookup"><span data-stu-id="d9255-180">**Julie Lerman. Data Points - Dapper, Entity Framework and Hybrid Apps (MSDN magazine article)**</span></span>  
  <https://docs.microsoft.com/archive/msdn-magazine/2016/may/data-points-dapper-entity-framework-and-hybrid-apps>

- <span data-ttu-id="d9255-181">**Páginas de ayuda de ASP.NET Core Web API mediante Swagger**</span><span class="sxs-lookup"><span data-stu-id="d9255-181">**ASP.NET Core Web API Help Pages using Swagger**</span></span>  
  <https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger?tabs=visual-studio>

>[!div class="step-by-step"]
><span data-ttu-id="d9255-182">[Anterior](eshoponcontainers-cqrs-ddd-microservice.md)
>[Siguiente](ddd-oriented-microservice.md)</span><span class="sxs-lookup"><span data-stu-id="d9255-182">[Previous](eshoponcontainers-cqrs-ddd-microservice.md)
[Next](ddd-oriented-microservice.md)</span></span>
