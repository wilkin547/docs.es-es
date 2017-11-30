---
title: "Implementación de lecturas/consultas en un microservicio CQRS"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Implementación de lecturas/consultas en un microservicio CQRS"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: e017aaaa701d8033110be8d6244d3e1120fc4fd9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-readsqueries-in-a-cqrs-microservice"></a><span data-ttu-id="18219-104">Implementación de lecturas/consultas en un microservicio CQRS</span><span class="sxs-lookup"><span data-stu-id="18219-104">Implementing reads/queries in a CQRS microservice</span></span>

<span data-ttu-id="18219-105">Para lecturas/las consultas, la ordenación microservicio desde la aplicación de referencia eShopOnContainers implementa las consultas por separado desde el modelo DDD y el área transaccional.</span><span class="sxs-lookup"><span data-stu-id="18219-105">For reads/queries, the ordering microservice from the eShopOnContainers reference application implements the queries independently from the DDD model and transactional area.</span></span> <span data-ttu-id="18219-106">Esto se hacía principalmente porque las demandas para las consultas y transacciones son considerablemente diferentes.</span><span class="sxs-lookup"><span data-stu-id="18219-106">This was done primarily because the demands for queries and for transactions are drastically different.</span></span> <span data-ttu-id="18219-107">Escrituras de ejecutan las transacciones que deben ser compatibles con la lógica del dominio.</span><span class="sxs-lookup"><span data-stu-id="18219-107">Writes execute transactions that must be compliant with the domain logic.</span></span> <span data-ttu-id="18219-108">Por otro lado, las consultas, son idempotentes y pueden se segregan de las reglas de dominio.</span><span class="sxs-lookup"><span data-stu-id="18219-108">Queries, on the other hand, are idempotent and can be segregated from the domain rules.</span></span>

<span data-ttu-id="18219-109">El enfoque es sencillo, tal como se muestra en la figura 9-3.</span><span class="sxs-lookup"><span data-stu-id="18219-109">The approach is simple, as shown in Figure 9-3.</span></span> <span data-ttu-id="18219-110">La interfaz API se implementa mediante los controladores de API Web mediante cualquier infraestructura (por ejemplo, un micro ORM como Dapper) y devolver ViewModels dinámica según las necesidades de las aplicaciones de interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="18219-110">The API interface is implemented by the Web API controllers using any infrastructure (such as a micro ORM like Dapper) and returning dynamic ViewModels depending on the needs of the UI applications.</span></span>

![](./media/image3.png)

<span data-ttu-id="18219-111">**Figura 9-3**.</span><span class="sxs-lookup"><span data-stu-id="18219-111">**Figure 9-3**.</span></span> <span data-ttu-id="18219-112">El enfoque más sencillo para las consultas en un microservicio CQRS</span><span class="sxs-lookup"><span data-stu-id="18219-112">The simplest approach for queries in a CQRS microservice</span></span>

<span data-ttu-id="18219-113">Este es el enfoque más sencillo posible para las consultas.</span><span class="sxs-lookup"><span data-stu-id="18219-113">This is the simplest possible approach for queries.</span></span> <span data-ttu-id="18219-114">Las definiciones de consulta la base de datos de consulta y devuelven un ViewModel dinámico creado sobre la marcha para cada consulta.</span><span class="sxs-lookup"><span data-stu-id="18219-114">The query definitions query the database and return a dynamic ViewModel built on the fly for each query.</span></span> <span data-ttu-id="18219-115">Puesto que las consultas son idempotentes, no cambiará los datos sin importar cuántas veces se ejecuta una consulta.</span><span class="sxs-lookup"><span data-stu-id="18219-115">Since the queries are idempotent, they will not change the data no matter how many times you run a query.</span></span> <span data-ttu-id="18219-116">Por lo tanto, no es necesario estar restringida por cualquier patrón DDD usado en el lado transaccional, como agregados y otros patrones, y por eso se separan las consultas desde el área transaccional.</span><span class="sxs-lookup"><span data-stu-id="18219-116">Therefore, you do not need to be restricted by any DDD pattern used in the transactional side, like aggregates and other patterns, and that is why queries are separated from the transactional area.</span></span> <span data-ttu-id="18219-117">Basta con consultar la base de datos para los datos que necesita la interfaz de usuario y devolver un ViewModel dinámico que no tienen que estáticamente desde cualquier lugar (no hay clases para la ViewModels) definida excepto en las instrucciones SQL por sí mismos.</span><span class="sxs-lookup"><span data-stu-id="18219-117">You simply query the database for the data that the UI needs and return a dynamic ViewModel that does not need to be statically defined anywhere (no classes for the ViewModels) except in the SQL statements themselves.</span></span>

