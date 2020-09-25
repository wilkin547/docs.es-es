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
# <a name="dataview-performance"></a>Rendimiento de DataView

En este tema se abordan las ventajas del uso de los métodos <xref:System.Data.DataView.Find%2A> y <xref:System.Data.DataView.FindRows%2A> de la clase <xref:System.Data.DataView>, y del almacenamiento en memoria caché de <xref:System.Data.DataView> en una aplicación web.  
  
## <a name="find-and-findrows"></a>Find y FindRows  

 <xref:System.Data.DataView> construye un índice. Un índice contiene claves generadas a partir de una o varias columnas de la tabla o la vista. Dichas claves están almacenadas en una estructura que permite que <xref:System.Data.DataView> busque de forma rápida y eficiente la fila o filas asociadas a los valores de cada clave. Las operaciones que usan el índice, como el filtrado y la ordenación, ven un aumento significativo del rendimiento. El índice de <xref:System.Data.DataView> se compila cuando se crea <xref:System.Data.DataView> y cuando se modifica cualquier información de filtro u ordenación. La creación de <xref:System.Data.DataView> y el posterior establecimiento de información de filtro y ordenación hace que el índice se compile al menos dos veces: una cuando se crea <xref:System.Data.DataView> y la otra cuando se modifica cualquiera de las propiedades de ordenación y filtrado. Para obtener más información sobre el filtrado y la ordenación con <xref:System.Data.DataView> , vea [filtrar con DataView](filtering-with-dataview-linq-to-dataset.md) y [ordenar con DataView](sorting-with-dataview-linq-to-dataset.md).  
  
 Si desea devolver los resultados de una consulta determinada en los datos, en lugar de proporcionar una vista dinámica de un subconjunto de los datos, para conseguir el máximo rendimiento puede utilizar los métodos <xref:System.Data.DataView.Find%2A> o <xref:System.Data.DataView.FindRows%2A> de la <xref:System.Data.DataView>, en lugar de establecer la propiedad <xref:System.Data.DataView.RowFilter%2A>. La propiedad <xref:System.Data.DataView.RowFilter%2A> es más idónea en una aplicación enlazada a datos donde un control enlazado muestra resultados filtrados. El establecimiento de la propiedad <xref:System.Data.DataView.RowFilter%2A> hace que se recompile el índice de los datos, lo que agrega sobrecarga a la aplicación y reduce el rendimiento. Los métodos <xref:System.Data.DataView.Find%2A> y <xref:System.Data.DataView.FindRows%2A> utilizan el índice actual, sin necesidad de recompilarlo. Si va a llamar a <xref:System.Data.DataView.Find%2A> o a <xref:System.Data.DataView.FindRows%2A> una única vez, entonces debería utilizar el <xref:System.Data.DataView> existente. Si va a llamar a <xref:System.Data.DataView.Find%2A> o a <xref:System.Data.DataView.FindRows%2A> varias veces, debería crear un nuevo <xref:System.Data.DataView> para recompilar el índice en la columna en la que desea buscar y, a continuación, llamar a los métodos <xref:System.Data.DataView.Find%2A> o <xref:System.Data.DataView.FindRows%2A>. Para obtener más información sobre <xref:System.Data.DataView.Find%2A> los <xref:System.Data.DataView.FindRows%2A> métodos y, vea [Buscar filas](./dataset-datatable-dataview/finding-rows.md).  
  
 El ejemplo siguiente utiliza el método <xref:System.Data.DataView.Find%2A> para buscar un contacto con el apellido "Zhu".  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryOrderByFind](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromqueryorderbyfind)]
 [!code-vb[DP DataView Samples#LDVFromQueryOrderByFind](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromqueryorderbyfind)]  
  
 En el ejemplo siguiente se usa el método <xref:System.Data.DataView.FindRows%2A> para buscar todos los productos de color rojo.  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryFindRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromqueryfindrows)]
 [!code-vb[DP DataView Samples#LDVFromQueryFindRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromqueryfindrows)]  
  
## <a name="aspnet"></a>ASP.NET  

 ASP.NET dispone de un mecanismo de almacenamiento en memoria caché de objetos cuya creación en memoria requiere una gran cantidad de recursos del servidor. Si se almacenan estos tipos de recursos en la memoria caché se puede mejorar de forma significativa el rendimiento de la aplicación. La clase <xref:System.Web.Caching.Cache> implementa el almacenamiento en memoria caché, con instancias de la memoria caché privadas para cada aplicación. Dado que la creación de un objeto <xref:System.Data.DataView> nuevo puede consumir muchos recursos, quizás desee utilizar esta funcionalidad de almacenamiento en caché en aplicaciones web para que <xref:System.Data.DataView> no tenga que recompilarse cada vez que se actualiza la página web.  
  
 En el ejemplo siguiente, <xref:System.Data.DataView> se almacena en caché para que los datos no tengan que volver a ordenarse cuando la página se actualice.  
  
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
  
## <a name="see-also"></a>Consulte también

- [Enlace de datos y LINQ to DataSet](data-binding-and-linq-to-dataset.md)
