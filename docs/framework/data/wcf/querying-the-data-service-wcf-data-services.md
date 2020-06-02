---
title: Consultar el servicio de datos (Data Services de WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, client library
- WCF Data Services, querying
- WCF Data Services, accessing data
ms.assetid: 823e9444-27aa-4f1f-be8e-0486d67f54c0
ms.openlocfilehash: 13334f6425c47e45d729d606d99602a99f35d8e6
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286163"
---
# <a name="querying-the-data-service-wcf-data-services"></a>Consultar el servicio de datos (Data Services de WCF)

La biblioteca de cliente de WCF Data Services permite ejecutar consultas en un servicio de datos usando patrones de programación de .NET Framework conocidos, incluido el uso de Language Integrated Query (LINQ). La biblioteca de cliente traduce una consulta, que se define en el cliente como instancia de la clase <xref:System.Data.Services.Client.DataServiceQuery%601>, en un mensaje de solicitud HTTP GET. La biblioteca recibe el mensaje de respuesta y lo traduce en instancias de las clases del servicio de datos de cliente. El seguimiento de estas clases lo realiza la clase <xref:System.Data.Services.Client.DataServiceContext> a la que pertenece <xref:System.Data.Services.Client.DataServiceQuery%601>.

## <a name="data-service-queries"></a>Consultas del servicio de datos

La clase <xref:System.Data.Services.Client.DataServiceQuery%601> genérica representa una consulta que devuelve una colección de cero o más instancias de tipo de entidad. Una consulta del servicio de datos siempre pertenece al contexto de un servicio de datos existente. Este contexto mantiene la información necesaria del URI del servicio y la de los metadatos para crear y ejecutar la consulta.

Cuando se usa el cuadro de diálogo **Agregar referencia de servicio** para agregar un servicio de datos a una aplicación cliente basada en .NET Framework, se crea una clase de contenedor de entidades que hereda de la <xref:System.Data.Services.Client.DataServiceContext> clase. Esta clase incluye propiedades que devuelven instancias de <xref:System.Data.Services.Client.DataServiceQuery%601> con tipo. Existe una propiedad para cada conjunto de entidades que expone el servicio de datos. Estas propiedades facilitan la creación de una instancia de <xref:System.Data.Services.Client.DataServiceQuery%601> con tipo.

Las consultas se ejecutan en los escenarios siguientes:

- Cuando se enumeran los resultados implícitamente, por ejemplo:

  - Cuando se enumeran una propiedad de la clase <xref:System.Data.Services.Client.DataServiceContext> que representa un conjunto de entidades, como ocurre en un bucle `foreach` (C#) o `For Each` (Visual Basic).

  - Cuando se asigna la consulta a una colección `List`.

- Cuando se llama explícitamente a los métodos <xref:System.Data.Services.Client.DataServiceQuery%601.Execute%2A> o <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A>.

- Cuando se llama a un operador de ejecución de consultas LINQ, como <xref:System.Linq.Enumerable.First%2A> o <xref:System.Linq.Enumerable.Single%2A>.

Cuando se ejecuta la siguiente consulta, devuelve todas las entidades `Customers` del servicio de datos de Northwind:

[!code-csharp[Astoria Northwind Client#GetAllCustomersSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#getallcustomersspecific)]
[!code-vb[Astoria Northwind Client#GetAllCustomersSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#getallcustomersspecific)]

Para obtener más información, vea [Cómo: ejecutar consultas de servicio de datos](how-to-execute-data-service-queries-wcf-data-services.md).

El cliente de WCF Data Services admite consultas para objetos enlazados en tiempo de ejecución, como cuando se usa el tipo *dinámico* en C#. Sin embargo, por motivos de rendimiento, siempre debe crear consultas fuertemente tipadas en el servicio de datos. El cliente no admite los objetos de tipo y dinámicos de la clase <xref:System.Tuple>.

## <a name="linq-queries"></a>Consultas LINQ

Dado <xref:System.Data.Services.Client.DataServiceQuery%601> que la clase implementa la <xref:System.Linq.IQueryable%601> interfaz definida por LINQ, la biblioteca de cliente de WCF Data Services puede transformar consultas LINQ en datos del conjunto de entidades en un URI que representa una expresión de consulta evaluada en un recurso del servicio de datos. En el siguiente ejemplo hay una consulta LINQ que es equivalente a la clase <xref:System.Data.Services.Client.DataServiceQuery%601> anterior que devuelve `Orders` con un costo de flete de más de 30 dólares y ordena los resultados por el costo del flete:

[!code-csharp[Astoria Northwind Client#AddQueryOptionsLinqSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addqueryoptionslinqspecific)]
[!code-vb[Astoria Northwind Client#AddQueryOptionsLinqSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addqueryoptionslinqspecific)]

Esta consulta LINQ se traduce en el siguiente URI de consulta que se ejecuta en el servicio de datos de [Inicio rápido](quickstart-wcf-data-services.md) basado en Northwind:

```http
http://localhost:12345/Northwind.svc/Orders?Orderby=ShippedDate&?filter=Freight gt 30
```

> [!NOTE]
> El conjunto de consultas que se pueden expresar en la sintaxis de LINQ es más amplio que los habilitados en la sintaxis URI basada en REST (Representational State Transfer) usada por los servicios de datos. Cuando la consulta no se puede asignar a ningún URI del servicio de datos de destino, se produce una excepción <xref:System.NotSupportedException>.

Para obtener más información, vea [consideraciones sobre LINQ](linq-considerations-wcf-data-services.md).

## <a name="adding-query-options"></a>Agregar opciones de consulta

Las consultas del servicio de datos admiten todas las opciones de consulta que proporciona WCF Data Services. Puede llamar al método <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> para anexar opciones de consulta a una instancia de <xref:System.Data.Services.Client.DataServiceQuery%601>. El método <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> devuelve una nueva instancia de <xref:System.Data.Services.Client.DataServiceQuery%601> que es equivalente a la consulta original pero con el nuevo conjunto de opciones de consulta. Cuando se ejecuta la siguiente consulta, devuelve el valor `Orders` filtrado por el valor `Freight` y ordenado por `OrderID`, en orden descendente:

[!code-csharp[Astoria Northwind Client#AddQueryOptionsSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addqueryoptionsspecific)]
[!code-vb[Astoria Northwind Client#AddQueryOptionsSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addqueryoptionsspecific)]

Puede usar la opción de consulta `$orderby` tanto para ordenar como para filtrar una consulta basada en una sola propiedad, como en el siguiente ejemplo que filtra y ordena los objetos `Orders` devueltos basados en el valor de la propiedad `Freight`:

[!code-csharp[Astoria Northwind Client#OrderWithFilter](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#orderwithfilter)]
[!code-vb[Astoria Northwind Client#OrderWithFilter](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#orderwithfilter)]

Puede llamar al método <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> consecutivamente para construir expresiones de consulta complejas. Para obtener más información, vea [Cómo: agregar opciones de consulta a una consulta de servicio de datos](how-to-add-query-options-to-a-data-service-query-wcf-data-services.md).

Las opciones de consulta le proporcionan otra forma de expresar los componentes estáticos de una consulta LINQ. Para obtener más información, vea [consideraciones sobre LINQ](linq-considerations-wcf-data-services.md).

> [!NOTE]
> La opción de consulta `$select` no se puede agregar a ningún URI de la consulta mediante el uso del método <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A>. Se recomienda usar el método <xref:System.Linq.Enumerable.Select%2A> de LINQ para que el cliente genere la opción de consulta `$select` en el URI de solicitud.

<a name="executingQueries"></a>

## <a name="client-versus-server-execution"></a>Ejecución de cliente frente a servidor

El cliente ejecuta una consulta en dos partes. Siempre que sea posible, las expresiones de una consulta primero se evalúan en el cliente y, a continuación, se generan y se envían al servicio de datos para su evaluación en los datos del servicio. Considere la siguiente consulta LINQ:

[!code-csharp[Astoria Northwind Client#LinqQueryClientEvalSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqqueryclientevalspecific)]
[!code-vb[Astoria Northwind Client#LinqQueryClientEvalSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqqueryclientevalspecific)]

En este ejemplo, la expresión `(basePrice – (basePrice * discount))` se evalúa en el cliente. Por ello, el URI de la consulta real `http://localhost:12345/northwind.svc/Products()?$filter=(UnitPrice gt 90.00M) and substringof('bike',ProductName)` que se envía al servicio de datos contiene el valor decimal ya calculado de `90` en la cláusula de filtro. El resto de las partes de la expresión de filtrado, incluida la expresión de subcadena, las evalúa el servicio de datos. Las expresiones que se evalúan en el cliente siguen la semántica de Common Language Runtime (CLR), mientras que las expresiones enviadas al servicio de datos se basan en la implementación del servicio de datos del protocolo OData. Debe tener en cuenta los escenarios en los que esta evaluación independiente pueda causar resultados inesperados, como cuando tanto el cliente como el servidor realicen evaluaciones basadas en la hora en distintas zonas horarias.

## <a name="query-responses"></a>Respuestas de consulta

Cuando se ejecuta, el objeto <xref:System.Data.Services.Client.DataServiceQuery%601> devuelve una interfaz <xref:System.Collections.Generic.IEnumerable%601> del tipo de entidad solicitado. Este resultado de consulta se puede convertir en un objeto <xref:System.Data.Services.Client.QueryOperationResponse%601>, como en el siguiente ejemplo:

[!code-csharp[Astoria Northwind Client#GetResponseSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#getresponsespecific)]
[!code-vb[Astoria Northwind Client#GetResponseSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#getresponsespecific)]

Las instancias de tipo de entidad que representan entidades del servicio de datos se crean en el cliente mediante un proceso denominado materialización de objetos. Para obtener más información, consulte [materialización de objetos](object-materialization-wcf-data-services.md). El objeto <xref:System.Data.Services.Client.QueryOperationResponse%601> implementa <xref:System.Collections.Generic.IEnumerable%601> para proporcionar acceso a los resultados de la consulta.

<xref:System.Data.Services.Client.QueryOperationResponse%601> también tiene los siguientes miembros que le permiten tener acceso a información adicional sobre el resultado de una consulta:

- La propiedad <xref:System.Data.Services.Client.OperationResponse.Error%2A>: obtiene un error provocado por la operación, si se ha producido alguna.

- La propiedad <xref:System.Data.Services.Client.OperationResponse.Headers%2A>: contiene una colección de encabezados de respuesta HTTP asociados con la respuesta de la consulta.

- La propiedad <xref:System.Data.Services.Client.QueryOperationResponse.Query%2A>: obtiene el objeto <xref:System.Data.Services.Client.DataServiceQuery%601> original generado por <xref:System.Data.Services.Client.QueryOperationResponse%601>.

- La propiedad <xref:System.Data.Services.Client.OperationResponse.StatusCode%2A>: obtiene el código de respuesta HTTP para la respuesta de la consulta.

- La propiedad <xref:System.Data.Services.Client.QueryOperationResponse%601.TotalCount%2A>: obtiene el número total de entidades establecidas cuando se llamó al método <xref:System.Data.Services.Client.DataServiceQuery%601.IncludeTotalCount%2A> en <xref:System.Data.Services.Client.DataServiceQuery%601>.

- La propiedad <xref:System.Data.Services.Client.QueryOperationResponse.GetContinuation%2A>: devuelve un objeto <xref:System.Data.Services.Client.DataServiceQueryContinuation> que contiene el URI de la siguiente página de resultados.

De forma predeterminada, WCF Data Services solo devuelve datos seleccionados explícitamente por el URI de la consulta. De esta forma, puede cargar explícitamente datos desde el servicio de datos cuando sea necesario. Se envía una solicitud al servicio de datos cada vez que carga datos explícitamente desde el servicio de datos. Los datos que se pueden cargar explícitamente incluyen entidades relacionadas, datos de respuesta paginados y flujos de datos binarios.

> [!NOTE]
> Puesto que un servicio de datos puede devolver una respuesta paginada, se recomienda que la aplicación use el patrón de programación para controlar la respuesta paginada de un servicio de datos. Para obtener más información, vea [cargar contenido diferido](loading-deferred-content-wcf-data-services.md).

La cantidad de datos devueltos por una consulta también se puede reducir especificando que solo se devuelvan algunas propiedades de una entidad en la respuesta. Para obtener más información, consulte [proyecciones de consultas](query-projections-wcf-data-services.md).

## <a name="getting-a-count-of-the-total-number-of-entities-in-the-set"></a>Obtener un recuento del número total de entidades del conjunto

En algunos escenarios, es útil saber el número total de entidades de una entidad establecida y no solamente el número devuelto por la consulta. Llame al método <xref:System.Data.Services.Client.DataServiceQuery%601.IncludeTotalCount%2A> de <xref:System.Data.Services.Client.DataServiceQuery%601> para solicitar que se incluya este recuento total de entidades del conjunto con los resultados de la consulta. En este caso, la propiedad <xref:System.Data.Services.Client.QueryOperationResponse%601.TotalCount%2A> del objeto <xref:System.Data.Services.Client.QueryOperationResponse%601> devuelto devuelve el número total de entidades del conjunto.

Además, puede obtener el recuento total de entidades del conjunto como valor de las estructuras <xref:System.Int32> o <xref:System.Int64> llamando a los métodos <xref:System.Linq.Enumerable.Count%2A> o <xref:System.Linq.Enumerable.LongCount%2A>, respectivamente. Cuando se llama a estos métodos, no se devuelve ningún objeto <xref:System.Data.Services.Client.QueryOperationResponse%601>; solo se devuelve el valor de recuento. Para obtener más información, vea [Cómo: determinar el número de entidades devueltas por una consulta](number-of-entities-returned-by-a-query-wcf.md).

## <a name="in-this-section"></a>En esta sección

- [Proyecciones de consultas](query-projections-wcf-data-services.md)

- [Materialización de objetos](object-materialization-wcf-data-services.md)

- [Consideraciones sobre LINQ](linq-considerations-wcf-data-services.md)

- [Procedimiento para ejecutar consultas de servicios de datos](how-to-execute-data-service-queries-wcf-data-services.md)

- [Procedimiento para agregar opciones de consulta a una consulta de servicio de datos](how-to-add-query-options-to-a-data-service-query-wcf-data-services.md)

- [Procedimiento para determinar el número de entidades devueltas por una consulta](number-of-entities-returned-by-a-query-wcf.md)

- [Procedimiento para especificar las credenciales del cliente para una solicitud de servicio de datos](specify-client-creds-for-a-data-service-request-wcf.md)

- [Procedimiento para establecer encabezados en la solicitud de cliente](how-to-set-headers-in-the-client-request-wcf-data-services.md)

- [Procedimiento relativo a los resultados de la consulta del proyecto](how-to-project-query-results-wcf-data-services.md)

## <a name="see-also"></a>Consulte también

- [Biblioteca cliente de Data Services de WCF](wcf-data-services-client-library.md)
