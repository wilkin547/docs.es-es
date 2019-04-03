---
title: Filtrar Devolver un resultado de consulta LINQ como un tipo específico (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], specific type returned
- projection [LINQ in Visual Basic]
- anonymous types [Visual Basic]
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 621bb10a-e5d7-44fb-a025-317964b19d92
ms.openlocfilehash: ba6479852f7a78fb26743a04fd08adea07c1ffff
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58835874"
---
# <a name="how-to-return-a-linq-query-result-as-a-specific-type-visual-basic"></a><span data-ttu-id="67d0d-102">Filtrar Devolver un resultado de consulta LINQ como un tipo específico (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67d0d-102">How to: Return a LINQ Query Result as a Specific Type (Visual Basic)</span></span>
<span data-ttu-id="67d0d-103">Language-Integrated Query (LINQ) facilita el acceso a la información de la base de datos y ejecutar consultas.</span><span class="sxs-lookup"><span data-stu-id="67d0d-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span> <span data-ttu-id="67d0d-104">De forma predeterminada, las consultas LINQ devuelven una lista de objetos como un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="67d0d-104">By default, LINQ queries return a list of objects as an anonymous type.</span></span> <span data-ttu-id="67d0d-105">También puede especificar que una consulta devuelva una lista de un tipo específico mediante el uso de la `Select` cláusula.</span><span class="sxs-lookup"><span data-stu-id="67d0d-105">You can also specify that a query return a list of a specific type by using the `Select` clause.</span></span>  
  
 <span data-ttu-id="67d0d-106">El ejemplo siguiente muestra cómo crear una nueva aplicación que realiza consultas en una base de datos de SQL Server y proyecta los resultados como un tipo con nombre específico.</span><span class="sxs-lookup"><span data-stu-id="67d0d-106">The following example shows how to create a new application that performs queries against a SQL Server database and projects the results as a specific named type.</span></span> <span data-ttu-id="67d0d-107">Para obtener más información, consulte [tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) y [cláusula Select](../../../../visual-basic/language-reference/queries/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="67d0d-107">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) and [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
 <span data-ttu-id="67d0d-108">Los ejemplos de este tema usan la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="67d0d-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="67d0d-109">Si no tiene esta base de datos en el equipo de desarrollo, puede descargarlo desde Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="67d0d-109">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="67d0d-110">Para obtener instrucciones, consulte [descargar bases de datos de ejemplo](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="67d0d-110">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="67d0d-111">Para crear una conexión a una base de datos</span><span class="sxs-lookup"><span data-stu-id="67d0d-111">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="67d0d-112">En Visual Studio, abra **Explorador de servidores**/**Database Explorer** haciendo **Explorador de servidores**/**base de datos Explorador** en el **vista** menú.</span><span class="sxs-lookup"><span data-stu-id="67d0d-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="67d0d-113">Haga clic en **conexiones de datos** en **Explorador de servidores**/**Database Explorer** y, a continuación, haga clic en **Agregar conexión**.</span><span class="sxs-lookup"><span data-stu-id="67d0d-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="67d0d-114">Especifique una conexión válida a la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="67d0d-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="67d0d-115">Para agregar un proyecto que contiene un archivo LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="67d0d-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="67d0d-116">En el menú **Archivo** de Visual Studio, apunte a **Nuevo** y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="67d0d-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="67d0d-117">Seleccione Visual Basic **aplicación de Windows Forms** como el tipo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="67d0d-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="67d0d-118">En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="67d0d-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="67d0d-119">Seleccione el **clases LINQ to SQL** plantilla de elemento.</span><span class="sxs-lookup"><span data-stu-id="67d0d-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="67d0d-120">Asigne al archivo el nombre `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="67d0d-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="67d0d-121">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="67d0d-121">Click **Add**.</span></span> <span data-ttu-id="67d0d-122">Se abre el Object Relational Designer (Object Relational Designer) para el archivo northwind.dbml.</span><span class="sxs-lookup"><span data-stu-id="67d0d-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="67d0d-123">Para agregar tablas a la consulta en el Object Relational Designer</span><span class="sxs-lookup"><span data-stu-id="67d0d-123">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="67d0d-124">En **Explorador de servidores**/**Database Explorer**, expanda la conexión a la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="67d0d-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="67d0d-125">Expanda el **tablas** carpeta.</span><span class="sxs-lookup"><span data-stu-id="67d0d-125">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="67d0d-126">Si ha cerrado el Object Relational Designer, puede volver a abrirlo haciendo doble clic en el archivo northwind.dbml que agregó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="67d0d-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="67d0d-127">Haga clic en la tabla Customers y arrástrelo hasta el panel izquierdo del diseñador.</span><span class="sxs-lookup"><span data-stu-id="67d0d-127">Click the Customers table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="67d0d-128">El diseñador crea un nuevo `Customer` objeto para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="67d0d-128">The designer creates a new `Customer` object for your project.</span></span> <span data-ttu-id="67d0d-129">Puede proyectar el resultado de una consulta como la `Customer` tipo o como un tipo que cree.</span><span class="sxs-lookup"><span data-stu-id="67d0d-129">You can project a query result as the `Customer` type or as a type that you create.</span></span> <span data-ttu-id="67d0d-130">En este ejemplo creará un nuevo tipo en un procedimiento posterior y el resultado de una consulta que ese tipo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="67d0d-130">This sample will create a new type in a later procedure and project a query result as that type.</span></span>  
  
3.  <span data-ttu-id="67d0d-131">Guarde los cambios y cierre el diseñador.</span><span class="sxs-lookup"><span data-stu-id="67d0d-131">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="67d0d-132">Guarde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="67d0d-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="67d0d-133">Para agregar código para consultar la base de datos y mostrar los resultados</span><span class="sxs-lookup"><span data-stu-id="67d0d-133">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="67d0d-134">Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.DataGridView> control en el formulario de Windows predeterminada para el proyecto, Form1.</span><span class="sxs-lookup"><span data-stu-id="67d0d-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="67d0d-135">Haga doble clic en Form1 para modificar la clase Form1.</span><span class="sxs-lookup"><span data-stu-id="67d0d-135">Double-click Form1 to modify the Form1 class.</span></span>  
  
3.  <span data-ttu-id="67d0d-136">Después de la `End Class` instrucción de la clase Form1, agregue el código siguiente para crear un `CustomerInfo` tipo para almacenar los resultados de consulta para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="67d0d-136">After the `End Class` statement of the Form1 class, add the following code to create a `CustomerInfo` type to hold the query results for this sample.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form8.vb#16)]  
  
4.  <span data-ttu-id="67d0d-137">Cuando agrega tablas a Object Relational Designer, el diseñador agrega un <xref:System.Data.Linq.DataContext> objeto a su proyecto.</span><span class="sxs-lookup"><span data-stu-id="67d0d-137">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="67d0d-138">Este objeto contiene el código que debe tener acceso a esas tablas y para tener acceso a objetos individuales y colecciones para cada tabla.</span><span class="sxs-lookup"><span data-stu-id="67d0d-138">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="67d0d-139">La <xref:System.Data.Linq.DataContext> objeto para el proyecto se denomina según el nombre del archivo dbml.</span><span class="sxs-lookup"><span data-stu-id="67d0d-139">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="67d0d-140">Para este proyecto, el <xref:System.Data.Linq.DataContext> se denomina objeto `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="67d0d-140">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="67d0d-141">Puede crear una instancia de la <xref:System.Data.Linq.DataContext> en el código y consultar las tablas especifican por el Object Relational Designer.</span><span class="sxs-lookup"><span data-stu-id="67d0d-141">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="67d0d-142">En el `Load` eventos de la clase Form1, agregue el código siguiente para consultar las tablas que se exponen como propiedades de su contexto de datos.</span><span class="sxs-lookup"><span data-stu-id="67d0d-142">In the `Load` event of the Form1 class, add the following code to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="67d0d-143">El `Select` creará una nueva cláusula de la consulta `CustomerInfo` tipo en lugar de un tipo anónimo para cada elemento de resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="67d0d-143">The `Select` clause of the query will create a new `CustomerInfo` type instead of an anonymous type for each item of the query result.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form8.vb#15)]  
  
5.  <span data-ttu-id="67d0d-144">Presione F5 para ejecutar el proyecto y ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="67d0d-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67d0d-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="67d0d-145">See also</span></span>

- [<span data-ttu-id="67d0d-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="67d0d-146">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="67d0d-147">Consultas</span><span class="sxs-lookup"><span data-stu-id="67d0d-147">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="67d0d-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="67d0d-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="67d0d-149">Métodos DataContext (Object Relational Designer)</span><span class="sxs-lookup"><span data-stu-id="67d0d-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
