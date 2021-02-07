---
description: 'Más información acerca de: SqlDependency en una aplicación ASP.NET'
title: SqlDependency en una aplicación ASP.NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ff226ce3-f6b5-47a1-8d22-dc78b67e07f5
ms.openlocfilehash: 686586af834884f97ff8e62fdc792b3cdc23f507
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767029"
---
# <a name="sqldependency-in-an-aspnet-application"></a><span data-ttu-id="fb5e5-103">SqlDependency en una aplicación ASP.NET</span><span class="sxs-lookup"><span data-stu-id="fb5e5-103">SqlDependency in an ASP.NET Application</span></span>

<span data-ttu-id="fb5e5-104">En el ejemplo de esta sección se muestra cómo usar <xref:System.Data.SqlClient.SqlDependency> indirectamente aprovechando el objeto <xref:System.Web.Caching.SqlCacheDependency> de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="fb5e5-104">The example in this section shows how to use <xref:System.Data.SqlClient.SqlDependency> indirectly by leveraging the ASP.NET <xref:System.Web.Caching.SqlCacheDependency> object.</span></span> <span data-ttu-id="fb5e5-105">El objeto <xref:System.Web.Caching.SqlCacheDependency> usa <xref:System.Data.SqlClient.SqlDependency> para escuchar notificaciones y actualizar correctamente la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="fb5e5-105">The <xref:System.Web.Caching.SqlCacheDependency> object uses a <xref:System.Data.SqlClient.SqlDependency> to listen for notifications and correctly update the cache.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fb5e5-106">En el código de ejemplo se supone que ha habilitado las notificaciones de consulta ejecutando los scripts en [habilitando las notificaciones de consulta](enabling-query-notifications.md).</span><span class="sxs-lookup"><span data-stu-id="fb5e5-106">The sample code assumes that you have enabled query notifications by executing the scripts in [Enabling Query Notifications](enabling-query-notifications.md).</span></span>  
  
## <a name="about-the-sample-application"></a><span data-ttu-id="fb5e5-107">Acerca de la aplicación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="fb5e5-107">About the Sample Application</span></span>  

 <span data-ttu-id="fb5e5-108">La aplicación de ejemplo usa una única página web de ASP.NET para mostrar información de producto de la base de datos **AdventureWorks** de SQL Server en un control <xref:System.Web.UI.WebControls.GridView>.</span><span class="sxs-lookup"><span data-stu-id="fb5e5-108">The sample application uses a single ASP.NET Web page to display product information from the **AdventureWorks** SQL Server database in a <xref:System.Web.UI.WebControls.GridView> control.</span></span> <span data-ttu-id="fb5e5-109">Cuando se carga la página, el código escribe la hora actual en un control de <xref:System.Web.UI.WebControls.Label>.</span><span class="sxs-lookup"><span data-stu-id="fb5e5-109">When the page loads, the code writes the current time to a <xref:System.Web.UI.WebControls.Label> control.</span></span> <span data-ttu-id="fb5e5-110">A continuación, define un objeto de <xref:System.Web.Caching.SqlCacheDependency> y establece propiedades en el objeto <xref:System.Web.Caching.Cache> para almacenar los datos de la memoria caché durante un máximo de tres minutos.</span><span class="sxs-lookup"><span data-stu-id="fb5e5-110">It then defines a <xref:System.Web.Caching.SqlCacheDependency> object and sets properties on the <xref:System.Web.Caching.Cache> object to store the cache data for up to three minutes.</span></span> <span data-ttu-id="fb5e5-111">Después, el código se conecta a la base de datos y recupera los datos.</span><span class="sxs-lookup"><span data-stu-id="fb5e5-111">The code then connects to the database and retrieves the data.</span></span> <span data-ttu-id="fb5e5-112">Cuando se carga la página y la aplicación se ejecuta, ASP.NET recuperará los datos de la memoria caché, lo cual se puede comprobar observando que la hora de la página no cambia.</span><span class="sxs-lookup"><span data-stu-id="fb5e5-112">When the page is loaded and the application is running ASP.NET will retrieve data from the cache, which you can verify by noting that the time on the page does not change.</span></span> <span data-ttu-id="fb5e5-113">Si los datos que se supervisan cambian, ASP.NET invalida la memoria caché y vuelve a rellenar el control `GridView` con datos nuevos, actualizando la hora que se muestra en el control `Label`.</span><span class="sxs-lookup"><span data-stu-id="fb5e5-113">If the data being monitored changes, ASP.NET invalidates the cache and repopulate the `GridView` control with fresh data, updating the time displayed in the `Label` control.</span></span>  
  
