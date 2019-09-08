---
title: Crear un servicio de datos de WCF en Visual Studio
ms.date: 08/24/2018
dev_langs:
- csharp
- vb
ms.assetid: 34d1d971-5e18-4c22-9bf6-d3612e27ea59
ms.openlocfilehash: c3c80fb48635199f45acb1e72bf756bbc65d2e14
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780414"
---
# <a name="create-the-data-service"></a><span data-ttu-id="00c6c-102">Crear el servicio de datos</span><span class="sxs-lookup"><span data-stu-id="00c6c-102">Create the data service</span></span>

<span data-ttu-id="00c6c-103">En este tema, creará un servicio de datos de ejemplo que utiliza WCF Data Services para [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] exponer una fuente basada en la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="00c6c-103">In this topic, you create a sample data service that uses WCF Data Services to expose an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed that's based on the Northwind sample database.</span></span> <span data-ttu-id="00c6c-104">Esta tarea supone la realización de los siguientes pasos básicos:</span><span class="sxs-lookup"><span data-stu-id="00c6c-104">The task involves the following basic steps:</span></span>

1. <span data-ttu-id="00c6c-105">Cree una aplicación web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="00c6c-105">Create an ASP.NET Web application.</span></span>

2. <span data-ttu-id="00c6c-106">Defina el modelo de datos usando las herramientas de Entity Data Model.</span><span class="sxs-lookup"><span data-stu-id="00c6c-106">Define the data model by using the Entity Data Model tools.</span></span>

3. <span data-ttu-id="00c6c-107">Agregar el servicio de datos a la aplicación web.</span><span class="sxs-lookup"><span data-stu-id="00c6c-107">Add the data service to the Web application.</span></span>

4. <span data-ttu-id="00c6c-108">Habilitar el acceso al servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="00c6c-108">Enable access to the data service.</span></span>

## <a name="create-the-aspnet-web-app"></a><span data-ttu-id="00c6c-109">Creación de la aplicación Web de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="00c6c-109">Create the ASP.NET web app</span></span>

1. <span data-ttu-id="00c6c-110">En Visual Studio, en el menú **archivo** , seleccione **nuevo** > **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="00c6c-110">In Visual Studio, on the **File** menu, select **New** > **Project**.</span></span>

1. <span data-ttu-id="00c6c-111">En el cuadro de diálogo **nuevo proyecto** , en Visual Basic o visual C# , seleccione la categoría **Web** y, a continuación, seleccione **aplicación Web ASP.net**.</span><span class="sxs-lookup"><span data-stu-id="00c6c-111">In the **New Project** dialog box, under either Visual Basic or Visual C# select the **Web** category, and then select **ASP.NET Web Application**.</span></span>

1. <span data-ttu-id="00c6c-112">Escriba `NorthwindService` como nombre del proyecto y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="00c6c-112">Enter `NorthwindService` as the name of the project and then select **OK**.</span></span>

1. <span data-ttu-id="00c6c-113">En el cuadro de diálogo **nueva aplicación Web de ASP.net** , seleccione **vacío** y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="00c6c-113">In the **New ASP.NET Web Application** dialog, select **Empty** and then select **OK**.</span></span>

1. <span data-ttu-id="00c6c-114">(Opcional) Especifique un número de puerto específico para la aplicación web.</span><span class="sxs-lookup"><span data-stu-id="00c6c-114">(Optional) Specify a specific port number for your Web application.</span></span> <span data-ttu-id="00c6c-115">Nota: el número `12345` de puerto se usa en esta serie de temas de inicio rápido.</span><span class="sxs-lookup"><span data-stu-id="00c6c-115">Note: the port number `12345` is used in this series of quickstart topics.</span></span>

    1. <span data-ttu-id="00c6c-116">En **Explorador de soluciones**, haga clic con el botón derecho en el proyecto ASP.net que acaba de crear y, a continuación, elija **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="00c6c-116">In **Solution Explorer**, right-click on the ASP.NET project that you just created, and then choose **Properties**.</span></span>

    2. <span data-ttu-id="00c6c-117">Seleccione la pestaña **Web** y establezca el valor del cuadro de texto **puerto específico** en `12345`.</span><span class="sxs-lookup"><span data-stu-id="00c6c-117">Select the **Web** tab, and set the value of the **Specific port** text box to `12345`.</span></span>

## <a name="define-the-data-model"></a><span data-ttu-id="00c6c-118">Definir el modelo de datos</span><span class="sxs-lookup"><span data-stu-id="00c6c-118">Define the data model</span></span>

