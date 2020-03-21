---
title: Buscar los valores máximo y mínimo en el resultado de una consulta usando LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- max operator [LINQ in Visual Basic]
- aggregate operator [LINQ in Visual Basic]
- aggregate queries
- minimum values [LINQ in Visual Basic]
- min operator [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], minimum and maximum values
- Max property
- maximum values [LINQ in Visual Basic]
- Aggregate clause [Visual Basic]
- queries [LINQ in Visual Basic], aggregate queries
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 238b763b-7dcd-4b14-8050-b65500a4f71c
ms.openlocfilehash: ef5f218cdcc7275f616486110825ad0b9df11cc3
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112367"
---
# <a name="how-to-find-the-minimum-or-maximum-value-in-a-query-result-by-using-linq-visual-basic"></a><span data-ttu-id="6fef3-102">Cómo: Buscar los valores máximo y mínimo en el resultado de una consulta usando LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6fef3-102">How to: Find the Minimum or Maximum Value in a Query Result by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="6fef3-103">Language-Integrated Query (LINQ) facilita el acceso a la información de la base de datos y la ejecución de consultas.</span><span class="sxs-lookup"><span data-stu-id="6fef3-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="6fef3-104">En el ejemplo siguiente se muestra cómo crear una nueva aplicación que realiza consultas en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6fef3-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span> <span data-ttu-id="6fef3-105">El ejemplo determina los valores mínimo y máximo `Aggregate` `Group By` para los resultados mediante las cláusulas y.</span><span class="sxs-lookup"><span data-stu-id="6fef3-105">The sample determines the minimum and maximum values for the results by using the `Aggregate` and `Group By` clauses.</span></span> <span data-ttu-id="6fef3-106">Para obtener más información, consulte [Cláusula agregada](../../../../visual-basic/language-reference/queries/aggregate-clause.md) y Cláusula de [grupo](../../../../visual-basic/language-reference/queries/group-by-clause.md)por .</span><span class="sxs-lookup"><span data-stu-id="6fef3-106">For more information, see [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
 <span data-ttu-id="6fef3-107">Los ejemplos de este tema usan la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="6fef3-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="6fef3-108">Si no dispone de esta base de datos en el equipo de desarrollo, puede descargarla del Centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6fef3-108">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="6fef3-109">Para obtener instrucciones, consulte [Descarga de bases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)de datos de ejemplo .</span><span class="sxs-lookup"><span data-stu-id="6fef3-109">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="create-a-connection-to-a-database"></a><span data-ttu-id="6fef3-110">Crear una conexión a una base de datos</span><span class="sxs-lookup"><span data-stu-id="6fef3-110">Create a connection to a database</span></span>  
  
1. <span data-ttu-id="6fef3-111">En Visual Studio, abra el Explorador de**bases** de datos del **Explorador**/de servidores haciendo clic en Explorador de bases de datos del **Server Explorer**/**Explorador** de servidores en el menú **Ver.**</span><span class="sxs-lookup"><span data-stu-id="6fef3-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="6fef3-112">Haga clic con el botón secundario en **Conexiones** de datos en el**Explorador** de bases de datos del **Explorador**/de servidores y, a continuación, haga clic en **Agregar conexión**.</span><span class="sxs-lookup"><span data-stu-id="6fef3-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="6fef3-113">Especifique una conexión válida a la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="6fef3-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="6fef3-114">Para agregar un proyecto que contiene un archivo LINQ to SQLLINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="6fef3-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="6fef3-115">En Visual Studio, en **el** archivo menú, seleccione **nuevo** y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="6fef3-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="6fef3-116">Seleccione Aplicación de **formularios Windows Forms** de Visual Basic como tipo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="6fef3-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="6fef3-117">En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="6fef3-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="6fef3-118">Seleccione la plantilla de elemento **LINQ to SQL Classes.**</span><span class="sxs-lookup"><span data-stu-id="6fef3-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="6fef3-119">Asigne el nombre `northwind.dbml` al archivo.</span><span class="sxs-lookup"><span data-stu-id="6fef3-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="6fef3-120">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="6fef3-120">Click **Add**.</span></span> <span data-ttu-id="6fef3-121">Object Relational Designer (O/R Designer) se abre para el archivo northwind.dbml.</span><span class="sxs-lookup"><span data-stu-id="6fef3-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
## <a name="add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="6fef3-122">Agregar tablas para consultar al Diseñador de O/R</span><span class="sxs-lookup"><span data-stu-id="6fef3-122">Add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="6fef3-123">En el**Explorador**de bases de datos del **Explorador**/de servidores , expanda la conexión a la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="6fef3-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="6fef3-124">Expanda la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="6fef3-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="6fef3-125">Si ha cerrado el Diseñador de O/R, puede volver a abrirlo haciendo doble clic en el archivo northwind.dbml que agregó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6fef3-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="6fef3-126">Haga clic en la tabla Customers y arrástrela al panel izquierdo del diseñador.</span><span class="sxs-lookup"><span data-stu-id="6fef3-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="6fef3-127">Haga clic en la tabla Orders y arrástrela al panel izquierdo del diseñador.</span><span class="sxs-lookup"><span data-stu-id="6fef3-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="6fef3-128">El diseñador `Customer` crea `Order` nuevos y objetos para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="6fef3-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="6fef3-129">Observe que el diseñador detecta automáticamente las relaciones entre las tablas y crea propiedades secundarias para los objetos relacionados.</span><span class="sxs-lookup"><span data-stu-id="6fef3-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="6fef3-130">Por ejemplo, IntelliSense mostrará `Customer` que `Orders` el objeto tiene una propiedad para todos los pedidos relacionados con ese cliente.</span><span class="sxs-lookup"><span data-stu-id="6fef3-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3. <span data-ttu-id="6fef3-131">Guarde los cambios y cierre el diseñador.</span><span class="sxs-lookup"><span data-stu-id="6fef3-131">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="6fef3-132">Guarde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="6fef3-132">Save your project.</span></span>  
  
