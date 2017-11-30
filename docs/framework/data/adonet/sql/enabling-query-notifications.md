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
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: fbdec484af39eb4d98418ad72ed66ef7913f2d56
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="enabling-query-notifications"></a><span data-ttu-id="f9f54-102">Habilitar notificaciones de consulta</span><span class="sxs-lookup"><span data-stu-id="f9f54-102">Enabling Query Notifications</span></span>
<span data-ttu-id="f9f54-103">Las aplicaciones que consumen notificaciones de consulta poseen un conjunto común de requisitos.</span><span class="sxs-lookup"><span data-stu-id="f9f54-103">Applications that consume query notifications have a common set of requirements.</span></span> <span data-ttu-id="f9f54-104">El origen de datos se debe configurar correctamente para que admita notificaciones de consulta SQL y el usuario debe contar con los permisos adecuados en el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="f9f54-104">Your data source must be correctly configured to support SQL query notifications, and the user must have the correct client-side and server-side permissions.</span></span>  
  
 <span data-ttu-id="f9f54-105">Para utilizar notificaciones de consulta, es necesario:</span><span class="sxs-lookup"><span data-stu-id="f9f54-105">To use query notifications you must:</span></span>  
  
-   <span data-ttu-id="f9f54-106">Habilitar las notificaciones de consulta en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f9f54-106">Enable query notifications for your database.</span></span>  
  
-   <span data-ttu-id="f9f54-107">Asegurarse de que el identificador de usuario usado para conectarse a la base de datos dispone de los permisos necesarios.</span><span class="sxs-lookup"><span data-stu-id="f9f54-107">Ensure that the user ID used to connect to the database has the necessary permissions.</span></span>  
  
-   <span data-ttu-id="f9f54-108">Utilizar un objeto <xref:System.Data.SqlClient.SqlCommand> para ejecutar una instrucción SELECT válida con un objeto de notificación asociado, <xref:System.Data.SqlClient.SqlDependency> o <xref:System.Data.Sql.SqlNotificationRequest>.</span><span class="sxs-lookup"><span data-stu-id="f9f54-108">Use a <xref:System.Data.SqlClient.SqlCommand> object to execute a valid SELECT statement with an associated notification object—either <xref:System.Data.SqlClient.SqlDependency> or <xref:System.Data.Sql.SqlNotificationRequest>.</span></span>  
  
-   <span data-ttu-id="f9f54-109">Proporcionar código para procesar la notificación si los datos que se supervisan cambian.</span><span class="sxs-lookup"><span data-stu-id="f9f54-109">Provide code to process the notification if the data being monitored changes.</span></span>  
  
## <a name="query-notifications-requirements"></a><span data-ttu-id="f9f54-110">Requisitos de las notificaciones de consulta</span><span class="sxs-lookup"><span data-stu-id="f9f54-110">Query Notifications Requirements</span></span>  
 <span data-ttu-id="f9f54-111">Las notificaciones de consulta solo son compatibles con las instrucciones SELECT que cumplen ciertos requisitos específicos.</span><span class="sxs-lookup"><span data-stu-id="f9f54-111">Query notifications are supported only for SELECT statements that meet a list of specific requirements.</span></span> <span data-ttu-id="f9f54-112">En la tabla siguiente se proporcionan vínculos a la documentación sobre Service Broker y las notificaciones de consulta de los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f9f54-112">The following table provides links to the Service Broker and Query Notifications documentation in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="f9f54-113">**Libros en pantalla de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="f9f54-113">**SQL Server Books Online**</span></span>  
  
