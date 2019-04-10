---
title: 'Tutorial: Mostrar los datos de una base de datos de SQL Server en un control DataGrid'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], displaying data from SQL Server
- controls [WPF], DataGrid
ms.assetid: 6810b048-0a23-4f86-bfa5-97f92b3cfab4
ms.openlocfilehash: 274ec2e8ef16190da53061bb197bc3b1a1fadcf8
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59336114"
---
# <a name="walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control"></a><span data-ttu-id="6e4af-102">Tutorial: Mostrar los datos de una base de datos de SQL Server en un control DataGrid</span><span class="sxs-lookup"><span data-stu-id="6e4af-102">Walkthrough: Display data from a SQL Server database in a DataGrid control</span></span>

<span data-ttu-id="6e4af-103">En este tutorial, recuperar datos de una base de datos de SQL Server y mostrar dichos datos en un <xref:System.Windows.Controls.DataGrid> control.</span><span class="sxs-lookup"><span data-stu-id="6e4af-103">In this walkthrough, you retrieve data from a SQL Server database and display that data in a <xref:System.Windows.Controls.DataGrid> control.</span></span> <span data-ttu-id="6e4af-104">Usar ADO.NET Entity Framework para crear las clases de entidad que representan los datos y usar LINQ para escribir una consulta que recupera los datos especificados de una clase de entidad.</span><span class="sxs-lookup"><span data-stu-id="6e4af-104">You use the ADO.NET Entity Framework to create the entity classes that represent the data, and use LINQ to write a query that retrieves the specified data from an entity class.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6e4af-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6e4af-105">Prerequisites</span></span>

<span data-ttu-id="6e4af-106">Necesita los componentes siguientes para completar este tutorial:</span><span class="sxs-lookup"><span data-stu-id="6e4af-106">You need the following components to complete this walkthrough:</span></span>

-   <span data-ttu-id="6e4af-107">Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6e4af-107">Visual Studio.</span></span>