1. <span data-ttu-id="00c6c-119">En **Explorador de soluciones**, haga clic con el botón secundario en el nombre del proyecto ASP.net y, a continuación, haga clic en **Agregar** > **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="00c6c-119">In **Solution Explorer**, right-click the name of the ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="00c6c-120">En el cuadro de diálogo **Agregar nuevo elemento** , seleccione la categoría de **datos** y, a continuación, seleccione **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="00c6c-120">In the **Add New Item** dialog box, select the **Data** category, and then select **ADO.NET Entity Data Model**.</span></span>

3. <span data-ttu-id="00c6c-121">Como nombre del modelo de datos, escriba `Northwind.edmx`.</span><span class="sxs-lookup"><span data-stu-id="00c6c-121">For the name of the data model, enter `Northwind.edmx`.</span></span>

4. <span data-ttu-id="00c6c-122">En el **Asistente para Entity Data Model**, seleccione **EF Designer desde base de datos**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="00c6c-122">In the **Entity Data Model Wizard**, select **EF Designer from Database**, and then click **Next**.</span></span>

5. <span data-ttu-id="00c6c-123">Conecte el modelo de datos a la base de datos mediante uno de los pasos siguientes y, a continuación, haga clic en **siguiente**:</span><span class="sxs-lookup"><span data-stu-id="00c6c-123">Connect the data model to the database by doing one of the following steps, and then click **Next**:</span></span>

    - <span data-ttu-id="00c6c-124">Si no tiene una conexión de base de datos ya configurada, haga clic en **nueva conexión** y cree una conexión nueva.</span><span class="sxs-lookup"><span data-stu-id="00c6c-124">If you don't have a database connection already configured, click **New Connection** and create a new connection.</span></span> <span data-ttu-id="00c6c-125">Para obtener más información, consulte [Cómo Crear conexiones a bases de datos](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90))de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="00c6c-125">For more information, see [How to: Create Connections to SQL Server Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)).</span></span> <span data-ttu-id="00c6c-126">Esta instancia de SQL Server debe tener asociada la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="00c6c-126">This SQL Server instance must have the Northwind sample database attached.</span></span>

         <span data-ttu-id="00c6c-127">\- o -</span><span class="sxs-lookup"><span data-stu-id="00c6c-127">\- or -</span></span>

    - <span data-ttu-id="00c6c-128">Si tiene una conexión de base de datos ya configurada para conectarse a la base de datos Northwind, seleccione esa conexión de la lista de conexiones.</span><span class="sxs-lookup"><span data-stu-id="00c6c-128">If you have a database connection already configured to connect to the Northwind database, select that connection from the list of connections.</span></span>

6. <span data-ttu-id="00c6c-129">En la página final del asistente, seleccione las casillas de todas las tablas de la base de datos y desactive las casillas correspondientes a las vistas y procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="00c6c-129">On the final page of the wizard, select the check boxes for all tables in the database, and clear the check boxes for views and stored procedures.</span></span>

7. <span data-ttu-id="00c6c-130">Haga clic en **Finalizar** para cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="00c6c-130">Click **Finish** to close the wizard.</span></span>

## <a name="create-the-wcf-data-service"></a><span data-ttu-id="00c6c-131">Crear el servicio de datos de WCF</span><span class="sxs-lookup"><span data-stu-id="00c6c-131">Create the WCF data service</span></span>

1. <span data-ttu-id="00c6c-132">En **Explorador de soluciones**, haga clic con el botón derecho en el proyecto ASP.net y, a continuación, elija **Agregar** > **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="00c6c-132">In **Solution Explorer**, right-click on the ASP.NET project, and then choose **Add** > **New Item**.</span></span>

