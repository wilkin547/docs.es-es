---
title: "Buscar filas | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5da300e2-74c0-4d13-9202-fc20ed8212d8
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Buscar filas
Es posible buscar filas en función de los valores clave de ordenación mediante los métodos <xref:System.Data.DataView.Find%2A> y <xref:System.Data.DataView.FindRows%2A> de la <xref:System.Data.DataView>.  La diferenciación entre mayúsculas y minúsculas de los valores de búsqueda en los métodos **Find** y **FindRows** está determinada por la propiedad **CaseSensitive** de la <xref:System.Data.DataTable> subyacente.  Los valores de búsqueda deben coincidir en su totalidad con los valores de clave de ordenación existentes para que se devuelva un resultado.  
  
 El método **Find** devuelve un entero con el índice de la <xref:System.Data.DataRowView> que coincide con los criterios de búsqueda.  Si más de una fila coincide con los criterios de búsqueda, sólo se devolverá el índice de la primera **DataRowView** coincidente.  Si no se encuentra ninguna coincidencia, **Find** devuelve \-1.  
  
 Para devolver resultados de la búsqueda que coincidan con varias filas, utilice el método **FindRows**.  **FindRows** funciona igual que el método **Find**, excepto en que devuelve una matriz de **DataRowView** que hace referencia a todas las filas coincidentes de la **DataView**.  Si no se encuentra ninguna coincidencia, la matriz de **DataRowView** estará vacía.  
  
 Para utilizar los métodos **Find** o **FindRows** debe especificar un criterio de ordenación; para ello, establezca **ApplyDefaultSort** como **true** o utilice la propiedad **Sort**.  Si no se especifica ningún criterio de ordenación, se inicia una excepción.  
  
 Los métodos **Find** y **FindRows** toman como entrada una matriz de valores cuya longitud coincide con el número de columnas del criterio de ordenación.  En el caso de una ordenación por una única columna, puede pasar un único valor.  Para los criterios de ordenación que contienen varias columnas, debe pasar una matriz de objetos.  Tenga en cuenta que para una ordenación según varias columnas, los valores de la matriz de objetos deben coincidir con el orden de las columnas especificado en la propiedad **Sort** de **DataView**.  
  
 En el siguiente ejemplo de código se muestra una llamada al método **Find** en una **DataView** con un criterio de ordenación de una única columna.  
  
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
  
 Si la propiedad **Sort** especifica varias columnas, debe pasar una matriz de objetos con los valores de búsqueda de cada columna en el orden especificado por la propiedad **Sort**, como en el siguiente ejemplo de código.  
  
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
  
## Vea también  
 <xref:System.Data.DataTable>   
 <xref:System.Data.DataView>   
 [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)