## <a name="add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="6fef3-133">Agregue código para consultar la base de datos y mostrar los resultados</span><span class="sxs-lookup"><span data-stu-id="6fef3-133">Add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="6fef3-134">En el **cuadro** <xref:System.Windows.Forms.DataGridView> de herramientas , arrastre un control al formulario Windows Forms predeterminado para el proyecto, Form1.</span><span class="sxs-lookup"><span data-stu-id="6fef3-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="6fef3-135">Haga doble clic en Form1 `Load` para agregar código al evento del formulario.</span><span class="sxs-lookup"><span data-stu-id="6fef3-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3. <span data-ttu-id="6fef3-136">Al agregar tablas al Diseñador de O/R, el diseñador agregó un <xref:System.Data.Linq.DataContext> objeto para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="6fef3-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="6fef3-137">Este objeto contiene el código que debe tener para tener acceso a esas tablas, además de objetos individuales y colecciones para cada tabla.</span><span class="sxs-lookup"><span data-stu-id="6fef3-137">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="6fef3-138">El <xref:System.Data.Linq.DataContext> objeto del proyecto se denomina en función del nombre del archivo .dbml.</span><span class="sxs-lookup"><span data-stu-id="6fef3-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="6fef3-139">Para este proyecto, <xref:System.Data.Linq.DataContext> el `northwindDataContext`objeto se denomina .</span><span class="sxs-lookup"><span data-stu-id="6fef3-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="6fef3-140">Puede crear una instancia <xref:System.Data.Linq.DataContext> del código y consultar las tablas especificadas por el Diseñador de O/R.</span><span class="sxs-lookup"><span data-stu-id="6fef3-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="6fef3-141">Agregue el código `Load` siguiente al evento.</span><span class="sxs-lookup"><span data-stu-id="6fef3-141">Add the following code to the `Load` event.</span></span> <span data-ttu-id="6fef3-142">Este código consulta las tablas que se exponen como propiedades del contexto de datos y determina los valores mínimo y máximo de los resultados.</span><span class="sxs-lookup"><span data-stu-id="6fef3-142">This code queries the tables that are exposed as properties of your data context and determines the minimum and maximum values for the results.</span></span> <span data-ttu-id="6fef3-143">El ejemplo `Aggregate` usa la cláusula para consultar `Group By` un único resultado y la cláusula para mostrar un promedio para los resultados agrupados.</span><span class="sxs-lookup"><span data-stu-id="6fef3-143">The sample uses the `Aggregate` clause to query for a single result, and the `Group By` clause to show an average for grouped results.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form7.vb#14)]  
  
4. <span data-ttu-id="6fef3-144">Presione **F5** para ejecutar el proyecto y ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="6fef3-144">Press **F5** to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fef3-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6fef3-145">See also</span></span>

- [<span data-ttu-id="6fef3-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="6fef3-146">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="6fef3-147">Consultas</span><span class="sxs-lookup"><span data-stu-id="6fef3-147">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="6fef3-148">LINQ a SQL</span><span class="sxs-lookup"><span data-stu-id="6fef3-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="6fef3-149">Métodos DataContext (Diseñador de O/R)</span><span class="sxs-lookup"><span data-stu-id="6fef3-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
