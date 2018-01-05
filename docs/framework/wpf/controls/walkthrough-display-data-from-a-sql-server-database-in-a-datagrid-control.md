---
title: 'Tutorial: Mostrar los datos de una base de datos de SQL Server en un control DataGrid'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], displaying data from SQL Server
- controls [WPF], DataGrid
ms.assetid: 6810b048-0a23-4f86-bfa5-97f92b3cfab4
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3c8ed596706c8d656842191262c25301db595ee3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control"></a><span data-ttu-id="94033-102">Tutorial: Mostrar los datos de una base de datos de SQL Server en un control DataGrid</span><span class="sxs-lookup"><span data-stu-id="94033-102">Walkthrough: Display Data from a SQL Server Database in a DataGrid Control</span></span>
<span data-ttu-id="94033-103">En este tutorial, recuperar datos de una base de datos de SQL Server y mostrar dichos datos en un <xref:System.Windows.Controls.DataGrid> control.</span><span class="sxs-lookup"><span data-stu-id="94033-103">In this walkthrough, you retrieve data from a SQL Server database and display that data in a <xref:System.Windows.Controls.DataGrid> control.</span></span> <span data-ttu-id="94033-104">Usar ADO.NET Entity Framework para crear las clases de entidad que representan los datos y usar LINQ para escribir una consulta que recupera los datos especificados de una clase de entidad.</span><span class="sxs-lookup"><span data-stu-id="94033-104">You use the ADO.NET Entity Framework to create the entity classes that represent the data, and use LINQ to write a query that retrieves the specified data from an entity class.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="94033-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="94033-105">Prerequisites</span></span>  
 <span data-ttu-id="94033-106">Necesita los componentes siguientes para completar este tutorial:</span><span class="sxs-lookup"><span data-stu-id="94033-106">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]<span data-ttu-id="94033-107">.</span><span class="sxs-lookup"><span data-stu-id="94033-107">.</span></span>  
  
