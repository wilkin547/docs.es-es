---
title: Crear el servicio de datos
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 34d1d971-5e18-4c22-9bf6-d3612e27ea59
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 781def411214b0804cdc094c00b2f655b6c3823d
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="creating-the-data-service"></a><span data-ttu-id="5530c-102">Crear el servicio de datos</span><span class="sxs-lookup"><span data-stu-id="5530c-102">Creating the Data Service</span></span>
<span data-ttu-id="5530c-103">En esta tarea, creará un servicio de datos de ejemplo que usa [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] para exponer un [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] fuente que se basa en la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="5530c-103">In this task, you will create a sample data service that uses [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] to expose an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed that is based on the Northwind sample database.</span></span> <span data-ttu-id="5530c-104">Esta tarea supone la realización de los siguientes pasos básicos:</span><span class="sxs-lookup"><span data-stu-id="5530c-104">The task involves the following basic steps:</span></span>  
  
1.  <span data-ttu-id="5530c-105">Crear una aplicación web de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5530c-105">Create an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web application.</span></span>  
  
2.  <span data-ttu-id="5530c-106">Definir el modelo de datos usando las herramientas de [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5530c-106">Define the data model by using the [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] tools.</span></span>  
  
3.  <span data-ttu-id="5530c-107">Agregar el servicio de datos a la aplicación web.</span><span class="sxs-lookup"><span data-stu-id="5530c-107">Add the data service to the Web application.</span></span>  
  
4.  <span data-ttu-id="5530c-108">Habilitar el acceso al servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="5530c-108">Enable access to the data service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5530c-109">El [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] aplicación Web que se crea al completar esta tarea se ejecuta en el [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] servidor de desarrollo de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5530c-109">The [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web application that you create when you complete this task runs on the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Development Server provided by Visual Studio.</span></span> <span data-ttu-id="5530c-110">El servidor de desarrollo de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] solo admite el acceso desde el equipo local.</span><span class="sxs-lookup"><span data-stu-id="5530c-110">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Development Server only supports access from the local computer.</span></span> <span data-ttu-id="5530c-111">Para facilitar también la comprobación y solución de problemas del servicio de datos durante el desarrollo, puede ejecutar la aplicación que hospeda el servicio de datos mediante Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="5530c-111">To also make it easier to test and troubleshoot the data service during development, consider running the application that hosts the data service by using Internet Information Services (IIS).</span></span> <span data-ttu-id="5530c-112">Para obtener más información, consulta [Cómo: Desarrollar un servicio de datos WCF que se ejecuta en IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md).</span><span class="sxs-lookup"><span data-stu-id="5530c-112">For more information, see [How to: Develop a WCF Data Service Running on IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md).</span></span>  
  
### <a name="to-create-the-aspnet-web-application"></a><span data-ttu-id="5530c-113">Para crear la aplicación web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="5530c-113">To create the ASP.NET Web application</span></span>  
  
1.  <span data-ttu-id="5530c-114">En Visual Studio, en el **archivo** menú, seleccione **New**y, a continuación, seleccione **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="5530c-114">In Visual Studio, on the **File** menu, select **New**, and then select **Project**.</span></span>  
  
2.  <span data-ttu-id="5530c-115">En el **nuevo proyecto** cuadro de diálogo, en Visual Basic o Visual C#, seleccione la **Web** plantilla y, a continuación, seleccione **aplicación Web ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="5530c-115">In the **New Project** dialog box, under either Visual Basic or Visual C# select the **Web** template, and then select **ASP.NET Web Application**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5530c-116">Si usa Visual Studio Web Developer, tendrá que crear un nuevo sitio web en lugar de una nueva aplicación web.</span><span class="sxs-lookup"><span data-stu-id="5530c-116">If you use Visual Studio Web Developer, you must create a new Web site instead of a new Web application.</span></span>  
  
3.  <span data-ttu-id="5530c-117">Tipo `NorthwindService` como el nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="5530c-117">Type `NorthwindService` as the name of the project.</span></span>  
  
4.  <span data-ttu-id="5530c-118">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5530c-118">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="5530c-119">(Opcional) Especifique un número de puerto específico para la aplicación web.</span><span class="sxs-lookup"><span data-stu-id="5530c-119">(Optional) Specify a specific port number for your Web application.</span></span> <span data-ttu-id="5530c-120">Nota: en el resto del tutorial rápido se usa el número de puerto `12345`.</span><span class="sxs-lookup"><span data-stu-id="5530c-120">Note: the port number `12345` is used in the rest of the quickstart.</span></span>  
  
    1.  <span data-ttu-id="5530c-121">En **el Explorador de soluciones**, haga clic en el nombre de la [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] proyecto recién creado y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5530c-121">In **Solution Explorer**, right-click the name of the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] project that you just created, and then click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="5530c-122">Seleccione el **Web** y a establecer el valor de la **puerto específico** cuadro de texto para `12345`.</span><span class="sxs-lookup"><span data-stu-id="5530c-122">Select the **Web** tab, and set the value of the **Specific port** text box to `12345`.</span></span>  
  
### <a name="to-define-the-data-model"></a><span data-ttu-id="5530c-123">Para definir el modelo de datos</span><span class="sxs-lookup"><span data-stu-id="5530c-123">To define the data model</span></span>  
  
1.  <span data-ttu-id="5530c-124">En **el Explorador de soluciones**, haga clic en el nombre de la [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] del proyecto y, a continuación, haga clic en **Agregar nuevo elemento.**</span><span class="sxs-lookup"><span data-stu-id="5530c-124">In **Solution Explorer**, right-click the name of the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] project, and then click **Add New Item.**</span></span>  
  
