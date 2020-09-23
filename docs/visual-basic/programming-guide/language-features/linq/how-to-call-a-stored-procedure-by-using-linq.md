---
title: Procedimiento para llamar a un procedimiento almacenado mediante LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
ms.openlocfilehash: 7e5fecf0c4c0d3a561ec7d0c4ac03c9d9ce7f759
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075140"
---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a><span data-ttu-id="16d68-102">Cómo: Llamar a un procedimiento almacenado usando LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16d68-102">How to: Call a Stored Procedure by Using LINQ (Visual Basic)</span></span>

<span data-ttu-id="16d68-103">Language-Integrated Query (LINQ) facilita el acceso a la información de base de datos, incluidos los objetos de base de datos, como los procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="16d68-103">Language-Integrated Query (LINQ) makes it easy to access database information, including database objects such as stored procedures.</span></span>  
  
 <span data-ttu-id="16d68-104">En el ejemplo siguiente se muestra cómo crear una aplicación que llama a un procedimiento almacenado en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="16d68-104">The following example shows how to create an application that calls a stored procedure in a SQL Server database.</span></span> <span data-ttu-id="16d68-105">En el ejemplo se muestra cómo llamar a dos procedimientos almacenados diferentes en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="16d68-105">The sample shows how to call two different stored procedures in the database.</span></span> <span data-ttu-id="16d68-106">Cada procedimiento devuelve los resultados de una consulta.</span><span class="sxs-lookup"><span data-stu-id="16d68-106">Each procedure returns the results of a query.</span></span> <span data-ttu-id="16d68-107">Un procedimiento toma parámetros de entrada y el otro procedimiento no toma parámetros.</span><span class="sxs-lookup"><span data-stu-id="16d68-107">One procedure takes input parameters, and the other procedure does not take parameters.</span></span>  
  
 <span data-ttu-id="16d68-108">En los ejemplos de este tema se utiliza la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="16d68-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="16d68-109">Si no dispone de esta base de datos en el equipo de desarrollo, puede descargarla del Centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="16d68-109">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="16d68-110">Para obtener instrucciones, consulte [Descargar bases de datos de ejemplo](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="16d68-110">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="16d68-111">Para crear una conexión a una base de datos</span><span class="sxs-lookup"><span data-stu-id="16d68-111">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="16d68-112">En Visual Studio, Abra **Explorador de servidores** / **Explorador de bases de datos** haciendo clic en **Explorador de servidores** / **Explorador de bases de datos** en el menú **Ver** .</span><span class="sxs-lookup"><span data-stu-id="16d68-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="16d68-113">Haga clic con el botón secundario en **conexiones de datos** en **Explorador de servidores** / **Explorador de bases de datos** y, a continuación, haga clic en **Agregar conexión**.</span><span class="sxs-lookup"><span data-stu-id="16d68-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="16d68-114">Especifique una conexión válida a la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="16d68-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="16d68-115">Para agregar un proyecto que contiene un archivo LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="16d68-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="16d68-116">En el menú **Archivo** de Visual Studio, apunte a **Nuevo** y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="16d68-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="16d68-117">Seleccione Visual Basic **aplicación de Windows Forms** como el tipo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="16d68-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="16d68-118">En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="16d68-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="16d68-119">Seleccione la plantilla de elementos **LINQ to SQL clases** .</span><span class="sxs-lookup"><span data-stu-id="16d68-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="16d68-120">Ponga al archivo el nombre `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="16d68-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="16d68-121">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="16d68-121">Click **Add**.</span></span> <span data-ttu-id="16d68-122">El Object Relational Designer (Object Relational Designer) se abre para el archivo Northwind. dbml.</span><span class="sxs-lookup"><span data-stu-id="16d68-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a><span data-ttu-id="16d68-123">Para agregar procedimientos almacenados a Object Relational Designer</span><span class="sxs-lookup"><span data-stu-id="16d68-123">To add stored procedures to the O/R Designer</span></span>  
  
1. <span data-ttu-id="16d68-124">En **Explorador de servidores** / **Explorador de bases de datos**, expanda la conexión a la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="16d68-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="16d68-125">Expanda la carpeta **Procedimientos almacenados** .</span><span class="sxs-lookup"><span data-stu-id="16d68-125">Expand the **Stored Procedures** folder.</span></span>  
  
     <span data-ttu-id="16d68-126">Si ha cerrado el Object Relational Designer, puede volver a abrirlo si hace doble clic en el archivo Northwind. dbml que agregó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="16d68-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="16d68-127">Haga clic en el procedimiento almacenado **sales by Year** y arrástrelo hasta el panel derecho del diseñador.</span><span class="sxs-lookup"><span data-stu-id="16d68-127">Click the **Sales by Year** stored procedure and drag it to the right pane of the designer.</span></span> <span data-ttu-id="16d68-128">Haga clic en el procedimiento almacenado de los **diez productos más caros** y arrástrelo al panel derecho del diseñador.</span><span class="sxs-lookup"><span data-stu-id="16d68-128">Click the **Ten Most Expensive Products** stored procedure drag it to the right pane of the designer.</span></span>  
  
