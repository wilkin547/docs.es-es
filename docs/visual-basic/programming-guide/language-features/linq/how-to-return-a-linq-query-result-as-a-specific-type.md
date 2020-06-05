---
title: Procedimiento para devolver el resultado de una consulta con LINQ como tipo específico
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], specific type returned
- projection [LINQ in Visual Basic]
- anonymous types [Visual Basic]
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 621bb10a-e5d7-44fb-a025-317964b19d92
ms.openlocfilehash: c8ed792bf3ffefd903d60522f621958e44546d32
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404957"
---
# <a name="how-to-return-a-linq-query-result-as-a-specific-type-visual-basic"></a><span data-ttu-id="fb110-102">Cómo: Devolver el resultado de una consulta con LINQ como tipo específico (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb110-102">How to: Return a LINQ Query Result as a Specific Type (Visual Basic)</span></span>
<span data-ttu-id="fb110-103">Language-Integrated Query (LINQ) facilita el acceso a la información de base de datos y la ejecución de consultas.</span><span class="sxs-lookup"><span data-stu-id="fb110-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span> <span data-ttu-id="fb110-104">De forma predeterminada, las consultas LINQ devuelven una lista de objetos como un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="fb110-104">By default, LINQ queries return a list of objects as an anonymous type.</span></span> <span data-ttu-id="fb110-105">También puede especificar que una consulta devuelva una lista de un tipo específico mediante la `Select` cláusula.</span><span class="sxs-lookup"><span data-stu-id="fb110-105">You can also specify that a query return a list of a specific type by using the `Select` clause.</span></span>  
  
 <span data-ttu-id="fb110-106">En el ejemplo siguiente se muestra cómo crear una nueva aplicación que realiza consultas en una base de datos de SQL Server y proyecta los resultados como un tipo con nombre específico.</span><span class="sxs-lookup"><span data-stu-id="fb110-106">The following example shows how to create a new application that performs queries against a SQL Server database and projects the results as a specific named type.</span></span> <span data-ttu-id="fb110-107">Para obtener más información, vea [tipos anónimos](../objects-and-classes/anonymous-types.md) y [cláusula SELECT](../../../language-reference/queries/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="fb110-107">For more information, see [Anonymous Types](../objects-and-classes/anonymous-types.md) and [Select Clause](../../../language-reference/queries/select-clause.md).</span></span>  
  
 <span data-ttu-id="fb110-108">En los ejemplos de este tema se utiliza la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="fb110-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="fb110-109">Si no dispone de esta base de datos en el equipo de desarrollo, puede descargarla del Centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fb110-109">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="fb110-110">Para obtener instrucciones, consulte [Descargar bases de datos de ejemplo](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="fb110-110">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="fb110-111">Para crear una conexión a una base de datos</span><span class="sxs-lookup"><span data-stu-id="fb110-111">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="fb110-112">En Visual Studio, Abra **Explorador de servidores** / **Explorador de bases de datos** haciendo clic en **Explorador de servidores** / **Explorador de bases de datos** en el menú **Ver** .</span><span class="sxs-lookup"><span data-stu-id="fb110-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="fb110-113">Haga clic con el botón secundario en **conexiones de datos** en **Explorador de servidores** / **Explorador de bases de datos** y, a continuación, haga clic en **Agregar conexión**.</span><span class="sxs-lookup"><span data-stu-id="fb110-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="fb110-114">Especifique una conexión válida a la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="fb110-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="fb110-115">Para agregar un proyecto que contiene un archivo LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="fb110-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="fb110-116">En Visual Studio, en el menú **archivo** , seleccione **nuevo** y haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="fb110-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="fb110-117">Seleccione Visual Basic **aplicación de Windows Forms** como el tipo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="fb110-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="fb110-118">En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="fb110-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="fb110-119">Seleccione la plantilla de elementos **LINQ to SQL clases** .</span><span class="sxs-lookup"><span data-stu-id="fb110-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="fb110-120">Ponga al archivo el nombre `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="fb110-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="fb110-121">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="fb110-121">Click **Add**.</span></span> <span data-ttu-id="fb110-122">El Object Relational Designer (Object Relational Designer) se abre para el archivo Northwind. dbml.</span><span class="sxs-lookup"><span data-stu-id="fb110-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="fb110-123">Para agregar tablas que se van a consultar en Object Relational Designer</span><span class="sxs-lookup"><span data-stu-id="fb110-123">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="fb110-124">En **Explorador de servidores** / **Explorador de bases de datos**, expanda la conexión a la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="fb110-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="fb110-125">Expanda la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="fb110-125">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="fb110-126">Si ha cerrado el Object Relational Designer, puede volver a abrirlo si hace doble clic en el archivo Northwind. dbml que agregó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="fb110-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="fb110-127">Haga clic en la tabla Customers y arrástrela hasta el panel izquierdo del diseñador.</span><span class="sxs-lookup"><span data-stu-id="fb110-127">Click the Customers table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="fb110-128">El diseñador crea un nuevo `Customer` objeto para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="fb110-128">The designer creates a new `Customer` object for your project.</span></span> <span data-ttu-id="fb110-129">Puede proyectar el resultado de una consulta como el `Customer` tipo o como un tipo que cree.</span><span class="sxs-lookup"><span data-stu-id="fb110-129">You can project a query result as the `Customer` type or as a type that you create.</span></span> <span data-ttu-id="fb110-130">En este ejemplo se creará un nuevo tipo en un procedimiento posterior y se proyectará un resultado de consulta como ese tipo.</span><span class="sxs-lookup"><span data-stu-id="fb110-130">This sample will create a new type in a later procedure and project a query result as that type.</span></span>  
  
3. <span data-ttu-id="fb110-131">Guarde los cambios y cierre el diseñador.</span><span class="sxs-lookup"><span data-stu-id="fb110-131">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="fb110-132">Guarde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="fb110-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="fb110-133">Para agregar código para consultar la base de datos y mostrar los resultados</span><span class="sxs-lookup"><span data-stu-id="fb110-133">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="fb110-134">En el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.DataGridView> control al formulario de Windows Forms predeterminado para el proyecto, Form1.</span><span class="sxs-lookup"><span data-stu-id="fb110-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="fb110-135">Haga doble clic en Form1 para modificar la clase Form1.</span><span class="sxs-lookup"><span data-stu-id="fb110-135">Double-click Form1 to modify the Form1 class.</span></span>  
  
3. <span data-ttu-id="fb110-136">Después de la `End Class` instrucción de la clase Form1, agregue el código siguiente para crear un `CustomerInfo` tipo que contenga los resultados de la consulta para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fb110-136">After the `End Class` statement of the Form1 class, add the following code to create a `CustomerInfo` type to hold the query results for this sample.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form8.vb#16)]  
  
4. <span data-ttu-id="fb110-137">Al agregar tablas a Object Relational Designer, el diseñador agregó un <xref:System.Data.Linq.DataContext> objeto al proyecto.</span><span class="sxs-lookup"><span data-stu-id="fb110-137">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="fb110-138">Este objeto contiene el código que debe tener para obtener acceso a esas tablas y para obtener acceso a objetos y colecciones individuales para cada tabla.</span><span class="sxs-lookup"><span data-stu-id="fb110-138">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="fb110-139">El <xref:System.Data.Linq.DataContext> nombre del objeto para el proyecto se basa en el nombre del archivo. dbml.</span><span class="sxs-lookup"><span data-stu-id="fb110-139">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="fb110-140">Para este proyecto, el <xref:System.Data.Linq.DataContext> objeto se denomina `northwindDataContext` .</span><span class="sxs-lookup"><span data-stu-id="fb110-140">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="fb110-141">Puede crear una instancia de en el <xref:System.Data.Linq.DataContext> código y consultar las tablas especificadas por Object Relational Designer.</span><span class="sxs-lookup"><span data-stu-id="fb110-141">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="fb110-142">En el `Load` caso de la clase Form1, agregue el siguiente código para consultar las tablas que se exponen como propiedades de su contexto de datos.</span><span class="sxs-lookup"><span data-stu-id="fb110-142">In the `Load` event of the Form1 class, add the following code to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="fb110-143">La `Select` cláusula de la consulta creará un nuevo `CustomerInfo` tipo en lugar de un tipo anónimo para cada elemento del resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="fb110-143">The `Select` clause of the query will create a new `CustomerInfo` type instead of an anonymous type for each item of the query result.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form8.vb#15)]  
  
5. <span data-ttu-id="fb110-144">Presione F5 para ejecutar el proyecto y ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="fb110-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb110-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fb110-145">See also</span></span>

- [<span data-ttu-id="fb110-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="fb110-146">LINQ</span></span>](index.md)
- [<span data-ttu-id="fb110-147">Consultas</span><span class="sxs-lookup"><span data-stu-id="fb110-147">Queries</span></span>](../../../language-reference/queries/index.md)
- [<span data-ttu-id="fb110-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="fb110-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="fb110-149">DataContext (métodos) (Object Relational Designer)</span><span class="sxs-lookup"><span data-stu-id="fb110-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
