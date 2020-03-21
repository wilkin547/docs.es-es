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
# <a name="paging-through-a-query-result"></a><span data-ttu-id="ab374-102">Paginar un resultado de consulta</span><span class="sxs-lookup"><span data-stu-id="ab374-102">Paging Through a Query Result</span></span>
<span data-ttu-id="ab374-103">La paginación a través del resultado de una consulta es un proceso que consiste en devolver los resultados de una consulta en subconjuntos menores de datos, o páginas.</span><span class="sxs-lookup"><span data-stu-id="ab374-103">Paging through a query result is the process of returning the results of a query in smaller subsets of data, or pages.</span></span> <span data-ttu-id="ab374-104">Se trata de una práctica frecuente para presentar los resultados a un usuario en fragmentos pequeños y fáciles de administrar.</span><span class="sxs-lookup"><span data-stu-id="ab374-104">This is a common practice for displaying results to a user in small, easy-to-manage chunks.</span></span>  
  
 <span data-ttu-id="ab374-105">El **DataAdapter** proporciona un recurso para devolver solo una página de datos, a través de sobrecargas de la **Fill** método.</span><span class="sxs-lookup"><span data-stu-id="ab374-105">The **DataAdapter** provides a facility for returning only a page of data, through overloads of the **Fill** method.</span></span> <span data-ttu-id="ab374-106">Sin embargo, esta podría no ser la mejor opción para paginar a <xref:System.Data.DataTable> <xref:System.Data.DataSet> través de resultados de consultas grandes porque, aunque el **DataAdapter** rellena el destino o solo con los registros solicitados, los recursos para devolver toda la consulta se siguen utilizando.</span><span class="sxs-lookup"><span data-stu-id="ab374-106">However, this might not be the best choice for paging through large query results because, although the **DataAdapter** fills the target <xref:System.Data.DataTable> or <xref:System.Data.DataSet> with only the requested records, the resources to return the entire query are still used.</span></span> <span data-ttu-id="ab374-107">Para devolver una página de datos a partir de un origen de datos sin utilizar los recursos necesarios para devolver toda la consulta, hay que especificar otros criterios adicionales para la consulta que reduzcan las filas devueltas a las filas únicamente necesarias.</span><span class="sxs-lookup"><span data-stu-id="ab374-107">To return a page of data from a data source without using the resources to return the entire query, specify additional criteria for your query that reduce the rows returned to only those required.</span></span>  
  
 <span data-ttu-id="ab374-108">Para usar el método **Fill** para devolver una página de datos, especifique un parámetro **startRecord** para el primer registro de la página de datos y un parámetro **maxRecords** para el número de registros de la página de datos.</span><span class="sxs-lookup"><span data-stu-id="ab374-108">To use the **Fill** method to return a page of data, specify a **startRecord** parameter, for the first record in the page of data, and a **maxRecords** parameter, for the number of records in the page of data.</span></span>  
  
 <span data-ttu-id="ab374-109">En el ejemplo de código siguiente se muestra cómo utilizar el **Fill** método para devolver la primera página de un resultado de consulta donde el tamaño de página es de cinco registros.</span><span class="sxs-lookup"><span data-stu-id="ab374-109">The following code example shows how to use the **Fill** method to return the first page of a query result where the page size is five records.</span></span>  
  
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
  
 <span data-ttu-id="ab374-110">En el ejemplo anterior, el **DataSet** solo se rellena con cinco registros, pero se devuelve toda la tabla **Orders.**</span><span class="sxs-lookup"><span data-stu-id="ab374-110">In the previous example, the **DataSet** is only filled with five records, but the entire **Orders** table is returned.</span></span> <span data-ttu-id="ab374-111">Para rellenar el **DataSet** con esos mismos cinco registros, pero solo devolver cinco registros, use las cláusulas TOP y WHERE en la instrucción SQL, como en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="ab374-111">To fill the **DataSet** with those same five records, but only return five records, use the TOP and WHERE clauses in your SQL statement, as in the following code example.</span></span>  
  
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
  
 <span data-ttu-id="ab374-112">Hay que tener en cuenta que, al paginar a través del resultado de una consulta de esta forma, hay que conservar el identificador único por el que están ordenadas las filas con el fin de pasar el identificador único al comando con el fin de devolver la siguiente página de registros, tal y como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="ab374-112">Note that, when paging through the query results in this way, you must preserve the unique identifier that orders the rows, in order to pass the unique ID to the command to return the next page of records, as shown in the following code example.</span></span>  
  
```vb  
Dim lastRecord As String = _  
  dataSet.Tables("Orders").Rows(pageSize - 1)("OrderID").ToString()  
```  
  
```csharp  
string lastRecord =
  dataSet.Tables["Orders"].Rows[pageSize - 1]["OrderID"].ToString();  
```  
  
 <span data-ttu-id="ab374-113">Para devolver la página siguiente de registros mediante la sobrecarga del método **Fill** que toma los parámetros **startRecord** y **maxRecords,** incremente el índice de registros actual por el tamaño de página y rellene la tabla.</span><span class="sxs-lookup"><span data-stu-id="ab374-113">To return the next page of records using the overload of the **Fill** method that takes the **startRecord** and **maxRecords** parameters, increment the current record index by the page size and fill the table.</span></span> <span data-ttu-id="ab374-114">Recuerde que el servidor de base de datos devuelve todos los resultados de la consulta aunque solo se agregue una página de registros al conjunto de **datos**.</span><span class="sxs-lookup"><span data-stu-id="ab374-114">Remember that the database server returns the entire query results even though only one page of records is added to the **DataSet**.</span></span> <span data-ttu-id="ab374-115">En el siguiente ejemplo de código se vacía el contenido de las filas de la tabla antes de rellenarse con la siguiente página de datos.</span><span class="sxs-lookup"><span data-stu-id="ab374-115">In the following code example, the table rows are cleared before they are filled with the next page of data.</span></span> <span data-ttu-id="ab374-116">Quizás se desee conservar un cierto número de filas devueltas en una caché local para reducir los viajes al servidor de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="ab374-116">You might want to preserve a certain number of returned rows in a local cache to reduce trips to the database server.</span></span>  
  
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
  
 <span data-ttu-id="ab374-117">Para devolver la siguiente página de registros sin que el servidor de bases de datos tenga que devolver toda la consulta, hay que especificar criterios restrictivos en la instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="ab374-117">To return the next page of records without having the database server return the entire query, specify restrictive criteria to the SELECT statement.</span></span> <span data-ttu-id="ab374-118">Como el ejemplo anterior conservaba el último registro devuelto, es posible utilizarlo en la cláusula WHERE con el fin de especificar un punto de partida para la consulta, como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="ab374-118">Because the preceding example preserved the last record returned, you can use it in the WHERE clause to specify a starting point for the query, as shown in the following code example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ab374-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ab374-119">See also</span></span>

- [<span data-ttu-id="ab374-120">Objetos DataAdapter y DataReader</span><span class="sxs-lookup"><span data-stu-id="ab374-120">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="ab374-121">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ab374-121">ADO.NET Overview</span></span>](ado-net-overview.md)
