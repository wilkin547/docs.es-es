---
title: Buscar filas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5da300e2-74c0-4d13-9202-fc20ed8212d8
ms.openlocfilehash: dc0661e29e6d3ee5aa3f54179e8abf265cd67d58
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186983"
---
# <a name="finding-rows"></a><span data-ttu-id="de102-102">Buscar filas</span><span class="sxs-lookup"><span data-stu-id="de102-102">Finding Rows</span></span>

<span data-ttu-id="de102-103">Es posible buscar filas en función de los valores clave de ordenación mediante los métodos <xref:System.Data.DataView.Find%2A> y <xref:System.Data.DataView.FindRows%2A> de la <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="de102-103">You can search for rows according to their sort key values by using the <xref:System.Data.DataView.Find%2A> and <xref:System.Data.DataView.FindRows%2A> methods of the <xref:System.Data.DataView>.</span></span> <span data-ttu-id="de102-104">La distinción de mayúsculas y minúsculas de los valores de búsqueda en los métodos **Find** y **FindRows** viene determinada por la propiedad **CaseSensitive** del subyacente <xref:System.Data.DataTable> .</span><span class="sxs-lookup"><span data-stu-id="de102-104">The case sensitivity of search values in the **Find** and **FindRows** methods is determined by the **CaseSensitive** property of the underlying <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="de102-105">Los valores de búsqueda deben coincidir en su totalidad con los valores de clave de ordenación existentes para que se devuelva un resultado.</span><span class="sxs-lookup"><span data-stu-id="de102-105">Search values must match existing sort key values in their entirety in order to return a result.</span></span>  
  
 <span data-ttu-id="de102-106">El método **Find** devuelve un entero con el índice de <xref:System.Data.DataRowView> que coincide con los criterios de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="de102-106">The **Find** method returns an integer with the index of the <xref:System.Data.DataRowView> that matches the search criteria.</span></span> <span data-ttu-id="de102-107">Si hay más de una fila que coincide con los criterios de búsqueda, solo se devuelve el índice de la primera **DataRowView** coincidente.</span><span class="sxs-lookup"><span data-stu-id="de102-107">If more than one row matches the search criteria, only the index of the first matching **DataRowView** is returned.</span></span> <span data-ttu-id="de102-108">Si no se encuentran coincidencias, **Find** devuelve-1.</span><span class="sxs-lookup"><span data-stu-id="de102-108">If no matches are found, **Find** returns -1.</span></span>  
  
 <span data-ttu-id="de102-109">Para devolver los resultados de la búsqueda que coinciden con varias filas, use el método **FindRows** .</span><span class="sxs-lookup"><span data-stu-id="de102-109">To return search results that match multiple rows, use the **FindRows** method.</span></span> <span data-ttu-id="de102-110">**FindRows** funciona igual que el método **Find** , con la salvedad de que devuelve una matriz de **DataRowView** que hace referencia a todas las filas coincidentes de **DataView**.</span><span class="sxs-lookup"><span data-stu-id="de102-110">**FindRows** works just like the **Find** method, except that it returns a **DataRowView** array that references all matching rows in the **DataView**.</span></span> <span data-ttu-id="de102-111">Si no se encuentran coincidencias, la matriz de **DataRowView** estará vacía.</span><span class="sxs-lookup"><span data-stu-id="de102-111">If no matches are found, the **DataRowView** array will be empty.</span></span>  
  
 <span data-ttu-id="de102-112">Para usar los métodos **Find** o **FindRows** , debe especificar un criterio de ordenación estableciendo el valor de **ApplyDefaultSort** en **true** o mediante la propiedad **Sort** .</span><span class="sxs-lookup"><span data-stu-id="de102-112">To use the **Find** or **FindRows** methods you must specify a sort order either by setting **ApplyDefaultSort** to **true** or by using the **Sort** property.</span></span> <span data-ttu-id="de102-113">Si no se especifica ningún criterio de ordenación, se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="de102-113">If no sort order is specified, an exception is thrown.</span></span>  
  
 <span data-ttu-id="de102-114">Los métodos **Find** y **FindRows** toman una matriz de valores como entrada cuya longitud coincide con el número de columnas en el criterio de ordenación.</span><span class="sxs-lookup"><span data-stu-id="de102-114">The **Find** and **FindRows** methods take an array of values as input whose length matches the number of columns in the sort order.</span></span> <span data-ttu-id="de102-115">En el caso de una ordenación por una única columna, puede pasar un único valor.</span><span class="sxs-lookup"><span data-stu-id="de102-115">In the case of a sort on a single column, you can pass a single value.</span></span> <span data-ttu-id="de102-116">Para los criterios de ordenación que contienen varias columnas, debe pasar una matriz de objetos.</span><span class="sxs-lookup"><span data-stu-id="de102-116">For sort orders containing multiple columns, you pass an array of objects.</span></span> <span data-ttu-id="de102-117">Tenga en cuenta que para una ordenación en varias columnas, los valores de la matriz de objetos deben coincidir con el orden de las columnas especificadas en la propiedad **Sort** de **DataView**.</span><span class="sxs-lookup"><span data-stu-id="de102-117">Note that for a sort on multiple columns, the values in the object array must match the order of the columns specified in the **Sort** property of the **DataView**.</span></span>  
  
 <span data-ttu-id="de102-118">En el ejemplo de código siguiente se muestra el método **Find** al que se llama en una **DataView** con un criterio de ordenación de una sola columna.</span><span class="sxs-lookup"><span data-stu-id="de102-118">The following code example shows the **Find** method being called against a **DataView** with a single column sort order.</span></span>  
  
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
  
 <span data-ttu-id="de102-119">Si la propiedad **Sort** especifica varias columnas, debe pasar una matriz de objetos con los valores de búsqueda de cada columna en el orden especificado por la propiedad **Sort** , como en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="de102-119">If your **Sort** property specifies multiple columns, you must pass an object array with the search values for each column in the order specified by the **Sort** property, as in the following code example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="de102-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="de102-120">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="de102-121">Objetos DataView</span><span class="sxs-lookup"><span data-stu-id="de102-121">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="de102-122">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="de102-122">ADO.NET Overview</span></span>](../ado-net-overview.md)