## <a name="creating-the-sample-application"></a><span data-ttu-id="fb5e5-114">Crear la aplicación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="fb5e5-114">Creating the Sample Application</span></span>  

 <span data-ttu-id="fb5e5-115">Siga estos pasos para crear y ejecutar la aplicación de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fb5e5-115">Follow these steps to create and run the sample application:</span></span>  
  
1. <span data-ttu-id="fb5e5-116">Cree un nuevo sitio web de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="fb5e5-116">Create a new ASP.NET Web site.</span></span>  
  
2. <span data-ttu-id="fb5e5-117">Agregue un control <xref:System.Web.UI.WebControls.Label> y <xref:System.Web.UI.WebControls.GridView> a la página Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="fb5e5-117">Add a <xref:System.Web.UI.WebControls.Label> and a <xref:System.Web.UI.WebControls.GridView> control to the Default.aspx page.</span></span>  
  
3. <span data-ttu-id="fb5e5-118">Abra el módulo de clase de la página y agregue las siguientes directivas:</span><span class="sxs-lookup"><span data-stu-id="fb5e5-118">Open the page's class module and add the following directives:</span></span>  
  
    ```vb  
    Option Strict On  
    Option Explicit On  
  
    Imports System.Data.SqlClient  
    ```  
  
    ```csharp  
    using System.Data.SqlClient;  
    using System.Web.Caching;  
    ```  
  
