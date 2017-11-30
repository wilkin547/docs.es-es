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
# <a name="implementing-readsqueries-in-a-cqrs-microservice"></a>Implementación de lecturas/consultas en un microservicio CQRS

Para lecturas/las consultas, la ordenación microservicio desde la aplicación de referencia eShopOnContainers implementa las consultas por separado desde el modelo DDD y el área transaccional. Esto se hacía principalmente porque las demandas para las consultas y transacciones son considerablemente diferentes. Escrituras de ejecutan las transacciones que deben ser compatibles con la lógica del dominio. Por otro lado, las consultas, son idempotentes y pueden se segregan de las reglas de dominio.

El enfoque es sencillo, tal como se muestra en la figura 9-3. La interfaz API se implementa mediante los controladores de API Web mediante cualquier infraestructura (por ejemplo, un micro ORM como Dapper) y devolver ViewModels dinámica según las necesidades de las aplicaciones de interfaz de usuario.

![](./media/image3.png)

**Figura 9-3**. El enfoque más sencillo para las consultas en un microservicio CQRS

Este es el enfoque más sencillo posible para las consultas. Las definiciones de consulta la base de datos de consulta y devuelven un ViewModel dinámico creado sobre la marcha para cada consulta. Puesto que las consultas son idempotentes, no cambiará los datos sin importar cuántas veces se ejecuta una consulta. Por lo tanto, no es necesario estar restringida por cualquier patrón DDD usado en el lado transaccional, como agregados y otros patrones, y por eso se separan las consultas desde el área transaccional. Basta con consultar la base de datos para los datos que necesita la interfaz de usuario y devolver un ViewModel dinámico que no tienen que estáticamente desde cualquier lugar (no hay clases para la ViewModels) definida excepto en las instrucciones SQL por sí mismos.

Puesto que se trata de un método sencillo, el código necesario para el lado de las consultas (como código que usa un micro ORM como [Dapper](https://github.com/StackExchange/Dapper)) pueden implementarse [dentro del mismo proyecto de API Web](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Queries/OrderQueries.cs). Figura 9-4 muestra cómo hacerlo. Las consultas se definen en el **Ordering.API** microservicio proyecto dentro de la solución eShopOnContainers.

![](./media/image4.png)

**Figura 9-4**. Consultas en el orden microservicio en eShopOnContainers

## <a name="using-viewmodels-specifically-made-for-client-apps-independent-from-domain-model-constraints"></a>Usar ViewModels fabricado específicamente para las aplicaciones de cliente, independientes de las restricciones del modelo de dominio

Dado que las consultas se realizan para obtener los datos necesarios para las aplicaciones cliente, el tipo de valor devuelto se puede realizar específicamente para los clientes, en función de los datos devueltos por las consultas. Estos modelos o los objetos de transferencia de datos (dto), se denominan ViewModels.

Los datos devueltos (ViewModel) pueden ser el resultado de combinar datos de varias entidades o tablas en la base de datos, o incluso entre varios agregados definidos en el modelo de dominio para el área transaccional. En este caso, dado que va a crear consultas independientes del modelo de dominio, completamente se omiten las restricciones y límites de agregados y está disponible consultar cualquier tabla y columna que tenga. Este enfoque proporciona gran flexibilidad y la productividad de los desarrolladores crear o actualizar las consultas.

El ViewModels puede ser definidos en las clases de tipos estáticos. O bien, se pueden crear dinámicamente en función de las consultas realizadas (tal y como se implementa en la ordenación microservicio), que es muy ágil para desarrolladores.

## <a name="using-dapper-as-a-micro-orm-to-perform-queries"></a>Uso de Dapper como un ORM micro para realizar consultas 

Puede usar cualquier micro ORM, Entity Framework Core o incluso sin formato ADO.NET para la consulta. En la aplicación de ejemplo, hemos seleccionado Dapper para la ordenación microservicio en eShopOnContainers como un buen ejemplo de una popular ORM micro. Se pueden ejecutar consultas SQL sin formato con un gran rendimiento, porque es un marco de trabajo muy claro. Con Dapper, puede escribir una consulta SQL que se puede obtener acceso y combinar varias tablas.

Dapper es un proyecto de código abierto (original creado por Sam Saffron) y forma parte de los bloques de creación que se usan en [desbordamiento de la pila](https://stackoverflow.com/). Para usar Dapper, solo necesita instalar a través de la [paquete NuGet Dapper](https://www.nuget.org/packages/Dapper), tal y como se muestra en la ilustración siguiente.

![](./media/image5.png)

También necesitará agregar un uso de la instrucción por lo que el código tiene acceso a los métodos de extensión Dapper.

Cuando usas Dapper en el código, utilizar directamente la clase SqlClient disponible en el espacio de nombres System.Data.SqlClient. Mediante el método QueryAsync y otros métodos de extensión que extienden la clase SqlClient, simplemente puede ejecutar consultas de una manera sencilla y eficaz.

## <a name="dynamic-and-static-viewmodels"></a>ViewModels estáticas y dinámicas

Como se muestra en el siguiente código de la ordenación microservicio, la mayoría de los ViewModels devueltos por las consultas se implementa como *dinámica*. Esto significa que el subconjunto de atributos que se devuelve se basa en la propia consulta. Si agrega una nueva columna a la consulta o una combinación, esos datos se agregan dinámicamente al ViewModel devuelta. Este enfoque reduce la necesidad de modificar consultas en respuesta a las actualizaciones para el modelo de datos subyacente, haciendo que este enfoque de diseño más flexible y con tolerancia a errores de los cambios futuros.

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

Lo importante es que mediante el uso de un tipo dinámico, la colección devuelta de datos se dinámicamente monta como el modelo de vista.

Para la mayoría de las consultas, no es necesario predefinir una clase DTO o ViewModel, lo que facilita su codificación sencillo y productiva. Sin embargo, puede predefinir ViewModels (por ejemplo, Dto predefinidos) si desea que estén ViewModels con una definición más restringida como contratos.

#### <a name="additional-resources"></a>Recursos adicionales

-   **Dapper**
    [*https://github.com/StackExchange/dapper-dot-net*](https://github.com/StackExchange/dapper-dot-net)

-   **Julia Lerman. Puntos de datos - Dapper, Entity Framework y aplicaciones híbridas (artículo de MSDN Mag.)**

    *https://msdn.Microsoft.com/en-us/Magazine/mt703432.aspx*


>[!div class="step-by-step"]
[Anterior] (eshoponcontainers-cqrs-ddd-microservice.md) [siguiente] (ddd-orientada a servicios-microservice.md)
