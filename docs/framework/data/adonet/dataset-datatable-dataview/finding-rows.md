---
title: Buscar filas
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 5da300e2-74c0-4d13-9202-fc20ed8212d8
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 96a65761cb6ddf31c0bb4c14077aed37336183f9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="finding-rows"></a>Buscar filas
Es posible buscar filas en función de los valores clave de ordenación mediante los métodos <xref:System.Data.DataView.Find%2A> y <xref:System.Data.DataView.FindRows%2A> de la <xref:System.Data.DataView>. Las mayúsculas y minúsculas de búsqueda de valores en el **buscar** y **FindRows** métodos viene determinado por la **CaseSensitive** propiedad de subyacente <xref:System.Data.DataTable>. Los valores de búsqueda deben coincidir en su totalidad con los valores de clave de ordenación existentes para que se devuelva un resultado.  
  
 El **buscar** método devuelve un entero con el índice de la <xref:System.Data.DataRowView> que coincida con los criterios de búsqueda. Si más de una fila coincide con los criterios de búsqueda, solo el índice de la primera coincidencia **DataRowView** se devuelve. Si se encuentra ninguna coincidencia, **buscar** devuelve -1.  
  
 Para devolver los resultados de búsqueda que coincidan con varias filas, utilice la **FindRows** método. **FindRows** funciona igual que el **buscar** método, salvo que devuelva un **DataRowView** matriz que hace referencia a todas las filas coincidentes en la **DataView**. Si se encuentra ninguna coincidencia, la **DataRowView** matriz estará vacía.  
  
 Para usar el **buscar** o **FindRows** métodos debe especificar un criterio de ordenación orden estableciendo **ApplyDefaultSort** a **true** o mediante la **Ordenación** propiedad. Si no se especifica ningún criterio de ordenación, se inicia una excepción.  
  
 El **buscar** y **FindRows** métodos toman una matriz de valores como entrada cuya longitud coincide con el número de columnas en el criterio de ordenación. En el caso de una ordenación por una única columna, puede pasar un único valor. Para los criterios de ordenación que contienen varias columnas, debe pasar una matriz de objetos. Tenga en cuenta que para una ordenación según varias columnas, los valores de la matriz de objetos deben coincidir con el orden de las columnas especificadas en el **ordenación** propiedad de la **DataView**.  
  
 El siguiente ejemplo de código muestra la **buscar** método que se llama con un **DataView** con un criterio de ordenación de columna única.  
  
```vb  
Dim custView As DataView = _  
  New DataView(custDS.Tables("Customers"), "", _  
  "CompanyName", DataViewRowState.CurrentRows)  
  
Dim rowIndex As Integer = custView.Find("The Cracker Box")  
  
If rowIndex = -1 Then  
  Console.WriteLine("No match found.")  
Else  
  Console.WriteLine("{0}, {1}", _  
    custView(rowIndex)("CustomerID").ToString(), _  
    custView(rowIndex)("CompanyName").ToString())  
End If  
```  
  
```csharp  
DataView custView = new DataView(custDS.Tables["Customers"], "",   
  "CompanyName", DataViewRowState.CurrentRows);  
  
int rowIndex = custView.Find("The Cracker Box");  
  
if (rowIndex == -1)  
  Console.WriteLine("No match found.");  
else  
  Console.WriteLine("{0}, {1}",  
    custView[rowIndex]["CustomerID"].ToString(),  
    custView[rowIndex]["CompanyName"].ToString());  
```  
  
 Si su **ordenación** propiedad especifica varias columnas, debe pasar una matriz de objetos con los valores de búsqueda para cada columna en el orden especificado por el **ordenación** propiedad, como en el ejemplo de código siguiente.  
  
```vb  
Dim custView As DataView = _  
  New DataView(custDS.Tables("Customers"), "", _  
  "CompanyName, ContactName", _  
  DataViewRowState.CurrentRows)  
  
Dim foundRows() As DataRowView = _  
  custView.FindRows(New object() {"The Cracker Box", "Liu Wong"})  
  
If foundRows.Length = 0 Then  
  Console.WriteLine("No match found.")  
Else  
  Dim myDRV As DataRowView  
  For Each myDRV In foundRows  
    Console.WriteLine("{0}, {1}", _  
      myDRV("CompanyName").ToString(), myDRV("ContactName").ToString())  
  Next  
End If  
```  
  
```csharp  
DataView custView = new DataView(custDS.Tables["Customers"], "",  
  "CompanyName, ContactName",  
  DataViewRowState.CurrentRows);  
  
DataRowView[] foundRows =   
  custView.FindRows(new object[] {"The Cracker Box", "Liu Wong"});  
  
if (foundRows.Length == 0)  
  Console.WriteLine("No match found.");  
else  
  foreach (DataRowView myDRV in foundRows)  
    Console.WriteLine("{0}, {1}", myDRV["CompanyName"].ToString(),   
      myDRV["ContactName"].ToString());  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 [Objetos DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
