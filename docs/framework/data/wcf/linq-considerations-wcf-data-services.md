---
description: 'Más información acerca de: consideraciones sobre LINQ (Servicios de datos de WCF)'
title: Consideraciones sobre LINQ (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, LINQ
- querying the data service [WCF Data Services]
- WCF Data Services, querying
ms.assetid: cc4ec9e9-348f-42a6-a78e-1cd40e370656
ms.openlocfilehash: 4205fc5c67c5939377e2a964d5a82d8855b03fce
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764970"
---
# <a name="linq-considerations-wcf-data-services"></a><span data-ttu-id="33ea6-103">Consideraciones sobre LINQ (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="33ea6-103">LINQ Considerations (WCF Data Services)</span></span>

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

<span data-ttu-id="33ea6-104">En este tema se proporciona información sobre la forma en que las consultas LINQ se componen y se ejecutan cuando se usa el cliente de Servicios de datos de WCF y las limitaciones del uso de LINQ para consultar un servicio de datos que implementa el Open Data Protocol (OData).</span><span class="sxs-lookup"><span data-stu-id="33ea6-104">This topic provides information about the way in which LINQ queries are composed and executed when you are using the WCF Data Services client and limitations of using LINQ to query a data service that implements the Open Data Protocol (OData).</span></span> <span data-ttu-id="33ea6-105">Para obtener más información acerca de la creación y ejecución de consultas en un servicio de datos basado en OData, consulte [consultar el servicio de datos](querying-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="33ea6-105">For more information about composing and executing queries against an OData-based data service, see [Querying the Data Service](querying-the-data-service-wcf-data-services.md).</span></span>  
  
## <a name="composing-linq-queries"></a><span data-ttu-id="33ea6-106">Redactar consultas LINQ</span><span class="sxs-lookup"><span data-stu-id="33ea6-106">Composing LINQ Queries</span></span>  

 <span data-ttu-id="33ea6-107">LINQ permite redactar consultas en una colección de objetos que implemente la interfaz <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="33ea6-107">LINQ enables you to compose queries against a collection of objects that implements <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="33ea6-108">Tanto el cuadro de diálogo **Agregar referencia de servicio** de Visual Studio como la herramienta de DataSvcUtil.exe se usan para generar una representación de un servicio de oData como una clase de contenedor de entidades que hereda de <xref:System.Data.Services.Client.DataServiceContext> , así como objetos que representan las entidades devueltas en las fuentes.</span><span class="sxs-lookup"><span data-stu-id="33ea6-108">Both the **Add Service Reference** dialog box in Visual Studio and the DataSvcUtil.exe tool are used to generate a representation of an OData service as an entity container class that inherits from <xref:System.Data.Services.Client.DataServiceContext>, as well as objects that represent the entities returned in feeds.</span></span> <span data-ttu-id="33ea6-109">Estas herramientas también generan propiedades en la clase de contenedor de entidades de las colecciones que el servicio exponen como fuentes.</span><span class="sxs-lookup"><span data-stu-id="33ea6-109">These tools also generate properties on the entity container class for the collections that are exposed as feeds by the service.</span></span> <span data-ttu-id="33ea6-110">Cada una de estas propiedades de la clase que encapsula el servicio de datos devuelve una clase <xref:System.Data.Services.Client.DataServiceQuery%601>.</span><span class="sxs-lookup"><span data-stu-id="33ea6-110">Each of these properties of the class that encapsulates the data service return a <xref:System.Data.Services.Client.DataServiceQuery%601>.</span></span> <span data-ttu-id="33ea6-111">Puesto que la clase <xref:System.Data.Services.Client.DataServiceQuery%601> implementa la interfaz <xref:System.Linq.IQueryable%601> definida por LINQ, puede crear una consulta LINQ en fuentes expuestas por el servicio de datos, que la biblioteca cliente traduce en un URI de solicitud de consulta que se envía al servicio de datos en la ejecución.</span><span class="sxs-lookup"><span data-stu-id="33ea6-111">Because the <xref:System.Data.Services.Client.DataServiceQuery%601> class implements the <xref:System.Linq.IQueryable%601> interface defined by LINQ, you can compose a LINQ query against feeds exposed by the data service, which are translated by the client library into a query request URI that is sent to the data service on execution.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="33ea6-112">El conjunto de consultas que se expresan en la sintaxis de LINQ es más amplio que los habilitados en la sintaxis de URI que usan los servicios de datos de OData.</span><span class="sxs-lookup"><span data-stu-id="33ea6-112">The set of queries expressible in the LINQ syntax is broader than those enabled in the URI syntax that is used by OData data services.</span></span> <span data-ttu-id="33ea6-113">Cuando la consulta no se puede asignar a ningún URI del servicio de datos de destino, se produce una excepción <xref:System.NotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="33ea6-113">A <xref:System.NotSupportedException> is raised when the query cannot be mapped to a URI in the target data service.</span></span> <span data-ttu-id="33ea6-114">Para obtener más información, vea los [métodos LINQ no admitidos](linq-considerations-wcf-data-services.md#unsupportedMethods) en este tema.</span><span class="sxs-lookup"><span data-stu-id="33ea6-114">For more information, see the [Unsupported LINQ Methods](linq-considerations-wcf-data-services.md#unsupportedMethods) in this topic.</span></span>  
  
 <span data-ttu-id="33ea6-115">El siguiente ejemplo es una consulta LINQ que devuelve `Orders` con un costo de flete de más de 30 $ y ordena los resultados por la fecha de envío, comenzando por la fecha de envío más reciente:</span><span class="sxs-lookup"><span data-stu-id="33ea6-115">The following example is a LINQ query that returns `Orders` that have a freight cost of more than $30 and sorts the results by the shipping date, starting with the latest ship date:</span></span>  
  
[!code-csharp[Astoria Northwind Client#AddQueryOptionsLinqSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addqueryoptionslinqspecific)]
[!code-vb[Astoria Northwind Client#AddQueryOptionsLinqSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addqueryoptionslinqspecific)]
  
 <span data-ttu-id="33ea6-116">Esta consulta LINQ se traduce en el siguiente URI de consulta que se ejecuta en el servicio de datos de [Inicio rápido](quickstart-wcf-data-services.md) basado en Northwind:</span><span class="sxs-lookup"><span data-stu-id="33ea6-116">This LINQ query is translated into the following query URI that is executed against the Northwind-based [quickstart](quickstart-wcf-data-services.md) data service:</span></span>  
  
```http
http://localhost:12345/Northwind.svc/Orders?Orderby=ShippedDate&?filter=Freight gt 30  
```  
  
 <span data-ttu-id="33ea6-117">Para obtener más información general sobre LINQ, consulte [Language-Integrated Query (LINQ)-C#](../../../csharp/programming-guide/concepts/linq/index.md) o [Language-Integrated Query (linq)-Visual Basic](../../../visual-basic/programming-guide/concepts/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="33ea6-117">For more general information about LINQ, see [Language-Integrated Query (LINQ) - C#](../../../csharp/programming-guide/concepts/linq/index.md) or [Language-Integrated Query (LINQ) - Visual Basic](../../../visual-basic/programming-guide/concepts/linq/index.md).</span></span>  
  
 <span data-ttu-id="33ea6-118">LINQ permite redactar consultas mediante el uso tanto de la sintaxis de consulta declarativa específica del lenguaje, mostrada en el ejemplo anterior, como de un conjunto de métodos de consulta denominados operadores de consulta estándar.</span><span class="sxs-lookup"><span data-stu-id="33ea6-118">LINQ enables you to compose queries by using both the language-specific declarative query syntax, shown in the previous example, as well as a set of query methods known as standard query operators.</span></span> <span data-ttu-id="33ea6-119">Una consulta equivalente al ejemplo anterior se puede redactar mediante el uso de la sintaxis basada en métodos únicamente, como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="33ea6-119">An equivalent query to the previous example can be composed by using only the method-based syntax, as shown the following example:</span></span>  
  
[!code-csharp[Astoria Northwind Client#AddQueryOptionsLinqExpressionSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addqueryoptionslinqexpressionspecific)]
[!code-vb[Astoria Northwind Client#AddQueryOptionsLinqExpressionSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addqueryoptionslinqexpressionspecific)]
  
 <span data-ttu-id="33ea6-120">El cliente Servicios de datos de WCF es capaz de traducir ambos tipos de consultas compuestas en un URI de consulta, y puede extender una consulta LINQ anexando métodos de consulta a una expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="33ea6-120">The WCF Data Services client is able to translate both kinds of composed queries into a query URI, and you can extend a LINQ query by appending query methods to a query expression.</span></span> <span data-ttu-id="33ea6-121">Cuando redacte consultas LINQ anexando la sintaxis del método a una expresión de consulta o a una clase <xref:System.Data.Services.Client.DataServiceQuery%601>, las operaciones se agregan al URI de la consulta en el orden en el que se llama a los métodos.</span><span class="sxs-lookup"><span data-stu-id="33ea6-121">When you compose LINQ queries by appending method syntax to a query expression or a <xref:System.Data.Services.Client.DataServiceQuery%601>, the operations are added to the query URI in the order in which methods are called.</span></span> <span data-ttu-id="33ea6-122">Esto es equivalente a llamar al método <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> para agregar cada opción de consulta al URI de la consulta.</span><span class="sxs-lookup"><span data-stu-id="33ea6-122">This is equivalent to calling the <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> method to add each query option to the query URI.</span></span>  
  
## <a name="executing-linq-queries"></a><span data-ttu-id="33ea6-123">Ejecutar consultas LINQ</span><span class="sxs-lookup"><span data-stu-id="33ea6-123">Executing LINQ Queries</span></span>  

 <span data-ttu-id="33ea6-124">Ciertos métodos de consulta LINQ, como los métodos <xref:System.Linq.Enumerable.First%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29> o <xref:System.Linq.Enumerable.Single%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29>, cuando se anexan a la consulta, provocan la ejecución de esta.</span><span class="sxs-lookup"><span data-stu-id="33ea6-124">Certain LINQ query methods, such as <xref:System.Linq.Enumerable.First%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29> or <xref:System.Linq.Enumerable.Single%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29>, when appended to the query, cause the query to be executed.</span></span> <span data-ttu-id="33ea6-125">También se ejecuta una consult6a cuando los resultados se enumeran implícitamente, como durante un bucle `foreach` o cuando la consulta se asigna a una colección `List`.</span><span class="sxs-lookup"><span data-stu-id="33ea6-125">A query is also executed when results are enumerated implicitly, such as during a `foreach` loop or when the query is assigned to a `List` collection.</span></span> <span data-ttu-id="33ea6-126">Para obtener más información, consulte [consultar el servicio de datos](querying-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="33ea6-126">For more information, see [Querying the Data Service](querying-the-data-service-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="33ea6-127">El cliente ejecuta una consulta LINQ en dos partes.</span><span class="sxs-lookup"><span data-stu-id="33ea6-127">The client executes a LINQ query in two parts.</span></span> <span data-ttu-id="33ea6-128">Siempre que sea posible, las expresiones LINQ de una consulta primero se evalúan en el cliente y, a continuación, se generan y se envían al servicio de datos para su evaluación en los datos del servicio.</span><span class="sxs-lookup"><span data-stu-id="33ea6-128">Whenever possible, LINQ expressions in a query are first evaluated on the client, and then a URI-based query is generated and sent to the data service for evaluation against data in the service.</span></span> <span data-ttu-id="33ea6-129">Para obtener más información, vea la sección [cliente frente a ejecución del servidor](querying-the-data-service-wcf-data-services.md#executingQueries) [al consultar el servicio de datos](querying-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="33ea6-129">For more information, see the section [Client versus Server Execution](querying-the-data-service-wcf-data-services.md#executingQueries) in [Querying the Data Service](querying-the-data-service-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="33ea6-130">Cuando una consulta LINQ no se puede traducir en un URI de consulta compatible con OData, se produce una excepción cuando se intenta la ejecución.</span><span class="sxs-lookup"><span data-stu-id="33ea6-130">When a LINQ query cannot be translated in an OData-compliant query URI, an exception is raised when execution is attempted.</span></span> <span data-ttu-id="33ea6-131">Para obtener más información, consulte [consultar el servicio de datos](querying-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="33ea6-131">For more information, see [Querying the Data Service](querying-the-data-service-wcf-data-services.md).</span></span>  
  
## <a name="linq-query-examples"></a><span data-ttu-id="33ea6-132">Ejemplos de consultas LINQ</span><span class="sxs-lookup"><span data-stu-id="33ea6-132">LINQ Query Examples</span></span>  

 <span data-ttu-id="33ea6-133">En los ejemplos de las secciones siguientes se muestran los tipos de consultas LINQ que se pueden ejecutar en un servicio de OData.</span><span class="sxs-lookup"><span data-stu-id="33ea6-133">The examples in the following sections demonstrate the kinds of LINQ queries that can be executed against an OData service.</span></span>  
  
<a name="filtering"></a>

### <a name="filtering"></a><span data-ttu-id="33ea6-134">Filtrado</span><span class="sxs-lookup"><span data-stu-id="33ea6-134">Filtering</span></span>  

 <span data-ttu-id="33ea6-135">Los ejemplos de consultas LINQ de esta sección filtran los datos de la fuente devuelta por el servicio.</span><span class="sxs-lookup"><span data-stu-id="33ea6-135">The LINQ query examples in this section filter data in the feed returned by the service.</span></span>  
  
 <span data-ttu-id="33ea6-136">Los siguientes ejemplos son consultas equivalentes que filtran las entidades `Orders` devueltas para que solo se devuelvan los pedidos con un costo de flete mayor que 30 $:</span><span class="sxs-lookup"><span data-stu-id="33ea6-136">The following examples are equivalent queries that filter the returned `Orders` entities so that only orders with a freight cost greater than $30 are returned:</span></span>  
  
- <span data-ttu-id="33ea6-137">Usar sintaxis de consulta LINQ:</span><span class="sxs-lookup"><span data-stu-id="33ea6-137">Using LINQ query syntax:</span></span>  
  
[!code-csharp[Astoria Northwind Client#LinqWhereClauseSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqwhereclausespecific)]
[!code-vb[Astoria Northwind Client#LinqWhereClauseSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqwhereclausespecific)]
  
- <span data-ttu-id="33ea6-138">Usar métodos de consulta LINQ:</span><span class="sxs-lookup"><span data-stu-id="33ea6-138">Using LINQ query methods:</span></span>  
  
[!code-csharp[Astoria Northwind Client#LinqWhereMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqwheremethodspecific)]
[!code-vb[Astoria Northwind Client#LinqWhereMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqwheremethodspecific)]
  
- <span data-ttu-id="33ea6-139">La opción `$filter` de la cadena de consulta del URI:</span><span class="sxs-lookup"><span data-stu-id="33ea6-139">The URI query string `$filter` option:</span></span>  
  
[!code-csharp[Astoria Northwind Client#ExplicitQueryWhereMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#explicitquerywheremethodspecific)]
[!code-vb[Astoria Northwind Client#ExplicitQueryWhereMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#explicitquerywheremethodspecific)]
  
 <span data-ttu-id="33ea6-140">Todos los ejemplos anteriores se traducen en el URI de consulta: `http://localhost:12345/northwind.svc/Orders()?$filter=Freight gt 30M`.</span><span class="sxs-lookup"><span data-stu-id="33ea6-140">All of the previous examples are translated to the query URI: `http://localhost:12345/northwind.svc/Orders()?$filter=Freight gt 30M`.</span></span>  
  
<a name="sorting"></a>

### <a name="sorting"></a><span data-ttu-id="33ea6-141">Ordenación</span><span class="sxs-lookup"><span data-stu-id="33ea6-141">Sorting</span></span>  

 <span data-ttu-id="33ea6-142">Los siguientes ejemplos muestran consultas equivalentes que ordenan ascendentemente los datos tanto por nombre de compañía como por código postal:</span><span class="sxs-lookup"><span data-stu-id="33ea6-142">The following examples show equivalent queries that sort returned data both by the company name and by postal code, descending:</span></span>  
  
- <span data-ttu-id="33ea6-143">Usar sintaxis de consulta LINQ:</span><span class="sxs-lookup"><span data-stu-id="33ea6-143">Using LINQ query syntax:</span></span>  
  
[!code-csharp[Astoria Northwind Client#LinqOrderByClauseSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqorderbyclausespecific)]
[!code-vb[Astoria Northwind Client#LinqOrderByClauseSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqorderbyclausespecific)]
  
- <span data-ttu-id="33ea6-144">Usar métodos de consulta LINQ:</span><span class="sxs-lookup"><span data-stu-id="33ea6-144">Using LINQ query methods:</span></span>  
  
[!code-csharp[Astoria Northwind Client#LinqOrderByMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqorderbymethodspecific)]
[!code-vb[Astoria Northwind Client#LinqOrderByMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqorderbymethodspecific)]
  
- <span data-ttu-id="33ea6-145">Opción `$orderby` de la cadena de consulta del URI):</span><span class="sxs-lookup"><span data-stu-id="33ea6-145">URI query string `$orderby` option):</span></span>  
  
[!code-csharp[Astoria Northwind Client#ExplicitQueryOrderByMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#explicitqueryorderbymethodspecific)]
[!code-vb[Astoria Northwind Client#ExplicitQueryOrderByMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#explicitqueryorderbymethodspecific)]
  
 <span data-ttu-id="33ea6-146">Todos los ejemplos anteriores se traducen en el URI de consulta: `http://localhost:12345/northwind.svc/Customers()?$orderby=CompanyName,PostalCode desc`.</span><span class="sxs-lookup"><span data-stu-id="33ea6-146">All of the previous examples are translated to the query URI: `http://localhost:12345/northwind.svc/Customers()?$orderby=CompanyName,PostalCode desc`.</span></span>  
  
<a name="projection"></a>

### <a name="projection"></a><span data-ttu-id="33ea6-147">Proyección</span><span class="sxs-lookup"><span data-stu-id="33ea6-147">Projection</span></span>  

 <span data-ttu-id="33ea6-148">Los siguientes ejemplos muestran las consultas equivalentes que proyectan los datos devueltos en el tipo `CustomerAddress` más restringido:</span><span class="sxs-lookup"><span data-stu-id="33ea6-148">The following examples show equivalent queries that project returned data into the narrower `CustomerAddress` type:</span></span>  
  
- <span data-ttu-id="33ea6-149">Usar sintaxis de consulta LINQ:</span><span class="sxs-lookup"><span data-stu-id="33ea6-149">Using LINQ query syntax:</span></span>  
  
[!code-csharp[Astoria Northwind Client#LinqSelectClauseSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqselectclausespecific)]
[!code-vb[Astoria Northwind Client#LinqSelectClauseSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqselectclausespecific)]
  
- <span data-ttu-id="33ea6-150">Usar métodos de consulta LINQ:</span><span class="sxs-lookup"><span data-stu-id="33ea6-150">Using LINQ query methods:</span></span>  
  
[!code-csharp[Astoria Northwind Client#LinqSelectMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqselectmethodspecific)]
[!code-vb[Astoria Northwind Client#LinqSelectMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqselectmethodspecific)]

> [!NOTE]
> <span data-ttu-id="33ea6-151">La opción de consulta `$select` no se puede agregar a ningún URI de la consulta mediante el uso del método <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A>.</span><span class="sxs-lookup"><span data-stu-id="33ea6-151">The `$select` query option cannot be added to a query URI by using the <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> method.</span></span> <span data-ttu-id="33ea6-152">Se recomienda usar el método <xref:System.Linq.Enumerable.Select%2A> de LINQ para que el cliente genere la opción de consulta `$select` en el URI de solicitud.</span><span class="sxs-lookup"><span data-stu-id="33ea6-152">We recommend that you use the LINQ <xref:System.Linq.Enumerable.Select%2A> method to have the client generate the `$select` query option in the request URI.</span></span>  
  
 <span data-ttu-id="33ea6-153">Los dos ejemplos anteriores se traducen en el URI de la consulta: `"http://localhost:12345/northwind.svc/Customers()?$filter=Country eq 'GerGerm'&$select=CustomerID,Address,City,Region,PostalCode,Country"`.</span><span class="sxs-lookup"><span data-stu-id="33ea6-153">Both of the previous examples are translated to the query URI: `"http://localhost:12345/northwind.svc/Customers()?$filter=Country eq 'GerGerm'&$select=CustomerID,Address,City,Region,PostalCode,Country"`.</span></span>  
  
<a name="paging"></a>

### <a name="client-paging"></a><span data-ttu-id="33ea6-154">Paginación del cliente</span><span class="sxs-lookup"><span data-stu-id="33ea6-154">Client Paging</span></span>  

 <span data-ttu-id="33ea6-155">En los siguientes ejemplos se muestran las consultas equivalentes que solicita una página de las entidades de pedidos ordenados que incluye 25 pedidos, omitiendo los 50 primeros pedidos:</span><span class="sxs-lookup"><span data-stu-id="33ea6-155">The following examples show equivalent queries that request a page of sorted order entities that includes 25 orders, skipping the first 50 orders:</span></span>  
  
- <span data-ttu-id="33ea6-156">Aplicar métodos de consulta a una consulta LINQ:</span><span class="sxs-lookup"><span data-stu-id="33ea6-156">Applying query methods to a LINQ query:</span></span>  
  
[!code-csharp[Astoria Northwind Client#LinqSkipTakeMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqskiptakemethodspecific)]
[!code-vb[Astoria Northwind Client#LinqSkipTakeMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqskiptakemethodspecific)]
  
- <span data-ttu-id="33ea6-157">opciones `$skip` y `$top` de cadena de consulta de URI):</span><span class="sxs-lookup"><span data-stu-id="33ea6-157">URI query string `$skip` and `$top` options):</span></span>  
  
[!code-csharp[Astoria Northwind Client#ExplicitQuerySkipTakeMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#explicitqueryskiptakemethodspecific)]
[!code-vb[Astoria Northwind Client#ExplicitQuerySkipTakeMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#explicitqueryskiptakemethodspecific)]
  
 <span data-ttu-id="33ea6-158">Los dos ejemplos anteriores se traducen en el URI de la consulta: `http://localhost:12345/northwind.svc/Orders()?$orderby=OrderDate desc&$skip=50&$top=25`.</span><span class="sxs-lookup"><span data-stu-id="33ea6-158">Both of the previous examples are translated to the query URI: `http://localhost:12345/northwind.svc/Orders()?$orderby=OrderDate desc&$skip=50&$top=25`.</span></span>  
  
<a name="expand"></a>

### <a name="expand"></a><span data-ttu-id="33ea6-159">Expanda</span><span class="sxs-lookup"><span data-stu-id="33ea6-159">Expand</span></span>  

 <span data-ttu-id="33ea6-160">Al consultar un servicio de datos de OData, puede solicitar que las entidades relacionadas con la entidad de destino de la consulta se incluyan en la fuente devuelta.</span><span class="sxs-lookup"><span data-stu-id="33ea6-160">When you query an OData data service, you can request that entities related to the entity targeted by the query be included the returned feed.</span></span> <span data-ttu-id="33ea6-161">Se llama al método <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> en la clase <xref:System.Data.Services.Client.DataServiceQuery%601> para el conjunto de entidades que sean el destino de la consulta LINQ, con el nombre del conjunto de entidades relacionado proporcionado como el parámetro `path`.</span><span class="sxs-lookup"><span data-stu-id="33ea6-161">The <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> method is called on the <xref:System.Data.Services.Client.DataServiceQuery%601> for the entity set targeted by the LINQ query, with the related entity set name supplied as the `path` parameter.</span></span> <span data-ttu-id="33ea6-162">Para obtener más información, vea [cargar contenido diferido](loading-deferred-content-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="33ea6-162">For more information, see [Loading Deferred Content](loading-deferred-content-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="33ea6-163">En los siguientes ejemplos se muestran las formas equivalentes de usar el método <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> en una consulta:</span><span class="sxs-lookup"><span data-stu-id="33ea6-163">The following examples show equivalent ways to use the <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> method in a query:</span></span>  
  
- <span data-ttu-id="33ea6-164">En la sintaxis de las consultas LINQ:</span><span class="sxs-lookup"><span data-stu-id="33ea6-164">In LINQ query syntax:</span></span>  
  
[!code-csharp[Astoria Northwind Client#LinqQueryExpandSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqqueryexpandspecific)]
[!code-vb[Astoria Northwind Client#LinqQueryExpandSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqqueryexpandspecific)]  
  
- <span data-ttu-id="33ea6-165">Con los métodos de consulta LINQ:</span><span class="sxs-lookup"><span data-stu-id="33ea6-165">With LINQ query methods:</span></span>  

[!code-csharp[Astoria Northwind Client#LinqQueryExpandMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqqueryexpandmethodspecific)]
[!code-vb[Astoria Northwind Client#LinqQueryExpandMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqqueryexpandmethodspecific)]

 <span data-ttu-id="33ea6-166">Los dos ejemplos anteriores se traducen en el URI de la consulta: `http://localhost:12345/northwind.svc/Orders()?$filter=CustomerID eq 'ALFKI'&$expand=Order_Details`.</span><span class="sxs-lookup"><span data-stu-id="33ea6-166">Both of the previous examples are translated to the query URI: `http://localhost:12345/northwind.svc/Orders()?$filter=CustomerID eq 'ALFKI'&$expand=Order_Details`.</span></span>  
  
<a name="unsupportedMethods"></a>

## <a name="unsupported-linq-methods"></a><span data-ttu-id="33ea6-167">Métodos LINQ no admitidos</span><span class="sxs-lookup"><span data-stu-id="33ea6-167">Unsupported LINQ Methods</span></span>  

 <span data-ttu-id="33ea6-168">La tabla siguiente contiene las clases de los métodos de LINQ no se admiten y no se pueden incluir en una consulta ejecutada en un servicio de OData:</span><span class="sxs-lookup"><span data-stu-id="33ea6-168">The following table contains the classes of LINQ methods are not supported and cannot be included in a query executed against an OData service:</span></span>  
  
|<span data-ttu-id="33ea6-169">Tipo de operación</span><span class="sxs-lookup"><span data-stu-id="33ea6-169">Operation Type</span></span>|<span data-ttu-id="33ea6-170">Método no admitido</span><span class="sxs-lookup"><span data-stu-id="33ea6-170">Unsupported Method</span></span>|  
|--------------------|------------------------|  
|<span data-ttu-id="33ea6-171">Operadores de conjuntos</span><span class="sxs-lookup"><span data-stu-id="33ea6-171">Set operators</span></span>|<span data-ttu-id="33ea6-172">No se admite ningún operador de conjuntos en una clase <xref:System.Data.Services.Client.DataServiceQuery%601>, que incluya lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="33ea6-172">All set operators are unsupported against a <xref:System.Data.Services.Client.DataServiceQuery%601>, which included the following:</span></span><br /><br /> -   <xref:System.Linq.Enumerable.All%2A><br />-   <xref:System.Linq.Enumerable.Any%2A><br />-   <xref:System.Linq.Enumerable.Concat%2A><br />-   <xref:System.Linq.Enumerable.DefaultIfEmpty%2A><br />-   <xref:System.Linq.Enumerable.Distinct%2A><br />-   <xref:System.Linq.Enumerable.Except%2A><br />-   <xref:System.Linq.Enumerable.Intersect%2A><br />-   <xref:System.Linq.Enumerable.Union%2A><br />-   <xref:System.Linq.Enumerable.Zip%2A>|  
|<span data-ttu-id="33ea6-173">Operaciones de ordenación</span><span class="sxs-lookup"><span data-stu-id="33ea6-173">Ordering operators</span></span>|<span data-ttu-id="33ea6-174">No se admiten los siguientes operadores de ordenación que requieran la interfaz <xref:System.Collections.Generic.IComparer%601> en una clase <xref:System.Data.Services.Client.DataServiceQuery%601>:</span><span class="sxs-lookup"><span data-stu-id="33ea6-174">The following ordering operators that require <xref:System.Collections.Generic.IComparer%601> are unsupported against a <xref:System.Data.Services.Client.DataServiceQuery%601>:</span></span><br /><br /> -   <xref:System.Linq.Enumerable.OrderBy%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.OrderByDescending%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.ThenBy%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.ThenByDescending%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29>|  
|<span data-ttu-id="33ea6-175">Métodos de proyección y filtrado</span><span class="sxs-lookup"><span data-stu-id="33ea6-175">Projection and filtering operators</span></span>|<span data-ttu-id="33ea6-176">No se admiten ninguno de los siguientes operadores de proyección y filtrado que acepten un argumento posicional en una clase <xref:System.Data.Services.Client.DataServiceQuery%601>:</span><span class="sxs-lookup"><span data-stu-id="33ea6-176">The following projection and filtering operators that accept a positional argument are unsupported against a <xref:System.Data.Services.Client.DataServiceQuery%601>:</span></span><br /><br /> -   <xref:System.Linq.Enumerable.Join%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D%2CSystem.Collections.Generic.IEqualityComparer%7B%60%602%7D%29><br />-   <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2C%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%603%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%602%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%603%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%602%7D%29><br />-   <xref:System.Linq.Enumerable.Where%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2CSystem.Boolean%7D%29>|  
|<span data-ttu-id="33ea6-177">Operadores de agrupación</span><span class="sxs-lookup"><span data-stu-id="33ea6-177">Grouping operators</span></span>|<span data-ttu-id="33ea6-178">No se admite ningún operador de agrupación en una clase <xref:System.Data.Services.Client.DataServiceQuery%601>, que incluya lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="33ea6-178">All grouping operators are unsupported against a <xref:System.Data.Services.Client.DataServiceQuery%601>, including the following:</span></span><br /><br /> -   <xref:System.Linq.Enumerable.GroupBy%2A><br />-   <xref:System.Linq.Enumerable.GroupJoin%2A><br /><br /> <span data-ttu-id="33ea6-179">Los operadores de agrupación se deben ejecutar en el cliente.</span><span class="sxs-lookup"><span data-stu-id="33ea6-179">Grouping operations must be performed on the client.</span></span>|  
|<span data-ttu-id="33ea6-180">Operadores de agregación</span><span class="sxs-lookup"><span data-stu-id="33ea6-180">Aggregate operators</span></span>|<span data-ttu-id="33ea6-181">No se admite ninguna operación de agregado en una clase <xref:System.Data.Services.Client.DataServiceQuery%601>, que incluya lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="33ea6-181">All aggregate operations are unsupported against a <xref:System.Data.Services.Client.DataServiceQuery%601>, including the following:</span></span><br /><br /> -   <xref:System.Linq.Enumerable.Aggregate%2A><br />-   <xref:System.Linq.Enumerable.Average%2A><br />-   <xref:System.Linq.Enumerable.Count%2A><br />-   <xref:System.Linq.Enumerable.LongCount%2A><br />-   <xref:System.Linq.Enumerable.Max%2A><br />-   <xref:System.Linq.Enumerable.Min%2A><br />-   <xref:System.Linq.Enumerable.Sum%2A><br /><br /> <span data-ttu-id="33ea6-182">Las operaciones de agregado se deben ejecutar en el cliente o las debe encapsular una operación de servicio.</span><span class="sxs-lookup"><span data-stu-id="33ea6-182">Aggregate operations must either be performed on the client or be encapsulated by a service operation.</span></span>|  
|<span data-ttu-id="33ea6-183">Operadores de paginación</span><span class="sxs-lookup"><span data-stu-id="33ea6-183">Paging operators</span></span>|<span data-ttu-id="33ea6-184">No se admiten los siguientes operadores de paginación en una clase <xref:System.Data.Services.Client.DataServiceQuery%601>:</span><span class="sxs-lookup"><span data-stu-id="33ea6-184">The following paging operators are not supported against a <xref:System.Data.Services.Client.DataServiceQuery%601>:</span></span><br /><br /> -   <xref:System.Linq.Enumerable.ElementAt%2A><br />-   <xref:System.Linq.Enumerable.Last%2A><br />-   <xref:System.Linq.Enumerable.LastOrDefault%2A><br />-   <xref:System.Linq.Enumerable.SkipWhile%2A><br />-   <xref:System.Linq.Enumerable.TakeWhile%2A><br/><br/><span data-ttu-id="33ea6-185">**Nota:**  Los operadores de paginación que se ejecutan en una secuencia vacía devuelven null.</span><span class="sxs-lookup"><span data-stu-id="33ea6-185">**Note:**  Paging operators that are executed on an empty sequence return null.</span></span>|  
|<span data-ttu-id="33ea6-186">Otros operadores</span><span class="sxs-lookup"><span data-stu-id="33ea6-186">Other operators</span></span>|<span data-ttu-id="33ea6-187">Los operadores siguientes tampoco se admiten en <xref:System.Data.Services.Client.DataServiceQuery%601> :</span><span class="sxs-lookup"><span data-stu-id="33ea6-187">The following operators are also not supported against a <xref:System.Data.Services.Client.DataServiceQuery%601>:</span></span><br /><br /> - <xref:System.Linq.Enumerable.Empty%2A><br />- <xref:System.Linq.Enumerable.Range%2A><br />- <xref:System.Linq.Enumerable.Repeat%2A><br />- <xref:System.Linq.Enumerable.ToDictionary%2A><br />- <xref:System.Linq.Enumerable.ToLookup%2A>|  
  
<a name="supportedExpressions"></a>

## <a name="supported-expression-functions"></a><span data-ttu-id="33ea6-188">Funciones de expresión admitidas</span><span class="sxs-lookup"><span data-stu-id="33ea6-188">Supported Expression Functions</span></span>  

 <span data-ttu-id="33ea6-189">Se admiten los siguientes métodos y propiedades de Common Language Runtime (CLR) porque se pueden traducir en una expresión de consulta para su inclusión en el URI de solicitud en un servicio de OData:</span><span class="sxs-lookup"><span data-stu-id="33ea6-189">The following common-language runtime (CLR) methods and properties are supported because they can be translated in a query expression for inclusion in the request URI to an OData service:</span></span>  
  
|<span data-ttu-id="33ea6-190">Miembro de <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="33ea6-190"><xref:System.String> Member</span></span>|<span data-ttu-id="33ea6-191">Función de OData admitida</span><span class="sxs-lookup"><span data-stu-id="33ea6-191">Supported OData Function</span></span>|  
|-----------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.String.Concat%28System.String%2CSystem.String%29>|`string concat(string p0, string p1)`|  
|<xref:System.String.Contains%28System.String%29>|`bool substringof(string p0, string p1)`|  
|<xref:System.String.EndsWith%28System.String%29>|`bool endswith(string p0, string p1)`|  
|<xref:System.String.IndexOf%28System.String%2CSystem.Int32%29>|`int indexof(string p0, string p1)`|  
|<xref:System.String.Length>|`int length(string p0)`|  
|<xref:System.String.Replace%28System.String%2CSystem.String%29>|`string replace(string p0, string find, string replace)`|  
|<xref:System.String.Substring%28System.Int32%29>|`string substring(string p0, int pos)`|  
|<xref:System.String.Substring%28System.Int32%2CSystem.Int32%29>|`string substring(string p0, int pos, int length)`|  
|<xref:System.String.ToLower>|`string tolower(string p0)`|  
|<xref:System.String.ToUpper>|`string toupper(string p0)`|  
|<xref:System.String.Trim>|`string trim(string p0)`|  
  
|<span data-ttu-id="33ea6-192"><xref:System.DateTime> Miembro<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="33ea6-192"><xref:System.DateTime> Member<sup>1</sup></span></span>|<span data-ttu-id="33ea6-193">Función de OData admitida</span><span class="sxs-lookup"><span data-stu-id="33ea6-193">Supported OData Function</span></span>|  
|-------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.DateTime.Day>|`int day(DateTime p0)`|  
|<xref:System.DateTime.Hour>|`int hour(DateTime p0)`|  
|<xref:System.DateTime.Minute>|`int minute(DateTime p0)`|  
|<xref:System.DateTime.Month>|`int month(DateTime p0)`|  
|<xref:System.DateTime.Second>|`int second(DateTime p0)`|  
|<xref:System.DateTime.Year>|`int year(DateTime p0)`|  
  
 <span data-ttu-id="33ea6-194"><sup>1</sup> También se admiten las propiedades de fecha y hora equivalentes de <xref:Microsoft.VisualBasic.DateAndTime?displayProperty=nameWithType> y el <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> método de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="33ea6-194"><sup>1</sup>The equivalent date and time properties of <xref:Microsoft.VisualBasic.DateAndTime?displayProperty=nameWithType> and the <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> method in Visual Basic are also supported.</span></span>  
  
|<span data-ttu-id="33ea6-195">Miembro de <xref:System.Math></span><span class="sxs-lookup"><span data-stu-id="33ea6-195"><xref:System.Math> Member</span></span>|<span data-ttu-id="33ea6-196">Función de OData admitida</span><span class="sxs-lookup"><span data-stu-id="33ea6-196">Supported OData Function</span></span>|  
|---------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.Math.Ceiling%28System.Decimal%29>|`decimal ceiling(decimal p0)`|  
|<xref:System.Math.Ceiling%28System.Double%29>|`double ceiling(double p0)`|  
|<xref:System.Math.Floor%28System.Decimal%29>|`decimal floor(decimal p0)`|  
|<xref:System.Math.Floor%28System.Double%29>|`double floor(double p0)`|  
|<xref:System.Math.Round%28System.Decimal%29>|`decimal round(decimal p0)`|  
|<xref:System.Math.Round%28System.Double%29>|`double round(double p0)`|  
  
|<span data-ttu-id="33ea6-197">Miembro de <xref:System.Linq.Expressions.Expression></span><span class="sxs-lookup"><span data-stu-id="33ea6-197"><xref:System.Linq.Expressions.Expression> Member</span></span>|<span data-ttu-id="33ea6-198">Función de OData admitida</span><span class="sxs-lookup"><span data-stu-id="33ea6-198">Supported OData Function</span></span>|  
|---------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.Linq.Expressions.Expression.TypeIs%28System.Linq.Expressions.Expression%2CSystem.Type%29>|`bool isof(type p0)`|  
  
 <span data-ttu-id="33ea6-199">Además, el cliente quizá pueda evaluar las funciones CLR adicionales en el cliente.</span><span class="sxs-lookup"><span data-stu-id="33ea6-199">The client may also be able to evaluate additional CLR functions on the client.</span></span> <span data-ttu-id="33ea6-200">Se produce una excepción <xref:System.NotSupportedException> para cualquier expresión que no se pueda evaluar en el cliente y que no se pueda traducir en un URI de solicitud válido para su evaluación en el servidor.</span><span class="sxs-lookup"><span data-stu-id="33ea6-200">A <xref:System.NotSupportedException> is raised for any expression that cannot be evaluated on the client and cannot be translated into a valid request URI for evaluation on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33ea6-201">Vea también</span><span class="sxs-lookup"><span data-stu-id="33ea6-201">See also</span></span>

- [<span data-ttu-id="33ea6-202">Consultar el servicio de datos</span><span class="sxs-lookup"><span data-stu-id="33ea6-202">Querying the Data Service</span></span>](querying-the-data-service-wcf-data-services.md)
- [<span data-ttu-id="33ea6-203">Proyecciones de consultas</span><span class="sxs-lookup"><span data-stu-id="33ea6-203">Query Projections</span></span>](query-projections-wcf-data-services.md)
- [<span data-ttu-id="33ea6-204">Materialización de objetos</span><span class="sxs-lookup"><span data-stu-id="33ea6-204">Object Materialization</span></span>](object-materialization-wcf-data-services.md)
- [<span data-ttu-id="33ea6-205">OData: convenciones de URI</span><span class="sxs-lookup"><span data-stu-id="33ea6-205">OData: URI Conventions</span></span>](https://www.odata.org/documentation/odata-version-2-0/uri-conventions/)
