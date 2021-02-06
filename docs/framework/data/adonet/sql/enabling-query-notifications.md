---
description: Más información acerca de cómo habilitar notificaciones de consulta
title: Habilitar notificaciones de consulta
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a5333e19-8e55-4aa9-82dc-ca8745e516ed
ms.openlocfilehash: e0ff405477a9faa141ce81c5ac8ba2d1ace95501
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99663344"
---
# <a name="enabling-query-notifications"></a><span data-ttu-id="87dce-103">Habilitar notificaciones de consulta</span><span class="sxs-lookup"><span data-stu-id="87dce-103">Enabling Query Notifications</span></span>

<span data-ttu-id="87dce-104">Las aplicaciones que consumen notificaciones de consulta tienen un conjunto común de requisitos.</span><span class="sxs-lookup"><span data-stu-id="87dce-104">Applications that consume query notifications have a common set of requirements.</span></span> <span data-ttu-id="87dce-105">El origen de datos se debe configurar correctamente para que admita notificaciones de consulta SQL y el usuario debe contar con los permisos adecuados en el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="87dce-105">Your data source must be correctly configured to support SQL query notifications, and the user must have the correct client-side and server-side permissions.</span></span>  
  
 <span data-ttu-id="87dce-106">Para usar notificaciones de consulta, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="87dce-106">To use query notifications you must:</span></span>  
  
- <span data-ttu-id="87dce-107">Habilitar las notificaciones de consulta para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="87dce-107">Enable query notifications for your database.</span></span>  
  
- <span data-ttu-id="87dce-108">Asegurarse de que el identificador de usuario usado para conectarse a la base de datos tiene los permisos necesarios.</span><span class="sxs-lookup"><span data-stu-id="87dce-108">Ensure that the user ID used to connect to the database has the necessary permissions.</span></span>  
  
- <span data-ttu-id="87dce-109">Usar un objeto <xref:System.Data.SqlClient.SqlCommand> para ejecutar una instrucción SELECT válida con un objeto de notificación asociado, ya sea <xref:System.Data.SqlClient.SqlDependency> o <xref:System.Data.Sql.SqlNotificationRequest>.</span><span class="sxs-lookup"><span data-stu-id="87dce-109">Use a <xref:System.Data.SqlClient.SqlCommand> object to execute a valid SELECT statement with an associated notification object—either <xref:System.Data.SqlClient.SqlDependency> or <xref:System.Data.Sql.SqlNotificationRequest>.</span></span>  
  
- <span data-ttu-id="87dce-110">Proporcionar código para procesar la notificación si los datos que se supervisan cambian.</span><span class="sxs-lookup"><span data-stu-id="87dce-110">Provide code to process the notification if the data being monitored changes.</span></span>  
  
## <a name="query-notifications-requirements"></a><span data-ttu-id="87dce-111">Requisitos de las notificaciones de consulta</span><span class="sxs-lookup"><span data-stu-id="87dce-111">Query Notifications Requirements</span></span>  

 <span data-ttu-id="87dce-112">Se admiten notificaciones de consultas solo para las instrucciones SELECT que cumplan un listado de requisitos específicos.</span><span class="sxs-lookup"><span data-stu-id="87dce-112">Query notifications are supported only for SELECT statements that meet a list of specific requirements.</span></span> <span data-ttu-id="87dce-113">En la tabla siguiente se proporcionan vínculos a la documentación de Service Broker y las notificaciones de consulta en Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="87dce-113">The following table provides links to the Service Broker and Query Notifications documentation in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="87dce-114">**Documentación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="87dce-114">**SQL Server documentation**</span></span>  
  
- <span data-ttu-id="87dce-115">[Crear una consulta de notificación](/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="87dce-115">[Creating a Query for Notification](/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))</span></span>  
  
