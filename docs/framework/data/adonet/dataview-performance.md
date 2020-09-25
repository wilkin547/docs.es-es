---
title: Rendimiento de DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 90820e49-9d46-41f6-9a3d-6c0741bbd8eb
ms.openlocfilehash: b2483becce31ab75d8b55b7a642c4ada83da59f6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183356"
---
# <a name="dataview-performance"></a><span data-ttu-id="14ed3-102">Rendimiento de DataView</span><span class="sxs-lookup"><span data-stu-id="14ed3-102">DataView Performance</span></span>

<span data-ttu-id="14ed3-103">En este tema se abordan las ventajas del uso de los métodos <xref:System.Data.DataView.Find%2A> y <xref:System.Data.DataView.FindRows%2A> de la clase <xref:System.Data.DataView>, y del almacenamiento en memoria caché de <xref:System.Data.DataView> en una aplicación web.</span><span class="sxs-lookup"><span data-stu-id="14ed3-103">This topic discusses the performance benefits of using the <xref:System.Data.DataView.Find%2A> and <xref:System.Data.DataView.FindRows%2A> methods of the <xref:System.Data.DataView> class, and of caching a <xref:System.Data.DataView> in a Web application.</span></span>  
  
## <a name="find-and-findrows"></a><span data-ttu-id="14ed3-104">Find y FindRows</span><span class="sxs-lookup"><span data-stu-id="14ed3-104">Find and FindRows</span></span>  

 <span data-ttu-id="14ed3-105"><xref:System.Data.DataView> construye un índice.</span><span class="sxs-lookup"><span data-stu-id="14ed3-105"><xref:System.Data.DataView> constructs an index.</span></span> <span data-ttu-id="14ed3-106">Un índice contiene claves generadas a partir de una o varias columnas de la tabla o la vista.</span><span class="sxs-lookup"><span data-stu-id="14ed3-106">An index contains keys built from one or more columns in the table or view.</span></span> <span data-ttu-id="14ed3-107">Dichas claves están almacenadas en una estructura que permite que <xref:System.Data.DataView> busque de forma rápida y eficiente la fila o filas asociadas a los valores de cada clave.</span><span class="sxs-lookup"><span data-stu-id="14ed3-107">These keys are stored in a structure that enables the <xref:System.Data.DataView> to find the row or rows associated with the key values quickly and efficiently.</span></span> <span data-ttu-id="14ed3-108">Las operaciones que usan el índice, como el filtrado y la ordenación, ven un aumento significativo del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="14ed3-108">Operations that use the index, such as filtering and sorting, see significant performance increases.</span></span> <span data-ttu-id="14ed3-109">El índice de <xref:System.Data.DataView> se compila cuando se crea <xref:System.Data.DataView> y cuando se modifica cualquier información de filtro u ordenación.</span><span class="sxs-lookup"><span data-stu-id="14ed3-109">The index for a <xref:System.Data.DataView> is built both when the <xref:System.Data.DataView> is created and when any of the sorting or filtering information is modified.</span></span> <span data-ttu-id="14ed3-110">La creación de <xref:System.Data.DataView> y el posterior establecimiento de información de filtro y ordenación hace que el índice se compile al menos dos veces: una cuando se crea <xref:System.Data.DataView> y la otra cuando se modifica cualquiera de las propiedades de ordenación y filtrado.</span><span class="sxs-lookup"><span data-stu-id="14ed3-110">Creating a <xref:System.Data.DataView> and then setting the sorting or filtering information later causes the index to be built at least twice: once when the <xref:System.Data.DataView> is created, and again when any of the sort or filter properties are modified.</span></span> <span data-ttu-id="14ed3-111">Para obtener más información sobre el filtrado y la ordenación con <xref:System.Data.DataView> , vea [filtrar con DataView](filtering-with-dataview-linq-to-dataset.md) y [ordenar con DataView](sorting-with-dataview-linq-to-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="14ed3-111">For more information about filtering and sorting with <xref:System.Data.DataView>, see [Filtering with DataView](filtering-with-dataview-linq-to-dataset.md) and [Sorting with DataView](sorting-with-dataview-linq-to-dataset.md).</span></span>  
  
 <span data-ttu-id="14ed3-112">Si desea devolver los resultados de una consulta determinada en los datos, en lugar de proporcionar una vista dinámica de un subconjunto de los datos, para conseguir el máximo rendimiento puede utilizar los métodos <xref:System.Data.DataView.Find%2A> o <xref:System.Data.DataView.FindRows%2A> de la <xref:System.Data.DataView>, en lugar de establecer la propiedad <xref:System.Data.DataView.RowFilter%2A>.</span><span class="sxs-lookup"><span data-stu-id="14ed3-112">If you want to return the results of a particular query on the data, as opposed to providing a dynamic view of a subset of the data, you can use the <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> methods of the <xref:System.Data.DataView>, rather than setting the <xref:System.Data.DataView.RowFilter%2A> property.</span></span> <span data-ttu-id="14ed3-113">La propiedad <xref:System.Data.DataView.RowFilter%2A> es más idónea en una aplicación enlazada a datos donde un control enlazado muestra resultados filtrados.</span><span class="sxs-lookup"><span data-stu-id="14ed3-113">The <xref:System.Data.DataView.RowFilter%2A> property is best used in a data-bound application where a bound control displays filtered results.</span></span> <span data-ttu-id="14ed3-114">El establecimiento de la propiedad <xref:System.Data.DataView.RowFilter%2A> hace que se recompile el índice de los datos, lo que agrega sobrecarga a la aplicación y reduce el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="14ed3-114">Setting the <xref:System.Data.DataView.RowFilter%2A> property rebuilds the index for the data, adding overhead to your application and decreasing performance.</span></span> <span data-ttu-id="14ed3-115">Los métodos <xref:System.Data.DataView.Find%2A> y <xref:System.Data.DataView.FindRows%2A> utilizan el índice actual, sin necesidad de recompilarlo.</span><span class="sxs-lookup"><span data-stu-id="14ed3-115">The <xref:System.Data.DataView.Find%2A> and <xref:System.Data.DataView.FindRows%2A> methods use the current index without requiring the index to be rebuilt.</span></span> <span data-ttu-id="14ed3-116">Si va a llamar a <xref:System.Data.DataView.Find%2A> o a <xref:System.Data.DataView.FindRows%2A> una única vez, entonces debería utilizar el <xref:System.Data.DataView> existente.</span><span class="sxs-lookup"><span data-stu-id="14ed3-116">If you are going to call <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> only once, then you should use the existing <xref:System.Data.DataView>.</span></span> <span data-ttu-id="14ed3-117">Si va a llamar a <xref:System.Data.DataView.Find%2A> o a <xref:System.Data.DataView.FindRows%2A> varias veces, debería crear un nuevo <xref:System.Data.DataView> para recompilar el índice en la columna en la que desea buscar y, a continuación, llamar a los métodos <xref:System.Data.DataView.Find%2A> o <xref:System.Data.DataView.FindRows%2A>.</span><span class="sxs-lookup"><span data-stu-id="14ed3-117">If you are going to call <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> multiple times, you should create a new <xref:System.Data.DataView> to rebuild the index on the column you want to search on, and then call the <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> methods.</span></span> <span data-ttu-id="14ed3-118">Para obtener más información sobre <xref:System.Data.DataView.Find%2A> los <xref:System.Data.DataView.FindRows%2A> métodos y, vea [Buscar filas](./dataset-datatable-dataview/finding-rows.md).</span><span class="sxs-lookup"><span data-stu-id="14ed3-118">For more information about the <xref:System.Data.DataView.Find%2A> and <xref:System.Data.DataView.FindRows%2A> methods, see [Finding Rows](./dataset-datatable-dataview/finding-rows.md).</span></span>  
  
 <span data-ttu-id="14ed3-119">El ejemplo siguiente utiliza el método <xref:System.Data.DataView.Find%2A> para buscar un contacto con el apellido "Zhu".</span><span class="sxs-lookup"><span data-stu-id="14ed3-119">The following example uses the <xref:System.Data.DataView.Find%2A> method to find a contact with the last name "Zhu".</span></span>  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryOrderByFind](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromqueryorderbyfind)]
 [!code-vb[DP DataView Samples#LDVFromQueryOrderByFind](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromqueryorderbyfind)]  
  
 <span data-ttu-id="14ed3-120">En el ejemplo siguiente se usa el método <xref:System.Data.DataView.FindRows%2A> para buscar todos los productos de color rojo.</span><span class="sxs-lookup"><span data-stu-id="14ed3-120">The following example uses the <xref:System.Data.DataView.FindRows%2A> method to find all the red colored products.</span></span>  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryFindRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromqueryfindrows)]
 [!code-vb[DP DataView Samples#LDVFromQueryFindRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromqueryfindrows)]  
  
## <a name="aspnet"></a><span data-ttu-id="14ed3-121">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="14ed3-121">ASP.NET</span></span>  

 <span data-ttu-id="14ed3-122">ASP.NET dispone de un mecanismo de almacenamiento en memoria caché de objetos cuya creación en memoria requiere una gran cantidad de recursos del servidor.</span><span class="sxs-lookup"><span data-stu-id="14ed3-122">ASP.NET has a caching mechanism that allows you to store objects that require extensive server resources to create in memory.</span></span> <span data-ttu-id="14ed3-123">Si se almacenan estos tipos de recursos en la memoria caché se puede mejorar de forma significativa el rendimiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="14ed3-123">Caching these types of resources can significantly improve the performance of your application.</span></span> <span data-ttu-id="14ed3-124">La clase <xref:System.Web.Caching.Cache> implementa el almacenamiento en memoria caché, con instancias de la memoria caché privadas para cada aplicación.</span><span class="sxs-lookup"><span data-stu-id="14ed3-124">Caching is implemented by the <xref:System.Web.Caching.Cache> class, with cache instances that are private to each application.</span></span> <span data-ttu-id="14ed3-125">Dado que la creación de un objeto <xref:System.Data.DataView> nuevo puede consumir muchos recursos, quizás desee utilizar esta funcionalidad de almacenamiento en caché en aplicaciones web para que <xref:System.Data.DataView> no tenga que recompilarse cada vez que se actualiza la página web.</span><span class="sxs-lookup"><span data-stu-id="14ed3-125">Because creating a new <xref:System.Data.DataView> object can be resource intensive, you might want to use this caching functionality in Web applications so that the <xref:System.Data.DataView> does not have to be rebuilt every time the Web page is refreshed.</span></span>  
  
 <span data-ttu-id="14ed3-126">En el ejemplo siguiente, <xref:System.Data.DataView> se almacena en caché para que los datos no tengan que volver a ordenarse cuando la página se actualice.</span><span class="sxs-lookup"><span data-stu-id="14ed3-126">In the following example, the <xref:System.Data.DataView> is cached so that the data does not have to be re-sorted when the page is refreshed.</span></span>  
  
```vb  
If (Cache("ordersView") = Nothing) Then  
  
Dim dataSet As New DataSet()  
  
   FillDataSet(dataSet)  
  
   Dim orders As DataTable = dataSet.Tables("SalesOrderHeader")  
  
   Dim query = _  
                    From order In orders.AsEnumerable() _  
                    Where order.Field(Of Boolean)("OnlineOrderFlag") = True _  
                    Order By order.Field(Of Decimal)("TotalDue") _  
                    Select order  
  
   Dim view As DataView = query.AsDataView()  
  
   Cache.Insert("ordersView", view)  
  
End If  
  
Dim ordersView = CType(Cache("ordersView"), DataView)  
  
GridView1.DataSource = ordersView  
GridView1.DataBind()  
```  
  
```csharp  
if (Cache["ordersView"] == null)  
{  
   // Fill the DataSet.
   DataSet dataSet = FillDataSet();  
  
   DataTable orders = dataSet.Tables["SalesOrderHeader"];  
  
   EnumerableRowCollection<DataRow> query =  
                        from order in orders.AsEnumerable()  
                        where order.Field<bool>("OnlineOrderFlag") == true  
                        orderby order.Field<decimal>("TotalDue")  
                        select order;  
  
   DataView view = query.AsDataView();  
   Cache.Insert("ordersView", view);  
}  
  
DataView ordersView = (DataView)Cache["ordersView"];  
  
GridView1.DataSource = ordersView;  
GridView1.DataBind();  
```  
  
## <a name="see-also"></a><span data-ttu-id="14ed3-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="14ed3-127">See also</span></span>

- [<span data-ttu-id="14ed3-128">Enlace de datos y LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="14ed3-128">Data Binding and LINQ to DataSet</span></span>](data-binding-and-linq-to-dataset.md)