-   <span data-ttu-id="94033-108">Acceso a una instancia en ejecución de SQL Server o SQL Server Express que tenga adjunta la base de datos de ejemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="94033-108">Access to a running instance of SQL Server or SQL Server Express that has the AdventureWorks sample database attached to it.</span></span> <span data-ttu-id="94033-109">Puede descargar la base de datos de AdventureWorks desde el [GitHub](https://github.com/Microsoft/sql-server-samples/releases).</span><span class="sxs-lookup"><span data-stu-id="94033-109">You can download the AdventureWorks database from the [GitHub](https://github.com/Microsoft/sql-server-samples/releases).</span></span>  
  
### <a name="to-create-entity-classes"></a><span data-ttu-id="94033-110">Para crear las clases de entidad</span><span class="sxs-lookup"><span data-stu-id="94033-110">To create entity classes</span></span>  
  
1.  <span data-ttu-id="94033-111">Crear un nuevo proyecto de aplicación WPF en Visual Basic o C# y asígnele el nombre `DataGridSQLExample`.</span><span class="sxs-lookup"><span data-stu-id="94033-111">Create a new WPF Application project in Visual Basic or C#, and name it `DataGridSQLExample`.</span></span>  
  
2.  <span data-ttu-id="94033-112">En el Explorador de soluciones, haga clic en el proyecto, seleccione **agregar**y, a continuación, seleccione **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="94033-112">In Solution Explorer, right-click your project, point to **Add**, and then select **New Item**.</span></span>  
  
     <span data-ttu-id="94033-113">Aparecerá el cuadro de diálogo Agregar nuevo elemento.</span><span class="sxs-lookup"><span data-stu-id="94033-113">The Add New Item dialog box appears.</span></span>  
  
3.  <span data-ttu-id="94033-114">En el panel Plantillas instaladas, seleccione **datos** y en la lista de plantillas, seleccione **modo de datos de entidad de ADO.NET**l.</span><span class="sxs-lookup"><span data-stu-id="94033-114">In the Installed Templates pane, select **Data** and in the list of templates, select **ADO.NET Entity Data Mode**l.</span></span>  
  
     <span data-ttu-id="94033-115">![Seleccione ADO.NET Entity Data Model](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step1.png "DataGrid_SQL_EF_Step1")</span><span class="sxs-lookup"><span data-stu-id="94033-115">![Select ADO.NET Entity Data Model](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step1.png "DataGrid_SQL_EF_Step1")</span></span>  
  
4.  <span data-ttu-id="94033-116">Asignar nombre al archivo `AdventureWorksModel.edmx` y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="94033-116">Name the file `AdventureWorksModel.edmx` and then click **Add**.</span></span>  
  
     <span data-ttu-id="94033-117">Aparecerá el Asistente para Entity Data Model.</span><span class="sxs-lookup"><span data-stu-id="94033-117">The Entity Data Model Wizard appears.</span></span>  
  
5.  <span data-ttu-id="94033-118">En la pantalla Elegir contenido del modelo, seleccione **generar desde la base de datos** y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="94033-118">In the Choose Model Contents screen, select **Generate from database** and then click **Next**.</span></span>  
  
     <span data-ttu-id="94033-119">![Seleccione Generar desde la opción de base de datos](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step2.png "DataGrid_SQL_EF_Step2")</span><span class="sxs-lookup"><span data-stu-id="94033-119">![Select Generate from database option](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step2.png "DataGrid_SQL_EF_Step2")</span></span>  
  
6.  <span data-ttu-id="94033-120">En la pantalla Elegir la conexión de datos, proporcione la conexión a la base de datos AdventureWorksLT2008.</span><span class="sxs-lookup"><span data-stu-id="94033-120">In the Choose Your Data Connection screen, provide the connection to your AdventureWorksLT2008 database.</span></span> <span data-ttu-id="94033-121">Para obtener más información, consulte [elija el cuadro de diálogo de conexión de datos](http://go.microsoft.com/fwlink/?LinkId=160190).</span><span class="sxs-lookup"><span data-stu-id="94033-121">For more information, see [Choose Your Data Connection Dialog Box](http://go.microsoft.com/fwlink/?LinkId=160190).</span></span>  
  
     <span data-ttu-id="94033-122">![Proporcionar conexión a base de datos](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step3.png "DataGrid_SQL_EF_Step3")</span><span class="sxs-lookup"><span data-stu-id="94033-122">![Provide connection to database](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step3.png "DataGrid_SQL_EF_Step3")</span></span>  
  
7.  <span data-ttu-id="94033-123">Asegúrese de que el nombre es `AdventureWorksLT2008Entities` y que la **Guardar configuración de conexión de entidad en App.Config como** casilla de verificación está seleccionada y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="94033-123">Make sure that the name is `AdventureWorksLT2008Entities` and that the **Save entity connection settings in App.Config as** check box is selected, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="94033-124">En la pantalla Elija los objetos de base de datos, expanda el nodo tablas y seleccione la **producto** y **ProductCategory** tablas.</span><span class="sxs-lookup"><span data-stu-id="94033-124">In the Choose Your Database Objects screen, expand the Tables node, and select the **Product** and **ProductCategory** tables.</span></span>  
  
     <span data-ttu-id="94033-125">También puede generar clases de entidad para todas las tablas; Sin embargo, en este ejemplo solo recuperar datos de esas dos tablas.</span><span class="sxs-lookup"><span data-stu-id="94033-125">You can generate entity classes for all of the tables; however, in this example you only retrieve data from those two tables.</span></span>  
  
     <span data-ttu-id="94033-126">![Seleccionar Product y ProductCategory de tablas](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step4.png "DataGrid_SQL_EF_Step4")</span><span class="sxs-lookup"><span data-stu-id="94033-126">![Select Product and ProductCategory from tables](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step4.png "DataGrid_SQL_EF_Step4")</span></span>  
  
9. <span data-ttu-id="94033-127">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="94033-127">Click **Finish**.</span></span>  
  
     <span data-ttu-id="94033-128">Las entidades Product y ProductCategory se muestran en el Diseñador de entidades.</span><span class="sxs-lookup"><span data-stu-id="94033-128">The Product and ProductCategory entities are displayed in the Entity Designer.</span></span>  
  
     <span data-ttu-id="94033-129">![Modelos de entidad de Product y ProductCategory](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step5.png "DataGrid_SQL_EF_Step5")</span><span class="sxs-lookup"><span data-stu-id="94033-129">![Product and ProductCategory entity models](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step5.png "DataGrid_SQL_EF_Step5")</span></span>  
  
### <a name="to-retrieve-and-present-the-data"></a><span data-ttu-id="94033-130">Para recuperar y presentar los datos</span><span class="sxs-lookup"><span data-stu-id="94033-130">To retrieve and present the data</span></span>  
  
1.  <span data-ttu-id="94033-131">Abra el archivo MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="94033-131">Open the MainWindow.xaml file.</span></span>  
  
2.  <span data-ttu-id="94033-132">Establecer el <xref:System.Windows.FrameworkElement.Width%2A> propiedad en la <xref:System.Windows.Window> a 450.</span><span class="sxs-lookup"><span data-stu-id="94033-132">Set the <xref:System.Windows.FrameworkElement.Width%2A> property on the <xref:System.Windows.Window> to 450.</span></span>  
  
3.  <span data-ttu-id="94033-133">En el editor XAML, agregue el siguiente <xref:System.Windows.Controls.DataGrid> etiqueta entre el `<Grid>` y `</Grid>` etiquetas para agregar una <xref:System.Windows.Controls.DataGrid> denominado `dataGrid1`.</span><span class="sxs-lookup"><span data-stu-id="94033-133">In the XAML editor, add the following <xref:System.Windows.Controls.DataGrid> tag between the `<Grid>` and `</Grid>` tags to add a <xref:System.Windows.Controls.DataGrid> named `dataGrid1`.</span></span>  
  
     [!code-xaml[DataGrid_SQL_EF_Walkthrough#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#3)]  
  
     <span data-ttu-id="94033-134">![Ventana con DataGrid](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step6.png "DataGrid_SQL_EF_Step6")</span><span class="sxs-lookup"><span data-stu-id="94033-134">![Window with DataGrid](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step6.png "DataGrid_SQL_EF_Step6")</span></span>  
  
4.  <span data-ttu-id="94033-135">Seleccione el control <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="94033-135">Select the <xref:System.Windows.Window>.</span></span>  
  
5.  <span data-ttu-id="94033-136">Con la ventana Propiedades o el editor XAML, cree un controlador de eventos para el <xref:System.Windows.Window> denominado `Window_Loaded` para el <xref:System.Windows.FrameworkElement.Loaded> eventos.</span><span class="sxs-lookup"><span data-stu-id="94033-136">Using the Properties window or XAML editor, create an event handler for the <xref:System.Windows.Window> named `Window_Loaded` for the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span> <span data-ttu-id="94033-137">Para obtener más información, consulte [Cómo: crear un controlador de eventos Simple](http://msdn.microsoft.com/en-us/b1456e07-9dec-4354-99cf-18666b64f480).</span><span class="sxs-lookup"><span data-stu-id="94033-137">For more information, see [How to: Create a Simple Event Handler](http://msdn.microsoft.com/en-us/b1456e07-9dec-4354-99cf-18666b64f480).</span></span>  
  
     <span data-ttu-id="94033-138">A continuación muestra el código XAML de MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="94033-138">The following shows the XAML for MainWindow.xaml.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="94033-139">Si utiliza Visual Basic, en la primera línea de MainWindow.xaml, reemplace `x:Class="DataGridSQLExample.MainWindow"` con `x:Class="MainWindow"`.</span><span class="sxs-lookup"><span data-stu-id="94033-139">If you are using Visual Basic, in the first line of MainWindow.xaml, replace `x:Class="DataGridSQLExample.MainWindow"` with `x:Class="MainWindow"`.</span></span>  
  
     [!code-xaml[DataGrid_SQL_EF_Walkthrough#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#1)]  
  
6.  <span data-ttu-id="94033-140">Abra el archivo de código subyacente (MainWindow.xaml.vb o MainWindow.xaml.cs) para el <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="94033-140">Open the code-behind file (MainWindow.xaml.vb or MainWindow.xaml.cs) for the <xref:System.Windows.Window>.</span></span>  
  
7.  <span data-ttu-id="94033-141">Agregue el código siguiente para recuperar solo los valores específicos de las tablas combinadas y establecer el <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> propiedad de la <xref:System.Windows.Controls.DataGrid> a los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="94033-141">Add the following code to retrieve only specific values from the joined tables and set the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.DataGrid> to the results of the query.</span></span>  
  
     [!code-csharp[DataGrid_SQL_EF_Walkthrough#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml.cs#2)]
     [!code-vb[DataGrid_SQL_EF_Walkthrough#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/VB/MainWindow.xaml.vb#2)]  
  
8.  <span data-ttu-id="94033-142">Ejecute el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="94033-142">Run the example.</span></span>  
  
     <span data-ttu-id="94033-143">Debería ver un <xref:System.Windows.Controls.DataGrid> que muestra los datos.</span><span class="sxs-lookup"><span data-stu-id="94033-143">You should see a <xref:System.Windows.Controls.DataGrid> that displays data.</span></span>  
  
     <span data-ttu-id="94033-144">![DataGrid con datos de base de datos SQL](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step7.png "DataGrid_SQL_EF_Step7")</span><span class="sxs-lookup"><span data-stu-id="94033-144">![DataGrid with data from SQL database](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step7.png "DataGrid_SQL_EF_Step7")</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="94033-145">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="94033-145">Next Steps</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94033-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="94033-146">See Also</span></span>  
 <xref:System.Windows.Controls.DataGrid>  
 [<span data-ttu-id="94033-147">¿Cómo I: comenzar con Entity Framework en aplicaciones WPF?</span><span class="sxs-lookup"><span data-stu-id="94033-147">How Do I: Get Started with Entity Framework in WPF Applications?</span></span>](http://go.microsoft.com/fwlink/?LinkId=159868)
