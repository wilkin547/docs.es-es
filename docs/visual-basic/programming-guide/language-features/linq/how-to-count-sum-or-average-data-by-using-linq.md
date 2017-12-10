---
title: "Cómo: Hacer el recuento, la suma o el promedio de datos usando LINQ (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a8c77804a9813d6127edcf4bd8371e0de2b36074
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2017
---
# <a name="how-to-count-sum-or-average-data-by-using-linq-visual-basic"></a><span data-ttu-id="e8e49-102">Cómo: Hacer el recuento, la suma o el promedio de datos usando LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e8e49-102">How to: Count, Sum, or Average Data by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="e8e49-103">Language-Integrated Query (LINQ) facilita el acceso a la información de la base de datos y ejecutar consultas.</span><span class="sxs-lookup"><span data-stu-id="e8e49-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="e8e49-104">En el ejemplo siguiente se muestra cómo crear una nueva aplicación que realiza consultas en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e8e49-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span> <span data-ttu-id="e8e49-105">El ejemplo de cuenta, suma y calcula el promedio de los resultados mediante el uso de la `Aggregate` y `Group By` cláusulas.</span><span class="sxs-lookup"><span data-stu-id="e8e49-105">The sample counts, sums, and averages the results by using the `Aggregate` and `Group By` clauses.</span></span> <span data-ttu-id="e8e49-106">Para obtener más información, consulte [Aggregate (cláusula)](../../../../visual-basic/language-reference/queries/aggregate-clause.md) y [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="e8e49-106">For more information, see [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
 <span data-ttu-id="e8e49-107">Los ejemplos de este tema usan la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="e8e49-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="e8e49-108">Si no tiene la base de datos de ejemplo Northwind en el equipo de desarrollo, puede descargarlo desde el [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) sitio Web.</span><span class="sxs-lookup"><span data-stu-id="e8e49-108">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="e8e49-109">Para obtener instrucciones, consulte [descargar bases de datos de ejemplo](../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="e8e49-109">For instructions, see [Downloading Sample Databases](../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="e8e49-110">Para crear una conexión a una base de datos</span><span class="sxs-lookup"><span data-stu-id="e8e49-110">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="e8e49-111">En Visual Studio, abra **Explorador de servidores**/**el Explorador de base de datos** haciendo clic en **Explorador de servidores**/**base de datos El Explorador de** en el **vista** menú.</span><span class="sxs-lookup"><span data-stu-id="e8e49-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="e8e49-112">Haga clic en **las conexiones de datos** en **Explorador de servidores**/**el Explorador de base de datos** y, a continuación, haga clic en **Agregar conexión**.</span><span class="sxs-lookup"><span data-stu-id="e8e49-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="e8e49-113">Especifique una conexión válida a la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="e8e49-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="e8e49-114">Para agregar un proyecto que contiene un archivo LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="e8e49-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="e8e49-115">En el menú **Archivo** de Visual Studio, apunte a **Nuevo** y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="e8e49-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="e8e49-116">Seleccione Visual Basic **aplicación de Windows Forms** como el tipo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="e8e49-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="e8e49-117">En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="e8e49-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="e8e49-118">Seleccione el **clases LINQ to SQL** plantilla de elemento.</span><span class="sxs-lookup"><span data-stu-id="e8e49-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="e8e49-119">Asigne al archivo el nombre `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="e8e49-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="e8e49-120">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="e8e49-120">Click **Add**.</span></span> <span data-ttu-id="e8e49-121">Se abre el Object Relational Designer (Object Relational Designer) para el archivo northwind.dbml.</span><span class="sxs-lookup"><span data-stu-id="e8e49-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="e8e49-122">Para agregar tablas a una consulta para el Object Relational Designer</span><span class="sxs-lookup"><span data-stu-id="e8e49-122">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="e8e49-123">En **Explorador de servidores**/**el Explorador de base de datos**, expanda la conexión a la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="e8e49-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="e8e49-124">Expanda el **tablas** carpeta.</span><span class="sxs-lookup"><span data-stu-id="e8e49-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="e8e49-125">Si ha cerrado el Object Relational Designer, puede volver a abrirlo haciendo doble clic en el archivo northwind.dbml que agregó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e8e49-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="e8e49-126">Haga clic en la tabla Customers y arrástrelo hasta el panel izquierdo del diseñador.</span><span class="sxs-lookup"><span data-stu-id="e8e49-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="e8e49-127">Haga clic en la tabla Orders y arrástrelo hasta el panel izquierdo del diseñador.</span><span class="sxs-lookup"><span data-stu-id="e8e49-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="e8e49-128">El diseñador crea nuevos `Customer` y `Order` objetos para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e8e49-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="e8e49-129">Observe que el diseñador automáticamente detecta las relaciones entre las tablas y crea a secundarios propiedades de objetos relacionados.</span><span class="sxs-lookup"><span data-stu-id="e8e49-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="e8e49-130">Por ejemplo, IntelliSense mostrará que el `Customer` objeto tiene una `Orders` propiedad para todos los pedidos relacionados con ese cliente.</span><span class="sxs-lookup"><span data-stu-id="e8e49-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="e8e49-131">Guarde los cambios y cierre el diseñador.</span><span class="sxs-lookup"><span data-stu-id="e8e49-131">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="e8e49-132">Guarde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e8e49-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="e8e49-133">Para agregar código para consultar la base de datos y mostrar los resultados</span><span class="sxs-lookup"><span data-stu-id="e8e49-133">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="e8e49-134">Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.DataGridView> control en el formulario Windows Forms predeterminado para el proyecto, Form1.</span><span class="sxs-lookup"><span data-stu-id="e8e49-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="e8e49-135">Haga doble clic en Form1 para agregar código a la `Load` evento del formulario.</span><span class="sxs-lookup"><span data-stu-id="e8e49-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="e8e49-136">Cuando agrega tablas a Object Relational Designer, el diseñador agrega un <xref:System.Data.Linq.DataContext> objeto para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e8e49-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="e8e49-137">Este objeto contiene el código que debe tener acceso a esas tablas y para tener acceso a objetos individuales y colecciones para cada tabla.</span><span class="sxs-lookup"><span data-stu-id="e8e49-137">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="e8e49-138">La <xref:System.Data.Linq.DataContext> objeto para el proyecto se denomina según el nombre del archivo dbml.</span><span class="sxs-lookup"><span data-stu-id="e8e49-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="e8e49-139">Para este proyecto, el <xref:System.Data.Linq.DataContext> se denomina objeto `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="e8e49-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="e8e49-140">Puede crear una instancia de la <xref:System.Data.Linq.DataContext> en el código y consultar las tablas especifican por el Object Relational Designer.</span><span class="sxs-lookup"><span data-stu-id="e8e49-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="e8e49-141">Agregue el código siguiente a la `Load` eventos para consultar las tablas que se exponen como propiedades de su <xref:System.Data.Linq.DataContext> y recuento, suma y promedio de los resultados.</span><span class="sxs-lookup"><span data-stu-id="e8e49-141">Add the following code to the `Load` event to query the tables that are exposed as properties of your <xref:System.Data.Linq.DataContext> and count, sum, and average the results.</span></span> <span data-ttu-id="e8e49-142">El ejemplo usa el `Aggregate` cláusula para consultar un único resultado y el `Group By` cláusula para mostrar un promedio para agrupar resultados.</span><span class="sxs-lookup"><span data-stu-id="e8e49-142">The sample uses the `Aggregate` clause to query for a single result, and the `Group By` clause to show an average for grouped results.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#13](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-count-sum-or-average-data-by-using-linq_1.vb)]  
  
4.  <span data-ttu-id="e8e49-143">Presione F5 para ejecutar el proyecto y ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="e8e49-143">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8e49-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8e49-144">See Also</span></span>  
 [<span data-ttu-id="e8e49-145">LINQ</span><span class="sxs-lookup"><span data-stu-id="e8e49-145">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="e8e49-146">Consultas</span><span class="sxs-lookup"><span data-stu-id="e8e49-146">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="e8e49-147">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="e8e49-147">LINQ to SQL</span></span>](../../../../../docs/framework/data/adonet/sql/linq/index.md)  
 [<span data-ttu-id="e8e49-148">Métodos de DataContext (Object Relational Designer)</span><span class="sxs-lookup"><span data-stu-id="e8e49-148">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)  
 [<span data-ttu-id="e8e49-149">Aggregate (cláusula)</span><span class="sxs-lookup"><span data-stu-id="e8e49-149">Aggregate Clause</span></span>](../../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [<span data-ttu-id="e8e49-150">Group By (cláusula)</span><span class="sxs-lookup"><span data-stu-id="e8e49-150">Group By Clause</span></span>](../../../../visual-basic/language-reference/queries/group-by-clause.md)
