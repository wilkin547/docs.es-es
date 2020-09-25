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
# <a name="query-notifications-in-sql-server"></a><span data-ttu-id="45e02-103">Notificaciones de consulta en SQL Server</span><span class="sxs-lookup"><span data-stu-id="45e02-103">Query Notifications in SQL Server</span></span>

<span data-ttu-id="45e02-104">Las notificaciones de consulta, creadas a partir de la infraestructura de Service Broker, permiten notificar a las aplicaciones si los datos han cambiado.</span><span class="sxs-lookup"><span data-stu-id="45e02-104">Built upon the Service Broker infrastructure, query notifications allow applications to be notified when data has changed.</span></span> <span data-ttu-id="45e02-105">Esta característica resulta especialmente útil para las aplicaciones que proporcionan una caché de información de una base de datos, como una aplicación web, y necesitan recibir notificaciones si se modifican los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="45e02-105">This feature is particularly useful for applications that provide a cache of information from a database, such as a Web application, and need to be notified when the source data is changed.</span></span>  
  
 <span data-ttu-id="45e02-106">Hay tres maneras de implementar notificaciones de consulta mediante ADO.NET:</span><span class="sxs-lookup"><span data-stu-id="45e02-106">There are three ways you can implement query notifications using ADO.NET:</span></span>  
  
1. <span data-ttu-id="45e02-107">La implementación de bajo nivel se proporciona mediante la clase `SqlNotificationRequest` que expone la funcionalidad del servidor, lo que permite ejecutar un comando con una solicitud de notificación.</span><span class="sxs-lookup"><span data-stu-id="45e02-107">The low-level implementation is provided by the `SqlNotificationRequest` class that exposes server-side functionality, enabling you to execute a command with a notification request.</span></span>  
  
2. <span data-ttu-id="45e02-108">La implementación de alto nivel se proporciona mediante la clase `SqlDependency`, que es una clase que proporciona una abstracción de alto nivel de la funcionalidad de notificación entre la aplicación de origen y SQL Server, lo que permite utilizar una dependencia para detectar los cambios en el servidor.</span><span class="sxs-lookup"><span data-stu-id="45e02-108">The high-level implementation is provided by the `SqlDependency` class, which is a class that provides a high-level abstraction of notification functionality between the source application and SQL Server, enabling you to use a dependency to detect changes in the server.</span></span> <span data-ttu-id="45e02-109">En la mayoría de los casos, ésta es la manera más sencilla y eficaz de aprovechar la funcionalidad de notificaciones de SQL Server 2005 por parte de aplicaciones cliente administradas que utilizan el proveedor de datos .NET Framework para SQL Server.</span><span class="sxs-lookup"><span data-stu-id="45e02-109">In most cases, this is the simplest and most effective way to leverage SQL Server notifications capability by managed client applications using the .NET Framework Data Provider for SQL Server.</span></span>  
  
3. <span data-ttu-id="45e02-110">Además, las aplicaciones web creadas mediante ASP.NET 2.0 o posterior pueden usar las clases auxiliares `SqlCacheDependency`.</span><span class="sxs-lookup"><span data-stu-id="45e02-110">In addition, Web applications built using ASP.NET 2.0 or later can use the `SqlCacheDependency` helper classes.</span></span>  
  
 <span data-ttu-id="45e02-111">Las notificaciones de consulta se usan para las aplicaciones que necesitan actualizar las visualizaciones o las almacena en caché en respuesta a los cambios en los datos subyacentes.</span><span class="sxs-lookup"><span data-stu-id="45e02-111">Query notifications are used for applications that need to refresh displays or caches in response to changes in underlying data.</span></span> <span data-ttu-id="45e02-112">Microsoft SQL Server 2005 permite que las aplicaciones .NET Framework envíen un comando a SQL Server y soliciten una notificación si la ejecución del mismo comando produjera conjuntos de resultados diferentes de los inicialmente recuperados.</span><span class="sxs-lookup"><span data-stu-id="45e02-112">Microsoft SQL Server allows .NET Framework applications to send a command to SQL Server and request notification if executing the same command would produce result sets different from those initially retrieved.</span></span> <span data-ttu-id="45e02-113">Las notificaciones generadas en el servidor se envían a través de colas para procesarse más adelante.</span><span class="sxs-lookup"><span data-stu-id="45e02-113">Notifications generated at the server are sent through queues to be processed later.</span></span>  
  
 <span data-ttu-id="45e02-114">Puede configurar notificaciones para las instrucciones SELECT y EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="45e02-114">You can set up notifications for SELECT and EXECUTE statements.</span></span> <span data-ttu-id="45e02-115">Cuando se usa una instrucción EXECUTE, SQL Server registra una notificación para el comando ejecutado en lugar de la propia instrucción EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="45e02-115">When using an EXECUTE statement, SQL Server registers a notification for the command executed rather than the EXECUTE statement itself.</span></span> <span data-ttu-id="45e02-116">El comando debe cumplir los requisitos y las limitaciones de una instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="45e02-116">The command must meet the requirements and limitations for a SELECT statement.</span></span> <span data-ttu-id="45e02-117">Cuando un comando que registra una notificación contiene más de una instrucción, el motor de base de datos crea una notificación para cada instrucción del lote.</span><span class="sxs-lookup"><span data-stu-id="45e02-117">When a command that registers a notification contains more than one statement, the Database Engine creates a notification for each statement in the batch.</span></span>  
  
 <span data-ttu-id="45e02-118">Si está desarrollando una aplicación que necesite las notificaciones de subsegundo confiables cuando cambian los datos, revise las secciones **planear una estrategia eficaz de notificaciones de consulta** y **alternativas a las notificaciones de consulta** en el artículo [planear notificaciones](/previous-versions/sql/sql-server-2008-r2/ms187528(v=sql.105)).</span><span class="sxs-lookup"><span data-stu-id="45e02-118">If you are developing an application where you need reliable sub-second notifications when data changes, review the sections **Planning an Efficient Query Notifications Strategy** and **Alternatives to Query Notifications** in the [Planning for Notifications](/previous-versions/sql/sql-server-2008-r2/ms187528(v=sql.105)) article.</span></span> <span data-ttu-id="45e02-119">Para obtener más información acerca de las notificaciones de consulta y SQL Server Service Broker, consulte los siguientes vínculos a los artículos de la documentación de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="45e02-119">For more information about Query Notifications and SQL Server Service Broker, see the following links to articles in the SQL Server documentation.</span></span>  
  
 <span data-ttu-id="45e02-120">**Documentación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="45e02-120">**SQL Server documentation**</span></span>  
  
