---
title: Información general sobre Data Services de WCF
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services
- WCF Data Services, about
ms.assetid: 7924cf94-c9a6-4015-afc9-f5d22b1743bb
ms.openlocfilehash: bca07bf776f20443c4ccd2af69fc8c0b4eec5a88
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991097"
---
# <a name="wcf-data-services-overview"></a>Información general sobre Data Services de WCF
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]habilita la creación y el consumo de servicios de datos para web o una intranet mediante [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]el. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]permite exponer los datos como recursos direccionables mediante URI. Esto permite tener acceso a los datos y modificarlos usando la semántica de Representational State Transfer (REST), específicamente los verbos HTTP estándar GET, PUT, POST y DELETE. En este tema se proporciona información general sobre los modelos y los procedimientos definidos por [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], así como las funciones proporcionadas por [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] para aprovechar las ventajas de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] en las aplicaciones basadas en .NET Framework.  
  
## <a name="address-data-as-resources"></a>Direccionamiento de datos como recursos  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] expone los datos como recursos direccionables a través de identificadores uniformes de recursos (URI). Las rutas de acceso de recursos se construyen según las convenciones del modelo entidad-relación de Entity Data Model. En este modelo, las entidades representan unidades operativas de datos en un dominio de aplicación, como clientes, pedidos, elementos y productos. Para obtener más información, vea [Entity Data Model](../adonet/entity-data-model.md).  
  
 En [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], los recursos de entidades se direccionan como conjunto de entidades que contiene instancias de tipos de entidad. Por ejemplo, el URI <https://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders> devuelve todos los pedidos `Northwind` del servicio de datos relacionados con el cliente con un `CustomerID` valor de`ALFKI.`  
  
 Las expresiones de consulta permiten realizar operaciones de consulta tradicionales en los recursos, como filtrarlos, ordenarlos y paginarlos. Por ejemplo, el URI <https://services.odata.org/Northwind/Northwind.svc/Customers( ' ALFKI ')/Orders? $Filter = Freight gt 50 > filtra los recursos para devolver solo los pedidos con un costo de flete superior a $50. Para obtener más información, consulte [acceso a los recursos del servicio de datos](accessing-data-service-resources-wcf-data-services.md).  
  
## <a name="interoperable-data-access"></a>Interoperabilidad en el acceso a los datos  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]se basa en protocolos estándar de Internet para que los servicios de datos puedan interoperar con aplicaciones que no usan el .NET Framework. Dado que puede usar URI estándar para direccionar los datos, la aplicación puede acceder a los datos y cambiarlos mediante la semántica de transferencia de estado representacional (REST), específicamente los verbos HTTP estándar GET, PUT, POST y DELETE. Esto le permite tener acceso a estos servicios desde cualquier cliente que pueda analizar y tener acceso a los datos que se transmiten mediante los protocolos HTTP estándar.  
  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] define un conjunto de extensiones del protocolo de publicación Atom (AtomPub). Es compatible con solicitudes y respuestas HTTP en más de un formato de datos para adaptarse a diversas aplicaciones y plataformas de cliente. Una fuente [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] puede representar los datos en formato Atom, JavaScript Object Notation (JSON) y como XML sin formato. Aunque Atom es el formato predeterminado, el formato de la fuente se especifica en el encabezado de la solicitud HTTP. Para obtener más información, [consulte OData: Formato](https://go.microsoft.com/fwlink/?LinkID=185794) Atom y [OData: Formato](https://go.microsoft.com/fwlink/?LinkID=185795)JSON.  
  
 Al publicar datos como una [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] fuente, [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] se basa en otros servicios de Internet existentes para operaciones como el almacenamiento en caché y la autenticación. Para ello, [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] se integra con servicios y aplicaciones de hospedaje existentes, como ASP.net, Windows Communication Foundation (WCF) y Internet Information Services (IIS).  
  
## <a name="storage-independence"></a>Independencia de almacenamiento  
 Aunque los recursos se direccionan basándose en un modelo entidad-relación, [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] expone las fuentes de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] sin tener en cuenta el origen de datos subyacente. Después de que [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] acepte una solicitud HTTP para un recurso identificado mediante un URI, se deserializa la solicitud y se pasa una representación de la misma a un proveedor de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]. Este proveedor traduce la solicitud en un formato específico del origen de datos y la ejecuta en el origen de datos subyacente. [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] logra la independencia de almacenamiento separando el modelo conceptual que direcciona los recursos indicados por [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] del esquema específico del origen de datos subyacente.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] se integra con ADO.NET Entity Framework para que puedan crearse servicios de datos que exponen datos relacionales. Puede usar las herramientas de Entity Data Model para crear un modelo de datos que contiene recursos direccionables como entidades y al mismo tiempo definir la asignación entre este modelo y las tablas de la base de datos subyacente. Para obtener más información, vea [proveedor de Entity Framework](entity-framework-provider-wcf-data-services.md).  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]también le permite crear servicios de datos que exponen cualquier estructura de datos que devuelva <xref:System.Linq.IQueryable%601> una implementación de la interfaz. Esto le permite crear servicios de datos que exponen los datos procedentes de tipos de .NET Framework. Si también se implementa la interfaz <xref:System.Data.Services.IUpdatable>, se admiten las operaciones de creación, actualización y eliminación. Para obtener más información, vea [proveedor de reflexión](reflection-provider-wcf-data-services.md).  
  
 Para ver una ilustración de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] cómo se integra con estos proveedores de datos, vea el diagrama arquitectónico más adelante en este tema.  
  
