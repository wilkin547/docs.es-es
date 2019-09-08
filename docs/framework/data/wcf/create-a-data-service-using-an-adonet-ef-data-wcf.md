---
title: Procedimiento Crear un servicio de datos mediante un origen de datos de ADO.NET Entity Framework (WCF Data Services)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, Entity Framework
ms.assetid: 6d11fec8-0108-42f5-8719-2a7866d04428
ms.openlocfilehash: ae4176fd986f870523e44a11eee48850e2dddd7c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70791074"
---
# <a name="how-to-create-a-data-service-using-an-adonet-entity-framework-data-source-wcf-data-services"></a><span data-ttu-id="2efff-102">Procedimiento Crear un servicio de datos mediante un origen de datos de ADO.NET Entity Framework (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="2efff-102">How to: Create a Data Service Using an ADO.NET Entity Framework Data Source (WCF Data Services)</span></span>

<span data-ttu-id="2efff-103">WCF Data Services expone los datos de entidad como un servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="2efff-103">WCF Data Services exposes entity data as a data service.</span></span> <span data-ttu-id="2efff-104">El ADO.net[!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] proporciona estos datos de entidad cuando el origen de datos es una base de datos relacional.</span><span class="sxs-lookup"><span data-stu-id="2efff-104">This entity data is provided by the ADO.NET[!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] when the data source is a relational database.</span></span> <span data-ttu-id="2efff-105">En este tema se muestra cómo crear un [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]modelo de datos basado en en una aplicación Web de Visual Studio basada en una base de datos existente y cómo usar este modelo de datos para crear un nuevo servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="2efff-105">This topic shows you how to create an [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]-based data model in a Visual Studio Web application that is based on an existing database and use this data model to create a new data service.</span></span>

