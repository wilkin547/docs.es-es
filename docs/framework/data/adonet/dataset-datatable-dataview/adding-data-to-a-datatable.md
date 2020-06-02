---
title: Agregar datos a un objeto DataTable
description: Consulte este código de ejemplo para agregar nuevas filas de datos a una tabla de ADO.NET, después de crear un DataTable y definir su estructura con columnas y restricciones.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d6aa8474-7bde-48f7-949d-20dc38a1625b
ms.openlocfilehash: 94ebc97d5f90b5bb92186ba6f33015633bd01127
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286939"
---
# <a name="adding-data-to-a-datatable"></a><span data-ttu-id="b837c-103">Agregar datos a un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="b837c-103">Adding Data to a DataTable</span></span>
<span data-ttu-id="b837c-104">Después de crear una <xref:System.Data.DataTable> y definir su estructura usando columnas y restricciones, se le pueden agregar nuevas filas de datos.</span><span class="sxs-lookup"><span data-stu-id="b837c-104">After you create a <xref:System.Data.DataTable> and define its structure using columns and constraints, you can add new rows of data to the table.</span></span> <span data-ttu-id="b837c-105">Para agregar una nueva fila, declare una nueva variable como tipo <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="b837c-105">To add a new row, declare a new variable as type <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="b837c-106">Cuando se llama al método, se devuelve un nuevo objeto **DataRow** <xref:System.Data.DataTable.NewRow%2A> .</span><span class="sxs-lookup"><span data-stu-id="b837c-106">A new **DataRow** object is returned when you call the <xref:System.Data.DataTable.NewRow%2A> method.</span></span> <span data-ttu-id="b837c-107">A continuación, **DataTable** crea el objeto **DataRow** basándose en la estructura de la tabla, tal y como se define en <xref:System.Data.DataColumnCollection> .</span><span class="sxs-lookup"><span data-stu-id="b837c-107">The **DataTable** then creates the **DataRow** object based on the structure of the table, as defined by the <xref:System.Data.DataColumnCollection>.</span></span>  
  
 <span data-ttu-id="b837c-108">En el ejemplo siguiente se muestra cómo crear una nueva fila llamando al método **NewRow** .</span><span class="sxs-lookup"><span data-stu-id="b837c-108">The following example demonstrates how to create a new row by calling the **NewRow** method.</span></span>  
  
```vb  
Dim workRow As DataRow = workTable.NewRow()  
```  
  
```csharp  
DataRow workRow = workTable.NewRow();  
```  
  
 <span data-ttu-id="b837c-109">A continuación, la fila recién agregada se puede manipular mediante un índice o nombre de columna, como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b837c-109">You then can manipulate the newly added row using an index or the column name, as shown in the following example.</span></span>  
  
```vb  
workRow("CustLName") = "Smith"  
workRow(1) = "Smith"  
```  
  
```csharp  
workRow["CustLName"] = "Smith";  
workRow[1] = "Smith";  
```  
  
 <span data-ttu-id="b837c-110">Después de insertar los datos en la nueva fila, se usa el método **Add** para agregar la fila a <xref:System.Data.DataRowCollection> , que se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="b837c-110">After data is inserted into the new row, the **Add** method is used to add the row to the <xref:System.Data.DataRowCollection>, shown in the following code.</span></span>  
  
```vb  
workTable.Rows.Add(workRow)  
```  
  
```csharp  
workTable.Rows.Add(workRow);  
```  
  
 <span data-ttu-id="b837c-111">También puede llamar al método **Add** para agregar una nueva fila pasando una matriz de valores, con <xref:System.Object> el tipo, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b837c-111">You can also call the **Add** method to add a new row by passing in an array of values, typed as <xref:System.Object>, as shown in the following example.</span></span>  
  
```vb  
workTable.Rows.Add(new Object() {1, "Smith"})  
```  
  
```csharp  
workTable.Rows.Add(new Object[] {1, "Smith"});  
```  
  
 <span data-ttu-id="b837c-112">Al pasar una matriz de valores, con tipo **Object**, al método **Add** , se crea una nueva fila dentro de la tabla y se establecen sus valores de columna en los valores de la matriz de objetos.</span><span class="sxs-lookup"><span data-stu-id="b837c-112">Passing an array of values, typed as **Object**, to the **Add** method creates a new row inside the table and sets its column values to the values in the object array.</span></span> <span data-ttu-id="b837c-113">Tenga en cuenta que los valores de la matriz se hacen coincidir en secuencia con las columnas, basándose en el orden en que aparecen en la tabla.</span><span class="sxs-lookup"><span data-stu-id="b837c-113">Note that values in the array are matched sequentially to the columns, based on the order in which they appear in the table.</span></span>  
  
 <span data-ttu-id="b837c-114">En el ejemplo siguiente se agregan 10 filas a la tabla **Customers** recién creada.</span><span class="sxs-lookup"><span data-stu-id="b837c-114">The following example adds 10 rows to the newly created **Customers** table.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b837c-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b837c-115">See also</span></span>

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="b837c-116">Manipular datos en un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="b837c-116">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="b837c-117">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b837c-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
