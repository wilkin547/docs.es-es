---
description: 'Más información sobre: paginación a través de un resultado de consulta'
title: Paginar un resultado de consulta
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa360c46-e5f8-411e-a711-46997771133d
ms.openlocfilehash: ead2c74e19cfb81c83c7bf1e73b0c0d7a0a7cc67
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99672366"
---
# <a name="paging-through-a-query-result"></a>Paginar un resultado de consulta

La paginación a través del resultado de una consulta es un proceso que consiste en devolver los resultados de una consulta en subconjuntos menores de datos, o páginas. Se trata de una práctica frecuente para presentar los resultados a un usuario en fragmentos pequeños y fáciles de administrar.  
  
 El **DataAdapter** proporciona una utilidad para devolver solo una página de datos, a través de sobrecargas del método **Fill** . Pero es posible que no sea la mejor opción para realizar la paginación por medio de resultados de consultas grandes, ya que, aunque el objeto **DataAdapter** rellena los elementos <xref:System.Data.DataTable> o <xref:System.Data.DataSet> de destino solo con los registros solicitados, se siguen utilizando los recursos para devolver toda la consulta. Para devolver una página de datos a partir de un origen de datos sin utilizar los recursos necesarios para devolver toda la consulta, hay que especificar otros criterios adicionales para la consulta que reduzcan las filas devueltas a las filas únicamente necesarias.  
  
 Para usar el método **Fill** para devolver una página de datos, especifique un parámetro **startRecord** , para el primer registro de la página de datos, y un parámetro **MaxRecords** , para el número de registros de la página de datos.  
  
 En el ejemplo de código siguiente se muestra cómo usar el método **Fill** para devolver la primera página del resultado de una consulta, donde el tamaño de página es cinco registros.  
  
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
  
 En el ejemplo anterior, el objeto **DataSet** solo se rellena con cinco registros pero se devuelve la tabla **Orders** completa. Para rellenar el **conjunto** de elementos con esos mismos cinco registros, pero devolver solo cinco registros, use las cláusulas Top y where en la instrucción SQL, como en el ejemplo de código siguiente.  
  
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
  
 Para devolver la siguiente página de registros mediante la sobrecarga del método **Fill** que toma los parámetros **startRecord** y **MaxRecords** , incremente el índice de registro actual por el tamaño de página y rellene la tabla. Recuerde que el servidor de bases de datos devuelve todos los resultados de la consulta aunque solo se agregue una página de registros al objeto **DataSet**. En el siguiente ejemplo de código se vacía el contenido de las filas de la tabla antes de rellenarse con la siguiente página de datos. Quizás se desee conservar un cierto número de filas devueltas en una caché local para reducir los viajes al servidor de bases de datos.  
  
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
