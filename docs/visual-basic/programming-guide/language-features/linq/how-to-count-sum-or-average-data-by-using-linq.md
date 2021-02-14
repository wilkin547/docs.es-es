---
description: 'Más información acerca de cómo: recuento, suma o promedio de datos mediante LINQ (Visual Basic)'
title: Procedimiento para hacer el recuento, la suma o el promedio de datos mediante LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- average operator [LINQ in Visual Basic]
- aggregate operator [LINQ in Visual Basic]
- aggregate queries
- queries [LINQ in Visual Basic], sum results
- Aggregate clause [Visual Basic]
- sum operator [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], aggregate queries
- queries [LINQ in Visual Basic], counting results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
- count operator [LINQ in Visual Basic]
ms.assetid: 51ca1f59-7770-4884-8b76-113002e54fc0
ms.openlocfilehash: 1759a2f990c2e61a862d032f2a09f29f65a05103
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100422808"
---
# <a name="how-to-count-sum-or-average-data-by-using-linq-visual-basic"></a><span data-ttu-id="fae65-103">Cómo: Hacer el recuento, la suma o el promedio de datos usando LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fae65-103">How to: Count, Sum, or Average Data by Using LINQ (Visual Basic)</span></span>

<span data-ttu-id="fae65-104">Language-Integrated Query (LINQ) facilita el acceso a la información de base de datos y la ejecución de consultas.</span><span class="sxs-lookup"><span data-stu-id="fae65-104">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="fae65-105">En el ejemplo siguiente se muestra cómo crear una nueva aplicación que realiza consultas en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fae65-105">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span> <span data-ttu-id="fae65-106">El ejemplo cuenta, suma y calcula el promedio de los resultados mediante las `Aggregate` `Group By` cláusulas y.</span><span class="sxs-lookup"><span data-stu-id="fae65-106">The sample counts, sums, and averages the results by using the `Aggregate` and `Group By` clauses.</span></span> <span data-ttu-id="fae65-107">Para obtener más información, vea [cláusula Aggregate](../../../language-reference/queries/aggregate-clause.md) y [cláusula Group by](../../../language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="fae65-107">For more information, see [Aggregate Clause](../../../language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../language-reference/queries/group-by-clause.md).</span></span>  
  
 <span data-ttu-id="fae65-108">En los ejemplos de este tema se utiliza la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="fae65-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="fae65-109">Si no dispone de esta base de datos en el equipo de desarrollo, puede descargarla del Centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fae65-109">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="fae65-110">Para obtener instrucciones, consulte [Descargar bases de datos de ejemplo](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="fae65-110">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="fae65-111">Para crear una conexión a una base de datos</span><span class="sxs-lookup"><span data-stu-id="fae65-111">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="fae65-112">En Visual Studio, Abra **Explorador de servidores** / **Explorador de bases de datos** haciendo clic en **Explorador de servidores** / **Explorador de bases de datos** en el menú **Ver** .</span><span class="sxs-lookup"><span data-stu-id="fae65-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="fae65-113">Haga clic con el botón secundario en **conexiones de datos** en **Explorador de servidores** / **Explorador de bases de datos** y, a continuación, haga clic en **Agregar conexión**.</span><span class="sxs-lookup"><span data-stu-id="fae65-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="fae65-114">Especifique una conexión válida a la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="fae65-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="fae65-115">Para agregar un proyecto que contiene un archivo LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="fae65-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="fae65-116">En el menú **Archivo** de Visual Studio, apunte a **Nuevo** y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="fae65-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="fae65-117">Seleccione Visual Basic **aplicación de Windows Forms** como el tipo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="fae65-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="fae65-118">En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="fae65-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="fae65-119">Seleccione la plantilla de elementos **LINQ to SQL clases** .</span><span class="sxs-lookup"><span data-stu-id="fae65-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="fae65-120">Ponga al archivo el nombre `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="fae65-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="fae65-121">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="fae65-121">Click **Add**.</span></span> <span data-ttu-id="fae65-122">El Object Relational Designer (Object Relational Designer) se abre para el archivo Northwind. dbml.</span><span class="sxs-lookup"><span data-stu-id="fae65-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="fae65-123">Para agregar tablas que se van a consultar en Object Relational Designer</span><span class="sxs-lookup"><span data-stu-id="fae65-123">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="fae65-124">En **Explorador de servidores** / **Explorador de bases de datos**, expanda la conexión a la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="fae65-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="fae65-125">Expanda la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="fae65-125">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="fae65-126">Si ha cerrado el Object Relational Designer, puede volver a abrirlo si hace doble clic en el archivo Northwind. dbml que agregó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="fae65-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="fae65-127">Haga clic en la tabla Customers y arrástrela hasta el panel izquierdo del diseñador.</span><span class="sxs-lookup"><span data-stu-id="fae65-127">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="fae65-128">Haga clic en la tabla Orders y arrástrela hasta el panel izquierdo del diseñador.</span><span class="sxs-lookup"><span data-stu-id="fae65-128">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="fae65-129">El diseñador crea `Customer` objetos y nuevos `Order` para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="fae65-129">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="fae65-130">Observe que el diseñador detecta automáticamente las relaciones entre las tablas y crea las propiedades secundarias de los objetos relacionados.</span><span class="sxs-lookup"><span data-stu-id="fae65-130">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="fae65-131">Por ejemplo, IntelliSense mostrará que el `Customer` objeto tiene una `Orders` propiedad para todos los pedidos relacionados con ese cliente.</span><span class="sxs-lookup"><span data-stu-id="fae65-131">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3. <span data-ttu-id="fae65-132">Guarde los cambios y cierre el diseñador.</span><span class="sxs-lookup"><span data-stu-id="fae65-132">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="fae65-133">Guarde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="fae65-133">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="fae65-134">Para agregar código para consultar la base de datos y mostrar los resultados</span><span class="sxs-lookup"><span data-stu-id="fae65-134">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="fae65-135">En el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.DataGridView> control al formulario de Windows Forms predeterminado para el proyecto, Form1.</span><span class="sxs-lookup"><span data-stu-id="fae65-135">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="fae65-136">Haga doble clic en Form1 para agregar código al `Load` evento del formulario.</span><span class="sxs-lookup"><span data-stu-id="fae65-136">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3. <span data-ttu-id="fae65-137">Al agregar tablas a Object Relational Designer, el diseñador agregó un <xref:System.Data.Linq.DataContext> objeto para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="fae65-137">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="fae65-138">Este objeto contiene el código que debe tener para obtener acceso a esas tablas y para obtener acceso a objetos y colecciones individuales para cada tabla.</span><span class="sxs-lookup"><span data-stu-id="fae65-138">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="fae65-139">El <xref:System.Data.Linq.DataContext> nombre del objeto para el proyecto se basa en el nombre del archivo. dbml.</span><span class="sxs-lookup"><span data-stu-id="fae65-139">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="fae65-140">Para este proyecto, el <xref:System.Data.Linq.DataContext> objeto se denomina `northwindDataContext` .</span><span class="sxs-lookup"><span data-stu-id="fae65-140">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="fae65-141">Puede crear una instancia de en el <xref:System.Data.Linq.DataContext> código y consultar las tablas especificadas por Object Relational Designer.</span><span class="sxs-lookup"><span data-stu-id="fae65-141">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="fae65-142">Agregue el código siguiente al `Load` evento para consultar las tablas que se exponen como propiedades de su <xref:System.Data.Linq.DataContext> cuenta y, sumar y calcular el promedio de los resultados.</span><span class="sxs-lookup"><span data-stu-id="fae65-142">Add the following code to the `Load` event to query the tables that are exposed as properties of your <xref:System.Data.Linq.DataContext> and count, sum, and average the results.</span></span> <span data-ttu-id="fae65-143">En el ejemplo se usa la `Aggregate` cláusula para consultar un solo resultado y la `Group By` cláusula para mostrar un promedio de los resultados agrupados.</span><span class="sxs-lookup"><span data-stu-id="fae65-143">The sample uses the `Aggregate` clause to query for a single result, and the `Group By` clause to show an average for grouped results.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form6.vb#13)]  
  
4. <span data-ttu-id="fae65-144">Presione F5 para ejecutar el proyecto y ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="fae65-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fae65-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="fae65-145">See also</span></span>

- [<span data-ttu-id="fae65-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="fae65-146">LINQ</span></span>](index.md)
- [<span data-ttu-id="fae65-147">Consultas</span><span class="sxs-lookup"><span data-stu-id="fae65-147">Queries</span></span>](../../../language-reference/queries/index.md)
- [<span data-ttu-id="fae65-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="fae65-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="fae65-149">DataContext (Métodos) (Object Relational Designer)</span><span class="sxs-lookup"><span data-stu-id="fae65-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [<span data-ttu-id="fae65-150">Aggregate Clause</span><span class="sxs-lookup"><span data-stu-id="fae65-150">Aggregate Clause</span></span>](../../../language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="fae65-151">Group by (cláusula)</span><span class="sxs-lookup"><span data-stu-id="fae65-151">Group By Clause</span></span>](../../../language-reference/queries/group-by-clause.md)
