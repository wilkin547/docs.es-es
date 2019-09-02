---
title: Agregar datos a un objeto DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d6aa8474-7bde-48f7-949d-20dc38a1625b
ms.openlocfilehash: 91c635e2bc2ed617e8c45171d9ec7d7359b9ca88
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205479"
---
# <a name="adding-data-to-a-datatable"></a>Agregar datos a un objeto DataTable
Después de crear una <xref:System.Data.DataTable> y definir su estructura usando columnas y restricciones, se le pueden agregar nuevas filas de datos. Para agregar una nueva fila, declare una nueva variable como tipo <xref:System.Data.DataRow>. Cuando se llama al <xref:System.Data.DataTable.NewRow%2A> método, se devuelve un nuevo objeto DataRow. A continuación, **DataTable** crea el objeto **DataRow** basándose en la estructura de la tabla, tal y <xref:System.Data.DataColumnCollection>como se define en.  
  
 En el ejemplo siguiente se muestra cómo crear una nueva fila llamando al método **NewRow** .  
  
```vb  
Dim workRow As DataRow = workTable.NewRow()  
```  
  
```csharp  
DataRow workRow = workTable.NewRow();  
```  
  
 A continuación, la fila recién agregada se puede manipular mediante un índice o nombre de columna, como se muestra en el siguiente ejemplo.  
  
```vb  
workRow("CustLName") = "Smith"  
workRow(1) = "Smith"  
```  
  
```csharp  
workRow["CustLName"] = "Smith";  
workRow[1] = "Smith";  
```  
  
 Después de insertar los datos en la nueva fila, se usa el método **Add** para agregar la fila a <xref:System.Data.DataRowCollection>, que se muestra en el código siguiente.  
  
```vb  
workTable.Rows.Add(workRow)  
```  
  
```csharp  
workTable.Rows.Add(workRow);  
```  
  
 También puede llamar al método **Add** para agregar una nueva fila pasando una matriz de valores, con el tipo <xref:System.Object>, tal como se muestra en el ejemplo siguiente.  
  
```vb  
workTable.Rows.Add(new Object() {1, "Smith"})  
```  
  
```csharp  
workTable.Rows.Add(new Object[] {1, "Smith"});  
```  
  
 Al pasar una matriz de valores, con tipo **Object**, al método **Add** , se crea una nueva fila dentro de la tabla y se establecen sus valores de columna en los valores de la matriz de objetos. Tenga en cuenta que los valores de la matriz se hacen coincidir en secuencia con las columnas, basándose en el orden en que aparecen en la tabla.  
  
 En el ejemplo siguiente se agregan 10 filas a la tabla Customers recién creada.  
  
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
  
## <a name="see-also"></a>Vea también

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [Manipulación de datos en un objeto DataTable](manipulating-data-in-a-datatable.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
