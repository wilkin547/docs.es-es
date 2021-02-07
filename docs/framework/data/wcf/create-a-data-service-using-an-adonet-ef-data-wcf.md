---
description: 'Más información acerca de cómo: crear un servicio de datos mediante un origen de datos de ADO.NET Entity Framework (Servicios de datos de WCF)'
title: 'Cómo: Crear un servicio de datos utilizando un origen de datos de ADO.NET Entity Framework (Data Services de WCF)'
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, Entity Framework
ms.assetid: 6d11fec8-0108-42f5-8719-2a7866d04428
ms.openlocfilehash: aea96c3953ec990b5f70a9702961512332330c6e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99766214"
---
# <a name="how-to-create-a-data-service-using-an-adonet-entity-framework-data-source-wcf-data-services"></a><span data-ttu-id="b8ba4-103">Cómo: Crear un servicio de datos utilizando un origen de datos de ADO.NET Entity Framework (Data Services de WCF)</span><span class="sxs-lookup"><span data-stu-id="b8ba4-103">How to: Create a Data Service Using an ADO.NET Entity Framework Data Source (WCF Data Services)</span></span>

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

<span data-ttu-id="b8ba4-104">Servicios de datos de WCF expone los datos de entidad como un servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="b8ba4-104">WCF Data Services exposes entity data as a data service.</span></span> <span data-ttu-id="b8ba4-105">El marco de trabajo ADO. NETEntity proporciona estos datos de entidad cuando el origen de datos es una base de datos relacional.</span><span class="sxs-lookup"><span data-stu-id="b8ba4-105">This entity data is provided by the ADO.NETEntity Framework when the data source is a relational database.</span></span> <span data-ttu-id="b8ba4-106">En este tema se muestra cómo crear un modelo de datos basado en Entity Framework en una aplicación web de Visual Studio que está basada en una base de datos existente y cómo usar este modelo de datos para crear un nuevo servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="b8ba4-106">This topic shows you how to create an Entity Framework-based data model in a Visual Studio Web application that is based on an existing database and use this data model to create a new data service.</span></span>

<span data-ttu-id="b8ba4-107">Entity Framework también proporciona una herramienta de línea de comandos que puede generar un modelo de Entity Framework fuera de un proyecto de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b8ba4-107">The Entity Framework also provides a command line tool that can generate an Entity Framework model outside of a Visual Studio project.</span></span> <span data-ttu-id="b8ba4-108">Para obtener más información, vea [Cómo: usar EdmGen.exe para generar los archivos de asignación y de modelo](../adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="b8ba4-108">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>

## <a name="to-add-an-entity-framework-model-that-is-based-on-an-existing-database-to-an-existing-web-application"></a><span data-ttu-id="b8ba4-109">Para agregar un modelo de Entity Framework que está basado en una base de datos existente a una aplicación web existente</span><span class="sxs-lookup"><span data-stu-id="b8ba4-109">To add an Entity Framework model that is based on an existing database to an existing Web application</span></span>

1. <span data-ttu-id="b8ba4-110">En el menú **proyecto** , haga clic en **Agregar**  >  **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="b8ba4-110">On the **Project** menu, click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="b8ba4-111">En el panel **plantillas** , haga clic en la categoría de **datos** y, a continuación, seleccione **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="b8ba4-111">In the **Templates** pane, click the **Data** category, and then select **ADO.NET Entity Data Model**.</span></span>

3. <span data-ttu-id="b8ba4-112">Escriba el nombre del modelo y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b8ba4-112">Enter the model name and then click **Add**.</span></span>

     <span data-ttu-id="b8ba4-113">Se muestra la primera página del Asistente para Entity Data Model.</span><span class="sxs-lookup"><span data-stu-id="b8ba4-113">The first page of the Entity Data Model Wizard is displayed.</span></span>

4. <span data-ttu-id="b8ba4-114">En el cuadro de diálogo **elegir contenido del modelo** , seleccione **generar desde la base de datos**.</span><span class="sxs-lookup"><span data-stu-id="b8ba4-114">In the **Choose Model Contents** dialog box, select **Generate from database**.</span></span> <span data-ttu-id="b8ba4-115">A continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b8ba4-115">Then click **Next**.</span></span>

