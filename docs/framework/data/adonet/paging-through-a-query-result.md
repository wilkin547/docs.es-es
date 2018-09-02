---
title: Paginar un resultado de consulta
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa360c46-e5f8-411e-a711-46997771133d
ms.openlocfilehash: 5d86095586af273f62980fcf8ddf10804b1cfa5a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43406815"
---
# <a name="paging-through-a-query-result"></a><span data-ttu-id="a1f8b-102">Paginar un resultado de consulta</span><span class="sxs-lookup"><span data-stu-id="a1f8b-102">Paging Through a Query Result</span></span>
<span data-ttu-id="a1f8b-103">La paginación a través del resultado de una consulta es un proceso que consiste en devolver los resultados de una consulta en subconjuntos menores de datos, o páginas.</span><span class="sxs-lookup"><span data-stu-id="a1f8b-103">Paging through a query result is the process of returning the results of a query in smaller subsets of data, or pages.</span></span> <span data-ttu-id="a1f8b-104">Se trata de una práctica frecuente para presentar los resultados a un usuario en fragmentos pequeños y fáciles de administrar.</span><span class="sxs-lookup"><span data-stu-id="a1f8b-104">This is a common practice for displaying results to a user in small, easy-to-manage chunks.</span></span>  
  
 <span data-ttu-id="a1f8b-105">El **DataAdapter** proporciona una función para devolver únicamente una página de datos mediante las sobrecargas de los **rellenar** método.</span><span class="sxs-lookup"><span data-stu-id="a1f8b-105">The **DataAdapter** provides a facility for returning only a page of data, through overloads of the **Fill** method.</span></span> <span data-ttu-id="a1f8b-106">Sin embargo, esto podría no ser la mejor opción para paginar a través de los resultados de consultas grandes ya que, aunque el **DataAdapter** rellena el destino <xref:System.Data.DataTable> o <xref:System.Data.DataSet> con solo los registros solicitados, los recursos para devolver el toda la consulta todavía se utilizan.</span><span class="sxs-lookup"><span data-stu-id="a1f8b-106">However, this might not be the best choice for paging through large query results because, although the **DataAdapter** fills the target <xref:System.Data.DataTable> or <xref:System.Data.DataSet> with only the requested records, the resources to return the entire query are still used.</span></span> <span data-ttu-id="a1f8b-107">Para devolver una página de datos a partir de un origen de datos sin utilizar los recursos necesarios para devolver toda la consulta, hay que especificar otros criterios adicionales para la consulta que reduzcan las filas devueltas a las filas únicamente necesarias.</span><span class="sxs-lookup"><span data-stu-id="a1f8b-107">To return a page of data from a data source without using the resources to return the entire query, specify additional criteria for your query that reduce the rows returned to only those required.</span></span>  
  
 <span data-ttu-id="a1f8b-108">Para usar el **rellenar** método para devolver una página de datos, especifique un **startRecord** parámetro para el primer registro en la página de datos y un **maxRecords** parámetro, el número de registros en la página de datos.</span><span class="sxs-lookup"><span data-stu-id="a1f8b-108">To use the **Fill** method to return a page of data, specify a **startRecord** parameter, for the first record in the page of data, and a **maxRecords** parameter, for the number of records in the page of data.</span></span>  
  
 <span data-ttu-id="a1f8b-109">En el ejemplo de código siguiente se muestra cómo utilizar el **rellenar** método para devolver la primera página del resultado de una consulta donde el tamaño de página es de cinco registros.</span><span class="sxs-lookup"><span data-stu-id="a1f8b-109">The following code example shows how to use the **Fill** method to return the first page of a query result where the page size is five records.</span></span>  
  
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
  
 <span data-ttu-id="a1f8b-110">En el ejemplo anterior, el **DataSet** sólo se rellena con cinco registros pero toda la **pedidos** se devuelve la tabla.</span><span class="sxs-lookup"><span data-stu-id="a1f8b-110">In the previous example, the **DataSet** is only filled with five records, but the entire **Orders** table is returned.</span></span> <span data-ttu-id="a1f8b-111">Para rellenar el **DataSet** con esos mismos cinco registros, pero devolver únicamente cinco registros, use la parte superior y las cláusulas WHERE en la instrucción SQL, como se muestra en el siguiente ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="a1f8b-111">To fill the **DataSet** with those same five records, but only return five records, use the TOP and WHERE clauses in your SQL statement, as in the following code example.</span></span>  
  
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
  
 <span data-ttu-id="a1f8b-112">Hay que tener en cuenta que, al paginar a través del resultado de una consulta de esta forma, hay que conservar el identificador único por el que están ordenadas las filas con el fin de pasar el identificador único al comando con el fin de devolver la siguiente página de registros, tal y como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="a1f8b-112">Note that, when paging through the query results in this way, you must preserve the unique identifier that orders the rows, in order to pass the unique ID to the command to return the next page of records, as shown in the following code example.</span></span>  
  
```vb  
Dim lastRecord As String = _  
  dataSet.Tables("Orders").Rows(pageSize - 1)("OrderID").ToString()  
```  
  
```csharp  
string lastRecord =   
  dataSet.Tables["Orders"].Rows[pageSize - 1]["OrderID"].ToString();  
```  
  
 <span data-ttu-id="a1f8b-113">Para devolver la siguiente página de registros utilizando la sobrecarga de la **rellenar** método que toma el **startRecord** y **maxRecords** parámetros, incrementar el índice del registro actual por el tamaño de página y el relleno de la tabla.</span><span class="sxs-lookup"><span data-stu-id="a1f8b-113">To return the next page of records using the overload of the **Fill** method that takes the **startRecord** and **maxRecords** parameters, increment the current record index by the page size and fill the table.</span></span> <span data-ttu-id="a1f8b-114">Recuerde que el servidor de base de datos devuelve los resultados de consulta completa, aunque solo una página de registros se agrega a la **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="a1f8b-114">Remember that the database server returns the entire query results even though only one page of records is added to the **DataSet**.</span></span> <span data-ttu-id="a1f8b-115">En el siguiente ejemplo de código se vacía el contenido de las filas de la tabla antes de rellenarse con la siguiente página de datos.</span><span class="sxs-lookup"><span data-stu-id="a1f8b-115">In the following code example, the table rows are cleared before they are filled with the next page of data.</span></span> <span data-ttu-id="a1f8b-116">Quizás se desee conservar un cierto número de filas devueltas en una caché local para reducir los viajes al servidor de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="a1f8b-116">You might want to preserve a certain number of returned rows in a local cache to reduce trips to the database server.</span></span>  
  
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
  
 <span data-ttu-id="a1f8b-117">Para devolver la siguiente página de registros sin que el servidor de bases de datos tenga que devolver toda la consulta, hay que especificar criterios restrictivos en la instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="a1f8b-117">To return the next page of records without having the database server return the entire query, specify restrictive criteria to the SELECT statement.</span></span> <span data-ttu-id="a1f8b-118">Como el ejemplo anterior conservaba el último registro devuelto, es posible utilizarlo en la cláusula WHERE con el fin de especificar un punto de partida para la consulta, como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="a1f8b-118">Because the preceding example preserved the last record returned, you can use it in the WHERE clause to specify a starting point for the query, as shown in the following code example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a1f8b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1f8b-119">See Also</span></span>  
 [<span data-ttu-id="a1f8b-120">Objetos DataAdapter y DataReader</span><span class="sxs-lookup"><span data-stu-id="a1f8b-120">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="a1f8b-121">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="a1f8b-121">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
