---
title: Crear un servicio de datos de WCF en Visual Studio
description: Aprenda a crear un servicio de datos de ejemplo que usa Servicios de datos de WCF para exponer una fuente de OData basada en una base de datos de ejemplo.
ms.date: 08/24/2018
dev_langs:
- csharp
- vb
ms.assetid: 34d1d971-5e18-4c22-9bf6-d3612e27ea59
ms.openlocfilehash: 04c91483587c8976e40584474ced2f5474ab89f4
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805771"
---
# <a name="create-the-data-service"></a><span data-ttu-id="597cd-103">Crear el servicio de datos</span><span class="sxs-lookup"><span data-stu-id="597cd-103">Create the data service</span></span>

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

<span data-ttu-id="597cd-104">En este tema, creará un servicio de datos de ejemplo que utiliza Servicios de datos de WCF para exponer una fuente Open Data Protocol (OData) basada en la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="597cd-104">In this topic, you create a sample data service that uses WCF Data Services to expose an Open Data Protocol (OData) feed that's based on the Northwind sample database.</span></span> <span data-ttu-id="597cd-105">Esta tarea supone la realización de los siguientes pasos básicos:</span><span class="sxs-lookup"><span data-stu-id="597cd-105">The task involves the following basic steps:</span></span>

1. <span data-ttu-id="597cd-106">Cree una aplicación web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="597cd-106">Create an ASP.NET Web application.</span></span>

2. <span data-ttu-id="597cd-107">Defina el modelo de datos usando las herramientas de Entity Data Model.</span><span class="sxs-lookup"><span data-stu-id="597cd-107">Define the data model by using the Entity Data Model tools.</span></span>

3. <span data-ttu-id="597cd-108">Agregar el servicio de datos a la aplicación web.</span><span class="sxs-lookup"><span data-stu-id="597cd-108">Add the data service to the Web application.</span></span>

4. <span data-ttu-id="597cd-109">Habilitar el acceso al servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="597cd-109">Enable access to the data service.</span></span>

## <a name="create-the-aspnet-web-app"></a><span data-ttu-id="597cd-110">Creación de la aplicación Web de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="597cd-110">Create the ASP.NET web app</span></span>

1. <span data-ttu-id="597cd-111">En Visual Studio, en el menú **Archivo**, seleccione **Nuevo** > **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="597cd-111">In Visual Studio, on the **File** menu, select **New** > **Project**.</span></span>

1. <span data-ttu-id="597cd-112">En el cuadro de diálogo **nuevo proyecto** , en Visual Basic o Visual C#, seleccione la categoría **Web** y, a continuación, seleccione **aplicación Web ASP.net**.</span><span class="sxs-lookup"><span data-stu-id="597cd-112">In the **New Project** dialog box, under either Visual Basic or Visual C# select the **Web** category, and then select **ASP.NET Web Application**.</span></span>

1. <span data-ttu-id="597cd-113">Escriba `NorthwindService` como nombre del proyecto y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="597cd-113">Enter `NorthwindService` as the name of the project and then select **OK**.</span></span>

1. <span data-ttu-id="597cd-114">En el cuadro de diálogo **nueva aplicación Web de ASP.net** , seleccione **vacío** y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="597cd-114">In the **New ASP.NET Web Application** dialog, select **Empty** and then select **OK**.</span></span>

1. <span data-ttu-id="597cd-115">(Opcional) Especifique un número de puerto específico para la aplicación web.</span><span class="sxs-lookup"><span data-stu-id="597cd-115">(Optional) Specify a specific port number for your Web application.</span></span> <span data-ttu-id="597cd-116">Nota: el número de puerto `12345` se usa en esta serie de temas de inicio rápido.</span><span class="sxs-lookup"><span data-stu-id="597cd-116">Note: the port number `12345` is used in this series of quickstart topics.</span></span>

    1. <span data-ttu-id="597cd-117">En **Explorador de soluciones**, haga clic con el botón derecho en el proyecto ASP.net que acaba de crear y, a continuación, elija **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="597cd-117">In **Solution Explorer**, right-click on the ASP.NET project that you just created, and then choose **Properties**.</span></span>

    2. <span data-ttu-id="597cd-118">Seleccione la pestaña **Web** y establezca el valor del cuadro de texto **puerto específico** en `12345` .</span><span class="sxs-lookup"><span data-stu-id="597cd-118">Select the **Web** tab, and set the value of the **Specific port** text box to `12345`.</span></span>

