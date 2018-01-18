---
title: "SqlDependency en una aplicación ASP.NET"
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
ms.assetid: ff226ce3-f6b5-47a1-8d22-dc78b67e07f5
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 3481d0f0be5a52b33125e2a92849f402cce82d93
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="sqldependency-in-an-aspnet-application"></a><span data-ttu-id="134b6-102">SqlDependency en una aplicación ASP.NET</span><span class="sxs-lookup"><span data-stu-id="134b6-102">SqlDependency in an ASP.NET Application</span></span>
<span data-ttu-id="134b6-103">En el ejemplo de esta sección se muestra cómo utilizar <xref:System.Data.SqlClient.SqlDependency> de forma indirecta aprovechando el objeto <xref:System.Web.Caching.SqlCacheDependency> de ASP:NET.</span><span class="sxs-lookup"><span data-stu-id="134b6-103">The example in this section shows how to use <xref:System.Data.SqlClient.SqlDependency> indirectly by leveraging the ASP.NET <xref:System.Web.Caching.SqlCacheDependency> object.</span></span> <span data-ttu-id="134b6-104">El objeto <xref:System.Web.Caching.SqlCacheDependency> utiliza <xref:System.Data.SqlClient.SqlDependency> para escuchar notificaciones y de actualizar correctamente la caché.</span><span class="sxs-lookup"><span data-stu-id="134b6-104">The <xref:System.Web.Caching.SqlCacheDependency> object uses a <xref:System.Data.SqlClient.SqlDependency> to listen for notifications and correctly update the cache.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="134b6-105">El código de ejemplo se da por supuesto que ha habilitado las notificaciones de consulta mediante la ejecución de las secuencias de comandos en [Enabling Query Notifications](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md).</span><span class="sxs-lookup"><span data-stu-id="134b6-105">The sample code assumes that you have enabled query notifications by executing the scripts in [Enabling Query Notifications](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md).</span></span>  
  
## <a name="about-the-sample-application"></a><span data-ttu-id="134b6-106">Acerca de la aplicación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="134b6-106">About the Sample Application</span></span>  
 <span data-ttu-id="134b6-107">La aplicación de ejemplo utiliza una sola página Web ASP.NET para mostrar información de producto de la **AdventureWorks** base de datos de SQL Server en un <xref:System.Web.UI.WebControls.GridView> control.</span><span class="sxs-lookup"><span data-stu-id="134b6-107">The sample application uses a single ASP.NET Web page to display product information from the **AdventureWorks** SQL Server database in a <xref:System.Web.UI.WebControls.GridView> control.</span></span> <span data-ttu-id="134b6-108">Cuando se carga la página, el código escribe la hora actual en un control <xref:System.Web.UI.WebControls.Label>.</span><span class="sxs-lookup"><span data-stu-id="134b6-108">When the page loads, the code writes the current time to a <xref:System.Web.UI.WebControls.Label> control.</span></span> <span data-ttu-id="134b6-109">A continuación, se define un objeto <xref:System.Web.Caching.SqlCacheDependency> y se establecen las propiedades del objeto <xref:System.Web.Caching.Cache> para almacenar los datos de la caché durante tres minutos como máximo.</span><span class="sxs-lookup"><span data-stu-id="134b6-109">It then defines a <xref:System.Web.Caching.SqlCacheDependency> object and sets properties on the <xref:System.Web.Caching.Cache> object to store the cache data for up to three minutes.</span></span> <span data-ttu-id="134b6-110">Entonces el código se conecta a la base de datos y recupera los datos.</span><span class="sxs-lookup"><span data-stu-id="134b6-110">The code then connects to the database and retrieves the data.</span></span> <span data-ttu-id="134b6-111">Cuando la página está cargada y la aplicación se está ejecutando, ASP.NET recuperará datos de la caché, lo cual podrá comprobar si observa que la hora de la página no cambia.</span><span class="sxs-lookup"><span data-stu-id="134b6-111">When the page is loaded and the application is running ASP.NET will retrieve data from the cache, which you can verify by noting that the time on the page does not change.</span></span> <span data-ttu-id="134b6-112">Si los datos que se supervisan cambian, ASP.NET invalida la caché y vuelve a llenar el control `GridView` con datos nuevos, actualizando la hora que se muestra en el control `Label`.</span><span class="sxs-lookup"><span data-stu-id="134b6-112">If the data being monitored changes, ASP.NET invalidates the cache and repopulate the `GridView` control with fresh data, updating the time displayed in the `Label` control.</span></span>  
  
## <a name="creating-the-sample-application"></a><span data-ttu-id="134b6-113">Crear la aplicación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="134b6-113">Creating the Sample Application</span></span>  
 <span data-ttu-id="134b6-114">Para crear y ejecutar la aplicación de ejemplo, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="134b6-114">Follow these steps to create and run the sample application:</span></span>  
  
1.  <span data-ttu-id="134b6-115">Cree un nuevo sitio web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="134b6-115">Create a new ASP.NET Web site.</span></span>  
  
2.  <span data-ttu-id="134b6-116">Agregue un control <xref:System.Web.UI.WebControls.Label> y <xref:System.Web.UI.WebControls.GridView> a la página Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="134b6-116">Add a <xref:System.Web.UI.WebControls.Label> and a <xref:System.Web.UI.WebControls.GridView> control to the Default.aspx page.</span></span>  
  
