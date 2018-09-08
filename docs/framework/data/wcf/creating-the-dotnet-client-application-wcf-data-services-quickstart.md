---
title: Crear la aplicación cliente de .NET Framework (Inicio rápido de Data Services de WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 41ade767-eeab-437d-9121-9797e8fb8045
ms.openlocfilehash: 86ded7351d435b3a7077f0354d8a923b33a3f2b6
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44216508"
---
# <a name="creating-the-net-framework-client-application-wcf-data-services-quickstart"></a><span data-ttu-id="47c85-102">Crear la aplicación cliente de .NET Framework (Inicio rápido de Data Services de WCF)</span><span class="sxs-lookup"><span data-stu-id="47c85-102">Creating the .NET Framework Client Application (WCF Data Services Quickstart)</span></span>

<span data-ttu-id="47c85-103">Se trata de la tarea final de la Guía de inicio rápido de WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="47c85-103">This is the final task of the WCF Data Services quickstart.</span></span> <span data-ttu-id="47c85-104">En esta tarea, agregará una aplicación de consola a la solución, agregue una referencia a la [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] se envían a esta nueva aplicación de cliente y tener acceso a la fuente de la aplicación cliente mediante el uso de las clases de servicio de datos de cliente generado y bibliotecas de cliente de OData .</span><span class="sxs-lookup"><span data-stu-id="47c85-104">In this task, you will add a console application to the solution, add a reference to the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed into this new client application, and access the OData feed from the client application by using the generated client data service classes and client libraries.</span></span>

> [!NOTE]
> <span data-ttu-id="47c85-105">No es necesaria una aplicación cliente basada en .NET Framework para obtener acceso a una fuente de datos.</span><span class="sxs-lookup"><span data-stu-id="47c85-105">A .NET Framework-based client application is not required to access a data feed.</span></span> <span data-ttu-id="47c85-106">Puede tener acceso al servicio de datos por cualquier componente de aplicación que consume una fuente de OData.</span><span class="sxs-lookup"><span data-stu-id="47c85-106">The data service can be accessed by any application component that consumes an OData feed.</span></span> <span data-ttu-id="47c85-107">Para obtener más información, consulte [mediante un servicio de datos en una aplicación cliente](../../../../docs/framework/data/wcf/using-a-data-service-in-a-client-application-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="47c85-107">For more information, see [Using a Data Service in a Client Application](../../../../docs/framework/data/wcf/using-a-data-service-in-a-client-application-wcf-data-services.md).</span></span>

## <a name="to-create-the-client-application-by-using-visual-studio"></a><span data-ttu-id="47c85-108">Para crear la aplicación cliente mediante Visual Studio</span><span class="sxs-lookup"><span data-stu-id="47c85-108">To create the client application by using Visual Studio</span></span>

1.  <span data-ttu-id="47c85-109">En **el Explorador de soluciones**, haga clic en la solución, haga clic en **agregar**y, a continuación, haga clic en **nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="47c85-109">In **Solution Explorer**, right-click the solution, click **Add**, and then click **New Project**.</span></span>

2.  <span data-ttu-id="47c85-110">En el panel izquierdo, seleccione **instalado** > [**Visual C#** o **Visual Basic**] > **Windows Desktop**y, a continuación, seleccione el **Aplicación WPF** plantilla.</span><span class="sxs-lookup"><span data-stu-id="47c85-110">In the left pane, select **Installed** > [**Visual C#** or **Visual Basic**] > **Windows Desktop**, and then select the **WPF App** template.</span></span>

3.  <span data-ttu-id="47c85-111">Escriba `NorthwindClient` para el nombre del proyecto y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="47c85-111">Enter `NorthwindClient` for the project name, and then click **OK**.</span></span>

4.  <span data-ttu-id="47c85-112">Abra el archivo MainWindow.xaml y reemplace el código XAML con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="47c85-112">Open the file MainWindow.xaml and replace the XAML code with the following code:</span></span>

     [!code-xaml[Astoria Quickstart Client#Window1Xaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml#window1xaml)]

## <a name="to-add-a-data-service-reference-to-the-project"></a><span data-ttu-id="47c85-113">Para agregar al proyecto una referencia al servicio de datos</span><span class="sxs-lookup"><span data-stu-id="47c85-113">To add a data service reference to the project</span></span>

1.  <span data-ttu-id="47c85-114">En **el Explorador de soluciones**, haga clic en el proyecto NorthwindClient, haga clic en **agregar** > **referencia de servicio**y, a continuación, haga clic en **Discover** .</span><span class="sxs-lookup"><span data-stu-id="47c85-114">In **Solution Explorer**, right-click the NorthwindClient project, click **Add** > **Service Reference**, and then click **Discover**.</span></span>

     <span data-ttu-id="47c85-115">De este modo se muestra el servicio de datos de Northwind que creó en la primera tarea.</span><span class="sxs-lookup"><span data-stu-id="47c85-115">This displays the Northwind data service that you created in the first task.</span></span>

2.  <span data-ttu-id="47c85-116">En el **Namespace** cuadro de texto, escriba `Northwind`y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="47c85-116">In the **Namespace** text box, type `Northwind`, and then click **OK**.</span></span>

     <span data-ttu-id="47c85-117">De este modo se agrega un nuevo archivo de código al proyecto, que contiene las clases de datos que se usan para obtener acceso e interactuar con los recursos del servicio de datos como objetos.</span><span class="sxs-lookup"><span data-stu-id="47c85-117">This adds a new code file to the project, which contains the data classes that are used to access and interact with data service resources as objects.</span></span> <span data-ttu-id="47c85-118">Las clases de datos se crean en el espacio de nombres `NorthwindClient.Northwind`.</span><span class="sxs-lookup"><span data-stu-id="47c85-118">The data classes are created in the namespace `NorthwindClient.Northwind`.</span></span>

## <a name="to-access-data-service-data-in-the-wpf-application"></a><span data-ttu-id="47c85-119">Para tener acceso a los datos del servicio de datos en la aplicación WPF</span><span class="sxs-lookup"><span data-stu-id="47c85-119">To access data service data in the WPF application</span></span>

1.  <span data-ttu-id="47c85-120">En **el Explorador de soluciones** en **NorthwindClient**, haga clic en el proyecto y haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="47c85-120">In **Solution Explorer** under **NorthwindClient**, right-click the project and click **Add Reference**.</span></span>

2.  <span data-ttu-id="47c85-121">En el **Agregar referencia** cuadro de diálogo, haga clic en el **.NET** , seleccione el ensamblado System.Data.Services.Client.dll y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="47c85-121">In the **Add Reference** dialog box, click the **.NET** tab, select the System.Data.Services.Client.dll assembly, and then click **OK**.</span></span>

3. <span data-ttu-id="47c85-122">En **el Explorador de soluciones** en **NorthwindClient**, abra la página de códigos para el archivo MainWindow.xaml y agregue las siguientes `using` instrucción (`Imports` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="47c85-122">In **Solution Explorer** under **NorthwindClient**, open the code page for the MainWindow.xaml file, and add the following `using` statement (`Imports` in Visual Basic).</span></span>

     [!code-csharp[Astoria Quickstart Client#Using](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart client/cs/window1.xaml.cs#using)]
     [!code-vb[Astoria Quickstart Client#Using](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml.vb#using)]

3.  <span data-ttu-id="47c85-123">Inserte el código siguiente que consulta al servicio de datos y enlaza el resultado a una instancia de <xref:System.Data.Services.Client.DataServiceCollection%601> en la clase `MainWindow`:</span><span class="sxs-lookup"><span data-stu-id="47c85-123">Insert the following code that queries that data service and binds the result to a <xref:System.Data.Services.Client.DataServiceCollection%601> into the `MainWindow` class:</span></span>

    > [!NOTE]
    > <span data-ttu-id="47c85-124">Debe reemplazar el nombre de host `localhost:12345` por el servidor y el puerto en que se hospeda la instancia del servicio de datos de Northwind.</span><span class="sxs-lookup"><span data-stu-id="47c85-124">You must replace the host name `localhost:12345` with the server and port that is hosting your instance of the Northwind data service.</span></span>

     [!code-csharp[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart client/cs/window1.xaml.cs#querycode)]
     [!code-vb[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml.vb#querycode)]

4.  <span data-ttu-id="47c85-125">Inserte el código siguiente que guarda los cambios en la clase `MainWindow`:</span><span class="sxs-lookup"><span data-stu-id="47c85-125">Insert the following code that saves changes into the `MainWindow` class:</span></span>

     [!code-csharp[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart client/cs/window1.xaml.cs#savechanges)]
     [!code-vb[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml.vb#savechanges)]

## <a name="to-build-and-run-the-northwindclient-application"></a><span data-ttu-id="47c85-126">Para compilar y ejecutar la aplicación NorthwindClient</span><span class="sxs-lookup"><span data-stu-id="47c85-126">To build and run the NorthwindClient application</span></span>

1.  <span data-ttu-id="47c85-127">En **el Explorador de soluciones**, haga clic en el proyecto NorthwindClient y seleccione **establecer como proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="47c85-127">In **Solution Explorer**, right-click the NorthwindClient project and select **Set as startup project**.</span></span>

2.  <span data-ttu-id="47c85-128">Presione **F5** para iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="47c85-128">Press **F5** to start the application.</span></span>

     <span data-ttu-id="47c85-129">Se compila la solución y se inicia la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="47c85-129">This builds the solution and starts the client application.</span></span> <span data-ttu-id="47c85-130">Los datos se solicitarán al servicio y se mostrarán en la consola.</span><span class="sxs-lookup"><span data-stu-id="47c85-130">Data is requested from the service and displayed in the console.</span></span>

3.  <span data-ttu-id="47c85-131">Modificar un valor en el **cantidad** columna de la cuadrícula de datos y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="47c85-131">Edit a value in the **Quantity** column of the data grid, and then click **Save**.</span></span>

     <span data-ttu-id="47c85-132">Los cambios se guardan en el servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="47c85-132">Changes are saved to the data service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="47c85-133">Esta versión de la aplicación NorthwindClient no admite agregar ni eliminar entidades.</span><span class="sxs-lookup"><span data-stu-id="47c85-133">This version of the NorthwindClient application does not support adding and deleting of entities.</span></span>

## <a name="next-steps"></a><span data-ttu-id="47c85-134">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="47c85-134">Next Steps</span></span>

<span data-ttu-id="47c85-135">Ha creado correctamente la aplicación cliente que tiene acceso a la fuente de OData de Northwind de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="47c85-135">You have successfully created the client application that accesses the sample Northwind OData feed.</span></span> <span data-ttu-id="47c85-136">También ha completado la Guía de inicio rápido de WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="47c85-136">You've also completed the WCF Data Services quickstart!</span></span>

<span data-ttu-id="47c85-137">Para obtener más información sobre el acceso a OData fuente de distribución desde un [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] aplicación, consulte [biblioteca de cliente de WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md).</span><span class="sxs-lookup"><span data-stu-id="47c85-137">For more information about accessing an OData feed from a [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] application, see [WCF Data Services Client Library](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="47c85-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="47c85-138">See Also</span></span>

- [<span data-ttu-id="47c85-139">Introducción</span><span class="sxs-lookup"><span data-stu-id="47c85-139">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)
- [<span data-ttu-id="47c85-140">Recursos</span><span class="sxs-lookup"><span data-stu-id="47c85-140">Resources</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)
