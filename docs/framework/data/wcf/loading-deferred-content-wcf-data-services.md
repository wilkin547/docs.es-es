---
description: Más información acerca de cómo cargar contenido diferido (Servicios de datos de WCF)
title: Cargar contenido diferido (Servicios de datos de WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, client library
- WCF Data Services, deferred content
- WCF Data Services, loading data
ms.assetid: 32f9b588-c832-44c4-a7e0-fcce635df59a
ms.openlocfilehash: e14796ba003cbad721160ed4a0e2be3e8d148660
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764923"
---
# <a name="loading-deferred-content-wcf-data-services"></a>Cargar contenido diferido (Servicios de datos de WCF)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

De forma predeterminada, Servicios de datos de WCF limita la cantidad de datos que devuelve una consulta. Sin embargo, es posible cargar explícitamente datos adicionales, incluidos los datos de la respuesta paginados, las entidades relacionadas y los flujos de datos binarios, del servicio de datos cuando sea necesario. En este tema se describe cómo cargar dicho contenido aplazado en una aplicación.  
  
## <a name="related-entities"></a>Entidades relacionadas  

 Cuando se ejecuta una consulta, solo se devuelven las entidades pertenecientes al conjunto de entidades direccionado. Por ejemplo, cuando una consulta al servicio de datos Northwind devuelve entidades `Customers`, no se devuelven de forma predeterminada las entidades `Orders` relacionadas aunque haya una relación entre `Customers` y `Orders`. Además, cuando está habilitada la paginación en el servicio de datos, debe cargar explícitamente las páginas de datos subsiguientes del servicio. Hay dos maneras de cargar las entidades relacionadas:  
  
- **Carga diligente**: puede usar la `$expand` opción de consulta para solicitar que la consulta devuelva entidades que están relacionadas por una asociación con el conjunto de entidades solicitado por la consulta. Utilice el método <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> en <xref:System.Data.Services.Client.DataServiceQuery%601> para agregar la opción `$expand` a la consulta que se envía al servicio de datos. Puede solicitar varios conjuntos de entidades relacionados separándolos mediante comas, como muestra el ejemplo siguiente. Todas las entidades solicitadas por la consulta se devuelven en una única respuesta. En el ejemplo siguiente se devuelve `Order_Details` y `Customers` junto con el conjunto de entidades `Orders`:  
  
     [!code-csharp[Astoria Northwind Client#ExpandOrderDetailsSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#expandorderdetailsspecific)]
     [!code-vb[Astoria Northwind Client#ExpandOrderDetailsSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#expandorderdetailsspecific)]  
  
     Servicios de datos de WCF limita a 12 el número de conjuntos de entidades que se pueden incluir en una sola consulta mediante la `$expand` opción de consulta.  
  
- **Carga explícita**: puede llamar al <xref:System.Data.Services.Client.DataServiceContext.LoadProperty%2A> método en la <xref:System.Data.Services.Client.DataServiceContext> instancia para cargar explícitamente las entidades relacionadas. Cada llamada al método <xref:System.Data.Services.Client.DataServiceContext.LoadProperty%2A> crea una solicitud independiente al servicio de datos. En el ejemplo siguiente se carga explícitamente `Order_Details` para una entidad `Orders`:  
  
     [!code-csharp[Astoria Northwind Client#LoadRelatedOrderDetailsSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#loadrelatedorderdetailsspecific)]
     [!code-vb[Astoria Northwind Client#LoadRelatedOrderDetailsSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#loadrelatedorderdetailsspecific)]  
  
 Al considerar qué opción se debe usar, observe que hay una correlación entre el número de solicitudes al servicio de datos y la cantidad de datos devueltos en una sola respuesta. Use la carga diligente cuando su aplicación requiera objetos asociados y desee evitar la latencia agregada de las solicitudes adicionales para recuperarlos explícitamente. Sin embargo, si hay casos en que la aplicación solo necesita los datos para determinadas instancias de entidades relacionadas, debería plantearse cargar explícitamente esas entidades llamando al método <xref:System.Data.Services.Client.DataServiceContext.LoadProperty%2A>. Para obtener más información, consulte [Cómo: cargar entidades relacionadas](how-to-load-related-entities-wcf-data-services.md).  
  
## <a name="paged-content"></a>Contenido paginado  

 Si la paginación está habilitada en el servicio de datos, la configuración del servicio de datos limita el número de entradas de la fuente que devuelve el servicio de datos. Los límites de página pueden establecerse por separado para cada conjunto de entidades. Para obtener más información, vea [configurar el servicio de datos](configuring-the-data-service-wcf-data-services.md). Si está habilitada la paginación, la última entrada de la fuente contiene un vínculo a la página de datos siguiente. Este vínculo está contenido en un objeto <xref:System.Data.Services.Client.DataServiceQueryContinuation%601>. El URI a la página de datos siguiente se obtiene llamando al método <xref:System.Data.Services.Client.QueryOperationResponse%601.GetContinuation%2A> del objeto <xref:System.Data.Services.Client.QueryOperationResponse%601> que se obtiene cuando se ejecuta <xref:System.Data.Services.Client.DataServiceQuery%601>. A continuación, el objeto <xref:System.Data.Services.Client.DataServiceQueryContinuation%601> devuelto se usa para cargar la página de resultados siguiente. Debe enumerar los resultados de la consulta antes de llamar al método <xref:System.Data.Services.Client.QueryOperationResponse%601.GetContinuation%2A>. Considere la posibilidad de usar un bucle `do…while` para enumerar el resultado de la consulta primero y, a continuación, comprobar el valor de un vínculo siguiente `non-null`. Cuando el método <xref:System.Data.Services.Client.QueryOperationResponse%601.GetContinuation%2A> devuelve `null` (`Nothing` en Visual Basic), no hay ninguna página de resultados adicional para la consulta original. En el ejemplo siguiente se muestra un bucle `do…while` que carga los datos del cliente paginados del servicio de datos de ejemplo Northwind.  
  
 [!code-csharp[Astoria Northwind Client#LoadNextLink](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#loadnextlink)]
 [!code-vb[Astoria Northwind Client#LoadNextLink](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#loadnextlink)]  
  
 Cuando una consulta solicita que se devuelvan las entidades relacionadas en una respuesta única junto con el conjunto de entidades solicitado, los límites de paginación pueden afectar a las fuentes anidadas que están incluidas alineadas con la respuesta. Por ejemplo, cuando se establece un límite de paginación en el servicio de datos de ejemplo Northwind para el conjunto de entidades `Customers`, también puede establecerse un límite de paginación independiente para el conjunto de entidades `Orders` relacionado, como en el ejemplo siguiente del archivo Northwind.svc.cs que define el servicio de datos de ejemplo Northwind.  
  
 [!code-csharp[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind.svc.cs#dataserviceconfigpaging)]
 [!code-vb[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind.svc.vb#dataserviceconfigpaging)]  
  
 En este caso, debe implementar la paginación para las dos fuentes de entidades, la de nivel superior, `Customers`, y las anidadas, `Orders`. En el ejemplo siguiente se muestra el bucle `while` que se usa para cargar las páginas de las entidades `Orders` relacionadas con una entidad `Customers` seleccionada.  
  
 [!code-csharp[Astoria Northwind Client#LoadNextOrdersLink](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#loadnextorderslink)]
 [!code-vb[Astoria Northwind Client#LoadNextOrdersLink](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#loadnextorderslink)]  
  
 Para obtener más información, consulte [Cómo: cargar resultados paginados](how-to-load-paged-results-wcf-data-services.md).  
  
## <a name="binary-data-streams"></a>Flujos de datos binarios  

 Servicios de datos de WCF permite tener acceso a datos de objetos binarios grandes (BLOB) como un flujo de datos. La transmisión por secuencias aplaza la carga de datos binarios hasta que se necesita, y el cliente puede procesar estos datos más eficazmente. Para aprovecharse de esta funcionalidad, el servicio de datos debe implementar el proveedor <xref:System.Data.Services.Providers.IDataServiceStreamProvider>. Para obtener más información, consulte [proveedor de streaming](streaming-provider-wcf-data-services.md). Cuando está habilitada la transmisión por secuencias, los tipos de entidad se devuelven sin los datos binarios relacionados. En este caso, debe utilizar el <xref:System.Data.Services.Client.DataServiceContext.GetReadStream%2A> método de la <xref:System.Data.Services.Client.DataServiceContext> clase para tener acceso al flujo de datos para los datos binarios del servicio. De igual forma, use el método <xref:System.Data.Services.Client.DataServiceContext.SetSaveStream%2A> para agregar o cambiar los datos binarios de una entidad como un flujo. Para obtener más información, vea [trabajar con datos binarios](working-with-binary-data-wcf-data-services.md).  
  
## <a name="see-also"></a>Vea también

- [Biblioteca cliente de Data Services de WCF](wcf-data-services-client-library.md)
- [Consultar el servicio de datos](querying-the-data-service-wcf-data-services.md)
