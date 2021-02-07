---
description: Más información acerca de cómo configurar el servicio de datos (Servicios de datos de WCF)
title: Configurar el servicio de datos (Data Services de WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 59efd4c8-cc7a-4800-a0a4-d3f8abe6c55c
ms.openlocfilehash: 72bd0de5319cc4b19fd831f4ee302e073106c74b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99766199"
---
# <a name="configuring-the-data-service-wcf-data-services"></a>Configurar el servicio de datos (Data Services de WCF)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

Con Servicios de datos de WCF, puede crear servicios de datos que expongan fuentes Open Data Protocol (OData). Los datos de estas fuentes pueden proceder de diferentes orígenes de datos. Servicios de datos de WCF utiliza proveedores de datos para exponer estos datos como una fuente de OData. Estos proveedores incluyen un proveedor de Entity Framework, un proveedor de reflexión y un conjunto de interfaces de proveedor de servicio de datos personalizados. La implementación del proveedor define el modelo de datos del servicio. Para obtener más información, vea [proveedores de Data Services](data-services-providers-wcf-data-services.md).  
  
 En Servicios de datos de WCF, un servicio de datos es una clase que hereda de la <xref:System.Data.Services.DataService%601> clase, donde el tipo del servicio de datos es el contenedor de entidades del modelo de datos. Este contenedor de entidades tiene una o varias propiedades que devuelven una interfaz <xref:System.Linq.IQueryable%601>, que se usa para tener acceso a los conjuntos de entidades del modelo de datos.  
  
 Los miembros de la clase <xref:System.Data.Services.DataServiceConfiguration> definen los comportamientos del servicio de datos junto con los miembros de la clase <xref:System.Data.Services.DataServiceBehavior>, a la que se tiene acceso desde la propiedad <xref:System.Data.Services.DataServiceConfiguration.DataServiceBehavior%2A> de la clase <xref:System.Data.Services.DataServiceConfiguration>. La clase <xref:System.Data.Services.DataServiceConfiguration> se proporciona al método `InitializeService` que implementa el servicio de datos, como en la siguiente implementación de un servicio de datos de Northwind:  
  
[!code-csharp[Astoria Northwind Service#DataServiceConfigComplete](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind.svc.cs#dataserviceconfigcomplete)]  
[!code-vb[Astoria Northwind Service#DataServiceConfigComplete](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind.svc.vb#dataserviceconfigcomplete)]  
  
## <a name="data-service-configuration-settings"></a>Configuración del servicio de datos  

 La clase <xref:System.Data.Services.DataServiceConfiguration> permite especificar los comportamientos siguientes del servicio de datos.  
  
|Miembro|Comportamiento|  
|------------|--------------|  
|<xref:System.Data.Services.DataServiceBehavior.AcceptCountRequests%2A>|Permite deshabilitar las solicitudes de recuento que se envían al servicio de datos usando el segmento de ruta de acceso `$count` y la opción de consulta `$inlinecount`. Para obtener más información, vea [OData: convenciones de URI](https://www.odata.org/documentation/odata-version-2-0/uri-conventions/).|  
|<xref:System.Data.Services.DataServiceBehavior.AcceptProjectionRequests%2A>|Permite deshabilitar la compatibilidad con la proyección de los datos en las solicitudes que se envían al servicio de datos usando la opción de consulta `$select`. Para obtener más información, vea [OData: convenciones de URI](https://www.odata.org/documentation/odata-version-2-0/uri-conventions/).|  
|<xref:System.Data.Services.DataServiceConfiguration.EnableTypeAccess%2A>|Permite exponer un tipo de datos en los metadatos para un proveedor de metadatos dinámico definido mediante la interfaz <xref:System.Data.Services.Providers.IDataServiceMetadataProvider>.|  
|<xref:System.Data.Services.DataServiceConfiguration.EnableTypeConversion%2A>|Le permite especificar si el motor en tiempo de ejecución del servicio de datos debe convertir el tipo contenido en la carga al tipo de propiedad real que se especifica en la solicitud.|  
|<xref:System.Data.Services.DataServiceBehavior.InvokeInterceptorsOnLinkDelete%2A>|Permite especificar si se invocan o no interceptores de cambio registrados en las entidades relacionadas cuando se elimina un vínculo de relación entre dos entidades.|  
|<xref:System.Data.Services.DataServiceConfiguration.MaxBatchCount%2A>|Permite limitar el número de conjuntos de cambios y operaciones de consulta que se permiten en un solo lote. Para obtener más información, consulte [OData: Batch](https://www.odata.org/documentation/odata-version-2-0/batch-processing/) and [batch Operations](batching-operations-wcf-data-services.md).|  
|<xref:System.Data.Services.DataServiceConfiguration.MaxChangesetCount%2A>|Permite limitar el número máximo de cambios que se pueden incluir en un solo conjunto de cambios. Para obtener más información, consulte [Cómo: habilitar la paginación de los resultados del servicio de datos](how-to-enable-paging-of-data-service-results-wcf-data-services.md).|  
|<xref:System.Data.Services.DataServiceConfiguration.MaxExpandCount%2A>|Permite limitar el tamaño de una respuesta limitando el número de entidades relacionadas que pueden incluirse en una sola solicitud utilizando el operador de consulta `$expand`. Para obtener más información, vea [OData: convenciones de URI](https://www.odata.org/documentation/odata-version-2-0/uri-conventions/) y [carga de contenido aplazado](loading-deferred-content-wcf-data-services.md).|  
|<xref:System.Data.Services.DataServiceConfiguration.MaxExpandDepth%2A>|Permite limitar el tamaño de una respuesta limitando la profundidad del gráfico de las entidades relacionadas que pueden incluirse en una sola solicitud usando el operador de consulta `$expand`. Para obtener más información, vea [OData: convenciones de URI](https://www.odata.org/documentation/odata-version-2-0/uri-conventions/) y [carga de contenido aplazado](loading-deferred-content-wcf-data-services.md).|  
|<xref:System.Data.Services.DataServiceConfiguration.MaxObjectCountOnInsert%2A>|Permite limitar el número de entidades que se van a insertar que puede contener una sola solicitud POST.|  
|<xref:System.Data.Services.DataServiceBehavior.MaxProtocolVersion%2A>|Define la versión del protocolo Atom utilizado por el servicio de datos. Cuando el valor de <xref:System.Data.Services.DataServiceBehavior.MaxProtocolVersion%2A> se establece en un valor menor que el valor máximo de <xref:System.Data.Services.Common.DataServiceProtocolVersion> , la funcionalidad más reciente de servicios de datos de WCF no está disponible para los clientes que tienen acceso al servicio de datos. Para obtener más información, vea [control de versiones del servicio de datos](data-service-versioning-wcf-data-services.md).|  
|<xref:System.Data.Services.DataServiceConfiguration.MaxResultsPerCollection%2A>|Le permite limitar el tamaño de una respuesta limitando el número de entidades de cada conjunto de entidades que se devuelve como fuente de distribución de datos.|  
|<xref:System.Data.Services.DataServiceConfiguration.RegisterKnownType%2A>|Agrega un tipo de datos a la lista de tipos reconocidos por el servicio de datos.|  
|<xref:System.Data.Services.DataServiceConfiguration.SetEntitySetAccessRule%2A>|Establece los derechos de acceso para los recursos del conjunto de entidades que están disponibles en el servicio de datos. Se puede proporcionar el valor asterisco (`*` para el parámetro de nombre para establecer el acceso en el mismo nivel para todos los conjuntos de entidades restantes. Se recomienda establecer el acceso a los conjuntos de entidades para proporcionar el acceso con privilegios mínimos a los recursos del servicio de datos requeridos por las aplicaciones cliente. Para obtener más información, consulta [Securing WCF Data Services](securing-wcf-data-services.md). Para obtener ejemplos de los derechos de acceso mínimos necesarios para un URI determinado y una acción HTTP, consulte la tabla de la sección [requisitos mínimos de acceso a recursos](configuring-the-data-service-wcf-data-services.md#accessRequirements) .|  
|<xref:System.Data.Services.DataServiceConfiguration.SetEntitySetPageSize%2A>|Establece el tamaño de página máximo de un recurso de conjunto de entidades. Para obtener más información, consulte [Cómo: habilitar la paginación de los resultados del servicio de datos](how-to-enable-paging-of-data-service-results-wcf-data-services.md).|  
|<xref:System.Data.Services.DataServiceConfiguration.SetServiceOperationAccessRule%2A>|Establece los derechos de acceso para las operaciones de servicio definidas en el servicio de datos. Para obtener más información, consulte [operaciones de servicio](service-operations-wcf-data-services.md). Se puede proporcionar el valor asterisco (`*`) para el parámetro de nombre con objeto de establecer el acceso en el mismo nivel para todas las operaciones de servicio. Se recomienda establecer el acceso a las operaciones de servicio para proporcionar el acceso con privilegios mínimos a los recursos del servicio de datos requeridos por las aplicaciones cliente. Para obtener más información, consulta [Securing WCF Data Services](securing-wcf-data-services.md).|  
|<xref:System.Data.Services.DataServiceConfiguration.UseVerboseErrors%2A>|Esta propiedad de configuración le permite solucionar más fácilmente los problemas de un servicio de datos devolviendo más información en el mensaje de respuesta del error. Esta opción no está pensada para su uso en un entorno de producción. Para obtener más información, consulte [desarrollar e implementar servicios de datos de WCF](developing-and-deploying-wcf-data-services.md).|  
  
<a name="accessRequirements"></a>

## <a name="minimum-resource-access-requirements"></a>Requisitos mínimos de acceso a recursos  

 En la siguiente tabla se detallan los derechos mínimos del conjunto de entidades que se deben conceder para ejecutar una operación concreta. Los ejemplos de rutas de acceso se basan en el servicio de datos de Northwind que se crea al completar la guía de [Inicio rápido](quickstart-wcf-data-services.md). Puesto que las enumeraciones <xref:System.Data.Services.EntitySetRights> y <xref:System.Data.Services.ServiceOperationRights> se definen usando la clase <xref:System.FlagsAttribute>, puede usar un operador OR lógico con el fin de especificar varios permisos para una operación o un conjunto de entidades únicos. Para obtener más información, consulte [Cómo: habilitar el acceso al servicio de datos](how-to-enable-access-to-the-data-service-wcf-data-services.md).  
  
|Ruta de acceso/acción|`GET`|`DELETE`|`MERGE`|`POST`|`PUT`|  
|------------------|-----------|--------------|-------------|------------|-----------|  
|`/Customers`|<xref:System.Data.Services.EntitySetRights.ReadMultiple>|No compatible|No compatible|<xref:System.Data.Services.EntitySetRights.WriteAppend>|No compatible|  
|`/Customers('ALFKI')`|<xref:System.Data.Services.EntitySetRights.ReadSingle>|<xref:System.Data.Services.EntitySetRights.ReadSingle> y <xref:System.Data.Services.EntitySetRights.WriteDelete>|<xref:System.Data.Services.EntitySetRights.ReadSingle> y <xref:System.Data.Services.EntitySetRights.WriteMerge>|N/D|<xref:System.Data.Services.EntitySetRights.ReadSingle> y <xref:System.Data.Services.EntitySetRights.WriteReplace>|  
|`/Customers('ALFKI')/Orders`|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle><br /><br /> - y -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.ReadMultiple>|No compatible|No compatible|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle> y <xref:System.Data.Services.EntitySetRights.WriteMerge> o <xref:System.Data.Services.EntitySetRights.WriteReplace><br /><br /> - y -<br /><br /> `Orders``:`y<xref:System.Data.Services.EntitySetRights.WriteAppend>|No compatible|  
|`/Customers('ALFKI')/Orders(10643)`|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle><br /><br /> - y -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.ReadSingle>|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle><br /><br /> - y -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.ReadSingle> y <xref:System.Data.Services.EntitySetRights.WriteDelete>|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle><br /><br /> - y -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.ReadSingle> y <xref:System.Data.Services.EntitySetRights.WriteMerge>|No compatible|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle><br /><br /> - y -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.ReadSingle> y <xref:System.Data.Services.EntitySetRights.WriteReplace>|  
|`/Orders(10643)/Customer`|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle><br /><br /> - y -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.ReadSingle>|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle> y <xref:System.Data.Services.EntitySetRights.WriteDelete><br /><br /> - y -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.ReadSingle>|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle> y <xref:System.Data.Services.EntitySetRights.WriteMerge>;<br /><br /> - y -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.ReadSingle>|`Customers`: <xref:System.Data.Services.EntitySetRights.WriteAppend><br /><br /> - y -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.WriteAppend> y <xref:System.Data.Services.EntitySetRights.ReadSingle>|No compatible|  
|`/Customers('ALFKI')/$links/Orders`|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle><br /><br /> - y -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.ReadMultiple>|No compatible|No compatible|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle> y <xref:System.Data.Services.EntitySetRights.WriteMerge> o <xref:System.Data.Services.EntitySetRights.WriteReplace><br /><br /> - y -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.ReadSingle>|No compatible|  
|`/Customers('ALFKI')/$links/Orders(10643)`|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle><br /><br /> - y -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.ReadSingle>|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle> y <xref:System.Data.Services.EntitySetRights.WriteMerge> o <xref:System.Data.Services.EntitySetRights.WriteReplace><br /><br /> - y -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.ReadSingle>|No compatible|No compatible|No compatible|  
|`/Orders(10643)/$links/Customer`|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle><br /><br /> - y -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.ReadSingle>|`Orders`: <xref:System.Data.Services.EntitySetRights.ReadSingle> y <xref:System.Data.Services.EntitySetRights.WriteMerge> o <xref:System.Data.Services.EntitySetRights.WriteReplace>|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle><br /><br /> - y -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.ReadSingle> y <xref:System.Data.Services.EntitySetRights.WriteMerge>|No compatible|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle>;<br /><br /> - y -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.ReadSingle> y <xref:System.Data.Services.EntitySetRights.WriteReplace>|  
|`/Customers/$count`|<xref:System.Data.Services.EntitySetRights.ReadMultiple>|No compatible|No compatible|No compatible|No compatible|  
|`/Customers('ALFKI')/ContactName`|<xref:System.Data.Services.EntitySetRights.ReadSingle>|No compatible|<xref:System.Data.Services.EntitySetRights.WriteMerge>|No compatible|<xref:System.Data.Services.EntitySetRights.WriteReplace>|  
|`/Customers('ALFKI')/Address/StreetAddress/$value` <sup>1</sup>|<xref:System.Data.Services.EntitySetRights.ReadSingle>|<xref:System.Data.Services.EntitySetRights.WriteDelete>|No compatible|No compatible|No compatible|  
|`/Customers('ALFKI')/ContactName/$value`|<xref:System.Data.Services.EntitySetRights.ReadSingle>|<xref:System.Data.Services.EntitySetRights.ReadSingle> y <xref:System.Data.Services.EntitySetRights.WriteDelete>|<xref:System.Data.Services.EntitySetRights.WriteMerge>|No compatible|<xref:System.Data.Services.EntitySetRights.WriteReplace>|  
|`/Customers('ALFKI')/$value` <sup>2</sup>|<xref:System.Data.Services.EntitySetRights.ReadSingle>|No compatible|No compatible|No compatible|<xref:System.Data.Services.EntitySetRights.WriteReplace>|  
|`/Customers?$select=Orders/*&$expand=Orders`|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle><br /><br /> - y -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.ReadMultiple>|No compatible|No compatible|`Customers`: <xref:System.Data.Services.EntitySetRights.WriteAppend>|No compatible|  
|`/Customers('ALFKI')?$select=Orders/*&$expand=Orders`|`Customers`: <xref:System.Data.Services.EntitySetRights.ReadSingle><br /><br /> - y -<br /><br /> `Orders`: <xref:System.Data.Services.EntitySetRights.ReadMultiple>|No compatible|No compatible|No compatible|No compatible|  
  
 <sup>1</sup> en este ejemplo, `Address` representa una propiedad de tipo complejo de la `Customers` entidad que tiene una propiedad denominada `StreetAddress` . El modelo utilizado por los servicios de datos de Northwind no define este tipo complejo explícitamente. Cuando el modelo de datos se define utilizando el proveedor de Entity Framework, puede utilizar las herramientas de Entity Data Model para definir este tipo complejo. Para obtener más información, vea [Cómo: crear y modificar tipos complejos](/previous-versions/dotnet/netframework-4.0/dd456820(v=vs.100)).  
  
 <sup>2</sup> este URI se admite cuando una propiedad que devuelve un objeto binario grande (BLOB) se define como el recurso multimedia que pertenece a una entidad que es una entrada de vínculo multimedia, que en este caso es `Customers` . Para obtener más información, consulte [proveedor de streaming](streaming-provider-wcf-data-services.md).  
  
<a name="versioning"></a>

## <a name="versioning-requirements"></a>Requisitos de control de versiones  

 Los siguientes comportamientos de configuración del servicio de datos requieren la versión 2 del protocolo OData o versiones posteriores:  
  
- Compatibilidad para las solicitudes de recuento.  
  
- Compatibilidad para la opción de consulta $select de proyección.  
  
 Para obtener más información, vea [control de versiones del servicio de datos](data-service-versioning-wcf-data-services.md).  
  
## <a name="see-also"></a>Vea también

- [Definir Servicios de datos de WCF](defining-wcf-data-services.md)
- [Hospedaje del servicio de datos](hosting-the-data-service-wcf-data-services.md)