## <a name="define-the-data-model"></a><span data-ttu-id="597cd-119">Definir el modelo de datos</span><span class="sxs-lookup"><span data-stu-id="597cd-119">Define the data model</span></span>

1. <span data-ttu-id="597cd-120">En **Explorador de soluciones**, haga clic con el botón secundario en el nombre del proyecto ASP.net y, a continuación, haga clic en **Agregar**  >  **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="597cd-120">In **Solution Explorer**, right-click the name of the ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="597cd-121">En el cuadro de diálogo **Agregar nuevo elemento** , seleccione la categoría de **datos** y, a continuación, seleccione **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="597cd-121">In the **Add New Item** dialog box, select the **Data** category, and then select **ADO.NET Entity Data Model**.</span></span>

3. <span data-ttu-id="597cd-122">Como nombre del modelo de datos, escriba `Northwind.edmx` .</span><span class="sxs-lookup"><span data-stu-id="597cd-122">For the name of the data model, enter `Northwind.edmx`.</span></span>

4. <span data-ttu-id="597cd-123">En el **Asistente para Entity Data Model**, seleccione **EF Designer desde base de datos** y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="597cd-123">In the **Entity Data Model Wizard**, select **EF Designer from Database**, and then click **Next**.</span></span>

5. <span data-ttu-id="597cd-124">Conecte el modelo de datos a la base de datos mediante uno de los pasos siguientes y, a continuación, haga clic en **siguiente**:</span><span class="sxs-lookup"><span data-stu-id="597cd-124">Connect the data model to the database by doing one of the following steps, and then click **Next**:</span></span>

    - <span data-ttu-id="597cd-125">Si no tiene una conexión de base de datos ya configurada, haga clic en **nueva conexión** y cree una conexión nueva.</span><span class="sxs-lookup"><span data-stu-id="597cd-125">If you don't have a database connection already configured, click **New Connection** and create a new connection.</span></span> <span data-ttu-id="597cd-126">Para obtener más información, consulta [How to: Create Connections to SQL Server Databases](/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="597cd-126">For more information, see [How to: Create Connections to SQL Server Databases](/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)).</span></span> <span data-ttu-id="597cd-127">Esta instancia de SQL Server debe tener asociada la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="597cd-127">This SQL Server instance must have the Northwind sample database attached.</span></span>

         <span data-ttu-id="597cd-128">\- o -</span><span class="sxs-lookup"><span data-stu-id="597cd-128">\- or -</span></span>

    - <span data-ttu-id="597cd-129">Si tiene una conexión de base de datos ya configurada para conectarse a la base de datos Northwind, seleccione esa conexión de la lista de conexiones.</span><span class="sxs-lookup"><span data-stu-id="597cd-129">If you have a database connection already configured to connect to the Northwind database, select that connection from the list of connections.</span></span>

6. <span data-ttu-id="597cd-130">En la página final del asistente, seleccione las casillas de todas las tablas de la base de datos y desactive las casillas correspondientes a las vistas y procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="597cd-130">On the final page of the wizard, select the check boxes for all tables in the database, and clear the check boxes for views and stored procedures.</span></span>

7. <span data-ttu-id="597cd-131">Haga clic en **Finalizar** para cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="597cd-131">Click **Finish** to close the wizard.</span></span>

## <a name="create-the-wcf-data-service"></a><span data-ttu-id="597cd-132">Crear el servicio de datos de WCF</span><span class="sxs-lookup"><span data-stu-id="597cd-132">Create the WCF data service</span></span>

1. <span data-ttu-id="597cd-133">En **Explorador de soluciones**, haga clic con el botón derecho en el proyecto ASP.net y, a continuación, elija **Agregar**  >  **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="597cd-133">In **Solution Explorer**, right-click on the ASP.NET project, and then choose **Add** > **New Item**.</span></span>

