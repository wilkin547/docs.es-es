---
description: Más información sobre cómo filtrar los resultados de una consulta mediante LINQ (Visual Basic)
title: Procedimiento para filtrar los resultados de una consulta mediante LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- filtering [Visual Basic]
- filtering data [LINQ in Visual Basic]
- filtering [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], filtering results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
- filtering data [Visual Basic]
ms.assetid: ef103092-9bed-4134-97f4-2db696e83c12
ms.openlocfilehash: b3f861d9a7fb7b601606f190ad3bfbeef054cad7
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100422809"
---
# <a name="how-to-filter-query-results-by-using-linq-visual-basic"></a><span data-ttu-id="c5c20-103">Cómo: Filtrar los resultados de consultas usando LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5c20-103">How to: Filter Query Results by Using LINQ (Visual Basic)</span></span>

<span data-ttu-id="c5c20-104">Language-Integrated Query (LINQ) facilita el acceso a la información de base de datos y la ejecución de consultas.</span><span class="sxs-lookup"><span data-stu-id="c5c20-104">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>

<span data-ttu-id="c5c20-105">En el ejemplo siguiente se muestra cómo crear una nueva aplicación que realiza consultas en una base de datos de SQL Server y filtra los resultados por un valor determinado mediante la `Where` cláusula.</span><span class="sxs-lookup"><span data-stu-id="c5c20-105">The following example shows how to create a new application that performs queries against a SQL Server database and filters the results by a particular value by using the `Where` clause.</span></span> <span data-ttu-id="c5c20-106">Para obtener más información, vea [cláusula WHERE](../../../language-reference/queries/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="c5c20-106">For more information, see [Where Clause](../../../language-reference/queries/where-clause.md).</span></span>

<span data-ttu-id="c5c20-107">En los ejemplos de este tema se utiliza la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="c5c20-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="c5c20-108">Si no dispone de esta base de datos en el equipo de desarrollo, puede descargarla del Centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c5c20-108">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="c5c20-109">Para obtener instrucciones, consulte [Descargar bases de datos de ejemplo](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="c5c20-109">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="c5c20-110">Para crear una conexión a una base de datos</span><span class="sxs-lookup"><span data-stu-id="c5c20-110">To create a connection to a database</span></span>

1. <span data-ttu-id="c5c20-111">En Visual Studio, Abra **Explorador de servidores** / **Explorador de bases de datos** haciendo clic en **Explorador de servidores** / **Explorador de bases de datos** en el menú **Ver** .</span><span class="sxs-lookup"><span data-stu-id="c5c20-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>

2. <span data-ttu-id="c5c20-112">Haga clic con el botón secundario en **conexiones de datos** en **Explorador de servidores** / **Explorador de bases de datos** y, a continuación, haga clic en **Agregar conexión**.</span><span class="sxs-lookup"><span data-stu-id="c5c20-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>

3. <span data-ttu-id="c5c20-113">Especifique una conexión válida a la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="c5c20-113">Specify a valid connection to the Northwind sample database.</span></span>

## <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="c5c20-114">Para agregar un proyecto que contiene un archivo LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="c5c20-114">To add a project that contains a LINQ to SQL file</span></span>

1. <span data-ttu-id="c5c20-115">En el menú **Archivo** de Visual Studio, apunte a **Nuevo** y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="c5c20-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="c5c20-116">Seleccione Visual Basic **aplicación de Windows Forms** como el tipo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="c5c20-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>

2. <span data-ttu-id="c5c20-117">En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="c5c20-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="c5c20-118">Seleccione la plantilla de elementos **LINQ to SQL clases** .</span><span class="sxs-lookup"><span data-stu-id="c5c20-118">Select the **LINQ to SQL Classes** item template.</span></span>

3. <span data-ttu-id="c5c20-119">Ponga al archivo el nombre `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="c5c20-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="c5c20-120">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c5c20-120">Click **Add**.</span></span> <span data-ttu-id="c5c20-121">Se abre el Object Relational Designer (Object Relational Designer) para el archivo Northwind. dbml.</span><span class="sxs-lookup"><span data-stu-id="c5c20-121">The Object Relational Designer (O/R Designer) opens for the northwind.dbml file.</span></span>

## <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="c5c20-122">Para agregar tablas que se van a consultar en Object Relational Designer</span><span class="sxs-lookup"><span data-stu-id="c5c20-122">To add tables to query to the O/R Designer</span></span>

1. <span data-ttu-id="c5c20-123">En **Explorador de servidores** / **Explorador de bases de datos**, expanda la conexión a la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="c5c20-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="c5c20-124">Expanda la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="c5c20-124">Expand the **Tables** folder.</span></span>

     <span data-ttu-id="c5c20-125">Si ha cerrado el Object Relational Designer, puede volver a abrirlo si hace doble clic en el archivo Northwind. dbml que agregó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c5c20-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>

2. <span data-ttu-id="c5c20-126">Haga clic en la tabla Customers y arrástrela hasta el panel izquierdo del diseñador.</span><span class="sxs-lookup"><span data-stu-id="c5c20-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="c5c20-127">Haga clic en la tabla Orders y arrástrela hasta el panel izquierdo del diseñador.</span><span class="sxs-lookup"><span data-stu-id="c5c20-127">Click the Orders table and drag it to the left pane of the designer.</span></span>

     <span data-ttu-id="c5c20-128">El diseñador crea `Customer` objetos y nuevos `Order` para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="c5c20-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="c5c20-129">Observe que el diseñador detecta automáticamente las relaciones entre las tablas y crea las propiedades secundarias de los objetos relacionados.</span><span class="sxs-lookup"><span data-stu-id="c5c20-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="c5c20-130">Por ejemplo, IntelliSense mostrará que el `Customer` objeto tiene una `Orders` propiedad para todos los pedidos relacionados con ese cliente.</span><span class="sxs-lookup"><span data-stu-id="c5c20-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>

3. <span data-ttu-id="c5c20-131">Guarde los cambios y cierre el diseñador.</span><span class="sxs-lookup"><span data-stu-id="c5c20-131">Save your changes and close the designer.</span></span>

4. <span data-ttu-id="c5c20-132">Guarde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="c5c20-132">Save your project.</span></span>

## <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="c5c20-133">Para agregar código para consultar la base de datos y mostrar los resultados</span><span class="sxs-lookup"><span data-stu-id="c5c20-133">To add code to query the database and display the results</span></span>

1. <span data-ttu-id="c5c20-134">En el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.DataGridView> control al formulario de Windows Forms predeterminado para el proyecto, Form1.</span><span class="sxs-lookup"><span data-stu-id="c5c20-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>

2. <span data-ttu-id="c5c20-135">Haga doble clic en Form1 para agregar código al `Load` evento del formulario.</span><span class="sxs-lookup"><span data-stu-id="c5c20-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>

3. <span data-ttu-id="c5c20-136">Al agregar tablas a Object Relational Designer, el diseñador agregó un <xref:System.Data.Linq.DataContext> objeto para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="c5c20-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="c5c20-137">Este objeto contiene el código que debe tener para obtener acceso a esas tablas, además de colecciones y objetos individuales para cada tabla.</span><span class="sxs-lookup"><span data-stu-id="c5c20-137">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="c5c20-138">El <xref:System.Data.Linq.DataContext> nombre del objeto para el proyecto se basa en el nombre del archivo. dbml.</span><span class="sxs-lookup"><span data-stu-id="c5c20-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="c5c20-139">Para este proyecto, el <xref:System.Data.Linq.DataContext> objeto se denomina `northwindDataContext` .</span><span class="sxs-lookup"><span data-stu-id="c5c20-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>

    <span data-ttu-id="c5c20-140">Puede crear una instancia de en el <xref:System.Data.Linq.DataContext> código y consultar las tablas especificadas por Object Relational Designer.</span><span class="sxs-lookup"><span data-stu-id="c5c20-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>

    <span data-ttu-id="c5c20-141">Agregue el código siguiente al `Load` evento para consultar las tablas que se exponen como propiedades de su contexto de datos.</span><span class="sxs-lookup"><span data-stu-id="c5c20-141">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="c5c20-142">La consulta filtra los resultados y devuelve solo los clientes que se encuentran en `London` .</span><span class="sxs-lookup"><span data-stu-id="c5c20-142">The query filters the results and returns only customers that are located in `London`.</span></span>

    [!code-vb[VbLINQToSQLHowTos#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form5.vb#11)]

4. <span data-ttu-id="c5c20-143">Presione F5 para ejecutar el proyecto y ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="c5c20-143">Press F5 to run your project and view the results.</span></span>

5. <span data-ttu-id="c5c20-144">A continuación se muestran otros filtros que puede probar.</span><span class="sxs-lookup"><span data-stu-id="c5c20-144">Following are some other filters that you can try.</span></span>

    [!code-vb[VbLINQToSQLHowTos#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form5.vb#12)]

## <a name="see-also"></a><span data-ttu-id="c5c20-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5c20-145">See also</span></span>

- [<span data-ttu-id="c5c20-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="c5c20-146">LINQ</span></span>](index.md)
- [<span data-ttu-id="c5c20-147">Consultas</span><span class="sxs-lookup"><span data-stu-id="c5c20-147">Queries</span></span>](../../../language-reference/queries/index.md)
- [<span data-ttu-id="c5c20-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="c5c20-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="c5c20-149">DataContext (Métodos) (Object Relational Designer)</span><span class="sxs-lookup"><span data-stu-id="c5c20-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
