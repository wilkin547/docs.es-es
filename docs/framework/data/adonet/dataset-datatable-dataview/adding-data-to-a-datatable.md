---
title: Agregar datos a un objeto DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d6aa8474-7bde-48f7-949d-20dc38a1625b
ms.openlocfilehash: 02d7f94259cc56513be404c5539ca7015d5f3533
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151538"
---
# <a name="adding-data-to-a-datatable"></a><span data-ttu-id="9883d-102">Agregar datos a un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="9883d-102">Adding Data to a DataTable</span></span>
<span data-ttu-id="9883d-103">Después de crear una <xref:System.Data.DataTable> y definir su estructura usando columnas y restricciones, se le pueden agregar nuevas filas de datos.</span><span class="sxs-lookup"><span data-stu-id="9883d-103">After you create a <xref:System.Data.DataTable> and define its structure using columns and constraints, you can add new rows of data to the table.</span></span> <span data-ttu-id="9883d-104">Para agregar una nueva fila, declare una nueva variable como tipo <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="9883d-104">To add a new row, declare a new variable as type <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="9883d-105">Se devuelve un nuevo objeto **DataRow** cuando se llama al <xref:System.Data.DataTable.NewRow%2A> método.</span><span class="sxs-lookup"><span data-stu-id="9883d-105">A new **DataRow** object is returned when you call the <xref:System.Data.DataTable.NewRow%2A> method.</span></span> <span data-ttu-id="9883d-106">A continuación, **DataTable** crea el objeto **DataRow** en función <xref:System.Data.DataColumnCollection>de la estructura de la tabla, tal como se define en el archivo .</span><span class="sxs-lookup"><span data-stu-id="9883d-106">The **DataTable** then creates the **DataRow** object based on the structure of the table, as defined by the <xref:System.Data.DataColumnCollection>.</span></span>  
  
 <span data-ttu-id="9883d-107">En el ejemplo siguiente se muestra cómo crear una nueva fila mediante una llamada a la **NewRow** método.</span><span class="sxs-lookup"><span data-stu-id="9883d-107">The following example demonstrates how to create a new row by calling the **NewRow** method.</span></span>  
  
```vb  
Dim workRow As DataRow = workTable.NewRow()  
```  
  
```csharp  
DataRow workRow = workTable.NewRow();  
```  
  
 <span data-ttu-id="9883d-108">A continuación, la fila recién agregada se puede manipular mediante un índice o nombre de columna, como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9883d-108">You then can manipulate the newly added row using an index or the column name, as shown in the following example.</span></span>  
  
```vb  
workRow("CustLName") = "Smith"  
workRow(1) = "Smith"  
```  
  
```csharp  
workRow["CustLName"] = "Smith";  
workRow[1] = "Smith";  
```  
  
 <span data-ttu-id="9883d-109">Después de insertar datos en **Add** la nueva fila, el Add <xref:System.Data.DataRowCollection>método se utiliza para agregar la fila a la , que se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="9883d-109">After data is inserted into the new row, the **Add** method is used to add the row to the <xref:System.Data.DataRowCollection>, shown in the following code.</span></span>  
  
```vb  
workTable.Rows.Add(workRow)  
```  
  
```csharp  
workTable.Rows.Add(workRow);  
```  
  
 <span data-ttu-id="9883d-110">También puede llamar al método **Add** para agregar una nueva fila pasando <xref:System.Object>una matriz de valores, escrita como , como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="9883d-110">You can also call the **Add** method to add a new row by passing in an array of values, typed as <xref:System.Object>, as shown in the following example.</span></span>  
  
```vb  
workTable.Rows.Add(new Object() {1, "Smith"})  
```  
  
```csharp  
workTable.Rows.Add(new Object[] {1, "Smith"});  
```  
  
 <span data-ttu-id="9883d-111">Al pasar una matriz de valores, escritos como **Object**, al método **Add** se crea una nueva fila dentro de la tabla y se establecen sus valores de columna en los valores de la matriz de objetos.</span><span class="sxs-lookup"><span data-stu-id="9883d-111">Passing an array of values, typed as **Object**, to the **Add** method creates a new row inside the table and sets its column values to the values in the object array.</span></span> <span data-ttu-id="9883d-112">Tenga en cuenta que los valores de la matriz se hacen coincidir en secuencia con las columnas, basándose en el orden en que aparecen en la tabla.</span><span class="sxs-lookup"><span data-stu-id="9883d-112">Note that values in the array are matched sequentially to the columns, based on the order in which they appear in the table.</span></span>  
  
 <span data-ttu-id="9883d-113">En el ejemplo siguiente se agregan 10 filas a la tabla **Customers** recién creada.</span><span class="sxs-lookup"><span data-stu-id="9883d-113">The following example adds 10 rows to the newly created **Customers** table.</span></span>  
  
```vb  
Dim workRow As DataRow  
Dim i As Integer  
  
For i = 0 To 9  
  workRow = workTable.NewRow()  
  workRow(0) = i  
  workRow(1) = "CustName" & I.ToString()  
  workTable.Rows.Add(workRow)  
Next  
```  
  
```csharp  
DataRow workRow;  
  
for (int i = 0; i <= 9; i++)
{  
  workRow = workTable.NewRow();  
  workRow[0] = i;  
  workRow[1] = "CustName" + i.ToString();  
  workTable.Rows.Add(workRow);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="9883d-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9883d-114">See also</span></span>

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="9883d-115">Manipular datos en un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="9883d-115">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="9883d-116">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9883d-116">ADO.NET Overview</span></span>](../ado-net-overview.md)
