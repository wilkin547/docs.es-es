---
title: Información general sobre Data Services de WCF
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services
- WCF Data Services, about
ms.assetid: 7924cf94-c9a6-4015-afc9-f5d22b1743bb
ms.openlocfilehash: a4121bb10de7bfe51c5fec6bc14a40ad4bdcdaf7
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900891"
---
# <a name="wcf-data-services-overview"></a>Información general sobre Data Services de WCF
WCF Data Services permite la creación y el consumo de servicios de datos para web o una intranet mediante el Open Data Protocol (OData). OData permite exponer los datos como recursos direccionables mediante URI. Esto le permite tener acceso a los datos y cambiarlos mediante la semántica de Representational State Transfer (REST), específicamente los verbos HTTP estándar GET, PUT, POST y DELETE. En este tema se proporciona información general sobre los patrones y prácticas definidos por OData y también los recursos proporcionados por WCF Data Services para aprovechar las ventajas de OData en aplicaciones basadas en .NET Framework.  
  
## <a name="address-data-as-resources"></a>Direccionamiento de datos como recursos  
 OData expone los datos como recursos direccionables a través de identificadores uniformes de recursos (URI). Las rutas de acceso de recursos se construyen según las convenciones del modelo entidad-relación de Entity Data Model. En este modelo, las entidades representan unidades operativas de datos en un dominio de aplicación, como clientes, pedidos, elementos y productos. Para obtener más información, vea [Entity Data Model](../adonet/entity-data-model.md).  
  
 En OData, los recursos de entidad se direccionan como un conjunto de entidades que contiene instancias de tipos de entidad. Por ejemplo, el URI <https://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders> devuelve todos los pedidos del servicio de datos `Northwind` que están relacionados con el cliente con un valor `CustomerID` de `ALFKI.`  
  
 Las expresiones de consulta permiten realizar operaciones de consulta tradicionales en los recursos, como filtrarlos, ordenarlos y paginarlos. Por ejemplo, el URI <https://services.odata.org/Northwind/Northwind.svc/Customers( ' ALFKI ')/Orders? $filter = Freight gt 50 > filtra los recursos para devolver solo los pedidos con un costo de flete superior a $50. Para obtener más información, consulte [acceso a los recursos del servicio de datos](accessing-data-service-resources-wcf-data-services.md).  
  
## <a name="interoperable-data-access"></a>Interoperabilidad en el acceso a los datos  
 OData se basa en protocolos estándar de Internet para que los servicios de datos puedan interoperar con aplicaciones que no usan el .NET Framework. Dado que puede usar URI estándar para direccionar los datos, la aplicación puede acceder a los datos y cambiarlos mediante la semántica de transferencia de estado representacional (REST), específicamente los verbos HTTP estándar GET, PUT, POST y DELETE. Esto le permite tener acceso a estos servicios desde cualquier cliente que pueda analizar y tener acceso a los datos que se transmiten mediante los protocolos HTTP estándar.  
  
