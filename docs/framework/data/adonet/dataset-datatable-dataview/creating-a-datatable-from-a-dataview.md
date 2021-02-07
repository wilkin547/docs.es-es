---
description: Más información acerca de cómo crear un objeto DataTable a partir de una DataView
title: Crear un objeto DataTable a partir de un objeto DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2d45cf41-d8ae-4409-af3e-a96a7e476d85
ms.openlocfilehash: 2cd1b4520cfcbeb626eea06ae2d87208339dae9a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725058"
---
# <a name="creating-a-datatable-from-a-dataview"></a><span data-ttu-id="081d4-103">Crear un objeto DataTable a partir de un objeto DataView</span><span class="sxs-lookup"><span data-stu-id="081d4-103">Creating a DataTable from a DataView</span></span>

<span data-ttu-id="081d4-104">Después de recuperar datos de un origen de datos y rellenar una <xref:System.Data.DataTable> con los mismos, puede ordenarlos, filtrarlos o limitar los datos devueltos sin volver a recuperarlos.</span><span class="sxs-lookup"><span data-stu-id="081d4-104">Once you have retrieved data from a data source, and have filled a <xref:System.Data.DataTable> with the data, you may want to sort, filter, or otherwise limit the returned data without retrieving it again.</span></span> <span data-ttu-id="081d4-105">Esto es posible gracias a la clase <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="081d4-105">The <xref:System.Data.DataView> class makes this possible.</span></span> <span data-ttu-id="081d4-106">Además, si necesita crear un nuevo a partir de <xref:System.Data.DataTable> <xref:System.Data.DataView> , puede utilizar el <xref:System.Data.DataView.ToTable%2A> método para copiar todas las filas y columnas, o un subconjunto de los datos en un nuevo <xref:System.Data.DataTable> .</span><span class="sxs-lookup"><span data-stu-id="081d4-106">In addition, if you need to create a new <xref:System.Data.DataTable> from the <xref:System.Data.DataView>, you can use the <xref:System.Data.DataView.ToTable%2A> method to copy all the rows and columns, or a subset of the data into a new <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="081d4-107">El método <xref:System.Data.DataView.ToTable%2A> proporciona sobrecargas para:</span><span class="sxs-lookup"><span data-stu-id="081d4-107">The <xref:System.Data.DataView.ToTable%2A> method provides overloads to:</span></span>  
  
- <span data-ttu-id="081d4-108">Crear una <xref:System.Data.DataTable> que contenga columnas que son un subconjunto de las columnas de la <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="081d4-108">Create a <xref:System.Data.DataTable> containing columns that are a subset of the columns in the <xref:System.Data.DataView>.</span></span>  
  
- <span data-ttu-id="081d4-109">Cree un <xref:System.Data.DataTable> que incluya solo filas distintas de, de forma <xref:System.Data.DataView> análoga a la palabra clave DISTINCT en TRANSACT-SQL.</span><span class="sxs-lookup"><span data-stu-id="081d4-109">Create a <xref:System.Data.DataTable> that includes only distinct rows from the <xref:System.Data.DataView>, analogously to the DISTINCT keyword in Transact-SQL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="081d4-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="081d4-110">Example</span></span>  

 <span data-ttu-id="081d4-111">En el siguiente ejemplo de aplicación de consola se crea un <xref:System.Data.DataTable> que contiene datos de la tabla **Person. contact** en la base de datos de ejemplo **AdventureWorks** .</span><span class="sxs-lookup"><span data-stu-id="081d4-111">The following console application example creates a <xref:System.Data.DataTable> that contains data from the **Person.Contact** table in the **AdventureWorks** sample database.</span></span> <span data-ttu-id="081d4-112">Después, en el ejemplo se crea una ordenada y filtrada <xref:System.Data.DataView> en función de <xref:System.Data.DataTable> .</span><span class="sxs-lookup"><span data-stu-id="081d4-112">Next, the example creates a sorted and filtered <xref:System.Data.DataView> based on the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="081d4-113">Después de mostrar el contenido de <xref:System.Data.DataTable> y <xref:System.Data.DataView> , en el ejemplo se crea un nuevo <xref:System.Data.DataTable> a partir de llamando <xref:System.Data.DataView> al <xref:System.Data.DataView.ToTable%2A> método, seleccionando solo un subconjunto de las columnas disponibles.</span><span class="sxs-lookup"><span data-stu-id="081d4-113">After displaying the contents of the <xref:System.Data.DataTable> and the <xref:System.Data.DataView>, the example creates a new <xref:System.Data.DataTable> from the <xref:System.Data.DataView> by calling the <xref:System.Data.DataView.ToTable%2A> method, selecting only a subset of the available columns.</span></span> <span data-ttu-id="081d4-114">Por último, se muestra el contenido de la <xref:System.Data.DataTable> nueva.</span><span class="sxs-lookup"><span data-stu-id="081d4-114">Finally, the example displays the contents of the new <xref:System.Data.DataTable>.</span></span>  
  
