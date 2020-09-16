---
title: Habilitar notificaciones de consulta
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a5333e19-8e55-4aa9-82dc-ca8745e516ed
ms.openlocfilehash: 693e67b4d369eb69b8e0a9dded6decb2d3928459
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554884"
---
# <a name="enabling-query-notifications"></a><span data-ttu-id="320d6-102">Habilitar notificaciones de consulta</span><span class="sxs-lookup"><span data-stu-id="320d6-102">Enabling Query Notifications</span></span>
<span data-ttu-id="320d6-103">Las aplicaciones que consumen notificaciones de consulta tienen un conjunto común de requisitos.</span><span class="sxs-lookup"><span data-stu-id="320d6-103">Applications that consume query notifications have a common set of requirements.</span></span> <span data-ttu-id="320d6-104">El origen de datos se debe configurar correctamente para que admita notificaciones de consulta SQL y el usuario debe contar con los permisos adecuados en el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="320d6-104">Your data source must be correctly configured to support SQL query notifications, and the user must have the correct client-side and server-side permissions.</span></span>  
  
 <span data-ttu-id="320d6-105">Para usar notificaciones de consulta, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="320d6-105">To use query notifications you must:</span></span>  
  
- <span data-ttu-id="320d6-106">Habilitar las notificaciones de consulta para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="320d6-106">Enable query notifications for your database.</span></span>  
  
- <span data-ttu-id="320d6-107">Asegurarse de que el identificador de usuario usado para conectarse a la base de datos tiene los permisos necesarios.</span><span class="sxs-lookup"><span data-stu-id="320d6-107">Ensure that the user ID used to connect to the database has the necessary permissions.</span></span>  
  
- <span data-ttu-id="320d6-108">Usar un objeto <xref:System.Data.SqlClient.SqlCommand> para ejecutar una instrucción SELECT válida con un objeto de notificación asociado, ya sea <xref:System.Data.SqlClient.SqlDependency> o <xref:System.Data.Sql.SqlNotificationRequest>.</span><span class="sxs-lookup"><span data-stu-id="320d6-108">Use a <xref:System.Data.SqlClient.SqlCommand> object to execute a valid SELECT statement with an associated notification object—either <xref:System.Data.SqlClient.SqlDependency> or <xref:System.Data.Sql.SqlNotificationRequest>.</span></span>  
  
- <span data-ttu-id="320d6-109">Proporcionar código para procesar la notificación si los datos que se supervisan cambian.</span><span class="sxs-lookup"><span data-stu-id="320d6-109">Provide code to process the notification if the data being monitored changes.</span></span>  
  
## <a name="query-notifications-requirements"></a><span data-ttu-id="320d6-110">Requisitos de las notificaciones de consulta</span><span class="sxs-lookup"><span data-stu-id="320d6-110">Query Notifications Requirements</span></span>  
 <span data-ttu-id="320d6-111">Se admiten notificaciones de consultas solo para las instrucciones SELECT que cumplan un listado de requisitos específicos.</span><span class="sxs-lookup"><span data-stu-id="320d6-111">Query notifications are supported only for SELECT statements that meet a list of specific requirements.</span></span> <span data-ttu-id="320d6-112">En la tabla siguiente se proporcionan vínculos a la documentación de Service Broker y las notificaciones de consulta en Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="320d6-112">The following table provides links to the Service Broker and Query Notifications documentation in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="320d6-113">**Documentación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="320d6-113">**SQL Server documentation**</span></span>  
  
- <span data-ttu-id="320d6-114">[Crear una consulta de notificación](/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="320d6-114">[Creating a Query for Notification](/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))</span></span>  
  
