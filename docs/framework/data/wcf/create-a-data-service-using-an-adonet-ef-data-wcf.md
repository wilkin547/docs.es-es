---
title: "Cómo: Crear un servicio de datos utilizando un origen de datos de ADO.NET Entity Framework (Data Services de WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, Entity Framework
ms.assetid: 6d11fec8-0108-42f5-8719-2a7866d04428
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e90b11800685707460171e5e2d250ef757979c44
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-a-data-service-using-an-adonet-entity-framework-data-source-wcf-data-services"></a><span data-ttu-id="1d65a-102">Cómo: Crear un servicio de datos utilizando un origen de datos de ADO.NET Entity Framework (Data Services de WCF)</span><span class="sxs-lookup"><span data-stu-id="1d65a-102">How to: Create a Data Service Using an ADO.NET Entity Framework Data Source (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="1d65a-103"> expone los datos de entidad como servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="1d65a-103"> exposes entity data as a data service.</span></span> <span data-ttu-id="1d65a-104">Estos datos de entidad proporciona la [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] cuando el origen de datos es una base de datos relacional.</span><span class="sxs-lookup"><span data-stu-id="1d65a-104">This entity data is provided by the [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)][!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] when the data source is a relational database.</span></span> <span data-ttu-id="1d65a-105">En este tema se muestra cómo crear un modelo de datos basado en [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] en una aplicación web de [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] que está basada en una base de datos existente y cómo usar este modelo de datos para crear un nuevo servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="1d65a-105">This topic shows you how to create an [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]-based data model in a [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] Web application that is based on an existing database and use this data model to create a new data service.</span></span>  
  
 <span data-ttu-id="1d65a-106">[!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] también proporciona una herramienta de línea de comandos que puede generar un modelo [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] fuera de un proyecto de [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1d65a-106">The [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] also provides a command line tool that can generate an [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] model outside of a [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] project.</span></span> <span data-ttu-id="1d65a-107">Para obtener más información, consulte [Cómo: usar EdmGen.exe para generar los archivos de asignación y modelo](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="1d65a-107">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
### <a name="to-add-an-entity-framework-model-that-is-based-on-an-existing-database-to-an-existing-web-application"></a><span data-ttu-id="1d65a-108">Para agregar un modelo de Entity Framework que está basado en una base de datos existente a una aplicación web existente</span><span class="sxs-lookup"><span data-stu-id="1d65a-108">To add an Entity Framework model that is based on an existing database to an existing Web application</span></span>  
  
1.  <span data-ttu-id="1d65a-109">En el **proyecto** menú, haga clic en **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="1d65a-109">On the **Project** menu, click **Add new item**.</span></span>  
  
2.  <span data-ttu-id="1d65a-110">En el **plantillas** panel, haga clic en el **datos** categoría y, a continuación, seleccione **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="1d65a-110">In the **Templates** pane, click the **Data** category, and then select **ADO.NET Entity Data Model**.</span></span>  
  
3.  <span data-ttu-id="1d65a-111">Escriba el nombre del modelo y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="1d65a-111">Type the model name and then click **Add**.</span></span>  
  
     <span data-ttu-id="1d65a-112">Se muestra la primera página del Asistente para [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1d65a-112">The first page of the [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] Wizard is displayed.</span></span>  
  
4.  <span data-ttu-id="1d65a-113">En el **Elegir contenido del modelo** cuadro de diálogo, seleccione **generar desde la base de datos**.</span><span class="sxs-lookup"><span data-stu-id="1d65a-113">In the **Choose Model Contents** dialog box, select **Generate from database**.</span></span> <span data-ttu-id="1d65a-114">Después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1d65a-114">Then click **Next**.</span></span>  
  
5.  <span data-ttu-id="1d65a-115">Haga clic en el **nueva conexión** botón.</span><span class="sxs-lookup"><span data-stu-id="1d65a-115">Click the **New Connection** button.</span></span>  
  
6.  <span data-ttu-id="1d65a-116">En el **propiedades de conexión** cuadro de diálogo, escriba el nombre del servidor, seleccione el método de autenticación, escriba el nombre de la base de datos y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1d65a-116">In the **Connection Properties** dialog box, type your server name, select the authentication method, type the database name, and then click **OK**.</span></span>  
  
     <span data-ttu-id="1d65a-117">El **elegir la conexión de datos**cuadro de diálogo se actualiza con la configuración de conexión de base de datos.</span><span class="sxs-lookup"><span data-stu-id="1d65a-117">The **Choose Your Data Connection**s dialog box is updated with your database connection settings.</span></span>  
  
7.  <span data-ttu-id="1d65a-118">Asegúrese de que el **Guardar configuración de conexión de entidad en App.Config como:** casilla de verificación está activada.</span><span class="sxs-lookup"><span data-stu-id="1d65a-118">Ensure that the **Save entity connection settings in App.Config as:** checkbox is checked.</span></span> <span data-ttu-id="1d65a-119">Después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1d65a-119">Then click **Next**.</span></span>  
  
8.  <span data-ttu-id="1d65a-120">En el **elija los objetos de base de datos** seleccionar todo de base de datos de cuadro de diálogo, objetos que piensa exponer en el servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="1d65a-120">In the **Choose Your Database Objects** dialog box, select all of database objects that you plan to expose in the data service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1d65a-121">El servicio de datos no expone automáticamente los objetos incluidos en el modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="1d65a-121">Objects included in the data model are not automatically exposed by the data service.</span></span> <span data-ttu-id="1d65a-122">El propio servicio debe exponerlos explícitamente.</span><span class="sxs-lookup"><span data-stu-id="1d65a-122">They must be explicitly exposed by the service itself.</span></span> <span data-ttu-id="1d65a-123">Para obtener más información, consulte [configurar el servicio de datos](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="1d65a-123">For more information, see [Configuring the Data Service](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).</span></span>  
  
9. <span data-ttu-id="1d65a-124">Haga clic en **finalizar** para completar el asistente.</span><span class="sxs-lookup"><span data-stu-id="1d65a-124">Click **Finish** to complete the wizard.</span></span>  
  
     <span data-ttu-id="1d65a-125">Con esto se crea un modelo de datos predeterminado basado en una base de datos específica.</span><span class="sxs-lookup"><span data-stu-id="1d65a-125">This creates a default data model based on the specific database.</span></span> <span data-ttu-id="1d65a-126">[!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] permite personalizar el modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="1d65a-126">The [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] enables to customize the data model.</span></span> <span data-ttu-id="1d65a-127">Para obtener más información, consulte [Tareas](http://msdn.microsoft.com/library/7166f1f1-4de8-4bd4-86b5-5e20a2ebaccb).</span><span class="sxs-lookup"><span data-stu-id="1d65a-127">For more information, see [Tasks](http://msdn.microsoft.com/library/7166f1f1-4de8-4bd4-86b5-5e20a2ebaccb).</span></span>  
  
### <a name="to-create-the-data-service-by-using-the-new-data-model"></a><span data-ttu-id="1d65a-128">Para crear el servicio de datos usando el nuevo modelo de datos</span><span class="sxs-lookup"><span data-stu-id="1d65a-128">To create the data service by using the new data model</span></span>  
  
1.  <span data-ttu-id="1d65a-129">En [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], abra el archivo .edmx que representa el modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="1d65a-129">In [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], open the .edmx file that represents the data model.</span></span>  
  
2.  <span data-ttu-id="1d65a-130">En el **Explorador de modelos**, haga clic en el modelo, haga clic en **propiedades**y, a continuación, anote el nombre del contenedor de entidades.</span><span class="sxs-lookup"><span data-stu-id="1d65a-130">In the **Model Browser**, right-click the model, click **Properties**, and then note the name of the entity container.</span></span>  
  
3.  <span data-ttu-id="1d65a-131">En **el Explorador de soluciones**, haga clic en el nombre de su [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] del proyecto y, a continuación, haga clic en **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="1d65a-131">In **Solution Explorer**, right-click the name of your [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] project, and then click **Add New Item**.</span></span>  
  
4.  <span data-ttu-id="1d65a-132">En el **Agregar nuevo elemento** cuadro de diálogo, seleccione **servicio de datos de WCF**.</span><span class="sxs-lookup"><span data-stu-id="1d65a-132">In the **Add New Item** dialog box, select **WCF Data Service**.</span></span>  
  
5.  <span data-ttu-id="1d65a-133">Proporcione un nombre para el servicio y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1d65a-133">Supply a name for the service, and then click **OK**.</span></span>  
  
     [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]<span data-ttu-id="1d65a-134"> crea los archivos de código y marcado XML para el nuevo servicio.</span><span class="sxs-lookup"><span data-stu-id="1d65a-134"> creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="1d65a-135">De forma predeterminada, se abre la ventana del editor de código.</span><span class="sxs-lookup"><span data-stu-id="1d65a-135">By default, the code-editor window opens.</span></span>  
  
6.  <span data-ttu-id="1d65a-136">En el código para el servicio de datos, reemplace el comentario `/* TODO: put your data source class name here */` de la definición de la clase que define el servicio de datos por el tipo que hereda de la clase <xref:System.Data.Objects.ObjectContext> y que es el contenedor de entidades del modelo de datos, que anotó en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="1d65a-136">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that inherits from the <xref:System.Data.Objects.ObjectContext> class and that is the entity container of the data model, which was noted in step 2.</span></span>  
  
7.  <span data-ttu-id="1d65a-137">En el código del servicio de datos, permita a los clientes autorizados tener acceso a los conjuntos de entidades que expone el servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="1d65a-137">In the code for the data service, enable authorized clients to access the entity sets that the data service exposes.</span></span> <span data-ttu-id="1d65a-138">Para obtener más información, consulte [crear el servicio de datos](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span><span class="sxs-lookup"><span data-stu-id="1d65a-138">For more information, see [Creating the Data Service](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span></span>  
  
8.  <span data-ttu-id="1d65a-139">Para probar el servicio de datos Northwind.svc mediante un explorador Web, siga las instrucciones que aparecen en el tema [acceder al servicio desde un explorador Web](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span><span class="sxs-lookup"><span data-stu-id="1d65a-139">To test the Northwind.svc data service by using a Web browser, follow the instructions in the topic [Accessing the Service from a Web Browser](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d65a-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d65a-140">See Also</span></span>  
 [<span data-ttu-id="1d65a-141">Definir Servicios de datos de WCF</span><span class="sxs-lookup"><span data-stu-id="1d65a-141">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 [<span data-ttu-id="1d65a-142">Proveedores de Data Services</span><span class="sxs-lookup"><span data-stu-id="1d65a-142">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [<span data-ttu-id="1d65a-143">Creación de un servicio de datos utilizando el proveedor de reflexión</span><span class="sxs-lookup"><span data-stu-id="1d65a-143">How to: Create a Data Service Using the Reflection Provider</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)  
 [<span data-ttu-id="1d65a-144">Creación de un servicio de datos utilizando un origen de datos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="1d65a-144">How to: Create a Data Service Using a LINQ to SQL Data Source</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)
