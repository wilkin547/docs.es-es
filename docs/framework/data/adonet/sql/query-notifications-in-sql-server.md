---
title: Notificaciones de consulta en SQL Server
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f0ba1a1-3180-4af8-87f7-c795dc8f8f55
caps.latest.revision: "6"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 376f2cfefcaf53affe5a20a5812a02839dd5d4a9
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="query-notifications-in-sql-server"></a><span data-ttu-id="63aae-102">Notificaciones de consulta en SQL Server</span><span class="sxs-lookup"><span data-stu-id="63aae-102">Query Notifications in SQL Server</span></span>
<span data-ttu-id="63aae-103">Las notificaciones de consulta, que están basadas en la infraestructura Service Broker, permiten que se notifique a las aplicaciones cuando cambian los datos.</span><span class="sxs-lookup"><span data-stu-id="63aae-103">Built upon the Service Broker infrastructure, query notifications allow applications to be notified when data has changed.</span></span> <span data-ttu-id="63aae-104">Esta característica es especialmente útil en aplicaciones que proporcionan una caché de información desde una base de datos, por ejemplo, una aplicación web, y necesitan recibir notificación cuando cambian los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="63aae-104">This feature is particularly useful for applications that provide a cache of information from a database, such as a Web application, and need to be notified when the source data is changed.</span></span>  
  
 <span data-ttu-id="63aae-105">Existen tres maneras de implementar las notificaciones de consulta mediante ADO.NET:</span><span class="sxs-lookup"><span data-stu-id="63aae-105">There are three ways you can implement query notifications using ADO.NET:</span></span>  
  
1.  <span data-ttu-id="63aae-106">La implementación de nivel inferior la proporciona la clase `SqlNotificationRequest`, que presenta funciones de servidor, lo que permite ejecutar un comando con una solicitud de notificación.</span><span class="sxs-lookup"><span data-stu-id="63aae-106">The low-level implementation is provided by the `SqlNotificationRequest` class that exposes server-side functionality, enabling you to execute a command with a notification request.</span></span>  
  
2.  <span data-ttu-id="63aae-107">La implementación de nivel superior la proporciona la clase `SqlDependency`, que ofrece un alto nivel de abstracción de la funcionalidad de notificación entre la aplicación de origen y SQL Server, lo que permite utilizar una dependencia para detectar cambios en el servidor.</span><span class="sxs-lookup"><span data-stu-id="63aae-107">The high-level implementation is provided by the `SqlDependency` class, which is a class that provides a high-level abstraction of notification functionality between the source application and SQL Server, enabling you to use a dependency to detect changes in the server.</span></span> <span data-ttu-id="63aae-108">En la mayoría de los casos, ésta es la manera más sencilla y eficaz de aprovechar la funcionalidad de notificaciones de SQL Server 2005 por parte de aplicaciones cliente administradas que utilizan el proveedor de datos .NET Framework para SQL Server.</span><span class="sxs-lookup"><span data-stu-id="63aae-108">In most cases, this is the simplest and most effective way to leverage SQL Server notifications capability by managed client applications using the .NET Framework Data Provider for SQL Server.</span></span>  
  
