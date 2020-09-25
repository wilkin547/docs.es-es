---
title: El método de carga
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
ms.openlocfilehash: ea437d1f8ed567934acafbd8db1f8dba8eb22bcc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177545"
---
# <a name="the-load-method"></a><span data-ttu-id="f07ab-102">El método de carga</span><span class="sxs-lookup"><span data-stu-id="f07ab-102">The Load Method</span></span>

<span data-ttu-id="f07ab-103">Se puede utilizar el método <xref:System.Data.DataTable.Load%2A> para cargar una <xref:System.Data.DataTable> con filas desde un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="f07ab-103">You can use the <xref:System.Data.DataTable.Load%2A> method to load a <xref:System.Data.DataTable> with rows from a data source.</span></span> <span data-ttu-id="f07ab-104">Se trata de un método sobrecargado que, en su forma más simple, acepta un único parámetro, un **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="f07ab-104">This is an overloaded method which, in its simplest form, accepts a single parameter, a **DataReader**.</span></span> <span data-ttu-id="f07ab-105">En este formato, simplemente carga la **DataTable** con filas.</span><span class="sxs-lookup"><span data-stu-id="f07ab-105">In this form, it simply loads the **DataTable** with rows.</span></span> <span data-ttu-id="f07ab-106">Opcionalmente, puede especificar el parámetro **LoadOption** para controlar el modo en que se agregan los datos a la **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="f07ab-106">Optionally, you can specify the **LoadOption** parameter to control how data is added to the **DataTable**.</span></span>  
  
 <span data-ttu-id="f07ab-107">El parámetro **LoadOption** es especialmente útil en los casos en los que **DataTable** ya contiene filas de datos, ya que describe cómo se combinarán los datos entrantes del origen de datos con los datos que ya están en la tabla.</span><span class="sxs-lookup"><span data-stu-id="f07ab-107">The **LoadOption** parameter is particularly useful in cases where the **DataTable** already contains rows of data, because it describes how incoming data from the data source will be combined with the data already in the table.</span></span> <span data-ttu-id="f07ab-108">Por ejemplo, **PreserveCurrentValues** (valor predeterminado) especifica que en los casos en los que una fila se marca como **agregada** en la **DataTable**, el valor **original** o cada columna se establece en el contenido de la fila coincidente del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="f07ab-108">For example, **PreserveCurrentValues** (the default) specifies that in cases where a row is marked as **Added** in the **DataTable**, the **Original** value or each column is set to the contents of the matching row from the data source.</span></span> <span data-ttu-id="f07ab-109">El valor **actual** conservará los valores asignados al agregar la fila y el **RowState** de la fila se establecerá en **cambiado**.</span><span class="sxs-lookup"><span data-stu-id="f07ab-109">The **Current** value will retain the values assigned when the row was added, and the **RowState** of the row will be set to **Changed**.</span></span>  
  
 <span data-ttu-id="f07ab-110">En la siguiente tabla se ofrece una breve descripción de los valores de enumeración <xref:System.Data.LoadOption>.</span><span class="sxs-lookup"><span data-stu-id="f07ab-110">The following table gives a short description of the <xref:System.Data.LoadOption> enumeration values.</span></span>  
  