- <span data-ttu-id="87dce-116">[Consideraciones de seguridad de Service Broker](/previous-versions/sql/sql-server-2005/ms166059(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="87dce-116">[Security Considerations for Service Broker](/previous-versions/sql/sql-server-2005/ms166059(v=sql.90))</span></span>  
  
- <span data-ttu-id="87dce-117">[Seguridad y protección (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522911(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="87dce-117">[Security and Protection (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522911(v=sql.105))</span></span>  
  
- <span data-ttu-id="87dce-118">[Consideraciones de seguridad de Notification Services](/previous-versions/sql/sql-server-2005/ms172604(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="87dce-118">[Security Considerations for Notifications Services](/previous-versions/sql/sql-server-2005/ms172604(v=sql.90))</span></span>  
  
- <span data-ttu-id="87dce-119">[Permisos de notificación de consulta](/previous-versions/sql/sql-server-2008-r2/ms188311(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="87dce-119">[Query Notification Permissions](/previous-versions/sql/sql-server-2008-r2/ms188311(v=sql.105))</span></span>  
  
- <span data-ttu-id="87dce-120">[Consideraciones internacionales de Service Broker](/previous-versions/sql/sql-server-2005/ms166028(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="87dce-120">[International Considerations for Service Broker](/previous-versions/sql/sql-server-2005/ms166028(v=sql.90))</span></span>  
  
- <span data-ttu-id="87dce-121">[Consideraciones de diseño de soluciones (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522899(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="87dce-121">[Solution Design Considerations (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522899(v=sql.105))</span></span>  
  
- <span data-ttu-id="87dce-122">[Centro de información del desarrollador de Service Broker](/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="87dce-122">[Service Broker Developer InfoCenter](/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))</span></span>  
  
- <span data-ttu-id="87dce-123">[Guía del desarrollador (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="87dce-123">[Developer's Guide (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))</span></span>  
  
## <a name="enabling-query-notifications-to-run-sample-code"></a><span data-ttu-id="87dce-124">Habilitar las notificaciones de consulta para ejecutar código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="87dce-124">Enabling Query Notifications to Run Sample Code</span></span>  

 <span data-ttu-id="87dce-125">Para habilitar Service Broker en la base de datos **AdventureWorks** mediante SQL Server Management Studio, ejecute la siguiente instrucción de Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="87dce-125">To enable Service Broker on the **AdventureWorks** database by using SQL Server Management Studio, execute the following Transact-SQL statement:</span></span>  
  
 `ALTER DATABASE AdventureWorks SET ENABLE_BROKER;`  
  
 <span data-ttu-id="87dce-126">Para que los ejemplos de notificaciones de consulta se ejecuten correctamente, se deben ejecutar las siguientes instrucciones Transact-SQL en el servidor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="87dce-126">For the query notification samples to run correctly, the following Transact-SQL statements must be executed on the database server.</span></span>  
  
```sql
CREATE QUEUE ContactChangeMessages;  
  
CREATE SERVICE ContactChangeNotifications  
  ON QUEUE ContactChangeMessages  
([http://schemas.microsoft.com/SQL/Notifications/PostQueryNotification]);  
```  
  
## <a name="query-notifications-permissions"></a><span data-ttu-id="87dce-127">Permisos de notificaciones de consulta</span><span class="sxs-lookup"><span data-stu-id="87dce-127">Query Notifications Permissions</span></span>  

 <span data-ttu-id="87dce-128">Los usuarios que ejecutan comandos que solicitan una notificación deben tener el permiso de base de datos SUBSCRIBE QUERY NOTIFICATIONS en el servidor.</span><span class="sxs-lookup"><span data-stu-id="87dce-128">Users who execute commands requesting notification must have SUBSCRIBE QUERY NOTIFICATIONS database permission on the server.</span></span>  
  
 <span data-ttu-id="87dce-129">El código del lado cliente que se ejecuta en una situación de confianza parcial requiere <xref:System.Data.SqlClient.SqlClientPermission>.</span><span class="sxs-lookup"><span data-stu-id="87dce-129">Client-side code that runs in a partial trust situation requires the <xref:System.Data.SqlClient.SqlClientPermission>.</span></span>  
  
 <span data-ttu-id="87dce-130">El código siguiente crea un objeto <xref:System.Data.SqlClient.SqlClientPermission>, estableciendo <xref:System.Security.Permissions.PermissionState> en <xref:System.Security.Permissions.PermissionState.Unrestricted>.</span><span class="sxs-lookup"><span data-stu-id="87dce-130">The following code creates a <xref:System.Data.SqlClient.SqlClientPermission> object, setting the <xref:System.Security.Permissions.PermissionState> to <xref:System.Security.Permissions.PermissionState.Unrestricted>.</span></span> <span data-ttu-id="87dce-131"><xref:System.Security.CodeAccessPermission.Demand%2A> forzará a <xref:System.Security.SecurityException> en un entorno de ejecución si todos los autores de llamada situados en la parte superior de la pila de llamadas no disponen del permiso.</span><span class="sxs-lookup"><span data-stu-id="87dce-131">The <xref:System.Security.CodeAccessPermission.Demand%2A> will force a <xref:System.Security.SecurityException> at run time if all callers higher in the call stack have not been granted the permission.</span></span>  
  
 [!code-csharp[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/CS/source.cs#1)]
 [!code-vb[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/VB/source.vb#1)]  
  
## <a name="choosing-a-notification-object"></a><span data-ttu-id="87dce-132">Elección de un objeto de notificación</span><span class="sxs-lookup"><span data-stu-id="87dce-132">Choosing a Notification Object</span></span>  

 <span data-ttu-id="87dce-133">La API de notificaciones de consulta proporciona dos objetos para procesar notificaciones: <xref:System.Data.SqlClient.SqlDependency> y <xref:System.Data.Sql.SqlNotificationRequest>.</span><span class="sxs-lookup"><span data-stu-id="87dce-133">The query notifications API provides two objects to process notifications: <xref:System.Data.SqlClient.SqlDependency> and <xref:System.Data.Sql.SqlNotificationRequest>.</span></span> <span data-ttu-id="87dce-134">En general, la mayoría de las aplicaciones que no son ASP.NET deben utilizar el objeto <xref:System.Data.SqlClient.SqlDependency>.</span><span class="sxs-lookup"><span data-stu-id="87dce-134">In general, most non-ASP.NET applications should use the <xref:System.Data.SqlClient.SqlDependency> object.</span></span> <span data-ttu-id="87dce-135">Las aplicaciones ASP.NET deben utilizar la <xref:System.Web.Caching.SqlCacheDependency> de nivel más alto, que abarca <xref:System.Data.SqlClient.SqlDependency> y proporciona un marco para administrar los objetos de notificación y de caché.</span><span class="sxs-lookup"><span data-stu-id="87dce-135">ASP.NET applications should use the higher-level <xref:System.Web.Caching.SqlCacheDependency>, which wraps <xref:System.Data.SqlClient.SqlDependency> and provides a framework for administering the notification and cache objects.</span></span>  
  
### <a name="using-sqldependency"></a><span data-ttu-id="87dce-136">Uso de SqlDependency</span><span class="sxs-lookup"><span data-stu-id="87dce-136">Using SqlDependency</span></span>  

 <span data-ttu-id="87dce-137">Para usar <xref:System.Data.SqlClient.SqlDependency>, Service Broker debe estar habilitado en la base de datos de SQL Server que se vaya a usar y los usuarios deben tener permisos para recibir notificaciones.</span><span class="sxs-lookup"><span data-stu-id="87dce-137">To use <xref:System.Data.SqlClient.SqlDependency>, Service Broker must be enabled for the SQL Server database being used, and users must have permissions to receive notifications.</span></span> <span data-ttu-id="87dce-138">Los objetos de Service Broker, como la cola de notificación, están predefinidos.</span><span class="sxs-lookup"><span data-stu-id="87dce-138">Service Broker objects, such as the notification queue, are predefined.</span></span>  
  
 <span data-ttu-id="87dce-139">Además, <xref:System.Data.SqlClient.SqlDependency> inicia automáticamente un subproceso de trabajo para procesar las notificaciones que se publican en la cola; también analiza el mensaje de Service Broker y expone la información en forma de datos de argumento de evento.</span><span class="sxs-lookup"><span data-stu-id="87dce-139">In addition, <xref:System.Data.SqlClient.SqlDependency> automatically launches a worker thread to process notifications as they are posted to the queue; it also parses the Service Broker message, exposing the information as event argument data.</span></span> <span data-ttu-id="87dce-140"><xref:System.Data.SqlClient.SqlDependency> se debe inicializar llamando al método `Start` para establecer una dependencia en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="87dce-140"><xref:System.Data.SqlClient.SqlDependency> must be initialized by calling the `Start` method to establish a dependency to the database.</span></span> <span data-ttu-id="87dce-141">Se trata de un método estático al que es necesario llamar solo una vez durante la inicialización de la aplicación para cada conexión de base de datos necesaria.</span><span class="sxs-lookup"><span data-stu-id="87dce-141">This is a static method that needs to be called only once during application initialization for each database connection required.</span></span> <span data-ttu-id="87dce-142">Se debe llamar al método `Stop` en la finalización de la aplicación para cada conexión de dependencia realizada.</span><span class="sxs-lookup"><span data-stu-id="87dce-142">The `Stop` method should be called at application termination for each dependency connection that was made.</span></span>  
  
### <a name="using-sqlnotificationrequest"></a><span data-ttu-id="87dce-143">Uso de SqlNotificationRequest</span><span class="sxs-lookup"><span data-stu-id="87dce-143">Using SqlNotificationRequest</span></span>  

 <span data-ttu-id="87dce-144">Por el contrario, <xref:System.Data.Sql.SqlNotificationRequest> requiere que implemente toda la infraestructura de escucha.</span><span class="sxs-lookup"><span data-stu-id="87dce-144">In contrast, <xref:System.Data.Sql.SqlNotificationRequest> requires you to implement the entire listening infrastructure yourself.</span></span> <span data-ttu-id="87dce-145">Además, se deben definir todos los objetos de Service Broker de compatibilidad, como la cola, el servicio y los tipos de mensajes admitidos por la cola.</span><span class="sxs-lookup"><span data-stu-id="87dce-145">In addition, all the supporting Service Broker objects such as the queue, service, and message types supported by the queue must be defined.</span></span> <span data-ttu-id="87dce-146">Este enfoque manual es útil si la aplicación requiere mensajes de notificación o comportamientos de notificación especiales, o si la aplicación forma parte de una aplicación Service Broker mayor.</span><span class="sxs-lookup"><span data-stu-id="87dce-146">This manual approach is useful if your application requires special notification messages or notification behaviors, or if your application is part of a larger Service Broker application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87dce-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="87dce-147">See also</span></span>

- [<span data-ttu-id="87dce-148">Notificaciones de consulta en SQL Server</span><span class="sxs-lookup"><span data-stu-id="87dce-148">Query Notifications in SQL Server</span></span>](query-notifications-in-sql-server.md)
- [<span data-ttu-id="87dce-149">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="87dce-149">ADO.NET Overview</span></span>](../ado-net-overview.md)
