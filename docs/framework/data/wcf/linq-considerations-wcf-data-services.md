---
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
ms.openlocfilehash: f8ec53323abec7077c69f50fe522338228ceddbb
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116635"
---
# <a name="linq-considerations-wcf-data-services"></a>Consideraciones sobre LINQ (WCF Data Services)
En este tema se proporciona información sobre la forma en que las consultas LINQ se componen y se ejecutan cuando se usa el cliente de WCF Data Services y las limitaciones del uso de LINQ para consultar un servicio de datos que implementa el Open Data Protocol (OData). Para obtener más información acerca de la creación y ejecución de consultas en un servicio de datos basado en OData, consulte [consultar el servicio de datos](querying-the-data-service-wcf-data-services.md).  
  
## <a name="composing-linq-queries"></a>Redactar consultas LINQ  
 LINQ permite redactar consultas en una colección de objetos que implemente la interfaz <xref:System.Collections.Generic.IEnumerable%601>. Tanto el cuadro de diálogo **Agregar referencia de servicio** de Visual Studio como la herramienta herramienta datasvcutil. exe se usan para generar una representación de un servicio de oData como una clase de contenedor de entidades que hereda de <xref:System.Data.Services.Client.DataServiceContext>, así como objetos que representan las entidades devueltas en las fuentes. Estas herramientas también generan propiedades en la clase de contenedor de entidades de las colecciones que el servicio exponen como fuentes. Cada una de estas propiedades de la clase que encapsula el servicio de datos devuelve una clase <xref:System.Data.Services.Client.DataServiceQuery%601>. Puesto que la clase <xref:System.Data.Services.Client.DataServiceQuery%601> implementa la interfaz <xref:System.Linq.IQueryable%601> definida por LINQ, puede crear una consulta LINQ en fuentes expuestas por el servicio de datos, que la biblioteca cliente traduce en un URI de solicitud de consulta que se envía al servicio de datos en la ejecución.  
  
