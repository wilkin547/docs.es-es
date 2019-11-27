---
title: 'Cómo: Devolver el resultado de una consulta con LINQ como tipo específico'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], specific type returned
- projection [LINQ in Visual Basic]
- anonymous types [Visual Basic]
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 621bb10a-e5d7-44fb-a025-317964b19d92
ms.openlocfilehash: 1084743b0c50d381375b76a3116ed7c9e6f9d769
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354198"
---
# <a name="how-to-return-a-linq-query-result-as-a-specific-type-visual-basic"></a><span data-ttu-id="247a2-102">Cómo: Devolver el resultado de una consulta con LINQ como tipo específico (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="247a2-102">How to: Return a LINQ Query Result as a Specific Type (Visual Basic)</span></span>
<span data-ttu-id="247a2-103">Language-Integrated Query (LINQ) facilita el acceso a la información de base de datos y la ejecución de consultas.</span><span class="sxs-lookup"><span data-stu-id="247a2-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span> <span data-ttu-id="247a2-104">De forma predeterminada, las consultas LINQ devuelven una lista de objetos como un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="247a2-104">By default, LINQ queries return a list of objects as an anonymous type.</span></span> <span data-ttu-id="247a2-105">También puede especificar que una consulta devuelva una lista de un tipo específico mediante la cláusula `Select`.</span><span class="sxs-lookup"><span data-stu-id="247a2-105">You can also specify that a query return a list of a specific type by using the `Select` clause.</span></span>  
  
 <span data-ttu-id="247a2-106">En el ejemplo siguiente se muestra cómo crear una nueva aplicación que realiza consultas en una base de datos de SQL Server y proyecta los resultados como un tipo con nombre específico.</span><span class="sxs-lookup"><span data-stu-id="247a2-106">The following example shows how to create a new application that performs queries against a SQL Server database and projects the results as a specific named type.</span></span> <span data-ttu-id="247a2-107">Para obtener más información, vea [tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) y [cláusula SELECT](../../../../visual-basic/language-reference/queries/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="247a2-107">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) and [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
 <span data-ttu-id="247a2-108">En los ejemplos de este tema se utiliza la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="247a2-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="247a2-109">Si no dispone de esta base de datos en el equipo de desarrollo, puede descargarla del Centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="247a2-109">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="247a2-110">Para obtener instrucciones, consulte [Descargar bases de datos de ejemplo](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="247a2-110">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="247a2-111">Para crear una conexión a una base de datos</span><span class="sxs-lookup"><span data-stu-id="247a2-111">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="247a2-112">En Visual Studio, Abra **Explorador de servidores**/**Explorador de bases de datos** haciendo clic en **Explorador de servidores**/**Explorador de bases de datos** en el menú **Ver** .</span><span class="sxs-lookup"><span data-stu-id="247a2-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="247a2-113">Haga clic con el botón secundario en **conexiones de datos** en **Explorador de servidores**/**Explorador de bases de datos** y, a continuación, haga clic en **Agregar conexión**.</span><span class="sxs-lookup"><span data-stu-id="247a2-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="247a2-114">Especifique una conexión válida a la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="247a2-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="247a2-115">Para agregar un proyecto que contiene un archivo LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="247a2-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="247a2-116">En el menú **Archivo** de Visual Studio, apunte a **Nuevo** y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="247a2-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="247a2-117">Seleccione Visual Basic **aplicación de Windows Forms** como el tipo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="247a2-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="247a2-118">En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="247a2-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="247a2-119">Seleccione la plantilla de elementos **LINQ to SQL clases** .</span><span class="sxs-lookup"><span data-stu-id="247a2-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="247a2-120">Asigne al archivo el nombre `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="247a2-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="247a2-121">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="247a2-121">Click **Add**.</span></span> <span data-ttu-id="247a2-122">El Object Relational Designer (Object Relational Designer) se abre para el archivo Northwind. dbml.</span><span class="sxs-lookup"><span data-stu-id="247a2-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="247a2-123">Para agregar tablas que se van a consultar en Object Relational Designer</span><span class="sxs-lookup"><span data-stu-id="247a2-123">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="247a2-124">En **Explorador de servidores**/**Explorador de bases de datos**, expanda la conexión a la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="247a2-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="247a2-125">Expanda la carpeta **tablas** .</span><span class="sxs-lookup"><span data-stu-id="247a2-125">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="247a2-126">Si ha cerrado el Object Relational Designer, puede volver a abrirlo si hace doble clic en el archivo Northwind. dbml que agregó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="247a2-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="247a2-127">Haga clic en la tabla Customers y arrástrela hasta el panel izquierdo del diseñador.</span><span class="sxs-lookup"><span data-stu-id="247a2-127">Click the Customers table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="247a2-128">El diseñador crea un nuevo objeto `Customer` para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="247a2-128">The designer creates a new `Customer` object for your project.</span></span> <span data-ttu-id="247a2-129">Puede proyectar el resultado de una consulta como el tipo de `Customer` o como un tipo que cree.</span><span class="sxs-lookup"><span data-stu-id="247a2-129">You can project a query result as the `Customer` type or as a type that you create.</span></span> <span data-ttu-id="247a2-130">En este ejemplo se creará un nuevo tipo en un procedimiento posterior y se proyectará un resultado de consulta como ese tipo.</span><span class="sxs-lookup"><span data-stu-id="247a2-130">This sample will create a new type in a later procedure and project a query result as that type.</span></span>  
  
3. <span data-ttu-id="247a2-131">Guarde los cambios y cierre el diseñador.</span><span class="sxs-lookup"><span data-stu-id="247a2-131">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="247a2-132">Guarde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="247a2-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="247a2-133">Para agregar código para consultar la base de datos y mostrar los resultados</span><span class="sxs-lookup"><span data-stu-id="247a2-133">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="247a2-134">En el **cuadro de herramientas**, arrastre un control <xref:System.Windows.Forms.DataGridView> al formulario predeterminado de Windows para el proyecto, Form1.</span><span class="sxs-lookup"><span data-stu-id="247a2-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="247a2-135">Haga doble clic en Form1 para modificar la clase Form1.</span><span class="sxs-lookup"><span data-stu-id="247a2-135">Double-click Form1 to modify the Form1 class.</span></span>  
  
3. <span data-ttu-id="247a2-136">Después de la instrucción `End Class` de la clase Form1, agregue el código siguiente para crear un tipo de `CustomerInfo` que contenga los resultados de la consulta para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="247a2-136">After the `End Class` statement of the Form1 class, add the following code to create a `CustomerInfo` type to hold the query results for this sample.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form8.vb#16)]  
  
4. <span data-ttu-id="247a2-137">Al agregar tablas a Object Relational Designer, el diseñador agregó un objeto <xref:System.Data.Linq.DataContext> al proyecto.</span><span class="sxs-lookup"><span data-stu-id="247a2-137">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="247a2-138">Este objeto contiene el código que debe tener para obtener acceso a esas tablas y para obtener acceso a objetos y colecciones individuales para cada tabla.</span><span class="sxs-lookup"><span data-stu-id="247a2-138">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="247a2-139">El nombre del objeto <xref:System.Data.Linq.DataContext> del proyecto se basa en el nombre del archivo. dbml.</span><span class="sxs-lookup"><span data-stu-id="247a2-139">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="247a2-140">Para este proyecto, el objeto de <xref:System.Data.Linq.DataContext> se denomina `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="247a2-140">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="247a2-141">Puede crear una instancia de la <xref:System.Data.Linq.DataContext> en el código y consultar las tablas especificadas por Object Relational Designer.</span><span class="sxs-lookup"><span data-stu-id="247a2-141">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="247a2-142">En el evento `Load` de la clase Form1, agregue el siguiente código para consultar las tablas que se exponen como propiedades de su contexto de datos.</span><span class="sxs-lookup"><span data-stu-id="247a2-142">In the `Load` event of the Form1 class, add the following code to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="247a2-143">La cláusula `Select` de la consulta creará un nuevo tipo de `CustomerInfo` en lugar de un tipo anónimo para cada elemento del resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="247a2-143">The `Select` clause of the query will create a new `CustomerInfo` type instead of an anonymous type for each item of the query result.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form8.vb#15)]  
  
5. <span data-ttu-id="247a2-144">Presione F5 para ejecutar el proyecto y ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="247a2-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="247a2-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="247a2-145">See also</span></span>

- [<span data-ttu-id="247a2-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="247a2-146">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="247a2-147">Consultas</span><span class="sxs-lookup"><span data-stu-id="247a2-147">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="247a2-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="247a2-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="247a2-149">Métodos DataContext (Object Relational Designer)</span><span class="sxs-lookup"><span data-stu-id="247a2-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