2.  <span data-ttu-id="5530c-125">En el **Agregar nuevo elemento** cuadro de diálogo, haga clic en el **datos** plantilla y, a continuación, seleccione **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="5530c-125">In the **Add New Item** dialog box, click the **Data** template and then select **ADO.NET Entity Data Model**.</span></span>  
  
3.  <span data-ttu-id="5530c-126">Para el nombre del modelo de datos, escriba `Northwind.edmx`.</span><span class="sxs-lookup"><span data-stu-id="5530c-126">For the name of the data model, type `Northwind.edmx`.</span></span>  
  
4.  <span data-ttu-id="5530c-127">En el [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] asistente, seleccione **generar desde la base de datos**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5530c-127">In the [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] Wizard, select **Generate from Database**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="5530c-128">Conectar el modelo de datos a la base de datos, realice uno de los pasos siguientes y, a continuación, haga clic en **siguiente**:</span><span class="sxs-lookup"><span data-stu-id="5530c-128">Connect the data model to the database by doing one of the following steps, and then click **Next**:</span></span>  
  
    -   <span data-ttu-id="5530c-129">Si no tiene una conexión de base de datos ya configurada, haga clic en **nueva conexión** y crear una nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="5530c-129">If you do not have a database connection already configured, click **New Connection** and create a new connection.</span></span> <span data-ttu-id="5530c-130">Para obtener más información, consulte [Cómo: crear conexiones a bases de datos de SQL Server](http://go.microsoft.com/fwlink/?LinkId=123631).</span><span class="sxs-lookup"><span data-stu-id="5530c-130">For more information, see [How to: Create Connections to SQL Server Databases](http://go.microsoft.com/fwlink/?LinkId=123631).</span></span> <span data-ttu-id="5530c-131">Esta instancia de SQL Server debe tener asociada la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="5530c-131">This SQL Server instance must have the Northwind sample database attached.</span></span>  
  
         <span data-ttu-id="5530c-132">\- o -</span><span class="sxs-lookup"><span data-stu-id="5530c-132">\- or -</span></span>  
  
    -   <span data-ttu-id="5530c-133">Si tiene una conexión de base de datos ya configurada para conectarse a la base de datos Northwind, seleccione esa conexión de la lista de conexiones.</span><span class="sxs-lookup"><span data-stu-id="5530c-133">If you have a database connection already configured to connect to the Northwind database, select that connection from the list of connections.</span></span>  
  
6.  <span data-ttu-id="5530c-134">En la página final del asistente, seleccione las casillas de todas las tablas de la base de datos y desactive las casillas correspondientes a las vistas y procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="5530c-134">On the final page of the wizard, select the check boxes for all tables in the database, and clear the check boxes for views and stored procedures.</span></span>  
  
7.  <span data-ttu-id="5530c-135">Haga clic en **finalizar** para cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="5530c-135">Click **Finish** to close the wizard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5530c-136">Este modelo de datos generado expone las propiedades de clave externa en los tipos de entidad.</span><span class="sxs-lookup"><span data-stu-id="5530c-136">This generated data model exposes foreign key properties on entity types.</span></span> <span data-ttu-id="5530c-137">Los modelos de datos creados mediante Visual Studio 2008 no incluyen estas propiedades de clave externa.</span><span class="sxs-lookup"><span data-stu-id="5530c-137">Data models created using Visual Studio 2008 do not include these foreign key properties.</span></span> <span data-ttu-id="5530c-138">Debido a esto, debe actualizar las clases del servicio de datos de cliente de cualquier aplicación cliente que se haya creado para tener acceso al servicio de datos de Northwind que se creó con Visual Studio 2008 antes de intentar tener acceso a esta versión del servicio de datos de Northwind.</span><span class="sxs-lookup"><span data-stu-id="5530c-138">Because of this, you must update the client data service classes of any client applications that were created to access the Northwind data service that was created using Visual Studio 2008 before attempting to access this version of the Northwind data service.</span></span>  
  
### <a name="to-create-the-data-service"></a><span data-ttu-id="5530c-139">Para crear el servicio de datos</span><span class="sxs-lookup"><span data-stu-id="5530c-139">To create the data service</span></span>  
  
1.  <span data-ttu-id="5530c-140">En **el Explorador de soluciones**, haga clic en el nombre de su [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] del proyecto y, a continuación, haga clic en **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="5530c-140">In **Solution Explorer**, right-click the name of your [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] project, and then click **Add New Item**.</span></span>  
  
2.  <span data-ttu-id="5530c-141">En el **Agregar nuevo elemento** cuadro de diálogo, seleccione **servicio de datos de WCF**.</span><span class="sxs-lookup"><span data-stu-id="5530c-141">In the **Add New Item** dialog box, select **WCF Data Service**.</span></span>  
  
3.  <span data-ttu-id="5530c-142">Para el nombre del servicio, escriba `Northwind`.</span><span class="sxs-lookup"><span data-stu-id="5530c-142">For the name of the service, type `Northwind`.</span></span>  
  
     <span data-ttu-id="5530c-143">Visual StudioVisual Studio crea los archivos de código y marcado XML para el nuevo servicio.</span><span class="sxs-lookup"><span data-stu-id="5530c-143">Visual StudioVisual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="5530c-144">De forma predeterminada, se abre la ventana del editor de código.</span><span class="sxs-lookup"><span data-stu-id="5530c-144">By default, the code-editor window opens.</span></span> <span data-ttu-id="5530c-145">En **el Explorador de soluciones**, el servicio tendrá el nombre Northwind, con la extensión. svc.cs o. svc.vb.</span><span class="sxs-lookup"><span data-stu-id="5530c-145">In **Solution Explorer**, the service will have the name, Northwind, with the extension .svc.cs or .svc.vb.</span></span>  
  
4.  <span data-ttu-id="5530c-146">En el código para el servicio de datos, reemplace el comentario `/* TODO: put your data source class name here */` de la definición de la clase que define el servicio de datos por el tipo que es el contenedor de entidades del modelo de datos, que en este caso es `NorthwindEntities`.</span><span class="sxs-lookup"><span data-stu-id="5530c-146">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindEntities`.</span></span> <span data-ttu-id="5530c-147">La definición de la clase debería ser como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="5530c-147">The class definition should look this the following:</span></span>  
  
     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]  
  
### <a name="to-enable-access-to-data-service-resources"></a><span data-ttu-id="5530c-148">Para habilitar el acceso a los recursos del servicio de datos</span><span class="sxs-lookup"><span data-stu-id="5530c-148">To enable access to data service resources</span></span>  
  
1.  <span data-ttu-id="5530c-149">En el código del servicio de datos, reemplace el código de marcador de posición de la función `InitializeService` por el siguiente:</span><span class="sxs-lookup"><span data-stu-id="5530c-149">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#allreadconfig)]  
  
     <span data-ttu-id="5530c-150">De esta forma, los clientes autorizados pueden tener acceso de lectura y escritura a los recursos para los conjuntos de entidades especificados.</span><span class="sxs-lookup"><span data-stu-id="5530c-150">This enables authorized clients to have read and write access to resources for the specified entity sets.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5530c-151">Cualquier cliente que pueda tener acceso a la aplicación [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] también puede tener acceso a los recursos expuestos por el servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="5530c-151">Any client that can access the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application can also access the resources exposed by the data service.</span></span> <span data-ttu-id="5530c-152">En un servicio de datos de producción, para evitar el acceso no autorizado a los recursos también debería proteger la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5530c-152">In a production data service, to prevent unauthorized access to resources you should also secure the application itself.</span></span> <span data-ttu-id="5530c-153">Para obtener más información, consulta [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="5530c-153">For more information, see [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="5530c-154">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="5530c-154">Next Steps</span></span>  
 <span data-ttu-id="5530c-155">Ha creado correctamente un nuevo servicio de datos que expone un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] fuente que se basa en la base de datos de ejemplo Northwind y se ha habilitado el acceso a la fuente para los clientes que tienen permisos en el [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] aplicación Web.</span><span class="sxs-lookup"><span data-stu-id="5530c-155">You have successfully created a new data service that exposes an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed that is based on the Northwind sample database, and you have enabled access to the feed for clients that have permissions on the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web application.</span></span> <span data-ttu-id="5530c-156">A continuación, iniciará el servicio de datos desde Visual Studio y tendrá acceso a la fuente de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] enviando solicitudes HTTP GET a través de un explorador web:</span><span class="sxs-lookup"><span data-stu-id="5530c-156">Next, you will start the data service from Visual Studio and you will access the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed by submitting HTTP GET requests through a Web browser:</span></span>  
  
 [<span data-ttu-id="5530c-157">Acceso al servicio desde un explorador web</span><span class="sxs-lookup"><span data-stu-id="5530c-157">Accessing the Service from a Web Browser</span></span>](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)  
  
## <a name="see-also"></a><span data-ttu-id="5530c-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="5530c-158">See Also</span></span>  
 [<span data-ttu-id="5530c-159">Herramientas de Entity Data Model de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="5530c-159">ADO.NET Entity Data Model  Tools</span></span>](http://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)