<span data-ttu-id="2efff-106">También proporciona una herramienta de línea de comandos que puede generar [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] un modelo fuera de un proyecto de Visual Studio. [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2efff-106">The [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] also provides a command line tool that can generate an [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] model outside of a Visual Studio project.</span></span> <span data-ttu-id="2efff-107">Para obtener más información, consulte [Cómo Use EdmGen. exe para generar los archivos](../adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)de asignación y de modelo.</span><span class="sxs-lookup"><span data-stu-id="2efff-107">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>

## <a name="to-add-an-entity-framework-model-that-is-based-on-an-existing-database-to-an-existing-web-application"></a><span data-ttu-id="2efff-108">Para agregar un modelo de Entity Framework que está basado en una base de datos existente a una aplicación web existente</span><span class="sxs-lookup"><span data-stu-id="2efff-108">To add an Entity Framework model that is based on an existing database to an existing Web application</span></span>

1. <span data-ttu-id="2efff-109">En el menú **proyecto** , haga clic en **Agregar** > **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="2efff-109">On the **Project** menu, click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="2efff-110">En el panel **plantillas** , haga clic en la categoría de **datos** y, a continuación, seleccione **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="2efff-110">In the **Templates** pane, click the **Data** category, and then select **ADO.NET Entity Data Model**.</span></span>

3. <span data-ttu-id="2efff-111">Escriba el nombre del modelo y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2efff-111">Enter the model name and then click **Add**.</span></span>

     <span data-ttu-id="2efff-112">Se muestra la primera página del Asistente para Entity Data Model.</span><span class="sxs-lookup"><span data-stu-id="2efff-112">The first page of the Entity Data Model Wizard is displayed.</span></span>

4. <span data-ttu-id="2efff-113">En el cuadro de diálogo **elegir contenido del modelo** , seleccione **generar desde la base de datos**.</span><span class="sxs-lookup"><span data-stu-id="2efff-113">In the **Choose Model Contents** dialog box, select **Generate from database**.</span></span> <span data-ttu-id="2efff-114">A continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2efff-114">Then click **Next**.</span></span>

5. <span data-ttu-id="2efff-115">Haga clic en el botón **nueva conexión** .</span><span class="sxs-lookup"><span data-stu-id="2efff-115">Click the **New Connection** button.</span></span>

6. <span data-ttu-id="2efff-116">En el cuadro de diálogo **propiedades de conexión** , escriba el nombre del servidor, seleccione el método de autenticación, escriba el nombre de la base de datos y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2efff-116">In the **Connection Properties** dialog box, type your server name, select the authentication method, type the database name, and then click **OK**.</span></span>

     <span data-ttu-id="2efff-117">El cuadro de diálogo **elegir la conexión de datos** se actualiza con la configuración de la conexión de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="2efff-117">The **Choose Your Data Connection** dialog box is updated with your database connection settings.</span></span>

7. <span data-ttu-id="2efff-118">Asegúrese de que la casilla **Guardar configuración de conexión de entidad en App. config como:** está activada.</span><span class="sxs-lookup"><span data-stu-id="2efff-118">Ensure that the **Save entity connection settings in App.Config as:** checkbox is checked.</span></span> <span data-ttu-id="2efff-119">A continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2efff-119">Then click **Next**.</span></span>

8. <span data-ttu-id="2efff-120">En el cuadro de diálogo **Elija los objetos de base** de datos, seleccione todos los objetos de base de datos que va a exponer en el servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="2efff-120">In the **Choose Your Database Objects** dialog box, select all of database objects that you plan to expose in the data service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2efff-121">El servicio de datos no expone automáticamente los objetos incluidos en el modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="2efff-121">Objects included in the data model are not automatically exposed by the data service.</span></span> <span data-ttu-id="2efff-122">El propio servicio debe exponerlos explícitamente.</span><span class="sxs-lookup"><span data-stu-id="2efff-122">They must be explicitly exposed by the service itself.</span></span> <span data-ttu-id="2efff-123">Para obtener más información, vea [configurar el servicio de datos](configuring-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2efff-123">For more information, see [Configuring the Data Service](configuring-the-data-service-wcf-data-services.md).</span></span>

9. <span data-ttu-id="2efff-124">Haga clic en **Finalizar** para completar el asistente.</span><span class="sxs-lookup"><span data-stu-id="2efff-124">Click **Finish** to complete the wizard.</span></span>

     <span data-ttu-id="2efff-125">Con esto se crea un modelo de datos predeterminado basado en una base de datos específica.</span><span class="sxs-lookup"><span data-stu-id="2efff-125">This creates a default data model based on the specific database.</span></span> <span data-ttu-id="2efff-126">[!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] permite personalizar el modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="2efff-126">The [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] enables to customize the data model.</span></span> <span data-ttu-id="2efff-127">Para obtener más información, vea [Entity Data Model herramientas tareas](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738480(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="2efff-127">For more information, see [Entity Data Model Tools Tasks](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738480(v=vs.100)).</span></span>

## <a name="to-create-the-data-service-by-using-the-new-data-model"></a><span data-ttu-id="2efff-128">Para crear el servicio de datos usando el nuevo modelo de datos</span><span class="sxs-lookup"><span data-stu-id="2efff-128">To create the data service by using the new data model</span></span>

1. <span data-ttu-id="2efff-129">En Visual Studio, abra el archivo .edmx que representa el modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="2efff-129">In Visual Studio, open the .edmx file that represents the data model.</span></span>

2. <span data-ttu-id="2efff-130">En el **Explorador de modelos**, haga clic con el botón derecho en el modelo, haga clic en **propiedades**y, a continuación, anote el nombre del contenedor de entidades.</span><span class="sxs-lookup"><span data-stu-id="2efff-130">In the **Model Browser**, right-click the model, click **Properties**, and then note the name of the entity container.</span></span>

3. <span data-ttu-id="2efff-131">En **Explorador de soluciones**, haga clic con el botón secundario en el nombre del proyecto ASP.net y, a continuación, haga clic en **Agregar** > **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="2efff-131">In **Solution Explorer**, right-click the name of your ASP.NET project, and then click **Add** > **New Item**.</span></span>

4. <span data-ttu-id="2efff-132">En el cuadro de diálogo **Agregar nuevo elemento** , seleccione la plantilla **servicio de datos de WCF** en la categoría **Web** .</span><span class="sxs-lookup"><span data-stu-id="2efff-132">In the **Add New Item** dialog box, select the **WCF Data Service** template in the **Web** category.</span></span>

   ![Plantilla de elemento de servicio de datos de WCF en Visual Studio 2015](media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="2efff-134">La plantilla de **servicio de datos de WCF** está disponible en visual Studio 2015, pero no en visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="2efff-134">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017.</span></span>

5. <span data-ttu-id="2efff-135">Proporcione un nombre para el servicio y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2efff-135">Supply a name for the service, and then click **OK**.</span></span>

     <span data-ttu-id="2efff-136">Visual Studio crea los archivos de código y marcado XML para el nuevo servicio.</span><span class="sxs-lookup"><span data-stu-id="2efff-136">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="2efff-137">De forma predeterminada, se abre la ventana del editor de código.</span><span class="sxs-lookup"><span data-stu-id="2efff-137">By default, the code-editor window opens.</span></span>

6. <span data-ttu-id="2efff-138">En el código para el servicio de datos, reemplace el comentario `/* TODO: put your data source class name here */` de la definición de la clase que define el servicio de datos por el tipo que hereda de la clase <xref:System.Data.Objects.ObjectContext> y que es el contenedor de entidades del modelo de datos, que anotó en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="2efff-138">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that inherits from the <xref:System.Data.Objects.ObjectContext> class and that is the entity container of the data model, which was noted in step 2.</span></span>

7. <span data-ttu-id="2efff-139">En el código del servicio de datos, permita a los clientes autorizados tener acceso a los conjuntos de entidades que expone el servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="2efff-139">In the code for the data service, enable authorized clients to access the entity sets that the data service exposes.</span></span> <span data-ttu-id="2efff-140">Para obtener más información, vea [crear el servicio de datos](creating-the-data-service.md).</span><span class="sxs-lookup"><span data-stu-id="2efff-140">For more information, see [Creating the Data Service](creating-the-data-service.md).</span></span>

8. <span data-ttu-id="2efff-141">Para probar el servicio de datos Northwind. SVC mediante un explorador Web, siga las instrucciones del tema [acceso al servicio desde un explorador Web](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span><span class="sxs-lookup"><span data-stu-id="2efff-141">To test the Northwind.svc data service by using a Web browser, follow the instructions in the topic [Accessing the Service from a Web Browser](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2efff-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="2efff-142">See also</span></span>

- [<span data-ttu-id="2efff-143">Definir Servicios de datos de WCF</span><span class="sxs-lookup"><span data-stu-id="2efff-143">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)
- [<span data-ttu-id="2efff-144">Proveedores de Data Services</span><span class="sxs-lookup"><span data-stu-id="2efff-144">Data Services Providers</span></span>](data-services-providers-wcf-data-services.md)
- [<span data-ttu-id="2efff-145">Cómo: Crear un servicio de datos mediante el proveedor de reflexión</span><span class="sxs-lookup"><span data-stu-id="2efff-145">How to: Create a Data Service Using the Reflection Provider</span></span>](create-a-data-service-using-rp-wcf-data-services.md)
- [<span data-ttu-id="2efff-146">Cómo: Crear un servicio de datos mediante un origen de datos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="2efff-146">How to: Create a Data Service Using a LINQ to SQL Data Source</span></span>](create-a-data-service-using-linq-to-sql-wcf.md)