- <span data-ttu-id="320d6-115">[Consideraciones de seguridad de Service Broker](/previous-versions/sql/sql-server-2005/ms166059(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="320d6-115">[Security Considerations for Service Broker](/previous-versions/sql/sql-server-2005/ms166059(v=sql.90))</span></span>  
  
- <span data-ttu-id="320d6-116">[Seguridad y protección (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522911(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="320d6-116">[Security and Protection (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522911(v=sql.105))</span></span>  
  
- <span data-ttu-id="320d6-117">[Consideraciones de seguridad de Notification Services](/previous-versions/sql/sql-server-2005/ms172604(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="320d6-117">[Security Considerations for Notifications Services](/previous-versions/sql/sql-server-2005/ms172604(v=sql.90))</span></span>  
  
- <span data-ttu-id="320d6-118">[Permisos de notificación de consulta](/previous-versions/sql/sql-server-2008-r2/ms188311(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="320d6-118">[Query Notification Permissions](/previous-versions/sql/sql-server-2008-r2/ms188311(v=sql.105))</span></span>  
  
- <span data-ttu-id="320d6-119">[Consideraciones internacionales de Service Broker](/previous-versions/sql/sql-server-2005/ms166028(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="320d6-119">[International Considerations for Service Broker](/previous-versions/sql/sql-server-2005/ms166028(v=sql.90))</span></span>  
  
- <span data-ttu-id="320d6-120">[Consideraciones de diseño de soluciones (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522899(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="320d6-120">[Solution Design Considerations (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522899(v=sql.105))</span></span>  
  
- <span data-ttu-id="320d6-121">[Centro de información del desarrollador de Service Broker](/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="320d6-121">[Service Broker Developer InfoCenter](/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))</span></span>  
  
- <span data-ttu-id="320d6-122">[Guía del desarrollador (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="320d6-122">[Developer's Guide (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))</span></span>  
  
## <a name="enabling-query-notifications-to-run-sample-code"></a><span data-ttu-id="320d6-123">Habilitar las notificaciones de consulta para ejecutar código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="320d6-123">Enabling Query Notifications to Run Sample Code</span></span>  
 <span data-ttu-id="320d6-124">Para habilitar Service Broker en la base de datos **AdventureWorks** mediante SQL Server Management Studio, ejecute la siguiente instrucción de Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="320d6-124">To enable Service Broker on the **AdventureWorks** database by using SQL Server Management Studio, execute the following Transact-SQL statement:</span></span>  
  
 `ALTER DATABASE AdventureWorks SET ENABLE_BROKER;`  
  
 <span data-ttu-id="320d6-125">Para que los ejemplos de notificaciones de consulta se ejecuten correctamente, se deben ejecutar las siguientes instrucciones Transact-SQL en el servidor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="320d6-125">For the query notification samples to run correctly, the following Transact-SQL statements must be executed on the database server.</span></span>  
  
```sql
CREATE QUEUE ContactChangeMessages;  
  
CREATE SERVICE ContactChangeNotifications  
  ON QUEUE ContactChangeMessages  
([http://schemas.microsoft.com/SQL/Notifications/PostQueryNotification]);  
```  
  
## <a name="query-notifications-permissions"></a><span data-ttu-id="320d6-126">Permisos de notificaciones de consulta</span><span class="sxs-lookup"><span data-stu-id="320d6-126">Query Notifications Permissions</span></span>  
 <span data-ttu-id="320d6-127">Los usuarios que ejecutan comandos que solicitan una notificación deben tener el permiso de base de datos SUBSCRIBE QUERY NOTIFICATIONS en el servidor.</span><span class="sxs-lookup"><span data-stu-id="320d6-127">Users who execute commands requesting notification must have SUBSCRIBE QUERY NOTIFICATIONS database permission on the server.</span></span>  
  
 <span data-ttu-id="320d6-128">El código del lado cliente que se ejecuta en una situación de confianza parcial requiere <xref:System.Data.SqlClient.SqlClientPermission>.</span><span class="sxs-lookup"><span data-stu-id="320d6-128">Client-side code that runs in a partial trust situation requires the <xref:System.Data.SqlClient.SqlClientPermission>.</span></span>  
  
 <span data-ttu-id="320d6-129">El código siguiente crea un objeto <xref:System.Data.SqlClient.SqlClientPermission>, estableciendo <xref:System.Security.Permissions.PermissionState> en <xref:System.Security.Permissions.PermissionState.Unrestricted>.</span><span class="sxs-lookup"><span data-stu-id="320d6-129">The following code creates a <xref:System.Data.SqlClient.SqlClientPermission> object, setting the <xref:System.Security.Permissions.PermissionState> to <xref:System.Security.Permissions.PermissionState.Unrestricted>.</span></span> <span data-ttu-id="320d6-130"><xref:System.Security.CodeAccessPermission.Demand%2A> forzará a <xref:System.Security.SecurityException> en un entorno de ejecución si todos los autores de llamada situados en la parte superior de la pila de llamadas no disponen del permiso.</span><span class="sxs-lookup"><span data-stu-id="320d6-130">The <xref:System.Security.CodeAccessPermission.Demand%2A> will force a <xref:System.Security.SecurityException> at run time if all callers higher in the call stack have not been granted the permission.</span></span>  
  
 [!code-csharp[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/CS/source.cs#1)]
 [!code-vb[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/VB/source.vb#1)]  
  
## <a name="choosing-a-notification-object"></a><span data-ttu-id="320d6-131">Elección de un objeto de notificación</span><span class="sxs-lookup"><span data-stu-id="320d6-131">Choosing a Notification Object</span></span>  
 <span data-ttu-id="320d6-132">La API de notificaciones de consulta proporciona dos objetos para procesar notificaciones: <xref:System.Data.SqlClient.SqlDependency> y <xref:System.Data.Sql.SqlNotificationRequest>.</span><span class="sxs-lookup"><span data-stu-id="320d6-132">The query notifications API provides two objects to process notifications: <xref:System.Data.SqlClient.SqlDependency> and <xref:System.Data.Sql.SqlNotificationRequest>.</span></span> <span data-ttu-id="320d6-133">En general, la mayoría de las aplicaciones que no son ASP.NET deben utilizar el objeto <xref:System.Data.SqlClient.SqlDependency>.</span><span class="sxs-lookup"><span data-stu-id="320d6-133">In general, most non-ASP.NET applications should use the <xref:System.Data.SqlClient.SqlDependency> object.</span></span> <span data-ttu-id="320d6-134">Las aplicaciones ASP.NET deben utilizar la <xref:System.Web.Caching.SqlCacheDependency> de nivel más alto, que abarca <xref:System.Data.SqlClient.SqlDependency> y proporciona un marco para administrar los objetos de notificación y de caché.</span><span class="sxs-lookup"><span data-stu-id="320d6-134">ASP.NET applications should use the higher-level <xref:System.Web.Caching.SqlCacheDependency>, which wraps <xref:System.Data.SqlClient.SqlDependency> and provides a framework for administering the notification and cache objects.</span></span>  
  
### <a name="using-sqldependency"></a><span data-ttu-id="320d6-135">Uso de SqlDependency</span><span class="sxs-lookup"><span data-stu-id="320d6-135">Using SqlDependency</span></span>  
 <span data-ttu-id="320d6-136">Para usar <xref:System.Data.SqlClient.SqlDependency>, Service Broker debe estar habilitado en la base de datos de SQL Server que se vaya a usar y los usuarios deben tener permisos para recibir notificaciones.</span><span class="sxs-lookup"><span data-stu-id="320d6-136">To use <xref:System.Data.SqlClient.SqlDependency>, Service Broker must be enabled for the SQL Server database being used, and users must have permissions to receive notifications.</span></span> <span data-ttu-id="320d6-137">Los objetos de Service Broker, como la cola de notificación, están predefinidos.</span><span class="sxs-lookup"><span data-stu-id="320d6-137">Service Broker objects, such as the notification queue, are predefined.</span></span>  
  
 <span data-ttu-id="320d6-138">Además, <xref:System.Data.SqlClient.SqlDependency> inicia automáticamente un subproceso de trabajo para procesar las notificaciones que se publican en la cola; también analiza el mensaje de Service Broker y expone la información en forma de datos de argumento de evento.</span><span class="sxs-lookup"><span data-stu-id="320d6-138">In addition, <xref:System.Data.SqlClient.SqlDependency> automatically launches a worker thread to process notifications as they are posted to the queue; it also parses the Service Broker message, exposing the information as event argument data.</span></span> <span data-ttu-id="320d6-139"><xref:System.Data.SqlClient.SqlDependency> se debe inicializar llamando al método `Start` para establecer una dependencia en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="320d6-139"><xref:System.Data.SqlClient.SqlDependency> must be initialized by calling the `Start` method to establish a dependency to the database.</span></span> <span data-ttu-id="320d6-140">Se trata de un método estático al que es necesario llamar solo una vez durante la inicialización de la aplicación para cada conexión de base de datos necesaria.</span><span class="sxs-lookup"><span data-stu-id="320d6-140">This is a static method that needs to be called only once during application initialization for each database connection required.</span></span> <span data-ttu-id="320d6-141">Se debe llamar al método `Stop` en la finalización de la aplicación para cada conexión de dependencia realizada.</span><span class="sxs-lookup"><span data-stu-id="320d6-141">The `Stop` method should be called at application termination for each dependency connection that was made.</span></span>  
  
### <a name="using-sqlnotificationrequest"></a><span data-ttu-id="320d6-142">Uso de SqlNotificationRequest</span><span class="sxs-lookup"><span data-stu-id="320d6-142">Using SqlNotificationRequest</span></span>  
 <span data-ttu-id="320d6-143">Por el contrario, <xref:System.Data.Sql.SqlNotificationRequest> requiere que implemente toda la infraestructura de escucha.</span><span class="sxs-lookup"><span data-stu-id="320d6-143">In contrast, <xref:System.Data.Sql.SqlNotificationRequest> requires you to implement the entire listening infrastructure yourself.</span></span> <span data-ttu-id="320d6-144">Además, se deben definir todos los objetos de Service Broker de compatibilidad, como la cola, el servicio y los tipos de mensajes admitidos por la cola.</span><span class="sxs-lookup"><span data-stu-id="320d6-144">In addition, all the supporting Service Broker objects such as the queue, service, and message types supported by the queue must be defined.</span></span> <span data-ttu-id="320d6-145">Este enfoque manual es útil si la aplicación requiere mensajes de notificación o comportamientos de notificación especiales, o si la aplicación forma parte de una aplicación Service Broker mayor.</span><span class="sxs-lookup"><span data-stu-id="320d6-145">This manual approach is useful if your application requires special notification messages or notification behaviors, or if your application is part of a larger Service Broker application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="320d6-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="320d6-146">See also</span></span>

- [<span data-ttu-id="320d6-147">Notificaciones de consulta en SQL Server</span><span class="sxs-lookup"><span data-stu-id="320d6-147">Query Notifications in SQL Server</span></span>](query-notifications-in-sql-server.md)
- [<span data-ttu-id="320d6-148">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="320d6-148">ADO.NET Overview</span></span>](../ado-net-overview.md)