2. <span data-ttu-id="00c6c-133">En el cuadro de diálogo **Agregar nuevo elemento** , seleccione la plantilla de elemento de **servicio de datos de WCF** en la categoría **Web** .</span><span class="sxs-lookup"><span data-stu-id="00c6c-133">In the **Add New Item** dialog box, select the **WCF Data Service** item template from the **Web** category.</span></span>

   ![Plantilla de elemento de servicio de datos de WCF en Visual Studio 2015](media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="00c6c-135">La plantilla de **servicio de datos de WCF** está disponible en visual Studio 2015, pero no en visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="00c6c-135">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017.</span></span>

3. <span data-ttu-id="00c6c-136">Como nombre del servicio, escriba `Northwind`.</span><span class="sxs-lookup"><span data-stu-id="00c6c-136">For the name of the service, type `Northwind`.</span></span>

     <span data-ttu-id="00c6c-137">Visual Studio crea los archivos de código y marcado XML para el nuevo servicio.</span><span class="sxs-lookup"><span data-stu-id="00c6c-137">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="00c6c-138">De forma predeterminada, se abre la ventana del editor de código.</span><span class="sxs-lookup"><span data-stu-id="00c6c-138">By default, the code-editor window opens.</span></span> <span data-ttu-id="00c6c-139">En **Explorador de soluciones**, el servicio tiene el nombre Northwind con la extensión *. SVC.CS* o *. SVC. VB*.</span><span class="sxs-lookup"><span data-stu-id="00c6c-139">In **Solution Explorer**, the service has the name Northwind with the extension *.svc.cs* or *.svc.vb*.</span></span>

4. <span data-ttu-id="00c6c-140">En el código para el servicio de datos, reemplace el comentario `/* TODO: put your data source class name here */` de la definición de la clase que define el servicio de datos por el tipo que es el contenedor de entidades del modelo de datos, que en este caso es `NorthwindEntities`.</span><span class="sxs-lookup"><span data-stu-id="00c6c-140">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindEntities`.</span></span> <span data-ttu-id="00c6c-141">La definición de la clase debería ser como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="00c6c-141">The class definition should look this the following:</span></span>

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

## <a name="enable-access-to-data-service-resources"></a><span data-ttu-id="00c6c-142">Habilitar el acceso a los recursos del servicio de datos</span><span class="sxs-lookup"><span data-stu-id="00c6c-142">Enable access to data service resources</span></span>

1. <span data-ttu-id="00c6c-143">En el código del servicio de datos, reemplace el código de marcador de posición de la función `InitializeService` por el siguiente:</span><span class="sxs-lookup"><span data-stu-id="00c6c-143">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>

     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#allreadconfig)]

     <span data-ttu-id="00c6c-144">De esta forma, los clientes autorizados pueden tener acceso de lectura y escritura a los recursos para los conjuntos de entidades especificados.</span><span class="sxs-lookup"><span data-stu-id="00c6c-144">This enables authorized clients to have read and write access to resources for the specified entity sets.</span></span>

    > [!NOTE]
    > <span data-ttu-id="00c6c-145">Cualquier cliente que pueda tener acceso a la aplicación ASP.NET también puede tener acceso a los recursos expuestos por el servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="00c6c-145">Any client that can access the ASP.NET application can also access the resources exposed by the data service.</span></span> <span data-ttu-id="00c6c-146">En un servicio de datos de producción, para evitar el acceso no autorizado a los recursos también debería proteger la aplicación.</span><span class="sxs-lookup"><span data-stu-id="00c6c-146">In a production data service, to prevent unauthorized access to resources you should also secure the application itself.</span></span> <span data-ttu-id="00c6c-147">Para obtener más información, consulta [Securing WCF Data Services](securing-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="00c6c-147">For more information, see [Securing WCF Data Services](securing-wcf-data-services.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="00c6c-148">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="00c6c-148">Next steps</span></span>

<span data-ttu-id="00c6c-149">Ha creado correctamente un nuevo servicio de datos que expone una fuente de OData basada en la base de datos de ejemplo Northwind y ha habilitado el acceso a la fuente para los clientes que tienen permisos en la aplicación Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="00c6c-149">You have successfully created a new data service that exposes an OData feed that is based on the Northwind sample database, and you have enabled access to the feed for clients that have permissions on the ASP.NET Web application.</span></span> <span data-ttu-id="00c6c-150">A continuación, iniciará el servicio de datos desde Visual Studio y tendrá acceso a la fuente de OData mediante el envío de solicitudes HTTP GET a través de un explorador Web:</span><span class="sxs-lookup"><span data-stu-id="00c6c-150">Next, you'll start the data service from Visual Studio and access the OData feed by submitting HTTP GET requests through a Web browser:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="00c6c-151">Acceder al servicio desde un explorador Web</span><span class="sxs-lookup"><span data-stu-id="00c6c-151">Access the service from a web browser</span></span>](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

## <a name="see-also"></a><span data-ttu-id="00c6c-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="00c6c-152">See also</span></span>

- <span data-ttu-id="00c6c-153">[ADO.NET Entity Data Model herramientas](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="00c6c-153">[ADO.NET Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
