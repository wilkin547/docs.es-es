---
title: Notificaciones de consulta en SQL Server
ms.date: 03/30/2017
ms.assetid: 0f0ba1a1-3180-4af8-87f7-c795dc8f8f55
ms.openlocfilehash: 11d9a1a800bea4224853a57b128ca89c9f2cf781
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452375"
---
# <a name="query-notifications-in-sql-server"></a>Notificaciones de consulta en SQL Server
Las notificaciones de consulta, creadas a partir de la infraestructura de Service Broker, permiten notificar a las aplicaciones si los datos han cambiado. Esta característica resulta especialmente útil para las aplicaciones que proporcionan una caché de información de una base de datos, como una aplicación web, y necesitan recibir notificaciones si se modifican los datos de origen.  
  
 Existen tres maneras de implementar las notificaciones de consulta mediante ADO.NET:  
  
1. La implementación de nivel inferior la proporciona la clase `SqlNotificationRequest`, que presenta funciones de servidor, lo que permite ejecutar un comando con una solicitud de notificación.  
  
2. La implementación de nivel superior la proporciona la clase `SqlDependency`, que ofrece un alto nivel de abstracción de la funcionalidad de notificación entre la aplicación de origen y SQL Server, lo que permite utilizar una dependencia para detectar cambios en el servidor. En la mayoría de los casos, ésta es la manera más sencilla y eficaz de aprovechar la funcionalidad de notificaciones de SQL Server 2005 por parte de aplicaciones cliente administradas que utilizan el proveedor de datos .NET Framework para SQL Server.  
  
3. Además, las aplicaciones web creadas mediante ASP.NET 2.0 o posterior pueden usar las clases auxiliares `SqlCacheDependency`.  
  
 Las notificaciones de consulta son útiles en aquellas aplicaciones que necesitan actualizar presentaciones o cachés como respuesta a los cambios en los datos subyacentes. Microsoft SQL Server 2005 permite que las aplicaciones .NET Framework envíen un comando a SQL Server y soliciten una notificación si la ejecución del mismo comando produjera conjuntos de resultados diferentes de los inicialmente recuperados. Las notificaciones generadas en el servidor se envían a través de colas para procesarse más adelante.  
  
 Puede definir notificaciones para las instrucciones SELECT y EXECUTE. Al utilizar una instrucción EXECUTE, SQL Server registra una notificación para el comando ejecutado en lugar de la propia instrucción EXECUTE. El comando debe cumplir los requisitos y las limitaciones de una instrucción SELECT. Cuando un comando que registra una notificación contiene más de una instrucción, el motor de base de datos crea una notificación para cada instrucción del lote.  
  
 Si está desarrollando una aplicación que necesite las notificaciones de subsegundo confiables cuando cambian los datos, revise las secciones **planear una estrategia eficaz de notificaciones de consulta** y **alternativas a las notificaciones de consulta** en el artículo [planear notificaciones](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms187528(v=sql.105)). Para obtener más información acerca de las notificaciones de consulta y SQL Server Service Broker, consulte los siguientes vínculos a los artículos de la documentación de SQL Server.  
  
 **Documentación de SQL Server**  
  
- [Usar notificaciones de consulta](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms175110(v=sql.105))  
  
- [Crear una consulta de notificación](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))  
  
- [Desarrollo (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522889(v=sql.105))  
  
- [Centro de información del desarrollador de Service Broker](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))  
  
- [Guía del desarrollador (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))  
  
## <a name="in-this-section"></a>En esta sección  
 [Habilitación de notificaciones de consulta](enabling-query-notifications.md)  
 Describe cómo utilizar las notificaciones de consulta, junto con los requisitos para habilitarlas y usarlas.  
  
 [SqlDependency en una aplicación ASP.NET](sqldependency-in-an-aspnet-app.md)  
 Muestra cómo usar notificaciones de consulta desde una aplicación ASP.NET.  
  
 [Detección de cambios con SqlDependency](detecting-changes-with-sqldependency.md)  
 Muestra cómo detectar cuándo los resultados de las consultas serán diferentes de los recibidos originalmente.  
  
 [Ejecución de SqlCommand con SqlNotificationRequest](sqlcommand-execution-with-a-sqlnotificationrequest.md)  
 Muestra cómo configurar un objeto <xref:System.Data.SqlClient.SqlCommand> para trabajar con una notificación de consulta.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Data.Sql.SqlNotificationRequest>  
 Describe la clase <xref:System.Data.Sql.SqlNotificationRequest>, así como todos sus miembros.  
  
 <xref:System.Data.SqlClient.SqlDependency>  
 Describe la clase <xref:System.Data.SqlClient.SqlDependency>, así como todos sus miembros.  
  
 <xref:System.Web.Caching.SqlCacheDependency>  
 Describe la clase <xref:System.Web.Caching.SqlCacheDependency>, así como todos sus miembros.  
  
## <a name="see-also"></a>Consulte también

- [SQL Server y ADO.NET](index.md)
- [Información general sobre ADO.NET](../ado-net-overview.md)
