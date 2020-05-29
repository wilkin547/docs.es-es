---
title: Operaciones de servicio de llamada (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1767f3a7-29d2-4834-a763-7d169693fa8b
ms.openlocfilehash: f1ff707c90e884dc66ab10563dc41ea7789f5cda
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202000"
---
# <a name="calling-service-operations-wcf-data-services"></a>Operaciones de servicio de llamada (WCF Data Services)
El Open Data Protocol (OData) define las operaciones de servicio para un servicio de datos. WCF Data Services permite definir operaciones como métodos en el servicio de datos. Las operaciones de servicio se direccionan como los demás recursos del servicio de datos, mediante los URI. Una operación de servicio puede devolver colecciones de tipos de entidad, instancias de tipo de entidad único y tipos primitivos, como entero y cadena. Una operación de servicio también puede devolver `null` (`Nothing` en Visual Basic). La biblioteca de cliente de WCF Data Services se puede utilizar para tener acceso a las operaciones de servicio que admiten solicitudes HTTP GET. Estas clases de operaciones de servicio se definen como métodos a los que se ha aplicado <xref:System.ServiceModel.Web.WebGetAttribute>. Para obtener más información, consulte [operaciones de servicio](service-operations-wcf-data-services.md).  
  
 Las operaciones de servicio se exponen en los metadatos devueltos por un servicio de datos que implementa OData. En los metadatos, las operaciones de servicio se representan como elementos `FunctionImport`. Al generar el fuertemente tipado <xref:System.Data.Services.Client.DataServiceContext> , las herramientas Agregar referencia de servicio y herramienta datasvcutil. exe omiten este elemento. Por esto, no encontrará un método en el contexto que se pueda usar para llamar directamente a una operación de servicio. Sin embargo, todavía puede usar el cliente de WCF Data Services para llamar a las operaciones de servicio de una de estas dos maneras:  
  
- Llamando al método <xref:System.Data.Services.Client.DataServiceContext.Execute%2A> en <xref:System.Data.Services.Client.DataServiceContext>, proporcionando el URI de la operación de servicio, junto con cualquier parámetro. Este método se usa para llamar a cualquier operación de servicio GET.  
  
- Usando el método <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A> en <xref:System.Data.Services.Client.DataServiceContext> para crear un objeto <xref:System.Data.Services.Client.DataServiceQuery%601>. Al llamar a <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A>, el nombre de la operación de servicio se proporciona al parámetro `entitySetName`. Este método devuelve un objeto <xref:System.Data.Services.Client.DataServiceQuery%601> que llama a la operación de servicio cuando se enumera o cuando se llama al método <xref:System.Data.Services.Client.DataServiceQuery%601.Execute%2A>. Este método se emplea para llamar a operaciones de servicio GET que devuelven una colección. Se puede proporcionar un parámetro único usando el método <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A>. El objeto <xref:System.Data.Services.Client.DataServiceQuery%601> devuelto por este método se puede componer más como cualquier objeto de consulta. Para obtener más información, consulte [consultar el servicio de datos](querying-the-data-service-wcf-data-services.md).  
  
## <a name="considerations-for-calling-service-operations"></a>Consideraciones para llamar a las operaciones de servicio  
 Las consideraciones siguientes se aplican cuando se usa el cliente de WCF Data Services para llamar a las operaciones de servicio.  
  
- Al tener acceso al servicio de datos de forma asincrónica, debe utilizar los métodos asincrónicos equivalentes <xref:System.Data.Services.Client.DataServiceContext.BeginExecute%2A> / <xref:System.Data.Services.Client.DataServiceContext.EndExecute%2A> en <xref:System.Data.Services.Client.DataServiceContext> o los <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> / <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> métodos de <xref:System.Data.Services.Client.DataServiceQuery%601> .  
  
- La biblioteca de cliente de WCF Data Services no puede materializar los resultados de una operación de servicio que devuelve una colección de tipos primitivos.  
  
- La biblioteca de cliente de WCF Data Services no admite la llamada a operaciones POST Service. Las operaciones de servicio a las que llama una solicitud HTTP POST se definen usando <xref:System.ServiceModel.Web.WebInvokeAttribute> con el parámetro `Method="POST"`. Para llamar a una operación de servicio usando una solicitud HTTP POST, debe usar <xref:System.Net.HttpWebRequest> en su lugar.  
  
- No puede usar <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A> para llamar a una operación de servicio GET que devuelve un único resultado, ya sea de tipo de entidad o de tipo primitivo, o que requiera más de un parámetro de entrada. Debe llamar en su lugar al método <xref:System.Data.Services.Client.DataServiceContext.Execute%2A>.  
  
- Considere la posibilidad de crear un método de extensión en la clase parcial fuertemente tipada <xref:System.Data.Services.Client.DataServiceContext> , generada por las herramientas de, que usa el <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A> <xref:System.Data.Services.Client.DataServiceContext.Execute%2A> método o para llamar a una operación de servicio. Esto le permite llamar directamente a operaciones de servicio desde el contexto. Para obtener más información, consulte la entrada de blog [operaciones de servicio y el cliente de WCF Data Services](https://docs.microsoft.com/archive/blogs/astoriateam/service-operations-and-the-wcf-data-services-client).  
  
- Cuando se usa <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A> para llamar a una operación de servicio, la biblioteca de cliente convierte automáticamente en caracteres de escape los caracteres proporcionados al <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> mediante la codificación porcentual de caracteres reservados, como la y comercial (&), y el escape de comillas simples en cadenas. Sin embargo, al llamar a uno de los métodos *Execute* para llamar a una operación de servicio, debe recordar realizar este escape de cualquier valor de cadena proporcionado por el usuario. Las comillas simples de los URI se pasan como pares de comillas simples.  
  
## <a name="examples-of-calling-service-operations"></a>Ejemplos de llamada a operaciones de servicio  
 Esta sección contiene los siguientes ejemplos de cómo llamar a las operaciones de servicio mediante la biblioteca de cliente de WCF Data Services:  
  
- [Llamar a Execute &lt; T &gt; para devolver una colección de entidades](calling-service-operations-wcf-data-services.md#ExecuteIQueryable)  
  
- [Usar CreateQuery &lt; T &gt; para devolver una colección de entidades](calling-service-operations-wcf-data-services.md#CreateQueryIQueryable)  
  
- [Llamar a Execute &lt; T &gt; para devolver una sola entidad](calling-service-operations-wcf-data-services.md#ExecuteSingleEntity)  
  
- [Llamar a Execute &lt; T &gt; para devolver una colección de valores primitivos](calling-service-operations-wcf-data-services.md#ExecutePrimitiveCollection)  
  
- [Llamar a Execute &lt; T &gt; para devolver un único valor primitivo](calling-service-operations-wcf-data-services.md#ExecutePrimitiveValue)  
  
- [Llamar una operación de servicio que no devuelve datos](calling-service-operations-wcf-data-services.md#ExecuteVoid)  
  
- [Llamar una operación de servicio de forma asincrónica](calling-service-operations-wcf-data-services.md#ExecuteAsync)  
  
<a name="ExecuteIQueryable"></a>
### <a name="calling-executet-to-return-a-collection-of-entities"></a>Llamar a Execute \<T> para devolver una colección de entidades  
 En el ejemplo siguiente se llama una operación de servicio denominada GetOrdersByCity, que toma un parámetro de cadena de `city` y devuelve <xref:System.Linq.IQueryable%601>:  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationIQueryable](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationiqueryable)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationIQueryable](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#callserviceoperationiqueryable)]  
  
 En este ejemplo, la operación de servicio devuelve una colección de objetos `Order` con objetos `Order_Detail` relacionados.  
  
<a name="CreateQueryIQueryable"></a>
### <a name="using-createqueryt-to-return-a-collection-of-entities"></a>Usar CreateQuery \<T> para devolver una colección de entidades  
 En el ejemplo siguiente se usa <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A> para devolver un <xref:System.Data.Services.Client.DataServiceQuery%601> que se emplea para llamar a la misma operación de servicio GetOrdersByCity:  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationCreateQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationcreatequery)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationCreateQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#callserviceoperationcreatequery)]  
  
 En este ejemplo, el método <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> se usa para agregar el parámetro a la consulta y el método <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> se usa para incluir objetos Order_Details relacionados en los resultados.  
  
<a name="ExecuteSingleEntity"></a>
### <a name="calling-executet-to-return-a-single-entity"></a>Llamar a Execute \<T> para devolver una sola entidad  
 En el ejemplo siguiente se llama a una operación de servicio denominada GetNewestOrder que solo devuelve una única entidad Order:  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationSingleEntity](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationsingleentity)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationSingleEntity](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#callserviceoperationsingleentity)]  
  
 En este ejemplo, el método <xref:System.Linq.Enumerable.FirstOrDefault%2A> se usa para solicitar solo una única entidad Order en la ejecución.  
  
<a name="ExecutePrimitiveCollection"></a>
### <a name="calling-executet-to-return-a-collection-of-primitive-values"></a>Llamar a Execute \<T> para devolver una colección de valores primitivos  
 En el ejemplo siguiente se llama a una operación de servicio que devuelve una colección de valores de cadena:  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationEnumString](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationenumstring)]  
  
<a name="ExecutePrimitiveValue"></a>
### <a name="calling-executet-to-return-a-single-primitive-value"></a>Llamar a Execute \<T> para devolver un único valor primitivo  
 En el ejemplo siguiente se llama a una operación de servicio que devuelve un único valor de cadena:  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationSingleInt](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationsingleint)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationSingleInt](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#callserviceoperationsingleint)]  
  
 De nuevo en este ejemplo, el método <xref:System.Linq.Enumerable.FirstOrDefault%2A> se emplea para solicitar solo un único valor entero en la ejecución.  
  
<a name="ExecuteVoid"></a>
### <a name="calling-a-service-operation-that-returns-no-data"></a>Llamar una operación de servicio que no devuelve datos  
 En el ejemplo siguiente se llama a una operación de servicio que no devuelve ningún dato:  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationVoid](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationvoid)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationVoid](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#callserviceoperationvoid)]  
  
 Como no se devuelven datos, no se asigna el valor de la ejecución. La única indicación de que la solicitud se ha realizado correctamente es que no se genera <xref:System.Data.Services.Client.DataServiceQueryException>.  
  
<a name="ExecuteAsync"></a>
### <a name="calling-a-service-operation-asynchronously"></a>Llamar una operación de servicio de forma asincrónica  
 En el ejemplo siguiente se llama de forma asincrónica a una operación de servicio llamando a <xref:System.Data.Services.Client.DataServiceContext.BeginExecute%2A> y <xref:System.Data.Services.Client.DataServiceContext.EndExecute%2A>:  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationasync)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#callserviceoperationasync)]  
  
 [!code-csharp[Astoria Northwind Client#OnAsyncExecutionComplete](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#onasyncexecutioncomplete)]
 [!code-vb[Astoria Northwind Client#OnAsyncExecutionComplete](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#onasyncexecutioncomplete)]  
  
 Como no se devuelven datos, no se asigna el valor devuelto por la ejecución. La única indicación de que la solicitud se ha realizado correctamente es que no se genera <xref:System.Data.Services.Client.DataServiceQueryException>.  
  
 En el ejemplo siguiente se llama de forma asincrónica a la misma operación de servicio mediante <xref:System.Data.Services.Client.DataServiceContext.CreateQuery%2A>:  
  
 [!code-csharp[Astoria Northwind Client#CallServiceOperationQueryAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#callserviceoperationqueryasync)]
 [!code-vb[Astoria Northwind Client#CallServiceOperationQueryAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#callserviceoperationqueryasync)]  
  
 [!code-csharp[Astoria Northwind Client#OnAsyncQueryExecutionComplete](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#onasyncqueryexecutioncomplete)]
 [!code-vb[Astoria Northwind Client#OnAsyncQueryExecutionComplete](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#onasyncqueryexecutioncomplete)]  
  
## <a name="see-also"></a>Consulta también

- [Biblioteca cliente de Data Services de WCF](wcf-data-services-client-library.md)
