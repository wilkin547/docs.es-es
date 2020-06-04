---
title: Procedimiento para ordenar los resultados de una consulta mediante LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- sorting query results, multiple columns
- sorting data [Visual Basic]
- sorting data [LINQ in Visual Basic]
- sorting query results [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], sorting results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 07a4584d-9fd8-4a1d-b7d9-ccf2efa5c84e
ms.openlocfilehash: c1bc6ab863f9de118d59e102d3d5d251d326f497
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404944"
---
# <a name="how-to-sort-query-results-by-using-linq-visual-basic"></a><span data-ttu-id="2e85c-102">Cómo: Ordenar los resultados de una consulta mediante LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2e85c-102">How to: Sort Query Results by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="2e85c-103">Language-Integrated Query (LINQ) facilita el acceso a la información de base de datos y la ejecución de consultas.</span><span class="sxs-lookup"><span data-stu-id="2e85c-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="2e85c-104">En el ejemplo siguiente se muestra cómo crear una nueva aplicación que realiza consultas en una base de datos de SQL Server y ordena los resultados por varios campos mediante la `Order By` cláusula.</span><span class="sxs-lookup"><span data-stu-id="2e85c-104">The following example shows how to create a new application that performs queries against a SQL Server database and sorts the results by multiple fields by using the `Order By` clause.</span></span> <span data-ttu-id="2e85c-105">El criterio de ordenación de cada campo puede ser en orden ascendente o descendente.</span><span class="sxs-lookup"><span data-stu-id="2e85c-105">The sort order for each field can be ascending order or descending order.</span></span> <span data-ttu-id="2e85c-106">Para obtener más información, vea [cláusula order by](../../../language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="2e85c-106">For more information, see [Order By Clause](../../../language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="2e85c-107">En los ejemplos de este tema se utiliza la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="2e85c-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="2e85c-108">Si no dispone de esta base de datos en el equipo de desarrollo, puede descargarla del Centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2e85c-108">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="2e85c-109">Para obtener instrucciones, consulte [Descargar bases de datos de ejemplo](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="2e85c-109">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="2e85c-110">Para crear una conexión a una base de datos</span><span class="sxs-lookup"><span data-stu-id="2e85c-110">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="2e85c-111">En Visual Studio, Abra **Explorador de servidores** / **Explorador de bases de datos** haciendo clic en **Explorador de servidores** / **Explorador de bases de datos** en el menú **Ver** .</span><span class="sxs-lookup"><span data-stu-id="2e85c-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="2e85c-112">Haga clic con el botón secundario en **conexiones de datos** en **Explorador de servidores** / **Explorador de bases de datos** y, a continuación, haga clic en **Agregar conexión**.</span><span class="sxs-lookup"><span data-stu-id="2e85c-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="2e85c-113">Especifique una conexión válida a la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="2e85c-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="2e85c-114">Para agregar un proyecto que contiene un archivo LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="2e85c-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="2e85c-115">En Visual Studio, en el menú **archivo** , seleccione **nuevo** y haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="2e85c-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="2e85c-116">Seleccione Visual Basic **aplicación de Windows Forms** como el tipo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="2e85c-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="2e85c-117">En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="2e85c-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="2e85c-118">Seleccione la plantilla de elementos **LINQ to SQL clases** .</span><span class="sxs-lookup"><span data-stu-id="2e85c-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="2e85c-119">Ponga al archivo el nombre `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="2e85c-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="2e85c-120">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2e85c-120">Click **Add**.</span></span> <span data-ttu-id="2e85c-121">El Object Relational Designer (Object Relational Designer) se abre para el archivo Northwind. dbml.</span><span class="sxs-lookup"><span data-stu-id="2e85c-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="2e85c-122">Para agregar tablas que se van a consultar en Object Relational Designer</span><span class="sxs-lookup"><span data-stu-id="2e85c-122">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="2e85c-123">En **Explorador de servidores** / **Explorador de bases de datos**, expanda la conexión a la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="2e85c-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="2e85c-124">Expanda la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="2e85c-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="2e85c-125">Si ha cerrado el Object Relational Designer, puede volver a abrirlo si hace doble clic en el archivo Northwind. dbml que agregó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="2e85c-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="2e85c-126">Haga clic en la tabla Customers y arrástrela hasta el panel izquierdo del diseñador.</span><span class="sxs-lookup"><span data-stu-id="2e85c-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="2e85c-127">Haga clic en la tabla Orders y arrástrela hasta el panel izquierdo del diseñador.</span><span class="sxs-lookup"><span data-stu-id="2e85c-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="2e85c-128">El diseñador crea `Customer` objetos y nuevos `Order` para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="2e85c-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="2e85c-129">Observe que el diseñador detecta automáticamente las relaciones entre las tablas y crea las propiedades secundarias de los objetos relacionados.</span><span class="sxs-lookup"><span data-stu-id="2e85c-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="2e85c-130">Por ejemplo, IntelliSense mostrará que el `Customer` objeto tiene una `Orders` propiedad para todos los pedidos relacionados con ese cliente.</span><span class="sxs-lookup"><span data-stu-id="2e85c-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3. <span data-ttu-id="2e85c-131">Guarde los cambios y cierre el diseñador.</span><span class="sxs-lookup"><span data-stu-id="2e85c-131">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="2e85c-132">Guarde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="2e85c-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="2e85c-133">Para agregar código para consultar la base de datos y mostrar los resultados</span><span class="sxs-lookup"><span data-stu-id="2e85c-133">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="2e85c-134">En el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.DataGridView> control al formulario de Windows Forms predeterminado para el proyecto, Form1.</span><span class="sxs-lookup"><span data-stu-id="2e85c-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="2e85c-135">Haga doble clic en Form1 para agregar código al `Load` evento del formulario.</span><span class="sxs-lookup"><span data-stu-id="2e85c-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3. <span data-ttu-id="2e85c-136">Al agregar tablas a Object Relational Designer, el diseñador agregó un <xref:System.Data.Linq.DataContext> objeto al proyecto.</span><span class="sxs-lookup"><span data-stu-id="2e85c-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="2e85c-137">Este objeto contiene el código que debe tener para obtener acceso a esas tablas y para obtener acceso a objetos y colecciones individuales para cada tabla.</span><span class="sxs-lookup"><span data-stu-id="2e85c-137">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="2e85c-138">El <xref:System.Data.Linq.DataContext> nombre del objeto para el proyecto se basa en el nombre del archivo. dbml.</span><span class="sxs-lookup"><span data-stu-id="2e85c-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="2e85c-139">Para este proyecto, el <xref:System.Data.Linq.DataContext> objeto se denomina `northwindDataContext` .</span><span class="sxs-lookup"><span data-stu-id="2e85c-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="2e85c-140">Puede crear una instancia de en el <xref:System.Data.Linq.DataContext> código y consultar las tablas especificadas por Object Relational Designer.</span><span class="sxs-lookup"><span data-stu-id="2e85c-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="2e85c-141">Agregue el código siguiente al `Load` evento para consultar las tablas que se exponen como propiedades del contexto de datos y ordenar los resultados.</span><span class="sxs-lookup"><span data-stu-id="2e85c-141">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context and sort the results.</span></span> <span data-ttu-id="2e85c-142">La consulta ordena los resultados por el número de pedidos de cliente, en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="2e85c-142">The query sorts the results by the number of customer orders, in descending order.</span></span> <span data-ttu-id="2e85c-143">Los clientes que tienen el mismo número de pedidos se ordenan por nombre de empresa en orden ascendente (el valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="2e85c-143">Customers that have the same number of orders are ordered by company name in ascending order (the default).</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form4.vb#10)]  
  
4. <span data-ttu-id="2e85c-144">Presione F5 para ejecutar el proyecto y ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="2e85c-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e85c-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2e85c-145">See also</span></span>

- [<span data-ttu-id="2e85c-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="2e85c-146">LINQ</span></span>](index.md)
- [<span data-ttu-id="2e85c-147">Consultas</span><span class="sxs-lookup"><span data-stu-id="2e85c-147">Queries</span></span>](../../../language-reference/queries/index.md)
- [<span data-ttu-id="2e85c-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="2e85c-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="2e85c-149">DataContext (métodos) (Object Relational Designer)</span><span class="sxs-lookup"><span data-stu-id="2e85c-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