3.  <span data-ttu-id="134b6-117">Abra el módulo de clase de la página y agregue las siguientes directivas:</span><span class="sxs-lookup"><span data-stu-id="134b6-117">Open the page's class module and add the following directives:</span></span>  
  
    ```vb  
    Option Strict On  
    Option Explicit On  
  
    Imports System.Data.SqlClient  
    ```  
  
    ```csharp  
    using System.Data.SqlClient;  
    using System.Web.Caching;  
    ```  
  
4.  <span data-ttu-id="134b6-118">Agregue el siguiente código al evento `Page_Load` de la página:</span><span class="sxs-lookup"><span data-stu-id="134b6-118">Add the following code in the page's `Page_Load` event:</span></span>  
  
     [!code-csharp[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#1)]
     [!code-vb[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#1)]  
  
5.  <span data-ttu-id="134b6-119">Agregue dos métodos auxiliares: `GetConnectionString` y `GetSQL`.</span><span class="sxs-lookup"><span data-stu-id="134b6-119">Add two helper methods, `GetConnectionString` and `GetSQL`.</span></span> <span data-ttu-id="134b6-120">La cadena de conexión definida utiliza seguridad integrada.</span><span class="sxs-lookup"><span data-stu-id="134b6-120">The connection string defined uses integrated security.</span></span> <span data-ttu-id="134b6-121">Debe comprobar que la cuenta que está usando tiene los permisos de base de datos necesarios y que la base de datos de ejemplo, **AdventureWorks**, tiene habilitadas las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="134b6-121">You will need to verify that the account you are using has the necessary database permissions and that the sample database, **AdventureWorks**, has notifications enabled.</span></span> <span data-ttu-id="134b6-122">Para obtener más información, consulte [especial consideraciones al usar notificaciones de consulta](http://msdn.microsoft.com/en-us/a83c8dc8-4fb9-4ffd-a2a5-c07cf4a203c7).</span><span class="sxs-lookup"><span data-stu-id="134b6-122">For more information, see [Special Considerations When Using Query Notifications](http://msdn.microsoft.com/en-us/a83c8dc8-4fb9-4ffd-a2a5-c07cf4a203c7).</span></span>  
  
     [!code-csharp[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#2)]
     [!code-vb[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#2)]  
  
### <a name="testing-the-application"></a><span data-ttu-id="134b6-123">Probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="134b6-123">Testing the Application</span></span>  
 <span data-ttu-id="134b6-124">La aplicación almacena en caché los datos mostrados en el formulario web y los actualiza cada tres minutos si no hay ninguna actividad</span><span class="sxs-lookup"><span data-stu-id="134b6-124">The application caches the data displayed on the Web form and refreshes it every three minutes if there is no activity.</span></span> <span data-ttu-id="134b6-125">Si se produce un cambio en la base de datos, la caché se actualiza inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="134b6-125">If a change occurs to the database, the cache is refreshed immediately.</span></span> <span data-ttu-id="134b6-126">Ejecute la aplicación desde Visual Studio, que carga la página en el explorador.</span><span class="sxs-lookup"><span data-stu-id="134b6-126">Run the application from Visual Studio, which loads the page into the browser.</span></span> <span data-ttu-id="134b6-127">La hora de actualización de la caché que se muestra indica la hora de la última actualización.</span><span class="sxs-lookup"><span data-stu-id="134b6-127">The cache refresh time displayed indicates when the cache was last refreshed.</span></span> <span data-ttu-id="134b6-128">Espere tres minutos y, a continuación, actualice la página, lo que dará lugar a un evento postback de datos.</span><span class="sxs-lookup"><span data-stu-id="134b6-128">Wait three minutes, and then refresh the page, causing a postback event to occur.</span></span> <span data-ttu-id="134b6-129">Observe que la hora que se muestra en la página ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="134b6-129">Note that the time displayed on the page has changed.</span></span> <span data-ttu-id="134b6-130">Si actualiza la página sin esperar los tres minutos, la hora mostrada será la misma.</span><span class="sxs-lookup"><span data-stu-id="134b6-130">If you refresh the page in less than three minutes, the time displayed on the page will remain the same.</span></span>  
  
 <span data-ttu-id="134b6-131">A continuación, actualice los datos de la base de datos mediante un comando UPDATE deTransact-SQL y actualice la página.</span><span class="sxs-lookup"><span data-stu-id="134b6-131">Now update the data in the database, using a Transact-SQL UPDATE command and refresh the page.</span></span> <span data-ttu-id="134b6-132">La hora que se muestra indica ahora que la caché se ha actualizado con los datos nuevos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="134b6-132">The time displayed now indicates that the cache was refreshed with the new data from the database.</span></span> <span data-ttu-id="134b6-133">Tenga en cuenta que, aunque la caché está actualizada, la hora que se muestra en la página no cambia hasta que se produce un evento postback de datos.</span><span class="sxs-lookup"><span data-stu-id="134b6-133">Note that although the cache is updated, the time displayed on the page does not change until a postback event occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="134b6-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="134b6-134">See Also</span></span>  
 [<span data-ttu-id="134b6-135">Notificaciones de consulta en SQL Server</span><span class="sxs-lookup"><span data-stu-id="134b6-135">Query Notifications in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)  
 [<span data-ttu-id="134b6-136">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="134b6-136">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
