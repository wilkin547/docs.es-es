---
title: Información de error de fila
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b1f9070-d032-48c7-b030-bd8fbb2ca59a
ms.openlocfilehash: 8673b7fbc2e4238f7047698376c53af991de9f1b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181172"
---
# <a name="row-error-information"></a><span data-ttu-id="fcd18-102">Información de error de fila</span><span class="sxs-lookup"><span data-stu-id="fcd18-102">Row Error Information</span></span>

<span data-ttu-id="fcd18-103">Para evitar responder a errores de fila durante la edición de valores en una <xref:System.Data.DataTable>, puede agregar la información de error a la fila para utilizarla más adelante.</span><span class="sxs-lookup"><span data-stu-id="fcd18-103">To avoid having to respond to row errors while editing values in a <xref:System.Data.DataTable>, you can add the error information to the row for later use.</span></span> <span data-ttu-id="fcd18-104">Para ello, el objeto <xref:System.Data.DataRow> proporciona una propiedad <xref:System.Data.DataRow.RowError%2A> en cada fila.</span><span class="sxs-lookup"><span data-stu-id="fcd18-104">The <xref:System.Data.DataRow> object provides a <xref:System.Data.DataRow.RowError%2A> property on each row for this purpose.</span></span> <span data-ttu-id="fcd18-105">Al agregar datos a la propiedad **RowError** de una **DataRow** , se establece la <xref:System.Data.DataRow.HasErrors%2A> propiedad de **DataRow** en **true**.</span><span class="sxs-lookup"><span data-stu-id="fcd18-105">Adding data to the **RowError** property of a **DataRow** sets the <xref:System.Data.DataRow.HasErrors%2A> property of the **DataRow** to **true**.</span></span> <span data-ttu-id="fcd18-106">Si **DataRow** es parte de un **DataTable**y **DataRow. hasErrors** es **true**, la propiedad **DataTable. hasErrors** también es **true**.</span><span class="sxs-lookup"><span data-stu-id="fcd18-106">If the **DataRow** is part of a **DataTable**, and **DataRow.HasErrors** is **true**, the **DataTable.HasErrors** property is also **true**.</span></span> <span data-ttu-id="fcd18-107">Esto se aplica también al **conjunto** de referencia al que pertenece la **DataTable** .</span><span class="sxs-lookup"><span data-stu-id="fcd18-107">This applies as well to the **DataSet** to which the **DataTable** belongs.</span></span> <span data-ttu-id="fcd18-108">Al probar errores, puede comprobar la propiedad **hasErrors** para determinar si se ha agregado información de error a alguna fila.</span><span class="sxs-lookup"><span data-stu-id="fcd18-108">When testing for errors, you can check the **HasErrors** property to determine if error information has been added to any rows.</span></span> <span data-ttu-id="fcd18-109">Si **hasErrors** es **true**, puede usar el <xref:System.Data.DataTable.GetErrors%2A> método de la **DataTable** para devolver y examinar únicamente las filas con errores, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="fcd18-109">If **HasErrors** is **true**, you can use the <xref:System.Data.DataTable.GetErrors%2A> method of the **DataTable** to return and examine only the rows with errors, as shown in the following example.</span></span>  
  
```vb  
Dim workTable As DataTable = New DataTable("Customers")  
workTable.Columns.Add("CustID", Type.GetType("System.Int32"))  
workTable.Columns.Add("Total", Type.GetType("System.Double"))  
  
AddHandler workTable.RowChanged, New DataRowChangeEventHandler(AddressOf OnRowChanged)  
  
Dim i  As Int32  
  
For i  = 0 To 10  
  workTable.Rows.Add(New Object() {i , i *100})  
Next  
  
If workTable.HasErrors Then  
  Console.WriteLine("Errors in Table " & workTable.TableName)  
  
  Dim myRow As DataRow  
  
  For Each myRow In workTable.GetErrors()  
    Console.WriteLine("CustID = " & myRow("CustID").ToString())  
    Console.WriteLine(" Error = " & myRow.RowError & vbCrLf)  
  Next  
End If  
  
Private Shared Sub OnRowChanged( _  
    sender As Object, args As DataRowChangeEventArgs)  
  ' Check for zero values.  
  If CDbl(args.Row("Total")) = 0 Then args.Row.RowError = _  
      "Total cannot be 0."  
End Sub  
```  
  
```csharp  
DataTable  workTable = new DataTable("Customers");  
workTable.Columns.Add("CustID", typeof(Int32));  
workTable.Columns.Add("Total", typeof(Double));  
  
workTable.RowChanged += new DataRowChangeEventHandler(OnRowChanged);  
  
for (int i = 0; i < 10; i++)  
  workTable.Rows.Add(new Object[] {i, i*100});  
  
if (workTable.HasErrors)  
{  
  Console.WriteLine("Errors in Table " + workTable.TableName);  
  
  foreach (DataRow myRow in workTable.GetErrors())  
  {  
    Console.WriteLine("CustID = " + myRow["CustID"]);  
    Console.WriteLine(" Error = " + myRow.RowError + "\n");  
  }  
}  
  
protected static void OnRowChanged(  
    Object sender, DataRowChangeEventArgs args)  
{  
  // Check for zero values.  
  if (args.Row["Total"].Equals(0D))  
    args.Row.RowError = "Total cannot be 0.";  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="fcd18-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fcd18-110">See also</span></span>

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataRow>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="fcd18-111">Manipular datos en un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="fcd18-111">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="fcd18-112">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="fcd18-112">ADO.NET Overview</span></span>](../ado-net-overview.md)