-   [<span data-ttu-id="f9f54-114">Crear una consulta de notificación</span><span class="sxs-lookup"><span data-stu-id="f9f54-114">Creating a Query for Notification</span></span>](http://msdn.microsoft.com/library/ms181122.aspx)  
  
-   [<span data-ttu-id="f9f54-115">Consideraciones de seguridad para Service Broker</span><span class="sxs-lookup"><span data-stu-id="f9f54-115">Security Considerations for Service Broker</span></span>](http://msdn.microsoft.com/library/ms166059.aspx)  
  
-   [<span data-ttu-id="f9f54-116">Seguridad y protección (Service Broker)</span><span class="sxs-lookup"><span data-stu-id="f9f54-116">Security and Protection (Service Broker)</span></span>](http://msdn.microsoft.com/library/bb522911.aspx)  
  
-   [<span data-ttu-id="f9f54-117">Consideraciones de seguridad para Notification Services</span><span class="sxs-lookup"><span data-stu-id="f9f54-117">Security Considerations for Notifications Services</span></span>](http://msdn.microsoft.com/library/ms172604.aspx)  
  
-   [<span data-ttu-id="f9f54-118">Permisos de notificaciones de consulta</span><span class="sxs-lookup"><span data-stu-id="f9f54-118">Query Notification Permissions</span></span>](http://msdn.microsoft.com/library/ms188311.aspx)  
  
-   [<span data-ttu-id="f9f54-119">Consideraciones internacionales para Service Broker</span><span class="sxs-lookup"><span data-stu-id="f9f54-119">International Considerations for Service Broker</span></span>](http://msdn.microsoft.com/library/ms166028.aspx)  
  
-   [<span data-ttu-id="f9f54-120">Consideraciones de diseño de soluciones (Service Broker)</span><span class="sxs-lookup"><span data-stu-id="f9f54-120">Solution Design Considerations (Service Broker)</span></span>](http://msdn.microsoft.com/library/bb522899.aspx)  
  
-   [<span data-ttu-id="f9f54-121">Centro de información para desarrolladores de Service Broker</span><span class="sxs-lookup"><span data-stu-id="f9f54-121">Service Broker Developer InfoCenter</span></span>](http://msdn.microsoft.com/library/ms166100.aspx)  
  
-   [<span data-ttu-id="f9f54-122">Guía del desarrollador (Service Broker)</span><span class="sxs-lookup"><span data-stu-id="f9f54-122">Developer's Guide (Service Broker)</span></span>](http://msdn.microsoft.com/library/bb522908.aspx)  
  
## <a name="enabling-query-notifications-to-run-sample-code"></a><span data-ttu-id="f9f54-123">Habilitar las notificaciones de consulta para ejecutar código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="f9f54-123">Enabling Query Notifications to Run Sample Code</span></span>  
 <span data-ttu-id="f9f54-124">Para habilitar Service Broker en la **AdventureWorks** base de datos mediante SQL Server Management Studio, ejecute la instrucción de Transact-SQL siguiente:</span><span class="sxs-lookup"><span data-stu-id="f9f54-124">To enable Service Broker on the **AdventureWorks** database by using SQL Server Management Studio, execute the following Transact-SQL statement:</span></span>  
  
 `ALTER DATABASE AdventureWorks SET ENABLE_BROKER;`  
  
 <span data-ttu-id="f9f54-125">Para que el ejemplo de notificación de consulta funcione correctamente, es necesario ejecutar las siguientes instrucciones Transact-SQL en el servidor de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="f9f54-125">For the query notification samples to run correctly, the following Transact-SQL statements must be executed on the database server.</span></span>  
  
```  
CREATE QUEUE ContactChangeMessages;  
  
CREATE SERVICE ContactChangeNotifications  
  ON QUEUE ContactChangeMessages  
([http://schemas.microsoft.com/SQL/Notifications/PostQueryNotification]);  
```  
  
## <a name="query-notifications-permissions"></a><span data-ttu-id="f9f54-126">Permisos de notificaciones de consulta</span><span class="sxs-lookup"><span data-stu-id="f9f54-126">Query Notifications Permissions</span></span>  
 <span data-ttu-id="f9f54-127">Los usuarios que ejecutan comandos solicitando notificaciones deben disponer del permiso de base de datos SUBSCRIBE QUERY NOTIFICATIONS en el servidor.</span><span class="sxs-lookup"><span data-stu-id="f9f54-127">Users who execute commands requesting notification must have SUBSCRIBE QUERY NOTIFICATIONS database permission on the server.</span></span>  
  
 <span data-ttu-id="f9f54-128">El código de cliente que se ejecuta en una situación de confianza parcial necesita el <xref:System.Data.SqlClient.SqlClientPermission>.</span><span class="sxs-lookup"><span data-stu-id="f9f54-128">Client-side code that runs in a partial trust situation requires the <xref:System.Data.SqlClient.SqlClientPermission>.</span></span>  
  
 <span data-ttu-id="f9f54-129">El código siguiente crea un objeto <xref:System.Data.SqlClient.SqlClientPermission>, estableciendo <xref:System.Security.Permissions.PermissionState> en <xref:System.Security.Permissions.PermissionState.Unrestricted>.</span><span class="sxs-lookup"><span data-stu-id="f9f54-129">The following code creates a <xref:System.Data.SqlClient.SqlClientPermission> object, setting the <xref:System.Security.Permissions.PermissionState> to <xref:System.Security.Permissions.PermissionState.Unrestricted>.</span></span> <span data-ttu-id="f9f54-130"><xref:System.Security.CodeAccessPermission.Demand%2A> fuerza <xref:System.Security.SecurityException> en tiempo de ejecución si todos los llamadores situados en la parte superior de la pila de llamadas no disponen del permiso.</span><span class="sxs-lookup"><span data-stu-id="f9f54-130">The <xref:System.Security.CodeAccessPermission.Demand%2A> will force a <xref:System.Security.SecurityException> at run time if all callers higher in the call stack have not been granted the permission.</span></span>  
  
 [!code-csharp[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/CS/source.cs#1)]
 [!code-vb[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/VB/source.vb#1)]  
  
## <a name="choosing-a-notification-object"></a><span data-ttu-id="f9f54-131">Elección de un objeto de notificación</span><span class="sxs-lookup"><span data-stu-id="f9f54-131">Choosing a Notification Object</span></span>  
 <span data-ttu-id="f9f54-132">La API de notificaciones de consulta proporciona dos objetos para procesar las notificaciones: <xref:System.Data.SqlClient.SqlDependency> y <xref:System.Data.Sql.SqlNotificationRequest>.</span><span class="sxs-lookup"><span data-stu-id="f9f54-132">The query notifications API provides two objects to process notifications: <xref:System.Data.SqlClient.SqlDependency> and <xref:System.Data.Sql.SqlNotificationRequest>.</span></span> <span data-ttu-id="f9f54-133">En general, la mayoría de las aplicaciones que no son ASP.NET deben utilizar el objeto <xref:System.Data.SqlClient.SqlDependency>.</span><span class="sxs-lookup"><span data-stu-id="f9f54-133">In general, most non-ASP.NET applications should use the <xref:System.Data.SqlClient.SqlDependency> object.</span></span> <span data-ttu-id="f9f54-134">Las aplicaciones ASP.NET deben utilizar la <xref:System.Web.Caching.SqlCacheDependency> de nivel más alto, que abarca <xref:System.Data.SqlClient.SqlDependency> y proporciona un marco para administrar los objetos de notificación y de caché.</span><span class="sxs-lookup"><span data-stu-id="f9f54-134">ASP.NET applications should use the higher-level <xref:System.Web.Caching.SqlCacheDependency>, which wraps <xref:System.Data.SqlClient.SqlDependency> and provides a framework for administering the notification and cache objects.</span></span>  
  
### <a name="using-sqldependency"></a><span data-ttu-id="f9f54-135">Utilizar SqlDependency</span><span class="sxs-lookup"><span data-stu-id="f9f54-135">Using SqlDependency</span></span>  
 <span data-ttu-id="f9f54-136">Para utilizar <xref:System.Data.SqlClient.SqlDependency>, debe estar habilitado Service Broker en la base de datos de SQL Server que se vaya a usar y los usuarios deben tener permisos para recibir notificaciones.</span><span class="sxs-lookup"><span data-stu-id="f9f54-136">To use <xref:System.Data.SqlClient.SqlDependency>, Service Broker must be enabled for the SQL Server database being used, and users must have permissions to receive notifications.</span></span> <span data-ttu-id="f9f54-137">Los objetos de Service Broker, como la cola de notificaciones, están predefinidos.</span><span class="sxs-lookup"><span data-stu-id="f9f54-137">Service Broker objects, such as the notification queue, are predefined.</span></span>  
  
 <span data-ttu-id="f9f54-138">Además, <xref:System.Data.SqlClient.SqlDependency> inicia automáticamente un subproceso de trabajo para procesar las notificaciones que se publican en la cola; también analiza el mensaje de Service Broker y expone la información en forma de datos de argumento de evento.</span><span class="sxs-lookup"><span data-stu-id="f9f54-138">In addition, <xref:System.Data.SqlClient.SqlDependency> automatically launches a worker thread to process notifications as they are posted to the queue; it also parses the Service Broker message, exposing the information as event argument data.</span></span> <span data-ttu-id="f9f54-139">Para inicializar <xref:System.Data.SqlClient.SqlDependency>, es necesario llamar al método `Start` con el fin de establecer una dependencia con la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f9f54-139"><xref:System.Data.SqlClient.SqlDependency> must be initialized by calling the `Start` method to establish a dependency to the database.</span></span> <span data-ttu-id="f9f54-140">Se trata de un método estático que solo es necesario llamar una vez durante la inicialización de la aplicación en cada conexión a la base de datos necesaria.</span><span class="sxs-lookup"><span data-stu-id="f9f54-140">This is a static method that needs to be called only once during application initialization for each database connection required.</span></span> <span data-ttu-id="f9f54-141">Se debe llamar al método `Stop` después de terminar la aplicación para cada conexión de dependencia que se haga.</span><span class="sxs-lookup"><span data-stu-id="f9f54-141">The `Stop` method should be called at application termination for each dependency connection that was made.</span></span>  
  
### <a name="using-sqlnotificationrequest"></a><span data-ttu-id="f9f54-142">Utilizar SqlNotificationRequest</span><span class="sxs-lookup"><span data-stu-id="f9f54-142">Using SqlNotificationRequest</span></span>  
 <span data-ttu-id="f9f54-143">Por el contrario, <xref:System.Data.Sql.SqlNotificationRequest> exige que implemente usted mismo toda la infraestructura de escucha.</span><span class="sxs-lookup"><span data-stu-id="f9f54-143">In contrast, <xref:System.Data.Sql.SqlNotificationRequest> requires you to implement the entire listening infrastructure yourself.</span></span> <span data-ttu-id="f9f54-144">Además, es necesario definir todos los objetos de Service Broker compatibles, como la cola, los servicios y los tipos de mensajes que admite la cola.</span><span class="sxs-lookup"><span data-stu-id="f9f54-144">In addition, all the supporting Service Broker objects such as the queue, service, and message types supported by the queue must be defined.</span></span> <span data-ttu-id="f9f54-145">Este enfoque manual resulta de utilidad si la aplicación necesita mensajes o comportamientos de notificación especiales, o si la aplicación forma parte de una aplicación de Service Broker más grande.</span><span class="sxs-lookup"><span data-stu-id="f9f54-145">This manual approach is useful if your application requires special notification messages or notification behaviors, or if your application is part of a larger Service Broker application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9f54-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9f54-146">See Also</span></span>  
 [<span data-ttu-id="f9f54-147">Notificaciones de consulta en SQL Server</span><span class="sxs-lookup"><span data-stu-id="f9f54-147">Query Notifications in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)  
 [<span data-ttu-id="f9f54-148">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="f9f54-148">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