3. <span data-ttu-id="16d68-129">Guarde los cambios y cierre el diseñador.</span><span class="sxs-lookup"><span data-stu-id="16d68-129">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="16d68-130">Guarde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="16d68-130">Save your project.</span></span>  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a><span data-ttu-id="16d68-131">Para agregar código para mostrar los resultados de los procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="16d68-131">To add code to display the results of the stored procedures</span></span>  
  
1. <span data-ttu-id="16d68-132">En el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.DataGridView> control al formulario de Windows Forms predeterminado para el proyecto, Form1.</span><span class="sxs-lookup"><span data-stu-id="16d68-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="16d68-133">Haga doble clic en Form1 para agregar código a su `Load` evento.</span><span class="sxs-lookup"><span data-stu-id="16d68-133">Double-click Form1 to add code to its `Load` event.</span></span>  
  
3. <span data-ttu-id="16d68-134">Cuando agregó procedimientos almacenados a Object Relational Designer, el diseñador agregó un <xref:System.Data.Linq.DataContext> objeto para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="16d68-134">When you added stored procedures to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="16d68-135">Este objeto contiene el código que debe tener para obtener acceso a esos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="16d68-135">This object contains the code that you must have to access those procedures.</span></span> <span data-ttu-id="16d68-136">El <xref:System.Data.Linq.DataContext> nombre del objeto para el proyecto se basa en el nombre del archivo. dbml.</span><span class="sxs-lookup"><span data-stu-id="16d68-136">The <xref:System.Data.Linq.DataContext> object for the project is named based on the name of the .dbml file.</span></span> <span data-ttu-id="16d68-137">Para este proyecto, el <xref:System.Data.Linq.DataContext> objeto se denomina `northwindDataContext` .</span><span class="sxs-lookup"><span data-stu-id="16d68-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="16d68-138">Puede crear una instancia de <xref:System.Data.Linq.DataContext> en el código y llamar a los métodos de procedimiento almacenado especificados por Object Relational Designer.</span><span class="sxs-lookup"><span data-stu-id="16d68-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and call the stored procedure methods specified by the O/R Designer.</span></span> <span data-ttu-id="16d68-139">Para enlazar con el <xref:System.Windows.Forms.DataGridView> objeto, puede que tenga que forzar la ejecución inmediata de la consulta llamando al <xref:System.Linq.Enumerable.ToList%2A> método en los resultados del procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="16d68-139">To bind to the <xref:System.Windows.Forms.DataGridView> object, you may have to force the query to execute immediately by calling the <xref:System.Linq.Enumerable.ToList%2A> method on the results of the stored procedure.</span></span>  
  
     <span data-ttu-id="16d68-140">Agregue el código siguiente al `Load` evento para llamar a cualquiera de los procedimientos almacenados que se exponen como métodos para el contexto de datos.</span><span class="sxs-lookup"><span data-stu-id="16d68-140">Add the following code to the `Load` event to call either of the stored procedures exposed as methods for your data context.</span></span>  
  
     [!code-vb[VbLINQtoSQLHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#1)]  
    [!code-vb[VbLINQtoSQLHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#2)]  
  
4. <span data-ttu-id="16d68-141">Presione F5 para ejecutar el proyecto y ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="16d68-141">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16d68-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="16d68-142">See also</span></span>

- [<span data-ttu-id="16d68-143">LINQ</span><span class="sxs-lookup"><span data-stu-id="16d68-143">LINQ</span></span>](index.md)
- [<span data-ttu-id="16d68-144">Consultas</span><span class="sxs-lookup"><span data-stu-id="16d68-144">Queries</span></span>](../../../language-reference/queries/index.md)
- [<span data-ttu-id="16d68-145">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="16d68-145">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="16d68-146">DataContext (Métodos) (Object Relational Designer)</span><span class="sxs-lookup"><span data-stu-id="16d68-146">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [<span data-ttu-id="16d68-147">Cómo: Asignar procedimientos almacenados para realizar actualizaciones, inserciones y eliminaciones (Object Relational Designer)</span><span class="sxs-lookup"><span data-stu-id="16d68-147">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
