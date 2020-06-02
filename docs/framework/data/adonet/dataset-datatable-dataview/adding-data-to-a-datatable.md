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
# <a name="adding-data-to-a-datatable"></a>Agregar datos a un objeto DataTable
Después de crear una <xref:System.Data.DataTable> y definir su estructura usando columnas y restricciones, se le pueden agregar nuevas filas de datos. Para agregar una nueva fila, declare una nueva variable como tipo <xref:System.Data.DataRow>. Cuando se llama al método, se devuelve un nuevo objeto **DataRow** <xref:System.Data.DataTable.NewRow%2A> . A continuación, **DataTable** crea el objeto **DataRow** basándose en la estructura de la tabla, tal y como se define en <xref:System.Data.DataColumnCollection> .  
  
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
  
 Después de insertar los datos en la nueva fila, se usa el método **Add** para agregar la fila a <xref:System.Data.DataRowCollection> , que se muestra en el código siguiente.  
  
```vb  
workTable.Rows.Add(workRow)  
```  
  
```csharp  
workTable.Rows.Add(workRow);  
```  
  
 También puede llamar al método **Add** para agregar una nueva fila pasando una matriz de valores, con <xref:System.Object> el tipo, tal como se muestra en el ejemplo siguiente.  
  
```vb  
workTable.Rows.Add(new Object() {1, "Smith"})  
```  
  
```csharp  
workTable.Rows.Add(new Object[] {1, "Smith"});  
```  
  
 Al pasar una matriz de valores, con tipo **Object**, al método **Add** , se crea una nueva fila dentro de la tabla y se establecen sus valores de columna en los valores de la matriz de objetos. Tenga en cuenta que los valores de la matriz se hacen coincidir en secuencia con las columnas, basándose en el orden en que aparecen en la tabla.  
  
 En el ejemplo siguiente se agregan 10 filas a la tabla **Customers** recién creada.  
  
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
  
## <a name="see-also"></a>Consulte también

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [Manipular datos en un objeto DataTable](manipulating-data-in-a-datatable.md)
- [Información general de ADO.NET](../ado-net-overview.md)