3.  <span data-ttu-id="63aae-109">Además, las aplicaciones web compiladas mediante ASP.NET 2.0 o posterior pueden utilizar las clases auxiliares `SqlCacheDependency`.</span><span class="sxs-lookup"><span data-stu-id="63aae-109">In addition, Web applications built using ASP.NET 2.0 or later can use the `SqlCacheDependency` helper classes.</span></span>  
  
 <span data-ttu-id="63aae-110">Las notificaciones de consulta son útiles en aquellas aplicaciones que necesitan actualizar presentaciones o cachés como respuesta a los cambios en los datos subyacentes.</span><span class="sxs-lookup"><span data-stu-id="63aae-110">Query notifications are used for applications that need to refresh displays or caches in response to changes in underlying data.</span></span> <span data-ttu-id="63aae-111">Microsoft SQL Server 2005 permite que las aplicaciones .NET Framework envíen un comando a SQL Server y soliciten una notificación si la ejecución del mismo comando produjera conjuntos de resultados diferentes de los inicialmente recuperados.</span><span class="sxs-lookup"><span data-stu-id="63aae-111">Microsoft SQL Server allows .NET Framework applications to send a command to SQL Server and request notification if executing the same command would produce result sets different from those initially retrieved.</span></span> <span data-ttu-id="63aae-112">Las notificaciones generadas en el servidor se envían a través de colas para procesarlas más adelante.</span><span class="sxs-lookup"><span data-stu-id="63aae-112">Notifications generated at the server are sent through queues to be processed later.</span></span>  
  
 <span data-ttu-id="63aae-113">Puede definir notificaciones para las instrucciones SELECT y EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="63aae-113">You can set up notifications for SELECT and EXECUTE statements.</span></span> <span data-ttu-id="63aae-114">Al utilizar una instrucción EXECUTE, SQL Server registra una notificación para el comando ejecutado en lugar de la propia instrucción EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="63aae-114">When using an EXECUTE statement, SQL Server registers a notification for the command executed rather than the EXECUTE statement itself.</span></span> <span data-ttu-id="63aae-115">El comando debe cumplir los requisitos y limitaciones de una instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="63aae-115">The command must meet the requirements and limitations for a SELECT statement.</span></span> <span data-ttu-id="63aae-116">Si un comando que registra una notificación contiene más de una instrucción, el motor de base de datos crea una notificación para cada instrucción del lote.</span><span class="sxs-lookup"><span data-stu-id="63aae-116">When a command that registers a notification contains more than one statement, the Database Engine creates a notification for each statement in the batch.</span></span>  
  
 <span data-ttu-id="63aae-117">Si está desarrollando una aplicación en los que tenga las notificaciones de subsegundo confiables cuando los datos cambien, consulte las secciones **planear una estrategia eficaz de notificaciones de consulta** y **alternativas a las notificaciones de consulta** en el [planear notificaciones](http://go.microsoft.com/fwlink/?LinkId=211984) tema en los libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="63aae-117">If you are developing an application where you need reliable sub-second notifications when data changes, review the sections **Planning an Efficient Query Notifications Strategy** and **Alternatives to Query Notifications** in the [Planning for Notifications](http://go.microsoft.com/fwlink/?LinkId=211984) topic in SQL Server Books Online.</span></span> <span data-ttu-id="63aae-118">Para obtener más información acerca de las notificaciones de consulta y SQL Server Service Broker, vea los siguientes vínculos a temas de los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="63aae-118">For more information about Query Notifications and SQL Server Service Broker, see the following links to topics in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="63aae-119">**Libros en pantalla de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="63aae-119">**SQL Server Books Online**</span></span>  
  
-   [<span data-ttu-id="63aae-120">Usar notificaciones de consulta</span><span class="sxs-lookup"><span data-stu-id="63aae-120">Using Query Notifications</span></span>](http://msdn.microsoft.com/library/ms175110.aspx)  
  
-   [<span data-ttu-id="63aae-121">Crear una consulta de notificación</span><span class="sxs-lookup"><span data-stu-id="63aae-121">Creating a Query for Notification</span></span>](http://msdn.microsoft.com/library/ms181122.aspx)  
  
-   [<span data-ttu-id="63aae-122">Service Broker</span><span class="sxs-lookup"><span data-stu-id="63aae-122">Service Broker</span></span>](http://msdn.microsoft.com/library/bb522889.aspx)  
  
-   [<span data-ttu-id="63aae-123">Centro de información para desarrolladores de Service Broker</span><span class="sxs-lookup"><span data-stu-id="63aae-123">Service Broker Developer InfoCenter</span></span>](http://msdn.microsoft.com/library/ms166100.aspx)  
  
-   [<span data-ttu-id="63aae-124">Desarrollo (Service Broker)</span><span class="sxs-lookup"><span data-stu-id="63aae-124">Development (Service Broker)</span></span>](http://msdn.microsoft.com/library/bb522908.aspx)  
  
## <a name="in-this-section"></a><span data-ttu-id="63aae-125">En esta sección</span><span class="sxs-lookup"><span data-stu-id="63aae-125">In This Section</span></span>  
 [<span data-ttu-id="63aae-126">Habilitación de notificaciones de consulta</span><span class="sxs-lookup"><span data-stu-id="63aae-126">Enabling Query Notifications</span></span>](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md)  
 <span data-ttu-id="63aae-127">Describe cómo utilizar las notificaciones de consulta, junto con los requisitos para habilitarlas y usarlas.</span><span class="sxs-lookup"><span data-stu-id="63aae-127">Discusses how to use query notifications, including the requirements for enabling and using them.</span></span>  
  
 [<span data-ttu-id="63aae-128">SqlDependency en una aplicación ASP.NET</span><span class="sxs-lookup"><span data-stu-id="63aae-128">SqlDependency in an ASP.NET Application</span></span>](../../../../../docs/framework/data/adonet/sql/sqldependency-in-an-aspnet-app.md)  
 <span data-ttu-id="63aae-129">Muestra cómo usar notificaciones de consulta desde una aplicación ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="63aae-129">Demonstrates how to use query notifications from an ASP.NET application.</span></span>  
  
 [<span data-ttu-id="63aae-130">Detección de cambios con SqlDependency</span><span class="sxs-lookup"><span data-stu-id="63aae-130">Detecting Changes with SqlDependency</span></span>](../../../../../docs/framework/data/adonet/sql/detecting-changes-with-sqldependency.md)  
 <span data-ttu-id="63aae-131">Muestra cómo detectar cuándo los resultados de las consultas serán diferentes de los recibidos originalmente.</span><span class="sxs-lookup"><span data-stu-id="63aae-131">Demonstrates how to detect when query results will be different from those originally received.</span></span>  
  
 [<span data-ttu-id="63aae-132">Ejecución de SqlCommand con SqlNotificationRequest</span><span class="sxs-lookup"><span data-stu-id="63aae-132">SqlCommand Execution with a SqlNotificationRequest</span></span>](../../../../../docs/framework/data/adonet/sql/sqlcommand-execution-with-a-sqlnotificationrequest.md)  
 <span data-ttu-id="63aae-133">Muestra cómo configurar un objeto <xref:System.Data.SqlClient.SqlCommand> para trabajar con una notificación de consulta.</span><span class="sxs-lookup"><span data-stu-id="63aae-133">Demonstrates configuring a <xref:System.Data.SqlClient.SqlCommand> object to work with a query notification.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="63aae-134">Referencia</span><span class="sxs-lookup"><span data-stu-id="63aae-134">Reference</span></span>  
 <xref:System.Data.Sql.SqlNotificationRequest>  
 <span data-ttu-id="63aae-135">Describe la clase <xref:System.Data.Sql.SqlNotificationRequest>, así como todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="63aae-135">Describes the <xref:System.Data.Sql.SqlNotificationRequest> class and all of its members.</span></span>  
  
 <xref:System.Data.SqlClient.SqlDependency>  
 <span data-ttu-id="63aae-136">Describe la clase <xref:System.Data.SqlClient.SqlDependency>, así como todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="63aae-136">Describes the <xref:System.Data.SqlClient.SqlDependency> class and all of its members.</span></span>  
  
 <xref:System.Web.Caching.SqlCacheDependency>  
 <span data-ttu-id="63aae-137">Describe la clase <xref:System.Web.Caching.SqlCacheDependency>, así como todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="63aae-137">Describes the <xref:System.Web.Caching.SqlCacheDependency> class and all of its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63aae-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="63aae-138">See Also</span></span>  
 [<span data-ttu-id="63aae-139">SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="63aae-139">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)  
 [<span data-ttu-id="63aae-140">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="63aae-140">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