|<span data-ttu-id="f07ab-111">Valor LoadOption</span><span class="sxs-lookup"><span data-stu-id="f07ab-111">LoadOption value</span></span>|<span data-ttu-id="f07ab-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f07ab-112">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="f07ab-113">**OverwriteRow**</span><span class="sxs-lookup"><span data-stu-id="f07ab-113">**OverwriteRow**</span></span>|<span data-ttu-id="f07ab-114">Si las filas entrantes tienen el mismo valor **PrimaryKey** que una fila ya existente en la **DataTable**, los valores **originales** y **actuales** de cada columna se reemplazan por los valores de la fila entrante y la propiedad **RowState** se establece en **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="f07ab-114">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** and **Current** values of each column are replaced with the values in the incoming row, and the **RowState** property is set to **Unchanged**.</span></span><br /><br /> <span data-ttu-id="f07ab-115">Las filas del origen de datos que aún no existen en la **DataTable** se agregan con un valor **RowState** de **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="f07ab-115">Rows from the data source that do not already exist in the **DataTable** are added with a **RowState** value of **Unchanged**.</span></span><br /><br /> <span data-ttu-id="f07ab-116">Esta opción en efecto actualiza el contenido de la **DataTable** para que coincida con el contenido del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="f07ab-116">This option in effect refreshes the contents of the **DataTable** so that it matches the contents of the data source.</span></span>|  
|<span data-ttu-id="f07ab-117">**PreserveCurrentValues (predeterminado)**</span><span class="sxs-lookup"><span data-stu-id="f07ab-117">**PreserveCurrentValues (default)**</span></span>|<span data-ttu-id="f07ab-118">Si las filas entrantes tienen el mismo valor **PrimaryKey** que una fila ya existente en la **DataTable**, el valor **original** se establece en el contenido de la fila entrante y no se cambia el valor **actual** .</span><span class="sxs-lookup"><span data-stu-id="f07ab-118">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** value is set to the contents of the incoming row, and the **Current** value is not changed.</span></span><br /><br /> <span data-ttu-id="f07ab-119">Si el **RowState** se **agrega** o se **modifica**, se establece en **Modified**.</span><span class="sxs-lookup"><span data-stu-id="f07ab-119">If the **RowState** is **Added** or **Modified**, it is set to **Modified**.</span></span><br /><br /> <span data-ttu-id="f07ab-120">Si se **eliminó**el **RowState** , permanecerá **eliminado**.</span><span class="sxs-lookup"><span data-stu-id="f07ab-120">If the **RowState** was **Deleted**, it remains **Deleted**.</span></span><br /><br /> <span data-ttu-id="f07ab-121">Las filas del origen de datos que aún no existen en la **DataTable** se agregan y el **RowState** se establece en **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="f07ab-121">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Unchanged**.</span></span>|  
|<span data-ttu-id="f07ab-122">**UpdateCurrentValues**</span><span class="sxs-lookup"><span data-stu-id="f07ab-122">**UpdateCurrentValues**</span></span>|<span data-ttu-id="f07ab-123">Si las filas entrantes tienen el mismo valor **PrimaryKey** que la fila que ya está en la **DataTable**, el valor **actual** se copia en el valor **original** y el valor **actual** se establece en el contenido de la fila entrante.</span><span class="sxs-lookup"><span data-stu-id="f07ab-123">If incoming rows have the same **PrimaryKey** value as the row already in the **DataTable**, the **Current** value is copied to the **Original** value, and the **Current** value is then set to the contents of the incoming row.</span></span><br /><br /> <span data-ttu-id="f07ab-124">Si se **agregó**el **RowState** en la **DataTable** , el **RowState** permanece **agregado**.</span><span class="sxs-lookup"><span data-stu-id="f07ab-124">If the **RowState** in the **DataTable** was **Added**, the **RowState** remains **Added**.</span></span> <span data-ttu-id="f07ab-125">En el caso de las filas marcadas como **modificadas** o **eliminadas**, se **modifica**el **RowState** .</span><span class="sxs-lookup"><span data-stu-id="f07ab-125">For rows marked as **Modified** or **Deleted**, the **RowState** is **Modified**.</span></span><br /><br /> <span data-ttu-id="f07ab-126">Las filas del origen de datos que aún no existen en la **DataTable** se agregan y el **RowState** se establece en **Added**.</span><span class="sxs-lookup"><span data-stu-id="f07ab-126">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Added**.</span></span>|  
  
 <span data-ttu-id="f07ab-127">En el ejemplo siguiente se usa el método **Load** para mostrar una lista de cumpleaños para los empleados de la base de datos **Northwind** .</span><span class="sxs-lookup"><span data-stu-id="f07ab-127">The following sample uses the **Load** method to display a list of birthdays for the employees in the **Northwind** database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f07ab-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f07ab-128">See also</span></span>

- [<span data-ttu-id="f07ab-129">Manipular datos en un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="f07ab-129">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="f07ab-130">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f07ab-130">ADO.NET Overview</span></span>](../ado-net-overview.md)
