---
title: Notificaciones de consulta en SQL Server
description: Obtenga información acerca de cómo usar notificaciones de consulta para notificar a las aplicaciones Cuándo han cambiado los datos en una base de datos SQL Server, por ejemplo, para actualizar las pantallas de la aplicación.
ms.date: 03/30/2017
ms.assetid: 0f0ba1a1-3180-4af8-87f7-c795dc8f8f55
ms.openlocfilehash: 8001f75d7e278a965b6e8e00e4b9af7b770a8bb5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183096"
---
# <a name="query-notifications-in-sql-server"></a>Notificaciones de consulta en SQL Server

Las notificaciones de consulta, creadas a partir de la infraestructura de Service Broker, permiten notificar a las aplicaciones si los datos han cambiado. Esta característica resulta especialmente útil para las aplicaciones que proporcionan una caché de información de una base de datos, como una aplicación web, y necesitan recibir notificaciones si se modifican los datos de origen.  
  
 Hay tres maneras de implementar notificaciones de consulta mediante ADO.NET:  
  
1. La implementación de bajo nivel se proporciona mediante la clase `SqlNotificationRequest` que expone la funcionalidad del servidor, lo que permite ejecutar un comando con una solicitud de notificación.  
  
2. La implementación de alto nivel se proporciona mediante la clase `SqlDependency`, que es una clase que proporciona una abstracción de alto nivel de la funcionalidad de notificación entre la aplicación de origen y SQL Server, lo que permite utilizar una dependencia para detectar los cambios en el servidor. En la mayoría de los casos, ésta es la manera más sencilla y eficaz de aprovechar la funcionalidad de notificaciones de SQL Server 2005 por parte de aplicaciones cliente administradas que utilizan el proveedor de datos .NET Framework para SQL Server.  
  
3. Además, las aplicaciones web creadas mediante ASP.NET 2.0 o posterior pueden usar las clases auxiliares `SqlCacheDependency`.  
  
 Las notificaciones de consulta se usan para las aplicaciones que necesitan actualizar las visualizaciones o las almacena en caché en respuesta a los cambios en los datos subyacentes. Microsoft SQL Server 2005 permite que las aplicaciones .NET Framework envíen un comando a SQL Server y soliciten una notificación si la ejecución del mismo comando produjera conjuntos de resultados diferentes de los inicialmente recuperados. Las notificaciones generadas en el servidor se envían a través de colas para procesarse más adelante.  
  
 Puede configurar notificaciones para las instrucciones SELECT y EXECUTE. Cuando se usa una instrucción EXECUTE, SQL Server registra una notificación para el comando ejecutado en lugar de la propia instrucción EXECUTE. El comando debe cumplir los requisitos y las limitaciones de una instrucción SELECT. Cuando un comando que registra una notificación contiene más de una instrucción, el motor de base de datos crea una notificación para cada instrucción del lote.  
  
 Si está desarrollando una aplicación que necesite las notificaciones de subsegundo confiables cuando cambian los datos, revise las secciones **planear una estrategia eficaz de notificaciones de consulta** y **alternativas a las notificaciones de consulta** en el artículo [planear notificaciones](/previous-versions/sql/sql-server-2008-r2/ms187528(v=sql.105)). Para obtener más información acerca de las notificaciones de consulta y SQL Server Service Broker, consulte los siguientes vínculos a los artículos de la documentación de SQL Server.  
  
 **Documentación de SQL Server**  
  
- [Usar notificaciones de consulta](/previous-versions/sql/sql-server-2008-r2/ms175110(v=sql.105))  
  
- [Crear una consulta de notificación](/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))  
  
- [Desarrollo (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522889(v=sql.105))  
  
- [Centro de información del desarrollador de Service Broker](/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))  
  
- [Guía del desarrollador (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))  
  
## <a name="in-this-section"></a>En esta sección  

 [Habilitación de notificaciones de consulta](enabling-query-notifications.md)  
 Describe cómo usar las notificaciones de consulta, incluidos los requisitos para habilitarlas y usarlas.  
  
 [SqlDependency en una aplicación ASP.NET](sqldependency-in-an-aspnet-app.md)  
 Muestra cómo usar notificaciones de consulta desde una aplicación de ASP.NET.  
  
 [Detección de cambios con SqlDependency](detecting-changes-with-sqldependency.md)  
 Muestra cómo detectar cuándo los resultados de la consulta serán distintos de los recibidos originalmente.  
  
 [Ejecución de SqlCommand con un SqlNotificationRequest](sqlcommand-execution-with-a-sqlnotificationrequest.md)  
 Muestra cómo configurar un objeto <xref:System.Data.SqlClient.SqlCommand> para que funcione con una notificación de consulta.  
  
## <a name="reference"></a>Referencia  

 <xref:System.Data.Sql.SqlNotificationRequest>  
 Describe la clase <xref:System.Data.Sql.SqlNotificationRequest> y todos sus miembros.  
  
 <xref:System.Data.SqlClient.SqlDependency>  
 Describe la clase <xref:System.Data.SqlClient.SqlDependency> y todos sus miembros.  
  
 <xref:System.Web.Caching.SqlCacheDependency>  
 Describe la clase <xref:System.Web.Caching.SqlCacheDependency> y todos sus miembros.  
  
## <a name="see-also"></a>Consulte también

- [SQL Server y ADO.NET](index.md)
- [Información general de ADO.NET](../ado-net-overview.md)
