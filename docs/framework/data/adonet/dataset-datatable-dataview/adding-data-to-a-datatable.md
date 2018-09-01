---
title: Agregar datos a un objeto DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d6aa8474-7bde-48f7-949d-20dc38a1625b
ms.openlocfilehash: c1ebe2d735924c559f450f4041884dc9845e4fe0
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43396090"
---
# <a name="adding-data-to-a-datatable"></a>Agregar datos a un objeto DataTable
Después de crear una <xref:System.Data.DataTable> y definir su estructura usando columnas y restricciones, se le pueden agregar nuevas filas de datos. Para agregar una nueva fila, declare una nueva variable como tipo <xref:System.Data.DataRow>. Un nuevo **DataRow** objeto se devuelve al llamar a la <xref:System.Data.DataTable.NewRow%2A> método. El **DataTable** , a continuación, se crea el **DataRow** objeto basándose en la estructura de la tabla, tal como se define por la <xref:System.Data.DataColumnCollection>.  
  
 En el ejemplo siguiente se muestra cómo crear una nueva fila mediante una llamada a la **NewRow** método.  
  
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
  
 Después de insertan datos en la nueva fila, el **agregar** método se usa para agregar la fila a la <xref:System.Data.DataRowCollection>, como se muestra en el código siguiente.  
  
```vb  
workTable.Rows.Add(workRow)  
```  
  
```csharp  
workTable.Rows.Add(workRow);  
```  
  
 También puede llamar a la **agregar** método para agregar una nueva fila pasando una matriz de valores, el tipo <xref:System.Object>, como se muestra en el ejemplo siguiente.  
  
```vb  
workTable.Rows.Add(new Object() {1, "Smith"})  
```  
  
```csharp  
workTable.Rows.Add(new Object[] {1, "Smith"});  
```  
  
 Pasa una matriz de valores de tipo **objeto**, a la **agregar** método crea una nueva fila dentro de la tabla y establece sus valores de columna a los valores de la matriz de objetos. Tenga en cuenta que los valores de la matriz se hacen coincidir en secuencia con las columnas, basándose en el orden en que aparecen en la tabla.  
  
 El ejemplo siguiente agrega a 10 filas recién creado **clientes** tabla.  
  
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
 <xref:System.Data.DataColumnCollection>  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataRowCollection>  
 <xref:System.Data.DataTable>  
 [Manipulación de datos en un objeto DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
