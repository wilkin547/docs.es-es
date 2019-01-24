---
title: El método de carga
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
ms.openlocfilehash: 06666e069f20bc06f303c4e829d1c69c185a8a84
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54602486"
---
# <a name="the-load-method"></a><span data-ttu-id="c7456-102">El método de carga</span><span class="sxs-lookup"><span data-stu-id="c7456-102">The Load Method</span></span>
<span data-ttu-id="c7456-103">Se puede utilizar el método <xref:System.Data.DataTable.Load%2A> para cargar una <xref:System.Data.DataTable> con filas desde un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="c7456-103">You can use the <xref:System.Data.DataTable.Load%2A> method to load a <xref:System.Data.DataTable> with rows from a data source.</span></span> <span data-ttu-id="c7456-104">Se trata de un método sobrecargado que, en su forma más sencilla, acepta un único parámetro, un **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="c7456-104">This is an overloaded method which, in its simplest form, accepts a single parameter, a **DataReader**.</span></span> <span data-ttu-id="c7456-105">En este formulario, simplemente se cargan los **DataTable** con filas.</span><span class="sxs-lookup"><span data-stu-id="c7456-105">In this form, it simply loads the **DataTable** with rows.</span></span> <span data-ttu-id="c7456-106">Opcionalmente, puede especificar el **LoadOption** parámetro para controlar cómo se agregan datos a la **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="c7456-106">Optionally, you can specify the **LoadOption** parameter to control how data is added to the **DataTable**.</span></span>  
  
 <span data-ttu-id="c7456-107">El **LoadOption** parámetro es especialmente útil en casos donde el **DataTable** ya contiene filas de datos, porque describe los datos entrantes del origen de datos se combinarán con los datos ya está en la tabla.</span><span class="sxs-lookup"><span data-stu-id="c7456-107">The **LoadOption** parameter is particularly useful in cases where the **DataTable** already contains rows of data, because it describes how incoming data from the data source will be combined with the data already in the table.</span></span> <span data-ttu-id="c7456-108">Por ejemplo, **PreserveCurrentValues** (valor predeterminado) especifica que en los casos donde una fila está marcada como **Added** en el **DataTable**, el **Original** cada columna o valor se establece en el contenido de la fila coincidente del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="c7456-108">For example, **PreserveCurrentValues** (the default) specifies that in cases where a row is marked as **Added** in the **DataTable**, the **Original** value or each column is set to the contents of the matching row from the data source.</span></span> <span data-ttu-id="c7456-109">El **actual** valor conservará los valores asignados cuando se agregó la fila y el **RowState** de la fila se establecerá en **Changed**.</span><span class="sxs-lookup"><span data-stu-id="c7456-109">The **Current** value will retain the values assigned when the row was added, and the **RowState** of the row will be set to **Changed**.</span></span>  
  
 <span data-ttu-id="c7456-110">En la siguiente tabla se ofrece una breve descripción de los valores de enumeración <xref:System.Data.LoadOption>.</span><span class="sxs-lookup"><span data-stu-id="c7456-110">The following table gives a short description of the <xref:System.Data.LoadOption> enumeration values.</span></span>  
  
