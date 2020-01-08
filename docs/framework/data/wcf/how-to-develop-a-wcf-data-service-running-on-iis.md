---
title: 'Cómo: Desarrollar un servicio de datos WCF que se ejecuta en IIS'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- WCF Data Services, hosting
ms.assetid: f6f768c5-4989-49e3-a36f-896ab4ded86e
ms.openlocfilehash: 5c75425783d3468ac42ef7cb32cd9c93e812192a
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75338347"
---
# <a name="how-to-develop-a-wcf-data-service-running-on-iis"></a><span data-ttu-id="0f5d0-102">Cómo: desarrollar un servicio de datos de WCF que se ejecuta en IIS</span><span class="sxs-lookup"><span data-stu-id="0f5d0-102">How to: Develop a WCF data service running on IIS</span></span>

<span data-ttu-id="0f5d0-103">En este tema se muestra cómo utilizar WCF Data Services para crear un servicio de datos basado en la base de datos de ejemplo Northwind que está hospedada en una aplicación Web de ASP.NET que se ejecuta en Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="0f5d0-103">This topic shows how to use WCF Data Services to create a data service that is based on the Northwind sample database that is hosted by an ASP.NET Web application that is running on Internet Information Services (IIS).</span></span> <span data-ttu-id="0f5d0-104">Para obtener un ejemplo de cómo crear el mismo servicio de datos de Northwind como una aplicación Web de ASP.NET que se ejecuta en el Servidor de desarrollo de ASP.NET, consulte la guía de [Inicio rápido de WCF Data Services](quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0f5d0-104">For an example of how to create the same Northwind data service as an ASP.NET Web application that runs on the ASP.NET Development Server, see the [WCF Data Services quickstart](quickstart-wcf-data-services.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0f5d0-105">Para crear el servicio de datos de Northwind, debe tener instalada la base de datos de ejemplo Northwind en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-105">To create the Northwind data service, you must have installed the Northwind sample database on the local computer.</span></span> <span data-ttu-id="0f5d0-106">Para descargar esta base de datos de ejemplo, consulte la página de descargas, [Bases de datos de ejemplo de SQL Server](https://go.microsoft.com/fwlink/?linkid=24758).</span><span class="sxs-lookup"><span data-stu-id="0f5d0-106">To download this sample database, see the download page, [Sample Databases for SQL Server](https://go.microsoft.com/fwlink/?linkid=24758).</span></span>

<span data-ttu-id="0f5d0-107">En este tema se muestra cómo crear un servicio de datos utilizando el proveedor de Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-107">This topic shows how to create a data service by using the Entity Framework provider.</span></span> <span data-ttu-id="0f5d0-108">Están disponibles otros proveedores de servicios de datos.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-108">Other data services providers are available.</span></span> <span data-ttu-id="0f5d0-109">Para obtener más información, vea [proveedores de Data Services](data-services-providers-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0f5d0-109">For more information, see [Data Services Providers](data-services-providers-wcf-data-services.md).</span></span>

<span data-ttu-id="0f5d0-110">Una vez creado el servicio, debe proporcionar acceso a los recursos del servicio de datos de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-110">After you create the service, you must explicitly provide access to data service resources.</span></span> <span data-ttu-id="0f5d0-111">Para obtener más información, consulte [Cómo: habilitar el acceso al servicio de datos](how-to-enable-access-to-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0f5d0-111">For more information, see [How to: Enable Access to the Data Service](how-to-enable-access-to-the-data-service-wcf-data-services.md).</span></span>

## <a name="create-the-aspnet-web-application-that-runs-on-iis"></a><span data-ttu-id="0f5d0-112">Crear la aplicación Web de ASP.NET que se ejecuta en IIS</span><span class="sxs-lookup"><span data-stu-id="0f5d0-112">Create the ASP.NET web application that runs on IIS</span></span>

1. <span data-ttu-id="0f5d0-113">En Visual Studio, en el menú **Archivo**, seleccione **Nuevo** > **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-113">In Visual Studio, on the **File** menu, select **New** > **Project**.</span></span>

2. <span data-ttu-id="0f5d0-114">En el cuadro de diálogo **nuevo proyecto** , seleccione el > **instalado** [ **C# visual** o **Visual Basic**] > categoría **Web** .</span><span class="sxs-lookup"><span data-stu-id="0f5d0-114">In the **New Project** dialog box, select the **Installed** > [**Visual C#** or **Visual Basic**] > **Web** category.</span></span>

3. <span data-ttu-id="0f5d0-115">Seleccione la plantilla **Aplicación Web ASP.NET** .</span><span class="sxs-lookup"><span data-stu-id="0f5d0-115">Select the **ASP.NET Web Application** template.</span></span>

4. <span data-ttu-id="0f5d0-116">Escriba `NorthwindService` como nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-116">Enter `NorthwindService` as the name of the project.</span></span>

5. <span data-ttu-id="0f5d0-117">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-117">Click **OK**.</span></span>

6. <span data-ttu-id="0f5d0-118">En el menú **proyecto** , seleccione **propiedades de NorthwindService**.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-118">On the **Project** menu, select **NorthwindService Properties**.</span></span>

7. <span data-ttu-id="0f5d0-119">Seleccione la pestaña **Web** y, a continuación, seleccione **usar servidor Web de IIS local**.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-119">Select the **Web** tab, and then select **Use Local IIS Web Server**.</span></span>

8. <span data-ttu-id="0f5d0-120">Haga clic en **Crear directorio virtual** y, a continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-120">Click **Create Virtual Directory** and then click **OK**.</span></span>

9. <span data-ttu-id="0f5d0-121">Desde el símbolo del sistema, con privilegios de administrador, ejecute uno de los siguientes comandos (en función de cuál sea el sistema operativo):</span><span class="sxs-lookup"><span data-stu-id="0f5d0-121">From the command prompt with administrator privileges, execute one of the following commands (depending on the operating system):</span></span>

    - <span data-ttu-id="0f5d0-122">sistemas de 32 bits:</span><span class="sxs-lookup"><span data-stu-id="0f5d0-122">32-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

    - <span data-ttu-id="0f5d0-123">Sistemas de 64 bits:</span><span class="sxs-lookup"><span data-stu-id="0f5d0-123">64-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework64\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

     <span data-ttu-id="0f5d0-124">De este modo, se garantiza que Windows Communication Foundation (WCF) se registre en el equipo.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-124">This makes sure that Windows Communication Foundation (WCF) is registered on the computer.</span></span>

10. <span data-ttu-id="0f5d0-125">Desde el símbolo del sistema, con privilegios de administrador, ejecute uno de los siguientes comandos (en función de cuál sea el sistema operativo):</span><span class="sxs-lookup"><span data-stu-id="0f5d0-125">From the command prompt with administrator privileges, execute one of the following commands (depending on the operating system):</span></span>

    - <span data-ttu-id="0f5d0-126">sistemas de 32 bits:</span><span class="sxs-lookup"><span data-stu-id="0f5d0-126">32-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

    - <span data-ttu-id="0f5d0-127">Sistemas de 64 bits:</span><span class="sxs-lookup"><span data-stu-id="0f5d0-127">64-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

     <span data-ttu-id="0f5d0-128">Esto garantiza que IIS se ejecuta correctamente una vez instalado WCF en el equipo.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-128">This makes sure that IIS runs correctly after WCF has been installed on the computer.</span></span> <span data-ttu-id="0f5d0-129">Es posible que también tenga que reiniciar IIS.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-129">You might have to also restart IIS.</span></span>

11. <span data-ttu-id="0f5d0-130">Cuando la aplicación ASP.NET se ejecuta en IIS7, también debe seguir estos pasos:</span><span class="sxs-lookup"><span data-stu-id="0f5d0-130">When the ASP.NET application runs on IIS7, you must also perform the following steps:</span></span>

    1. <span data-ttu-id="0f5d0-131">Abra el administrador de IIS y navegue hasta la aplicación de fotoservicio en **sitio web predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-131">Open IIS Manager and navigate to the PhotoService application under **Default Web Site**.</span></span>

    2. <span data-ttu-id="0f5d0-132">En la vista **Características**, haga doble clic en **Autenticación**.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-132">In **Features View**, double-click **Authentication**.</span></span>

    3. <span data-ttu-id="0f5d0-133">En la página **Autenticación**, seleccione **Autenticación anónima**.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-133">On the **Authentication** page, select **Anonymous Authentication**.</span></span>

    4. <span data-ttu-id="0f5d0-134">En el panel **acciones** , haga clic en **Editar** para establecer la entidad de seguridad en la que los usuarios anónimos se conectarán al sitio.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-134">In the **Actions** pane, click **Edit** to set the security principal under which anonymous users will connect to the site.</span></span>

    5. <span data-ttu-id="0f5d0-135">En el cuadro de diálogo **modificar credenciales de autenticación anónima** , seleccione **identidad del grupo de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-135">In the **Edit Anonymous Authentication Credentials** dialog box, select **Application pool identity**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0f5d0-136">Cuando se usa la cuenta Network Service, se concede a los usuarios anónimos el acceso a toda la red interna asociada a esa cuenta.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-136">When you use the Network Service account, you grant anonymous users all the internal network access associated with that account.</span></span>

12. <span data-ttu-id="0f5d0-137">Desde SQL Server Management Studio, la utilidad sqlcmd.exe o el Editor de Transact-SQL en Visual Studio, ejecute el siguiente comando de Transact-SQL con la instancia de SQL Server que tenga la base de datos Northwind asociada:</span><span class="sxs-lookup"><span data-stu-id="0f5d0-137">By using SQL Server Management Studio, the sqlcmd.exe utility, or the Transact-SQL Editor in Visual Studio, execute the following Transact-SQL command against the instance of SQL Server that has the Northwind database attached:</span></span>

    ```sql
    CREATE LOGIN [NT AUTHORITY\NETWORK SERVICE] FROM WINDOWS;
    GO
    ```

    <span data-ttu-id="0f5d0-138">De este modo, se crea un inicio de sesión en la instancia de SQL Server para la cuenta de Windows utilizada para ejecutar IIS.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-138">This creates a login in the SQL Server instance for the Windows account used to run IIS.</span></span> <span data-ttu-id="0f5d0-139">Esto permite a IIS conectarse a la instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-139">This enables IIS to connect to the SQL Server instance.</span></span>

13. <span data-ttu-id="0f5d0-140">Con la base de datos Northwind asociada, ejecute los siguientes comandos de Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="0f5d0-140">With the Northwind database attached, execute the following Transact-SQL commands:</span></span>

    ```sql
    USE Northwind
    GO
    CREATE USER [NT AUTHORITY\NETWORK SERVICE]
    FOR LOGIN [NT AUTHORITY\NETWORK SERVICE] WITH DEFAULT_SCHEMA=[dbo];
    GO
    ALTER LOGIN [NT AUTHORITY\NETWORK SERVICE]
    WITH DEFAULT_DATABASE=[Northwind];
    GO
    EXEC sp_addrolemember 'db_datareader', 'NT AUTHORITY\NETWORK SERVICE'
    GO
    EXEC sp_addrolemember 'db_datawriter', 'NT AUTHORITY\NETWORK SERVICE'
    GO
    ```

    <span data-ttu-id="0f5d0-141">Esto otorga derechos al inicio de sesión nuevo, lo que permite a IIS leer y escribir datos en la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-141">This grants rights to the new login, which enables IIS to read data from and write data to the Northwind database.</span></span>

## <a name="define-the-data-model"></a><span data-ttu-id="0f5d0-142">Definir el modelo de datos</span><span class="sxs-lookup"><span data-stu-id="0f5d0-142">Define the data model</span></span>

1. <span data-ttu-id="0f5d0-143">En **Explorador de soluciones**, haga clic con el botón secundario en el nombre del proyecto ASP.net y, a continuación, haga clic en **Agregar** > **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-143">In **Solution Explorer**, right-click the name of the ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="0f5d0-144">En el cuadro de diálogo **Agregar nuevo elemento** , seleccione **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-144">In the **Add New Item** dialog box, select **ADO.NET Entity Data Model**.</span></span>

3. <span data-ttu-id="0f5d0-145">Como nombre del modelo de datos, escriba `Northwind.edmx`.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-145">For the name of the data model, type `Northwind.edmx`.</span></span>

4. <span data-ttu-id="0f5d0-146">En el Asistente para Entity Data Model, seleccione **generar desde la base de datos**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-146">In the Entity Data Model Wizard, select **Generate from Database**, and then click **Next**.</span></span>

5. <span data-ttu-id="0f5d0-147">Conecte el modelo de datos a la base de datos mediante uno de los pasos siguientes y, a continuación, haga clic en **siguiente**:</span><span class="sxs-lookup"><span data-stu-id="0f5d0-147">Connect the data model to the database by doing one of the following steps, and then click **Next**:</span></span>

    - <span data-ttu-id="0f5d0-148">Si no tiene una conexión de base de datos ya configurada, haga clic en **nueva conexión** y cree una conexión nueva.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-148">If you do not have a database connection already configured, click **New Connection** and create a new connection.</span></span> <span data-ttu-id="0f5d0-149">Para obtener más información, consulta [How to: Create Connections to SQL Server Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="0f5d0-149">For more information, see [How to: Create Connections to SQL Server Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)).</span></span> <span data-ttu-id="0f5d0-150">Esta instancia de SQL Server debe tener asociada la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-150">This SQL Server instance must have the Northwind sample database attached.</span></span>

         <span data-ttu-id="0f5d0-151">\- o -</span><span class="sxs-lookup"><span data-stu-id="0f5d0-151">\- or -</span></span>

    - <span data-ttu-id="0f5d0-152">Si tiene una conexión de base de datos ya configurada para conectarse a la base de datos Northwind, seleccione esa conexión de la lista de conexiones.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-152">If you have a database connection already configured to connect to the Northwind database, select that connection from the list of connections.</span></span>

6. <span data-ttu-id="0f5d0-153">En la página final del asistente, seleccione las casillas de todas las tablas de la base de datos y desactive las casillas correspondientes a las vistas y procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-153">On the final page of the wizard, select the check boxes for all tables in the database, and clear the check boxes for views and stored procedures.</span></span>

7. <span data-ttu-id="0f5d0-154">Haga clic en **Finalizar** para cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-154">Click **Finish** to close the wizard.</span></span>

## <a name="create-the-data-service"></a><span data-ttu-id="0f5d0-155">Crear el servicio de datos</span><span class="sxs-lookup"><span data-stu-id="0f5d0-155">Create the data service</span></span>

1. <span data-ttu-id="0f5d0-156">En **Explorador de soluciones**, haga clic con el botón secundario en el nombre del proyecto ASP.net y, a continuación, haga clic en **Agregar** > **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-156">In **Solution Explorer**, right-click the name of your ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="0f5d0-157">En el cuadro de diálogo **Agregar nuevo elemento** , seleccione **servicio de datos de WCF**.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-157">In the **Add New Item** dialog box, select **WCF Data Service**.</span></span>

   ![Plantilla de elemento de servicio de datos de WCF en Visual Studio 2015](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="0f5d0-159">La plantilla de **servicio de datos de WCF** está disponible en visual Studio 2015, pero no en visual Studio 2017 o posterior.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-159">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017 or later.</span></span>

3. <span data-ttu-id="0f5d0-160">Como nombre del servicio, escriba `Northwind`.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-160">For the name of the service, enter `Northwind`.</span></span>

     <span data-ttu-id="0f5d0-161">Visual Studio crea los archivos de código y marcado XML para el nuevo servicio.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-161">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="0f5d0-162">De forma predeterminada, se abre la ventana del editor de código.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-162">By default, the code-editor window opens.</span></span> <span data-ttu-id="0f5d0-163">En **Explorador de soluciones**, el servicio tiene el nombre, Northwind, y la extensión. SVC.cs o. SVC. VB.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-163">In **Solution Explorer**, the service has the name, Northwind, and the extension .svc.cs or .svc.vb.</span></span>

4. <span data-ttu-id="0f5d0-164">En el código para el servicio de datos, reemplace el comentario `/* TODO: put your data source class name here */` de la definición de la clase que define el servicio de datos por el tipo que es el contenedor de entidades del modelo de datos, que en este caso es `NorthwindEntities`.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-164">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindEntities`.</span></span> <span data-ttu-id="0f5d0-165">La definición de la clase debería ser como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="0f5d0-165">The class definition should look this the following:</span></span>

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

## <a name="see-also"></a><span data-ttu-id="0f5d0-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f5d0-166">See also</span></span>

- [<span data-ttu-id="0f5d0-167">Exposición de los datos como servicio</span><span class="sxs-lookup"><span data-stu-id="0f5d0-167">Exposing Your Data as a Service</span></span>](exposing-your-data-as-a-service-wcf-data-services.md)
