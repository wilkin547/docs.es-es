---
title: "El método de carga"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: a54eda8d96468d4506a5f7dafc342fa5ff128c2a
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="the-load-method"></a><span data-ttu-id="3d93b-102">El método de carga</span><span class="sxs-lookup"><span data-stu-id="3d93b-102">The Load Method</span></span>
<span data-ttu-id="3d93b-103">Se puede utilizar el método <xref:System.Data.DataTable.Load%2A> para cargar una <xref:System.Data.DataTable> con filas desde un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="3d93b-103">You can use the <xref:System.Data.DataTable.Load%2A> method to load a <xref:System.Data.DataTable> with rows from a data source.</span></span> <span data-ttu-id="3d93b-104">Se trata de un método sobrecargado que, en su forma más sencilla, acepta un único parámetro, un **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="3d93b-104">This is an overloaded method which, in its simplest form, accepts a single parameter, a **DataReader**.</span></span> <span data-ttu-id="3d93b-105">En este formulario, simplemente se cargan los **DataTable** con filas.</span><span class="sxs-lookup"><span data-stu-id="3d93b-105">In this form, it simply loads the **DataTable** with rows.</span></span> <span data-ttu-id="3d93b-106">Si lo desea, puede especificar el **LoadOption** parámetro para controlar cómo se agregan datos a la **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="3d93b-106">Optionally, you can specify the **LoadOption** parameter to control how data is added to the **DataTable**.</span></span>  
  
 <span data-ttu-id="3d93b-107">El **LoadOption** parámetro es especialmente útil en casos donde la **DataTable** ya contiene filas de datos, porque describe como datos del origen de datos se combinarán con los datos ya se encuentran en la tabla.</span><span class="sxs-lookup"><span data-stu-id="3d93b-107">The **LoadOption** parameter is particularly useful in cases where the **DataTable** already contains rows of data, because it describes how incoming data from the data source will be combined with the data already in the table.</span></span> <span data-ttu-id="3d93b-108">Por ejemplo, **PreserveCurrentValues** (valor predeterminado) especifica que en casos donde una fila está marcada como **Added** en el **DataTable**, el **Original** cada columna o valor se establece en el contenido de la fila coincidente del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="3d93b-108">For example, **PreserveCurrentValues** (the default) specifies that in cases where a row is marked as **Added** in the **DataTable**, the **Original** value or each column is set to the contents of the matching row from the data source.</span></span> <span data-ttu-id="3d93b-109">El **actual** valor conservarán los valores asignados cuando se agregó la fila y el **RowState** de la fila se establecerá en **Changed**.</span><span class="sxs-lookup"><span data-stu-id="3d93b-109">The **Current** value will retain the values assigned when the row was added, and the **RowState** of the row will be set to **Changed**.</span></span>  
  
 <span data-ttu-id="3d93b-110">En la siguiente tabla se ofrece una breve descripción de los valores de enumeración <xref:System.Data.LoadOption>.</span><span class="sxs-lookup"><span data-stu-id="3d93b-110">The following table gives a short description of the <xref:System.Data.LoadOption> enumeration values.</span></span>  
  
