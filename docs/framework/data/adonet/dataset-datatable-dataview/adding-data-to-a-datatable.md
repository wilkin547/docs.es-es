---
title: "Agregar datos a DataTable | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d6aa8474-7bde-48f7-949d-20dc38a1625b
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Agregar datos a DataTable
Después de crear una <xref:System.Data.DataTable> y definir su estructura usando columnas y restricciones, se le pueden agregar nuevas filas de datos.  Para agregar una nueva fila, declare una nueva variable como tipo <xref:System.Data.DataRow>.  Se devuelve un nuevo objeto **DataRow** cuando se llama al método <xref:System.Data.DataTable.NewRow%2A>.  A continuación, la **DataTable** crea el objeto **DataRow** basándose en la estructura de la tabla, definida por la <xref:System.Data.DataColumnCollection>.  
  
 En el ejemplo siguiente se muestra cómo se crea una nueva fila llamando al método **NewRow**.  
  
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
  
 Una vez que se han insertado datos en la nueva fila, se utiliza el método **Add** para agregar la fila a la <xref:System.Data.DataRowCollection>, como se muestra en el siguiente código.  
  
```vb  
workTable.Rows.Add(workRow)  
  
```  
  
```csharp  
workTable.Rows.Add(workRow);  
```  
  
 También se puede llamar al método **Add** para agregar una nueva fila pasando una matriz de valores, con el tipo <xref:System.Object>, tal y como se muestra en el ejemplo siguiente.  
  
```vb  
workTable.Rows.Add(new Object() {1, "Smith"})  
  
```  
  
```csharp  
workTable.Rows.Add(new Object[] {1, "Smith"});  
```  
  
 Si se pasa una matriz de objetos con el tipo **Object** al método **Add**, se crea una nueva fila dentro de la tabla y se establece sus valores de columna en los valores de la matriz de objetos.  Tenga en cuenta que los valores de la matriz se hacen coincidir en secuencia con las columnas, basándose en el orden en que aparecen en la tabla.  
  
 En el siguiente ejemplo se agregan diez filas a la tabla **Customers** recién creada.  
  
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
  
## Vea también  
 <xref:System.Data.DataColumnCollection>   
 <xref:System.Data.DataRow>   
 <xref:System.Data.DataRowCollection>   
 <xref:System.Data.DataTable>   
 [Manipular datos en DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)