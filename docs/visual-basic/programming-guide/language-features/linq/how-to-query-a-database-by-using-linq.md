---
description: 'Más información acerca de cómo: consultar una base de datos mediante LINQ (Visual Basic)'
title: Procedimiento para consultar una base de datos mediante LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- query samples [LINQ]
- database querying [LINQ]
- queries [LINQ in Visual Basic], database querying
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: bcf5e9c3-a236-4399-9a7f-3991eca7cf56
ms.openlocfilehash: 9a5577b52fc9bb313717386ce921421a34928a4c
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100430604"
---
# <a name="how-to-query-a-database-by-using-linq-visual-basic"></a><span data-ttu-id="6f9b0-103">Cómo: Consultar una base de datos usando LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6f9b0-103">How to: Query a Database by Using LINQ (Visual Basic)</span></span>

<span data-ttu-id="6f9b0-104">Language-Integrated Query (LINQ) facilita el acceso a la información de base de datos y la ejecución de consultas.</span><span class="sxs-lookup"><span data-stu-id="6f9b0-104">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="6f9b0-105">En el ejemplo siguiente se muestra cómo crear una nueva aplicación que realiza consultas en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6f9b0-105">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span>  
  
 <span data-ttu-id="6f9b0-106">En los ejemplos de este tema se utiliza la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="6f9b0-106">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="6f9b0-107">Si no dispone de esta base de datos en el equipo de desarrollo, puede descargarla del Centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6f9b0-107">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="6f9b0-108">Para obtener instrucciones, consulte [Descargar bases de datos de ejemplo](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="6f9b0-108">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="6f9b0-109">Para crear una conexión a una base de datos</span><span class="sxs-lookup"><span data-stu-id="6f9b0-109">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="6f9b0-110">En Visual Studio, Abra **Explorador de servidores** / **Explorador de bases de datos** haciendo clic en **Explorador de servidores** / **Explorador de bases de datos** en el menú **Ver** .</span><span class="sxs-lookup"><span data-stu-id="6f9b0-110">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="6f9b0-111">Haga clic con el botón secundario en **conexiones de datos** en **Explorador de servidores** / **Explorador de bases de datos** y, a continuación, haga clic en **Agregar conexión**.</span><span class="sxs-lookup"><span data-stu-id="6f9b0-111">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="6f9b0-112">Especifique una conexión válida a la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="6f9b0-112">Specify a valid connection to the Northwind sample database.</span></span>  
  
## <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="6f9b0-113">Para agregar un proyecto que contiene un archivo LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="6f9b0-113">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="6f9b0-114">En el menú **Archivo** de Visual Studio, apunte a **Nuevo** y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="6f9b0-114">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="6f9b0-115">Seleccione Visual Basic **aplicación de Windows Forms** como el tipo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="6f9b0-115">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="6f9b0-116">En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="6f9b0-116">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="6f9b0-117">Seleccione la plantilla de elementos **LINQ to SQL clases** .</span><span class="sxs-lookup"><span data-stu-id="6f9b0-117">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="6f9b0-118">Ponga al archivo el nombre `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="6f9b0-118">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="6f9b0-119">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="6f9b0-119">Click **Add**.</span></span> <span data-ttu-id="6f9b0-120">El Object Relational Designer (Object Relational Designer) se abre para el archivo Northwind. dbml.</span><span class="sxs-lookup"><span data-stu-id="6f9b0-120">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
## <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="6f9b0-121">Para agregar tablas que se van a consultar en Object Relational Designer</span><span class="sxs-lookup"><span data-stu-id="6f9b0-121">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="6f9b0-122">En **Explorador de servidores** / **Explorador de bases de datos**, expanda la conexión a la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="6f9b0-122">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="6f9b0-123">Expanda la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="6f9b0-123">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="6f9b0-124">Si ha cerrado el Object Relational Designer, puede volver a abrirlo si hace doble clic en el archivo Northwind. dbml que agregó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6f9b0-124">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="6f9b0-125">Haga clic en la tabla Customers y arrástrela hasta el panel izquierdo del diseñador.</span><span class="sxs-lookup"><span data-stu-id="6f9b0-125">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="6f9b0-126">Haga clic en la tabla Orders y arrástrela hasta el panel izquierdo del diseñador.</span><span class="sxs-lookup"><span data-stu-id="6f9b0-126">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="6f9b0-127">El diseñador crea `Customer` objetos y nuevos `Order` para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="6f9b0-127">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="6f9b0-128">Observe que el diseñador detecta automáticamente las relaciones entre las tablas y crea las propiedades secundarias de los objetos relacionados.</span><span class="sxs-lookup"><span data-stu-id="6f9b0-128">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="6f9b0-129">Por ejemplo, IntelliSense mostrará que el `Customer` objeto tiene una `Orders` propiedad para todos los pedidos relacionados con ese cliente.</span><span class="sxs-lookup"><span data-stu-id="6f9b0-129">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3. <span data-ttu-id="6f9b0-130">Guarde los cambios y cierre el diseñador.</span><span class="sxs-lookup"><span data-stu-id="6f9b0-130">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="6f9b0-131">Guarde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="6f9b0-131">Save your project.</span></span>  
  
