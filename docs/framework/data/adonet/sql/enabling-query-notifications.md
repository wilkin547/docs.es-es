---
title: Habilitar notificaciones de consulta
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: a5333e19-8e55-4aa9-82dc-ca8745e516ed
caps.latest.revision: "6"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c7b02ba7959a5cfc2205222655460026847c3098
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="enabling-query-notifications"></a>Habilitar notificaciones de consulta
Las aplicaciones que consumen notificaciones de consulta poseen un conjunto común de requisitos. El origen de datos se debe configurar correctamente para que admita notificaciones de consulta SQL y el usuario debe contar con los permisos adecuados en el cliente y el servidor.  
  
 Para utilizar notificaciones de consulta, es necesario:  
  
-   Habilitar las notificaciones de consulta en la base de datos.  
  
-   Asegurarse de que el identificador de usuario usado para conectarse a la base de datos dispone de los permisos necesarios.  
  
-   Utilizar un objeto <xref:System.Data.SqlClient.SqlCommand> para ejecutar una instrucción SELECT válida con un objeto de notificación asociado, <xref:System.Data.SqlClient.SqlDependency> o <xref:System.Data.Sql.SqlNotificationRequest>.  
  
-   Proporcionar código para procesar la notificación si los datos que se supervisan cambian.  
  
## <a name="query-notifications-requirements"></a>Requisitos de las notificaciones de consulta  
 Las notificaciones de consulta solo son compatibles con las instrucciones SELECT que cumplen ciertos requisitos específicos. En la tabla siguiente se proporcionan vínculos a la documentación sobre Service Broker y las notificaciones de consulta de los Libros en pantalla de SQL Server.  
  
 **Libros en pantalla de SQL Server**  
  
-   [Crear una consulta de notificación](http://msdn.microsoft.com/library/ms181122.aspx)  
  
-   [Consideraciones de seguridad para Service Broker](http://msdn.microsoft.com/library/ms166059.aspx)  
  
-   [Seguridad y protección (Service Broker)](http://msdn.microsoft.com/library/bb522911.aspx)  
  
-   [Consideraciones de seguridad para Notification Services](http://msdn.microsoft.com/library/ms172604.aspx)  
  
-   [Permisos de notificaciones de consulta](http://msdn.microsoft.com/library/ms188311.aspx)  
  
-   [Consideraciones internacionales para Service Broker](http://msdn.microsoft.com/library/ms166028.aspx)  
  
-   [Consideraciones de diseño de soluciones (Service Broker)](http://msdn.microsoft.com/library/bb522899.aspx)  
  
-   [Centro de información para desarrolladores de Service Broker](http://msdn.microsoft.com/library/ms166100.aspx)  
  
-   [Guía del desarrollador (Service Broker)](http://msdn.microsoft.com/library/bb522908.aspx)  
  
## <a name="enabling-query-notifications-to-run-sample-code"></a>Habilitar las notificaciones de consulta para ejecutar código de ejemplo  
 Para habilitar Service Broker en la **AdventureWorks** base de datos mediante SQL Server Management Studio, ejecute la instrucción de Transact-SQL siguiente:  
  
 `ALTER DATABASE AdventureWorks SET ENABLE_BROKER;`  
  
 Para que el ejemplo de notificación de consulta funcione correctamente, es necesario ejecutar las siguientes instrucciones Transact-SQL en el servidor de bases de datos.  
  
```  
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
 [Notificaciones de consulta en SQL Server](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