|<span data-ttu-id="c7456-111">Valor LoadOption</span><span class="sxs-lookup"><span data-stu-id="c7456-111">LoadOption value</span></span>|<span data-ttu-id="c7456-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="c7456-112">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="c7456-113">**OverwriteRow**</span><span class="sxs-lookup"><span data-stu-id="c7456-113">**OverwriteRow**</span></span>|<span data-ttu-id="c7456-114">Si las filas entrantes tienen el mismo **PrimaryKey** valor como una fila ya existente en el **DataTable**, **Original** y **actual** valores de cada uno columna se reemplazan por los valores de la fila entrante y el **RowState** propiedad está establecida en **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="c7456-114">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** and **Current** values of each column are replaced with the values in the incoming row, and the **RowState** property is set to **Unchanged**.</span></span><br /><br /> <span data-ttu-id="c7456-115">Las filas del origen de datos que aún no existen en el **DataTable** se agregan con un **RowState** valor **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="c7456-115">Rows from the data source that do not already exist in the **DataTable** are added with a **RowState** value of **Unchanged**.</span></span><br /><br /> <span data-ttu-id="c7456-116">Esta opción activa actualiza el contenido de la **DataTable** para que coincida con el contenido del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="c7456-116">This option in effect refreshes the contents of the **DataTable** so that it matches the contents of the data source.</span></span>|  
|<span data-ttu-id="c7456-117">**PreserveCurrentValues (default)**</span><span class="sxs-lookup"><span data-stu-id="c7456-117">**PreserveCurrentValues (default)**</span></span>|<span data-ttu-id="c7456-118">Si las filas entrantes tienen el mismo **PrimaryKey** valor como una fila ya existente en el **DataTable**, **Original** valor se establece en el contenido de la fila entrante y la **Actual** no se cambia el valor.</span><span class="sxs-lookup"><span data-stu-id="c7456-118">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** value is set to the contents of the incoming row, and the **Current** value is not changed.</span></span><br /><br /> <span data-ttu-id="c7456-119">Si el **RowState** es **Added** o **Modified**, se establece en **Modified**.</span><span class="sxs-lookup"><span data-stu-id="c7456-119">If the **RowState** is **Added** or **Modified**, it is set to **Modified**.</span></span><br /><br /> <span data-ttu-id="c7456-120">Si el **RowState** era **Deleted**, permanece **Deleted**.</span><span class="sxs-lookup"><span data-stu-id="c7456-120">If the **RowState** was **Deleted**, it remains **Deleted**.</span></span><br /><br /> <span data-ttu-id="c7456-121">Las filas del origen de datos que aún no existen en el **DataTable** se agregan y el **RowState** está establecido en **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="c7456-121">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Unchanged**.</span></span>|  
|<span data-ttu-id="c7456-122">**UpdateCurrentValues**</span><span class="sxs-lookup"><span data-stu-id="c7456-122">**UpdateCurrentValues**</span></span>|<span data-ttu-id="c7456-123">Si las filas entrantes tienen el mismo **PrimaryKey** valor como la fila existente en el **DataTable**, **actual** valor se copia en el **Original**valor y el **actual** , a continuación, se establece el valor en el contenido de la fila entrante.</span><span class="sxs-lookup"><span data-stu-id="c7456-123">If incoming rows have the same **PrimaryKey** value as the row already in the **DataTable**, the **Current** value is copied to the **Original** value, and the **Current** value is then set to the contents of the incoming row.</span></span><br /><br /> <span data-ttu-id="c7456-124">Si el **RowState** en el **DataTable** era **Added**, **RowState** permanece **Added**.</span><span class="sxs-lookup"><span data-stu-id="c7456-124">If the **RowState** in the **DataTable** was **Added**, the **RowState** remains **Added**.</span></span> <span data-ttu-id="c7456-125">Las filas marcadas como **Modified** o **Deleted**, **RowState** es **Modified**.</span><span class="sxs-lookup"><span data-stu-id="c7456-125">For rows marked as **Modified** or **Deleted**, the **RowState** is **Modified**.</span></span><br /><br /> <span data-ttu-id="c7456-126">Las filas del origen de datos que aún no existen en el **DataTable** se agregan y el **RowState** está establecido en **Added**.</span><span class="sxs-lookup"><span data-stu-id="c7456-126">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Added**.</span></span>|  
  
 <span data-ttu-id="c7456-127">El ejemplo siguiente usa el **carga** método para mostrar una lista de cumpleaños de los empleados de la **Northwind** base de datos.</span><span class="sxs-lookup"><span data-stu-id="c7456-127">The following sample uses the **Load** method to display a list of birthdays for the employees in the **Northwind** database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c7456-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7456-128">See also</span></span>
- [<span data-ttu-id="c7456-129">Manipulación de datos en un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="c7456-129">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="c7456-130">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="c7456-130">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