<span data-ttu-id="18219-118">Puesto que se trata de un método sencillo, el código necesario para el lado de las consultas (como código que usa un micro ORM como [Dapper](https://github.com/StackExchange/Dapper)) pueden implementarse [dentro del mismo proyecto de API Web](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Queries/OrderQueries.cs).</span><span class="sxs-lookup"><span data-stu-id="18219-118">Since this is a simple approach, the code required for the queries side (such as code using a micro ORM like [Dapper](https://github.com/StackExchange/Dapper)) can be implemented [within the same Web API project](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Queries/OrderQueries.cs).</span></span> <span data-ttu-id="18219-119">Figura 9-4 muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="18219-119">Figure 9-4 shows this.</span></span> <span data-ttu-id="18219-120">Las consultas se definen en el **Ordering.API** microservicio proyecto dentro de la solución eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="18219-120">The queries are defined in the **Ordering.API** microservice project within the eShopOnContainers solution.</span></span>

![](./media/image4.png)

<span data-ttu-id="18219-121">**Figura 9-4**.</span><span class="sxs-lookup"><span data-stu-id="18219-121">**Figure 9-4**.</span></span> <span data-ttu-id="18219-122">Consultas en el orden microservicio en eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="18219-122">Queries in the Ordering microservice in eShopOnContainers</span></span>

## <a name="using-viewmodels-specifically-made-for-client-apps-independent-from-domain-model-constraints"></a><span data-ttu-id="18219-123">Usar ViewModels fabricado específicamente para las aplicaciones de cliente, independientes de las restricciones del modelo de dominio</span><span class="sxs-lookup"><span data-stu-id="18219-123">Using ViewModels specifically made for client apps, independent from domain model constraints</span></span>

<span data-ttu-id="18219-124">Dado que las consultas se realizan para obtener los datos necesarios para las aplicaciones cliente, el tipo de valor devuelto se puede realizar específicamente para los clientes, en función de los datos devueltos por las consultas.</span><span class="sxs-lookup"><span data-stu-id="18219-124">Since the queries are performed to obtain the data needed by the client applications, the returned type can be specifically made for the clients, based on the data returned by the queries.</span></span> <span data-ttu-id="18219-125">Estos modelos o los objetos de transferencia de datos (dto), se denominan ViewModels.</span><span class="sxs-lookup"><span data-stu-id="18219-125">These models, or Data Transfer Objects (DTOs), are called ViewModels.</span></span>

<span data-ttu-id="18219-126">Los datos devueltos (ViewModel) pueden ser el resultado de combinar datos de varias entidades o tablas en la base de datos, o incluso entre varios agregados definidos en el modelo de dominio para el área transaccional.</span><span class="sxs-lookup"><span data-stu-id="18219-126">The returned data (ViewModel) can be the result of joining data from multiple entities or tables in the database, or even across multiple aggregates defined in the domain model for the transactional area.</span></span> <span data-ttu-id="18219-127">En este caso, dado que va a crear consultas independientes del modelo de dominio, completamente se omiten las restricciones y límites de agregados y está disponible consultar cualquier tabla y columna que tenga.</span><span class="sxs-lookup"><span data-stu-id="18219-127">In this case, because you are creating queries independent of the domain model, the aggregates boundaries and constraints are completely ignored and you are free to query any table and column you might need.</span></span> <span data-ttu-id="18219-128">Este enfoque proporciona gran flexibilidad y la productividad de los desarrolladores crear o actualizar las consultas.</span><span class="sxs-lookup"><span data-stu-id="18219-128">This approach provides great flexibility and productivity for the developers creating or updating the queries.</span></span>

<span data-ttu-id="18219-129">El ViewModels puede ser definidos en las clases de tipos estáticos.</span><span class="sxs-lookup"><span data-stu-id="18219-129">The ViewModels can be static types defined in classes.</span></span> <span data-ttu-id="18219-130">O bien, se pueden crear dinámicamente en función de las consultas realizadas (tal y como se implementa en la ordenación microservicio), que es muy ágil para desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="18219-130">Or they can be created dynamically based on the queries performed (as is implemented in the ordering microservice), which is very agile for developers.</span></span>

## <a name="using-dapper-as-a-micro-orm-to-perform-queries"></a><span data-ttu-id="18219-131">Uso de Dapper como un ORM micro para realizar consultas</span><span class="sxs-lookup"><span data-stu-id="18219-131">Using Dapper as a micro ORM to perform queries</span></span> 

<span data-ttu-id="18219-132">Puede usar cualquier micro ORM, Entity Framework Core o incluso sin formato ADO.NET para la consulta.</span><span class="sxs-lookup"><span data-stu-id="18219-132">You can use any micro ORM, Entity Framework Core, or even plain ADO.NET for querying.</span></span> <span data-ttu-id="18219-133">En la aplicación de ejemplo, hemos seleccionado Dapper para la ordenación microservicio en eShopOnContainers como un buen ejemplo de una popular ORM micro.</span><span class="sxs-lookup"><span data-stu-id="18219-133">In the sample application, we selected Dapper for the ordering microservice in eShopOnContainers as a good example of a popular micro ORM.</span></span> <span data-ttu-id="18219-134">Se pueden ejecutar consultas SQL sin formato con un gran rendimiento, porque es un marco de trabajo muy claro.</span><span class="sxs-lookup"><span data-stu-id="18219-134">It can run plain SQL queries with great performance, because it is a very light framework.</span></span> <span data-ttu-id="18219-135">Con Dapper, puede escribir una consulta SQL que se puede obtener acceso y combinar varias tablas.</span><span class="sxs-lookup"><span data-stu-id="18219-135">Using Dapper, you can write a SQL query that can access and join multiple tables.</span></span>

<span data-ttu-id="18219-136">Dapper es un proyecto de código abierto (original creado por Sam Saffron) y forma parte de los bloques de creación que se usan en [desbordamiento de la pila](https://stackoverflow.com/).</span><span class="sxs-lookup"><span data-stu-id="18219-136">Dapper is an open source project (original created by Sam Saffron), and is part of the building blocks used in [Stack Overflow](https://stackoverflow.com/).</span></span> <span data-ttu-id="18219-137">Para usar Dapper, solo necesita instalar a través de la [paquete NuGet Dapper](https://www.nuget.org/packages/Dapper), tal y como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="18219-137">To use Dapper, you just need to install it through the [Dapper NuGet package](https://www.nuget.org/packages/Dapper), as shown in the following figure.</span></span>

![](./media/image5.png)

<span data-ttu-id="18219-138">También necesitará agregar un uso de la instrucción por lo que el código tiene acceso a los métodos de extensión Dapper.</span><span class="sxs-lookup"><span data-stu-id="18219-138">You will also need to add a using statement so your code has access to the Dapper extension methods.</span></span>

<span data-ttu-id="18219-139">Cuando usas Dapper en el código, utilizar directamente la clase SqlClient disponible en el espacio de nombres System.Data.SqlClient.</span><span class="sxs-lookup"><span data-stu-id="18219-139">When you use Dapper in your code, you directly use the SqlClient class available in the System.Data.SqlClient namespace.</span></span> <span data-ttu-id="18219-140">Mediante el método QueryAsync y otros métodos de extensión que extienden la clase SqlClient, simplemente puede ejecutar consultas de una manera sencilla y eficaz.</span><span class="sxs-lookup"><span data-stu-id="18219-140">Through the QueryAsync method and other extension methods which extend the SqlClient class, you can simply run queries in a straightforward and performant way.</span></span>

## <a name="dynamic-and-static-viewmodels"></a><span data-ttu-id="18219-141">ViewModels estáticas y dinámicas</span><span class="sxs-lookup"><span data-stu-id="18219-141">Dynamic and static ViewModels</span></span>

<span data-ttu-id="18219-142">Como se muestra en el siguiente código de la ordenación microservicio, la mayoría de los ViewModels devueltos por las consultas se implementa como *dinámica*.</span><span class="sxs-lookup"><span data-stu-id="18219-142">As shown in the following code from the ordering microservice, most of the ViewModels returned by the queries are implemented as *dynamic*.</span></span> <span data-ttu-id="18219-143">Esto significa que el subconjunto de atributos que se devuelve se basa en la propia consulta.</span><span class="sxs-lookup"><span data-stu-id="18219-143">That means that the subset of attributes to be returned is based on the query itself.</span></span> <span data-ttu-id="18219-144">Si agrega una nueva columna a la consulta o una combinación, esos datos se agregan dinámicamente al ViewModel devuelta.</span><span class="sxs-lookup"><span data-stu-id="18219-144">If you add a new column to the query or join, that data is dynamically added to the returned ViewModel.</span></span> <span data-ttu-id="18219-145">Este enfoque reduce la necesidad de modificar consultas en respuesta a las actualizaciones para el modelo de datos subyacente, haciendo que este enfoque de diseño más flexible y con tolerancia a errores de los cambios futuros.</span><span class="sxs-lookup"><span data-stu-id="18219-145">This approach reduces the need to modify queries in response to updates to the underlying data model, making this design approach more flexible and tolerant of future changes.</span></span>

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

<span data-ttu-id="18219-146">Lo importante es que mediante el uso de un tipo dinámico, la colección devuelta de datos se dinámicamente monta como el modelo de vista.</span><span class="sxs-lookup"><span data-stu-id="18219-146">The important point is that by using a dynamic type, the returned collection of data will be dynamically assembled as the ViewModel.</span></span>

<span data-ttu-id="18219-147">Para la mayoría de las consultas, no es necesario predefinir una clase DTO o ViewModel, lo que facilita su codificación sencillo y productiva.</span><span class="sxs-lookup"><span data-stu-id="18219-147">For most queries, you do not need to predefine a DTO or ViewModel class, which makes coding them straightforward and productive.</span></span> <span data-ttu-id="18219-148">Sin embargo, puede predefinir ViewModels (por ejemplo, Dto predefinidos) si desea que estén ViewModels con una definición más restringida como contratos.</span><span class="sxs-lookup"><span data-stu-id="18219-148">However, you can predefine ViewModels (like predefined DTOs) if you want to have ViewModels with a more restricted definition as contracts.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="18219-149">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="18219-149">Additional resources</span></span>

-   <span data-ttu-id="18219-150">**Dapper**
    [*https://github.com/StackExchange/dapper-dot-net*](https://github.com/StackExchange/dapper-dot-net)</span><span class="sxs-lookup"><span data-stu-id="18219-150">**Dapper**
[*https://github.com/StackExchange/dapper-dot-net*](https://github.com/StackExchange/dapper-dot-net)</span></span>

-   <span data-ttu-id="18219-151">**Julia Lerman. Puntos de datos - Dapper, Entity Framework y aplicaciones híbridas (artículo de MSDN Mag.)**</span><span class="sxs-lookup"><span data-stu-id="18219-151">**Julie Lerman. Data Points - Dapper, Entity Framework and Hybrid Apps (MSDN Mag. article)**</span></span>

    <span data-ttu-id="18219-152">*https://msdn.Microsoft.com/en-us/Magazine/mt703432.aspx*</span><span class="sxs-lookup"><span data-stu-id="18219-152">*https://msdn.microsoft.com/en-us/magazine/mt703432.aspx*</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="18219-153">[Anterior] (eshoponcontainers-cqrs-ddd-microservice.md) [siguiente] (ddd-orientada a servicios-microservice.md)</span><span class="sxs-lookup"><span data-stu-id="18219-153">[Previous] (eshoponcontainers-cqrs-ddd-microservice.md) [Next] (ddd-oriented-microservice.md)</span></span>