OData define un conjunto de extensiones para el protocolo de publicación Atom (AtomPub). Es compatible con solicitudes y respuestas HTTP en más de un formato de datos para adaptarse a diversas aplicaciones y plataformas de cliente. Una fuente de OData puede representar datos en Atom, notación de objetos JavaScript (JSON) y como XML sin formato. Aunque Atom es el formato predeterminado, el formato de la fuente se especifica en el encabezado de la solicitud HTTP. Para obtener más información, consulte [OData: formato Atom](https://www.odata.org/documentation/odata-version-2-0/atom-format/) y [ODATA: formato JSON](https://www.odata.org/documentation/odata-version-2-0/json-format/).  
  
 Al publicar datos como una fuente de OData, WCF Data Services se basa en otros servicios de Internet existentes para operaciones como el almacenamiento en caché y la autenticación. Para ello, WCF Data Services se integra con aplicaciones y servicios de hospedaje existentes, como ASP.NET, Windows Communication Foundation (WCF) y Internet Information Services (IIS).  
  
## <a name="storage-independence"></a>Independencia de almacenamiento  
 Aunque los recursos se direccionan basándose en un modelo entidad-relación, WCF Data Services exponer las fuentes de OData independientemente del origen de datos subyacente. Después de que WCF Data Services acepte una solicitud HTTP para un recurso identificado por un URI, se deserializa la solicitud y se pasa una representación de esa solicitud a un proveedor de WCF Data Services. Este proveedor traduce la solicitud en un formato específico del origen de datos y la ejecuta en el origen de datos subyacente. WCF Data Services logra la independencia de almacenamiento separando el modelo conceptual que direcciona los recursos recetados por OData desde el esquema específico del origen de datos subyacente.  
  
 WCF Data Services se integra con el Entity Framework ADO.NET para que pueda crear servicios de datos que exponen datos relacionales. Puede usar las herramientas de Entity Data Model para crear un modelo de datos que contiene recursos direccionables como entidades y al mismo tiempo definir la asignación entre este modelo y las tablas de la base de datos subyacente. Para obtener más información, vea [proveedor de Entity Framework](entity-framework-provider-wcf-data-services.md).  
  
 WCF Data Services también le permite crear servicios de datos que exponen cualquier estructura de datos que devuelva una implementación de la interfaz de <xref:System.Linq.IQueryable%601>. Esto le permite crear servicios de datos que exponen los datos procedentes de tipos de .NET Framework. Si también se implementa la interfaz <xref:System.Data.Services.IUpdatable>, se admiten las operaciones de creación, actualización y eliminación. Para obtener más información, vea [proveedor de reflexión](reflection-provider-wcf-data-services.md).  
  
 Para ver una ilustración de cómo WCF Data Services se integra con estos proveedores de datos, vea el diagrama arquitectónico más adelante en este tema.  
  
## <a name="custom-business-logic"></a>Lógica de negocios personalizada  
 WCF Data Services permite agregar fácilmente lógica de negocios personalizada a un servicio de datos a través de operaciones de servicio e interceptores. Las operaciones de servicio son métodos definidos en el servidor direccionables a través de URI con el mismo formato que los recursos de datos. Las operaciones de servicio también pueden usar la sintaxis de las expresiones de consulta para filtrar, ordenar y paginar los datos devueltos por una operación. Por ejemplo, el URI `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$orderby=OrderDate&$top=10&$skip=10` representa una llamada a una operación de servicio denominada `GetOrdersByCity` en el servicio de datos de Northwind que devuelve los pedidos para los clientes residentes en Londres, con los resultados paginados ordenados por `OrderDate`. Para obtener más información, consulte [operaciones de servicio](service-operations-wcf-data-services.md).  
  
 Los interceptores permiten integrar la lógica de la aplicación personalizada en el procesamiento de los mensajes de solicitud o respuesta de un servicio de datos. Se llama a los interceptores cuando se produce una acción de consulta, inserción, actualización o eliminación en el conjunto de entidades especificado. Un interceptor puede modificar después los datos, aplicar la directiva de autorización o incluso terminar la operación. Los métodos de interceptor se deben registrar explícitamente para un conjunto de entidades determinado expuesto por un servicio de datos. Para obtener más información, vea [interceptores](interceptors-wcf-data-services.md).  
  
## <a name="client-libraries"></a>Bibliotecas de cliente  
 OData define un conjunto de modelos uniformes para interactuar con los servicios de datos. Esto proporciona una oportunidad para crear componentes reutilizables basados en estos servicios, como bibliotecas de cliente que facilitan el consumo de servicios de datos.  
  
 WCF Data Services incluye bibliotecas de cliente para aplicaciones cliente basadas en .NET Framework y en Silverlight. Estas bibliotecas de cliente le permiten interactuar con los servicios de datos mediante objetos de .NET Framework. También admiten consultas basadas en objetos y consultas LINQ, carga de objetos relacionados, seguimiento de cambios y resolución de identidades. Para obtener más información, vea [WCF Data Services biblioteca de cliente](wcf-data-services-client-library.md).  
  
 Además de las bibliotecas de cliente de OData incluidas con el .NET Framework y con Silverlight, hay otras bibliotecas de cliente que le permiten consumir una fuente de OData en aplicaciones cliente, como aplicaciones PHP, AJAX y Java. Para obtener más información sobre el SDK de OData, vea [el SDK de oData: código de ejemplo](https://www.odata.org/ecosystem/#sdk).
  
## <a name="architecture-overview"></a>Información general sobre la arquitectura  
 En el diagrama siguiente se muestra la arquitectura de WCF Data Services para exponer fuentes de OData y usar estas fuentes en bibliotecas de cliente habilitadas para OData:  
  
 ![Captura de pantalla que muestra un diagrama de arquitectura de WCF Data Services.](./media/wcf-data-services-overview/windows-communication-foundation-data-services-architecture.gif)  
  
## <a name="see-also"></a>Vea también

- [Servicios de datos de WCF 4.5](index.md)
- [Introducción](getting-started-with-wcf-data-services.md)
- [Definir Servicios de datos de WCF](defining-wcf-data-services.md)
- [Acceso a los recursos del servicio de datos (WCF Data Services)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd728283(v=vs.100))
- [Biblioteca cliente de Servicios de datos de WCF](wcf-data-services-client-library.md)
- [Transferencia de estado representacional (REST)](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)