5. <span data-ttu-id="b8ba4-116">Haga clic en el botón **nueva conexión** .</span><span class="sxs-lookup"><span data-stu-id="b8ba4-116">Click the **New Connection** button.</span></span>

6. <span data-ttu-id="b8ba4-117">En el cuadro de diálogo **propiedades de conexión** , escriba el nombre del servidor, seleccione el método de autenticación, escriba el nombre de la base de datos y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b8ba4-117">In the **Connection Properties** dialog box, type your server name, select the authentication method, type the database name, and then click **OK**.</span></span>

     <span data-ttu-id="b8ba4-118">El cuadro de diálogo **elegir la conexión de datos** se actualiza con la configuración de la conexión de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b8ba4-118">The **Choose Your Data Connection** dialog box is updated with your database connection settings.</span></span>

7. <span data-ttu-id="b8ba4-119">Asegúrese de que la casilla **Guardar configuración de conexión de entidad en App.Config como:** está activada.</span><span class="sxs-lookup"><span data-stu-id="b8ba4-119">Ensure that the **Save entity connection settings in App.Config as:** checkbox is checked.</span></span> <span data-ttu-id="b8ba4-120">A continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b8ba4-120">Then click **Next**.</span></span>

8. <span data-ttu-id="b8ba4-121">En el cuadro de diálogo **Elija los objetos de base** de datos, seleccione todos los objetos de base de datos que va a exponer en el servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="b8ba4-121">In the **Choose Your Database Objects** dialog box, select all of database objects that you plan to expose in the data service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b8ba4-122">El servicio de datos no expone automáticamente los objetos incluidos en el modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="b8ba4-122">Objects included in the data model are not automatically exposed by the data service.</span></span> <span data-ttu-id="b8ba4-123">El propio servicio debe exponerlos explícitamente.</span><span class="sxs-lookup"><span data-stu-id="b8ba4-123">They must be explicitly exposed by the service itself.</span></span> <span data-ttu-id="b8ba4-124">Para obtener más información, vea [configurar el servicio de datos](configuring-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="b8ba4-124">For more information, see [Configuring the Data Service](configuring-the-data-service-wcf-data-services.md).</span></span>

