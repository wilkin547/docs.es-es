---
title: Paginar un resultado de consulta
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa360c46-e5f8-411e-a711-46997771133d
ms.openlocfilehash: 2e7fb97e5c0cb42deff43c411f47e8d30e2257ef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149393"
---
# <a name="paging-through-a-query-result"></a>Paginar un resultado de consulta
La paginación a través del resultado de una consulta es un proceso que consiste en devolver los resultados de una consulta en subconjuntos menores de datos, o páginas. Se trata de una práctica frecuente para presentar los resultados a un usuario en fragmentos pequeños y fáciles de administrar.  
  
 El **DataAdapter** proporciona un recurso para devolver solo una página de datos, a través de sobrecargas de la **Fill** método. Sin embargo, esta podría no ser la mejor opción para paginar a <xref:System.Data.DataTable> <xref:System.Data.DataSet> través de resultados de consultas grandes porque, aunque el **DataAdapter** rellena el destino o solo con los registros solicitados, los recursos para devolver toda la consulta se siguen utilizando. Para devolver una página de datos a partir de un origen de datos sin utilizar los recursos necesarios para devolver toda la consulta, hay que especificar otros criterios adicionales para la consulta que reduzcan las filas devueltas a las filas únicamente necesarias.  
  
 Para usar el método **Fill** para devolver una página de datos, especifique un parámetro **startRecord** para el primer registro de la página de datos y un parámetro **maxRecords** para el número de registros de la página de datos.  
  
 En el ejemplo de código siguiente se muestra cómo utilizar el **Fill** método para devolver la primera página de un resultado de consulta donde el tamaño de página es de cinco registros.  
  
```vb  
Dim currentIndex As Integer = 0  
Dim pageSize As Integer = 5  
  
Dim orderSQL As String = "SELECT * FROM dbo.Orders ORDER BY OrderID"  
' Assumes that connection is a valid SqlConnection object.  
Dim adapter As SqlDataAdapter = _  
  New SqlDataAdapter(orderSQL, connection)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders")  
```  
  
```csharp  
int currentIndex = 0;  
int pageSize = 5;  
  
string orderSQL = "SELECT * FROM Orders ORDER BY OrderID";  
// Assumes that connection is a valid SqlConnection object.  
SqlDataAdapter adapter = new SqlDataAdapter(orderSQL, connection);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders");  
```  
  
 En el ejemplo anterior, el **DataSet** solo se rellena con cinco registros, pero se devuelve toda la tabla **Orders.** Para rellenar el **DataSet** con esos mismos cinco registros, pero solo devolver cinco registros, use las cláusulas TOP y WHERE en la instrucción SQL, como en el ejemplo de código siguiente.  
  
```vb  
Dim pageSize As Integer = 5  
  
Dim orderSQL As String = "SELECT TOP " & pageSize & _  
  " * FROM Orders ORDER BY OrderID"  
Dim adapter As SqlDataAdapter = _  
  New SqlDataAdapter(orderSQL, connection)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, "Orders")
```  
  
```csharp  
int pageSize = 5;  
  
string orderSQL = "SELECT TOP " + pageSize +
  " * FROM Orders ORDER BY OrderID";  
SqlDataAdapter adapter = new SqlDataAdapter(orderSQL, connection);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, "Orders");  
```  
  
 Hay que tener en cuenta que, al paginar a través del resultado de una consulta de esta forma, hay que conservar el identificador único por el que están ordenadas las filas con el fin de pasar el identificador único al comando con el fin de devolver la siguiente página de registros, tal y como se muestra en el ejemplo de código siguiente.  
  
```vb  
Dim lastRecord As String = _  
  dataSet.Tables("Orders").Rows(pageSize - 1)("OrderID").ToString()  
```  
  
```csharp  
string lastRecord =
  dataSet.Tables["Orders"].Rows[pageSize - 1]["OrderID"].ToString();  
```  
  
 Para devolver la página siguiente de registros mediante la sobrecarga del método **Fill** que toma los parámetros **startRecord** y **maxRecords,** incremente el índice de registros actual por el tamaño de página y rellene la tabla. Recuerde que el servidor de base de datos devuelve todos los resultados de la consulta aunque solo se agregue una página de registros al conjunto de **datos**. En el siguiente ejemplo de código se vacía el contenido de las filas de la tabla antes de rellenarse con la siguiente página de datos. Quizás se desee conservar un cierto número de filas devueltas en una caché local para reducir los viajes al servidor de bases de datos.  
  
```vb  
currentIndex = currentIndex + pageSize  
  
dataSet.Tables("Orders").Rows.Clear()  
  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders")  
```  
  
```csharp  
currentIndex += pageSize;  
  
dataSet.Tables["Orders"].Rows.Clear();  
  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders");  
```  
  
 Para devolver la siguiente página de registros sin que el servidor de bases de datos tenga que devolver toda la consulta, hay que especificar criterios restrictivos en la instrucción SELECT. Como el ejemplo anterior conservaba el último registro devuelto, es posible utilizarlo en la cláusula WHERE con el fin de especificar un punto de partida para la consulta, como se muestra en el ejemplo de código siguiente.  
  
```vb  
orderSQL = "SELECT TOP " & pageSize & _  
  " * FROM Orders WHERE OrderID > " & lastRecord & " ORDER BY OrderID"  
adapter.SelectCommand.CommandText = orderSQL  
  
dataSet.Tables("Orders").Rows.Clear()  
  
adapter.Fill(dataSet, "Orders")  
```  
  
```csharp  
orderSQL = "SELECT TOP " + pageSize +
  " * FROM Orders WHERE OrderID > " + lastRecord + " ORDER BY OrderID";  
adapter.SelectCommand.CommandText = orderSQL;  
  
dataSet.Tables["Orders"].Rows.Clear();  
  
adapter.Fill(dataSet, "Orders");  
```  
  
## <a name="see-also"></a>Consulte también

- [Objetos DataAdapter y DataReader](dataadapters-and-datareaders.md)
- [Información general de ADO.NET](ado-net-overview.md)