## <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="6f9b0-132">Para agregar código para consultar la base de datos y mostrar los resultados</span><span class="sxs-lookup"><span data-stu-id="6f9b0-132">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="6f9b0-133">En el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.DataGridView> control al formulario de Windows Forms predeterminado para el proyecto, Form1.</span><span class="sxs-lookup"><span data-stu-id="6f9b0-133">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="6f9b0-134">Haga doble clic en Form1 para agregar código al `Load` evento del formulario.</span><span class="sxs-lookup"><span data-stu-id="6f9b0-134">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3. <span data-ttu-id="6f9b0-135">Al agregar tablas a Object Relational Designer, el diseñador agregó un <xref:System.Data.Linq.DataContext> objeto para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="6f9b0-135">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="6f9b0-136">Este objeto contiene el código que debe tener para obtener acceso a esas tablas, además de colecciones y objetos individuales para cada tabla.</span><span class="sxs-lookup"><span data-stu-id="6f9b0-136">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="6f9b0-137">El <xref:System.Data.Linq.DataContext> nombre del objeto para el proyecto se basa en el nombre del archivo. dbml.</span><span class="sxs-lookup"><span data-stu-id="6f9b0-137">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="6f9b0-138">Para este proyecto, el <xref:System.Data.Linq.DataContext> objeto se denomina `northwindDataContext` .</span><span class="sxs-lookup"><span data-stu-id="6f9b0-138">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="6f9b0-139">Puede crear una instancia de en el <xref:System.Data.Linq.DataContext> código y consultar las tablas especificadas por Object Relational Designer.</span><span class="sxs-lookup"><span data-stu-id="6f9b0-139">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="6f9b0-140">Agregue el código siguiente al `Load` evento para consultar las tablas que se exponen como propiedades de su contexto de datos.</span><span class="sxs-lookup"><span data-stu-id="6f9b0-140">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form2.vb#3)]  
  
4. <span data-ttu-id="6f9b0-141">Presione F5 para ejecutar el proyecto y ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="6f9b0-141">Press F5 to run your project and view the results.</span></span>  
  
5. <span data-ttu-id="6f9b0-142">A continuación se muestran algunas consultas adicionales que puede probar:</span><span class="sxs-lookup"><span data-stu-id="6f9b0-142">Following are some additional queries that you can try:</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form2.vb#4)]  
    [!code-vb[VbLINQToSQLHowTos#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form2.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="6f9b0-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f9b0-143">See also</span></span>

- [<span data-ttu-id="6f9b0-144">LINQ</span><span class="sxs-lookup"><span data-stu-id="6f9b0-144">LINQ</span></span>](index.md)
- [<span data-ttu-id="6f9b0-145">Consultas</span><span class="sxs-lookup"><span data-stu-id="6f9b0-145">Queries</span></span>](../../../language-reference/queries/index.md)
- [<span data-ttu-id="6f9b0-146">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="6f9b0-146">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="6f9b0-147">DataContext (Métodos) (Object Relational Designer)</span><span class="sxs-lookup"><span data-stu-id="6f9b0-147">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