2. <span data-ttu-id="597cd-134">En el cuadro de diálogo **Agregar nuevo elemento** , seleccione la plantilla de elemento de **servicio de datos de WCF** en la categoría **Web** .</span><span class="sxs-lookup"><span data-stu-id="597cd-134">In the **Add New Item** dialog box, select the **WCF Data Service** item template from the **Web** category.</span></span>

   ![Plantilla de elemento de servicio de datos de WCF en Visual Studio 2015](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="597cd-136">La plantilla de **servicio de datos de WCF** está disponible en visual Studio 2015, pero no en visual Studio 2017 o posterior.</span><span class="sxs-lookup"><span data-stu-id="597cd-136">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017 or later.</span></span>

3. <span data-ttu-id="597cd-137">Como nombre del servicio, escriba `Northwind` .</span><span class="sxs-lookup"><span data-stu-id="597cd-137">For the name of the service, type `Northwind`.</span></span>

     <span data-ttu-id="597cd-138">Visual Studio crea los archivos de código y marcado XML para el nuevo servicio.</span><span class="sxs-lookup"><span data-stu-id="597cd-138">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="597cd-139">De forma predeterminada, se abre la ventana del editor de código.</span><span class="sxs-lookup"><span data-stu-id="597cd-139">By default, the code-editor window opens.</span></span> <span data-ttu-id="597cd-140">En **Explorador de soluciones**, el servicio tiene el nombre Northwind con la extensión *. SVC. CS* o *. SVC. VB*.</span><span class="sxs-lookup"><span data-stu-id="597cd-140">In **Solution Explorer**, the service has the name Northwind with the extension *.svc.cs* or *.svc.vb*.</span></span>

4. <span data-ttu-id="597cd-141">En el código para el servicio de datos, reemplace el comentario `/* TODO: put your data source class name here */` de la definición de la clase que define el servicio de datos por el tipo que es el contenedor de entidades del modelo de datos, que en este caso es `NorthwindEntities`.</span><span class="sxs-lookup"><span data-stu-id="597cd-141">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindEntities`.</span></span> <span data-ttu-id="597cd-142">La definición de la clase debería ser como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="597cd-142">The class definition should look this the following:</span></span>

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

## <a name="enable-access-to-data-service-resources"></a><span data-ttu-id="597cd-143">Habilitar el acceso a los recursos del servicio de datos</span><span class="sxs-lookup"><span data-stu-id="597cd-143">Enable access to data service resources</span></span>

1. <span data-ttu-id="597cd-144">En el código del servicio de datos, reemplace el código de marcador de posición de la función `InitializeService` por el siguiente:</span><span class="sxs-lookup"><span data-stu-id="597cd-144">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>

     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#allreadconfig)]

     <span data-ttu-id="597cd-145">De esta forma, los clientes autorizados pueden tener acceso de lectura y escritura a los recursos para los conjuntos de entidades especificados.</span><span class="sxs-lookup"><span data-stu-id="597cd-145">This enables authorized clients to have read and write access to resources for the specified entity sets.</span></span>

    > [!NOTE]
    > <span data-ttu-id="597cd-146">Cualquier cliente que pueda tener acceso a la aplicación ASP.NET también puede tener acceso a los recursos expuestos por el servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="597cd-146">Any client that can access the ASP.NET application can also access the resources exposed by the data service.</span></span> <span data-ttu-id="597cd-147">En un servicio de datos de producción, para evitar el acceso no autorizado a los recursos también debería proteger la aplicación.</span><span class="sxs-lookup"><span data-stu-id="597cd-147">In a production data service, to prevent unauthorized access to resources you should also secure the application itself.</span></span> <span data-ttu-id="597cd-148">Para obtener más información, consulta [Securing WCF Data Services](securing-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="597cd-148">For more information, see [Securing WCF Data Services](securing-wcf-data-services.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="597cd-149">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="597cd-149">Next steps</span></span>

<span data-ttu-id="597cd-150">Ha creado correctamente un nuevo servicio de datos que expone una fuente de OData basada en la base de datos de ejemplo Northwind y ha habilitado el acceso a la fuente para los clientes que tienen permisos en la aplicación Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="597cd-150">You have successfully created a new data service that exposes an OData feed that is based on the Northwind sample database, and you have enabled access to the feed for clients that have permissions on the ASP.NET Web application.</span></span> <span data-ttu-id="597cd-151">A continuación, iniciará el servicio de datos desde Visual Studio y tendrá acceso a la fuente de OData mediante el envío de solicitudes HTTP GET a través de un explorador Web:</span><span class="sxs-lookup"><span data-stu-id="597cd-151">Next, you'll start the data service from Visual Studio and access the OData feed by submitting HTTP GET requests through a Web browser:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="597cd-152">Acceder al servicio desde un explorador Web</span><span class="sxs-lookup"><span data-stu-id="597cd-152">Access the service from a web browser</span></span>](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

## <a name="see-also"></a><span data-ttu-id="597cd-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="597cd-153">See also</span></span>

- <span data-ttu-id="597cd-154">[ADO.NET Entity Data Model herramientas](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="597cd-154">[ADO.NET Entity Data Model Tools](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