-   <span data-ttu-id="6e4af-108">Acceso a una instancia en ejecución de SQL Server o SQL Server Express que tiene la base de datos de ejemplo AdventureWorks conectada a ella.</span><span class="sxs-lookup"><span data-stu-id="6e4af-108">Access to a running instance of SQL Server or SQL Server Express that has the AdventureWorks sample database attached to it.</span></span> <span data-ttu-id="6e4af-109">Puede descargar la base de datos de AdventureWorks desde el [GitHub](https://github.com/Microsoft/sql-server-samples/releases).</span><span class="sxs-lookup"><span data-stu-id="6e4af-109">You can download the AdventureWorks database from the [GitHub](https://github.com/Microsoft/sql-server-samples/releases).</span></span>

## <a name="create-entity-classes"></a><span data-ttu-id="6e4af-110">Crear clases de entidad</span><span class="sxs-lookup"><span data-stu-id="6e4af-110">Create entity classes</span></span>

1. <span data-ttu-id="6e4af-111">Cree un nuevo proyecto de aplicación de WPF en Visual Basic o C# y asígnele el nombre `DataGridSQLExample`.</span><span class="sxs-lookup"><span data-stu-id="6e4af-111">Create a new WPF Application project in Visual Basic or C#, and name it `DataGridSQLExample`.</span></span>

2. <span data-ttu-id="6e4af-112">En el Explorador de soluciones, haga clic en el proyecto, seleccione **agregar**y, a continuación, seleccione **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="6e4af-112">In Solution Explorer, right-click your project, point to **Add**, and then select **New Item**.</span></span>

     <span data-ttu-id="6e4af-113">Aparece el cuadro de diálogo Agregar nuevo elemento.</span><span class="sxs-lookup"><span data-stu-id="6e4af-113">The Add New Item dialog box appears.</span></span>

3. <span data-ttu-id="6e4af-114">En el panel Plantillas instaladas, seleccione **datos** y en la lista de plantillas, seleccione **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="6e4af-114">In the Installed Templates pane, select **Data** and in the list of templates, select **ADO.NET Entity Data Model**.</span></span>

     ![Plantilla de elemento de Entity Data Model ADO.NET](../../wcf/feature-details/./media/ado-net-entity-data-model-item-template.png)

4. <span data-ttu-id="6e4af-116">Nombre del archivo `AdventureWorksModel.edmx` y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="6e4af-116">Name the file `AdventureWorksModel.edmx` and then click **Add**.</span></span>

     <span data-ttu-id="6e4af-117">Aparecerá el Asistente para Entity Data Model.</span><span class="sxs-lookup"><span data-stu-id="6e4af-117">The Entity Data Model Wizard appears.</span></span>

5. <span data-ttu-id="6e4af-118">En la pantalla Elegir contenido del modelo, seleccione **EF Designer de base de datos** y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6e4af-118">In the Choose Model Contents screen, select **EF Designer from database** and then click **Next**.</span></span>

6. <span data-ttu-id="6e4af-119">En la pantalla Elegir la conexión de datos, proporcione la conexión a la base de datos AdventureWorksLT2008.</span><span class="sxs-lookup"><span data-stu-id="6e4af-119">In the Choose Your Data Connection screen, provide the connection to your AdventureWorksLT2008 database.</span></span> <span data-ttu-id="6e4af-120">Para obtener más información, consulte [elija el cuadro de diálogo de conexión de datos](https://go.microsoft.com/fwlink/?LinkId=160190).</span><span class="sxs-lookup"><span data-stu-id="6e4af-120">For more information, see [Choose Your Data Connection Dialog Box](https://go.microsoft.com/fwlink/?LinkId=160190).</span></span>

    <span data-ttu-id="6e4af-121">Asegúrese de que el nombre es `AdventureWorksLT2008Entities` y que la **Guardar configuración de conexión de entidad en App.Config como** casilla de verificación está seleccionada y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6e4af-121">Make sure that the name is `AdventureWorksLT2008Entities` and that the **Save entity connection settings in App.Config as** check box is selected, and then click **Next**.</span></span>

7. <span data-ttu-id="6e4af-122">En la pantalla Elegir los objetos de base de datos, expanda el nodo tablas y seleccione el **producto** y **ProductCategory** tablas.</span><span class="sxs-lookup"><span data-stu-id="6e4af-122">In the Choose Your Database Objects screen, expand the Tables node, and select the **Product** and **ProductCategory** tables.</span></span>

     <span data-ttu-id="6e4af-123">Puede generar clases de entidad para todas las tablas; Sin embargo, en este ejemplo solo recuperar datos de esas dos tablas.</span><span class="sxs-lookup"><span data-stu-id="6e4af-123">You can generate entity classes for all of the tables; however, in this example you only retrieve data from those two tables.</span></span>

     <span data-ttu-id="6e4af-124">![Seleccionar Product y ProductCategory de las tablas](./media/datagrid-sql-ef-step4.png "DataGrid_SQL_EF_Step4")</span><span class="sxs-lookup"><span data-stu-id="6e4af-124">![Select Product and ProductCategory from tables](./media/datagrid-sql-ef-step4.png "DataGrid_SQL_EF_Step4")</span></span>

8. <span data-ttu-id="6e4af-125">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="6e4af-125">Click **Finish**.</span></span>

     <span data-ttu-id="6e4af-126">Las entidades Product y ProductCategory se muestran en el Diseñador de entidades.</span><span class="sxs-lookup"><span data-stu-id="6e4af-126">The Product and ProductCategory entities are displayed in the Entity Designer.</span></span>

     <span data-ttu-id="6e4af-127">![Modelos de entidad de Product y ProductCategory](./media/datagrid-sql-ef-step5.png "DataGrid_SQL_EF_Step5")</span><span class="sxs-lookup"><span data-stu-id="6e4af-127">![Product and ProductCategory entity models](./media/datagrid-sql-ef-step5.png "DataGrid_SQL_EF_Step5")</span></span>

## <a name="retrieve-and-present-the-data"></a><span data-ttu-id="6e4af-128">Recuperar y presentar los datos</span><span class="sxs-lookup"><span data-stu-id="6e4af-128">Retrieve and present the data</span></span>

1. <span data-ttu-id="6e4af-129">Abra el archivo MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="6e4af-129">Open the MainWindow.xaml file.</span></span>

2. <span data-ttu-id="6e4af-130">Establecer el <xref:System.Windows.FrameworkElement.Width%2A> propiedad en el <xref:System.Windows.Window> a 450.</span><span class="sxs-lookup"><span data-stu-id="6e4af-130">Set the <xref:System.Windows.FrameworkElement.Width%2A> property on the <xref:System.Windows.Window> to 450.</span></span>

3. <span data-ttu-id="6e4af-131">En el editor XAML, agregue el siguiente <xref:System.Windows.Controls.DataGrid> etiqueta entre el `<Grid>` y `</Grid>` etiquetas para agregar un <xref:System.Windows.Controls.DataGrid> denominado `dataGrid1`.</span><span class="sxs-lookup"><span data-stu-id="6e4af-131">In the XAML editor, add the following <xref:System.Windows.Controls.DataGrid> tag between the `<Grid>` and `</Grid>` tags to add a <xref:System.Windows.Controls.DataGrid> named `dataGrid1`.</span></span>

     [!code-xaml[DataGrid_SQL_EF_Walkthrough#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#3)]

     <span data-ttu-id="6e4af-132">![Ventana con DataGrid](./media/datagrid-sql-ef-step6.png "DataGrid_SQL_EF_Step6")</span><span class="sxs-lookup"><span data-stu-id="6e4af-132">![Window with DataGrid](./media/datagrid-sql-ef-step6.png "DataGrid_SQL_EF_Step6")</span></span>

4. <span data-ttu-id="6e4af-133">Seleccione el control <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="6e4af-133">Select the <xref:System.Windows.Window>.</span></span>

5. <span data-ttu-id="6e4af-134">Con la ventana Propiedades o el editor XAML, cree un controlador de eventos para el <xref:System.Windows.Window> denominado `Window_Loaded` para el <xref:System.Windows.FrameworkElement.Loaded> eventos.</span><span class="sxs-lookup"><span data-stu-id="6e4af-134">Using the Properties window or XAML editor, create an event handler for the <xref:System.Windows.Window> named `Window_Loaded` for the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span> <span data-ttu-id="6e4af-135">Para obtener más información, vea [Cómo: Crear un controlador de eventos Simple](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="6e4af-135">For more information, see [How to: Create a Simple Event Handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

     <span data-ttu-id="6e4af-136">A continuación muestra el XAML de MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="6e4af-136">The following shows the XAML for MainWindow.xaml.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6e4af-137">Si utiliza Visual Basic, en la primera línea de MainWindow.xaml, reemplace `x:Class="DataGridSQLExample.MainWindow"` con `x:Class="MainWindow"`.</span><span class="sxs-lookup"><span data-stu-id="6e4af-137">If you are using Visual Basic, in the first line of MainWindow.xaml, replace `x:Class="DataGridSQLExample.MainWindow"` with `x:Class="MainWindow"`.</span></span>

     [!code-xaml[DataGrid_SQL_EF_Walkthrough#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#1)]

6. <span data-ttu-id="6e4af-138">Abra el archivo de código subyacente (MainWindow.xaml.vb o MainWindow.xaml.cs) para el <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="6e4af-138">Open the code-behind file (MainWindow.xaml.vb or MainWindow.xaml.cs) for the <xref:System.Windows.Window>.</span></span>

7. <span data-ttu-id="6e4af-139">Agregue el código siguiente para recuperar solo los valores específicos de las tablas combinadas y establecer el <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> propiedad de la <xref:System.Windows.Controls.DataGrid> a los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="6e4af-139">Add the following code to retrieve only specific values from the joined tables and set the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.DataGrid> to the results of the query.</span></span>

     [!code-csharp[DataGrid_SQL_EF_Walkthrough#2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml.cs#2)]
     [!code-vb[DataGrid_SQL_EF_Walkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/VB/MainWindow.xaml.vb#2)]

8. <span data-ttu-id="6e4af-140">Ejecute el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="6e4af-140">Run the example.</span></span>

     <span data-ttu-id="6e4af-141">Debería ver un <xref:System.Windows.Controls.DataGrid> que muestra los datos.</span><span class="sxs-lookup"><span data-stu-id="6e4af-141">You should see a <xref:System.Windows.Controls.DataGrid> that displays data.</span></span>

     <span data-ttu-id="6e4af-142">![DataGrid con datos de la base de datos SQL](./media/datagrid-sql-ef-step7.png "DataGrid_SQL_EF_Step7")</span><span class="sxs-lookup"><span data-stu-id="6e4af-142">![DataGrid with data from SQL database](./media/datagrid-sql-ef-step7.png "DataGrid_SQL_EF_Step7")</span></span>

## <a name="see-also"></a><span data-ttu-id="6e4af-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e4af-143">See also</span></span>

- <xref:System.Windows.Controls.DataGrid>
- [<span data-ttu-id="6e4af-144">¿Cómo lo hago?: ¿Introducción a Entity Framework en aplicaciones WPF?</span><span class="sxs-lookup"><span data-stu-id="6e4af-144">How Do I: Get Started with Entity Framework in WPF Applications?</span></span>](https://go.microsoft.com/fwlink/?LinkId=159868)