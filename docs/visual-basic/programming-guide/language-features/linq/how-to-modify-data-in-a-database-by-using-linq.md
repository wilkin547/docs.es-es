---
title: "Cómo: Modificar datos en una base de datos usando LINQ (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3c491825d8fcacb9852584e7934682598441c2bd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-modify-data-in-a-database-by-using-linq-visual-basic"></a><span data-ttu-id="1a00f-102">Cómo: Modificar datos en una base de datos usando LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1a00f-102">How to: Modify Data in a Database by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="1a00f-103">Language Integrated Query de Query (LINQ) facilitan el acceso a la información de la base de datos y modificar los valores de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1a00f-103">Language-Integrated Query (LINQ) queries make it easy to access database information and modify values in the database.</span></span>  
  
 <span data-ttu-id="1a00f-104">En el ejemplo siguiente se muestra cómo crear una nueva aplicación que recupera y actualiza la información en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1a00f-104">The following example shows how to create a new application that retrieves and updates information in a SQL Server database.</span></span>  
  
 <span data-ttu-id="1a00f-105">Los ejemplos de este tema usan la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="1a00f-105">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="1a00f-106">Si no tiene la base de datos de ejemplo Northwind en el equipo de desarrollo, puede descargarlo desde el [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) sitio Web.</span><span class="sxs-lookup"><span data-stu-id="1a00f-106">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="1a00f-107">Para obtener instrucciones, consulte [descargar bases de datos de ejemplo](https://msdn.microsoft.com/library/bb399411).</span><span class="sxs-lookup"><span data-stu-id="1a00f-107">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="1a00f-108">Para crear una conexión a una base de datos</span><span class="sxs-lookup"><span data-stu-id="1a00f-108">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="1a00f-109">En Visual Studio, abra **Explorador de servidores**/**el Explorador de base de datos** haciendo clic en el **vista** menú y, a continuación, seleccione **delexploradordeservidores** / **El Explorador de la base de datos**.</span><span class="sxs-lookup"><span data-stu-id="1a00f-109">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking the **View** menu, and then select **Server Explorer**/**Database Explorer**.</span></span>  
  
2.  <span data-ttu-id="1a00f-110">Haga clic en **las conexiones de datos** en **Explorador de servidores**/**el Explorador de base de datos**y haga clic en **Agregar conexión**.</span><span class="sxs-lookup"><span data-stu-id="1a00f-110">Right-click **Data Connections** in **Server Explorer**/**Database Explorer**, and click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="1a00f-111">Especifique una conexión válida a la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="1a00f-111">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-with-a-linq-to-sql-file"></a><span data-ttu-id="1a00f-112">Para agregar un proyecto con LINQ a archivo SQL</span><span class="sxs-lookup"><span data-stu-id="1a00f-112">To add a Project with a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="1a00f-113">En el menú **Archivo** de Visual Studio, apunte a **Nuevo** y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="1a00f-113">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="1a00f-114">Seleccione Visual Basic **aplicación de Windows Forms** como el tipo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="1a00f-114">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="1a00f-115">En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="1a00f-115">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="1a00f-116">Seleccione el **clases LINQ to SQL** plantilla de elemento.</span><span class="sxs-lookup"><span data-stu-id="1a00f-116">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="1a00f-117">Asigne al archivo el nombre `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="1a00f-117">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="1a00f-118">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="1a00f-118">Click **Add**.</span></span> <span data-ttu-id="1a00f-119">Se abre el Object Relational Designer (Object Relational Designer) para el `northwind.dbml` archivo.</span><span class="sxs-lookup"><span data-stu-id="1a00f-119">The Object Relational Designer (O/R Designer) is opened for the `northwind.dbml` file.</span></span>  
  
### <a name="to-add-tables-to-query-and-modify-to-the-designer"></a><span data-ttu-id="1a00f-120">Para agregar tablas para consultar y modificar el diseñador</span><span class="sxs-lookup"><span data-stu-id="1a00f-120">To add tables to query and modify to the designer</span></span>  
  
1.  <span data-ttu-id="1a00f-121">En **Explorador de servidores**/**el Explorador de base de datos**, expanda la conexión a la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="1a00f-121">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="1a00f-122">Expanda el **tablas** carpeta.</span><span class="sxs-lookup"><span data-stu-id="1a00f-122">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="1a00f-123">Si ha cerrado el Object Relational Designer, puede volver a abrirlo haciendo doble clic en el `northwind.dbml` archivo que agregó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="1a00f-123">If you have closed the O/R Designer, you can reopen it by double-clicking the `northwind.dbml` file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="1a00f-124">Haga clic en la tabla Customers y arrástrelo hasta el panel izquierdo del diseñador.</span><span class="sxs-lookup"><span data-stu-id="1a00f-124">Click the Customers table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="1a00f-125">El diseñador crea un nuevo objeto de cliente para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="1a00f-125">The designer creates a new Customer object for your project.</span></span>  
  
3.  <span data-ttu-id="1a00f-126">Guarde los cambios y cierre el diseñador.</span><span class="sxs-lookup"><span data-stu-id="1a00f-126">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="1a00f-127">Guarde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="1a00f-127">Save your project.</span></span>  
  
### <a name="to-add-code-to-modify-the-database-and-display-the-results"></a><span data-ttu-id="1a00f-128">Para agregar código para modificar la base de datos y mostrar los resultados</span><span class="sxs-lookup"><span data-stu-id="1a00f-128">To add code to modify the database and display the results</span></span>  
  
1.  <span data-ttu-id="1a00f-129">Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.DataGridView> control en el formulario Windows Forms predeterminado para el proyecto, Form1.</span><span class="sxs-lookup"><span data-stu-id="1a00f-129">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="1a00f-130">Cuando agrega tablas a Object Relational Designer, el diseñador agrega un <xref:System.Data.Linq.DataContext> objeto a su proyecto.</span><span class="sxs-lookup"><span data-stu-id="1a00f-130">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="1a00f-131">Este objeto contiene código que puede usar para tener acceso a la tabla Customers.</span><span class="sxs-lookup"><span data-stu-id="1a00f-131">This object contains code that you can use to access the Customers table.</span></span> <span data-ttu-id="1a00f-132">También contiene el código que define un objeto de cliente local y una colección de los clientes de la tabla.</span><span class="sxs-lookup"><span data-stu-id="1a00f-132">It also contains code that defines  a local Customer object and a Customers collection for the table.</span></span> <span data-ttu-id="1a00f-133">La <xref:System.Data.Linq.DataContext> objeto para el proyecto se denomina según el nombre del archivo dbml.</span><span class="sxs-lookup"><span data-stu-id="1a00f-133">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="1a00f-134">Para este proyecto, el <xref:System.Data.Linq.DataContext> se denomina objeto `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="1a00f-134">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="1a00f-135">Puede crear una instancia de la <xref:System.Data.Linq.DataContext> objeto en el código y consultar y modificar la colección de los clientes especificada por el Object Relational Designer.</span><span class="sxs-lookup"><span data-stu-id="1a00f-135">You can create an instance of the <xref:System.Data.Linq.DataContext> object in your code and query and modify the Customers collection specified by the O/R Designer.</span></span> <span data-ttu-id="1a00f-136">Los cambios realizados en la colección de los clientes no se reflejan en la base de datos hasta que enviarlos mediante una llamada a la <xref:System.Data.Linq.DataContext.SubmitChanges%2A> método de la <xref:System.Data.Linq.DataContext> objeto.</span><span class="sxs-lookup"><span data-stu-id="1a00f-136">Changes that you make to the Customers collection are not reflected in the database until you submit them by calling the <xref:System.Data.Linq.DataContext.SubmitChanges%2A> method of the <xref:System.Data.Linq.DataContext> object.</span></span>  
  
     <span data-ttu-id="1a00f-137">Haga doble clic en el formulario Windows Forms, Form1, para agregar código a la <xref:System.Windows.Forms.Form.Load> eventos para consultar la tabla Customers que se exponen como una propiedad de su <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="1a00f-137">Double-click the Windows Form, Form1, to add code to the <xref:System.Windows.Forms.Form.Load> event to query the Customers table that is exposed as a property of your <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="1a00f-138">Agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="1a00f-138">Add the following code:</span></span>  
  
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
  
3.  <span data-ttu-id="1a00f-139">Desde el **cuadro de herramientas**, arrastre tres <xref:System.Windows.Forms.Button> controles al formulario.</span><span class="sxs-lookup"><span data-stu-id="1a00f-139">From the **Toolbox**, drag three <xref:System.Windows.Forms.Button> controls onto the form.</span></span> <span data-ttu-id="1a00f-140">Seleccione la primera `Button` control.</span><span class="sxs-lookup"><span data-stu-id="1a00f-140">Select the first `Button` control.</span></span> <span data-ttu-id="1a00f-141">En el **propiedades** ventana, establezca el `Name` de la `Button` el control a `AddButton` y `Text` a `Add`.</span><span class="sxs-lookup"><span data-stu-id="1a00f-141">In the **Properties** window, set the `Name` of the `Button` control to `AddButton` and the `Text` to `Add`.</span></span> <span data-ttu-id="1a00f-142">Seleccione el segundo botón y establezca la `Name` propiedad `UpdateButton` y `Text` propiedad `Update`.</span><span class="sxs-lookup"><span data-stu-id="1a00f-142">Select the second button and set the `Name` property to `UpdateButton` and the `Text` property to `Update`.</span></span> <span data-ttu-id="1a00f-143">Seleccione el tercer botón y establezca la `Name` propiedad `DeleteButton` y `Text` propiedad `Delete`.</span><span class="sxs-lookup"><span data-stu-id="1a00f-143">Select the third button and set the `Name` property to `DeleteButton` and the `Text` property to `Delete`.</span></span>  
  
4.  <span data-ttu-id="1a00f-144">Haga doble clic en el **agregar** botón para agregar código a su `Click` eventos.</span><span class="sxs-lookup"><span data-stu-id="1a00f-144">Double-click the **Add** button to add code to its `Click` event.</span></span> <span data-ttu-id="1a00f-145">Agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="1a00f-145">Add the following code:</span></span>  
  
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
  
5.  <span data-ttu-id="1a00f-146">Haga doble clic en el **actualización** botón para agregar código a su `Click` eventos.</span><span class="sxs-lookup"><span data-stu-id="1a00f-146">Double-click the **Update** button to add code to its `Click` event.</span></span> <span data-ttu-id="1a00f-147">Agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="1a00f-147">Add the following code:</span></span>  
  
    ```vb  
    Private Sub UpdateButton_Click(ByVal sender As System.Object, _  
                                   ByVal e As System.EventArgs  
                                  ) Handles UpdateButton.Click  
      Dim updateCust = (From cust In db.Customers   
                        Where cust.CustomerID = "JILLF").ToList()(0)  
  
      updateCust.ContactName = "Jill Shrader"  
  
      Try  
        db.SubmitChanges()  
      Catch  
        ' Handle exception.  
      End Try  
  
      RefreshData()  
    End Sub  
    ```  
  
6.  <span data-ttu-id="1a00f-148">Haga doble clic en el **eliminar** botón para agregar código a su `Click` eventos.</span><span class="sxs-lookup"><span data-stu-id="1a00f-148">Double-click the **Delete** button to add code to its `Click` event.</span></span> <span data-ttu-id="1a00f-149">Agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="1a00f-149">Add the following code:</span></span>  
  
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
  
7.  <span data-ttu-id="1a00f-150">Presione F5 para ejecutar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="1a00f-150">Press F5 to run your project.</span></span> <span data-ttu-id="1a00f-151">Haga clic en **agregar** para agregar un nuevo registro.</span><span class="sxs-lookup"><span data-stu-id="1a00f-151">Click **Add** to add a new record.</span></span> <span data-ttu-id="1a00f-152">Haga clic en **actualización** para modificar el nuevo registro.</span><span class="sxs-lookup"><span data-stu-id="1a00f-152">Click **Update** to modify the new record.</span></span> <span data-ttu-id="1a00f-153">Haga clic en **eliminar** para eliminar el nuevo registro.</span><span class="sxs-lookup"><span data-stu-id="1a00f-153">Click **Delete** to delete the new record.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a00f-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a00f-154">See Also</span></span>  
 [<span data-ttu-id="1a00f-155">LINQ</span><span class="sxs-lookup"><span data-stu-id="1a00f-155">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="1a00f-156">Consultas</span><span class="sxs-lookup"><span data-stu-id="1a00f-156">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="1a00f-157">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="1a00f-157">LINQ to SQL</span></span>](https://msdn.microsoft.com/library/bb386976)  
 [<span data-ttu-id="1a00f-158">Métodos de DataContext (Object Relational Designer)</span><span class="sxs-lookup"><span data-stu-id="1a00f-158">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)  
 [<span data-ttu-id="1a00f-159">Cómo: asignar procedimientos almacenados para realizar actualizaciones, inserciones y eliminaciones (Object Relational Designer)</span><span class="sxs-lookup"><span data-stu-id="1a00f-159">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)
