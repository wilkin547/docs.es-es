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
# <a name="paging-through-a-query-result"></a><span data-ttu-id="ed43a-103">Paginar un resultado de consulta</span><span class="sxs-lookup"><span data-stu-id="ed43a-103">Paging Through a Query Result</span></span>

<span data-ttu-id="ed43a-104">La paginación a través del resultado de una consulta es un proceso que consiste en devolver los resultados de una consulta en subconjuntos menores de datos, o páginas.</span><span class="sxs-lookup"><span data-stu-id="ed43a-104">Paging through a query result is the process of returning the results of a query in smaller subsets of data, or pages.</span></span> <span data-ttu-id="ed43a-105">Se trata de una práctica frecuente para presentar los resultados a un usuario en fragmentos pequeños y fáciles de administrar.</span><span class="sxs-lookup"><span data-stu-id="ed43a-105">This is a common practice for displaying results to a user in small, easy-to-manage chunks.</span></span>  
  
 <span data-ttu-id="ed43a-106">El **DataAdapter** proporciona una utilidad para devolver solo una página de datos, a través de sobrecargas del método **Fill** .</span><span class="sxs-lookup"><span data-stu-id="ed43a-106">The **DataAdapter** provides a facility for returning only a page of data, through overloads of the **Fill** method.</span></span> <span data-ttu-id="ed43a-107">Pero es posible que no sea la mejor opción para realizar la paginación por medio de resultados de consultas grandes, ya que, aunque el objeto **DataAdapter** rellena los elementos <xref:System.Data.DataTable> o <xref:System.Data.DataSet> de destino solo con los registros solicitados, se siguen utilizando los recursos para devolver toda la consulta.</span><span class="sxs-lookup"><span data-stu-id="ed43a-107">However, this might not be the best choice for paging through large query results because, although the **DataAdapter** fills the target <xref:System.Data.DataTable> or <xref:System.Data.DataSet> with only the requested records, the resources to return the entire query are still used.</span></span> <span data-ttu-id="ed43a-108">Para devolver una página de datos a partir de un origen de datos sin utilizar los recursos necesarios para devolver toda la consulta, hay que especificar otros criterios adicionales para la consulta que reduzcan las filas devueltas a las filas únicamente necesarias.</span><span class="sxs-lookup"><span data-stu-id="ed43a-108">To return a page of data from a data source without using the resources to return the entire query, specify additional criteria for your query that reduce the rows returned to only those required.</span></span>  
  
 <span data-ttu-id="ed43a-109">Para usar el método **Fill** para devolver una página de datos, especifique un parámetro **startRecord** , para el primer registro de la página de datos, y un parámetro **MaxRecords** , para el número de registros de la página de datos.</span><span class="sxs-lookup"><span data-stu-id="ed43a-109">To use the **Fill** method to return a page of data, specify a **startRecord** parameter, for the first record in the page of data, and a **maxRecords** parameter, for the number of records in the page of data.</span></span>  
  
 <span data-ttu-id="ed43a-110">En el ejemplo de código siguiente se muestra cómo usar el método **Fill** para devolver la primera página del resultado de una consulta, donde el tamaño de página es cinco registros.</span><span class="sxs-lookup"><span data-stu-id="ed43a-110">The following code example shows how to use the **Fill** method to return the first page of a query result where the page size is five records.</span></span>  
  
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
  
 <span data-ttu-id="ed43a-111">En el ejemplo anterior, el objeto **DataSet** solo se rellena con cinco registros pero se devuelve la tabla **Orders** completa.</span><span class="sxs-lookup"><span data-stu-id="ed43a-111">In the previous example, the **DataSet** is only filled with five records, but the entire **Orders** table is returned.</span></span> <span data-ttu-id="ed43a-112">Para rellenar el **conjunto** de elementos con esos mismos cinco registros, pero devolver solo cinco registros, use las cláusulas Top y where en la instrucción SQL, como en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="ed43a-112">To fill the **DataSet** with those same five records, but only return five records, use the TOP and WHERE clauses in your SQL statement, as in the following code example.</span></span>  
  
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
  
 <span data-ttu-id="ed43a-113">Hay que tener en cuenta que, al paginar a través del resultado de una consulta de esta forma, hay que conservar el identificador único por el que están ordenadas las filas con el fin de pasar el identificador único al comando con el fin de devolver la siguiente página de registros, tal y como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="ed43a-113">Note that, when paging through the query results in this way, you must preserve the unique identifier that orders the rows, in order to pass the unique ID to the command to return the next page of records, as shown in the following code example.</span></span>  
  
```vb  
Dim lastRecord As String = _  
  dataSet.Tables("Orders").Rows(pageSize - 1)("OrderID").ToString()  
```  
  
```csharp  
string lastRecord =
  dataSet.Tables["Orders"].Rows[pageSize - 1]["OrderID"].ToString();  
```  
  
 <span data-ttu-id="ed43a-114">Para devolver la siguiente página de registros mediante la sobrecarga del método **Fill** que toma los parámetros **startRecord** y **MaxRecords** , incremente el índice de registro actual por el tamaño de página y rellene la tabla.</span><span class="sxs-lookup"><span data-stu-id="ed43a-114">To return the next page of records using the overload of the **Fill** method that takes the **startRecord** and **maxRecords** parameters, increment the current record index by the page size and fill the table.</span></span> <span data-ttu-id="ed43a-115">Recuerde que el servidor de bases de datos devuelve todos los resultados de la consulta aunque solo se agregue una página de registros al objeto **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="ed43a-115">Remember that the database server returns the entire query results even though only one page of records is added to the **DataSet**.</span></span> <span data-ttu-id="ed43a-116">En el siguiente ejemplo de código se vacía el contenido de las filas de la tabla antes de rellenarse con la siguiente página de datos.</span><span class="sxs-lookup"><span data-stu-id="ed43a-116">In the following code example, the table rows are cleared before they are filled with the next page of data.</span></span> <span data-ttu-id="ed43a-117">Quizás se desee conservar un cierto número de filas devueltas en una caché local para reducir los viajes al servidor de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="ed43a-117">You might want to preserve a certain number of returned rows in a local cache to reduce trips to the database server.</span></span>  
  
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
  
 <span data-ttu-id="ed43a-118">Para devolver la siguiente página de registros sin que el servidor de bases de datos tenga que devolver toda la consulta, hay que especificar criterios restrictivos en la instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="ed43a-118">To return the next page of records without having the database server return the entire query, specify restrictive criteria to the SELECT statement.</span></span> <span data-ttu-id="ed43a-119">Como el ejemplo anterior conservaba el último registro devuelto, es posible utilizarlo en la cláusula WHERE con el fin de especificar un punto de partida para la consulta, como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="ed43a-119">Because the preceding example preserved the last record returned, you can use it in the WHERE clause to specify a starting point for the query, as shown in the following code example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ed43a-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ed43a-120">See also</span></span>

- [<span data-ttu-id="ed43a-121">Objetos DataAdapter y DataReader</span><span class="sxs-lookup"><span data-stu-id="ed43a-121">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="ed43a-122">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ed43a-122">ADO.NET Overview</span></span>](ado-net-overview.md)
