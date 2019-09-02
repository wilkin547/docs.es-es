---
title: El método de carga
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
ms.openlocfilehash: b704deeffcd06bca09b6c26d60a66218b46fc55c
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203175"
---
# <a name="the-load-method"></a><span data-ttu-id="2c6ad-102">El método de carga</span><span class="sxs-lookup"><span data-stu-id="2c6ad-102">The Load Method</span></span>
<span data-ttu-id="2c6ad-103">Se puede utilizar el método <xref:System.Data.DataTable.Load%2A> para cargar una <xref:System.Data.DataTable> con filas desde un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="2c6ad-103">You can use the <xref:System.Data.DataTable.Load%2A> method to load a <xref:System.Data.DataTable> with rows from a data source.</span></span> <span data-ttu-id="2c6ad-104">Se trata de un método sobrecargado que, en su forma más simple, acepta un único parámetro, un **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="2c6ad-104">This is an overloaded method which, in its simplest form, accepts a single parameter, a **DataReader**.</span></span> <span data-ttu-id="2c6ad-105">En este formato, simplemente carga la **DataTable** con filas.</span><span class="sxs-lookup"><span data-stu-id="2c6ad-105">In this form, it simply loads the **DataTable** with rows.</span></span> <span data-ttu-id="2c6ad-106">Opcionalmente, puede especificar el parámetro **LoadOption** para controlar el modo en que se agregan los datos a la **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="2c6ad-106">Optionally, you can specify the **LoadOption** parameter to control how data is added to the **DataTable**.</span></span>  
  
 <span data-ttu-id="2c6ad-107">El parámetro **LoadOption** es especialmente útil en los casos en los que **DataTable** ya contiene filas de datos, ya que describe cómo se combinarán los datos entrantes del origen de datos con los datos que ya están en la tabla.</span><span class="sxs-lookup"><span data-stu-id="2c6ad-107">The **LoadOption** parameter is particularly useful in cases where the **DataTable** already contains rows of data, because it describes how incoming data from the data source will be combined with the data already in the table.</span></span> <span data-ttu-id="2c6ad-108">Por ejemplo, **PreserveCurrentValues** (valor predeterminado) especifica que en los casos en los que una fila se marca como agregada en la **DataTable**, el valor **original** o cada columna se establece en el contenido de la fila coincidente del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="2c6ad-108">For example, **PreserveCurrentValues** (the default) specifies that in cases where a row is marked as **Added** in the **DataTable**, the **Original** value or each column is set to the contents of the matching row from the data source.</span></span> <span data-ttu-id="2c6ad-109">El valor **actual** conservará los valores asignados al agregar la fila y el **RowState** de la fila se establecerá en **cambiado**.</span><span class="sxs-lookup"><span data-stu-id="2c6ad-109">The **Current** value will retain the values assigned when the row was added, and the **RowState** of the row will be set to **Changed**.</span></span>  
  
 <span data-ttu-id="2c6ad-110">En la siguiente tabla se ofrece una breve descripción de los valores de enumeración <xref:System.Data.LoadOption>.</span><span class="sxs-lookup"><span data-stu-id="2c6ad-110">The following table gives a short description of the <xref:System.Data.LoadOption> enumeration values.</span></span>  
  
