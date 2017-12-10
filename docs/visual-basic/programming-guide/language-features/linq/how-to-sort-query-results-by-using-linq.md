---
title: "Cómo: Ordenar los resultados de una consulta mediante LINQ (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 956eb92ca802b478fac9452cc98b5dd2e2fbcd4a
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2017
---
# <a name="how-to-sort-query-results-by-using-linq-visual-basic"></a><span data-ttu-id="7e1c0-102">Cómo: Ordenar los resultados de una consulta mediante LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7e1c0-102">How to: Sort Query Results by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="7e1c0-103">Language-Integrated Query (LINQ) facilita el acceso a la información de la base de datos y ejecutar consultas.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="7e1c0-104">En el ejemplo siguiente se muestra cómo crear una nueva aplicación que realiza consultas en una base de datos de SQL Server y ordena los resultados por varios campos mediante el uso de la `Order By` cláusula.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-104">The following example shows how to create a new application that performs queries against a SQL Server database and sorts the results by multiple fields by using the `Order By` clause.</span></span> <span data-ttu-id="7e1c0-105">El criterio de ordenación para cada campo puede ser ascendente o descendente.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-105">The sort order for each field can be ascending order or descending order.</span></span> <span data-ttu-id="7e1c0-106">Para obtener más información, consulte [cláusula Order By](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="7e1c0-106">For more information, see [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="7e1c0-107">Los ejemplos de este tema usan la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="7e1c0-108">Si no tiene la base de datos de ejemplo Northwind en el equipo de desarrollo, puede descargarlo desde el [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) sitio Web.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-108">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="7e1c0-109">Para obtener instrucciones, consulte [descargar bases de datos de ejemplo](../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="7e1c0-109">For instructions, see [Downloading Sample Databases](../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="7e1c0-110">Para crear una conexión a una base de datos</span><span class="sxs-lookup"><span data-stu-id="7e1c0-110">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="7e1c0-111">En Visual Studio, abra **Explorador de servidores**/**el Explorador de base de datos** haciendo clic en **Explorador de servidores**/**base de datos El Explorador de** en el **vista** menú.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="7e1c0-112">Haga clic en **las conexiones de datos** en **Explorador de servidores**/**el Explorador de base de datos** y, a continuación, haga clic en **Agregar conexión**.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="7e1c0-113">Especifique una conexión válida a la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="7e1c0-114">Para agregar un proyecto que contiene un archivo LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="7e1c0-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="7e1c0-115">En el menú **Archivo** de Visual Studio, apunte a **Nuevo** y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="7e1c0-116">Seleccione Visual Basic **aplicación de Windows Forms** como el tipo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="7e1c0-117">En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="7e1c0-118">Seleccione el **clases LINQ to SQL** plantilla de elemento.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="7e1c0-119">Asigne al archivo el nombre `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="7e1c0-120">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-120">Click **Add**.</span></span> <span data-ttu-id="7e1c0-121">Se abre el Object Relational Designer (Object Relational Designer) para el archivo northwind.dbml.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="7e1c0-122">Para agregar tablas a una consulta para el Object Relational Designer</span><span class="sxs-lookup"><span data-stu-id="7e1c0-122">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="7e1c0-123">En **Explorador de servidores**/**el Explorador de base de datos**, expanda la conexión a la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="7e1c0-124">Expanda el **tablas** carpeta.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="7e1c0-125">Si ha cerrado el Object Relational Designer, puede volver a abrirlo haciendo doble clic en el archivo northwind.dbml que agregó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="7e1c0-126">Haga clic en la tabla Customers y arrástrelo hasta el panel izquierdo del diseñador.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="7e1c0-127">Haga clic en la tabla Orders y arrástrelo hasta el panel izquierdo del diseñador.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="7e1c0-128">El diseñador crea nuevos `Customer` y `Order` objetos para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="7e1c0-129">Observe que el diseñador automáticamente detecta las relaciones entre las tablas y crea a secundarios propiedades de objetos relacionados.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="7e1c0-130">Por ejemplo, IntelliSense mostrará que el `Customer` objeto tiene una `Orders` propiedad para todos los pedidos relacionados con ese cliente.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="7e1c0-131">Guarde los cambios y cierre el diseñador.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-131">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="7e1c0-132">Guarde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="7e1c0-133">Para agregar código para consultar la base de datos y mostrar los resultados</span><span class="sxs-lookup"><span data-stu-id="7e1c0-133">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="7e1c0-134">Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.DataGridView> control en el formulario Windows Forms predeterminado para el proyecto, Form1.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="7e1c0-135">Haga doble clic en Form1 para agregar código a la `Load` evento del formulario.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="7e1c0-136">Cuando agrega tablas a Object Relational Designer, el diseñador agrega un <xref:System.Data.Linq.DataContext> objeto a su proyecto.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="7e1c0-137">Este objeto contiene el código que debe tener acceso a esas tablas y para tener acceso a objetos individuales y colecciones para cada tabla.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-137">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="7e1c0-138">La <xref:System.Data.Linq.DataContext> objeto para el proyecto se denomina según el nombre del archivo dbml.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="7e1c0-139">Para este proyecto, el <xref:System.Data.Linq.DataContext> se denomina objeto `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="7e1c0-140">Puede crear una instancia de la <xref:System.Data.Linq.DataContext> en el código y consultar las tablas especifican por el Object Relational Designer.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="7e1c0-141">Agregue el código siguiente a la `Load` eventos para consultar las tablas que se exponen como propiedades de su contexto de datos y ordenación los resultados.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-141">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context and sort the results.</span></span> <span data-ttu-id="7e1c0-142">La consulta ordena los resultados por el número de pedidos de cliente, en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-142">The query sorts the results by the number of customer orders, in descending order.</span></span> <span data-ttu-id="7e1c0-143">Los clientes que tienen el mismo número de pedidos se ordenan por nombre de la compañía de forma ascendente (el valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="7e1c0-143">Customers that have the same number of orders are ordered by company name in ascending order (the default).</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#10](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-sort-query-results-by-using-linq_1.vb)]  
  
4.  <span data-ttu-id="7e1c0-144">Presione F5 para ejecutar el proyecto y ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e1c0-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e1c0-145">See Also</span></span>  
 [<span data-ttu-id="7e1c0-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="7e1c0-146">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="7e1c0-147">Consultas</span><span class="sxs-lookup"><span data-stu-id="7e1c0-147">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="7e1c0-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="7e1c0-148">LINQ to SQL</span></span>](../../../../../docs/framework/data/adonet/sql/linq/index.md)  
 [<span data-ttu-id="7e1c0-149">Métodos de DataContext (Object Relational Designer)</span><span class="sxs-lookup"><span data-stu-id="7e1c0-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
