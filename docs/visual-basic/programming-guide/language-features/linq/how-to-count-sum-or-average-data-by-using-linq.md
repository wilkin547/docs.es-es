---
title: 'Cómo: recuento, suma o promedio de datos mediante LINQ'
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
ms.openlocfilehash: 7e105c75653f979f53567ef49f1f4cdeafaa4d0f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345008"
---
# <a name="how-to-count-sum-or-average-data-by-using-linq-visual-basic"></a><span data-ttu-id="14201-102">Cómo: Hacer el recuento, la suma o el promedio de datos usando LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="14201-102">How to: Count, Sum, or Average Data by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="14201-103">Language-Integrated Query (LINQ) facilita el acceso a la información de base de datos y la ejecución de consultas.</span><span class="sxs-lookup"><span data-stu-id="14201-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="14201-104">En el ejemplo siguiente se muestra cómo crear una nueva aplicación que realiza consultas en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="14201-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span> <span data-ttu-id="14201-105">El ejemplo cuenta, suma y calcula el promedio de los resultados mediante el uso de las cláusulas `Aggregate` y `Group By`.</span><span class="sxs-lookup"><span data-stu-id="14201-105">The sample counts, sums, and averages the results by using the `Aggregate` and `Group By` clauses.</span></span> <span data-ttu-id="14201-106">Para obtener más información, vea [cláusula Aggregate](../../../../visual-basic/language-reference/queries/aggregate-clause.md) y [cláusula Group by](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="14201-106">For more information, see [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
 <span data-ttu-id="14201-107">En los ejemplos de este tema se utiliza la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="14201-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="14201-108">Si no dispone de esta base de datos en el equipo de desarrollo, puede descargarla del Centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="14201-108">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="14201-109">Para obtener instrucciones, consulte [Descargar bases de datos de ejemplo](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="14201-109">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="14201-110">Para crear una conexión a una base de datos</span><span class="sxs-lookup"><span data-stu-id="14201-110">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="14201-111">En Visual Studio, Abra **Explorador de servidores**/**Explorador de bases de datos** haciendo clic en **Explorador de servidores**/**Explorador de bases de datos** en el menú **Ver** .</span><span class="sxs-lookup"><span data-stu-id="14201-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="14201-112">Haga clic con el botón secundario en **conexiones de datos** en **Explorador de servidores**/**Explorador de bases de datos** y, a continuación, haga clic en **Agregar conexión**.</span><span class="sxs-lookup"><span data-stu-id="14201-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="14201-113">Especifique una conexión válida a la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="14201-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="14201-114">Para agregar un proyecto que contiene un archivo LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="14201-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="14201-115">En el menú **Archivo** de Visual Studio, apunte a **Nuevo** y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="14201-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="14201-116">Seleccione Visual Basic **aplicación de Windows Forms** como el tipo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="14201-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="14201-117">En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="14201-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="14201-118">Seleccione la plantilla de elementos **LINQ to SQL clases** .</span><span class="sxs-lookup"><span data-stu-id="14201-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="14201-119">Asigne al archivo el nombre `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="14201-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="14201-120">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="14201-120">Click **Add**.</span></span> <span data-ttu-id="14201-121">El Object Relational Designer (Object Relational Designer) se abre para el archivo Northwind. dbml.</span><span class="sxs-lookup"><span data-stu-id="14201-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="14201-122">Para agregar tablas que se van a consultar en Object Relational Designer</span><span class="sxs-lookup"><span data-stu-id="14201-122">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="14201-123">En **Explorador de servidores**/**Explorador de bases de datos**, expanda la conexión a la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="14201-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="14201-124">Expanda la carpeta **tablas** .</span><span class="sxs-lookup"><span data-stu-id="14201-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="14201-125">Si ha cerrado el Object Relational Designer, puede volver a abrirlo si hace doble clic en el archivo Northwind. dbml que agregó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="14201-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="14201-126">Haga clic en la tabla Customers y arrástrela hasta el panel izquierdo del diseñador.</span><span class="sxs-lookup"><span data-stu-id="14201-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="14201-127">Haga clic en la tabla Orders y arrástrela hasta el panel izquierdo del diseñador.</span><span class="sxs-lookup"><span data-stu-id="14201-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="14201-128">El diseñador crea nuevos objetos `Customer` y `Order` para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="14201-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="14201-129">Observe que el diseñador detecta automáticamente las relaciones entre las tablas y crea las propiedades secundarias de los objetos relacionados.</span><span class="sxs-lookup"><span data-stu-id="14201-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="14201-130">Por ejemplo, IntelliSense mostrará que el objeto `Customer` tiene una propiedad `Orders` para todos los pedidos relacionados con ese cliente.</span><span class="sxs-lookup"><span data-stu-id="14201-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3. <span data-ttu-id="14201-131">Guarde los cambios y cierre el diseñador.</span><span class="sxs-lookup"><span data-stu-id="14201-131">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="14201-132">Guarde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="14201-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="14201-133">Para agregar código para consultar la base de datos y mostrar los resultados</span><span class="sxs-lookup"><span data-stu-id="14201-133">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="14201-134">En el **cuadro de herramientas**, arrastre un control <xref:System.Windows.Forms.DataGridView> al formulario predeterminado de Windows para el proyecto, Form1.</span><span class="sxs-lookup"><span data-stu-id="14201-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="14201-135">Haga doble clic en Form1 para agregar código al evento `Load` del formulario.</span><span class="sxs-lookup"><span data-stu-id="14201-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3. <span data-ttu-id="14201-136">Al agregar tablas a Object Relational Designer, el diseñador agregó un <xref:System.Data.Linq.DataContext> objeto para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="14201-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="14201-137">Este objeto contiene el código que debe tener para obtener acceso a esas tablas y para obtener acceso a objetos y colecciones individuales para cada tabla.</span><span class="sxs-lookup"><span data-stu-id="14201-137">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="14201-138">El nombre del objeto <xref:System.Data.Linq.DataContext> del proyecto se basa en el nombre del archivo. dbml.</span><span class="sxs-lookup"><span data-stu-id="14201-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="14201-139">Para este proyecto, el objeto de <xref:System.Data.Linq.DataContext> se denomina `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="14201-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="14201-140">Puede crear una instancia de la <xref:System.Data.Linq.DataContext> en el código y consultar las tablas especificadas por Object Relational Designer.</span><span class="sxs-lookup"><span data-stu-id="14201-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="14201-141">Agregue el código siguiente al evento `Load` para consultar las tablas que se exponen como propiedades de los <xref:System.Data.Linq.DataContext> y el recuento, la suma y el promedio de los resultados.</span><span class="sxs-lookup"><span data-stu-id="14201-141">Add the following code to the `Load` event to query the tables that are exposed as properties of your <xref:System.Data.Linq.DataContext> and count, sum, and average the results.</span></span> <span data-ttu-id="14201-142">En el ejemplo se usa la cláusula `Aggregate` para consultar un solo resultado y la cláusula `Group By` para mostrar un promedio de los resultados agrupados.</span><span class="sxs-lookup"><span data-stu-id="14201-142">The sample uses the `Aggregate` clause to query for a single result, and the `Group By` clause to show an average for grouped results.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form6.vb#13)]  
  
4. <span data-ttu-id="14201-143">Presione F5 para ejecutar el proyecto y ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="14201-143">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14201-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="14201-144">See also</span></span>

- [<span data-ttu-id="14201-145">LINQ</span><span class="sxs-lookup"><span data-stu-id="14201-145">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="14201-146">Consultas</span><span class="sxs-lookup"><span data-stu-id="14201-146">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="14201-147">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="14201-147">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="14201-148">Métodos DataContext (Object Relational Designer)</span><span class="sxs-lookup"><span data-stu-id="14201-148">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [<span data-ttu-id="14201-149">Aggregate (cláusula)</span><span class="sxs-lookup"><span data-stu-id="14201-149">Aggregate Clause</span></span>](../../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="14201-150">Group By (cláusula)</span><span class="sxs-lookup"><span data-stu-id="14201-150">Group By Clause</span></span>](../../../../visual-basic/language-reference/queries/group-by-clause.md)