|<span data-ttu-id="2c6ad-111">Valor LoadOption</span><span class="sxs-lookup"><span data-stu-id="2c6ad-111">LoadOption value</span></span>|<span data-ttu-id="2c6ad-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2c6ad-112">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="2c6ad-113">**OverwriteRow**</span><span class="sxs-lookup"><span data-stu-id="2c6ad-113">**OverwriteRow**</span></span>|<span data-ttu-id="2c6ad-114">Si las filas entrantes tienen el mismo valor **PrimaryKey** que una fila ya existente en la **DataTable**, los valores **originales** y **actuales** de cada columna se reemplazan por los valores de la fila entrante y la propiedad **RowState** está establecida en **Sin cambios**.</span><span class="sxs-lookup"><span data-stu-id="2c6ad-114">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** and **Current** values of each column are replaced with the values in the incoming row, and the **RowState** property is set to **Unchanged**.</span></span><br /><br /> <span data-ttu-id="2c6ad-115">Las filas del origen de datos que aún no existen en la **DataTable** se agregan con un valor **RowState** de Unchanged.</span><span class="sxs-lookup"><span data-stu-id="2c6ad-115">Rows from the data source that do not already exist in the **DataTable** are added with a **RowState** value of **Unchanged**.</span></span><br /><br /> <span data-ttu-id="2c6ad-116">Esta opción en efecto actualiza el contenido de la **DataTable** para que coincida con el contenido del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="2c6ad-116">This option in effect refreshes the contents of the **DataTable** so that it matches the contents of the data source.</span></span>|  
|<span data-ttu-id="2c6ad-117">**PreserveCurrentValues (valor predeterminado)**</span><span class="sxs-lookup"><span data-stu-id="2c6ad-117">**PreserveCurrentValues (default)**</span></span>|<span data-ttu-id="2c6ad-118">Si las filas entrantes tienen el mismo valor **PrimaryKey** que una fila ya existente en la **DataTable**, el valor **original** se establece en el contenido de la fila entrante y no se cambia el valor **actual** .</span><span class="sxs-lookup"><span data-stu-id="2c6ad-118">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** value is set to the contents of the incoming row, and the **Current** value is not changed.</span></span><br /><br /> <span data-ttu-id="2c6ad-119">Si el **RowState** se **agrega** o se **modifica**, se establece en **Modified**.</span><span class="sxs-lookup"><span data-stu-id="2c6ad-119">If the **RowState** is **Added** or **Modified**, it is set to **Modified**.</span></span><br /><br /> <span data-ttu-id="2c6ad-120">Si se eliminóel **RowState** , permanecerá **eliminado**.</span><span class="sxs-lookup"><span data-stu-id="2c6ad-120">If the **RowState** was **Deleted**, it remains **Deleted**.</span></span><br /><br /> <span data-ttu-id="2c6ad-121">Las filas del origen de datos que aún no existen en la **DataTable** se agregan y el **RowState** se establece enUnchanged.</span><span class="sxs-lookup"><span data-stu-id="2c6ad-121">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Unchanged**.</span></span>|  
|<span data-ttu-id="2c6ad-122">**UpdateCurrentValues**</span><span class="sxs-lookup"><span data-stu-id="2c6ad-122">**UpdateCurrentValues**</span></span>|<span data-ttu-id="2c6ad-123">Si las filas entrantes tienen el mismo valor **PrimaryKey** que la fila que ya está en la **DataTable**, el valor **actual** se copia en el valor **original** y el valor **actual** se establece en el contenido de la fila entrante.</span><span class="sxs-lookup"><span data-stu-id="2c6ad-123">If incoming rows have the same **PrimaryKey** value as the row already in the **DataTable**, the **Current** value is copied to the **Original** value, and the **Current** value is then set to the contents of the incoming row.</span></span><br /><br /> <span data-ttu-id="2c6ad-124">Si se **agregó**el **RowState** en la **DataTable** , el **RowState** permanece **agregado**.</span><span class="sxs-lookup"><span data-stu-id="2c6ad-124">If the **RowState** in the **DataTable** was **Added**, the **RowState** remains **Added**.</span></span> <span data-ttu-id="2c6ad-125">En el caso de las filas marcadas como modificadas o **eliminadas**, se **modifica**el **RowState** .</span><span class="sxs-lookup"><span data-stu-id="2c6ad-125">For rows marked as **Modified** or **Deleted**, the **RowState** is **Modified**.</span></span><br /><br /> <span data-ttu-id="2c6ad-126">Las filas del origen de datos que aún no existen en la **DataTable** se agregan y el **RowState** se establece en **Added**.</span><span class="sxs-lookup"><span data-stu-id="2c6ad-126">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Added**.</span></span>|  
  
 <span data-ttu-id="2c6ad-127">En el ejemplo siguiente se usa el método **Load** para mostrar una lista de cumpleaños para los empleados de la base de datos **Northwind** .</span><span class="sxs-lookup"><span data-stu-id="2c6ad-127">The following sample uses the **Load** method to display a list of birthdays for the employees in the **Northwind** database.</span></span>  
  
```vb  
Private Sub LoadBirthdays(ByVal connectionString As String)  
    ' Assumes that connectionString is a valid connection string  
    ' to the Northwind database on SQL Server.  
    Dim queryString As String = _  
    "SELECT LastName, FirstName, BirthDate " & _  
      " FROM dbo.Employees " & _  
      "ORDER BY BirthDate, LastName, FirstName"  
  
    ' Open and fill a DataSet.   
    Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
        queryString, connectionString)  
    Dim employees As New DataSet  
    adapter.Fill(employees, "Employees")  
  
    ' Create a SqlDataReader for use with the Load Method.  
    Dim reader As DataTableReader = employees.GetDataReader()  
  
    ' Create an instance of DataTable and assign the first  
    ' DataTable in the DataSet.Tables collection to it.  
    Dim dataTableEmp As DataTable = employees.Tables(0)  
  
    ' Fill the DataTable with data by calling Load and  
    ' passing the SqlDataReader.  
    dataTableEmp.Load(reader, LoadOption.OverwriteRow)  
  
    ' Loop through the rows collection and display the values  
    ' in the console window.  
    Dim employeeRow As DataRow  
    For Each employeeRow In dataTableEmp.Rows  
        Console.WriteLine("{0:MM\\dd\\yyyy}" & ControlChars.Tab & _  
          "{1}, {2}", _  
          employeeRow("BirthDate"), _  
          employeeRow("LastName"), _  
          employeeRow("FirstName"))  
    Next employeeRow  
  
    ' Keep the window opened to view the contents.  
    Console.ReadLine()  
End Sub  
```  
  
## <a name="see-also"></a><span data-ttu-id="2c6ad-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c6ad-128">See also</span></span>

- [<span data-ttu-id="2c6ad-129">Manipulación de datos en un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="2c6ad-129">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="2c6ad-130">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="2c6ad-130">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
