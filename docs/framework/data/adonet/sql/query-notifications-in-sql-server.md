---
title: Notificaciones de consulta en SQL Server
ms.date: 03/30/2017
ms.assetid: 0f0ba1a1-3180-4af8-87f7-c795dc8f8f55
ms.openlocfilehash: 166471658ccd1ef48db2ac1647f74ea696f3263d
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2019
ms.locfileid: "56092298"
---
# <a name="query-notifications-in-sql-server"></a>Notificaciones de consulta en SQL Server
Las notificaciones de consulta, que están basadas en la infraestructura Service Broker, permiten que se notifique a las aplicaciones cuando cambian los datos. Esta característica es especialmente útil en aplicaciones que proporcionan una caché de información desde una base de datos, por ejemplo, una aplicación web, y necesitan recibir notificación cuando cambian los datos de origen.  
  
 Existen tres maneras de implementar las notificaciones de consulta mediante ADO.NET:  
  
1.  La implementación de nivel inferior la proporciona la clase `SqlNotificationRequest`, que presenta funciones de servidor, lo que permite ejecutar un comando con una solicitud de notificación.  
  
2.  La implementación de nivel superior la proporciona la clase `SqlDependency`, que ofrece un alto nivel de abstracción de la funcionalidad de notificación entre la aplicación de origen y SQL Server, lo que permite utilizar una dependencia para detectar cambios en el servidor. En la mayoría de los casos, ésta es la manera más sencilla y eficaz de aprovechar la funcionalidad de notificaciones de SQL Server 2005 por parte de aplicaciones cliente administradas que utilizan el proveedor de datos .NET Framework para SQL Server.  
  
3.  Además, las aplicaciones web compiladas mediante ASP.NET 2.0 o posterior pueden utilizar las clases auxiliares `SqlCacheDependency`.  
  
 Las notificaciones de consulta son útiles en aquellas aplicaciones que necesitan actualizar presentaciones o cachés como respuesta a los cambios en los datos subyacentes. Microsoft SQL Server 2005 permite que las aplicaciones .NET Framework envíen un comando a SQL Server y soliciten una notificación si la ejecución del mismo comando produjera conjuntos de resultados diferentes de los inicialmente recuperados. Las notificaciones generadas en el servidor se envían a través de colas para procesarlas más adelante.  
  
 Puede definir notificaciones para las instrucciones SELECT y EXECUTE. Al utilizar una instrucción EXECUTE, SQL Server registra una notificación para el comando ejecutado en lugar de la propia instrucción EXECUTE. El comando debe cumplir los requisitos y limitaciones de una instrucción SELECT. Si un comando que registra una notificación contiene más de una instrucción, el motor de base de datos crea una notificación para cada instrucción del lote.  
  
 Si está desarrollando una aplicación que necesite las notificaciones de subsegundo confiables cuando cambian los datos, revise las secciones **planear una estrategia eficaz de notificaciones de consulta** y **alternativas a la consulta Las notificaciones** en el [planear notificaciones](https://go.microsoft.com/fwlink/?LinkId=211984) tema en libros en pantalla de SQL Server. Para obtener más información acerca de las notificaciones de consulta y SQL Server Service Broker, vea los siguientes vínculos a temas de los Libros en pantalla de SQL Server.  
  
 **Documentación de SQL Server**  
  
-   [Usar notificaciones de consulta](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms175110(v=sql.105))  
  
-   [Crear una consulta de notificación](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))  
  
-   [Desarrollo (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522889(v=sql.105))  
  
-   [InfoCenter para desarrolladores de Service Broker](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))  
  
-   [Guía del desarrollador (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))  
  
## <a name="in-this-section"></a>En esta sección  
 [Habilitación de notificaciones de consulta](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md)  
 Describe cómo utilizar las notificaciones de consulta, junto con los requisitos para habilitarlas y usarlas.  
  
 [SqlDependency en una aplicación ASP.NET](../../../../../docs/framework/data/adonet/sql/sqldependency-in-an-aspnet-app.md)  
 Muestra cómo usar notificaciones de consulta desde una aplicación ASP.NET.  
  
 [Detección de cambios con SqlDependency](../../../../../docs/framework/data/adonet/sql/detecting-changes-with-sqldependency.md)  
 Muestra cómo detectar cuándo los resultados de las consultas serán diferentes de los recibidos originalmente.  
  
 [Ejecución de SqlCommand con SqlNotificationRequest](../../../../../docs/framework/data/adonet/sql/sqlcommand-execution-with-a-sqlnotificationrequest.md)  
 Muestra cómo configurar un objeto <xref:System.Data.SqlClient.SqlCommand> para trabajar con una notificación de consulta.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Data.Sql.SqlNotificationRequest>  
 Describe la clase <xref:System.Data.Sql.SqlNotificationRequest>, así como todos sus miembros.  
  
 <xref:System.Data.SqlClient.SqlDependency>  
 Describe la clase <xref:System.Data.SqlClient.SqlDependency>, así como todos sus miembros.  
  
 <xref:System.Web.Caching.SqlCacheDependency>  
 Describe la clase <xref:System.Web.Caching.SqlCacheDependency>, así como todos sus miembros.  
  
## <a name="see-also"></a>Vea también
- [SQL Server y ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
