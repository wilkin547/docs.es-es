---
description: 'Más información acerca de cómo: modificar datos en una base de datos mediante LINQ (Visual Basic)'
title: Procedimiento para modificar datos en una base de datos mediante LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- inserting rows [LINQ to SQL]
- deleting rows [LINQ to SQL]
- updating rows [LINQ to SQL]
- inserting data [Visual Basic]
- deleting data
- data [Visual Basic], updating
- updating data [LINQ]
- queries [LINQ in Visual Basic], data changes in database
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: cf52635f-0c1b-46c3-aff1-bdf181cf19b1
ms.openlocfilehash: b58ca542fbc6f4d63705e45b53edc8ded83ab88b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100422775"
---
# <a name="how-to-modify-data-in-a-database-by-using-linq-visual-basic"></a><span data-ttu-id="b772f-103">Cómo: Modificar datos en una base de datos usando LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b772f-103">How to: Modify Data in a Database by Using LINQ (Visual Basic)</span></span>

<span data-ttu-id="b772f-104">Las consultas de Language-Integrated Query (LINQ) facilitan el acceso a la información de base de datos y la modificación de los valores de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b772f-104">Language-Integrated Query (LINQ) queries make it easy to access database information and modify values in the database.</span></span>

<span data-ttu-id="b772f-105">En el ejemplo siguiente se muestra cómo crear una nueva aplicación que recupera y actualiza la información en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b772f-105">The following example shows how to create a new application that retrieves and updates information in a SQL Server database.</span></span>

<span data-ttu-id="b772f-106">En los ejemplos de este tema se utiliza la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="b772f-106">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="b772f-107">Si no dispone de esta base de datos en el equipo de desarrollo, puede descargarla del Centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b772f-107">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="b772f-108">Para obtener instrucciones, consulte [Descargar bases de datos de ejemplo](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="b772f-108">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>

### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="b772f-109">Para crear una conexión a una base de datos</span><span class="sxs-lookup"><span data-stu-id="b772f-109">To create a connection to a database</span></span>

1. <span data-ttu-id="b772f-110">Para abrir **Explorador de servidores** explorador de bases de datos en Visual Studio, /  haga clic en el menú **Ver** y, a continuación, seleccione **Explorador de servidores** / **Explorador de bases de datos**.</span><span class="sxs-lookup"><span data-stu-id="b772f-110">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking the **View** menu, and then select **Server Explorer**/**Database Explorer**.</span></span>

2. <span data-ttu-id="b772f-111">Haga clic con el botón secundario en **conexiones de datos** en **Explorador de servidores** / **Explorador de bases de datos** y haga clic en **Agregar conexión**.</span><span class="sxs-lookup"><span data-stu-id="b772f-111">Right-click **Data Connections** in **Server Explorer**/**Database Explorer**, and click **Add Connection**.</span></span>

3. <span data-ttu-id="b772f-112">Especifique una conexión válida a la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="b772f-112">Specify a valid connection to the Northwind sample database.</span></span>

### <a name="to-add-a-project-with-a-linq-to-sql-file"></a><span data-ttu-id="b772f-113">Para agregar un proyecto con un archivo LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="b772f-113">To add a Project with a LINQ to SQL file</span></span>

1. <span data-ttu-id="b772f-114">En el menú **Archivo** de Visual Studio, apunte a **Nuevo** y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="b772f-114">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="b772f-115">Seleccione Visual Basic **aplicación de Windows Forms** como el tipo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="b772f-115">Select Visual Basic **Windows Forms Application** as the project type.</span></span>

2. <span data-ttu-id="b772f-116">En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="b772f-116">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="b772f-117">Seleccione la plantilla de elementos **LINQ to SQL clases** .</span><span class="sxs-lookup"><span data-stu-id="b772f-117">Select the **LINQ to SQL Classes** item template.</span></span>