|<span data-ttu-id="3d93b-111">Valor LoadOption</span><span class="sxs-lookup"><span data-stu-id="3d93b-111">LoadOption value</span></span>|<span data-ttu-id="3d93b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="3d93b-112">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="3d93b-113">**OverwriteRow**</span><span class="sxs-lookup"><span data-stu-id="3d93b-113">**OverwriteRow**</span></span>|<span data-ttu-id="3d93b-114">Si las filas entrantes tienen el mismo **PrimaryKey** valor como una fila ya existente en el **DataTable**, **Original** y **actual** valores de cada uno columna se reemplazan por los valores de la fila entrante y el **RowState** propiedad está establecida en **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="3d93b-114">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** and **Current** values of each column are replaced with the values in the incoming row, and the **RowState** property is set to **Unchanged**.</span></span><br /><br /> <span data-ttu-id="3d93b-115">Filas del origen de datos que ya no existe en el **DataTable** se agregan con un **RowState** valo **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="3d93b-115">Rows from the data source that do not already exist in the **DataTable** are added with a **RowState** value of **Unchanged**.</span></span><br /><br /> <span data-ttu-id="3d93b-116">Esta opción activa actualiza el contenido de la **DataTable** para que coincida con el contenido del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="3d93b-116">This option in effect refreshes the contents of the **DataTable** so that it matches the contents of the data source.</span></span>|  
|<span data-ttu-id="3d93b-117">**PreserveCurrentValues (predeterminado)**</span><span class="sxs-lookup"><span data-stu-id="3d93b-117">**PreserveCurrentValues (default)**</span></span>|<span data-ttu-id="3d93b-118">Si las filas entrantes tienen el mismo **PrimaryKey** valor como una fila ya existente en el **DataTable**, **Original** valor se establece en el contenido de la fila entrante y la **Actual** no se cambia el valor.</span><span class="sxs-lookup"><span data-stu-id="3d93b-118">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** value is set to the contents of the incoming row, and the **Current** value is not changed.</span></span><br /><br /> <span data-ttu-id="3d93b-119">Si el **RowState** es **Added** o **Modified**, se establece en **Modified**.</span><span class="sxs-lookup"><span data-stu-id="3d93b-119">If the **RowState** is **Added** or **Modified**, it is set to **Modified**.</span></span><br /><br /> <span data-ttu-id="3d93b-120">Si el **RowState** era **Deleted**, permanece **Deleted**.</span><span class="sxs-lookup"><span data-stu-id="3d93b-120">If the **RowState** was **Deleted**, it remains **Deleted**.</span></span><br /><br /> <span data-ttu-id="3d93b-121">Filas del origen de datos que ya no existe en el **DataTable** se agregan y el **RowState** está establecido en **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="3d93b-121">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Unchanged**.</span></span>|  
|<span data-ttu-id="3d93b-122">**UpdateCurrentValues**</span><span class="sxs-lookup"><span data-stu-id="3d93b-122">**UpdateCurrentValues**</span></span>|<span data-ttu-id="3d93b-123">Si las filas entrantes tienen el mismo **PrimaryKey** valor como la fila ya existente en el **DataTable**, **actual** valor se copia en el **Original**valor y el **actual** , a continuación, se establece el valor en el contenido de la fila entrante.</span><span class="sxs-lookup"><span data-stu-id="3d93b-123">If incoming rows have the same **PrimaryKey** value as the row already in the **DataTable**, the **Current** value is copied to the **Original** value, and the **Current** value is then set to the contents of the incoming row.</span></span><br /><br /> <span data-ttu-id="3d93b-124">Si el **RowState** en el **DataTable** era **Added**, **RowState** permanece **Added**.</span><span class="sxs-lookup"><span data-stu-id="3d93b-124">If the **RowState** in the **DataTable** was **Added**, the **RowState** remains **Added**.</span></span> <span data-ttu-id="3d93b-125">Filas marcadas como **Modified** o **Deleted**, **RowState** es **Modified**.</span><span class="sxs-lookup"><span data-stu-id="3d93b-125">For rows marked as **Modified** or **Deleted**, the **RowState** is **Modified**.</span></span><br /><br /> <span data-ttu-id="3d93b-126">Filas del origen de datos que ya no existe en el **DataTable** se agregan y el **RowState** está establecido en **Added**.</span><span class="sxs-lookup"><span data-stu-id="3d93b-126">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Added**.</span></span>|  
  
 <span data-ttu-id="3d93b-127">El siguiente ejemplo se utiliza la **carga** método para mostrar una lista de cumpleaños de los empleados de la **Northwind** base de datos.</span><span class="sxs-lookup"><span data-stu-id="3d93b-127">The following sample uses the **Load** method to display a list of birthdays for the employees in the **Northwind** database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3d93b-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d93b-128">See Also</span></span>  
 [<span data-ttu-id="3d93b-129">Manipulación de datos en un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="3d93b-129">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [<span data-ttu-id="3d93b-130">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="3d93b-130">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