- <span data-ttu-id="45e02-121">[Usar notificaciones de consulta](/previous-versions/sql/sql-server-2008-r2/ms175110(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="45e02-121">[Using Query Notifications](/previous-versions/sql/sql-server-2008-r2/ms175110(v=sql.105))</span></span>  
  
- <span data-ttu-id="45e02-122">[Crear una consulta de notificación](/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="45e02-122">[Creating a Query for Notification](/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))</span></span>  
  
- <span data-ttu-id="45e02-123">[Desarrollo (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522889(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="45e02-123">[Development (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522889(v=sql.105))</span></span>  
  
- <span data-ttu-id="45e02-124">[Centro de información del desarrollador de Service Broker](/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="45e02-124">[Service Broker Developer InfoCenter](/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))</span></span>  
  
- <span data-ttu-id="45e02-125">[Guía del desarrollador (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="45e02-125">[Developer's Guide (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="45e02-126">En esta sección</span><span class="sxs-lookup"><span data-stu-id="45e02-126">In This Section</span></span>  

 [<span data-ttu-id="45e02-127">Habilitación de notificaciones de consulta</span><span class="sxs-lookup"><span data-stu-id="45e02-127">Enabling Query Notifications</span></span>](enabling-query-notifications.md)  
 <span data-ttu-id="45e02-128">Describe cómo usar las notificaciones de consulta, incluidos los requisitos para habilitarlas y usarlas.</span><span class="sxs-lookup"><span data-stu-id="45e02-128">Discusses how to use query notifications, including the requirements for enabling and using them.</span></span>  
  
 [<span data-ttu-id="45e02-129">SqlDependency en una aplicación ASP.NET</span><span class="sxs-lookup"><span data-stu-id="45e02-129">SqlDependency in an ASP.NET Application</span></span>](sqldependency-in-an-aspnet-app.md)  
 <span data-ttu-id="45e02-130">Muestra cómo usar notificaciones de consulta desde una aplicación de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="45e02-130">Demonstrates how to use query notifications from an ASP.NET application.</span></span>  
  
 [<span data-ttu-id="45e02-131">Detección de cambios con SqlDependency</span><span class="sxs-lookup"><span data-stu-id="45e02-131">Detecting Changes with SqlDependency</span></span>](detecting-changes-with-sqldependency.md)  
 <span data-ttu-id="45e02-132">Muestra cómo detectar cuándo los resultados de la consulta serán distintos de los recibidos originalmente.</span><span class="sxs-lookup"><span data-stu-id="45e02-132">Demonstrates how to detect when query results will be different from those originally received.</span></span>  
  
 [<span data-ttu-id="45e02-133">Ejecución de SqlCommand con un SqlNotificationRequest</span><span class="sxs-lookup"><span data-stu-id="45e02-133">SqlCommand Execution with a SqlNotificationRequest</span></span>](sqlcommand-execution-with-a-sqlnotificationrequest.md)  
 <span data-ttu-id="45e02-134">Muestra cómo configurar un objeto <xref:System.Data.SqlClient.SqlCommand> para que funcione con una notificación de consulta.</span><span class="sxs-lookup"><span data-stu-id="45e02-134">Demonstrates configuring a <xref:System.Data.SqlClient.SqlCommand> object to work with a query notification.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="45e02-135">Referencia</span><span class="sxs-lookup"><span data-stu-id="45e02-135">Reference</span></span>  

 <xref:System.Data.Sql.SqlNotificationRequest>  
 <span data-ttu-id="45e02-136">Describe la clase <xref:System.Data.Sql.SqlNotificationRequest> y todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="45e02-136">Describes the <xref:System.Data.Sql.SqlNotificationRequest> class and all of its members.</span></span>  
  
 <xref:System.Data.SqlClient.SqlDependency>  
 <span data-ttu-id="45e02-137">Describe la clase <xref:System.Data.SqlClient.SqlDependency> y todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="45e02-137">Describes the <xref:System.Data.SqlClient.SqlDependency> class and all of its members.</span></span>  
  
 <xref:System.Web.Caching.SqlCacheDependency>  
 <span data-ttu-id="45e02-138">Describe la clase <xref:System.Web.Caching.SqlCacheDependency> y todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="45e02-138">Describes the <xref:System.Web.Caching.SqlCacheDependency> class and all of its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45e02-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="45e02-139">See also</span></span>

- [<span data-ttu-id="45e02-140">SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="45e02-140">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="45e02-141">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="45e02-141">ADO.NET Overview</span></span>](../ado-net-overview.md)
