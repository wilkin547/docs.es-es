---
title: Habilitar notificaciones de consulta
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a5333e19-8e55-4aa9-82dc-ca8745e516ed
ms.openlocfilehash: 84048a3fba2b32b1ae745160e2b405c04b738c65
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040229"
---
# <a name="enabling-query-notifications"></a>Habilitar notificaciones de consulta
Las aplicaciones que consumen notificaciones de consulta poseen un conjunto común de requisitos. El origen de datos se debe configurar correctamente para que admita notificaciones de consulta SQL y el usuario debe contar con los permisos adecuados en el cliente y el servidor.  
  
 Para utilizar notificaciones de consulta, es necesario:  
  
- Habilitar las notificaciones de consulta en la base de datos.  
  
- Asegurarse de que el identificador de usuario usado para conectarse a la base de datos dispone de los permisos necesarios.  
  
- Utilizar un objeto <xref:System.Data.SqlClient.SqlCommand> para ejecutar una instrucción SELECT válida con un objeto de notificación asociado, <xref:System.Data.SqlClient.SqlDependency> o <xref:System.Data.Sql.SqlNotificationRequest>.  
  
- Proporcionar código para procesar la notificación si los datos que se supervisan cambian.  
  
## <a name="query-notifications-requirements"></a>Requisitos de las notificaciones de consulta  
 Las notificaciones de consulta solo son compatibles con las instrucciones SELECT que cumplen ciertos requisitos específicos. En la tabla siguiente se proporcionan vínculos a la documentación sobre Service Broker y las notificaciones de consulta de los Libros en pantalla de SQL Server.  
  
 **SQL Server documentación**  
  
- [Crear una consulta para la notificación](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))  
  
- [Consideraciones de seguridad para Service Broker](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms166059(v=sql.90))  
  
- [Seguridad y protección (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522911(v=sql.105))  
  
- [Consideraciones de seguridad para los servicios de notificaciones](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms172604(v=sql.90))  
  
- [Permisos de notificación de consulta](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms188311(v=sql.105))  
  
- [Consideraciones internacionales para Service Broker](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms166028(v=sql.90))  
  
- [Consideraciones sobre el diseño de soluciones (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522899(v=sql.105))  
  
- [InfoCenter para desarrolladores de Service Broker](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))  
  
- [Guía del desarrollador (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))  
  
## <a name="enabling-query-notifications-to-run-sample-code"></a>Habilitar las notificaciones de consulta para ejecutar código de ejemplo  
 Para habilitar Service Broker en la base de datos **AdventureWorks** mediante SQL Server Management Studio, ejecute la siguiente instrucción TRANSACT-SQL:  
  
 `ALTER DATABASE AdventureWorks SET ENABLE_BROKER;`  
  
 Para que el ejemplo de notificación de consulta funcione correctamente, es necesario ejecutar las siguientes instrucciones Transact-SQL en el servidor de bases de datos.  
  
```sql
CREATE QUEUE ContactChangeMessages;  
  
CREATE SERVICE ContactChangeNotifications  
  ON QUEUE ContactChangeMessages  
([http://schemas.microsoft.com/SQL/Notifications/PostQueryNotification]);  
```  
  
## <a name="query-notifications-permissions"></a>Permisos de notificaciones de consulta  
 Los usuarios que ejecutan comandos solicitando notificaciones deben disponer del permiso de base de datos SUBSCRIBE QUERY NOTIFICATIONS en el servidor.  
  
 El código de cliente que se ejecuta en una situación de confianza parcial necesita el <xref:System.Data.SqlClient.SqlClientPermission>.  
  
 El código siguiente crea un objeto <xref:System.Data.SqlClient.SqlClientPermission>, estableciendo <xref:System.Security.Permissions.PermissionState> en <xref:System.Security.Permissions.PermissionState.Unrestricted>. <xref:System.Security.CodeAccessPermission.Demand%2A> fuerza <xref:System.Security.SecurityException> en tiempo de ejecución si todos los llamadores situados en la parte superior de la pila de llamadas no disponen del permiso.  
  
 [!code-csharp[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/CS/source.cs#1)]
 [!code-vb[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/VB/source.vb#1)]  
  
## <a name="choosing-a-notification-object"></a>Elección de un objeto de notificación  
 La API de notificaciones de consulta proporciona dos objetos para procesar las notificaciones: <xref:System.Data.SqlClient.SqlDependency> y <xref:System.Data.Sql.SqlNotificationRequest>. En general, la mayoría de las aplicaciones que no son ASP.NET deben utilizar el objeto <xref:System.Data.SqlClient.SqlDependency>. Las aplicaciones ASP.NET deben utilizar la <xref:System.Web.Caching.SqlCacheDependency> de nivel más alto, que abarca <xref:System.Data.SqlClient.SqlDependency> y proporciona un marco para administrar los objetos de notificación y de caché.  
  
### <a name="using-sqldependency"></a>Utilizar SqlDependency  
 Para utilizar <xref:System.Data.SqlClient.SqlDependency>, debe estar habilitado Service Broker en la base de datos de SQL Server que se vaya a usar y los usuarios deben tener permisos para recibir notificaciones. Los objetos de Service Broker, como la cola de notificaciones, están predefinidos.  
  
 Además, <xref:System.Data.SqlClient.SqlDependency> inicia automáticamente un subproceso de trabajo para procesar las notificaciones que se publican en la cola; también analiza el mensaje de Service Broker y expone la información en forma de datos de argumento de evento. Para inicializar <xref:System.Data.SqlClient.SqlDependency>, es necesario llamar al método `Start` con el fin de establecer una dependencia con la base de datos. Se trata de un método estático que solo es necesario llamar una vez durante la inicialización de la aplicación en cada conexión a la base de datos necesaria. Se debe llamar al método `Stop` después de terminar la aplicación para cada conexión de dependencia que se haga.  
  
### <a name="using-sqlnotificationrequest"></a>Utilizar SqlNotificationRequest  
 Por el contrario, <xref:System.Data.Sql.SqlNotificationRequest> exige que implemente usted mismo toda la infraestructura de escucha. Además, es necesario definir todos los objetos de Service Broker compatibles, como la cola, los servicios y los tipos de mensajes que admite la cola. Este enfoque manual resulta de utilidad si la aplicación necesita mensajes o comportamientos de notificación especiales, o si la aplicación forma parte de una aplicación de Service Broker más grande.  
  
## <a name="see-also"></a>Vea también

- [Notificaciones de consulta en SQL Server](query-notifications-in-sql-server.md)
- [Información general sobre ADO.NET](../ado-net-overview.md)