```vb  
Private Sub DemonstrateDataView()  
    ' Retrieve a DataTable from the AdventureWorks sample database.  
    ' connectionString is assumed to be a valid connection string.  
    Dim adapter As New SqlDataAdapter( _  
       "SELECT FirstName, LastName, EmailAddress FROM Person.Contact WHERE FirstName LIKE 'Mich%'", connectionString)  
    Dim table As New DataTable  
  
    adapter.Fill(table)  
    Console.WriteLine("Original table name: " & table.TableName)  
    ' Print current table values.  
    PrintTableOrView(table, "Current Values in Table")  
  
    ' Now create a DataView based on the DataTable.  
    ' Sort and filter the data.  
    Dim view As DataView = table.DefaultView  
    view.Sort = "LastName, FirstName"  
    view.RowFilter = "LastName > 'M'"  
    PrintTableOrView(view, "Current Values in View")  
  
    ' Create a new DataTable based on the DataView,  
    ' requesting only two columns with distinct values  
    ' in the columns.  
    Dim newTable As DataTable = view.ToTable("UniqueLastNames", True, "FirstName", "LastName")  
    PrintTableOrView(newTable, "Table created from DataView")  
    Console.WriteLine("New table name: " & newTable.TableName)  
  
    Console.WriteLine("Press any key to continue.")  
    Console.ReadKey()  
    End Sub  
  
Private Sub PrintTableOrView(ByVal dv As DataView, ByVal label As String)  
    Dim sw As System.IO.StringWriter  
    Dim output As String  
    Dim table As DataTable = dv.Table  
  
    Console.WriteLine(label)  
  
    ' Loop through each row in the view.  
    For Each rowView As DataRowView In dv  
        sw = New System.IO.StringWriter  
  
        ' Loop through each column.  
        For Each col As DataColumn In table.Columns  
            ' Output the value of each column's data.  
            sw.Write(rowView(col.ColumnName).ToString() & ", ")  
        Next  
        output = sw.ToString  
        ' Trim off the trailing ", ", so the output looks correct.  
        If output.Length > 2 Then  
            output = output.Substring(0, output.Length - 2)  
        End If  
        ' Display the row in the console window.  
        Console.WriteLine(output)  
    Next  
    Console.WriteLine()  
End Sub  
  
Private Sub PrintTableOrView(ByVal table As DataTable, ByVal label As String)  
    Dim sw As System.IO.StringWriter  
    Dim output As String  
  
    Console.WriteLine(label)  
  
    ' Loop through each row in the table.  
    For Each row As DataRow In table.Rows  
        sw = New System.IO.StringWriter  
        ' Loop through each column.  
        For Each col As DataColumn In table.Columns  
            ' Output the value of each column's data.  
            sw.Write(row(col).ToString() & ", ")  
        Next  
        output = sw.ToString  
        ' Trim off the trailing ", ", so the output looks correct.  
        If output.Length > 2 Then  
            output = output.Substring(0, output.Length - 2)  
        End If  
        ' Display the row in the console window.  
        Console.WriteLine(output)  
    Next  
    Console.WriteLine()  
    End Sub  
End Module  
```  
  
```csharp  
private static void DemonstrateDataView()  
{  
// Retrieve a DataTable from the AdventureWorks sample database.  
// connectionString is assumed to be a valid connection string.  
SqlDataAdapter adapter = new SqlDataAdapter(  
    "SELECT FirstName, LastName, EmailAddress " +  
    "FROM Person.Contact WHERE FirstName LIKE 'Mich%'",
       GetConnectionString());  
DataTable table = new DataTable();  
  
adapter.Fill(table);  
Console.WriteLine("Original table name: " + table.TableName);  
// Print current table values.  
PrintTableOrView(table, "Current Values in Table");  
  
// Now create a DataView based on the DataTable.  
// Sort and filter the data.  
DataView view = table.DefaultView;  
view.Sort = "LastName, FirstName";  
view.RowFilter = "LastName > 'M'";  
PrintTableOrView(view, "Current Values in View");  
  
// Create a new DataTable based on the DataView,  
// requesting only two columns with distinct values  
// in the columns.  
DataTable newTable = view.ToTable("UniqueLastNames",  
     true, "FirstName", "LastName");  
PrintTableOrView(newTable, "Table created from DataView");  
Console.WriteLine("New table name: " + newTable.TableName);  
  
Console.WriteLine("Press any key to continue.");  
Console.ReadKey();  
}  
  
private static void PrintTableOrView(DataView dv, string label)  
{  
System.IO.StringWriter sw;  
string output;  
DataTable table = dv.Table;  
  
Console.WriteLine(label);  
  
// Loop through each row in the view.  
foreach (DataRowView rowView in dv)  
{  
    sw = new System.IO.StringWriter();  
  
    // Loop through each column.  
    foreach (DataColumn col in table.Columns)  
    {  
        // Output the value of each column's data.  
        sw.Write(rowView[col.ColumnName].ToString() + ", ");  
    }  
    output = sw.ToString();  
    // Trim off the trailing ", ", so the output looks correct.  
    if (output.Length > 2)  
    {  
        output = output.Substring(0, output.Length - 2);  
    }  
    // Display the row in the console window.  
    Console.WriteLine(output);  
}  
Console.WriteLine();  
}  
  
private static void PrintTableOrView(DataTable table, string label)  
{  
System.IO.StringWriter sw;  
string output;  
  
Console.WriteLine(label);  
  
// Loop through each row in the table.  
foreach (DataRow row in table.Rows)  
{  
    sw = new System.IO.StringWriter();  
    // Loop through each column.  
    foreach (DataColumn col in table.Columns)  
    {  
        // Output the value of each column's data.  
        sw.Write(row[col].ToString() + ", ");  
    }  
    output = sw.ToString();  
    // Trim off the trailing ", ", so the output looks correct.  
    if (output.Length > 2)  
    {  
        output = output.Substring(0, output.Length - 2);  
    }  
    // Display the row in the console window.  
    Console.WriteLine(output);  
} //  
Console.WriteLine();  
}  
```  
  
 <span data-ttu-id="081d4-115">}</span><span class="sxs-lookup"><span data-stu-id="081d4-115">}</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="081d4-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="081d4-116">See also</span></span>

- <xref:System.Data.DataView.ToTable%2A>
- [<span data-ttu-id="081d4-117">Objetos DataView</span><span class="sxs-lookup"><span data-stu-id="081d4-117">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="081d4-118">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="081d4-118">ADO.NET Overview</span></span>](../ado-net-overview.md)
