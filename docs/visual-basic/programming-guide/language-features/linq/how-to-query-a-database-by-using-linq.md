---
title: 'Cómo: Consultar una base de datos usando LINQ (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- query samples [LINQ]
- database querying [LINQ]
- queries [LINQ in Visual Basic], database querying
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: bcf5e9c3-a236-4399-9a7f-3991eca7cf56
ms.openlocfilehash: f17e0dc6956c5465f8269562705eb0f754f1585c
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2018
ms.locfileid: "37960480"
---
# <a name="how-to-query-a-database-by-using-linq-visual-basic"></a><span data-ttu-id="bcadf-102">Cómo: Consultar una base de datos usando LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bcadf-102">How to: Query a Database by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="bcadf-103">Language-Integrated Query (LINQ) facilita el acceso a la información de la base de datos y ejecutar consultas.</span><span class="sxs-lookup"><span data-stu-id="bcadf-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="bcadf-104">El ejemplo siguiente muestra cómo crear una nueva aplicación que realiza consultas en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bcadf-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span>  
  
 <span data-ttu-id="bcadf-105">Los ejemplos de este tema usan la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="bcadf-105">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="bcadf-106">Si no tiene esta base de datos en el equipo de desarrollo, puede descargarlo desde Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="bcadf-106">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="bcadf-107">Para obtener instrucciones, consulte [descargar bases de datos de ejemplo](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="bcadf-107">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="bcadf-108">Para crear una conexión a una base de datos</span><span class="sxs-lookup"><span data-stu-id="bcadf-108">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="bcadf-109">En Visual Studio, abra **Explorador de servidores**/**Database Explorer** haciendo **Explorador de servidores**/**base de datos Explorador** en el **vista** menú.</span><span class="sxs-lookup"><span data-stu-id="bcadf-109">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="bcadf-110">Haga clic en **conexiones de datos** en **Explorador de servidores**/**Database Explorer** y, a continuación, haga clic en **Agregar conexión**.</span><span class="sxs-lookup"><span data-stu-id="bcadf-110">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="bcadf-111">Especifique una conexión válida a la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="bcadf-111">Specify a valid connection to the Northwind sample database.</span></span>  
  
## <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="bcadf-112">Para agregar un proyecto que contiene un archivo LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="bcadf-112">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="bcadf-113">En el menú **Archivo** de Visual Studio, apunte a **Nuevo** y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="bcadf-113">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="bcadf-114">Seleccione Visual Basic **aplicación de Windows Forms** como el tipo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="bcadf-114">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="bcadf-115">En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="bcadf-115">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="bcadf-116">Seleccione el **clases LINQ to SQL** plantilla de elemento.</span><span class="sxs-lookup"><span data-stu-id="bcadf-116">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="bcadf-117">Asigne al archivo el nombre `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="bcadf-117">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="bcadf-118">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="bcadf-118">Click **Add**.</span></span> <span data-ttu-id="bcadf-119">Se abre el Object Relational Designer (Object Relational Designer) para el archivo northwind.dbml.</span><span class="sxs-lookup"><span data-stu-id="bcadf-119">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
## <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="bcadf-120">Para agregar tablas a la consulta en el Object Relational Designer</span><span class="sxs-lookup"><span data-stu-id="bcadf-120">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="bcadf-121">En **Explorador de servidores**/**Database Explorer**, expanda la conexión a la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="bcadf-121">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="bcadf-122">Expanda el **tablas** carpeta.</span><span class="sxs-lookup"><span data-stu-id="bcadf-122">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="bcadf-123">Si ha cerrado el Object Relational Designer, puede volver a abrirlo haciendo doble clic en el archivo northwind.dbml que agregó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="bcadf-123">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="bcadf-124">Haga clic en la tabla Customers y arrástrelo hasta el panel izquierdo del diseñador.</span><span class="sxs-lookup"><span data-stu-id="bcadf-124">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="bcadf-125">Haga clic en la tabla Orders y arrástrelo hasta el panel izquierdo del diseñador.</span><span class="sxs-lookup"><span data-stu-id="bcadf-125">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="bcadf-126">El diseñador crea nuevos `Customer` y `Order` objetos para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="bcadf-126">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="bcadf-127">Tenga en cuenta que el diseñador automáticamente detecta las relaciones entre las tablas y crea las propiedades de los objetos relacionados de secundarios.</span><span class="sxs-lookup"><span data-stu-id="bcadf-127">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="bcadf-128">Por ejemplo, IntelliSense mostrará que el `Customer` objeto tiene una `Orders` relacionados con la propiedad de todos los pedidos para ese cliente.</span><span class="sxs-lookup"><span data-stu-id="bcadf-128">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="bcadf-129">Guarde los cambios y cierre el diseñador.</span><span class="sxs-lookup"><span data-stu-id="bcadf-129">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="bcadf-130">Guarde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="bcadf-130">Save your project.</span></span>  
  
## <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="bcadf-131">Para agregar código para consultar la base de datos y mostrar los resultados</span><span class="sxs-lookup"><span data-stu-id="bcadf-131">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="bcadf-132">Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.DataGridView> control en el formulario de Windows predeterminada para el proyecto, Form1.</span><span class="sxs-lookup"><span data-stu-id="bcadf-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="bcadf-133">Haga doble clic en Form1 para agregar código a la `Load` evento del formulario.</span><span class="sxs-lookup"><span data-stu-id="bcadf-133">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="bcadf-134">Cuando agrega tablas a Object Relational Designer, el diseñador agrega un <xref:System.Data.Linq.DataContext> objeto para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="bcadf-134">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="bcadf-135">Este objeto contiene el código que debe tener para tener acceso a esas tablas, además de los objetos individuales y colecciones para cada tabla.</span><span class="sxs-lookup"><span data-stu-id="bcadf-135">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="bcadf-136">La <xref:System.Data.Linq.DataContext> objeto para el proyecto se denomina según el nombre del archivo dbml.</span><span class="sxs-lookup"><span data-stu-id="bcadf-136">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="bcadf-137">Para este proyecto, el <xref:System.Data.Linq.DataContext> se denomina objeto `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="bcadf-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="bcadf-138">Puede crear una instancia de la <xref:System.Data.Linq.DataContext> en el código y consultar las tablas especifican por el Object Relational Designer.</span><span class="sxs-lookup"><span data-stu-id="bcadf-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="bcadf-139">Agregue el código siguiente a la `Load` que consultar las tablas que se exponen como propiedades del contexto de datos de evento.</span><span class="sxs-lookup"><span data-stu-id="bcadf-139">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#3](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_1.vb)]  
  
4.  <span data-ttu-id="bcadf-140">Presione F5 para ejecutar el proyecto y ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="bcadf-140">Press F5 to run your project and view the results.</span></span>  
  
5.  <span data-ttu-id="bcadf-141">Estos son algunas consultas adicionales que puede probar:</span><span class="sxs-lookup"><span data-stu-id="bcadf-141">Following are some additional queries that you can try:</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#4](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_2.vb)]  
    [!code-vb[VbLINQToSQLHowTos#5](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="bcadf-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="bcadf-142">See Also</span></span>  
 [<span data-ttu-id="bcadf-143">LINQ</span><span class="sxs-lookup"><span data-stu-id="bcadf-143">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="bcadf-144">Consultas</span><span class="sxs-lookup"><span data-stu-id="bcadf-144">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="bcadf-145">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="bcadf-145">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)  
 [<span data-ttu-id="bcadf-146">Métodos DataContext (Object Relational Designer)</span><span class="sxs-lookup"><span data-stu-id="bcadf-146">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