3. <span data-ttu-id="b772f-118">Ponga al archivo el nombre `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="b772f-118">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="b772f-119">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b772f-119">Click **Add**.</span></span> <span data-ttu-id="b772f-120">Se abre el Object Relational Designer (Object Relational Designer) para el `northwind.dbml` archivo.</span><span class="sxs-lookup"><span data-stu-id="b772f-120">The Object Relational Designer (O/R Designer) is opened for the `northwind.dbml` file.</span></span>

### <a name="to-add-tables-to-query-and-modify-to-the-designer"></a><span data-ttu-id="b772f-121">Para agregar tablas que se van a consultar y modificar en el diseñador</span><span class="sxs-lookup"><span data-stu-id="b772f-121">To add tables to query and modify to the designer</span></span>

1. <span data-ttu-id="b772f-122">En **Explorador de servidores** / **Explorador de bases de datos**, expanda la conexión a la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="b772f-122">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="b772f-123">Expanda la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="b772f-123">Expand the **Tables** folder.</span></span>

     <span data-ttu-id="b772f-124">Si ha cerrado el Object Relational Designer, puede volver a abrirlo si hace doble clic en el `northwind.dbml` archivo que agregó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="b772f-124">If you have closed the O/R Designer, you can reopen it by double-clicking the `northwind.dbml` file that you added earlier.</span></span>

2. <span data-ttu-id="b772f-125">Haga clic en la tabla Customers y arrástrela hasta el panel izquierdo del diseñador.</span><span class="sxs-lookup"><span data-stu-id="b772f-125">Click the Customers table and drag it to the left pane of the designer.</span></span>

     <span data-ttu-id="b772f-126">El diseñador crea un nuevo objeto Customer para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b772f-126">The designer creates a new Customer object for your project.</span></span>

3. <span data-ttu-id="b772f-127">Guarde los cambios y cierre el diseñador.</span><span class="sxs-lookup"><span data-stu-id="b772f-127">Save your changes and close the designer.</span></span>

4. <span data-ttu-id="b772f-128">Guarde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b772f-128">Save your project.</span></span>

### <a name="to-add-code-to-modify-the-database-and-display-the-results"></a><span data-ttu-id="b772f-129">Para agregar código con el fin de modificar la base de datos y mostrar los resultados</span><span class="sxs-lookup"><span data-stu-id="b772f-129">To add code to modify the database and display the results</span></span>

1. <span data-ttu-id="b772f-130">En el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.DataGridView> control al formulario de Windows Forms predeterminado para el proyecto, Form1.</span><span class="sxs-lookup"><span data-stu-id="b772f-130">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>

2. <span data-ttu-id="b772f-131">Al agregar tablas a Object Relational Designer, el diseñador agregó un <xref:System.Data.Linq.DataContext> objeto al proyecto.</span><span class="sxs-lookup"><span data-stu-id="b772f-131">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="b772f-132">Este objeto contiene código que se puede utilizar para tener acceso a la tabla customers.</span><span class="sxs-lookup"><span data-stu-id="b772f-132">This object contains code that you can use to access the Customers table.</span></span> <span data-ttu-id="b772f-133">También contiene código que define un objeto de cliente local y una colección de clientes para la tabla.</span><span class="sxs-lookup"><span data-stu-id="b772f-133">It also contains code that defines  a local Customer object and a Customers collection for the table.</span></span> <span data-ttu-id="b772f-134">El <xref:System.Data.Linq.DataContext> nombre del objeto para el proyecto se basa en el nombre del archivo. dbml.</span><span class="sxs-lookup"><span data-stu-id="b772f-134">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="b772f-135">Para este proyecto, el <xref:System.Data.Linq.DataContext> objeto se denomina `northwindDataContext` .</span><span class="sxs-lookup"><span data-stu-id="b772f-135">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>

     <span data-ttu-id="b772f-136">Puede crear una instancia del <xref:System.Data.Linq.DataContext> objeto en el código y consultar y modificar la colección customers especificada por Object Relational Designer.</span><span class="sxs-lookup"><span data-stu-id="b772f-136">You can create an instance of the <xref:System.Data.Linq.DataContext> object in your code and query and modify the Customers collection specified by the O/R Designer.</span></span> <span data-ttu-id="b772f-137">Los cambios que realice en la colección customers no se reflejarán en la base de datos hasta que los envíe llamando al <xref:System.Data.Linq.DataContext.SubmitChanges%2A> método del <xref:System.Data.Linq.DataContext> objeto.</span><span class="sxs-lookup"><span data-stu-id="b772f-137">Changes that you make to the Customers collection are not reflected in the database until you submit them by calling the <xref:System.Data.Linq.DataContext.SubmitChanges%2A> method of the <xref:System.Data.Linq.DataContext> object.</span></span>

     <span data-ttu-id="b772f-138">Haga doble clic en Windows Forms, Form1, para agregar código al <xref:System.Windows.Forms.Form.Load> evento para consultar la tabla Customers que se expone como una propiedad de su <xref:System.Data.Linq.DataContext> .</span><span class="sxs-lookup"><span data-stu-id="b772f-138">Double-click the Windows Form, Form1, to add code to the <xref:System.Windows.Forms.Form.Load> event to query the Customers table that is exposed as a property of your <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="b772f-139">Agregue el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="b772f-139">Add the following code:</span></span>

    ```vb
    Private db As northwindDataContext

    Private Sub Form1_Load(ByVal sender As System.Object,
                           ByVal e As System.EventArgs
                          ) Handles MyBase.Load
      db = New northwindDataContext()

      RefreshData()
    End Sub

    Private Sub RefreshData()
      Dim customers = From cust In db.Customers
                      Where cust.City(0) = "W"
                      Select cust

      DataGridView1.DataSource = customers
    End Sub
    ```

3. <span data-ttu-id="b772f-140">En el **cuadro de herramientas**, arrastre tres <xref:System.Windows.Forms.Button> controles al formulario.</span><span class="sxs-lookup"><span data-stu-id="b772f-140">From the **Toolbox**, drag three <xref:System.Windows.Forms.Button> controls onto the form.</span></span> <span data-ttu-id="b772f-141">Seleccione el primer `Button` control.</span><span class="sxs-lookup"><span data-stu-id="b772f-141">Select the first `Button` control.</span></span> <span data-ttu-id="b772f-142">En la ventana **propiedades** , establezca la propiedad `Name` del `Button` control en `AddButton` y `Text` en `Add` .</span><span class="sxs-lookup"><span data-stu-id="b772f-142">In the **Properties** window, set the `Name` of the `Button` control to `AddButton` and the `Text` to `Add`.</span></span> <span data-ttu-id="b772f-143">Seleccione el segundo botón y establezca la `Name` propiedad en `UpdateButton` y la `Text` propiedad en `Update` .</span><span class="sxs-lookup"><span data-stu-id="b772f-143">Select the second button and set the `Name` property to `UpdateButton` and the `Text` property to `Update`.</span></span> <span data-ttu-id="b772f-144">Seleccione el tercer botón y establezca la `Name` propiedad en `DeleteButton` y la `Text` propiedad en `Delete` .</span><span class="sxs-lookup"><span data-stu-id="b772f-144">Select the third button and set the `Name` property to `DeleteButton` and the `Text` property to `Delete`.</span></span>

4. <span data-ttu-id="b772f-145">Haga doble clic en el botón **Agregar** para agregar código a su `Click` evento.</span><span class="sxs-lookup"><span data-stu-id="b772f-145">Double-click the **Add** button to add code to its `Click` event.</span></span> <span data-ttu-id="b772f-146">Agregue el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="b772f-146">Add the following code:</span></span>

    ```vb
    Private Sub AddButton_Click(ByVal sender As System.Object,
                                ByVal e As System.EventArgs
                               ) Handles AddButton.Click
      Dim cust As New Customer With {
        .City = "Wellington",
        .CompanyName = "Blue Yonder Airlines",
        .ContactName = "Jill Frank",
        .Country = "New Zealand",
        .CustomerID = "JILLF"}

      db.Customers.InsertOnSubmit(cust)

      Try
        db.SubmitChanges()
      Catch
        ' Handle exception.
      End Try

      RefreshData()
    End Sub
    ```

5. <span data-ttu-id="b772f-147">Haga doble clic en el botón **Actualizar** para agregar código a su `Click` evento.</span><span class="sxs-lookup"><span data-stu-id="b772f-147">Double-click the **Update** button to add code to its `Click` event.</span></span> <span data-ttu-id="b772f-148">Agregue el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="b772f-148">Add the following code:</span></span>

    ```vb
    Private Sub UpdateButton_Click(ByVal sender As System.Object, _
                                   ByVal e As System.EventArgs
                                  ) Handles UpdateButton.Click
      Dim updateCust = (From cust In db.Customers
                        Where cust.CustomerID = "JILLF").ToList()(0)

      updateCust.ContactName = "Jill Shrader"
      updateCust.Country = "Wales"
      updateCust.CompanyName = "Red Yonder Airlines"
      updateCust.City = "Cardiff"

      Try
        db.SubmitChanges()
      Catch
        ' Handle exception.
      End Try

      RefreshData()
    End Sub
    ```

6. <span data-ttu-id="b772f-149">Haga doble clic en el botón **eliminar** para agregar código a su `Click` evento.</span><span class="sxs-lookup"><span data-stu-id="b772f-149">Double-click the **Delete** button to add code to its `Click` event.</span></span> <span data-ttu-id="b772f-150">Agregue el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="b772f-150">Add the following code:</span></span>

    ```vb
    Private Sub DeleteButton_Click(ByVal sender As System.Object, _
                                   ByVal e As System.EventArgs
                                  ) Handles DeleteButton.Click
      Dim deleteCust = (From cust In db.Customers
                        Where cust.CustomerID = "JILLF").ToList()(0)

      db.Customers.DeleteOnSubmit(deleteCust)

      Try
        db.SubmitChanges()
      Catch
        ' Handle exception.
      End Try

      RefreshData()
    End Sub
    ```

7. <span data-ttu-id="b772f-151">Presione F5 para ejecutar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b772f-151">Press F5 to run your project.</span></span> <span data-ttu-id="b772f-152">Haga clic en **Agregar** para agregar un nuevo registro.</span><span class="sxs-lookup"><span data-stu-id="b772f-152">Click **Add** to add a new record.</span></span> <span data-ttu-id="b772f-153">Haga clic en **Actualizar** para modificar el nuevo registro.</span><span class="sxs-lookup"><span data-stu-id="b772f-153">Click **Update** to modify the new record.</span></span> <span data-ttu-id="b772f-154">Haga clic en **eliminar** para eliminar el nuevo registro.</span><span class="sxs-lookup"><span data-stu-id="b772f-154">Click **Delete** to delete the new record.</span></span>

## <a name="see-also"></a><span data-ttu-id="b772f-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="b772f-155">See also</span></span>

- [<span data-ttu-id="b772f-156">LINQ</span><span class="sxs-lookup"><span data-stu-id="b772f-156">LINQ</span></span>](index.md)
- [<span data-ttu-id="b772f-157">Consultas</span><span class="sxs-lookup"><span data-stu-id="b772f-157">Queries</span></span>](../../../language-reference/queries/index.md)
- [<span data-ttu-id="b772f-158">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="b772f-158">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="b772f-159">DataContext (Métodos) (Object Relational Designer)</span><span class="sxs-lookup"><span data-stu-id="b772f-159">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [<span data-ttu-id="b772f-160">Cómo: Asignar procedimientos almacenados para realizar actualizaciones, inserciones y eliminaciones (Object Relational Designer)</span><span class="sxs-lookup"><span data-stu-id="b772f-160">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