4. <span data-ttu-id="fb5e5-119">Agregue el siguiente código en el evento `Page_Load` de la página:</span><span class="sxs-lookup"><span data-stu-id="fb5e5-119">Add the following code in the page's `Page_Load` event:</span></span>  
  
     [!code-csharp[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#1)]
     [!code-vb[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#1)]  
  
5. <span data-ttu-id="fb5e5-120">Agregue dos métodos del asistente, `GetConnectionString` y `GetSQL`.</span><span class="sxs-lookup"><span data-stu-id="fb5e5-120">Add two helper methods, `GetConnectionString` and `GetSQL`.</span></span> <span data-ttu-id="fb5e5-121">La cadena de conexión definida usa seguridad integrada.</span><span class="sxs-lookup"><span data-stu-id="fb5e5-121">The connection string defined uses integrated security.</span></span> <span data-ttu-id="fb5e5-122">Debe comprobar que la cuenta que usa dispone de los permisos de base de datos necesarios y que la base de datos de ejemplo, **AdventureWorks**, tiene habilitadas las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="fb5e5-122">You will need to verify that the account you are using has the necessary database permissions and that the sample database, **AdventureWorks**, has notifications enabled.</span></span>
  
     [!code-csharp[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#2)]
     [!code-vb[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#2)]  
  
### <a name="testing-the-application"></a><span data-ttu-id="fb5e5-123">Probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="fb5e5-123">Testing the Application</span></span>  

 <span data-ttu-id="fb5e5-124">La aplicación almacena en caché los datos que se muestran en el formulario web y los actualiza cada tres minutos si no hay ninguna actividad.</span><span class="sxs-lookup"><span data-stu-id="fb5e5-124">The application caches the data displayed on the Web form and refreshes it every three minutes if there is no activity.</span></span> <span data-ttu-id="fb5e5-125">Si se produce un cambio en la base de datos, la caché se actualiza inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="fb5e5-125">If a change occurs to the database, the cache is refreshed immediately.</span></span> <span data-ttu-id="fb5e5-126">Ejecute la aplicación desde Visual Studio, que carga la página en el explorador.</span><span class="sxs-lookup"><span data-stu-id="fb5e5-126">Run the application from Visual Studio, which loads the page into the browser.</span></span> <span data-ttu-id="fb5e5-127">La hora de actualización de la caché que se muestra indica cuándo se actualizó la memoria caché por última vez.</span><span class="sxs-lookup"><span data-stu-id="fb5e5-127">The cache refresh time displayed indicates when the cache was last refreshed.</span></span> <span data-ttu-id="fb5e5-128">Espere tres minutos y, a continuación, actualice la página, lo que hará que se produzca un evento de postback.</span><span class="sxs-lookup"><span data-stu-id="fb5e5-128">Wait three minutes, and then refresh the page, causing a postback event to occur.</span></span> <span data-ttu-id="fb5e5-129">Observe que la hora que se muestra en la página ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="fb5e5-129">Note that the time displayed on the page has changed.</span></span> <span data-ttu-id="fb5e5-130">Si actualiza la página en menos de tres minutos, la hora que se muestra en la página seguirá siendo la misma.</span><span class="sxs-lookup"><span data-stu-id="fb5e5-130">If you refresh the page in less than three minutes, the time displayed on the page will remain the same.</span></span>  
  
 <span data-ttu-id="fb5e5-131">Ahora, actualice los datos de la base de datos mediante un comando UPDATE de Transact-SQL y actualice la página.</span><span class="sxs-lookup"><span data-stu-id="fb5e5-131">Now update the data in the database, using a Transact-SQL UPDATE command and refresh the page.</span></span> <span data-ttu-id="fb5e5-132">La hora que se muestra ahora indica que la memoria caché se ha actualizado con los nuevos datos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="fb5e5-132">The time displayed now indicates that the cache was refreshed with the new data from the database.</span></span> <span data-ttu-id="fb5e5-133">Tenga en cuenta que aunque la memoria caché se actualiza, la hora que se muestra en la página no cambia hasta que se produce un evento de postback.</span><span class="sxs-lookup"><span data-stu-id="fb5e5-133">Note that although the cache is updated, the time displayed on the page does not change until a postback event occurs.</span></span>  

## <a name="distributed-cache-synchronization-using-sql-dependency"></a><span data-ttu-id="fb5e5-134">Sincronización de caché distribuida mediante la dependencia de SQL</span><span class="sxs-lookup"><span data-stu-id="fb5e5-134">Distributed cache synchronization using SQL Dependency</span></span>

<span data-ttu-id="fb5e5-135">Algunas de las memorias caché distribuidas de terceros, como [NCache](https://www.alachisoft.com/ncache) , proporcionan compatibilidad para sincronizar la base de datos SQL y la memoria caché mediante la [dependencia de SQL](https://www.alachisoft.com/resources/docs/ncache/prog-guide/sql-dependency.html).</span><span class="sxs-lookup"><span data-stu-id="fb5e5-135">Some of the third-party distributed caches such as [NCache](https://www.alachisoft.com/ncache) provide support to synchronize the SQL database and cache using [SQL Dependency](https://www.alachisoft.com/resources/docs/ncache/prog-guide/sql-dependency.html).</span></span> <span data-ttu-id="fb5e5-136">Para obtener más información y un ejemplo de implementación de código fuente, vea [ejemplo de dependencia SQL de caché distribuida](https://github.com/Alachisoft/NCache-Samples/tree/master/dotnet/Dependencies/SQLDependency).</span><span class="sxs-lookup"><span data-stu-id="fb5e5-136">For more information and an example source code implementation, see [Distributed cache SQL Dependency sample](https://github.com/Alachisoft/NCache-Samples/tree/master/dotnet/Dependencies/SQLDependency).</span></span>

## <a name="see-also"></a><span data-ttu-id="fb5e5-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb5e5-137">See also</span></span>

- [<span data-ttu-id="fb5e5-138">Notificaciones de consulta en SQL Server</span><span class="sxs-lookup"><span data-stu-id="fb5e5-138">Query Notifications in SQL Server</span></span>](query-notifications-in-sql-server.md)
- [<span data-ttu-id="fb5e5-139">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="fb5e5-139">ADO.NET Overview</span></span>](../ado-net-overview.md)
