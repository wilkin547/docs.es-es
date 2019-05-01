---
title: Agregar datos a un objeto DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d6aa8474-7bde-48f7-949d-20dc38a1625b
ms.openlocfilehash: ec4ad84a39afe21ef77507732e5e0e417d45f3e7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034533"
---
# <a name="adding-data-to-a-datatable"></a><span data-ttu-id="51e9c-102">Agregar datos a un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="51e9c-102">Adding Data to a DataTable</span></span>
<span data-ttu-id="51e9c-103">Después de crear una <xref:System.Data.DataTable> y definir su estructura usando columnas y restricciones, se le pueden agregar nuevas filas de datos.</span><span class="sxs-lookup"><span data-stu-id="51e9c-103">After you create a <xref:System.Data.DataTable> and define its structure using columns and constraints, you can add new rows of data to the table.</span></span> <span data-ttu-id="51e9c-104">Para agregar una nueva fila, declare una nueva variable como tipo <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="51e9c-104">To add a new row, declare a new variable as type <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="51e9c-105">Un nuevo **DataRow** objeto se devuelve al llamar a la <xref:System.Data.DataTable.NewRow%2A> método.</span><span class="sxs-lookup"><span data-stu-id="51e9c-105">A new **DataRow** object is returned when you call the <xref:System.Data.DataTable.NewRow%2A> method.</span></span> <span data-ttu-id="51e9c-106">El **DataTable** , a continuación, se crea el **DataRow** objeto basándose en la estructura de la tabla, tal como se define por la <xref:System.Data.DataColumnCollection>.</span><span class="sxs-lookup"><span data-stu-id="51e9c-106">The **DataTable** then creates the **DataRow** object based on the structure of the table, as defined by the <xref:System.Data.DataColumnCollection>.</span></span>  
  
 <span data-ttu-id="51e9c-107">En el ejemplo siguiente se muestra cómo crear una nueva fila mediante una llamada a la **NewRow** método.</span><span class="sxs-lookup"><span data-stu-id="51e9c-107">The following example demonstrates how to create a new row by calling the **NewRow** method.</span></span>  
  
```vb  
Dim workRow As DataRow = workTable.NewRow()  
```  
  
```csharp  
DataRow workRow = workTable.NewRow();  
```  
  
 <span data-ttu-id="51e9c-108">A continuación, la fila recién agregada se puede manipular mediante un índice o nombre de columna, como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="51e9c-108">You then can manipulate the newly added row using an index or the column name, as shown in the following example.</span></span>  
  
```vb  
workRow("CustLName") = "Smith"  
workRow(1) = "Smith"  
```  
  
```csharp  
workRow["CustLName"] = "Smith";  
workRow[1] = "Smith";  
```  
  
 <span data-ttu-id="51e9c-109">Después de insertan datos en la nueva fila, el **agregar** método se usa para agregar la fila a la <xref:System.Data.DataRowCollection>, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="51e9c-109">After data is inserted into the new row, the **Add** method is used to add the row to the <xref:System.Data.DataRowCollection>, shown in the following code.</span></span>  
  
```vb  
workTable.Rows.Add(workRow)  
```  
  
```csharp  
workTable.Rows.Add(workRow);  
```  
  
 <span data-ttu-id="51e9c-110">También puede llamar a la **agregar** método para agregar una nueva fila pasando una matriz de valores, el tipo <xref:System.Object>, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="51e9c-110">You can also call the **Add** method to add a new row by passing in an array of values, typed as <xref:System.Object>, as shown in the following example.</span></span>  
  
```vb  
workTable.Rows.Add(new Object() {1, "Smith"})  
```  
  
```csharp  
workTable.Rows.Add(new Object[] {1, "Smith"});  
```  
  
 <span data-ttu-id="51e9c-111">Pasa una matriz de valores de tipo **objeto**, a la **agregar** método crea una nueva fila dentro de la tabla y establece sus valores de columna a los valores de la matriz de objetos.</span><span class="sxs-lookup"><span data-stu-id="51e9c-111">Passing an array of values, typed as **Object**, to the **Add** method creates a new row inside the table and sets its column values to the values in the object array.</span></span> <span data-ttu-id="51e9c-112">Tenga en cuenta que los valores de la matriz se hacen coincidir en secuencia con las columnas, basándose en el orden en que aparecen en la tabla.</span><span class="sxs-lookup"><span data-stu-id="51e9c-112">Note that values in the array are matched sequentially to the columns, based on the order in which they appear in the table.</span></span>  
  
 <span data-ttu-id="51e9c-113">El ejemplo siguiente agrega a 10 filas recién creado **clientes** tabla.</span><span class="sxs-lookup"><span data-stu-id="51e9c-113">The following example adds 10 rows to the newly created **Customers** table.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="51e9c-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="51e9c-114">See also</span></span>

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="51e9c-115">Manipulación de datos en un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="51e9c-115">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="51e9c-116">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="51e9c-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