> [!IMPORTANT]
> El conjunto de consultas que se expresan en la sintaxis de LINQ es más amplio que los habilitados en la sintaxis de URI que usan los servicios de datos de OData. Cuando la consulta no se puede asignar a ningún URI del servicio de datos de destino, se produce una excepción <xref:System.NotSupportedException>. Para obtener más información, vea los [métodos LINQ no admitidos](linq-considerations-wcf-data-services.md#unsupportedMethods) en este tema.  
  
 El siguiente ejemplo es una consulta LINQ que devuelve `Orders` con un costo de flete de más de 30 $ y ordena los resultados por la fecha de envío, comenzando por la fecha de envío más reciente:  
  
[!code-csharp[Astoria Northwind Client#AddQueryOptionsLinqSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addqueryoptionslinqspecific)]      
[!code-vb[Astoria Northwind Client#AddQueryOptionsLinqSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addqueryoptionslinqspecific)]    
  
 Esta consulta LINQ se traduce en el siguiente URI de consulta que se ejecuta en el servicio de datos de [Inicio rápido](quickstart-wcf-data-services.md) basado en Northwind:  
  
```http
http://localhost:12345/Northwind.svc/Orders?Orderby=ShippedDate&?filter=Freight gt 30  
```  
  
 Para obtener más información general sobre LINQ, consulte [Language-Integrated Query (LINQ) C# ](../../../csharp/programming-guide/concepts/linq/index.md) o [Language-Integrated Query (LINQ)-Visual Basic](../../../visual-basic/programming-guide/concepts/linq/index.md).  
  
 LINQ permite redactar consultas mediante el uso tanto de la sintaxis de consulta declarativa específica del lenguaje, mostrada en el ejemplo anterior, como de un conjunto de métodos de consulta denominados operadores de consulta estándar. Una consulta equivalente al ejemplo anterior se puede redactar mediante el uso de la sintaxis basada en métodos únicamente, como se muestra en el siguiente ejemplo:  
  
[!code-csharp[Astoria Northwind Client#AddQueryOptionsLinqExpressionSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addqueryoptionslinqexpressionspecific)]      
[!code-vb[Astoria Northwind Client#AddQueryOptionsLinqExpressionSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addqueryoptionslinqexpressionspecific)]    
  
 El cliente WCF Data Services es capaz de traducir ambos tipos de consultas compuestas en un URI de consulta, y puede extender una consulta LINQ anexando métodos de consulta a una expresión de consulta. Cuando redacte consultas LINQ anexando la sintaxis del método a una expresión de consulta o a una clase <xref:System.Data.Services.Client.DataServiceQuery%601>, las operaciones se agregan al URI de la consulta en el orden en el que se llama a los métodos. Esto es equivalente a llamar al método <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> para agregar cada opción de consulta al URI de la consulta.  
  
## <a name="executing-linq-queries"></a>Ejecutar consultas LINQ  
 Ciertos métodos de consulta LINQ, como los métodos <xref:System.Linq.Enumerable.First%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29> o <xref:System.Linq.Enumerable.Single%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29>, cuando se anexan a la consulta, provocan la ejecución de esta. También se ejecuta una consult6a cuando los resultados se enumeran implícitamente, como durante un bucle `foreach` o cuando la consulta se asigna a una colección `List`. Para obtener más información, consulte [consultar el servicio de datos](querying-the-data-service-wcf-data-services.md).  
  
 El cliente ejecuta una consulta LINQ en dos partes. Siempre que sea posible, las expresiones LINQ de una consulta primero se evalúan en el cliente y, a continuación, se generan y se envían al servicio de datos para su evaluación en los datos del servicio. Para obtener más información, vea la sección [cliente frente a ejecución del servidor](querying-the-data-service-wcf-data-services.md#executingQueries) [al consultar el servicio de datos](querying-the-data-service-wcf-data-services.md).  
  
 Cuando una consulta LINQ no se puede traducir en un URI de consulta compatible con OData, se produce una excepción cuando se intenta la ejecución. Para obtener más información, consulte [consultar el servicio de datos](querying-the-data-service-wcf-data-services.md).  
  
## <a name="linq-query-examples"></a>Ejemplos de consultas LINQ  
 En los ejemplos de las secciones siguientes se muestran los tipos de consultas LINQ que se pueden ejecutar en un servicio de OData.  
  
<a name="filtering"></a>   
### <a name="filtering"></a>Filtrado  
 Los ejemplos de consultas LINQ de esta sección filtran los datos de la fuente devuelta por el servicio.  
  
 Los siguientes ejemplos son consultas equivalentes que filtran las entidades `Orders` devueltas para que solo se devuelvan los pedidos con un costo de flete mayor que 30 $:  
  
- Usar sintaxis de consulta LINQ:  
  
[!code-csharp[Astoria Northwind Client#LinqWhereClauseSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqwhereclausespecific)]      
[!code-vb[Astoria Northwind Client#LinqWhereClauseSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqwhereclausespecific)]     
  
- Usar métodos de consulta LINQ:  
  
[!code-csharp[Astoria Northwind Client#LinqWhereMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqwheremethodspecific)]      
[!code-vb[Astoria Northwind Client#LinqWhereMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqwheremethodspecific)]       
  
- La opción `$filter` de la cadena de consulta del URI:  
  
[!code-csharp[Astoria Northwind Client#ExplicitQueryWhereMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#explicitquerywheremethodspecific)]      
[!code-vb[Astoria Northwind Client#ExplicitQueryWhereMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#explicitquerywheremethodspecific)]       
  
 Todos los ejemplos anteriores se traducen en el URI de consulta: `http://localhost:12345/northwind.svc/Orders()?$filter=Freight gt 30M`.  
  
<a name="sorting"></a>   
### <a name="sorting"></a>Ordenar  
 Los siguientes ejemplos muestran consultas equivalentes que ordenan ascendentemente los datos tanto por nombre de compañía como por código postal:  
  
- Usar sintaxis de consulta LINQ:  
  
[!code-csharp[Astoria Northwind Client#LinqOrderByClauseSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqorderbyclausespecific)]      
[!code-vb[Astoria Northwind Client#LinqOrderByClauseSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqorderbyclausespecific)]        
  
- Usar métodos de consulta LINQ:  
  
[!code-csharp[Astoria Northwind Client#LinqOrderByMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqorderbymethodspecific)]      
[!code-vb[Astoria Northwind Client#LinqOrderByMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqorderbymethodspecific)]        
  
- Opción `$orderby` de la cadena de consulta del URI):  
  
[!code-csharp[Astoria Northwind Client#ExplicitQueryOrderByMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#explicitqueryorderbymethodspecific)]      
[!code-vb[Astoria Northwind Client#ExplicitQueryOrderByMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#explicitqueryorderbymethodspecific)]         
  
 Todos los ejemplos anteriores se traducen en el URI de consulta: `http://localhost:12345/northwind.svc/Customers()?$orderby=CompanyName,PostalCode desc`.  
  
<a name="projection"></a>   
### <a name="projection"></a>Proyección  
 Los siguientes ejemplos muestran las consultas equivalentes que proyectan los datos devueltos en el tipo `CustomerAddress` más restringido:  
  
- Usar sintaxis de consulta LINQ:  
  
[!code-csharp[Astoria Northwind Client#LinqSelectClauseSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqselectclausespecific)]      
[!code-vb[Astoria Northwind Client#LinqSelectClauseSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqselectclausespecific)]         
  
- Usar métodos de consulta LINQ:  
  
[!code-csharp[Astoria Northwind Client#LinqSelectMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqselectmethodspecific)]      
[!code-vb[Astoria Northwind Client#LinqSelectMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqselectmethodspecific)]         

> [!NOTE]
> La opción de consulta `$select` no se puede agregar a ningún URI de la consulta mediante el uso del método <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A>. Se recomienda usar el método <xref:System.Linq.Enumerable.Select%2A> de LINQ para que el cliente genere la opción de consulta `$select` en el URI de solicitud.  
  
 Los dos ejemplos anteriores se traducen en el URI de la consulta: `"http://localhost:12345/northwind.svc/Customers()?$filter=Country eq 'GerGerm'&$select=CustomerID,Address,City,Region,PostalCode,Country"`.  
  
<a name="paging"></a>   
### <a name="client-paging"></a>Paginación del cliente  
 En los siguientes ejemplos se muestran las consultas equivalentes que solicita una página de las entidades de pedidos ordenados que incluye 25 pedidos, omitiendo los 50 primeros pedidos:  
  
- Aplicar métodos de consulta a una consulta LINQ:  
  
[!code-csharp[Astoria Northwind Client#LinqSkipTakeMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqskiptakemethodspecific)]      
[!code-vb[Astoria Northwind Client#LinqSkipTakeMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqskiptakemethodspecific)]     
  
- opciones `$skip` y `$top` de cadena de consulta de URI):  
  
[!code-csharp[Astoria Northwind Client#ExplicitQuerySkipTakeMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#explicitqueryskiptakemethodspecific)]      
[!code-vb[Astoria Northwind Client#ExplicitQuerySkipTakeMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#explicitqueryskiptakemethodspecific)]     
  
 Los dos ejemplos anteriores se traducen en el URI de la consulta: `http://localhost:12345/northwind.svc/Orders()?$orderby=OrderDate desc&$skip=50&$top=25`.  
  
<a name="expand"></a>   
### <a name="expand"></a>Expandir  
 Al consultar un servicio de datos de OData, puede solicitar que las entidades relacionadas con la entidad de destino de la consulta se incluyan en la fuente devuelta. Se llama al método <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> en la clase <xref:System.Data.Services.Client.DataServiceQuery%601> para el conjunto de entidades que sean el destino de la consulta LINQ, con el nombre del conjunto de entidades relacionado proporcionado como el parámetro `path`. Para obtener más información, vea [cargar contenido diferido](loading-deferred-content-wcf-data-services.md).  
  
 En los siguientes ejemplos se muestran las formas equivalentes de usar el método <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> en una consulta:  
  
- En la sintaxis de las consultas LINQ:  
  
[!code-csharp[Astoria Northwind Client#LinqQueryExpandSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqqueryexpandspecific)]      
[!code-vb[Astoria Northwind Client#LinqQueryExpandSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqqueryexpandspecific)]  
  
- Con los métodos de consulta LINQ:  

[!code-csharp[Astoria Northwind Client#LinqQueryExpandMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqqueryexpandmethodspecific)]       
[!code-vb[Astoria Northwind Client#LinqQueryExpandMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqqueryexpandmethodspecific)]       

 Los dos ejemplos anteriores se traducen en el URI de la consulta: `http://localhost:12345/northwind.svc/Orders()?$filter=CustomerID eq 'ALFKI'&$expand=Order_Details`.  
  
<a name="unsupportedMethods"></a>   
## <a name="unsupported-linq-methods"></a>Métodos LINQ no admitidos  
 La tabla siguiente contiene las clases de los métodos de LINQ no se admiten y no se pueden incluir en una consulta ejecutada en un servicio de OData:  
  
|Tipo de operación|Métodos no admitidos|  
|--------------------|------------------------|  
|Operadores de conjuntos|No se admite ningún operador de conjuntos en una clase <xref:System.Data.Services.Client.DataServiceQuery%601>, que incluya lo siguiente:<br /><br /> -   <xref:System.Linq.Enumerable.All%2A><br />-   <xref:System.Linq.Enumerable.Any%2A><br />-   <xref:System.Linq.Enumerable.Concat%2A><br />-   <xref:System.Linq.Enumerable.DefaultIfEmpty%2A><br />-   <xref:System.Linq.Enumerable.Distinct%2A><br />-   <xref:System.Linq.Enumerable.Except%2A><br />-   <xref:System.Linq.Enumerable.Intersect%2A><br />-   <xref:System.Linq.Enumerable.Union%2A><br />-   <xref:System.Linq.Enumerable.Zip%2A>|  
|Operaciones de ordenación|No se admiten los siguientes operadores de ordenación que requieran la interfaz <xref:System.Collections.Generic.IComparer%601> en una clase <xref:System.Data.Services.Client.DataServiceQuery%601>:<br /><br /> -   <xref:System.Linq.Enumerable.OrderBy%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.OrderByDescending%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.ThenBy%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.ThenByDescending%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29>|  
|Métodos de proyección y filtrado|No se admiten ninguno de los siguientes operadores de proyección y filtrado que acepten un argumento posicional en una clase <xref:System.Data.Services.Client.DataServiceQuery%601>:<br /><br /> -   <xref:System.Linq.Enumerable.Join%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D%2CSystem.Collections.Generic.IEqualityComparer%7B%60%602%7D%29><br />-   <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2C%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%603%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%602%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%603%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%602%7D%29><br />-   <xref:System.Linq.Enumerable.Where%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2CSystem.Boolean%7D%29>|  
|Operadores de agrupación|No se admite ningún operador de agrupación en una clase <xref:System.Data.Services.Client.DataServiceQuery%601>, que incluya lo siguiente:<br /><br /> -   <xref:System.Linq.Enumerable.GroupBy%2A><br />-   <xref:System.Linq.Enumerable.GroupJoin%2A><br /><br /> Los operadores de agrupación se deben ejecutar en el cliente.|  
|Operadores de agregación|No se admite ninguna operación de agregado en una clase <xref:System.Data.Services.Client.DataServiceQuery%601>, que incluya lo siguiente:<br /><br /> -   <xref:System.Linq.Enumerable.Aggregate%2A><br />-   <xref:System.Linq.Enumerable.Average%2A><br />-   <xref:System.Linq.Enumerable.Count%2A><br />-   <xref:System.Linq.Enumerable.LongCount%2A><br />-   <xref:System.Linq.Enumerable.Max%2A><br />-   <xref:System.Linq.Enumerable.Min%2A><br />-   <xref:System.Linq.Enumerable.Sum%2A><br /><br /> Las operaciones de agregado se deben ejecutar en el cliente o las debe encapsular una operación de servicio.|  
|Operadores de paginación|No se admiten los siguientes operadores de paginación en una clase <xref:System.Data.Services.Client.DataServiceQuery%601>:<br /><br /> -   <xref:System.Linq.Enumerable.ElementAt%2A><br />-   <xref:System.Linq.Enumerable.Last%2A><br />-   <xref:System.Linq.Enumerable.LastOrDefault%2A><br />-   <xref:System.Linq.Enumerable.SkipWhile%2A><br />-   <xref:System.Linq.Enumerable.TakeWhile%2A><br/><br/>**Nota:**  Los operadores de paginación que se ejecutan en una secuencia vacía devuelven null.|  
|Operadores adicionales|Los operadores siguientes tampoco se admiten en un <xref:System.Data.Services.Client.DataServiceQuery%601>:<br /><br /> - <xref:System.Linq.Enumerable.Empty%2A><br />- <xref:System.Linq.Enumerable.Range%2A><br />- <xref:System.Linq.Enumerable.Repeat%2A><br />- <xref:System.Linq.Enumerable.ToDictionary%2A><br />- <xref:System.Linq.Enumerable.ToLookup%2A>|  
  
<a name="supportedExpressions"></a>   
## <a name="supported-expression-functions"></a>Funciones de expresión admitidas  
 Se admiten los siguientes métodos y propiedades de Common Language Runtime (CLR) porque se pueden traducir en una expresión de consulta para su inclusión en el URI de solicitud en un servicio de OData:  
  
|Miembro de <xref:System.String>|Función de OData admitida|  
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
  
|Miembro de <xref:System.DateTime><sup>1</sup>|Función de OData admitida|  
|-------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.DateTime.Day>|`int day(DateTime p0)`|  
|<xref:System.DateTime.Hour>|`int hour(DateTime p0)`|  
|<xref:System.DateTime.Minute>|`int minute(DateTime p0)`|  
|<xref:System.DateTime.Month>|`int month(DateTime p0)`|  
|<xref:System.DateTime.Second>|`int second(DateTime p0)`|  
|<xref:System.DateTime.Year>|`int year(DateTime p0)`|  
  
 <sup>1</sup> También se admiten las propiedades de fecha y hora equivalentes de <xref:Microsoft.VisualBasic.DateAndTime?displayProperty=nameWithType> y el método de <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> de Visual Basic.  
  
|Miembro de <xref:System.Math>|Función de OData admitida|  
|---------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.Math.Ceiling%28System.Decimal%29>|`decimal ceiling(decimal p0)`|  
|<xref:System.Math.Ceiling%28System.Double%29>|`double ceiling(double p0)`|  
|<xref:System.Math.Floor%28System.Decimal%29>|`decimal floor(decimal p0)`|  
|<xref:System.Math.Floor%28System.Double%29>|`double floor(double p0)`|  
|<xref:System.Math.Round%28System.Decimal%29>|`decimal round(decimal p0)`|  
|<xref:System.Math.Round%28System.Double%29>|`double round(double p0)`|  
  
|Miembro de <xref:System.Linq.Expressions.Expression>|Función de OData admitida|  
|---------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.Linq.Expressions.Expression.TypeIs%28System.Linq.Expressions.Expression%2CSystem.Type%29>|`bool isof(type p0)`|  
  
 Además, el cliente quizá pueda evaluar las funciones CLR adicionales en el cliente. Se produce una excepción <xref:System.NotSupportedException> para cualquier expresión que no se pueda evaluar en el cliente y que no se pueda traducir en un URI de solicitud válido para su evaluación en el servidor.  
  
## <a name="see-also"></a>Vea también

- [Consultar el servicio de datos](querying-the-data-service-wcf-data-services.md)
- [Proyecciones de consultas](query-projections-wcf-data-services.md)
- [Materialización de objetos](object-materialization-wcf-data-services.md)
- [OData: convenciones de URI](https://www.odata.org/documentation/odata-version-2-0/uri-conventions/)
