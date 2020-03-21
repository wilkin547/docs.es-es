---
title: Buscar filas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5da300e2-74c0-4d13-9202-fc20ed8212d8
ms.openlocfilehash: cfd4587f0dde7687ecf88bf6b31c44b90a2287ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151148"
---
# <a name="finding-rows"></a>Buscar filas
Es posible buscar filas en función de los valores clave de ordenación mediante los métodos <xref:System.Data.DataView.Find%2A> y <xref:System.Data.DataView.FindRows%2A> de la <xref:System.Data.DataView>. La distinción entre mayúsculas y minúsculas de los valores de búsqueda <xref:System.Data.DataTable>en los métodos **Find** y **FindRows** viene determinada por la propiedad **CaseSensitive** del archivo . Los valores de búsqueda deben coincidir en su totalidad con los valores de clave de ordenación existentes para que se devuelva un resultado.  
  
 El **método Find** devuelve un entero <xref:System.Data.DataRowView> con el índice que coincide con los criterios de búsqueda. Si más de una fila coincide con los criterios de búsqueda, solo se devuelve el índice de la primera **coincidencia DataRowView.** Si no se encuentra ninguna coincidencia, **Find** devuelve -1.  
  
 Para devolver resultados de búsqueda que coincidan con varias filas, utilice el **FindRows** método. **FindRows** funciona igual que el método **Find,** excepto que devuelve una matriz **DataRowView** que hace referencia a todas las filas coincidentes de **DataView**. Si no se encuentra ninguna coincidencia, la matriz **DataRowView** estará vacía.  
  
 Para usar el **Find** o **FindRows** métodos debe especificar un criterio de ordenación estableciendo **ApplyDefaultSort** en **true** o mediante el **Sort** propiedad. Si no se especifica ningún criterio de ordenación, se inicia una excepción.  
  
 El **Find** y **FindRows** métodos toman una matriz de valores como entrada cuya longitud coincide con el número de columnas en el criterio de ordenación. En el caso de una ordenación por una única columna, puede pasar un único valor. Para los criterios de ordenación que contienen varias columnas, debe pasar una matriz de objetos. Tenga en cuenta que para una ordenación en varias columnas, los valores de la matriz de objetos deben coincidir con el orden de las columnas especificadas en la propiedad **Sort** de **DataView**.  
  
 En el ejemplo de código siguiente se muestra el **Find** método que se llama en un **DataView** con un único criterio de ordenación de columna.  
  
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
  
 Si el **Sort** propiedad especifica varias columnas, debe pasar una matriz de objetos con los valores de búsqueda para cada columna en el orden especificado por el **Sort** propiedad, como en el ejemplo de código siguiente.  
  
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
  
## <a name="see-also"></a>Consulte también

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [Objetos DataView](dataviews.md)
- [Información general de ADO.NET](../ado-net-overview.md)