## <a name="custom-business-logic"></a>Lógica de negocios personalizada  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]facilita la tarea de agregar lógica de negocios personalizada a un servicio de datos a través de operaciones de servicio e interceptores. Las operaciones de servicio son métodos definidos en el servidor direccionables a través de URI con el mismo formato que los recursos de datos. Las operaciones de servicio también pueden usar la sintaxis de las expresiones de consulta para filtrar, ordenar y paginar los datos devueltos por una operación. Por ejemplo, el URI `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$orderby=OrderDate&$top=10&$skip=10` representa una llamada a una operación de servicio denominada `GetOrdersByCity` en el servicio de datos de Northwind que devuelve los pedidos para los clientes residentes en Londres, con los resultados paginados ordenados por `OrderDate`. Para obtener más información, consulte [operaciones de servicio](service-operations-wcf-data-services.md).  
  
 Los interceptores permiten integrar la lógica de la aplicación personalizada en el procesamiento de los mensajes de solicitud o respuesta de un servicio de datos. Se llama a los interceptores cuando se produce una acción de consulta, inserción, actualización o eliminación en el conjunto de entidades especificado. Un interceptor puede modificar después los datos, aplicar la directiva de autorización o incluso terminar la operación. Los métodos de interceptor se deben registrar explícitamente para un conjunto de entidades determinado expuesto por un servicio de datos. Para obtener más información, vea [interceptores](interceptors-wcf-data-services.md).  
  
## <a name="client-libraries"></a>Bibliotecas de cliente  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]define un conjunto de modelos uniformes para interactuar con los servicios de datos. Esto proporciona una oportunidad para crear componentes reutilizables basados en estos servicios, como bibliotecas de cliente que facilitan el consumo de servicios de datos.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] incluye bibliotecas de cliente para aplicaciones cliente basadas en .NET Framework o en Silverlight. Estas bibliotecas de cliente le permiten interactuar con los servicios de datos mediante objetos de .NET Framework. También admiten consultas basadas en objetos y consultas LINQ, carga de objetos relacionados, seguimiento de cambios y resolución de identidades. Para obtener más información, vea [WCF Data Services biblioteca de cliente](wcf-data-services-client-library.md).  
  
 Además de las [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] bibliotecas de cliente incluidas en el .NET Framework y con Silverlight, hay otras bibliotecas de cliente que le permiten consumir una [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] fuente en aplicaciones cliente, como aplicaciones PHP, Ajax y Java. Para obtener más información, vea el [SDK de oData](https://go.microsoft.com/fwlink/?LinkID=185796).  
  
## <a name="architecture-overview"></a>Información general sobre la arquitectura  
 En el diagrama siguiente se muestra [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] la arquitectura para [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] exponer fuentes y usar estas fuentes en [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]las bibliotecas de cliente habilitadas para:  
  
 ![Captura de pantalla que muestra un diagrama de arquitectura de WCF Data Services.](./media/wcf-data-services-overview/windows-communication-foundation-data-services-architecture.gif)  
  
## <a name="see-also"></a>Vea también

- [Servicios de datos de WCF 4.5](index.md)
- [Introducción](getting-started-with-wcf-data-services.md)
- [Definir Servicios de datos de WCF](defining-wcf-data-services.md)
- [Acceso a los recursos del servicio de datos (WCF Data Services)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd728283(v=vs.100))
- [Biblioteca cliente de Servicios de datos de WCF](wcf-data-services-client-library.md)
- [Transferencia de estado representacional (REST)](https://go.microsoft.com/fwlink/?LinkId=113919)