9. <span data-ttu-id="b8ba4-125">Haga clic en **Finalizar** para completar el asistente.</span><span class="sxs-lookup"><span data-stu-id="b8ba4-125">Click **Finish** to complete the wizard.</span></span>

     <span data-ttu-id="b8ba4-126">Con esto se crea un modelo de datos predeterminado basado en una base de datos específica.</span><span class="sxs-lookup"><span data-stu-id="b8ba4-126">This creates a default data model based on the specific database.</span></span> <span data-ttu-id="b8ba4-127">Entity Framework permite personalizar el modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="b8ba4-127">The Entity Framework enables to customize the data model.</span></span> <span data-ttu-id="b8ba4-128">Para obtener más información, vea [Entity Data Model herramientas tareas](/previous-versions/dotnet/netframework-4.0/bb738480(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="b8ba4-128">For more information, see [Entity Data Model Tools Tasks](/previous-versions/dotnet/netframework-4.0/bb738480(v=vs.100)).</span></span>

## <a name="to-create-the-data-service-by-using-the-new-data-model"></a><span data-ttu-id="b8ba4-129">Para crear el servicio de datos usando el nuevo modelo de datos</span><span class="sxs-lookup"><span data-stu-id="b8ba4-129">To create the data service by using the new data model</span></span>

1. <span data-ttu-id="b8ba4-130">En Visual Studio, abra el archivo .edmx que representa el modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="b8ba4-130">In Visual Studio, open the .edmx file that represents the data model.</span></span>

2. <span data-ttu-id="b8ba4-131">En el **Explorador de modelos**, haga clic con el botón derecho en el modelo, haga clic en **propiedades** y, a continuación, anote el nombre del contenedor de entidades.</span><span class="sxs-lookup"><span data-stu-id="b8ba4-131">In the **Model Browser**, right-click the model, click **Properties**, and then note the name of the entity container.</span></span>

3. <span data-ttu-id="b8ba4-132">En **Explorador de soluciones**, haga clic con el botón secundario en el nombre del proyecto ASP.net y, a continuación, haga clic en **Agregar**  >  **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="b8ba4-132">In **Solution Explorer**, right-click the name of your ASP.NET project, and then click **Add** > **New Item**.</span></span>

4. <span data-ttu-id="b8ba4-133">En el cuadro de diálogo **Agregar nuevo elemento** , seleccione la plantilla **servicio de datos de WCF** en la categoría **Web** .</span><span class="sxs-lookup"><span data-stu-id="b8ba4-133">In the **Add New Item** dialog box, select the **WCF Data Service** template in the **Web** category.</span></span>

   ![Plantilla de elemento de servicio de datos de WCF en Visual Studio 2015](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="b8ba4-135">La plantilla de **servicio de datos de WCF** está disponible en visual Studio 2015, pero no en visual Studio 2017 o posterior.</span><span class="sxs-lookup"><span data-stu-id="b8ba4-135">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017 or later.</span></span>

5. <span data-ttu-id="b8ba4-136">Proporcione un nombre para el servicio y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b8ba4-136">Supply a name for the service, and then click **OK**.</span></span>

     <span data-ttu-id="b8ba4-137">Visual Studio crea los archivos de código y marcado XML para el nuevo servicio.</span><span class="sxs-lookup"><span data-stu-id="b8ba4-137">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="b8ba4-138">De forma predeterminada, se abre la ventana del editor de código.</span><span class="sxs-lookup"><span data-stu-id="b8ba4-138">By default, the code-editor window opens.</span></span>

6. <span data-ttu-id="b8ba4-139">En el código para el servicio de datos, reemplace el comentario `/* TODO: put your data source class name here */` de la definición de la clase que define el servicio de datos por el tipo que hereda de la clase <xref:System.Data.Objects.ObjectContext> y que es el contenedor de entidades del modelo de datos, que anotó en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="b8ba4-139">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that inherits from the <xref:System.Data.Objects.ObjectContext> class and that is the entity container of the data model, which was noted in step 2.</span></span>

7. <span data-ttu-id="b8ba4-140">En el código del servicio de datos, permita a los clientes autorizados tener acceso a los conjuntos de entidades que expone el servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="b8ba4-140">In the code for the data service, enable authorized clients to access the entity sets that the data service exposes.</span></span> <span data-ttu-id="b8ba4-141">Para obtener más información, vea [crear el servicio de datos](creating-the-data-service.md).</span><span class="sxs-lookup"><span data-stu-id="b8ba4-141">For more information, see [Creating the Data Service](creating-the-data-service.md).</span></span>

8. <span data-ttu-id="b8ba4-142">Para probar el servicio de datos Northwind. SVC mediante un explorador Web, siga las instrucciones del tema [acceso al servicio desde un explorador Web](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span><span class="sxs-lookup"><span data-stu-id="b8ba4-142">To test the Northwind.svc data service by using a Web browser, follow the instructions in the topic [Accessing the Service from a Web Browser](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b8ba4-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8ba4-143">See also</span></span>

- [<span data-ttu-id="b8ba4-144">Definir Servicios de datos de WCF</span><span class="sxs-lookup"><span data-stu-id="b8ba4-144">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)
- [<span data-ttu-id="b8ba4-145">Proveedores de Data Services</span><span class="sxs-lookup"><span data-stu-id="b8ba4-145">Data Services Providers</span></span>](data-services-providers-wcf-data-services.md)
- [<span data-ttu-id="b8ba4-146">Procedimiento para crear un servicio de datos mediante el proveedor de reflexión</span><span class="sxs-lookup"><span data-stu-id="b8ba4-146">How to: Create a Data Service Using the Reflection Provider</span></span>](create-a-data-service-using-rp-wcf-data-services.md)
- [<span data-ttu-id="b8ba4-147">Procedimiento para crear un servicio de datos mediante un origen de datos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="b8ba4-147">How to: Create a Data Service Using a LINQ to SQL Data Source</span></span>](create-a-data-service-using-linq-to-sql-wcf.md)
