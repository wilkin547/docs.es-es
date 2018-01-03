---
title: "Cómo: Buscar los valores máximo y mínimo en el resultado de una consulta usando LINQ (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6a9555a86914f2352bc1a07bd92a839181355c9d
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-find-the-minimum-or-maximum-value-in-a-query-result-by-using-linq-visual-basic"></a><span data-ttu-id="76e5b-102">Cómo: Buscar los valores máximo y mínimo en el resultado de una consulta usando LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="76e5b-102">How to: Find the Minimum or Maximum Value in a Query Result by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="76e5b-103">Language-Integrated Query (LINQ) facilita el acceso a la información de la base de datos y ejecutar consultas.</span><span class="sxs-lookup"><span data-stu-id="76e5b-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="76e5b-104">En el ejemplo siguiente se muestra cómo crear una nueva aplicación que realiza consultas en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="76e5b-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span> <span data-ttu-id="76e5b-105">El ejemplo determina los valores mínimos y máximo de los resultados mediante el uso de la `Aggregate` y `Group By` cláusulas.</span><span class="sxs-lookup"><span data-stu-id="76e5b-105">The sample determines the minimum and maximum values for the results by using the `Aggregate` and `Group By` clauses.</span></span> <span data-ttu-id="76e5b-106">Para obtener más información, consulte [Aggregate (cláusula)](../../../../visual-basic/language-reference/queries/aggregate-clause.md) y [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="76e5b-106">For more information, see [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
 <span data-ttu-id="76e5b-107">Los ejemplos de este tema usan la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="76e5b-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="76e5b-108">Si no tiene la base de datos de ejemplo Northwind en el equipo de desarrollo, puede descargarlo desde el [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) sitio Web.</span><span class="sxs-lookup"><span data-stu-id="76e5b-108">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="76e5b-109">Para obtener instrucciones, consulte [descargar bases de datos de ejemplo](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="76e5b-109">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="76e5b-110">Para crear una conexión a una base de datos</span><span class="sxs-lookup"><span data-stu-id="76e5b-110">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="76e5b-111">En Visual Studio, abra **Explorador de servidores**/**el Explorador de base de datos** haciendo clic en **Explorador de servidores**/**base de datos El Explorador de** en el **vista** menú.</span><span class="sxs-lookup"><span data-stu-id="76e5b-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="76e5b-112">Haga clic en **las conexiones de datos** en **Explorador de servidores**/**el Explorador de base de datos** y, a continuación, haga clic en **Agregar conexión**.</span><span class="sxs-lookup"><span data-stu-id="76e5b-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="76e5b-113">Especifique una conexión válida a la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="76e5b-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="76e5b-114">Para agregar un proyecto que contiene un archivo LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="76e5b-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="76e5b-115">En el menú **Archivo** de Visual Studio, apunte a **Nuevo** y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="76e5b-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="76e5b-116">Seleccione Visual Basic **aplicación de Windows Forms** como el tipo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="76e5b-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="76e5b-117">En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="76e5b-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="76e5b-118">Seleccione el **clases LINQ to SQL** plantilla de elemento.</span><span class="sxs-lookup"><span data-stu-id="76e5b-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="76e5b-119">Asigne al archivo el nombre `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="76e5b-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="76e5b-120">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="76e5b-120">Click **Add**.</span></span> <span data-ttu-id="76e5b-121">Se abre el Object Relational Designer (Object Relational Designer) para el archivo northwind.dbml.</span><span class="sxs-lookup"><span data-stu-id="76e5b-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="76e5b-122">Para agregar tablas a una consulta para el Object Relational Designer</span><span class="sxs-lookup"><span data-stu-id="76e5b-122">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="76e5b-123">En **Explorador de servidores**/**el Explorador de base de datos**, expanda la conexión a la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="76e5b-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="76e5b-124">Expanda el **tablas** carpeta.</span><span class="sxs-lookup"><span data-stu-id="76e5b-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="76e5b-125">Si ha cerrado el Object Relational Designer, puede volver a abrirlo haciendo doble clic en el archivo northwind.dbml que agregó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="76e5b-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="76e5b-126">Haga clic en la tabla Customers y arrástrelo hasta el panel izquierdo del diseñador.</span><span class="sxs-lookup"><span data-stu-id="76e5b-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="76e5b-127">Haga clic en la tabla Orders y arrástrelo hasta el panel izquierdo del diseñador.</span><span class="sxs-lookup"><span data-stu-id="76e5b-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="76e5b-128">El diseñador crea nuevos `Customer` y `Order` objetos para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="76e5b-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="76e5b-129">Observe que el diseñador automáticamente detecta las relaciones entre las tablas y crea a secundarios propiedades de objetos relacionados.</span><span class="sxs-lookup"><span data-stu-id="76e5b-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="76e5b-130">Por ejemplo, IntelliSense mostrará que el `Customer` objeto tiene una `Orders` propiedad para todos los pedidos relacionados con ese cliente.</span><span class="sxs-lookup"><span data-stu-id="76e5b-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="76e5b-131">Guarde los cambios y cierre el diseñador.</span><span class="sxs-lookup"><span data-stu-id="76e5b-131">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="76e5b-132">Guarde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="76e5b-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="76e5b-133">Para agregar código para consultar la base de datos y mostrar los resultados</span><span class="sxs-lookup"><span data-stu-id="76e5b-133">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="76e5b-134">Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.DataGridView> control en el formulario Windows Forms predeterminado para el proyecto, Form1.</span><span class="sxs-lookup"><span data-stu-id="76e5b-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="76e5b-135">Haga doble clic en Form1 para agregar código a la `Load` evento del formulario.</span><span class="sxs-lookup"><span data-stu-id="76e5b-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="76e5b-136">Cuando agrega tablas a Object Relational Designer, el diseñador agrega un <xref:System.Data.Linq.DataContext> objeto para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="76e5b-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="76e5b-137">Este objeto contiene el código que necesita para tener acceso a esas tablas, además de los objetos individuales y colecciones de cada tabla.</span><span class="sxs-lookup"><span data-stu-id="76e5b-137">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="76e5b-138">La <xref:System.Data.Linq.DataContext> objeto para el proyecto se denomina según el nombre del archivo dbml.</span><span class="sxs-lookup"><span data-stu-id="76e5b-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="76e5b-139">Para este proyecto, el <xref:System.Data.Linq.DataContext> se denomina objeto `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="76e5b-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="76e5b-140">Puede crear una instancia de la <xref:System.Data.Linq.DataContext> en el código y consultar las tablas especifican por el Object Relational Designer.</span><span class="sxs-lookup"><span data-stu-id="76e5b-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="76e5b-141">Agregue el código siguiente a la `Load` eventos.</span><span class="sxs-lookup"><span data-stu-id="76e5b-141">Add the following code to the `Load` event.</span></span> <span data-ttu-id="76e5b-142">Este código realiza una consulta de las tablas que se exponen como propiedades de su contexto de datos y determina los valores mínimos y máximo para los resultados.</span><span class="sxs-lookup"><span data-stu-id="76e5b-142">This code queries the tables that are exposed as properties of your data context and determines the minimum and maximum values for the results.</span></span> <span data-ttu-id="76e5b-143">El ejemplo se usa `Aggregate` cláusula para consultar un único resultado y el `Group By` cláusula para mostrar un promedio para agrupar resultados.</span><span class="sxs-lookup"><span data-stu-id="76e5b-143">The sample uses he `Aggregate` clause to query for a single result, and the `Group By` clause to show an average for grouped results.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#14](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-find-the-minimum-or-maximum-value-in-a-query-result_1.vb)]  
  
4.  <span data-ttu-id="76e5b-144">Presione F5 para ejecutar el proyecto y ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="76e5b-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76e5b-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="76e5b-145">See Also</span></span>  
 [<span data-ttu-id="76e5b-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="76e5b-146">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="76e5b-147">Consultas</span><span class="sxs-lookup"><span data-stu-id="76e5b-147">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="76e5b-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="76e5b-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)  
 [<span data-ttu-id="76e5b-149">Métodos de DataContext (Object Relational Designer)</span><span class="sxs-lookup"><span data-stu-id="76e5b-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
